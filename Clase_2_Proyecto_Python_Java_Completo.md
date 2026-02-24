# 🚀 Clase 2 --- Crear tu Primer Proyecto Profesional (Python y Java) desde CERO

Esta guía es extremadamente detallada y pensada para estudiantes que
comienzan desde cero. Aquí no asumimos conocimientos previos.

=====================================================================
PARTE I --- PROYECTO PROFESIONAL EN PYTHON
=====================================================================

ETAPA 0 --- Objetivo Al finalizar tendrás: - Python instalado
correctamente - VS Code configurado - Entorno virtual funcionando -
Proyecto estructurado profesionalmente - Dependencias controladas -
Proyecto listo para Git

  -----------------------------
  ETAPA 1 --- Instalar Python
  -----------------------------

1.  Ir a https://www.python.org/downloads/
2.  Descargar la versión estable recomendada.
3.  Ejecutar el instalador.
4.  MUY IMPORTANTE: marcar "Add Python to PATH"
5.  Click en "Install Now"

  -----------------------------------
  ETAPA 2 --- Verificar instalación
  -----------------------------------

Abrir PowerShell y ejecutar:

python --version

Debe mostrar algo como: Python 3.12.x

Si no funciona, Python no está en el PATH.

  ------------------------------
  ETAPA 3 --- Instalar VS Code
  ------------------------------

Descargar desde: https://code.visualstudio.com/

Instalar normalmente.

Verificar en terminal:

code --version

  ----------------------------------------
  ETAPA 4 --- Crear carpeta del proyecto
  ----------------------------------------

mkdir mi_proyecto_python cd mi_proyecto_python code .

Ahora tienes un Workspace activo.

  -----------------------------------
  ETAPA 5 --- Crear entorno virtual
  -----------------------------------

python -m venv venv

Se crea la carpeta:

mi_proyecto_python/ venv/

  -------------------------------------
  ETAPA 6 --- Activar entorno virtual
  -------------------------------------

Windows: venv`\Scripts`{=tex}`\activate`{=tex}

Mac/Linux: source venv/bin/activate

Debe aparecer:

(venv) C:`\ruta`{=tex}`\mi`{=tex}\_proyecto_python\>

  ---------------------------------------
  ETAPA 7 --- Instalar extensión Python
  ---------------------------------------

En VS Code: Extensiones → Buscar "Python" → Instalar la oficial.

Luego: Ctrl + Shift + P Buscar: Python: Select Interpreter Elegir el del
venv.

  -------------------------------------------
  ETAPA 8 --- Crear estructura del proyecto
  -------------------------------------------

mi_proyecto_python/ │ ├── venv/ ├── main.py ├── requirements.txt └──
README.md

  -------------------------------------
  ETAPA 9 --- Escribir código inicial
  -------------------------------------

main.py:

def saludar(nombre): return f"Hola {nombre}, este es tu primer proyecto
profesional 🚀"

if **name** == "**main**": print(saludar("Estudiante"))

Ejecutar:

python main.py

  ---------------------------------
  ETAPA 10 --- Instalar librerías
  ---------------------------------

pip install numpy

Guardar dependencias:

pip freeze \> requirements.txt

  ------------------------------
  ETAPA 11 --- Inicializar Git
  ------------------------------

git init

Crear .gitignore:

venv/ **pycache**/

Luego:

git add . git commit -m "Initial Python project setup"

=====================================================================
PARTE II --- PROYECTO PROFESIONAL EN JAVA
=====================================================================

ETAPA 0 --- Objetivo - JDK instalado - Proyecto compilable - Estructura
organizada - Código ejecutable

  --------------------------
  ETAPA 1 --- Instalar JDK
  --------------------------

Descargar desde: https://www.oracle.com/java/technologies/downloads/

Verificar:

java -version javac -version

  ---------------------------------------
  ETAPA 2 --- Instalar extensiones Java
  ---------------------------------------

En VS Code instalar: Java Extension Pack (Microsoft)

  ------------------------------
  ETAPA 3 --- Crear estructura
  ------------------------------

mkdir mi_proyecto_java cd mi_proyecto_java mkdir src cd src

  -----------------------------------
  ETAPA 4 --- Crear clase principal
  -----------------------------------

Crear Main.java:

public class Main { public static void main(String\[\] args) {
System.out.println("Hola mundo profesional en Java 🚀"); } }

  ----------------------
  ETAPA 5 --- Compilar
  ----------------------

javac Main.java

Se genera Main.class

  ----------------------
  ETAPA 6 --- Ejecutar
  ----------------------

java Main

  -----------------------------
  ETAPA 7 --- Inicializar Git
  -----------------------------

cd .. git init git add . git commit -m "Initial Java project setup"

=====================================================================
FIN DE LA GUÍA
=====================================================================

Ahora comprendes el pipeline profesional completo: Instalar → Configurar
→ Crear estructura → Ejecutar → Versionar
