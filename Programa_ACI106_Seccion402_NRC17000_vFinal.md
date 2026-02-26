# Diseño de ramo Python→Java con un diseño bilingüe desde el inicio.

> Documento organizado en secciones plegables (details). Recomendado para VS Code Preview y GitHub.

## Índice
1. [Datos del curso](#datos-del-curso)
2. [Normas de aula](#normas-de-aula)
3. [Calendario y restricciones UDLA](#calendario-y-restricciones-udla)
4. [Evaluaciones](#evaluaciones)
5. [Diseño didáctico Python→Java](#diseno-didactico-pythonjava)
6. [Instrumentos de evaluación](#instrumentos-de-evaluacion)
7. [Planificación semana a semana](#planificacion-semana-a-semana)
8. [Recomendaciones operativas](#recomendaciones-operativas)
9. [Fuentes y referencias](#fuentes-y-referencias)

<a id="datos-del-curso"></a>

<details open>
<summary><b>0. Datos del curso (ACI106 | NRC 17000 | Sección 402)</b></summary>

- **Código:** ACI106
- **NRC:** 17000
- **Sección:** 402
- **Sala:** A316 (Edif. A)
- **Horario Miércoles:** 13:10–14:10 | 14:20–15:20 | 15:30–16:30
- **Horario Viernes:** 14:20–15:20 | 15:30–16:30

</details>

<a id="normas-de-aula"></a>

<details open>
<summary><b>1. Normas de aula y funcionamiento</b></summary>

- **Asistencia mínima:** 50% (Reglamento Académico UDLA).
- **Retraso:** se permite un retraso máximo de **15 minutos**. Pasado ese tiempo, se registra **inasistencia** en la sesión.
- **IA generativa (ChatGPT, etc.):** no se permite su uso para **resolver problemas, ejercicios o escribir código** durante clases/ayudantías ni durante evaluaciones en sala. (Objetivo: aprendizaje y práctica propia en el primer curso de programación).
- **Canales oficiales:** avisos y material por Blackboard; fechas y notas por MiUdla.

</details>

<a id="calendario-y-restricciones-udla"></a>

<details>
<summary><b>2. Calendario y restricciones UDLA (viabilidad)</b></summary>

- Inicio de clases: lunes 02/03/2026.
- Plazo para programar evaluaciones en MiUdla (Fijar Pruebas): 14/03/2026.
- 1er hito evaluativo: semana 06–11/04 (debe existir al menos 1 evaluación registrada).
- Semana de consolidación: 18–24/05 (reforzamiento/recuperación).
- 2do hito evaluativo: semana 25–30/05 (debe haber al menos 2 evaluaciones registradas).
- Todas las evaluaciones ingresadas en MiUdla: 08–13/06 (salvo pendientes planificadas).
- Término de clases: 27/06/2026.
- Semana evaluación de exámenes (1): 30/06–04/07.
- Semana evaluación de exámenes (2) y cierre: 06–11/07; cierre 11/07.
- Nota operativa: el 25/03 hay “Reunión semestral de estudiantes” con suspensión de módulo 9. Si tu sección cae en ese módulo, ajustas esa semana.

</details>

<a id="evaluaciones"></a>

<details open>
<summary><b>3. Evaluaciones (ponderaciones + fechas)</b></summary>

### Ponderaciones oficiales
- Examen: 35%
- Cátedras: 50% (2×25%)
- Ejercicios: 15% (4×3,75%)

### Calendario evaluativo (fechas fijas)
| Evaluación | Fecha | Ponderación |
|---|---:|---:|
| Ejercicio 1 | Vie 27/03 | 3,75% |
| Cátedra 1 | Mié 08/04 | 25% |
| Ejercicio 2 | Vie 17/04 | 3,75% |
| Ejercicio 3 | Vie 08/05 | 3,75% |
| Ejercicio 4 | Vie 15/05 | 3,75% |
| Cátedra 2 | Mié 27/05 | 25% |
| Examen final integrador | Vie 03/07 | 35% |

### Nota
- El examen final es **integrador** (aplica todo lo aprendido).
- Estas fechas deben quedar **fijadas** en MiUdla dentro del plazo institucional.

</details>

<a id="diseno-didactico-pythonjava"></a>

<details open>
<summary><b>4. Diseño didáctico Python→Java (bilingüe desde semana 1)</b></summary>

- Desde semana 1: cada concepto se ve en Python (principal) + “espejo” en Java (mínimo), para que Java nunca sea “desde cero”. El curso explícitamente trabaja con Python y Java y progresa hasta POO.
- El hilo conductor: un mismo caso (por ejemplo, “Sistema de tickets/incidencias”) que parte con estructuras de control y luego se convierte en POO (mismo problema, nuevo paradigma). Esto calza con RAA1–RAA3 (análisis algorítmico → Python estructurado → Java POO).
- Ayudantías: viernes se usa para laboratorio guiado y retroalimentación (tal como plantea la metodología con ayudantías/e-support).

### Regla semanal
- **Miércoles:** concepto + algoritmo + implementación principal en Python + mini-espejo en Java (10–20 min).
- **Viernes:** laboratorio guiado + kata + mini code-review (y entrega si corresponde).
- **Trabajo personal:** 1 micro-traducción Python→Java por semana (10–15 min).

### Caso conductor
- Sistema de tickets/incidencias: creación, listado, búsqueda, métricas → luego POO en Java con robustez.

</details>

<a id="instrumentos-de-evaluacion"></a>

<details>
<summary><b>5. Instrumentos y recursos (rúbrica + checklist)</b></summary>

### Lista de cotejo (Ejercicios E1–E4)
- Ejecuta/compila sin errores
- Cumple requerimientos mínimos
- Valida entradas / maneja casos borde
- Usa estructuras correctas (if/loops/colecciones según semana)
- Claridad: nombres, formato, comentarios mínimos

### Rúbrica corta (Cátedras y Examen)
- Correctitud funcional (requerimientos + casos de prueba)
- Diseño/estructura (modularidad en Python / encapsulamiento y cohesión en Java)
- Robustez (validación / excepciones cuando aplique)
- Legibilidad (nombres, orden, consistencia)

### Lecturas/recursos sugeridos
- Chazallet, *Python 3* (bibliografía básica).
- Joyanes Aguilar, *Programación en JAVA 6* (bibliografía básica).
- Documentación oficial de Python y Java (Oracle).

</details>

<a id="planificacion-semana-a-semana"></a>

<details>
<summary><b>6. Resumen rápido (tablas por tramo)</b></summary>

**Parte I**

| Semana (rango) | Miércoles (teoría) | Viernes (ayudantía/práctica) | Evaluación |
| --- | --- | --- | --- |
| 1 (02/03–08/03) | Diagnóstico + pensamiento algorítmico (RAA1) + entorno | Setup VS Code + primer programa + trazas | — |
| 2 (09/03–15/03) | Variables, tipos, I/O, operadores (Py+Java) | Katas de secuencial + validación básica | — |
| 3 (16/03–22/03) | Condicionales, lógica booleana, casos borde | Clínica de “casos de prueba” (tabla de decisiones) | — |
| 4 (23/03–29/03) | Bucles (while/for), contadores y acumuladores | Laboratorio: menú por consola + validación | Ejercicio 1 (Vie 27/03) |
| 5 (30/03–05/04) | Patrones algorítmicos: búsqueda lineal, bandera, corte | Laboratorio: “mini tickets v1” (sin estructuras complejas) | — |
| 6 (06/04–12/04) | Repaso guiado + resolución tipo prueba | Taller de preparación + dudas | Cátedra 1 (Mié 08/04) <br>Calendario-Academico-UDLA-2026_… |

**Parte II**

| Semana (rango) | Miércoles (teoría) | Viernes (ayudantía/práctica) | Evaluación |
| --- | --- | --- | --- |
| 7 (13/04–19/04) | Funciones, parámetros, retorno, scope; diseño por descomposición | Refactor del mini ticket: todo a funciones | Ejercicio 2 (Vie 17/04) |
| 8 (20/04–26/04) | Listas/diccionarios (Py) + colecciones equivalentes (Java: idea, no profundidad) | Laboratorio: métricas simples (conteos, top-N, filtros) | — |
| 9 (27/04–03/05) | Depuración, lectura de errores, buenas prácticas | “Bug clinic”: arreglar 6 bugs típicos (con guía) | — |

**Parte III**

| Semana (rango) | Miércoles (teoría) | Viernes (ayudantía/práctica) | Evaluación |
| --- | --- | --- | --- |
| 10 (04/05–10/05) | Java “bootcamp”: tipos, métodos, arreglos/listas; mismo algoritmo que en Python | Kata: convertir 3 ejercicios Python→Java (con plantilla) | Ejercicio 3 (Vie 08/05) |
| 11 (11/05–17/05) | Clases/objetos + encapsulamiento (atributos privados, constructor) | Laboratorio: Ticket + Usuario + reglas de estado | Ejercicio 4 (Vie 15/05) |
| 12 (18/05–24/05) | Semana de consolidación UDLA: reforzamiento + recuperación + preparación cátedra | Taller de recuperación/repaso + mini simulacro | — <br>Calendario-Academico-UDLA-2026_… |
| 13 (25/05–31/05) | Excepciones (try/catch) + colecciones aplicadas al diseño | Laboratorio: consolidación “tickets POO v1” | Cátedra 2 (Mié 27/05) <br>Calendario-Academico-UDLA-2026_… |

**Parte IV**

| Semana (rango) | Miércoles (teoría) | Viernes (ayudantía/práctica) | Entregables formativos |
| --- | --- | --- | --- |
| 14 (01/06–07/06) | Herencia vs composición (cuándo sí/cuándo no) | Modelado guiado: jerarquía mínima (sin sobre-heredar) | Checklist de diseño |
| 15 (08/06–14/06) | Polimorfismo (interfaces/abstracto como idea) + refactor | Code review en parejas + mejoras por rúbrica | Mini informe de decisiones |
| 16 (15/06–21/06) | Sprint integrador: arquitectura simple + robustez | Laboratorio: “tickets final” (Java) + manejo de errores | README + ejemplos de uso |
| 17 (22/06–28/06) | Preparación examen: estrategia de resolución, lectura de enunciado, plan | Simulacro integrador corto + retro | Banco de ejercicios resueltos |

**Parte V**

| Semana (rango) | Evaluación |
| --- | --- |
| 18 (29/06–05/07) | Examen final integrador (35%) — Vie 03/07 (dentro de la semana de exámenes 30/06–04/07) <br>Calendario-Academico-UDLA-2026_… |


</details>

<details open>
<summary><b>7. Planificación detallada por semana (plegable por fecha)</b></summary>

<details open>
<summary><b>Semana 1 (02/03–08/03) — Unidad 1</b></summary>


<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- identificar entradas/salidas de un problema y escribir un algoritmo en pasos (pseudocódigo + traza). (RAA1)

**Lectura / antes de clase**
- Python 3 (capítulos intro) + “docs” Python (concepto de programa).

<summary><b>Miércoles (teoría)</b></summary>

- diagnóstico + pensamiento algorítmico (descomposición, patrones, abstracción) + presentación del caso “tickets”.

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- setup VS Code/terminal + primer programa en Python + traza guiada (entrada→proceso→salida).

<summary><b>Evaluación</b></summary>

_(Sin evaluación esta semana)_

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Trabajo personal (e-support)**
- 6 micro-ejercicios de trazas (sin código) + 2 con código.

**Instrumento / criterio**
- lista de cotejo de algoritmo (pasos completos, variables identificadas, salida definida).

</details>

<details open>
<summary><b>Semana 2 (09/03–15/03) — Unidad 1</b></summary>


<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- implementar programas secuenciales con variables, tipos, operadores e I/O en Python y reconocer el equivalente mínimo en Java. (RAA1→inicio RAA2)

**Lectura / antes de clase**
- Python 3 (variables, I/O) + Java (sintaxis básica I/O).

<summary><b>Miércoles (teoría)</b></summary>

- variables, tipos, operadores, I/O (Python completo) + espejo Java (Scanner/println).

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- katas secuenciales + validación simple (rangos).

<summary><b>Evaluación</b></summary>

_(Sin evaluación esta semana)_

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Trabajo personal (e-support)**
- “traducción micro” 10 min: input/print ↔ Scanner/println.

**Instrumento / criterio**
- correctitud de I/O + nombres significativos

</details>

<details open>
<summary><b>Semana 3 (16/03–22/03) — Unidad 1</b></summary>


<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- resolver problemas con condicionales y lógica booleana, definiendo casos borde y criterios de prueba. (RAA1/RAA2)

**Lectura / antes de clase**
- Python 3 (if/elif) + lectura corta: tabla de decisiones.

<summary><b>Miércoles (teoría)</b></summary>

- condicionales + lógica + diseño de casos. Espejo Java: if/else if/else.

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- clínica de pruebas manuales (casos borde) sobre mini-tickets (prioridad/estado).

<summary><b>Evaluación</b></summary>

_(Sin evaluación esta semana)_

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Trabajo personal (e-support)**
- 8 ejercicios cortos + 1 plantilla Java para completar.

**Instrumento / criterio**
- lista de cotejo: casos borde explícitos + trazas correctas.

</details>

<details open>
<summary><b>Semana 4 (23/03–29/03) — Unidad 1 • Ejercicio 1 (Vie 27/03) — bucles + pruebas manuales (3,75%).</b></summary>


<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- usar bucles (for/while) con contadores/acumuladores y validación de entrada. (RAA2)

**Lectura / antes de clase**
- Python 3 (bucles) + docs Python (range).

<summary><b>Miércoles (teoría)</b></summary>

- bucles + patrones (contador/acumulador).

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- laboratorio “menú por consola” + validación.

<summary><b>Evaluación</b></summary>

- Ejercicio 1 (Vie 27/03) — bucles + pruebas manuales (3,75%).

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Instrumento / criterio**
- lista de cotejo (correctitud, validación, casos borde).

<summary><b>Notas</b></summary>

- si se suspende tu módulo, este bloque se entrega como cápsula + guía de ejercicios.


</details>

<details open>
<summary><b>Semana 5 (30/03–05/04) — Unidad 1→2</b></summary>

<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- aplicar patrones algorítmicos (búsqueda lineal, bandera, corte) al caso tickets v0. (RAA1/RAA2)

**Lectura / antes de clase**
- Python 3 (listas intro)

<summary><b>Miércoles (teoría)</b></summary>

- patrones algorítmicos típicos + modelado de datos mínimo.

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- mini tickets v0 (alta/listado/búsqueda) en Python.

<summary><b>Evaluación</b></summary>

_(Sin evaluación esta semana)_

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Trabajo personal (e-support)**
- 1 guía de ejercicios + micro-traducción de “for + bandera” a Java.

</details>

<details open>
<summary><b>Semana 6 (06/04–12/04) — Hito evaluativo 1 • Cátedra 1 (Mié 08/04) — práctica: diseño + implementación Python (25%).</b></summary>


<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- integrar control de flujo + trazas + pruebas manuales en una resolución tipo prueba. (RAA1/RAA2)

**Lectura / antes de clase**
- repaso dirigido + banco de ejercicios.

<summary><b>Miércoles (teoría)</b></summary>

- repaso guiado + estrategia de lectura de enunciado.

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- taller de preparación + dudas.

<summary><b>Evaluación</b></summary>

- Cátedra 1 (Mié 08/04) — práctica: diseño + implementación Python (25%).

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Instrumento / criterio**
- rúbrica corta (correctitud, claridad, validación, casos borde).

</details>

<details open>
<summary><b>Semana 7 (13/04–19/04) — Unidad 2 • Ejercicio 2 (Vie 17/04) — refactor + checklist (3,75%).</b></summary>


<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- descomponer un problema en funciones y refactorizar código para modularidad. (RAA2)

**Lectura / antes de clase**
- Python 3 (funciones, scope).

<summary><b>Miércoles (teoría)</b></summary>

- funciones, parámetros, retorno, ámbito.

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- refactor tickets v0 → funciones.

<summary><b>Evaluación</b></summary>

- Ejercicio 2 (Vie 17/04) — refactor + checklist (3,75%).

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Instrumento / criterio**
- lista de cotejo de modularidad (funciones pequeñas, nombres, reutilización).

</details>

<details open>
<summary><b>Semana 8 (20/04–26/04) — Unidad 2</b></summary>

<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- manipular listas/diccionarios para resolver filtros, conteos y métricas; reconocer equivalentes en Java (ArrayList/Map) como concepto. (RAA2)

**Lectura / antes de clase**
- Python 3 (listas/dicts) + lectura breve: colecciones en Java (conceptual).

<summary><b>Miércoles (teoría)</b></summary>

- estructuras de datos básicas + operaciones típicas.

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- laboratorio métricas (top-N, filtros, conteos) sobre tickets.

<summary><b>Evaluación</b></summary>

_(Sin evaluación esta semana)_

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Trabajo personal (e-support)**
- mini-traducción: lista Python ↔ ArrayList (plantilla).

</details>

<details open>>
<summary><b>Semana 9 (27/04–03/05) — Unidad 2</b></summary>


<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- depurar y mejorar legibilidad siguiendo estándares básicos y evidencia de pruebas manuales. (RAA2)

**Lectura / antes de clase**
- Python 3 (errores comunes)

<summary><b>Miércoles (teoría)</b></summary>

- depuración, lectura de errores, buenas prácticas.

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- “bug clinic” (6 bugs típicos) + mini code-review.

<summary><b>Evaluación</b></summary>

_(Sin evaluación esta semana)_

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Trabajo personal (e-support)**
- bitácora corta: “qué bug era / cómo lo detecté / cómo lo probé”.

</details>

<details open>
<summary><b>Semana 10 (04/05–10/05) — Unidad 3 (Java entra formal) • Ejercicio 3 (Vie 08/05) — traducción controlada (3,75%).</b></summary>


<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- implementar en Java algoritmos ya dominados en Python (sin partir de cero) usando plantillas. (RAA3 en transición)

**Lectura / antes de clase**
- Joyanes (sintaxis básica) + docs Java.

<summary><b>Miércoles (teoría)</b></summary>

- “bootcamp Java” (tipos, métodos, arreglos/listas) con mismo problema.

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- kata: convertir 3 ejercicios Python→Java con plantilla.

<summary><b>Evaluación</b></summary>

- Ejercicio 3 (Vie 08/05) — traducción controlada (3,75%).

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Instrumento / criterio**
- lista de cotejo (compila, salida correcta, nombres, control de errores básico).

</details>

<details open>
<summary><b>Semana 11 (11/05–17/05) — Unidad 3 • Ejercicio 4 (Vie 15/05) — mini-POO (3,75%).</b></summary>

<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- modelar clases y objetos con encapsulamiento (atributos privados, constructor, métodos) en Java. (RAA3)

**Lectura / antes de clase**
- Joyanes (clases/objetos)

<summary><b>Miércoles (teoría)</b></summary>

- clases/objetos + encapsulamiento.

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- laboratorio: Ticket + Usuario + reglas de estado.

<summary><b>Evaluación</b></summary>

- Ejercicio 4 (Vie 15/05) — mini-POO (3,75%).

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Instrumento / criterio**
- rúbrica corta (encapsulamiento, coherencia del modelo, correctitud).

</details>

<details open>
<summary><b>Semana 12 (18/05–24/05) — Semana de consolidación UDLA</b></summary>

<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- cerrar brechas detectadas en Cátedra 1/Ejercicios y preparar Cátedra 2 (reforzamiento/recuperación).

**Lectura / antes de clase**
- banco de problemas seleccionados.

<summary><b>Miércoles (teoría)</b></summary>

- reforzamiento dirigido (según diagnóstico) + práctica guiada.

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- recuperación + mini simulacro formativo (sin nota).

<summary><b>Evaluación</b></summary>

_(Sin evaluación esta semana)_

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Evidencia**
- checklist de progreso por estudiante (errores recurrentes y plan de mejora).

</details>

<details open>
<summary><b>Semana 13 (25/05–31/05) — Hito evaluativo 2 • Cátedra 2 (Mié 27/05) — Java POO + robustez (25%).</b></summary>

<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- usar excepciones y colecciones en Java para robustez y escalabilidad básica del sistema. (RAA3)

**Lectura / antes de clase**
- Joyanes (excepciones) + docs Java try/catch.

<summary><b>Miércoles (teoría)</b></summary>

- try/catch + colecciones aplicadas.

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- consolidación “tickets POO v1”.

<summary><b>Evaluación</b></summary>

- Cátedra 2 (Mié 27/05) — Java POO + robustez (25%).

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Instrumento / criterio**
- rúbrica corta (modelo, correctitud, excepciones, claridad).

</details>


<details open>
<summary><b>Semana 14 (01/06–07/06) — Unidad 3 (POO “real”)</b></summary>


<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- decidir entre herencia y composición justificando una elección simple en el modelo. (RAA3)

**Lectura / antes de clase**
- lectura guiada (herencia vs composición) + ejemplo del caso tickets.

<summary><b>Miércoles (teoría)</b></summary>

- herencia vs composición (cuándo sí/cuándo no).

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- modelado guiado: jerarquía mínima (sin sobre-heredar).

<summary><b>Evaluación</b></summary>

_(Sin evaluación esta semana)_

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Trabajo personal (e-support)**
- breve justificación (½ página) de decisiones de diseño.

**Instrumento / criterio**
- checklist de diseño (responsabilidad única, acoplamiento bajo).

</details>

<details open>
<summary><b>Semana 15 (08/06–14/06) — Unidad 3</b></summary>

<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- aplicar polimorfismo (interfaces/abstracto como idea) para desacoplar comportamiento en el sistema. (RAA3)

**Lectura / antes de clase**
- docs Java (interfaces) + ejemplo corto.

<summary><b>Miércoles (teoría)</b></summary>

- polimorfismo aplicado (mínimo necesario).

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- code review en parejas + refactor por rúbrica.

<summary><b>Evaluación</b></summary>

_(Sin evaluación esta semana)_

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Trabajo personal (e-support)**
- “plan de refactor” (3 cambios con motivo + evidencia).

**Instrumento / criterio**
- rúbrica (diseño, claridad, pruebas manuales).

</details>

<details open>
<summary><b>Semana 16 (15/06–21/06) — Integración</b></summary>

<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- integrar POO + colecciones + excepciones en un entregable funcional y documentado (README + ejemplos). (RAA3)

**Lectura / antes de clase**
- plantilla README + ejemplo de documentación de uso.

<summary><b>Miércoles (teoría)</b></summary>

- arquitectura simple del proyecto (capas mínimas) + robustez.

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- laboratorio “tickets final” + manejo de errores + ejemplos.

<summary><b>Evaluación</b></summary>

_(Sin evaluación esta semana)_

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Trabajo personal (e-support)**
- completar README + set de casos de prueba manuales.

**Instrumento / criterio**
- rúbrica (funciona, documenta, robustez, diseño).

</details>

<details open>
<summary><b>Semana 17 (22/06–28/06) — Preparación de examen</b></summary>

<summary><b>Objetivo y lecturas</b></summary>

**Objetivo**
- resolver un caso integrador en tiempo acotado siguiendo una estrategia (leer, planificar, implementar, probar). (RAA1–RAA3)

**Lectura / antes de clase**
- banco de ejercicios resueltos + checklist de examen.

<summary><b>Miércoles (teoría)</b></summary>

- estrategia de examen (lectura de requerimientos + plan).

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

- simulacro integrador corto + retro.

<summary><b>Evaluación</b></summary>

_(Sin evaluación esta semana)_

<summary><b>Tarea / evidencia / instrumento</b></summary>

**Evidencia**
- banco personal de “errores frecuentes” + plan de corrección.

</details>

<details open>
<summary><b>Semana 18 (29/06–05/07) — Examen final integrador • Examen final (Vie 03/07) — integrador, aplica lo aprendido durante el curso. (35%)</b></summary>


<summary><b>Objetivo y lecturas</b></summary>

_(Sin información)_

<summary><b>Miércoles (teoría)</b></summary>

_(Sin información)_

<summary><b>Viernes (ayudantía / laboratorio)</b></summary>

_(Sin información)_

<summary><b>Evaluación</b></summary>

- Examen final (Vie 03/07) — integrador, aplica lo aprendido durante el curso. (35%)

<summary><b>Tarea / evidencia / instrumento</b></summary>

_(Sin información)_


</details>

<details open>
<a id="recomendaciones-operativas"></a>

<summary><b>8. Recomendaciones operativas (MiUdla + dinámica de clase)</b></summary>

### Dos mejoras finas
- A) “Espejo Java” con reglas claras (para no comerse el tiempo)
- Semanas 1–3: solo I/O + if + loops (10 min).
- Semanas 4–6: funciones vs métodos (idea), sin POO aún.
- Semanas 7–9: colecciones como concepto (sin detalle).
- Semanas 10+: Java pasa a ser el principal.
- B) Plantillas obligatorias (desde semana 10) + rúbrica mínima recurrente
- Plantillas: Main.java, clases base, imports, lectura de input, estructura de carpetas.
- Mini-rúbrica recurrente (sirve para ejercicios, laboratorios y parte del examen):
- Correctitud (casos borde)
- Claridad (nombres/estructura)
- Modularidad (funciones/métodos)
- Robustez (validación/excepciones)
- Esto calza con el programa cuando señala uso de rúbricas/listas de cotejo e integración de procedimientos formativos y sumativos.

### Recomendación MiUdla (fijar evaluaciones)
- Como el plazo de “Fijar Pruebas” es 14/03, mi recomendación operativa es que en MiUdla queden así desde el día 1:
- E1 27/03, C1 08/04, E2 17/04, E3 08/05, E4 15/05, C2 27/05, Examen 03/07 (este último como evaluación planificada).

### La receta para que funcione sin duplicar carga
- Para que enseñar dos lenguajes no duplique trabajo:
- Un solo problema por semana, dos implementaciones (una parcial en Java):
- Miércoles: Python completo + Java mínimo (solo las líneas clave).
- Viernes: los estudiantes completan la versión Java en plantilla.
- Plantillas obligatorias para Java desde semana 10:
- Main.java listo, imports listos, estructura base lista.
- Así el tiempo se va al diseño, no al boilerplate.
- Traducción semanal “micro” (10–15 min):
- “Convierte este if/for/list de Python a Java”.
- Esto hace que cuando llegue POO, Java ya sea familiar.
- Ayudantía como “clínica” (no como segunda clase teórica):
- 70% práctica guiada, 20% trabajo en pares, 10% retro.
- Si quieres, en el siguiente paso te lo dejo aún más “universitario”:
- por cada semana: objetivo medible, lecturas, actividad de aula, actividad de ayudantía, tarea, criterios de evaluación (mini rúbrica).
- Principio del formulario
- Otra version del programa con fechas
- 1) Chequeo de viabilidad con tus restricciones UDLA
- Lo que ya cumple
- Al menos 1 evaluación en semana 06–11/04: tu Cátedra 1 (08/04) cumple perfecto.
- Semana de consolidación 18–24/05: la usas bien como refuerzo/recuperación (sin evaluación sumativa).
- Al menos 2 evaluaciones a semana 25–30/05: tu Cátedra 2 (27/05) + Ejercicios previos ya aseguran “≥2”.
- Examen dentro de semana de exámenes 30/06–04/07: 03/07 está perfecto.
- Distribución por unidades del programa: Unidad 1 (fundamentos), Unidad 2 (Python estructurado), Unidad 3 (POO en Java) está alineado con el programa.
- Ajuste clave (operativo)
- MiUdla “Fijar Pruebas” al 14/03: para llegar sin estrés, te conviene que todas las evaluaciones queden definidas desde semana 1, incluyendo “Examen final (fecha tentativa)” como pendiente planificada.
- 25/03 suspensión de módulo 9 (reunión semestral): cae miércoles de semana 4. Para que no te rompa el hilo, te propongo un “plan B” listo: esa semana el miércoles queda como material asincrónico corto + quiz diagnóstico sin nota (o traslado del contenido al viernes).
- 2) Evaluaciones: mismo calendario, pero más pedagógicas (y coherentes con resultados de aprendizaje)
- Ponderaciones oficiales del syllabus: Examen 35%, Cátedras 50% (2×25%), Ejercicios 15% (4×3,75%).
- Calendario evaluativo (mantengo tus fechas, solo mejoro el “cómo”)
- Ejercicio 1 (3,75%) — Vie 27/03
- Tipo: “trazas + casos de prueba” (condicionales/bucles).
- Pedagogía: 30% trazas / 70% código corto.
- Cátedra 1 (25%) — Mié 08/04 (1er hito)
- Tipo: prueba práctica guiada (parte A en papel: diseño/algoritmo; parte B en PC: implementación).
- Evalúa: RAA1 + inicio RAA2.
- 202610ACI106_sillabus
- Ejercicio 2 (3,75%) — Vie 17/04
- Tipo: refactor a funciones + tests manuales.
- Ejercicio 3 (3,75%) — Vie 08/05
- Tipo: “traducción controlada” Python→Java (con plantilla).
- Ejercicio 4 (3,75%) — Vie 15/05
- Tipo: mini-POO (clase + constructor + getters/setters + regla simple).
- Cátedra 2 (25%) — Mié 27/05 (2do hito)
- Tipo: Java aplicado + modelado (clases + excepciones + colecciones).
- Evalúa: cierre RAA2 e inicio fuerte RAA3.
- 202610ACI106_sillabus
- Examen final integrador (35%) — Vie 03/07
- Tipo: caso completo (tickets/incidencias) con POO + robustez + lectura de requerimientos.
- Evalúa: RAA1–RAA3 integrados.
- 202610ACI106_sillabus
- La mejora pedagógica más importante: “doble lenguaje” sin doble carga
- En cada evaluación, el enunciado trae 2 capas:
- Capa común: problema + casos + criterios (sirve para ambos lenguajes).
- Capa de lenguaje:
- hasta semana 9: Python completo + “micro-espejo Java”
- desde semana 10: Java completo (Python queda como apoyo/lectura)
- 3) Plan semana a semana (18 semanas) mejorado (bilingüe desde semana 1)
- Mantengo tu estructura (miércoles teoría / viernes ayudantía), pero la vuelvo más “a prueba de calendario” y más explícita en el puente Python→Java.

</details>

<a id="fuentes-y-referencias"></a>

<details>
<summary><b>9. Fuentes y referencias</b></summary>

Este programa referencia los siguientes documentos:

- Calendario Académico UDLA 2026 (mencionado como `Calendario-Academico-UDLA-2026_…`).
- Syllabus ACI106 (mencionado como `202610ACI106_sillabus`).

</details>
