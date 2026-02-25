# Clase 2 — Configuración de VS Code para Python, Java y Git (opcional) + Terminal

> **Objetivo de la clase:** dejar tu entorno listo para programar en **Python** y **Java** de forma cómoda y profesional: editor configurado, extensiones mínimas, terminal integrada, entornos virtuales, ejecución y depuración, y un flujo básico con Git/GitHub.

---

## Índice

- [0) Checklist rápido (lo que debe quedar funcionando hoy)](#0-checklist-rápido-lo-que-debe-quedar-funcionando-hoy)
- [1) Instalar Visual Studio Code](#1-instalar-visual-studio-code)
  - [1.1 Descarga (Windows / macOS / Linux)](#11-descarga-windows--macos--linux)
  - [1.2 Instalación por sistema operativo](#12-instalación-por-sistema-operativo-resumen-práctico)
- [2) Tour: “Get started” y lo mínimo del interfaz](#2-tour-get-started-y-lo-mínimo-del-interfaz)
  - [2.1 Lo esencial del UI](#21-lo-esencial-del-ui)
- [3) Python en VS Code (setup + ejecución + edición)](#3-python-en-vs-code-setup--ejecución--edición)
  - [3.1 Quick Start (visión general)](#31-quick-start-visión-general)
  - [3.2 Flujo mínimo: crear proyecto, ejecutar y elegir intérprete](#32-flujo-mínimo-crear-proyecto-ejecutar-y-elegir-intérprete)
  - [3.3 Elementos básicos en la creación de un proyecto](#33-elementos-básicos-en-la-creación-de-un-proyecto-flujo-completo)
- [4) Mini proyecto en Python paso a paso](#4-mini-proyecto-en-python-paso-a-paso)
  - [4.1 Estructura del proyecto](#41-estructura-del-proyecto)
  - [4.2 Paso 1: crear la carpeta](#42-paso-1-crear-la-carpeta-mini_proyecto)
  - [4.3 Paso 2: crear y activar entorno virtual](#43-paso-2-crear-y-activar-entorno-virtual)
  - [4.4 Paso 3: crear estructura `src/` y paquetes](#44-paso-3-crear-estructura-src-y-paquetes)
  - [4.5 Ejecutar el proyecto](#45-ejecutar-el-proyecto)
  - [4.6 Archivos `.pyc` y `__pycache__`](#46-archivos-pyc-y-__pycache__)
  - [4.7 Modelo mental de la arquitectura](#47-modelo-mental-de-la-arquitectura)
  - [4.8 Escalar el proyecto](#48-cómo-escalar-este-proyecto)
- [5) `requirements.txt` (dependencias)](#5-requirementstxt-dependencias)
- [6) `.gitignore` (archivos que NO se suben)](#6-gitignore-archivos-que-no-se-suben)
- [7) REPL de Python](#7-repl-de-python)
- [8) Git en VS Code](#8-git-en-vs-code)
- [9) Instalación de Java en VS Code + Hola Mundo](#9-instalación-de-java-en-vs-code--hola-mundo)

---

## 0) Checklist rápido (lo que debe quedar funcionando hoy)

Al finalizar la clase deberías poder:

- Abrir una carpeta de proyecto en VS Code (**workspace**).
- Crear y activar un entorno virtual (`venv`) y seleccionar el intérprete correcto.
- Ejecutar un script Python desde VS Code y desde la terminal integrada.
- Ejecutar código en Java.
- Hacer commit con Git y sincronizar con un repositorio remoto (GitHub).

---

## 1) Instalar Visual Studio Code

### 1.1 Descarga (Windows / macOS / Linux)

- Página oficial de descarga: https://code.visualstudio.com/download

**Recomendación general:** usa instaladores oficiales (User Installer en Windows, `.dmg` en macOS, `.deb`/`.rpm`/Snap en Linux) para tener actualizaciones y rutas por defecto bien configuradas.

### 1.2 Instalación por sistema operativo (resumen práctico)

Guías oficiales:

- Windows: https://code.visualstudio.com/docs/setup/windows
- macOS: https://code.visualstudio.com/docs/setup/mac
- Linux: https://code.visualstudio.com/docs/setup/linux

#### Windows (recomendado: User Installer)

1. Descarga el instalador para Windows.
2. Ejecuta `VSCodeUserSetup-<version>.exe`.
3. Después de instalar, reinicia la terminal si quieres usar el comando `code`.

**Tip importante:** el instalador agrega VS Code al `%PATH%` para poder usar `code .` (abre VS Code en esa carpeta).

Para verificar, abre Git Bash y ejecuta:

```bash
code
```

Esto debería abrir VS Code.

#### macOS

1. Descarga el `.dmg`.
2. Arrastra `Visual Studio Code.app` a **Applications**.
3. Para habilitar `code` en la terminal:
   - Abre VS Code → Command Palette → ejecuta: **Shell Command: Install 'code' command in PATH**.

Referencia: https://code.visualstudio.com/docs/setup/mac

#### Linux (varía según distro)

- Debian/Ubuntu (`.deb`):
  ```bash
  sudo apt install ./<file>.deb
  ```
- Snap:
  ```bash
  sudo snap install --classic code
  ```
- RPM (Fedora/RHEL/SUSE):
  ```bash
  sudo dnf install <file>.rpm
  ```

Referencia: https://code.visualstudio.com/docs/setup/linux

---

## 2) Tour: “Get started” y lo mínimo del interfaz

Tutorial oficial (recomendado): https://code.visualstudio.com/docs/getstarted/getting-started

### 2.1 Lo esencial del UI

- **Activity Bar**: Explorer, Search, Source Control, Run and Debug, Extensions.
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

Lo que te interesa hoy:

1) Instalar Python (en el sistema)

1. Descargar el instalador: https://www.python.org/downloads/
2. Descargar la versión standalone de Python:

<img width="530" height="155" alt="image" src="https://github.com/user-attachments/assets/73833019-5c22-4ae0-b75d-f47fd7b59c58" />

3. Al instalar, marcar la opción **Add python.exe to path**:

<img width="972" height="601" alt="image" src="https://github.com/user-attachments/assets/983bf922-697f-498c-944e-a6f415429650" />

4. Next a todo lo siguiente.

2) Instalar extensiones de Python en VS Code:

<img width="742" height="921" alt="image" src="https://github.com/user-attachments/assets/dffd3357-1d97-4d33-ac99-e1d7d3d6ab41" />

### 3.2 Flujo mínimo: crear proyecto, ejecutar y elegir intérprete

**Ejecutar scripts**

1. Crea una carpeta de proyectos, por ejemplo: `tests_python`.
2. Ábrela en VS Code:

<img width="323" height="240" alt="image" src="https://github.com/user-attachments/assets/ea07d14f-f3e0-4dc4-bfe6-50655c697b18" />

3. Selecciona la carpeta:

<img width="802" height="396" alt="image" src="https://github.com/user-attachments/assets/a9e2bb8a-00fb-45fe-a178-1cfee52fe32f" />

4. Crea `test.py`:

<img width="332" height="109" alt="image" src="https://github.com/user-attachments/assets/e7af39e1-9462-4360-8f35-bf4e704c5834" />

5. Corre tu primer código en Python:

<img width="1053" height="679" alt="image" src="https://github.com/user-attachments/assets/98ffb5ee-3297-47a6-8642-ce7336fe3299" />

### 3.3 Elementos básicos en la creación de un proyecto (flujo completo)

Estructura típica mínima:

```text
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

## 4) Mini proyecto en Python paso a paso

### 4.1 Estructura del proyecto

```text
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

### 4.2 Paso 1: crear la carpeta `mini_proyecto`

Crear la carpeta del proyecto y abrirla en VS Code.

### 4.3 Paso 2: crear y activar entorno virtual

Un entorno virtual es una copia aislada del intérprete de Python + su propio espacio para instalar librerías. Es como crear un “mini Python independiente” dentro de tu proyecto.

Crear:

```bash
python -m venv venv
```

Activar:

```bash
venv\Scripts\activate
```

#### Cómo verificar que está activo el ambiente

En la terminal debería aparecer:

```text
(venv) C:\ruta\mi_proyecto>
```

También puedes escribir:

```bash
where python
```

Debe apuntar a:

```text
...mi_proyecto\venv\Scripts\python.exe
```

#### Importante: qué hacer si no te permite activar el ambiente (PowerShell)

1. En PowerShell ejecuta:

```powershell
Get-ExecutionPolicy
```

Si dice:

```text
Restricted
```

Ese es el problema.

2. Cambiar política solo para tu usuario (en PowerShell):

```powershell
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

Esto permite:

- Scripts creados en tu máquina
- Scripts firmados digitalmente

3. Cierra y reabre PowerShell.
4. Intenta activar nuevamente:

```bash
venv\Scripts\activate
```

#### Desactivar y activar otro ambiente (otro proyecto)

```bash
deactivate
cd ../ProyectoB
python -m venv venv
venv\Scripts\activate
```

### 4.4 Paso 3: crear estructura `src/` y paquetes

Dentro del proyecto crea la carpeta:

```text
src/
```

Dentro de `src/mini_proyecto/` agrega un archivo vacío:

```text
__init__.py
```

(Esto convierte la carpeta en paquete Python)

#### `models/usuario.py`

```python
class Usuario:
    def __init__(self, nombre: str, edad: int):
        self.nombre = nombre
        self.edad = edad

    def __str__(self):
        return f"{self.nombre} ({self.edad} años)"
```

Esto es un modelo: representa una entidad del sistema.

#### `services/usuario_service.py`

```python
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

Esta capa es la lógica del negocio: no imprime ni interactúa con el usuario; solo maneja datos.

#### `utils/calculos.py`

```python
def promedio(lista):
    if not lista:
        return 0
    return sum(lista) / len(lista)
```

¿Por qué separar `utils`? Porque el cálculo podría reutilizarse en otro lugar.

#### `main.py`

```python
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

### 4.5 Ejecutar el proyecto

Desde la raíz `...\Clases_pregrado\mini_proyecto>`:

```powershell
$env:PYTHONPATH="src"
```

Luego:

```bash
python -m mini_proyecto.main
```

Esto es importante cuando usas estructura con `src/`.

### 4.6 Archivos `.pyc` y `__pycache__`

`.pyc` significa “Python Compiled”: son versiones compiladas de tus archivos `.py`.

Flujo interno:

```text
Archivo .py
   ↓
Compilación
   ↓
Bytecode (.pyc)
   ↓
Python Virtual Machine
   ↓
Ejecución
```

¿Debo subir los `.pyc` a GitHub? No. Por eso en `.gitignore` ponemos:

```text
__pycache__/
*.pyc
```

### 4.7 Modelo mental de la arquitectura

```text
main.py
   ↓
UsuarioService (lógica)
   ↓
Usuario (modelo)
   ↓
calculos.py (utilidad)
```

¿Por qué esta estructura es buena?

- Código modular
- Fácil de escalar
- Fácil de testear
- Fácil de mantener
- Profesional

### 4.8 Cómo escalar este proyecto

Podrías agregar:

```text
database/
tests/
config/
api/
```

Y la arquitectura se mantiene ordenada.

---

## 5) `requirements.txt` (dependencias)

Es el archivo que guarda las dependencias del proyecto. Traducción simple:

“Estas son las librerías que mi proyecto necesita para funcionar”.

Si otra persona clona tu proyecto, solo debe hacer:

```bash
pip install -r requirements.txt
```

Y tendrá exactamente las mismas versiones.

### Paso a paso — crear `requirements.txt`

1) Activar entorno virtual:

```bash
venv\Scripts\activate
```

2) Instalar dependencias (ejemplo):

```bash
pip install requests
```

3) Generar el archivo automáticamente:

```bash
pip freeze > requirements.txt
```

Ejemplo de contenido:

```text
requests==2.31.0
certifi==2024.2.2
charset-normalizer==3.3.2
```

¿Por qué no escribirlo a mano? Porque puedes olvidar versiones o dependencias internas. `pip freeze` garantiza reproducibilidad.

---

## 6) `.gitignore` (archivos que NO se suben)

`.gitignore` le dice a Git qué archivos NO debe subir. Traducción simple:

“Estos archivos son locales. No deben ir al repositorio”.

### ¿Qué nunca debe subirse?

1. `venv/`
2. Archivos temporales
3. Archivos compilados
4. Configuraciones locales

### Paso a paso — crear `.gitignore` en VS Code

1) Crear archivo en la raíz del proyecto (con punto al inicio):

```text
.gitignore
```

2) Agregar contenido básico para Python:

```gitignore
# Entorno virtual
venv/

# Archivos compilados
__pycache__/
*.pyc

# Configuración VS Code
.vscode/

# Archivos del sistema
.DS_Store
Thumbs.db
```

---

## 7) REPL de Python

REPL significa:

Read → Eval → Print → Loop

Ejemplo simple:

Si abres una terminal y escribes:

```bash
python
```

Verás algo así:

```text
>>>
```

Ese `>>>` indica que estás dentro del REPL.

Ahora escribes:

```python
2 + 2
```

Para salir:

```python
exit()
```

---

## 8) Git en VS Code

1) Inicializar el repositorio:

<img width="540" height="639" alt="image" src="https://github.com/user-attachments/assets/f262c490-aa46-467b-ac49-1d68980e3b23" />

2) Al hacer commit puede dar error por no haber configurado nombre y email. Para configurar:

```bash
git config --global user.name "Tu Nombre Completo"
git config --global user.email "tu_email@gmail.com"
```

3) Testea que todo quedó bien:

```bash
git config --list
```

4) Luego, eso te da la posibilidad de hacer tu primer commit.

---

## 9) Instalación de Java en VS Code + Hola Mundo

Para instalar Java en VS Code, sigue estos pasos:

### Paso 1: instalar extensiones necesarias de Java

Abrir VS Code y su marketplace:

<img width="831" height="369" alt="image" src="https://github.com/user-attachments/assets/c9f66193-762e-445b-a432-90a1df4740c2" />

### Paso 2: instalar JDK desde Welcome

Ir a Help → Welcome → opción de instalar JDK:

<img width="896" height="452" alt="image" src="https://github.com/user-attachments/assets/9a36b904-5c62-476b-b475-68d7be44be62" />

### Paso 3: seguir pasos para instalar el JDK

<img width="921" height="429" alt="image" src="https://github.com/user-attachments/assets/93d97ac8-690e-46b8-93f1-27fcf710eab6" />

### Hola Mundo en Java

Pasos:

1. Crear una carpeta, por ejemplo: `test_java`
2. Crear un archivo llamado `holamundo.java`
3. Autocompletando puedes llegar a diseñar tu primera clase (elemento fundamental en programación orientada a objetos, POO, que veremos más adelante):

```java
public class holamundo {
    public static void main(String[] args) {
        System.out.println("Hola Mundo");
    }    
}
```

Importante: la clase se tiene que llamar igual que el archivo: `holamundo.java` → `public class holamundo`.

Listo: ya tienes tu primer código en Java.
