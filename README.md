# Pregunta 1 — Caso de Estudio: Vendematica.pe (10 puntos)
## Empresa: Redy Farmacia — Arquitectura Tecnológica en 3 Capas

---

## 1. Dimensionamiento previo (base para el hardware)

Antes de diseñar la arquitectura, se calculan los requerimientos reales del sistema.

### Almacenamiento de datos

```
Transacciones por día   = 50,000
Tamaño por transacción  = 0.4 MB
─────────────────────────────────────────────
Almacenamiento diario   = 50,000 × 0.4 = 20,000 MB = ~20 GB/día
Almacenamiento mensual  = 20 GB × 30   = 600 GB/mes
Almacenamiento anual    = 20 GB × 365  = ~7,300 GB ≈ 7.3 TB/año
```

→ Se recomienda un disco SSD de **2 TB** para el primer año con margen de crecimiento, escalable en cloud.

### Carga concurrente (pico de transacciones)

```
Lunes a Viernes: 8h – 23h = 15 horas activas
50,000 transacciones / 15 h = ~3,333 tx/hora = ~56 tx/minuto

Domingo: 9h – 12h = 3 horas activas
Carga domingo es menor, se asume ~10% del volumen semanal
```

→ El servidor de aplicación debe soportar picos de al menos **60 tx/minuto** de forma estable.

### Usuarios concurrentes estimados

```
100,000 clientes registrados
Se estima que el 5–10% estará activo simultáneamente en hora pico
100,000 × 10% = ~10,000 usuarios concurrentes en pico
```

→ El servidor web debe escalar para **10,000 conexiones simultáneas**.

---

## 2. Diagrama de Arquitectura en 3 Capas

```
┌─────────────────────────────────────────────────────────────────┐
│                     INTERNET (HTTPS / TLS)                      │
└──────────────────────────┬──────────────────────────────────────┘
                           │
┌──────────────────────────▼──────────────────────────────────────┐
│               CAPA 1: PRESENTACIÓN                              │
│                                                                  │
│  Dispositivos: PC / Laptop / Smartphone / Tablet                │
│  SO Cliente:   Windows, macOS, Linux, Android, iOS              │
│  Software:     React.js + Bootstrap 5 (SPA responsive)         │
│  Protocolo:    HTTPS — puerto 443                               │
│  Navegadores:  Chrome, Firefox, Safari, Edge                    │
└──────────────────────────┬──────────────────────────────────────┘
                           │ HTTPS / REST API (JSON)
┌──────────────────────────▼──────────────────────────────────────┐
│               CAPA 2: APLICACIÓN (Microsoft Azure)              │
│                                                                  │
│  SO:           Ubuntu Server 24.04 LTS                          │
│  Web Server:   Nginx (balanceador + proxy inverso)              │
│  Runtime:      Node.js v20 LTS                                  │
│  Seguridad:    Certificado SSL/TLS, Firewall Azure, CORS        │
│  Cloud:        Azure App Service (escalado automático)          │
│                                                                  │
│  Hardware (Azure B2s → escalar a B4ms según demanda):           │
│    CPU: 4 vCPUs  |  RAM: 8 GB  |  Red: 1 Gbps                  │
└──────────────────────────┬──────────────────────────────────────┘
                           │ TCP / Puerto 5432
┌──────────────────────────▼──────────────────────────────────────┐
│               CAPA 3: DATOS (Microsoft Azure)                   │
│                                                                  │
│  SO:           Ubuntu Server 24.04 LTS                          │
│  DBMS:         PostgreSQL 16                                     │
│  Cloud:        Azure Database for PostgreSQL (Flexible Server)  │
│  Backup:       Automático diario — retención 7 días             │
│  Seguridad:    VNet privada, encriptación en reposo (AES-256)   │
│                                                                  │
│  Hardware (Azure D2s_v3):                                       │
│    CPU: 4 vCPUs  |  RAM: 16 GB  |  Disco SSD: 2 TB             │
└─────────────────────────────────────────────────────────────────┘
```

> **Nota:** El diagrama visual se construye en Ms. Word replicando esta estructura de 3 bloques apilados verticalmente con flechas entre capas.

---

## 3. Sustentación por Capa

---

### C01 + C02 — Capa de Presentación: Software y Sistema Operativo

#### Software elegido: React.js + Bootstrap 5

React.js es una librería JavaScript de código abierto mantenida por Meta, ideal para construir interfaces web modernas tipo SPA (Single Page Application). Se eligió porque:

- Permite desarrollar **componentes reutilizables** (catálogo de productos, carrito, seguimiento de pedido), reduciendo el tiempo y costo de desarrollo, lo cual es clave para un startup con recursos limitados.
- Gestiona el estado de la aplicación de forma eficiente, lo que se traduce en una **experiencia fluida** sin recargas completas de página al consultar el estado del delivery o actualizar el carrito.
- Tiene una comunidad enorme y documentación extensa, facilitando el mantenimiento futuro.

Bootstrap 5 complementa a React proporcionando un sistema de grillas y componentes visuales responsivos que se adaptan automáticamente a **PC, laptop, tablet y smartphone**, cubriendo el requisito de acceso multi-dispositivo del enunciado.

#### Sistema Operativo: Windows / macOS / Android / iOS (lado cliente)

La capa de presentación corre en el dispositivo del usuario final. No requiere instalación de software adicional; el acceso se realiza únicamente a través de un **navegador web** (Chrome, Firefox, Safari, Edge), lo que garantiza compatibilidad universal sin costos de licencia para el startup.

---

### C01 + C02 — Capa de Aplicación: Software y Sistema Operativo

#### Software elegido: Node.js v20 LTS + Nginx

**Node.js** fue seleccionado como runtime del servidor de aplicación por las siguientes razones:

- Arquitectura **event-driven y no bloqueante (non-blocking I/O)**: Node.js puede gestionar miles de conexiones concurrentes con un solo hilo, lo que lo hace ideal para soportar los **10,000 usuarios concurrentes** estimados en hora pico, sin necesidad de hardware costoso.
- Permite construir una **API REST** en formato JSON que sirve tanto a la versión web como a la versión móvil desde el mismo backend, evitando duplicar lógica de negocio.
- Ecosistema npm con librerías para autenticación (JWT), pagos, ORM (Sequelize/Prisma) y envío de correos, acelerando el desarrollo para un startup.
- Licencia MIT — completamente gratuito, sin costos de licencia.

**Nginx** actúa como proxy inverso y balanceador de carga frente a Node.js:

- Gestiona las conexiones HTTPS entrantes y distribuye la carga entre instancias de Node.js.
- Sirve los archivos estáticos del frontend directamente (HTML, CSS, JS compilado de React), descargando trabajo al servidor de aplicación.
- Ofrece protección frente a ataques de tipo DDoS mediante limitación de tasa (rate limiting).
- Es el servidor web más usado en el mundo (38% del mercado) por su estabilidad y alto rendimiento bajo carga.

#### Sistema Operativo: Ubuntu Server 24.04 LTS

Ubuntu Server 24.04 LTS (Long Term Support) fue elegido porque:

- Es **gratuito y de código abierto**, eliminando costos de licencia de sistema operativo, crucial para un startup con presupuesto ajustado.
- La versión LTS garantiza **5 años de soporte y actualizaciones de seguridad** (hasta 2029), reduciendo riesgos operativos.
- Tiene excelente compatibilidad con Node.js, Nginx y las herramientas de despliegue de Microsoft Azure.
- Es el SO más usado en servidores cloud a nivel mundial, con amplia documentación y comunidad de soporte.

#### Hardware: Azure App Service (Plan B2s → escalable a B4ms)

| Componente | Especificación | Justificación |
|------------|---------------|---------------|
| vCPUs      | 4 núcleos     | Soporte a 56 tx/minuto en pico con margen holgado |
| RAM        | 8 GB          | Node.js no es intensivo en memoria; suficiente para 10k conexiones |
| Red        | 1 Gbps        | Transferencia fluida de datos JSON ligeros (<1KB por request) |
| Escalado   | Automático (Azure) | En picos de tráfico, Azure escala horizontalmente sin intervención manual |

Se optó por **Azure App Service** en lugar de servidor físico propio porque: el startup evita la inversión inicial en hardware, solo paga por uso, y puede escalar en minutos ante un crecimiento inesperado de clientes.

---

### C01 + C02 — Capa de Datos: Software y Sistema Operativo

#### Software elegido: PostgreSQL 16

PostgreSQL fue seleccionado como sistema gestor de base de datos relacional (RDBMS) por las siguientes razones:

- **Cumplimiento ACID** (Atomicidad, Consistencia, Aislamiento, Durabilidad): garantiza que cada transacción de compra se registre de forma íntegra o no se registre en absoluto, evitando inconsistencias como pedidos sin pago o pagos sin pedido.
- Soporta **datos complejos y relaciones entre entidades**: clientes, empleados, productos, pedidos, estados de delivery, formas de pago — todas entidades relacionadas que se modelan de forma natural en un esquema relacional.
- La tabla de **trazabilidad del delivery** (con historial de estados: Recibida → Aceptada → Rechazada, con fecha/hora, repartidor y observaciones) se implementa eficientemente con tablas de auditoría e índices en PostgreSQL.
- Soporte nativo a **JSONB** para almacenar datos semiestructurados si en el futuro se requiere flexibilidad de esquema.
- Es **gratuito y de código abierto** (licencia PostgreSQL), sin costos de licencia.
- Ampliamente probado en aplicaciones de e-commerce de alta demanda (Shopify, Instagram originalmente usaron PostgreSQL).

#### Sistema Operativo: Ubuntu Server 24.04 LTS

Misma justificación que la capa de aplicación: gratuito, estable, soporte LTS hasta 2029, compatible con PostgreSQL y los servicios de Azure. Se mantiene el mismo SO en ambas capas para simplificar la administración del sistema y reducir la curva de aprendizaje del equipo técnico.

#### Hardware: Azure Database for PostgreSQL — Flexible Server (D2s_v3)

| Componente | Especificación   | Justificación |
|------------|-----------------|---------------|
| vCPUs      | 4 núcleos       | Consultas concurrentes sin degradación en hora pico |
| RAM        | 16 GB           | Cache de datos frecuentes en memoria, reduciendo lecturas a disco |
| Disco      | SSD 2 TB        | Cubre 7.3 TB/año calculados con margen; SSD garantiza baja latencia de I/O |
| Backup     | Automático diario | Recuperación ante desastres sin pérdida de datos mayor a 24h |
| Red        | VNet privada Azure | La base de datos NO es accesible desde internet; solo desde la capa de aplicación |

---

### C04 — Herramientas de Integración y Seguridad

#### Seguridad de la información

| Herramienta / Componente | Capa | Función |
|--------------------------|------|---------|
| **HTTPS / TLS 1.3**      | Presentación ↔ Aplicación | Encriptación del tráfico entre el navegador del cliente y el servidor. Impide la interceptación de datos de pago y credenciales. |
| **Certificado SSL (Let's Encrypt)** | Aplicación | Gratuito, renovación automática cada 90 días. Habilita el candado de seguridad en el navegador. |
| **Firewall de Azure (NSG)**  | Aplicación + Datos | Bloquea todo el tráfico no autorizado. Solo permite el puerto 443 (HTTPS) desde internet hacia la capa de aplicación. La capa de datos solo acepta conexiones internas de la capa de aplicación. |
| **VNet privada de Azure** | Datos | La base de datos PostgreSQL vive en una red privada virtual. No tiene IP pública expuesta a internet. |
| **JWT (JSON Web Tokens)** | Aplicación | Autenticación stateless para los endpoints de la API. Cada cliente autenticado recibe un token firmado con expiración, evitando accesos no autorizados. |
| **Encriptación en reposo (AES-256)** | Datos | Azure encripta automáticamente todos los datos almacenados en disco. |

#### Integración entre capas

| Herramienta | Función |
|-------------|---------|
| **API REST (JSON sobre HTTPS)** | Protocolo de comunicación entre la capa de presentación y la capa de aplicación. Estandarizado, compatible con web y móvil simultáneamente. |
| **ORM Sequelize / Prisma** | Capa de abstracción entre Node.js y PostgreSQL. Facilita las consultas a la base de datos y previene inyección SQL. |
| **Azure Monitor + Log Analytics** | Monitoreo de disponibilidad, tiempos de respuesta y errores en tiempo real. Permite detectar cuellos de botella antes de que afecten al usuario. |
| **Azure CDN** | Distribuye los archivos estáticos del frontend (React compilado) desde servidores cercanos al usuario, reduciendo la latencia de carga inicial de la tienda. |

---

## 4. Resumen ejecutivo de la arquitectura

| Capa          | Software            | Sistema Operativo        | Hardware (Azure)              |
|---------------|---------------------|--------------------------|-------------------------------|
| Presentación  | React.js + Bootstrap 5 | Windows / macOS / Android / iOS (cliente) | PC, Laptop, Smartphone, Tablet |
| Aplicación    | Node.js v20 + Nginx | Ubuntu Server 24.04 LTS  | 4 vCPU, 8 GB RAM — App Service B2s (escalable) |
| Datos         | PostgreSQL 16        | Ubuntu Server 24.04 LTS  | 4 vCPU, 16 GB RAM, SSD 2 TB — Azure DB Flexible Server |

**Infraestructura cloud:** Microsoft Azure — pago por uso, sin inversión inicial en hardware físico.  
**Costo inicial estimado:** ~$80–$150 USD/mes en Azure (plan básico), escalable conforme crezca la base de clientes.

# Solución — Preguntas 2 y 3: Gestión de Procesos (Round Robin)

---

## Pregunta 2 — Round Robin con Quantum = 4 (5 puntos)

### Datos del problema

| Proceso | Arrival Time (AT) | Burst Time (BT) |
|---------|:-----------------:|:---------------:|
| P1      | 4                 | 5               |
| P2      | 1                 | 4               |
| P3      | 6                 | 6               |
| P4      | 3                 | 2               |

**Quantum = 4**

---

### Paso 1 — Ordenar por llegada

Orden de llegada: **P2 (t=1) → P4 (t=3) → P1 (t=4) → P3 (t=6)**

---

### Paso 2 — Simulación de la cola Round Robin

Llevamos una columna de **Remaining Burst (REM)** que se va reduciendo.

| Tiempo | Proceso en CPU | REM antes | Ejecuta | REM después | Nota                        |
|:------:|:--------------:|:---------:|:-------:|:-----------:|-----------------------------|
| 1      | P2             | 4         | 4       | 0           | P2 termina en t=5           |
| 5      | P4             | 2         | 2       | 0           | P4 termina en t=7 (llegó t=3, ya estaba en cola) |
| 7      | P1             | 5         | 4       | 1           | P1 usa su quantum completo  |
| 11     | P3             | 6         | 4       | 2           | P3 usa su quantum completo  |
| 15     | P1             | 1         | 1       | 0           | P1 termina en t=16          |
| 16     | P3             | 2         | 2       | 0           | P3 termina en t=18          |

---

### Paso 3 — Diagrama de Gantt

```
| P2 | P4 | P1 | P3 | P1 | P3 |
1    5    7    11   15   16   18
```

---

### Paso 4 — Tabla de resultados

Fórmulas:
- **CT** (Completion Time) = tiempo en que el proceso termina en el Gantt
- **WT** (Waiting Time) = CT − AT − BT
- **AWT** = promedio de todos los WT
- **ACT** = promedio de todos los CT

| Proceso | AT | BT | CT | WT = CT − AT − BT |
|---------|:--:|:--:|:--:|:-----------------:|
| P1      | 4  | 5  | 16 | 16 − 4 − 5 = **7**  |
| P2      | 1  | 4  | 5  | 5 − 1 − 4 = **0**   |
| P3      | 6  | 6  | 18 | 18 − 6 − 6 = **6**  |
| P4      | 3  | 2  | 7  | 7 − 3 − 2 = **2**   |

### Paso 5 — AWT y ACT

```
AWT = (7 + 0 + 6 + 2) / 4 = 15 / 4 = 3.75
ACT = (16 + 5 + 18 + 7) / 4 = 46 / 4 = 11.50
```

| Métrica | Valor |
|---------|:-----:|
| **AWT** | **3.75** |
| **ACT** | **11.50** |

---
---

## Pregunta 3 — Round Robin: comparar Quantum = 2 vs Quantum = 3 (5 puntos)

### Datos del problema

| Proceso | Arrival Time (AT) | Burst Time (BT) |
|---------|:-----------------:|:---------------:|
| P1      | 0                 | 4               |
| P2      | 2                 | 2               |
| P3      | 4                 | 4               |
| P4      | 6                 | 5               |

---

## 3.1 — Quantum = 2

### Paso 1 — Simulación

| Tiempo | Proceso en CPU | REM antes | Ejecuta | REM después | Nota                    |
|:------:|:--------------:|:---------:|:-------:|:-----------:|-------------------------|
| 0      | P1             | 4         | 2       | 2           | P2 llega en t=2 (entra a cola) |
| 2      | P2             | 2         | 2       | 0           | P2 termina en t=4       |
| 4      | P1             | 2         | 2       | 0           | P1 termina en t=6; P3 llega en t=4 (entra a cola) |
| 6      | P3             | 4         | 2       | 2           | P4 llega en t=6 (entra a cola) |
| 8      | P4             | 5         | 2       | 3           |                         |
| 10     | P3             | 2         | 2       | 0           | P3 termina en t=12      |
| 12     | P4             | 3         | 2       | 1           |                         |
| 14     | P4             | 1         | 1       | 0           | P4 termina en t=15      |

### Paso 2 — Diagrama de Gantt (Q=2)

```
| P1 | P2 | P1 | P3 | P4 | P3 | P4 | P4 |
0    2    4    6    8    10   12   14   15
```

### Paso 3 — Tabla de resultados (Q=2)

| Proceso | AT | BT | CT | WT = CT − AT − BT |
|---------|:--:|:--:|:--:|:-----------------:|
| P1      | 0  | 4  | 6  | 6 − 0 − 4 = **2**  |
| P2      | 2  | 2  | 4  | 4 − 2 − 2 = **0**  |
| P3      | 4  | 4  | 12 | 12 − 4 − 4 = **4** |
| P4      | 6  | 5  | 15 | 15 − 6 − 5 = **4** |

```
AWT = (2 + 0 + 4 + 4) / 4 = 10 / 4 = 2.50
ACT = (6 + 4 + 12 + 15) / 4 = 37 / 4 = 9.25
```

| Métrica | Valor |
|---------|:-----:|
| **AWT** | **2.50** |
| **ACT** | **9.25** |

---

## 3.2 — Quantum = 3

### Paso 1 — Simulación

| Tiempo | Proceso en CPU | REM antes | Ejecuta | REM después | Nota                          |
|:------:|:--------------:|:---------:|:-------:|:-----------:|-------------------------------|
| 0      | P1             | 4         | 3       | 1           | P2 llega en t=2 (entra a cola)|
| 3      | P2             | 2         | 2       | 0           | P2 termina en t=5; P1 vuelve a cola |
| 5      | P1             | 1         | 1       | 0           | P1 termina en t=6; P3 llegó en t=4 (estaba en cola) |
| 6      | P3             | 4         | 3       | 1           | P4 llega en t=6 (entra a cola)|
| 9      | P4             | 5         | 3       | 2           |                               |
| 12     | P3             | 1         | 1       | 0           | P3 termina en t=13            |
| 13     | P4             | 2         | 2       | 0           | P4 termina en t=15            |

### Paso 2 — Diagrama de Gantt (Q=3)

```
| P1 | P2 | P1 | P3 | P4 | P3 | P4 |
0    3    5    6    9    12   13   15
```

### Paso 3 — Tabla de resultados (Q=3)

| Proceso | AT | BT | CT | WT = CT − AT − BT |
|---------|:--:|:--:|:--:|:-----------------:|
| P1      | 0  | 4  | 6  | 6 − 0 − 4 = **2**  |
| P2      | 2  | 2  | 5  | 5 − 2 − 2 = **1**  |
| P3      | 4  | 4  | 13 | 13 − 4 − 4 = **5** |
| P4      | 6  | 5  | 15 | 15 − 6 − 5 = **4** |

```
AWT = (2 + 1 + 5 + 4) / 4 = 12 / 4 = 3.00
ACT = (6 + 5 + 13 + 15) / 4 = 39 / 4 = 9.75
```

| Métrica | Valor |
|---------|:-----:|
| **AWT** | **3.00** |
| **ACT** | **9.75** |

---

## 3.4 — Conclusión: ¿Qué Quantum es más óptimo?

| Quantum | AWT  | ACT  |
|:-------:|:----:|:----:|
| Q = 2   | **2.50** | **9.25** |
| Q = 3   | 3.00 | 9.75 |

**El Quantum = 2 es el más óptimo**, ya que presenta un menor tiempo de espera promedio (AWT = 2.50) y un menor tiempo de completitud promedio (ACT = 9.25) en comparación con Quantum = 3 (AWT = 3.00, ACT = 9.75).

Si bien un Quantum = 2 genera más cambios de contexto, permite que los procesos más cortos como P2 terminen rápido sin bloquear a los demás, reduciendo la espera general del sistema.
