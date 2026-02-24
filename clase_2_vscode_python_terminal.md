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

Desde la raíz **...\Clases_pregrado\mini_proyecto>**:
```bash
$env:PYTHONPATH="src"
```

```bash
python -m mini_proyecto.main
```
Esto es importante cuando usas estructura con src.

---
**¿Qué son los archivos .pyc?**

.pyc significa:

Python Compiled

Son versiones compiladas de tus archivos .py.

Python NO ejecuta directamente el texto del archivo.

Primero:

1️⃣ Lee el código .py

2️⃣ Lo compila a bytecode

3️⃣ Guarda ese bytecode en un archivo .pyc

4️⃣ Luego ejecuta ese bytecode

---
**¿Qué es bytecode?**

No es código máquina (como C).
Es un código intermedio que ejecuta la máquina virtual de Python.

Flujo interno:
```bash
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
---
**¿Debo subir los .pyc a GitHub?**

NO.

Por eso en .gitignore ponemos:
```bash
__pycache__/
*.pyc
```
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

----
**Paso 4: ¿Qué es requirements.txt y por qué es obligatorio?**

Es el archivo que guarda las dependencias del proyecto.

Traducción simple:

"Estas son las librerías que mi proyecto necesita para funcionar"

Si otra persona clona tu proyecto, solo debe hacer:
```bash
pip install -r requirements.txt
```
Y tendrá exactamente las mismas versiones.

---
**PASO A PASO — Crear requirements.txt**

Paso 1 — Activar entorno virtual
```bash
venv\Scripts\activate
```
Paso 2 — Instalar dependencias

Ejemplo:
```bash
pip install requests
```
Paso 3 — Generar el archivo automáticamente

pip freeze > requirements.txt
```bash
```
Esto crea el archivo en la raíz del proyecto.

---
**¿Qué contiene?**

Ejemplo:
```bash
requests==2.31.0
certifi==2024.2.2
charset-normalizer==3.3.2
```
Incluye dependencias internas también.

---
**¿Por qué no escribirlo a mano?**

Porque puedes olvidar versiones o dependencias internas.

pip freeze garantiza reproducibilidad.

---

**Paso 5:  ¿Qué es .gitignore y por qué es CRÍTICO?**

.gitignore le dice a Git qué archivos NO debe subir.

Traducción simple:

"Estos archivos son locales. No deben ir al repositorio."

---
**¿Qué nunca debe subirse?**
1. venv/

2. Archivos temporales

3. Archivos compilados

4. Configuraciones locales

---
**PASO A PASO — Crear .gitignore en VS Code**

Paso 1 — Crear archivo

En VS Code:

1. Click derecho en la raíz del proyecto

2. "New File"

3. Escribir:
```bash
.gitignore
```
(Con punto al inicio)

---
**Paso 2 — Agregar contenido básico para Python**
```bash
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
Guardar.

