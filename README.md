# ACI106 – Programación (Python → Java) | UDLA 2026-1

**Código:** ACI106 · **NRC:** 17000 · **Sección:** 402 · **Sala:** A316 (Edif. A)

Repositorio oficial del curso **ACI106: Programación** (UDLA 2026-1).  
El curso está diseñado para que aprendas **fundamentos de programación** en **Python** y llegues a **Programación Orientada a Objetos (POO) en Java** sin “partir de cero” a mitad de semestre.

---

## Índice

1. [Horario](#horario)  
2. [Evaluaciones](#evaluaciones)  
3. [Reglas del curso](#reglas-del-curso)  
4. [Estructura del repositorio](#estructura-del-repositorio)  
5. [Mapa semanal (recursos por fecha)](#mapa-semanal-recursos-por-fecha)  
6. [Cómo ejecutar](#cómo-ejecutar)  

---

## Horario

**Miércoles (Teoría / Aula) – Sala A316**  
- 13:10–14:10  
- 14:20–15:20  
- 15:30–16:30  

**Viernes (Ayudantía / Laboratorio) – Sala A316**  
- 14:20–15:20  
- 15:30–16:30  

---

## Evaluaciones

**Ponderaciones oficiales:** Examen **35%**, Cátedras **50%** (2), Ejercicios **15%** (4).

| Evaluación | Fecha | Ponderación | Recursos |
|---|---:|---:|---|
| Ejercicio 1 (E1) | Vie 27/03 | 3,75% | [`evaluaciones/E1/`](evaluaciones/E1/) |
| Cátedra 1 (C1) | Mié 08/04 | 25% | [`evaluaciones/C1/`](evaluaciones/C1/) |
| Ejercicio 2 (E2) | Vie 17/04 | 3,75% | [`evaluaciones/E2/`](evaluaciones/E2/) |
| Ejercicio 3 (E3) | Vie 08/05 | 3,75% | [`evaluaciones/E3/`](evaluaciones/E3/) |
| Ejercicio 4 (E4) | Vie 15/05 | 3,75% | [`evaluaciones/E4/`](evaluaciones/E4/) |
| Cátedra 2 (C2) | Mié 27/05 | 25% | [`evaluaciones/C2/`](evaluaciones/C2/) |
| **Examen final integrador** | Vie 03/07 | **35%** | [`evaluaciones/EXAMEN/`](evaluaciones/EXAMEN/) |

> **Examen final:** integrador (aplica todo lo aprendido). El caso final mostrará utilidad real de lo visto en el semestre.

---

## Reglas del curso

- **Asistencia mínima:** 50% (según reglamento).  
- **Retraso:** se permite un retraso máximo de **15 minutos**. Pasado ese tiempo, se registra **inasistencia**.  
- **Uso de IA generativa (ChatGPT, etc.):** **NO permitido** para resolver problemas, ejercicios o escribir código durante clases/ayudantías ni durante evaluaciones en sala.  
  - Motivo: es tu **primer curso de programación**; el objetivo es desarrollar práctica y pensamiento propio.

**Nota operativa UDLA:**  
- **Miércoles 25/03:** reunión semestral con suspensión de **módulo 9**. Si afecta alguno de nuestros bloques del miércoles, se aplicará Plan B: cápsula asincrónica breve + guía, y recuperación práctica el viernes.

---

## Estructura del repositorio

Esta es la estructura recomendada para que los links de este README funcionen. Puedes ajustar nombres, pero mantén consistencia.

```text
.
├─ clases/                 # material por semana (slides, guías, ejemplos)
│  ├─ semana-01/
│  ├─ semana-02/
│  └─ ...
├─ ayudantias/             # laboratorios guiados y katas por semana
│  ├─ semana-01/
│  ├─ semana-02/
│  └─ ...
├─ evaluaciones/           # E1–E4, C1–C2, Examen (enunciados, rúbricas, plantillas)
│  ├─ E1/
│  ├─ C1/
│  ├─ E2/
│  ├─ E3/
│  ├─ E4/
│  ├─ C2/
│  └─ EXAMEN/
├─ plantillas/             # plantillas Python/Java (starter, helpers)
└─ recursos/               # bibliografía, enlaces, cheatsheets, etc.
```

> Si un enlace aún no existe, es porque el recurso está “pendiente de subir” (pero el link ya queda listo).

---

## Mapa semanal (recursos por fecha)

Convención de links por semana:
- Teoría: `clases/semana-XX/`
- Ayudantía: `ayudantias/semana-XX/`
- Código/ejemplos: dentro de esas carpetas
- Evaluaciones: `evaluaciones/EXX/` o `evaluaciones/CX/`

<details>
<summary><b>Semana 01 (02/03–08/03) — Diagnóstico, pensamiento algorítmico y entorno</b></summary>

- Teoría: [`clases/semana-01/`](clases/semana-01/)
- Ayudantía: [`ayudantias/semana-01/`](ayudantias/semana-01/)

</details>

<details>
<summary><b>Semana 02 (09/03–15/03) — Variables, tipos, I/O (Python) + mini espejo Java</b></summary>

- Teoría: [`clases/semana-02/`](clases/semana-02/)
- Ayudantía: [`ayudantias/semana-02/`](ayudantias/semana-02/)

</details>

<details>
<summary><b>Semana 03 (16/03–22/03) — Condicionales + casos borde + pruebas manuales</b></summary>

- Teoría: [`clases/semana-03/`](clases/semana-03/)
- Ayudantía: [`ayudantias/semana-03/`](ayudantias/semana-03/)

</details>

<details>
<summary><b>Semana 04 (23/03–29/03) — Bucles, contadores y acumuladores · E1 (27/03)</b></summary>

- Teoría: [`clases/semana-04/`](clases/semana-04/)
- Ayudantía: [`ayudantias/semana-04/`](ayudantias/semana-04/)
- Evaluación E1: [`evaluaciones/E1/`](evaluaciones/E1/)
  - Enunciado: [`evaluaciones/E1/ENUNCIADO.md`](evaluaciones/E1/ENUNCIADO.md)
  - Starter: [`evaluaciones/E1/e1_menu_atencion_STARTER.py`](evaluaciones/E1/e1_menu_atencion_STARTER.py)
  - Pauta 3 niveles: [`evaluaciones/E1/Pauta_E1_3Niveles.xlsx`](evaluaciones/E1/Pauta_E1_3Niveles.xlsx)
  - Diagrama de flujo: [`evaluaciones/E1/Diagrama_Flujo_E1.png`](evaluaciones/E1/Diagrama_Flujo_E1.png)

</details>

<details>
<summary><b>Semana 05 (30/03–05/04) — Patrones algorítmicos (bandera/corte/búsqueda)</b></summary>

- Teoría: [`clases/semana-05/`](clases/semana-05/)
- Ayudantía: [`ayudantias/semana-05/`](ayudantias/semana-05/)

</details>

<details>
<summary><b>Semana 06 (06/04–12/04) — Repaso guiado tipo prueba · C1 (08/04)</b></summary>

- Teoría: [`clases/semana-06/`](clases/semana-06/)
- Ayudantía: [`ayudantias/semana-06/`](ayudantias/semana-06/)
- Evaluación C1: [`evaluaciones/C1/`](evaluaciones/C1/)
  - Enunciado: [`evaluaciones/C1/ENUNCIADO.md`](evaluaciones/C1/ENUNCIADO.md)
  - Starter: [`evaluaciones/C1/c1_tickets_STARTER.py`](evaluaciones/C1/c1_tickets_STARTER.py)
  - Pauta 3 niveles: [`evaluaciones/C1/Pauta_C1_3Niveles.xlsx`](evaluaciones/C1/Pauta_C1_3Niveles.xlsx)

</details>

<details>
<summary><b>Semanas 07–09 (13/04–03/05) — Python estructurado + puente a Java</b></summary>

- Semana 07: [`clases/semana-07/`](clases/semana-07/) · [`ayudantias/semana-07/`](ayudantias/semana-07/) · **E2 (17/04)** → [`evaluaciones/E2/`](evaluaciones/E2/)
- Semana 08: [`clases/semana-08/`](clases/semana-08/) · [`ayudantias/semana-08/`](ayudantias/semana-08/)
- Semana 09: [`clases/semana-09/`](clases/semana-09/) · [`ayudantias/semana-09/`](ayudantias/semana-09/)

</details>

<details>
<summary><b>Semanas 10–13 (04/05–31/05) — Java bootcamp + POO base + consolidación</b></summary>

- Semana 10: [`clases/semana-10/`](clases/semana-10/) · [`ayudantias/semana-10/`](ayudantias/semana-10/) · **E3 (08/05)** → [`evaluaciones/E3/`](evaluaciones/E3/)
- Semana 11: [`clases/semana-11/`](clases/semana-11/) · [`ayudantias/semana-11/`](ayudantias/semana-11/) · **E4 (15/05)** → [`evaluaciones/E4/`](evaluaciones/E4/)
- Semana 12: [`clases/semana-12/`](clases/semana-12/) · [`ayudantias/semana-12/`](ayudantias/semana-12/)
- Semana 13: [`clases/semana-13/`](clases/semana-13/) · [`ayudantias/semana-13/`](ayudantias/semana-13/) · **C2 (27/05)** → [`evaluaciones/C2/`](evaluaciones/C2/)

</details>

<details>
<summary><b>Semanas 14–18 (01/06–05/07) — POO aplicada + integración + examen</b></summary>

- Semana 14: [`clases/semana-14/`](clases/semana-14/) · [`ayudantias/semana-14/`](ayudantias/semana-14/)
- Semana 15: [`clases/semana-15/`](clases/semana-15/) · [`ayudantias/semana-15/`](ayudantias/semana-15/)
- Semana 16: [`clases/semana-16/`](clases/semana-16/) · [`ayudantias/semana-16/`](ayudantias/semana-16/)
- Semana 17: [`clases/semana-17/`](clases/semana-17/) · [`ayudantias/semana-17/`](ayudantias/semana-17/)
- Semana 18: **Examen (03/07)** → [`evaluaciones/EXAMEN/`](evaluaciones/EXAMEN/)

</details>

---

## Cómo ejecutar

### Python
```bash
python --version
python evaluaciones/E1/e1_menu_atencion_STARTER.py
```

### Java (cuando corresponda)
```bash
javac -d out src/Main.java src/models/*.java src/utils/*.java
java -cp out Main
```

---

## Notas para docentes / ayudantes (opcional)
- Publicar pauta/rúbrica junto al enunciado.
- Entregar retroalimentación al publicar resultados y, cuando aplique, revisar en la clase siguiente.
