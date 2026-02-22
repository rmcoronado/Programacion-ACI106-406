# Clase 1: Fundamentos de Git y GitHub

---

## 📌 Índice

1. [¿Qué es Git?](#qué-es-git)
2. [¿Qué es GitHub?](#qué-es-github)
3. [Diferencia entre Git y GitHub](#diferencia-entre-git-y-github)
4. [Instalación y Configuración Inicial](#instalación-y-configuración-inicial)
5. [Flujo básico de trabajo en Git](#flujo-básico-de-trabajo-en-git)
6. [Estados de los archivos](#estados-de-los-archivos)
7. [Comandos fundamentales](#comandos-fundamentales)
   - [git status](#git-status)
   - [git add](#git-add)
   - [git commit](#git-commit)
8. [Historial y versiones](#historial-y-versiones)
9. [Ramas (branches)](#ramas-branches)
10. [Merge y resolución de conflictos](#merge-y-resolución-de-conflictos)
11. [Conectar repositorio local con GitHub](#conectar-repositorio-local-con-github)
12. [Fetch, Pull y Push](#fetch-pull-y-push)
13. [Pull vs Pull --rebase](#pull-vs-pull---rebase)

---

## ¿Qué es Git?

Git es un sistema de control de versiones distribuido. Permite:

- Registrar cambios en archivos
- Volver a versiones anteriores
- Trabajar en paralelo mediante ramas
- Colaborar sin sobrescribir el trabajo de otros

Concepto clave: **Git guarda snapshots (fotografías) del proyecto**, no solo diferencias.

---

## ¿Qué es GitHub?

GitHub es una plataforma en la nube que aloja repositorios Git y permite:

- Compartir código
- Colaborar en equipo
- Gestionar issues y proyectos
- Automatizar procesos (CI/CD)

---

## Diferencia entre Git y GitHub

| Git | GitHub |
|------|--------|
| Herramienta local | Plataforma remota |
| Controla versiones | Aloja repositorios |
| Funciona sin internet | Requiere internet |

---

## Instalación y Configuración Inicial

```bash
git --version
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

Ver configuración:

```bash
git config --list
```

---

## Flujo básico de trabajo en Git

Directorio de trabajo → Staging Area → Repositorio (commit)

1. Modificas archivos
2. `git add`
3. `git commit`

---

## Estados de los archivos

- Untracked
- Modified
- Staged
- Committed

---

## Comandos fundamentales

### git status

Muestra:

- Archivos modificados
- Archivos en staging
- Archivos no rastreados
- Rama actual

Mensaje típico:

```bash
On branch main
Changes not staged for commit:
```

---

### git add

Agrega archivos al staging.

```bash
git add archivo.txt
git add .
```

No guarda cambios definitivamente, solo los prepara.

---

### git commit

Crea un snapshot del proyecto.

```bash
git commit -m "Mensaje descriptivo"
```

Con `-v` muestra diferencias incluidas en el commit.

---

## Historial y versiones

Ver historial:

```bash
git log
```

Moverse entre commits:

```bash
git checkout <hash>
```

Volver a la rama principal:

```bash
git checkout main
```

---

## Ramas (branches)

Crear rama:

```bash
git branch nueva-rama
```

Cambiar de rama:

```bash
git checkout nueva-rama
```

Crear y cambiar en un paso:

```bash
git checkout -b nueva-rama
```

---

## Merge y resolución de conflictos

Fusionar rama:

```bash
git merge nueva-rama
```

Si hay conflicto, Git mostrará marcadores:

```text
<<<<<<< HEAD
código actual
=======
código entrante
>>>>>>> nueva-rama
```

Pasos para resolver:

1. Editar archivo
2. Eliminar marcadores
3. `git add archivo`
4. `git commit`

---

## Conectar repositorio local con GitHub

1. Crear repositorio en GitHub
2. En carpeta local:

```bash
git init
git remote add origin https://github.com/usuario/repositorio.git
git branch -M main
git push -u origin main
```

Ver remotos:

```bash
git remote -v
```

---

## Fetch, Pull y Push

### git fetch

Descarga cambios del remoto sin fusionarlos.

### git pull

Equivale a:

```bash
git fetch
git merge
```

Actualiza tu rama local.

### git push

Envía commits locales al repositorio remoto.

Se recomienda hacer `pull` antes de `push` para evitar conflictos.

---

## Pull vs Pull --rebase

### Pull normal

Crea un commit de merge.

### Pull --rebase

Reescribe commits locales encima del remoto.

```bash
git pull --rebase origin main
```

Ventaja: historial más limpio.

---

# 🎯 Recomendación pedagógica

Orden sugerido para dictar la clase:

1. Conceptos (Git vs GitHub)
2. Flujo mental (Working → Staging → Commit)
3. Comandos básicos
4. Historial
5. Ramas
6. Conflictos
7. Conexión con GitHub
8. Pull / Push / Rebase

---

---

# 🧠 Diagramas Mentales Explicativos

## 1️⃣ Modelo Mental de Git

```
                ┌──────────────────────┐
                │   Working Directory  │
                │ (Tus archivos reales)│
                └──────────┬───────────┘
                           │ git add
                           ▼
                ┌──────────────────────┐
                │     Staging Area     │
                │ (Zona de preparación)│
                └──────────┬───────────┘
                           │ git commit
                           ▼
                ┌──────────────────────┐
                │     Repository       │
                │   (Historial Git)    │
                └──────────────────────┘
```

📌 Idea clave: **Git no guarda cambios automáticamente. Tú decides qué entra en cada commit.**

---

## 2️⃣ Modelo Mental Local vs Remoto

```
        TU COMPUTADOR                    GITHUB

   ┌──────────────────┐          ┌──────────────────┐
   │   Repo Local     │          │   Repo Remoto    │
   │                  │          │                  │
   │  commit A        │  push →  │  commit A        │
   │  commit B        │          │  commit B        │
   └──────────────────┘          └──────────────────┘

                ← pull
```

- `push` = Enviar cambios
- `pull` = Traer cambios
- `fetch` = Mirar cambios sin mezclarlos

---

## 3️⃣ Modelo Mental de Ramas

```
main
  ●───●───●──────────────
           \
            ●───●  feature-login
```

Cada rama es una línea independiente de desarrollo.

---

# 🧪 Ejercicios Guiados Paso a Paso

---

## 🧩 Ejercicio 1: Primer repositorio

### Objetivo
Entender el flujo add → commit

### Paso 1
Crear carpeta:

```bash
mkdir mi-primer-repo
cd mi-primer-repo
```

### Paso 2
Inicializar Git:

```bash
git init
```

### Paso 3
Crear archivo:

```bash
echo "Hola Git" > archivo.txt
```

### Paso 4
Ver estado:

```bash
git status
```

Pregunta: ¿Qué estado tiene el archivo?

### Paso 5
Agregar al staging:

```bash
git add archivo.txt
```

### Paso 6
Crear commit:

```bash
git commit -m "Primer commit"
```

### Paso 7
Ver historial:

```bash
git log
```

---

## 🧩 Ejercicio 2: Simular error y volver atrás

### Paso 1
Modificar archivo:

```bash
echo "Cambio incorrecto" >> archivo.txt
```

### Paso 2
Ver diferencias:

```bash
git diff
```

### Paso 3
Descartar cambios:

```bash
git restore archivo.txt
```

Verifica con `git status`.

---

## 🧩 Ejercicio 3: Trabajar con ramas

### Paso 1
Crear rama nueva:

```bash
git checkout -b nueva-funcionalidad
```

### Paso 2
Modificar archivo y hacer commit.

### Paso 3
Volver a main:

```bash
git checkout main
```

Observa cómo los cambios desaparecen.

### Paso 4
Fusionar:

```bash
git merge nueva-funcionalidad
```

---

## 🧩 Ejercicio 4: Simular conflicto

1. Crear rama A y modificar una línea.
2. Volver a main y modificar la misma línea.
3. Intentar hacer merge.

Git mostrará conflicto.

Resolver:

1. Editar archivo
2. Eliminar marcadores
3. `git add archivo`
4. `git commit`

---

# 🎓 Dinámica sugerida en clase

1. Explicar modelo mental
2. Dibujarlo en pizarra
3. Hacer ejercicio 1 en vivo
4. Hacer que los estudiantes repitan
5. Introducir error controlado
6. Mostrar cómo Git salva el día

---

Si quieres, puedo ahora:

- Convertir esto en una guía tipo laboratorio evaluado
- Agregar rúbrica de evaluación
- Diseñar Clase 2 (colaboración real en equipo)
- Crear un repositorio ejemplo estructurado

