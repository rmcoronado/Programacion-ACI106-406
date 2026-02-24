# Clase 2 — Configuración de VS Code, Python y Terminal

> **Objetivo de la clase:** dejar tu entorno listo para programar en **Python** de forma cómoda y profesional: editor configurado, extensiones mínimas, terminal integrada, entornos virtuales, ejecución y depuración, y un flujo básico con Git/GitHub.

---

## 0) Checklist rápido (lo que debe quedar funcionando hoy)

Al finalizar la clase deberías poder:

- Abrir una carpeta de proyecto en VS Code (**workspace**).
- Crear y activar un entorno virtual (`.venv`) y seleccionar el intérprete correcto.
- Ejecutar un script Python desde VS Code y desde la terminal integrada.
- Usar IntelliSense/autocompletado y navegación básica.
- Depurar con breakpoints (F5).
- Hacer commit con Git y sincronizar con un repositorio remoto (GitHub).

---

## 1) Instalar Visual Studio Code

### 1.1 Descarga (Windows / macOS / Linux)

- Página oficial de descarga: https://code.visualstudio.com/download

**Recomendación general:** usa instaladores oficiales (User Installer en Windows, `.dmg` en macOS, `.deb`/`.rpm`/Snap en Linux) para tener actualizaciones y “buenas rutas” por defecto.

### 1.2 Instalación por sistema operativo (resumen práctico)

> Guías oficiales:  
> - Windows: https://code.visualstudio.com/docs/setup/windows  
> - macOS: https://code.visualstudio.com/docs/setup/mac  
> - Linux: https://code.visualstudio.com/docs/setup/linux  

#### Windows (recomendado: *User Installer*)
1. Descarga el instalador para Windows.
2. Ejecuta `VSCodeUserSetup-<version>.exe`.
3. Después de instalar, reinicia la terminal si quieres usar el comando `code`.

✅ **Tip importante:** el instalador agrega VS Code al `%PATH%` para poder usar `code .` (abre VS Code en esa carpeta).  
Referencia: https://code.visualstudio.com/docs/setup/windows. Para verificar, abrán git bash y escriban: 
```bash
code
```
Esto debería abrir automaticamente VS code.

#### macOS
1. Descarga el `.dmg`.
2. Arrastra `Visual Studio Code.app` a **Applications**.
3. Para habilitar `code` en la terminal:
   - Abre VS Code → Command Palette → ejecuta: **Shell Command: Install 'code' command in PATH**.

Referencia: https://code.visualstudio.com/docs/setup/mac

#### Linux (varía según distro)
- **Debian/Ubuntu (.deb)**:
  ```bash
  sudo apt install ./<file>.deb
  ```
- **Snap**:
  ```bash
  sudo snap install --classic code
  ```
- **RPM (Fedora/RHEL/SUSE)**:
  ```bash
  sudo dnf install <file>.rpm
  ```

Referencia: https://code.visualstudio.com/docs/setup/linux

---

## 2) Tour: “Get started” y lo mínimo del interfaz

Tutorial oficial (muy recomendado): https://code.visualstudio.com/docs/getstarted/getting-started

### 2.1 Lo esencial del UI
- **Activity Bar**: iconos de Explorer, Search, Source Control, Run and Debug, Extensions.
- **Explorer**: archivos/carpetas del proyecto.
- **Editor**: donde codificas.
- **Panel**: Terminal / Output / Debug Console / Problems.
- **Command Palette** (el “centro de mando”):
  - Atajo: `Ctrl+Shift+P` (Win/Linux) o `Cmd+Shift+P` (macOS).

Referencia: https://code.visualstudio.com/docs/getstarted/tips-and-tricks

---




## 3) Python en VS Code (setup + ejecución + edición)

### 3.1 Quick Start (visión general)
https://code.visualstudio.com/docs/python/python-quick-start

Qué te interesa hoy:
- Instalar la extensión Python
- Ejecutar scripts
- Primer debug (F5)
- Testing (cuando corresponda)

### 3.2 Tutorial Python (flujo completo)
https://code.visualstudio.com/docs/python/python-tutorial

Útil para entender el “camino típico”:
1) crear proyecto  
2) crear entorno  
3) instalar paquetes  
4) ejecutar  
5) debug  

---

## 4) Configurar ambientes (selección de intérprete y `.venv`)

Guía oficial: https://code.visualstudio.com/docs/python/environments

### 4.1 Seleccionar intérprete
Dos maneras:
- **Status Bar**: abajo, selecciona la versión de Python mostrada.
- **Command Palette**: `Python: Select Interpreter`

La selección se usa para:
- ejecutar,
- depurar,
- IntelliSense y features del lenguaje.

### 4.2 Crear un entorno desde VS Code (cuando esté disponible)
VS Code puede ayudarte a crear entornos y detectar dependencias.

Pistas útiles del doc:
- Por defecto puede crear `.venv` y elegir el Python más reciente disponible.
- Si existe `requirements.txt` o `pyproject.toml`, puede instalar dependencias automáticamente.

Referencia: https://code.visualstudio.com/docs/python/environments

### 4.3 Variables de entorno con `.env`
Puedes inyectar variables a terminales desde un archivo `.env` (útil para llaves/API en desarrollo).

Referencia: https://code.visualstudio.com/docs/python/environments

Ejemplo `.env` (NO lo subas al repo si tiene secretos):
```env
API_KEY=tu-clave
ENV=dev
```

---

## 5) Ejecutar Python

Guía oficial: https://code.visualstudio.com/docs/python/run

Formas recomendadas:
1. Botón **Run Python File in Terminal** (arriba a la derecha)
2. Clic derecho → **Run > Python File in Terminal**
3. Selecciona líneas → `Shift+Enter` → **Run Selection/Line...**

VS Code activa automáticamente el intérprete/entorno seleccionado en la terminal al ejecutar.

### 5.1 REPL (modo interactivo)
- **Native REPL**: `Python: Start Native REPL`
- **Terminal REPL**: `Python: Start Terminal REPL` o `python` / `python3` en terminal

Referencia: https://code.visualstudio.com/docs/python/run

---

## 6) Edición en Python (IntelliSense, navegación, productividad)

Guía oficial: https://code.visualstudio.com/docs/python/editing

Lo clave:
- **IntelliSense/autocompletado**
- **Auto-imports** (configurable)
- Navegación por símbolos, referencias y renombrado (F2)

Nota importante del doc:
- **Pylance** es el *language server* por defecto para Python y se instala junto al soporte Python (IntelliSense).

Referencia: https://code.visualstudio.com/docs/python/editing

---

## 7) Debugging con Python (breakpoints y `launch.json`)

Guía oficial: https://code.visualstudio.com/docs/python/debugging

### 7.1 Primer debug
- Pon un breakpoint (clic a la izquierda del número de línea)
- Presiona **F5**
- Elige “Python File” si te lo pide la primera vez

VS Code puede crear un archivo `launch.json` con configuración base.

Referencia: https://code.visualstudio.com/docs/python/debugging

### 7.2 Debug “mínimo” que usaremos
- Breakpoints
- Step Over / Step Into / Step Out
- Variables / Watch
- Debug Console

---

## 8) Git en VS Code (flujo mínimo)

Guía oficial: https://code.visualstudio.com/docs/sourcecontrol/overview

### 8.1 Prerrequisitos
- VS Code usa la instalación de Git de tu máquina (recomendado Git 2.0.0+).
- Configura usuario y email:

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

Referencia: https://code.visualstudio.com/docs/sourcecontrol/overview

### 8.2 Primer flujo (staging + commit)
1) Abre **Source Control**  
2) Revisa diffs  
3) Stage (botón `+`)  
4) Escribe mensaje  
5) Commit  

VS Code ofrece herramientas visuales (diff editor, graph) para revisar cambios.

---

## 9) Repos remotos (GitHub u otro host)

Guía oficial: https://code.visualstudio.com/docs/sourcecontrol/repos-remotes

Conceptos:
- **fetch**: descarga cambios sin mezclar
- **pull**: fetch + merge
- **push**: sube tus commits
- **sync**: combina pull + push (flujo recomendado cuando ya hay remoto)

Referencia: https://code.visualstudio.com/docs/sourcecontrol/repos-remotes

### 9.1 Clonar
- Command Palette → `Git: Clone`
- Elige repo y carpeta local

### 9.2 Publicar a GitHub (si el repo era local)
- Source Control → **Publish to GitHub**
- Define público/privado
- Selecciona archivos del commit inicial

Referencia: https://code.visualstudio.com/docs/sourcecontrol/repos-remotes

### 9.3 Agregar remoto (cuando necesitas `upstream`, etc.)
- Source Control → More Actions (...) → Remotes → Add Remote  
  o `Git: Add Remote`

Referencia: https://code.visualstudio.com/docs/sourcecontrol/repos-remotes

---


## 10) Actividad guiada (hands-on): “Hola VS Code + Python + Git”

### Paso A — Crea el proyecto
1. Crea carpeta `clase_2_vscode`
2. Ábrela en VS Code (File → Open Folder)
3. Crea `main.py` con este contenido:

```python
def saludar(nombre: str) -> str:
    return f"Hola, {nombre}!"

if __name__ == "__main__":
    print(saludar("mundo"))
```

### Paso B — Crea entorno y selecciona intérprete
1. Terminal integrada → crea `.venv`
2. Activa `.venv`
3. En la barra inferior, selecciona ese intérprete

### Paso C — Ejecuta y prueba modo interactivo
- Ejecuta con el botón **Run Python File in Terminal**
- Selecciona solo la función `saludar` y usa `Shift+Enter` (Run Selection)

### Paso D — Debug
- Pon breakpoint en `print(...)`
- F5 y observa variables/flujo

### Paso E — Git básico
- Inicializa repo (`Initialize Repository`) o `git init`
- Commit
- Publica/usa remoto (GitHub) si aplica

---

