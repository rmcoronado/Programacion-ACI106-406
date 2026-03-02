# Clase 2 — Configuración de VS Code para Python, Java y Git (opcional) + Terminal

> **Objetivo de la clase:** dejar tu entorno listo para programar en **Python** y **Java** de forma cómoda y profesional: editor configurado, extensiones mínimas, terminal integrada, entornos virtuales, ejecución y depuración, y un flujo básico con Git/GitHub.

---

> Nota: Este apunte usa bloques plegables (HTML `details`). En la vista previa de VS Code y en GitHub puedes desplegar/plegar secciones para navegar más rápido.

## Índice

0) [Checklist rápido (lo que debe quedar funcionando hoy)](#sec-0)  
1) [Instalar Visual Studio Code](#sec-1)  
1.1) [Descarga (Windows / macOS / Linux)](#sec-1-1)  
1.2) [Instalación por sistema operativo (resumen práctico)](#sec-1-2)  
2) [Tour: “Get started” y lo mínimo del interfaz](#sec-2)  
2.1) [Lo esencial del UI](#sec-2-1)  
3) [Python en VS Code (setup + ejecución + edición)](#sec-3)  
3.1) [Quick Start (visión general)](#sec-3-1)  
3.2) [Flujo mínimo: crear proyecto, ejecutar y elegir intérprete](#sec-3-2)  
3.3) [Elementos básicos en la creación de un proyecto (flujo completo)](#sec-3-3)  
4) [Mini proyecto en Python paso a paso](#sec-4)  
4.1) [Estructura del proyecto](#sec-4-1)  
4.2) [Paso 1: crear la carpeta `mini_proyecto`](#sec-4-2)  
4.3) [Paso 2: crear y activar entorno virtual](#sec-4-3)  
4.4) [Paso 3: crear estructura `src/` y paquetes](#sec-4-4)  
4.5) [Ejecutar el proyecto](#sec-4-5)  
4.6) [Archivos `.pyc` y `__pycache__`](#sec-4-6)  
4.7) [Modelo mental de la arquitectura](#sec-4-7)  
4.8) [Cómo escalar este proyecto](#sec-4-8)  
5) [`requirements.txt` (dependencias)](#sec-5)  
6) [`.gitignore` (archivos que NO se suben)](#sec-6)  
7) [REPL de Python](#sec-7)  
8) [Git en VS Code](#sec-8)  
9) [Instalación de Java en VS Code + Hola Mundo](#sec-9)  
10) [Actividades de cierre (práctica guiada)](#sec-10)  
11) [Errores típicos y soluciones rápidas](#sec-11)


---

<details open>
<summary><a id="sec-0"></a><strong>0) Checklist rápido (lo que debe quedar funcionando hoy)</strong></summary>

Al finalizar la clase deberías poder:

- Abrir una carpeta de proyecto en VS Code (**workspace**).
- Crear y activar un entorno virtual (`venv`) y seleccionar el intérprete correcto.
- Ejecutar un script Python desde VS Code y desde la terminal integrada.
- Ejecutar código en Java.
- Hacer commit con Git y sincronizar con un repositorio remoto (GitHub).

---

</details>

<details>
<summary><a id="sec-1"></a><strong>1) Instalar Visual Studio Code</strong></summary>

<details>
<summary><a id="sec-1-1"></a><strong>1.1) Descarga (Windows / macOS / Linux)</strong></summary>

- Página oficial de descarga: https://code.visualstudio.com/download

**Recomendación general:** usa instaladores oficiales (User Installer en Windows, `.dmg` en macOS, `.deb`/`.rpm`/Snap en Linux) para tener actualizaciones y rutas por defecto bien configuradas.

</details>

<details>
<summary><a id="sec-1-2"></a><strong>1.2) Instalación por sistema operativo (resumen práctico)</strong></summary>

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

</details>

</details>

<details>
<summary><a id="sec-2"></a><strong>2) Tour: “Get started” y lo mínimo del interfaz</strong></summary>

Tutorial oficial (recomendado): https://code.visualstudio.com/docs/getstarted/getting-started

<details>
<summary><a id="sec-2-1"></a><strong>2.1) Lo esencial del UI</strong></summary>

- **Activity Bar**: Explorer, Search, Source Control, Run and Debug, Extensions.
- **Explorer**: archivos/carpetas del proyecto.
- **Editor**: donde codificas.
- **Panel**: Terminal / Output / Debug Console / Problems.
- **Command Palette** (el “centro de mando”):
  - Atajo: `Ctrl+Shift+P` (Win/Linux) o `Cmd+Shift+P` (macOS).

Referencia: https://code.visualstudio.com/docs/getstarted/tips-and-tricks

---

</details>

</details>

<details>
<summary><a id="sec-3"></a><strong>3) Python en VS Code (setup + ejecución + edición)</strong></summary>

<details>
<summary><a id="sec-3-1"></a><strong>3.1) Quick Start (visión general)</strong></summary>

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

</details>

<details>
<summary><a id="sec-3-2"></a><strong>3.2) Flujo mínimo: crear proyecto, ejecutar y elegir intérprete</strong></summary>

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

</details>

<details>
<summary><a id="sec-3-3"></a><strong>3.3) Elementos básicos en la creación de un proyecto (flujo completo)</strong></summary>

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

</details>

</details>

<details>
<summary><a id="sec-4"></a><strong>4) Mini proyecto en Python paso a paso</strong></summary>

<details>
<summary><a id="sec-4-1"></a><strong>4.1) Estructura del proyecto</strong></summary>

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

</details>

<details>
<summary><a id="sec-4-2"></a><strong>4.2) Paso 1: crear la carpeta `mini_proyecto`</strong></summary>

Crear la carpeta del proyecto y abrirla en VS Code.

</details>

<details>
<summary><a id="sec-4-3"></a><strong>4.3) Paso 2: crear y activar entorno virtual</strong></summary>

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

</details>

<details>
<summary><a id="sec-4-4"></a><strong>4.4) Paso 3: crear estructura `src/` y paquetes</strong></summary>

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

</details>

<details>
<summary><a id="sec-4-5"></a><strong>4.5) Ejecutar el proyecto</strong></summary>

Desde la raíz `...\Clases_pregrado\mini_proyecto>`:

```powershell
$env:PYTHONPATH="src"
```

Luego:

```bash
python -m mini_proyecto.main
```

Esto es importante cuando usas estructura con `src/`.

</details>

<details>
<summary><a id="sec-4-6"></a><strong>4.6) Archivos `.pyc` y `__pycache__`</strong></summary>

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

</details>

<details>
<summary><a id="sec-4-7"></a><strong>4.7) Modelo mental de la arquitectura</strong></summary>

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

</details>

<details>
<summary><a id="sec-4-8"></a><strong>4.8) Cómo escalar este proyecto</strong></summary>

Podrías agregar:

```text
database/
tests/
config/
api/
```

Y la arquitectura se mantiene ordenada.

---

</details>

</details>

<details>
<summary><a id="sec-5"></a><strong>5) `requirements.txt` (dependencias)</strong></summary>

Es el archivo que guarda las dependencias del proyecto. Traducción simple:

“Estas son las librerías que mi proyecto necesita para funcionar”.

Si otra persona clona tu proyecto, solo debe hacer:

```bash
pip install -r requirements.txt
```

Y tendrá exactamente las mismas versiones.

<details>
<summary><strong>Paso a paso — crear `requirements.txt`</strong></summary>

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

</details>

</details>

<details>
<summary><a id="sec-6"></a><strong>6) `.gitignore` (archivos que NO se suben)</strong></summary>

`.gitignore` le dice a Git qué archivos NO debe subir. Traducción simple:

“Estos archivos son locales. No deben ir al repositorio”.

<details>
<summary><strong>¿Qué nunca debe subirse?</strong></summary>

1. `venv/`
2. Archivos temporales
3. Archivos compilados
4. Configuraciones locales

</details>

<details>
<summary><strong>Paso a paso — crear `.gitignore` en VS Code</strong></summary>

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

</details>

</details>

<details>
<summary><a id="sec-7"></a><strong>7) REPL de Python</strong></summary>

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

</details>

<details>
<summary><a id="sec-8"></a><strong>8) Git en VS Code</strong></summary>

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

</details>

<details>
<summary><a id="sec-9"></a><strong>9) Instalación de Java en VS Code + Hola Mundo</strong></summary>

Para instalar Java en VS Code, sigue estos pasos:

<details>
<summary><strong>Paso 1: instalar extensiones necesarias de Java</strong></summary>

Abrir VS Code y su marketplace:

<img width="831" height="369" alt="image" src="https://github.com/user-attachments/assets/c9f66193-762e-445b-a432-90a1df4740c2" />

</details>

<details>
<summary><strong>Paso 2: instalar JDK desde Welcome</strong></summary>

Ir a Help → Welcome → opción de instalar JDK:

<img width="896" height="452" alt="image" src="https://github.com/user-attachments/assets/9a36b904-5c62-476b-b475-68d7be44be62" />

</details>

<details>
<summary><strong>Paso 3: seguir pasos para instalar el JDK</strong></summary>

<img width="921" height="429" alt="image" src="https://github.com/user-attachments/assets/93d97ac8-690e-46b8-93f1-27fcf710eab6" />

</details>

<details>
<summary><strong>Hola Mundo en Java</strong></summary>

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

</details>

</details>

<details>
<summary><a id="sec-10"></a><strong>10) Actividades de cierre (práctica guiada)</strong></summary>

Usa esta pauta para cerrar la clase con una práctica corta. La idea es que al final puedas decir: “mi entorno quedó listo y sé ejecutar en Python/Java”.

<details>
<summary><strong>A) VS Code listo (2–3 min)</strong></summary>

- Abre una carpeta de trabajo en VS Code (File → Open Folder).
- Verifica que ves el **Explorer** a la izquierda y el **Panel** abajo (Terminal/Problems).
- Abre la **Command Palette** (`Ctrl+Shift+P` / `Cmd+Shift+P`) y confirma que puedes buscar comandos.

</details>

<details>
<summary><strong>B) Python: ejecutar un archivo (2–3 min)</strong></summary>

- Crea un archivo `test.py` y agrega un `print("Hola")`.
- Ejecútalo desde VS Code (botón Run) y también desde la terminal:

```bash
python test.py
```

</details>

<details>
<summary><strong>C) Entorno virtual (3–4 min)</strong></summary>

En la raíz del proyecto:

```bash
python -m venv venv
venv\Scripts\activate
```

Chequeo rápido:

```bash
where python
```

Debiera apuntar a `...\venv\Scripts\python.exe`.

</details>

<details>
<summary><strong>D) Mini proyecto con `src/` (4–5 min)</strong></summary>

Desde la raíz del proyecto:

1) Define el `PYTHONPATH`:

```powershell
$env:PYTHONPATH="src"
```

2) Ejecuta con módulo:

```bash
python -m mini_proyecto.main
```

</details>

<details>
<summary><strong>E) Git mínimo (2–3 min)</strong></summary>

- Crea tu `.gitignore` con `venv/`, `__pycache__/` y `*.pyc`.
- Inicializa el repo y deja listo tu primer commit (si aparece error de identidad, usa la configuración del punto 8).

</details>

<details>
<summary><strong>F) Java (opcional, 3–5 min)</strong></summary>

- Crea `holamundo.java` y ejecútalo desde VS Code.
- Recuerda: el archivo y la clase pública deben llamarse igual (`holamundo.java` → `public class holamundo`).

</details>

</details>


<details>
<summary><a id="sec-11"></a><strong>11) Errores típicos y soluciones rápidas</strong></summary>

<details>
<summary><strong>“`code` no se reconoce como comando”</strong></summary>

- Windows: reinicia la terminal después de instalar VS Code (para que tome el PATH).
- macOS: en VS Code ejecuta **Shell Command: Install 'code' command in PATH** desde la Command Palette.

</details>

<details>
<summary><strong>“`python` no se reconoce como comando” (Windows)</strong></summary>

- Reinstala Python y marca **Add python.exe to path** durante la instalación.
- Cierra y abre la terminal para que tome los cambios.

</details>

<details>
<summary><strong>El entorno virtual “no se activa” en PowerShell</strong></summary>

1) Revisa la política:

```powershell
Get-ExecutionPolicy
```

2) Si aparece `Restricted`, cambia para tu usuario:

```powershell
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

3) Cierra y abre PowerShell, luego:

```bash
venv\Scripts\activate
```

</details>

<details>
<summary><strong>Instalé librerías, pero el proyecto “no las ve”</strong></summary>

- Asegúrate de que el entorno virtual esté activo (deberías ver `(venv)` al inicio de la línea).
- Verifica con:

```bash
where python
```

</details>

<details>
<summary><strong>“`ModuleNotFoundError: No module named 'mini_proyecto'`”</strong></summary>

En proyectos con `src/`, usa estas dos ideas (las dos están en esta guía):

1) Asegura el `PYTHONPATH`:

```powershell
$env:PYTHONPATH="src"
```

2) Ejecuta como módulo desde la raíz:

```bash
python -m mini_proyecto.main
```

</details>

<details>
<summary><strong>Git no me deja hacer commit (identidad)</strong></summary>

Configura nombre y correo una sola vez:

```bash
git config --global user.name "Tu Nombre Completo"
git config --global user.email "tu_email@gmail.com"
git config --list
```

</details>

<details>
<summary><strong>Java: “la clase pública no coincide con el archivo”</strong></summary>

- Si tu archivo se llama `holamundo.java`, entonces debe ser:

```java
public class holamundo {
    public static void main(String[] args) {
        System.out.println("Hola Mundo");
    }
}
```

</details>

</details>

