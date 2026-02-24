# Clase 2 — Configuración de VS Code para usar Python, JAVA y Git (opcional)rminal

> **Objetivo de la clase:** dejar tu entorno listo para programar en **Python** y **JAVA** de forma cómoda y profesional: editor configurado, extensiones mínimas, terminal integrada, entornos virtuales, ejecución y depuración, y un flujo básico con Git/GitHub.

---

## 0) Checklist rápido (lo que debe quedar funcionando hoy)

Al finalizar la clase deberías poder:

- Abrir una carpeta de proyecto en VS Code (**workspace**).
- Crear y activar un entorno virtual (`.venv`) y seleccionar el intérprete correcto.
- Ejecutar un script Python desde VS Code y desde la terminal integrada.
- Ejecutar código en JAVA
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

1. Descargar el instalador de python: https://www.python.org/downloads/
2. Descargar la versión standalone de python:
   
    <img width="530" height="155" alt="image" src="https://github.com/user-attachments/assets/73833019-5c22-4ae0-b75d-f47fd7b59c58" />
    
3. Al instalar marcar la opción **Add python.exe to path**:

<img width="972" height="601" alt="image" src="https://github.com/user-attachments/assets/983bf922-697f-498c-944e-a6f415429650" />

4. Next a todo lo siguiente
5. Instalar extensiones de python:

 <img width="742" height="921" alt="image" src="https://github.com/user-attachments/assets/dffd3357-1d97-4d33-ac99-e1d7d3d6ab41" /> 
 
- Ejecutar scripts
  1. Creamos una carpeta de proyectos, por ejemplo: tests_ptyhon
  2. La abro:
     
     <img width="323" height="240" alt="image" src="https://github.com/user-attachments/assets/ea07d14f-f3e0-4dc4-bfe6-50655c697b18" />

3. Selecciono la carpeta:

<img width="802" height="396" alt="image" src="https://github.com/user-attachments/assets/a9e2bb8a-00fb-45fe-a178-1cfee52fe32f" />


4. Crear un test.py

<img width="332" height="109" alt="image" src="https://github.com/user-attachments/assets/e7af39e1-9462-4360-8f35-bf4e704c5834" />


5. Corremo nuestro primer codigo en python:

   <img width="1053" height="679" alt="image" src="https://github.com/user-attachments/assets/98ffb5ee-3297-47a6-8642-ce7336fe3299" />


### 3.2 Elementos básicos en la creación de un proyecto (flujo completo)

Los elementos que debe contener un proyecto:

```bash
mi_proyecto/
│
├── venv/
├── src/
│   ├── main.py
│   └── utils.py
├── requirements.txt
├── README.md
└── .gitignore
```

---

---

## 4) Ejemplo de mini proyecto en python paso a paso:

### Definimos la estructura del proyecto: 

```bash
mini_proyecto/
│
├── venv/
├── src/
│   └── mini_proyecto/
│       ├── __init__.py
│       ├── main.py
│       ├── models/
│       │   ├── __init__.py
│       │   └── usuario.py
│       ├── services/
│       │   ├── __init__.py
│       │   └── usuario_service.py
│       └── utils/
│           ├── __init__.py
│           └── calculos.py
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

**Paso 1**: Crear la carpeta mini_proyecto

---
**Paso 2**: Crear entorno virtual

Un entorno virtual es:

Una copia aislada del intérprete de Python + su propio espacio para instalar librerías.

Es como crear un “mini Python independiente” dentro de tu proyecto. Esto se hace con el siguiente comando:

```bash
python -m venv venv
```
Luego hay que activarlo: 
```bash
venv\Scripts\activate
```

---
**Cómo verificar que está activo el ambiente**

En la terminal debería aparecer:
```bash
(venv) C:\ruta\mi_proyecto>
```
También puedes escribir:
```bash
where python
```
Debe apuntar a:
```bash
...mi_proyecto\venv\Scripts\python.exe
```
---
**IMPORTANTE: qué hacer si no te permite activar el ambiente:**
1. En la consola de PowerShell ejecuta el siguiente comando:

   ```bash
      Get-ExecutionPolicy
   ```
   
    Si dice:
    ```bash
    Restricted
    ```
    Ese es el problema.

   **Cambiar política solo para tu usuario**, ejecuta en el powershell este comando:
   ```bash
   Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
   ```
   Permite:

✔ Scripts creados en tu máquina

✔ Scripts firmados digitalmente

---
**Cerrar y reabrir PowerShell**

Muy importante.
---
**Intentar activar nuevamente**
```bash
venv\Scripts\activate
```
Ahora debería funcionar.

---
**Breve explicación de los ambientes (enviroments) en python:** 

Es importante el uso de ambientes porque permite cargar diferentes estructuras de configuración dependiendo de las necesidades de los proyectos.

Para activar el ambiente luego de cargar el proyecto debemos hacer lo siguiente en consola: 

```bash
venv\Scripts\activate
```
Eso activa el ambiente de ese proyecto:

```bash
1. Se modifica temporalmente el PATH

2. El python que usas pasa a ser el del venv

3. El pip que usas instala dentro del venv

4. La terminal muestra (venv) al inicio
```

Si no lo activas: 

1. python será el global

2. pip install instalará globalmente

3. **Tu proyecto puede romperse**
   
---
**Pasos para desactivar y activar otro ambiente de otro proyecto:**
```bash
deactivate
cd ../ProyectoB
python -m venv venv
venv\Scripts\activate
```
---
**Paso 3:** Crear estructura src

Dentro de proyecto crear la carpeta:
```bash
src/
```
Y vamos a ir creando la estructura de los archivos dentro src/

Agregar archivo vacío:
```bash
__init__.py
```
(Esto convierte la carpeta en paquete Python)

---
**models/usuario.py**
Aquí colocaremos el siguiente código: 
```bash
class Usuario:
    def __init__(self, nombre: str, edad: int):
        self.nombre = nombre
        self.edad = edad

    def __str__(self):
        return f"{self.nombre} ({self.edad} años)"
```

**¿Qué es esto?**

Un modelo.

Representa una entidad del sistema.

---
**services/usuario_service.py**
```bash
from typing import List
from mini_proyecto.models.usuario import Usuario
from mini_proyecto.utils.calculos import promedio


class UsuarioService:
    def __init__(self):
        self.usuarios: List[Usuario] = []

    def agregar_usuario(self, nombre: str, edad: int):
        usuario = Usuario(nombre, edad)
        self.usuarios.append(usuario)

    def listar_usuarios(self):
        return self.usuarios

    def edad_promedio(self):
        edades = [u.edad for u in self.usuarios]
        return promedio(edades)
```
**¿Qué hace esta capa?**

Es la lógica del negocio.

No imprime.

No interactúa con usuario.

Solo maneja datos.

---
**utils/calculos.py**
```bash
def promedio(lista):
    if not lista:
        return 0
    return sum(lista) / len(lista)
```
**¿Por qué separar utils?**

Porque el cálculo podría reutilizarse en otro lugar.

---
**main.py**
```bash
from mini_proyecto.services.usuario_service import UsuarioService

def main():
    servicio = UsuarioService()

    servicio.agregar_usuario("Ana", 20)
    servicio.agregar_usuario("Luis", 25)
    servicio.agregar_usuario("Carla", 30)

    print("Usuarios registrados:")
    for usuario in servicio.listar_usuarios():
        print(usuario)

    print("\nEdad promedio:")
    print(servicio.edad_promedio())

if __name__ == "__main__":
    main()
```
---
**Ejecutar el proyecto**

Desde la raíz:
```bash
python -m mini_proyecto.main
```
Esto es importante cuando usas estructura con src.

---
**Modelo mental de la arquitectura**
```bash
main.py
   ↓
UsuarioService (lógica)
   ↓
Usuario (modelo)
   ↓
calculos.py (utilidad)
```
---
**¿Por qué esta estructura es buena?**

✔ Código modular

✔ Fácil de escalar

✔ Fácil de testear

✔ Fácil de mantener

✔ Profesional

---
**Cómo escalar este proyecto**

Podrías agregar:
```bash
database/
tests/
config/
api/
```
Y la arquitectura se mantiene ordenada.

---

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

