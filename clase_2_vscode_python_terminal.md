🚀 Clase 2 — Configuración Profesional de tu Entorno de Desarrollo🎯 Objetivo de la clase: Dejar tu computador listo para programar en Python y JAVA de forma cómoda y profesional. Configuraremos tu editor (VS Code), instalaremos extensiones mínimas, aprenderemos a usar la terminal integrada, gestionaremos entornos virtuales y daremos nuestros primeros pasos con Git y GitHub.📑 Índice de ContenidosEl Editor: Instalar Visual Studio CodeTour Rápido: Conociendo VS CodeEcosistema Python: Configuración y Ejecución3.1 Instalación y Extensiones3.2 Tu Primer Script3.3 Entornos Virtuales (¡Muy Importante!)Arquitectura de un Proyecto: Mini Proyecto Paso a Paso4.1 Estructura del Proyecto4.2 Construyendo el CódigoBuenas Prácticas: Dependencias e Ignorados5.1 El archivo requirements.txt5.2 El archivo .gitignoreCápsula Teórica: Bytecode y REPLControl de Versiones: Git en VS CodeEcosistema Java: Hola Mundo✅ Checklist Rápido (Lo que lograrás hoy)Al finalizar la clase, serás capaz de:[x] Abrir una carpeta de proyecto en VS Code (workspace).[x] Crear y activar un entorno virtual (.venv) seleccionando el intérprete correcto.[x] Ejecutar un script Python desde el editor y la terminal integrada.[x] Ejecutar tu primer código en JAVA.[x] Hacer un commit con Git para guardar el historial de tus cambios.1. El Editor: Instalar Visual Studio Code1.1 Descarga (Windows / macOS / Linux)📥 Página oficial: https://code.visualstudio.com/download💡 Recomendación general: Usa instaladores oficiales (User Installer en Windows, .dmg en macOS, .deb/.rpm/Snap en Linux) para tener actualizaciones y "buenas rutas" por defecto.1.2 Instalación por Sistema Operativo<details><summary><strong>🪟 Windows (Recomendado: <em>User Installer</em>)</strong></summary>Descarga el instalador para Windows.Ejecuta VSCodeUserSetup-<version>.exe.¡Siguiente a todo! Asegúrate de marcar las opciones para agregar al PATH.Después de instalar, reinicia la terminal.Tip importante: El instalador agrega VS Code a tus variables de entorno para poder usar el comando code . (esto abre VS Code directamente en la carpeta donde estás).Para verificarlo, abre Git Bash o tu terminal y escribe:code
¡Esto debería abrir automáticamente VS Code!</details><details>
<summary><strong>🍎 macOS</strong></summary>Descarga el .dmg.Arrastra Visual Studio Code.app a la carpeta de Aplicaciones.Para habilitar el comando code en la terminal:Abre VS Code.Presiona Cmd+Shift+P para abrir la Command Palette.Ejecuta: Shell Command: Install 'code' command in PATH.</details><details><summary><strong>🐧 Linux (varía según distro)</strong></summary>Debian/Ubuntu (.deb): sudo apt install ./<file>.debSnap: sudo snap install --classic codeRPM (Fedora/RHEL/SUSE): sudo dnf install <file>.rpm</details>2. Tour Rápido: Conociendo VS CodeAntes de programar, es crucial conocer nuestra herramienta de trabajo.🗂️ Activity Bar (Barra lateral izquierda): Iconos de Explorer (Tus archivos), Search (Buscar en el código), Source Control (Git), Run and Debug, y Extensions.📂 Explorer: Donde ves los archivos y carpetas de tu proyecto.📝 Editor: El espacio central donde escribes tu código.💻 Panel Inferior: Aquí viven la Terminal, el Output, Debug Console y los Problemas del código.🚀 Command Palette (El "centro de mando"):Atajo: Ctrl+Shift+P (Win/Linux) o Cmd+Shift+P (macOS). ¡Úsalo para ejecutar cualquier acción en el editor!3. Ecosistema Python: Configuración y Ejecución3.1 Instalación y ExtensionesDescarga el instalador desde la página oficial de Python.Busca la versión standalone correspondiente a tu sistema:<img width="530" height="155" alt="image" src="https://github.com/user-attachments/assets/73833019-5c22-4ae0-b75d-f47fd7b59c58" />⚠️ ¡PASO CRÍTICO EN WINDOWS! Al abrir el instalador, marca la casilla "Add python.exe to PATH" antes de darle a Install Now.<img width="972" height="601" alt="image" src="https://github.com/user-attachments/assets/983bf922-697f-498c-944e-a6f415429650" />Siguiente a todo.En VS Code, ve al panel de Extensiones e instala las oficiales de Python:<img width="742" height="921" alt="image" src="https://github.com/user-attachments/assets/dffd3357-1d97-4d33-ac99-e1d7d3d6ab41" />3.2 Tu Primer ScriptCrea una carpeta para tus proyectos (ej: tests_python).Ábrela en VS Code desde File > Open Folder:<img width="323" height="240" alt="image" src="https://github.com/user-attachments/assets/ea07d14f-f3e0-4dc4-bfe6-50655c697b18" /><img width="802" height="396" alt="image" src="https://github.com/user-attachments/assets/a9e2bb8a-00fb-45fe-a178-1cfee52fe32f" />Crea un archivo llamado test.py:<img width="332" height="109" alt="image" src="https://github.com/user-attachments/assets/e7af39e1-9462-4360-8f35-bf4e704c5834" />¡Escribe un print y córrelo usando el botón de "Play" arriba a la derecha!<img width="1053" height="679" alt="image" src="https://github.com/user-attachments/assets/98ffb5ee-3297-47a6-8642-ce7336fe3299" />3.3 Entornos Virtuales (¡Muy Importante!)¿Qué es un entorno virtual (venv)?Es una copia aislada del intérprete de Python más su propio espacio para instalar librerías. Es como crear un "mini Python independiente" solo para un proyecto, evitando que los proyectos se mezclen y rompan entre sí.Paso 1: Crear el entorno (en la terminal de VS Code):python -m venv venv
Paso 2: Activarlo:venv\Scripts\activate
Verificación: Si funcionó, verás (venv) al inicio de tu línea de comandos en la terminal.🚨 ERROR COMÚN EN WINDOWS: Si te sale un error rojo sobre ExecutionPolicy, haz lo siguiente:Abre Windows PowerShell como administrador y ejecuta: Get-ExecutionPolicySi dice Restricted, ejecuta: Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSignedCierra la terminal, ábrela de nuevo y vuelve a intentar activar el entorno.¿Cómo salir de un entorno?Simplemente escribe deactivate en la consola.4. Arquitectura de un Proyecto: Mini Proyecto Paso a PasoPara programar como profesionales, no usamos un solo archivo gigante. Dividimos las responsabilidades.4.1 Estructura del ProyectoVamos a construir la siguiente estructura. Crea una carpeta mini_proyecto e inicializa tu entorno virtual en ella.mini_proyecto/
│
├── venv/                 # <-- Tu entorno virtual (ya creado)
├── src/                  # <-- Código fuente
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
(Nota: El archivo __init__.py puede estar vacío, sirve para que Python reconozca la carpeta como un paquete importable).4.2 Construyendo el CódigoCrea los siguientes archivos dentro de la estructura src/:1️⃣ El Modelo: models/usuario.pyRepresenta una entidad del sistema (un "molde" para los datos).class Usuario:
    def __init__(self, nombre: str, edad: int):
        self.nombre = nombre
        self.edad = edad

    def __str__(self):
        return f"{self.nombre} ({self.edad} años)"
2️⃣ La Utilidad: utils/calculos.pyFunciones matemáticas o genéricas separadas para poder reutilizarlas.def promedio(lista):
    if not lista:
        return 0
    return sum(lista) / len(lista)
3️⃣ El Servicio (Lógica de negocio): services/usuario_service.pyManeja los datos, no imprime en pantalla ni interactúa con el usuario directamente.from typing import List
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
4️⃣ El Punto de Entrada: main.pyEs el archivo principal que une todo y arranca el programa.from mini_proyecto.services.usuario_service import UsuarioService

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
🚀 Ejecutar el proyecto:Desde la raíz de la carpeta (no desde src), dile a Python dónde está tu código fuente y ejecuta el módulo:$env:PYTHONPATH="src"
python -m mini_proyecto.main
💡 ¿Por qué esta estructura es buena? Porque es modular, fácil de escalar, de testear y muy profesional. Si el proyecto crece, fácilmente agregas carpetas como database/ o api/ sin hacer un desastre.5. Buenas Prácticas: Dependencias e Ignorados5.1 El archivo requirements.txtEs el "inventario" de librerías de tu proyecto. Si le pasas el código a un compañero, él sabrá qué instalar.Pasos para generarlo:Asegúrate de tener el entorno virtual activado.Instala alguna librería (ej: pip install requests).Congela y exporta la lista:<!-- end list -->pip freeze > requirements.txt
Si otra persona recibe tu proyecto, solo deberá ejecutar: pip install -r requirements.txt.5.2 El archivo .gitignoreEs un archivo de texto CRÍTICO que le dice a Git qué archivos NO debe subir a GitHub (como entornos virtuales, contraseñas o archivos temporales).Crea un archivo llamado .gitignore en la raíz de tu proyecto con esto:# Entorno virtual (¡NUNCA SE SUBE!)
venv/

# Archivos compilados
__pycache__/
*.pyc

# Configuración de VS Code
.vscode/

# Archivos del sistema
.DS_Store
Thumbs.db
6. Cápsula Teórica: Bytecode y REPL<details><summary><strong>🧠 ¿Qué son los archivos .pyc y el Bytecode?</strong></summary>Python no ejecuta el texto que tú escribes.Lee tu código .pyLo compila a un código intermedio llamado Bytecode.Guarda ese resultado en un archivo .pyc (dentro de la carpeta __pycache__).La máquina virtual de Python ejecuta ese .pyc.Es por esto que JAMÁS subimos los .pyc a GitHub (se regeneran solos).</details><details><summary><strong>🔄 ¿Qué es el REPL?</strong></summary>REPL significa: Read, Eval, Print, Loop.Si escribes python en tu terminal sin un archivo, entras a un modo interactivo:&gt;&gt;&gt; 2 + 2
4
Para salir, simplemente escribe exit().</details>7. Control de Versiones: Git en VS CodeInicializa el repositorio desde el icono de Source Control en la barra lateral:<img width="540" height="639" alt="image" src="https://github.com/user-attachments/assets/f262c490-aa46-467b-ac49-1d68980e3b23" />Error común: Al hacer el primer commit te puede pedir que te identifiques. Abre la terminal y configura tus datos:<!-- end list -->git config --global user.name "Tu Nombre Completo"
git config --global user.email "tu_email@gmail.com"
Verifica que se guardó bien:<!-- end list -->git config --list
Escribe un mensaje en la caja de texto (ej. "Primer commit de mi mini proyecto") y presiona Commit. ¡Listo!8. Ecosistema Java: Hola MundoPara instalar y correr JAVA en VS Code, sigue estos pasos rápidos:Paso 1: Abre el Marketplace de VS Code e instala el Extension Pack for Java.<img width="831" height="369" alt="image" src="https://github.com/user-attachments/assets/c9f66193-762e-445b-a432-90a1df4740c2" />Paso 2: Presiona Ctrl+Shift+P, escribe Java: Getting Started (o búscalo en la pestaña Help -> Welcome) y selecciona la opción de instalar un JDK.<img width="896" height="452" alt="image" src="https://github.com/user-attachments/assets/9a36b904-5c62-476b-b475-68d7be44be62" />Paso 3: Descarga e instala el JDK siguiendo el asistente.<img width="921" height="429" alt="image" src="https://github.com/user-attachments/assets/93d97ac8-690e-46b8-93f1-27fcf710eab6" />☕ Tu primer Hola Mundo en JAVACrea una carpeta, por ejemplo: test_java.Crea un archivo llamado holamundo.java.Escribe el código. VS Code te ayudará a autocompletar la clase:<!-- end list -->public class holamundo {
    public static void main(String[] args) {
        System.out.println("Hola Mundo");
    }    
}
⚠️ REGLA DE ORO EN JAVA: El nombre de la clase pública (public class holamundo) tiene que ser exactamente igual al nombre de tu archivo (holamundo.java). Si no coinciden, ¡no funcionará!¡LISTO! Le das al botón de Run (play) que aparecerá sobre la función main y ya habrás corrido tu primer código en Java. 🎉
