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
Referencia: https://code.visualstudio.com/docs/setup/windows

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

## 3) Personalización (para trabajar cómodo sin “romper” el entorno)

Guía oficial: https://code.visualstudio.com/docs/getstarted/personalize-vscode

### 3.1 Settings: User vs Workspace

- **User settings**: aplican a todos tus proyectos.
- **Workspace settings**: aplican solo al proyecto actual (sobrescriben al User).

VS Code guarda settings en `settings.json` y se puede editar desde el editor gráfico o directo en JSON.

Referencia: https://code.visualstudio.com/docs/getstarted/personalize-vscode

Ejemplo (settings básicos recomendados para el curso):

```json
{
  "editor.formatOnSave": true,
  "editor.wordWrap": "on",
  "files.trimTrailingWhitespace": true,
  "terminal.integrated.defaultProfile.windows": "PowerShell"
}
```

> Nota: no hace falta que copies esto tal cual. La idea es que sepas **dónde** y **cómo** se configuran.

### 3.2 Temas (Color Theme)
- Command Palette → `Preferences: Color Theme`
- Previsualiza con flechas y confirma con Enter.

Referencia: https://code.visualstudio.com/docs/getstarted/personalize-vscode

### 3.3 Atajos (Keyboard Shortcuts)
- Abre el editor de atajos:
  - `Ctrl+K Ctrl+S` (Win/Linux) o `Cmd+K Cmd+S` (macOS)
- Busca un comando, edítalo y asigna una combinación.

Referencia: https://code.visualstudio.com/docs/getstarted/personalize-vscode

### 3.4 Profiles (perfiles)
Útil si un día quieres separar “Python/Data” de “Web/JS”, o tener un perfil “clase” vs “trabajo”.

- Puedes crear perfiles **vacíos** o copiando un template.
- Puedes exportar/importar perfiles (por ejemplo, para compartirlo con estudiantes).

Referencia: https://code.visualstudio.com/docs/configure/profiles

### 3.5 Settings Sync (sincronizar configuración)
Te permite sincronizar settings, atajos, snippets, extensiones y perfiles entre máquinas.

- Manage (ruedita) → **Backup and Sync Settings...**
- Inicia sesión con cuenta Microsoft o GitHub
- Elige qué sincronizar

Referencia: https://code.visualstudio.com/docs/configure/settings-sync

---

## 4) Extensiones (las mínimas para Python)

Guía oficial: https://code.visualstudio.com/docs/getstarted/extensions

### 4.1 Instalar/extender VS Code
- Abre **Extensions**:
  - `Ctrl+Shift+X` (Win/Linux) o `Cmd+Shift+X` (macOS)
- Busca y presiona **Install**.

### 4.2 Extensiones recomendadas para este curso (Python)
Instala al menos:
- **Python** (`ms-python.python`)
- **Pylance** (normalmente se instala junto a Python; provee IntelliSense)

> VS Code indica extensiones recomendadas según archivos y workspace.  
> Para administrar recomendaciones/instalación masiva, revisa:
> https://code.visualstudio.com/docs/configure/extensions/extension-marketplace

### 4.3 Instalar extensiones por terminal (opcional)
Si tienes `code` habilitado en PATH:

```bash
code --install-extension ms-python.python
```

Referencia: https://code.visualstudio.com/docs/configure/extensions/extension-marketplace

### 4.4 Recomendaciones por proyecto (extensiones.json)
Para sugerir extensiones a quien abra tu repo:

`.vscode/extensions.json`
```json
{
  "recommendations": [
    "ms-python.python"
  ]
}
```

Referencia: https://code.visualstudio.com/docs/configure/extensions/extension-marketplace

---

## 5) Workspaces (cómo ordenar tu proyecto)

Guía oficial: https://code.visualstudio.com/docs/editing/workspaces/workspaces

### 5.1 ¿Qué es un workspace?
En VS Code, un **workspace** es el contexto del proyecto abierto: carpetas + settings + (opcional) configuraciones de tasks/launch.

### 5.2 Single-folder vs Multi-root
- **Single-folder**: abres 1 carpeta.
  - Settings del proyecto quedan en: `.vscode/settings.json`
- **Multi-root**: abres varias carpetas en un mismo workspace.
  - Se guarda en un archivo: `*.code-workspace`

Puntos clave:
- Los **workspace settings** siempre sobrescriben los **user settings**.
- En multi-root puedes tener settings por “workspace” y settings por “carpeta”.

Referencia: https://code.visualstudio.com/docs/editing/workspaces/workspaces

---

## 6) Terminal integrada en VS Code

### 6.1 Primeros pasos (tutorial)
https://code.visualstudio.com/docs/terminal/getting-started

Aprenderás a:
- Abrir/crear terminales.
- Cambiar de shell (PowerShell / Bash / Zsh, etc.).
- Trabajar con varias terminales para tareas distintas.

### 6.2 Básicos útiles (features del terminal)
https://code.visualstudio.com/docs/terminal/basics

Cosas prácticas:
- **Split terminal** (paneles lado a lado).
- Copiar/pegar con atajos del sistema.
- Links detectables (Ctrl/Cmd + click).
- Abrir terminal en el área del editor o en una ventana nueva.

---

## 7) “Terminal basics” para el curso (comandos que vamos a usar)

> Esta sección es un mini “chuletario” para el curso (no es documentación de VS Code).

### 7.1 Navegación y archivos (macOS/Linux o Git Bash)
```bash
pwd
ls
cd carpeta
mkdir proyecto
touch main.py
```

### 7.2 Navegación y archivos (Windows PowerShell)
```powershell
pwd
ls
cd carpeta
mkdir proyecto
ni main.py
```

### 7.3 Python + entornos virtuales (recomendado)
#### Crear entorno
```bash
python -m venv .venv
```

#### Activar
- macOS/Linux:
  ```bash
  source .venv/bin/activate
  ```
- Windows (PowerShell):
  ```powershell
  .\.venv\Scripts\Activate.ps1
  ```

#### Instalar dependencias
```bash
python -m pip install requests
python -m pip freeze > requirements.txt
```

---

## 8) Python en VS Code (setup + ejecución + edición)

### 8.1 Quick Start (visión general)
https://code.visualstudio.com/docs/python/python-quick-start

Qué te interesa hoy:
- Instalar la extensión Python
- Ejecutar scripts
- Primer debug (F5)
- Testing (cuando corresponda)

### 8.2 Tutorial Python (flujo completo)
https://code.visualstudio.com/docs/python/python-tutorial

Útil para entender el “camino típico”:
1) crear proyecto  
2) crear entorno  
3) instalar paquetes  
4) ejecutar  
5) debug  

---

## 9) Configurar ambientes (selección de intérprete y `.venv`)

Guía oficial: https://code.visualstudio.com/docs/python/environments

### 9.1 Seleccionar intérprete
Dos maneras:
- **Status Bar**: abajo, selecciona la versión de Python mostrada.
- **Command Palette**: `Python: Select Interpreter`

La selección se usa para:
- ejecutar,
- depurar,
- IntelliSense y features del lenguaje.

### 9.2 Crear un entorno desde VS Code (cuando esté disponible)
VS Code puede ayudarte a crear entornos y detectar dependencias.

Pistas útiles del doc:
- Por defecto puede crear `.venv` y elegir el Python más reciente disponible.
- Si existe `requirements.txt` o `pyproject.toml`, puede instalar dependencias automáticamente.

Referencia: https://code.visualstudio.com/docs/python/environments

### 9.3 Variables de entorno con `.env`
Puedes inyectar variables a terminales desde un archivo `.env` (útil para llaves/API en desarrollo).

Referencia: https://code.visualstudio.com/docs/python/environments

Ejemplo `.env` (NO lo subas al repo si tiene secretos):
```env
API_KEY=tu-clave
ENV=dev
```

---

## 10) Ejecutar Python

Guía oficial: https://code.visualstudio.com/docs/python/run

Formas recomendadas:
1. Botón **Run Python File in Terminal** (arriba a la derecha)
2. Clic derecho → **Run > Python File in Terminal**
3. Selecciona líneas → `Shift+Enter` → **Run Selection/Line...**

VS Code activa automáticamente el intérprete/entorno seleccionado en la terminal al ejecutar.

### 10.1 REPL (modo interactivo)
- **Native REPL**: `Python: Start Native REPL`
- **Terminal REPL**: `Python: Start Terminal REPL` o `python` / `python3` en terminal

Referencia: https://code.visualstudio.com/docs/python/run

---

## 11) Edición en Python (IntelliSense, navegación, productividad)

Guía oficial: https://code.visualstudio.com/docs/python/editing

Lo clave:
- **IntelliSense/autocompletado**
- **Auto-imports** (configurable)
- Navegación por símbolos, referencias y renombrado (F2)

Nota importante del doc:
- **Pylance** es el *language server* por defecto para Python y se instala junto al soporte Python (IntelliSense).

Referencia: https://code.visualstudio.com/docs/python/editing

---

## 12) Debugging con Python (breakpoints y `launch.json`)

Guía oficial: https://code.visualstudio.com/docs/python/debugging

### 12.1 Primer debug
- Pon un breakpoint (clic a la izquierda del número de línea)
- Presiona **F5**
- Elige “Python File” si te lo pide la primera vez

VS Code puede crear un archivo `launch.json` con configuración base.

Referencia: https://code.visualstudio.com/docs/python/debugging

### 12.2 Debug “mínimo” que usaremos
- Breakpoints
- Step Over / Step Into / Step Out
- Variables / Watch
- Debug Console

---

## 13) Git en VS Code (flujo mínimo)

Guía oficial: https://code.visualstudio.com/docs/sourcecontrol/overview

### 13.1 Prerrequisitos
- VS Code usa la instalación de Git de tu máquina (recomendado Git 2.0.0+).
- Configura usuario y email:

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

Referencia: https://code.visualstudio.com/docs/sourcecontrol/overview

### 13.2 Primer flujo (staging + commit)
1) Abre **Source Control**  
2) Revisa diffs  
3) Stage (botón `+`)  
4) Escribe mensaje  
5) Commit  

VS Code ofrece herramientas visuales (diff editor, graph) para revisar cambios.

---

## 14) Repos remotos (GitHub u otro host)

Guía oficial: https://code.visualstudio.com/docs/sourcecontrol/repos-remotes

Conceptos:
- **fetch**: descarga cambios sin mezclar
- **pull**: fetch + merge
- **push**: sube tus commits
- **sync**: combina pull + push (flujo recomendado cuando ya hay remoto)

Referencia: https://code.visualstudio.com/docs/sourcecontrol/repos-remotes

### 14.1 Clonar
- Command Palette → `Git: Clone`
- Elige repo y carpeta local

### 14.2 Publicar a GitHub (si el repo era local)
- Source Control → **Publish to GitHub**
- Define público/privado
- Selecciona archivos del commit inicial

Referencia: https://code.visualstudio.com/docs/sourcecontrol/repos-remotes

### 14.3 Agregar remoto (cuando necesitas `upstream`, etc.)
- Source Control → More Actions (...) → Remotes → Add Remote  
  o `Git: Add Remote`

Referencia: https://code.visualstudio.com/docs/sourcecontrol/repos-remotes

---

## 15) Colaborar en GitHub desde VS Code (PRs e Issues)

Guía oficial: https://code.visualstudio.com/docs/sourcecontrol/github

VS Code integra GitHub principalmente vía la extensión:
- **GitHub Pull Requests and Issues**

### 15.1 Setup
1) Instala la extensión **GitHub Pull Requests and Issues**
2) Sign in (autenticación en navegador)
3) Vuelve a VS Code

Referencia: https://code.visualstudio.com/docs/sourcecontrol/github

### 15.2 Pull Requests (PR)
- Usa `GitHub Pull Requests: Create Pull Request`
- Completa título/descr, reviewers, labels, etc.
- Entra en “Review Mode” para revisar y comentar diffs

Referencia: https://code.visualstudio.com/docs/sourcecontrol/github

### 15.3 Issues
- Crear issues desde el panel de Issues
- Incluso generar issues desde “TODO”/selección

Referencia: https://code.visualstudio.com/docs/sourcecontrol/github

---

## 16) Actividad guiada (hands-on): “Hola VS Code + Python + Git”

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

## 17) Troubleshooting (fallas típicas y cómo atacarlas)

### “`code` no se reconoce como comando”
- Windows: reinicia la terminal después de instalar VS Code (PATH se actualiza).
- macOS: usa “Shell Command: Install 'code' command in PATH”.

Referencias:
- https://code.visualstudio.com/docs/setup/windows
- https://code.visualstudio.com/docs/setup/mac

### “VS Code no encuentra mi Python / el intérprete es incorrecto”
- Selecciona intérprete: `Python: Select Interpreter`.
- Revisa que el entorno esté activado y exista `.venv`.

Referencia: https://code.visualstudio.com/docs/python/environments

### “Git no aparece en Source Control”
- Instala Git y verifica `git --version`.
- VS Code usa el Git del sistema.

Referencia: https://code.visualstudio.com/docs/sourcecontrol/overview

---

## 18) Lecturas y referencias (oficiales)

1. Instalar VS Code (descarga): https://code.visualstudio.com/download  
2. Get started / tutorial: https://code.visualstudio.com/docs/getstarted/getting-started  
3. Personalización: https://code.visualstudio.com/docs/getstarted/personalize-vscode  
4. Extensiones: https://code.visualstudio.com/docs/getstarted/extensions  
5. Tips & tricks: https://code.visualstudio.com/docs/getstarted/tips-and-tricks  
6. Workspaces: https://code.visualstudio.com/docs/editing/workspaces/workspaces  
7. Git en VS Code: https://code.visualstudio.com/docs/sourcecontrol/overview  
8. Repos y remotos: https://code.visualstudio.com/docs/sourcecontrol/repos-remotes  
9. GitHub (PRs/Issues): https://code.visualstudio.com/docs/sourcecontrol/github  
10. Terminal (getting started): https://code.visualstudio.com/docs/terminal/getting-started  
11. Terminal (basics): https://code.visualstudio.com/docs/terminal/basics  
12. Python quick start: https://code.visualstudio.com/docs/python/python-quick-start  
13. Tutorial Python: https://code.visualstudio.com/docs/python/python-tutorial  
14. Run Python + REPL: https://code.visualstudio.com/docs/python/run  
15. Python editing: https://code.visualstudio.com/docs/python/editing  
16. Python debugging: https://code.visualstudio.com/docs/python/debugging  
17. Python environments: https://code.visualstudio.com/docs/python/environments  
