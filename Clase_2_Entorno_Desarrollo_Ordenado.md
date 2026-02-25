# 🚀 Clase 2 --- Configuración Profesional de tu Entorno de Desarrollo

## 🎯 Objetivo de la Clase

Dejar tu computador listo para programar en **Python y Java** de forma
cómoda y profesional.

Al finalizar esta clase podrás:

-   Configurar Visual Studio Code correctamente.
-   Instalar y usar Python con entornos virtuales.
-   Crear un mini proyecto profesional en Python.
-   Ejecutar tu primer programa en Java.
-   Usar Git dentro de VS Code para guardar el historial de tu trabajo.

------------------------------------------------------------------------

# 📑 Índice

1.  Instalación de Visual Studio Code\
2.  Tour rápido por VS Code\
3.  Configuración del entorno Python\
4.  Mini Proyecto Profesional en Python\
5.  Buenas prácticas (requirements y gitignore)\
6.  Cápsula teórica: Bytecode y REPL\
7.  Git en VS Code\
8.  Ecosistema Java: Instalación y Hola Mundo

------------------------------------------------------------------------

# 1️⃣ Instalación de Visual Studio Code

## Descarga oficial

https://code.visualstudio.com/download

### 🪟 Windows

-   Descargar **User Installer**
-   Ejecutar instalador
-   Marcar "Add to PATH"
-   Reiniciar terminal
-   Verificar con:

```{=html}
<!-- -->
```
    code

### 🍎 macOS

-   Descargar `.dmg`
-   Arrastrar a Aplicaciones
-   Activar comando `code` desde Command Palette:

```{=html}
<!-- -->
```
    Shell Command: Install 'code' command in PATH

### 🐧 Linux

-   Debian/Ubuntu:

```{=html}
<!-- -->
```
    sudo apt install ./archivo.deb

-   Snap:

```{=html}
<!-- -->
```
    sudo snap install --classic code

------------------------------------------------------------------------

# 2️⃣ Tour Rápido por VS Code

-   **Activity Bar** → Explorer, Search, Git, Run, Extensions\
-   **Explorer** → Archivos del proyecto\
-   **Editor** → Donde escribes código\
-   **Terminal Integrada** → Ctrl + ñ\
-   **Command Palette** → Ctrl + Shift + P

------------------------------------------------------------------------

# 3️⃣ Configuración del Entorno Python

## Instalación

Descargar desde: https://www.python.org

⚠ En Windows marcar: **Add Python to PATH**

Verificar:

    python --version

## Extensiones en VS Code

Instalar: - Python (Microsoft) - Pylance

------------------------------------------------------------------------

## Crear entorno virtual

En la raíz del proyecto:

    python -m venv venv

Activar:

Windows:

    venv\Scripts\activate

Mac/Linux:

    source venv/bin/activate

Si aparece `(venv)` está funcionando.

Salir:

    deactivate

------------------------------------------------------------------------

# 4️⃣ Mini Proyecto Profesional en Python

## Estructura

    mini_proyecto/
    │
    ├── venv/
    ├── src/
    │   └── mini_proyecto/
    │       ├── __init__.py
    │       ├── main.py
    │       ├── models/
    │       ├── services/
    │       └── utils/
    │
    ├── requirements.txt
    ├── README.md
    └── .gitignore

## Ejecutar correctamente

Desde la raíz:

    $env:PYTHONPATH="src"
    python -m mini_proyecto.main

------------------------------------------------------------------------

# 5️⃣ Buenas Prácticas

## requirements.txt

Instalar librerías:

    pip install requests

Generar archivo:

    pip freeze > requirements.txt

Instalar dependencias desde archivo:

    pip install -r requirements.txt

------------------------------------------------------------------------

## .gitignore

Contenido mínimo recomendado:

    venv/
    __pycache__/
    *.pyc
    .vscode/
    .DS_Store
    Thumbs.db

------------------------------------------------------------------------

# 6️⃣ Cápsula Teórica

## Bytecode (.pyc)

Python: 1. Lee archivo .py 2. Lo compila a bytecode 3. Guarda en
**pycache** 4. Ejecuta en la máquina virtual

No se suben a GitHub.

------------------------------------------------------------------------

## REPL

Modo interactivo:

    python

Ejemplo:

    >>> 2 + 2
    4

Salir:

    exit()

------------------------------------------------------------------------

# 7️⃣ Git en VS Code

Inicializar:

    git init

Agregar archivos:

    git add .

Primer commit:

    git commit -m "Primer commit del proyecto"

Si pide identidad:

    git config --global user.name "Tu Nombre"
    git config --global user.email "tu_email@gmail.com"

------------------------------------------------------------------------

# 8️⃣ Ecosistema Java

## Instalar Extension Pack for Java

Desde el marketplace de VS Code instalar:

-   Extension Pack for Java

## Instalar JDK

Verificar:

    java -version
    javac -version

------------------------------------------------------------------------

## Hola Mundo en Java

Archivo `HolaMundo.java`:

``` java
public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("Hola Mundo");
    }
}
```

⚠ El nombre de la clase pública debe coincidir con el nombre del
archivo.

Ejecutar desde VS Code con el botón Run.

------------------------------------------------------------------------

# ✅ Checklist Final

-   Crear proyecto Python con entorno virtual
-   Ejecutar código desde VS Code
-   Generar requirements.txt
-   Usar git para commits
-   Ejecutar programa en Java

------------------------------------------------------------------------

🎉 ¡Entorno profesional configurado!
