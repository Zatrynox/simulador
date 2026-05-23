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
