# 🛡️ MÓDULO 1 — Git & GitHub Desde Cero a Profesional

![Git](https://img.shields.io/badge/Git-Control%20de%20Versiones-orange?logo=git)
![GitHub](https://img.shields.io/badge/GitHub-Plataforma-black?logo=github)
![Nivel](https://img.shields.io/badge/Nivel-Primer%20Año-blue)
![Estado](https://img.shields.io/badge/Estado-Activo-success)

---

## 📚 Introducción

Este módulo te enseñará:

- Qué es Git y cómo funciona
- Qué es GitHub y cómo se usa profesionalmente
- Cómo instalar Git en cualquier sistema operativo
- Cómo crear tu cuenta en GitHub
- Cómo conectar Git local con GitHub usando SSH
- Flujo profesional real de trabajo
- Buenas prácticas desde el día 1

---

# 📌 Índice

1. [¿Por qué Git?](#-por-qué-git)
2. [¿Qué es Git?](#-qué-es-git)
3. [¿Qué es GitHub?](#%EF%B8%8F-qué-es-github)
4. [Instalación de Git](#-instalación-de-git)
5. [Verificación de Instalación](#-verificación-de-instalación)
6. [Crear Cuenta en GitHub](#-crear-cuenta-en-github)
7. [Configuración Inicial de Git](#-configuración-inicial-de-git)
8. [Configuración de Llaves SSH](#-configuración-de-llaves-ssh)
9. [Conectar Proyecto Local a GitHub](#-conectar-proyecto-local-a-github)
10. [Flujo Profesional de Trabajo](#-flujo-profesional-de-trabajo)
11. [Buenas Prácticas](#-buenas-prácticas)
12. [Errores Comunes](#-errores-comunes)
13. [Checklist Profesional](#-checklist-profesional)

---

# 🚨 ¿Por qué Git?

Problema clásico:

- proyecto_final.py  
- proyecto_final_v2.py  
- proyecto_final_definitivo.py  

Sin control de versiones:

- No sabes qué cambió
- No puedes volver atrás
- No puedes colaborar bien

Git resuelve esto guardando versiones completas del proyecto.

## $\color{red}{\text{🛡️ El Escenario "Con Git" (El Superpoder)}}$

**Máquina del Tiempo**: Git guarda una "foto" ($\color{red}{\text{commit}}$) de tu proyecto cada vez que tú quieres. Si rompes algo hoy, puedes volver a la versión de ayer en 1 segundo.

**Trabajo en Equipo**: GitHub fusiona el trabajo de 10, 50 o 1000 ingenieros automáticamente, avisando si hay conflictos lógicos.

**Seguridad**: Tu código vive en la nube (GitHub). Si tu laptop explota, bajas el código en una nueva y sigues trabajando.

**En resumen**: Programar sin Git es como escribir una tesis de 500 páginas sin guardar el archivo nunca.

---

# 🧠 ¿Qué es Git?

Git es un sistema de control de versiones distribuido.

Guarda “fotografías” del proyecto llamadas commits.

Cada $\color{red}{\text{commit}}$ tiene:

- Autor
- Fecha
- Identificador único
- Mensaje descriptivo

Es una máquina del tiempo para tu código.

---

# ☁️ ¿Qué es GitHub?

GitHub es una plataforma en la nube que aloja repositorios de Git.

| Git | GitHub |
|------|--------|
| Herramienta local | Plataforma web |
| Controla versiones | Permite colaboración |
| Funciona offline | Respaldo en la nube |

---

# 💻 Instalación de Git

---

## 🪟 WINDOWS

1. Ir a: https://git-scm.com
2. Descargar versión para Windows
3. Ejecutar instalador
4. Dejar opciones por defecto
5. Instalar

Se instalará también **Git Bash**.

---

## 🍎 MAC

### Opción 1 (recomendada)

Instalar Homebrew (si no lo tienes):

```bash
brew install git
```

### Opción 2

Instalar Xcode Command Line Tools:

```bash
xcode-select --install
```

## 🐧 LINUX

Debian/Ubuntu
For the latest stable version for your release of Debian/Ubuntu

```bash
apt-get install git
```
For Ubuntu, this PPA provides the latest stable upstream Git version

```bash
add-apt-repository ppa:git-core/ppa
apt update; apt install git
```

**Para más información de Instalación visita el siguiente link: https://git-scm.com/install/windows**

🔎 Verificación de Instalación

En terminal:

git --version


Debe mostrar algo como:

git version 2.x.x

🌐 Crear Cuenta en GitHub

Ir a https://github.com

Click en "Sign up"

Ingresar email

Crear contraseña

Elegir username profesional

Verificar correo

Consejo profesional:
Usa un username serio. Evita cosas infantiles.

⚙️ Configuración Inicial de Git

Configura tu identidad (una sola vez):

git config --global user.name "Tu Nombre"
git config --global user.email "tu_email@gmail.com"


Verificar:

git config --list

🔐 Configuración de Llaves SSH
1️⃣ Generar llave
ssh-keygen -t ed25519 -C "tu_email@gmail.com"


Presiona ENTER a todo.

2️⃣ Iniciar agente SSH
Windows / Mac
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

3️⃣ Copiar llave pública
Windows (Git Bash)
cat ~/.ssh/id_ed25519.pub | clip

Mac
pbcopy < ~/.ssh/id_ed25519.pub

Linux
cat ~/.ssh/id_ed25519.pub


Copiar manualmente.

4️⃣ Agregar llave a GitHub

Ir a GitHub

Settings

SSH and GPG Keys

New SSH Key

Pegar clave

Guardar

5️⃣ Verificar conexión
ssh -T git@github.com


Debe decir:

Hi username! You've successfully authenticated

🔗 Conectar Proyecto Local a GitHub
1️⃣ Crear repositorio en GitHub

Click en "New"

Nombre del repo

No marcar README si ya tienes proyecto local

2️⃣ En proyecto local
git init
git add .
git commit -m "Initial commit"

3️⃣ Conectar repositorio remoto
git remote add origin git@github.com:USERNAME/REPO.git


Verificar:

git remote -v

4️⃣ Subir proyecto
git push -u origin main

🔄 Flujo Profesional de Trabajo

Siempre:

git status
git add .
git commit -m "mensaje claro"
git push


En equipo:

git pull


Antes de trabajar.

🌿 Uso de Ramas (Profesional)

Crear rama:

git checkout -b nueva_funcionalidad


Volver a main:

git checkout main


Fusionar:

git merge nueva_funcionalidad

✅ Buenas Prácticas

Commits pequeños y frecuentes

Mensajes claros

No subir archivos grandes innecesarios

Usar .gitignore

Hacer pull antes de push

Usar ramas para experimentar

📄 Ejemplo de .gitignore (Python)
__pycache__/
*.pyc
.env
venv/

❌ Errores Comunes

Hacer un commit gigante

Mensajes como "cambios"

No usar ramas

Subir claves privadas

No usar SSH

🧠 Tips Profesionales

Usa git log --oneline

Usa git diff

Usa git branch

Aprende a leer conflictos

Nunca subas archivos sensibles

Crea commits descriptivos

🧪 Checklist Profesional

☑ Git instalado
☑ Cuenta GitHub creada
☑ SSH configurado
☑ Primer repositorio creado
☑ Primer push realizado
☑ Rama creada y fusionada

🎯 Conclusión

Git no es solo una herramienta.

Es una competencia profesional obligatoria.

Si dominas Git:

Piensas como ingeniero

Trabajas como profesional

Colaboras como industria

Bienvenido al desarrollo profesional.
