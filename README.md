# SISTEMAS OPERATIVOS — EXAMEN PARCIAL
### Solución completa | Preguntas 1, 2 y 3

---

# Pregunta 1: Caso de estudio — Vendematica.pe (10 puntos)

## Dimensionamiento previo

Antes de definir el hardware y software, se calculan los requerimientos reales del sistema a partir de los datos del enunciado:

**Almacenamiento de datos:**

```
Transacciones por día   = 50,000
Tamaño por transacción  = 0.4 MB
─────────────────────────────────────────
Almacenamiento diario   = 50,000 × 0.4 = 20,000 MB = 20 GB/día
Almacenamiento mensual  = 20 GB × 30   = 600 GB/mes
Almacenamiento anual    = 20 GB × 365  = 7,300 GB ≈ 7.3 TB/año
→ Disco recomendado: SSD 2 TB (primer año) — escalable en nube
```

**Pico de transacciones por hora:**

```
Lunes a Viernes: 8h – 23h = 15 horas activas
50,000 tx / 15 h = ~3,333 tx/hora = ~56 tx/minuto
→ El servidor de aplicación debe soportar mínimo 60 tx/min
```

**Usuarios concurrentes estimados:**

```
100,000 clientes registrados
Pico estimado: 10% activos simultáneamente
100,000 × 10% = 10,000 usuarios concurrentes en hora pico
→ El servidor web debe escalar para 10,000 conexiones simultáneas
```

---

## Diagrama de solución basada en 3 capas

|                   | **PRESENTACIÓN**                                                        | **APLICACIÓN**                                           | **DATOS**                                              |
|-------------------|-------------------------------------------------------------------------|----------------------------------------------------------|--------------------------------------------------------|
| **SOFTWARE**      | React + Bootstrap y navegadores web (Chrome, Firefox, Safari, Edge)     | Nginx y NodeJS                                           | PostgreSQL                                             |
| **SISTEMA OPERATIVO** | Windows, Linux, Android, MacOS y iOS                                | Ubuntu Server 24.04 LTS                                  | Ubuntu Server 24.04 LTS                                |
| **HARDWARE**      | Computadora, Laptop, Celular, Tablet                                    | Microsoft Azure (App Service — 4 vCPU, 8 GB RAM)        | Microsoft Azure (DB Flexible Server — 4 vCPU, 16 GB RAM, SSD 2 TB) |

> El diagrama visual con logos se construye en Ms. Word replicando esta tabla de 3 columnas × 3 filas con bordes punteados, tal como indica la Figura 1 del enunciado.

---

## Sustentación de la Capa de Presentación

### Software: React.js + Bootstrap 5

La capa de presentación fue diseñada utilizando **React.js** y **Bootstrap 5** por las siguientes razones:

- **React.js** permite desarrollar interfaces web modernas tipo SPA (Single Page Application) con componentes reutilizables (catálogo de productos, carrito de compras, seguimiento de delivery). Su arquitectura basada en componentes reduce el tiempo de desarrollo, lo cual es clave para un startup con recursos económicos limitados.
- React gestiona el estado de la aplicación de forma eficiente, brindando una experiencia fluida sin recargas completas de página al consultar el estado del pedido o actualizar el carrito.
- **Bootstrap 5** proporciona un sistema de grillas y componentes visuales **responsive**, que se adaptan automáticamente a PC, laptop, tablet y smartphone, cubriendo el requisito de acceso multi-dispositivo del enunciado.
- Ambas herramientas son **gratuitas y de código abierto**, sin costos de licencia.

### Sistema Operativo: Windows / macOS / Linux / Android / iOS (lado cliente)

La capa de presentación se ejecuta en el dispositivo del usuario final. El acceso se realiza exclusivamente a través de un **navegador web** (Chrome, Firefox, Safari, Edge), lo que garantiza:

- Compatibilidad universal sin necesidad de instalar aplicaciones adicionales.
- Cero costos de licencia de sistema operativo para el startup.
- Funcionamiento correcto en cualquier dispositivo que tenga un navegador moderno instalado.

### Hardware: Computadora, Laptop, Celular, Tablet

El hardware de la capa de presentación son los dispositivos del usuario final. No requiere servidores propios. El startup no incurre en ningún costo de hardware en esta capa.

---

## Sustentación de la Capa de Aplicación

### Software: Node.js v20 LTS + Nginx

**Node.js** fue seleccionado como runtime del servidor de aplicación por:

- Arquitectura **event-driven y non-blocking I/O**: puede gestionar miles de conexiones concurrentes con un solo hilo, ideal para soportar los 10,000 usuarios concurrentes estimados en hora pico sin necesidad de hardware costoso.
- Permite construir una **API REST en JSON** que sirve simultáneamente a la versión web y móvil desde el mismo backend, evitando duplicar lógica de negocio.
- Amplio ecosistema npm con librerías para autenticación (JWT), pagos y ORM (Sequelize/Prisma), acelerando el desarrollo.
- Licencia MIT — completamente gratuito.

**Nginx** actúa como proxy inverso y balanceador de carga frente a Node.js:

- Gestiona las conexiones HTTPS entrantes y distribuye la carga entre instancias de Node.js.
- Sirve directamente los archivos estáticos del frontend (HTML, CSS, JS de React compilado), reduciendo la carga del servidor de aplicación.
- Ofrece protección ante ataques DDoS mediante limitación de tasa (rate limiting).
- Es el servidor web más usado en producción a nivel mundial por su estabilidad y alto rendimiento.

### Sistema Operativo: Ubuntu Server 24.04 LTS

- **Gratuito y de código abierto**: elimina costos de licencia de sistema operativo, esencial para un startup con presupuesto ajustado.
- Versión **LTS (Long Term Support)**: soporte y actualizaciones de seguridad garantizadas hasta 2029, reduciendo riesgos operativos.
- Excelente compatibilidad con Node.js, Nginx y las herramientas de despliegue de Microsoft Azure.
- SO más utilizado en servidores cloud a nivel mundial, con amplia documentación y comunidad.

### Hardware: Microsoft Azure — App Service (Plan B2s, escalable a B4ms)

| Componente | Especificación    | Justificación |
|------------|-------------------|---------------|
| vCPUs      | 4 núcleos         | Soporta 56 tx/minuto en pico con margen holgado |
| RAM        | 8 GB              | Node.js no es intensivo en memoria; suficiente para 10k conexiones |
| Red        | 1 Gbps            | Transferencia fluida de datos JSON ligeros por request |
| Escalado   | Automático (Azure)| En picos de tráfico, Azure escala horizontalmente sin intervención manual |

Se optó por **Azure App Service** en lugar de servidor físico propio porque el startup evita la inversión inicial en hardware, paga solo por uso y puede escalar en minutos ante un crecimiento inesperado.

---

## Sustentación de la Capa de Datos

### Software: PostgreSQL 16

PostgreSQL fue elegido como sistema gestor de base de datos relacional (RDBMS) por:

- **Cumplimiento ACID** (Atomicidad, Consistencia, Aislamiento, Durabilidad): garantiza que cada transacción de compra se registre de forma íntegra o no se registre en absoluto, evitando inconsistencias como pedidos sin pago.
- Soporta relaciones complejas entre entidades: clientes, empleados, productos, pedidos, estados de delivery, formas de pago.
- La **trazabilidad del delivery** (historial de estados: Recibida → Aceptada → Rechazada, con fecha/hora, repartidor y observaciones) se implementa eficientemente con tablas de auditoría e índices en PostgreSQL.
- Soporte nativo a **JSONB** para datos semiestructurados en el futuro.
- **Gratuito y de código abierto** (licencia PostgreSQL), sin costos de licencia.
- Probado en plataformas de e-commerce de alta demanda a escala global.

### Sistema Operativo: Ubuntu Server 24.04 LTS

Misma justificación que la capa de aplicación: gratuito, estable, soporte LTS hasta 2029, compatible con PostgreSQL y los servicios de Azure. Mantener el mismo SO en ambas capas simplifica la administración y reduce la curva de aprendizaje del equipo técnico del startup.

### Hardware: Microsoft Azure — Database for PostgreSQL Flexible Server (D2s_v3)

| Componente | Especificación    | Justificación |
|------------|-------------------|---------------|
| vCPUs      | 4 núcleos         | Consultas concurrentes sin degradación en hora pico |
| RAM        | 16 GB             | Caché de datos frecuentes en memoria, reduciendo lecturas a disco |
| Disco      | SSD 2 TB          | Cubre los 7.3 TB/año calculados con margen; SSD garantiza baja latencia de I/O |
| Backup     | Automático diario | Recuperación ante desastres sin pérdida mayor a 24 horas |
| Red        | VNet privada Azure| La base de datos NO es accesible desde internet; solo desde la capa de aplicación |

---

## Herramientas de integración y seguridad (C04)

| Herramienta / Componente         | Capa                        | Función |
|----------------------------------|-----------------------------|---------|
| HTTPS / TLS 1.3                  | Presentación ↔ Aplicación   | Encripta el tráfico entre el navegador del cliente y el servidor. Protege datos de pago y credenciales. |
| Certificado SSL (Let's Encrypt)  | Aplicación                  | Gratuito, renovación automática cada 90 días. Habilita el candado de seguridad en el navegador. |
| Firewall de Azure (NSG)          | Aplicación + Datos          | Bloquea tráfico no autorizado. Solo permite puerto 443 desde internet. La BD solo acepta conexiones internas. |
| VNet privada de Azure            | Datos                       | La base de datos PostgreSQL vive en red privada. Sin IP pública expuesta a internet. |
| JWT (JSON Web Tokens)            | Aplicación                  | Autenticación stateless. Cada cliente autenticado recibe un token firmado con expiración. |
| Encriptación en reposo AES-256   | Datos                       | Azure encripta automáticamente todos los datos almacenados en disco. |
| API REST (JSON sobre HTTPS)      | Presentación ↔ Aplicación   | Protocolo estándar entre frontend y backend. Compatible con web y móvil simultáneamente. |
| Azure Monitor + Log Analytics    | Aplicación + Datos          | Monitoreo de disponibilidad, tiempos de respuesta y errores en tiempo real. |

---
---

# Pregunta 2: Gestión de Procesos — Round Robin Q = 4 (5 puntos)

## Tabla de procesos

| **Process** | **Arrive Time** | **Burst Time** |
|:-----------:|:---------------:|:--------------:|
| P1          | 4               | 5              |
| P2          | 1               | 4              |
| P3          | 6               | 6              |
| P4          | 3               | 2              |

**Quantum = 4**

---

## Simulación paso a paso

Ordenamos por Arrival Time: P2 (t=1) → P4 (t=3) → P1 (t=4) → P3 (t=6)

| Tick | Proceso | REM antes | Ejecuta | REM después | Evento |
|:----:|:-------:|:---------:|:-------:|:-----------:|--------|
| 1    | P2      | 4         | 4       | 0           | P2 **termina** en t=5 |
| 5    | P4      | 2         | 2       | 0           | P4 **termina** en t=7 |
| 7    | P1      | 5         | 4       | 1           | P1 vuelve al final de la cola |
| 11   | P3      | 6         | 4       | 2           | P3 vuelve al final de la cola |
| 15   | P1      | 1         | 1       | 0           | P1 **termina** en t=16 |
| 16   | P3      | 2         | 2       | 0           | P3 **termina** en t=18 |

---

## 2.1 Diagrama de Gantt

```
 _______ _______ _______________ _______________ _____ _______
|       |       |               |               |     |       |
|  P2   |  P4   |      P1       |      P3       | P1  |  P3   |
|_______|_______|_______________|_______________|_____|_______|
1       5       7               11              15    16      18
```

Representación como tabla (cada celda = 1 unidad de tiempo):

| t→  | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 |
|-----|---|---|---|---|---|---|---|---|---|---|----|----|----|----|----|----|----|----|
| P1  |   |   |   |   |   |   |   | ▓ | ▓ | ▓ | ▓  |    |    |    |    | ▓  |    |    |
| P2  |   | ▓ | ▓ | ▓ | ▓ |   |   |   |   |   |    |    |    |    |    |    |    |    |
| P3  |   |   |   |   |   |   |   |   |   |   |    | ▓  | ▓  | ▓  | ▓  |    | ▓  | ▓  |
| P4  |   |   |   |   |   | ▓ | ▓ |   |   |   |    |    |    |    |    |    |    |    |

---

## 2.2 Tabla de resultados

Fórmulas:
- **CT** = tiempo en que el proceso termina
- **WT** = CT − Arrive Time − Burst Time
- **AWT** = suma de WT ÷ número de procesos
- **ACT** = suma de CT ÷ número de procesos

| **Process** | **Arrive Time** | **Burst Time** | **(WT) Waiting Time**    | **(CT) Complete Time**   |
|:-----------:|:---------------:|:--------------:|:------------------------:|:------------------------:|
| P1          | 4               | 5              | 16 − 4 − 5 = **7**       | **16**                   |
| P2          | 1               | 4              | 5 − 1 − 4 = **0**        | **5**                    |
| P3          | 6               | 6              | 18 − 6 − 6 = **6**       | **18**                   |
| P4          | 3               | 2              | 7 − 3 − 2 = **2**        | **7**                    |

## 2.3 Calcular AWT y ACT

| **AWT**                        | **ACT**                          |
|:------------------------------:|:--------------------------------:|
| (7 + 0 + 6 + 2) / 4 = **3.75** | (16 + 5 + 18 + 7) / 4 = **11.50** |

---
---

# Pregunta 3: Gestión de Procesos — Round Robin Q=2 y Q=3 (5 puntos)

## Tabla de procesos

| **Procesos** | **Tiempo de llegada** | **Tiempo de proceso** | **Tiempo de espera** | **Tiempo de completitud** |
|:------------:|:---------------------:|:---------------------:|:--------------------:|:-------------------------:|
| P1           | 0                     | 4                     |                      |                           |
| P2           | 2                     | 2                     |                      |                           |
| P3           | 4                     | 4                     |                      |                           |
| P4           | 6                     | 5                     |                      |                           |

---

## Respuesta Quantum = 2

### Simulación paso a paso (Q=2)

| Tick | Proceso | REM antes | Ejecuta | REM después | Evento |
|:----:|:-------:|:---------:|:-------:|:-----------:|--------|
| 0    | P1      | 4         | 2       | 2           | P2 llega en t=2, entra a cola |
| 2    | P2      | 2         | 2       | 0           | P2 **termina** en t=4 |
| 4    | P1      | 2         | 2       | 0           | P1 **termina** en t=6; P3 llegó en t=4 |
| 6    | P3      | 4         | 2       | 2           | P4 llega en t=6, entra a cola |
| 8    | P4      | 5         | 2       | 3           | P4 vuelve al final |
| 10   | P3      | 2         | 2       | 0           | P3 **termina** en t=12 |
| 12   | P4      | 3         | 2       | 1           | P4 vuelve al final |
| 14   | P4      | 1         | 1       | 0           | P4 **termina** en t=15 |

### 3.1 Diagrama de Gantt (Q=2)

```
 _____ _____ _____ _____ _____ _____ _____ ____
|     |     |     |     |     |     |     |    |
| P1  | P2  | P1  | P3  | P4  | P3  | P4  | P4 |
|_____|_____|_____|_____|_____|_____|_____|____|
0     2     4     6     8     10    12    14   15
```

Representación como tabla (cada celda = 1 unidad de tiempo):

| t→  | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 |
|-----|---|---|---|---|---|---|---|---|---|---|----|----|----|----|-----|
| P1  | ▓ | ▓ |   |   | ▓ | ▓ |   |   |   |   |    |    |    |    |    |
| P2  |   |   | ▓ | ▓ |   |   |   |   |   |   |    |    |    |    |    |
| P3  |   |   |   |   |   |   | ▓ | ▓ |   |   | ▓  | ▓  |    |    |    |
| P4  |   |   |   |   |   |   |   |   | ▓ | ▓ |    |    | ▓  | ▓  | ▓  |

### 3.2 y 3.3 Tabla de resultados (Q=2)

| **Procesos** | **Tiempo de llegada** | **Tiempo de proceso** | **Tiempo de espera (WT)**   | **Tiempo de completitud (CT)** |
|:------------:|:---------------------:|:---------------------:|:---------------------------:|:------------------------------:|
| P1           | 0                     | 4                     | 6 − 0 − 4 = **2**           | **6**                          |
| P2           | 2                     | 2                     | 4 − 2 − 2 = **0**           | **4**                          |
| P3           | 4                     | 4                     | 12 − 4 − 4 = **4**          | **12**                         |
| P4           | 6                     | 5                     | 15 − 6 − 5 = **4**          | **15**                         |

| **AWT**                        | **ACT**                          |
|:------------------------------:|:--------------------------------:|
| (2 + 0 + 4 + 4) / 4 = **2.50** | (6 + 4 + 12 + 15) / 4 = **9.25** |

---

## Respuesta Quantum = 3

### Simulación paso a paso (Q=3)

| Tick | Proceso | REM antes | Ejecuta | REM después | Evento |
|:----:|:-------:|:---------:|:-------:|:-----------:|--------|
| 0    | P1      | 4         | 3       | 1           | P2 llega en t=2, entra a cola |
| 3    | P2      | 2         | 2       | 0           | P2 **termina** en t=5; P1 vuelve a cola |
| 5    | P1      | 1         | 1       | 0           | P1 **termina** en t=6; P3 llegó en t=4 |
| 6    | P3      | 4         | 3       | 1           | P4 llega en t=6, entra a cola |
| 9    | P4      | 5         | 3       | 2           | P4 vuelve al final |
| 12   | P3      | 1         | 1       | 0           | P3 **termina** en t=13 |
| 13   | P4      | 2         | 2       | 0           | P4 **termina** en t=15 |

### 3.1 Diagrama de Gantt (Q=3)

```
 _________ _____ __ _________ _________ __ _____
|         |     |  |         |         |  |     |
|   P1    | P2  |P1|   P3    |   P4    |P3| P4  |
|_________|_____|__|_________|_________|__|_____|
0         3     5  6         9         12 13    15
```

Representación como tabla (cada celda = 1 unidad de tiempo):

| t→  | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 |
|-----|---|---|---|---|---|---|---|---|---|---|----|----|----|----|-----|
| P1  | ▓ | ▓ | ▓ |   |   | ▓ |   |   |   |   |    |    |    |    |    |
| P2  |   |   |   | ▓ | ▓ |   |   |   |   |   |    |    |    |    |    |
| P3  |   |   |   |   |   |   | ▓ | ▓ | ▓ |   |    |    | ▓  |    |    |
| P4  |   |   |   |   |   |   |   |   |   | ▓ | ▓  | ▓  |    | ▓  | ▓  |

### 3.2 y 3.3 Tabla de resultados (Q=3)

| **Procesos** | **Tiempo de llegada** | **Tiempo de proceso** | **Tiempo de espera (WT)**   | **Tiempo de completitud (CT)** |
|:------------:|:---------------------:|:---------------------:|:---------------------------:|:------------------------------:|
| P1           | 0                     | 4                     | 6 − 0 − 4 = **2**           | **6**                          |
| P2           | 2                     | 2                     | 5 − 2 − 2 = **1**           | **5**                          |
| P3           | 4                     | 4                     | 13 − 4 − 4 = **5**          | **13**                         |
| P4           | 6                     | 5                     | 15 − 6 − 5 = **4**          | **15**                         |

| **AWT**                        | **ACT**                          |
|:------------------------------:|:--------------------------------:|
| (2 + 1 + 5 + 4) / 4 = **3.00** | (6 + 5 + 13 + 15) / 4 = **9.75** |

---

## 3.4 Tiempo de espera óptimo

| Quantum | AWT      | ACT      |
|:-------:|:--------:|:--------:|
| Q = 2   | **2.50** | **9.25** |
| Q = 3   | 3.00     | 9.75     |

**El Quantum = 2 es el más óptimo.**

En los diagramas de Gantt se puede visualizar que si bien con Q=2 hay más cambios de contexto, los procesos en general esperan menos tiempo en comparación con Q=3. Este hecho también se representa en los valores de AWT y ACT que son menores en Quantum 2 (AWT=2.50 vs 3.00, ACT=9.25 vs 9.75). Un quantum menor beneficia especialmente a procesos cortos como P2, que con Q=2 termina en t=4 mientras que con Q=3 termina en t=5.
