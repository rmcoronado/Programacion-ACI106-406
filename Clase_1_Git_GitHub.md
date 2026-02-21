# Clase 1: Fundamentos de Git y GitHub

------------------------------------------------------------------------

## 📌 Índice

1.  ¿Qué es Git?
2.  ¿Qué es GitHub?
3.  Diferencia entre Git y GitHub
4.  Flujo mental de Git
5.  Comandos fundamentales
6.  Ramas (branches)
7.  Merge y resolución de conflictos
8.  Conectar repositorio local con GitHub
9.  Fetch, Pull y Push
10. Ejercicios guiados

------------------------------------------------------------------------

# ¿Qué es Git?

Git es un sistema de control de versiones distribuido.

Permite: - Registrar cambios - Volver a versiones anteriores - Trabajar
en ramas - Colaborar sin sobrescribir trabajo

Git guarda *snapshots* (fotografías completas del proyecto).

------------------------------------------------------------------------

# ¿Qué es GitHub?

GitHub es una plataforma en la nube que aloja repositorios Git y permite
colaboración.

------------------------------------------------------------------------

# Diferencia entre Git y GitHub

  Git                  GitHub
  -------------------- --------------------
  Herramienta local    Plataforma remota
  Controla versiones   Aloja repositorios
  Funciona offline     Requiere internet

------------------------------------------------------------------------

# Flujo Mental de Git

Working Directory → Staging Area → Repository

    Working Directory
            │ git add
            ▼
    Staging Area
            │ git commit
            ▼
    Repository

------------------------------------------------------------------------

# Comandos Fundamentales

## git status

Muestra el estado actual del repositorio.

## git add

Agrega archivos al staging.

## git commit

Crea un snapshot del proyecto.

## git log

Muestra historial de commits.

------------------------------------------------------------------------

# Ramas (Branches)

Crear rama:

    git checkout -b nueva-rama

Fusionar:

    git merge nueva-rama

------------------------------------------------------------------------

# Resolución de Conflictos

Cuando ocurre un conflicto:

    <<<<<<< HEAD
    código actual
    =======
    código entrante
    >>>>>>> rama

Pasos: 1. Editar archivo 2. Eliminar marcadores 3. git add archivo 4.
git commit

------------------------------------------------------------------------

# Conectar Repo Local con GitHub

    git init
    git remote add origin https://github.com/usuario/repositorio.git
    git branch -M main
    git push -u origin main

------------------------------------------------------------------------

# Fetch, Pull y Push

-   git fetch → Descarga cambios sin fusionar
-   git pull → fetch + merge
-   git push → Envía commits al remoto

------------------------------------------------------------------------

# Ejercicios Guiados

## Ejercicio 1

1.  mkdir mi-repo
2.  git init
3.  crear archivo
4.  git add .
5.  git commit -m "Primer commit"

## Ejercicio 2

Modificar archivo → git diff → git restore archivo.txt

## Ejercicio 3

Crear rama → modificar → merge

------------------------------------------------------------------------

Fin de la Clase 1.
