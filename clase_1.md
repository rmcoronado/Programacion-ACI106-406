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

## 🔎 Verificación de Instalación

En terminal:

```bash
git --version
```

Debe mostrar algo como:

_git version 2.x.x_

## 🌐 Crear Cuenta en GitHub

Paso 1: Ir a https://github.com

Paso 2: Click en "Sign up"

Paso 3: Ingresar email

Paso 4: Crear contraseña

Paso 5: Elegir username profesional

Paso 6: Verificar correo

**$\color{red}{\text{Consejo profesional:}}$** Usa un username que te identifique como un profesional, nada de soy LOBO therian, Goku, sayayin, etc...

## ⚙️ Configuración Inicial de Git

Configura tu identidad (una sola vez):

```bash
git config --global user.name "Tu Nombre"
```

```bash
git config --global user.email "tu_email@gmail.com"
```

Verificar:

```bash
git config --list
```

Configurar el nombre de Master a Main: 

```bash
git config --global init.defaultBranch main
```

Eliminar una configuración no deseada: 

```bash
git config --global --unset user.name
```

Activar colores en la terminal

```bash
git config --global color.ui auto
```

## 🔐 Configuración de Llaves SSH

Esta llave es importante para conectar de forma automática y segura el repositorio local con github (repositorio en la nube)

#### 1️⃣ Generar llave
```bash
ssh-keygen -t ed25519 -C "tu_email@gmail.com"
```
Presiona ENTER a todo.

Verifica creación de la llave con el siguiente comando: 

```bash
ls ~/.ssh
```

Si ves archivos como:

**id_ed25519**

**id_ed25519.pub**

Ya tienes una llave.

Si no aparece nada → debes crearla.


### 2️⃣ Iniciar agente SSH

Windows / Mac

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

### 3️⃣ Copiar llave pública

Windows (Git Bash)
```bash
cat ~/.ssh/id_ed25519.pub | clip
```
Mac
```bash
pbcopy < ~/.ssh/id_ed25519.pub
```
Linux
```bash
cat ~/.ssh/id_ed25519.pub
```

Copiar manualmente.

#### 4️⃣ Agregar llave a GitHub

1. Ir a GitHub

2. Click en tu foto → Settings

3. Ir a SSH and GPG keys

4. Click en New SSH key

5. Pegar la llave copiada

6. Guardar

### 5️⃣ Verificar conexión

```bash
ssh -T git@github.com
```

Debe decir:

**Hi username! You've successfully authenticated**

## Comandos bash importantes: 

Eliminar archivos .* no deseados o que se crearon por error: 

```bash
rm -rf .git
```

Listar carpetas: 

```bash
ls
```

Moverse hacia una carpeta: 
```bash
cd  direccion de carpeta (tip: usar Tab para autocompletar)
```

Devolver a la carpeta superior: 

```bash
cd  ..
```

Crear una carpeta

```bash
mkdir nombre_de_carpeta
```

Visualizar en que direccion actual estas: 
```bash
pwd
```


**IMPORTANTE RECOMENDACION**: estudiar comandos bash.


## 🔗 Conectar Proyecto Local a GitHub

Escenario

Tienes esto:

```bash
mi_proyecto/
   archivo1.py
   archivo2.py
```

✅ Siempre dentro de la carpeta del proyecto. $\color{red}{\text{Nunca fuera.}}$ 


---
Antes de empezar: el modelo mental correcto

Git tiene 3 áreas principales:

```bash
1️⃣ Working Directory  → tus archivos reales
2️⃣ Staging Area       → lo que prepararás para commit
3️⃣ Repository (.git)  → donde viven los commits
```
Visualmente

```bash
Archivo → git add → Staging (preparing and organizing a commit) → git commit → Historial
```
---



### 1️⃣ Entrar a la carpeta del proyecto
```bash
cd mi_proyecto
```

Verifica que estás en la carpeta: 
```bash
pwd
```



### 2️⃣ Inicializar Git (dentro de la carpeta)


```bash
git init
```

Eso crea:

```bash
mi_proyecto/.git
```

**Ahora esa carpeta ya es un repositorio.**

----
Ahora podemos ver el estatus con:

```bash
git status
```
Podrías ver: 
```bash
On branch main
Changes not staged for commit:
  modified:   archivo.py
```
¿Qué significa?

Estás en la rama main

Modificaste archivo.py

Aún NO lo agregaste al staging
----
📂 Qué pasa si creas un archivo nuevo dentro de tu proyecto:
```bash
git status
```
Muestra lo siguiente:
```bash
Untracked files:
  nuevo.py
```
Eso significa:

Git lo ve, pero aún no lo está siguiendo.
----
🟢 Qué debes hacer en ambos casos:
```bash
git add .
```
📌 Qué hace

Mueve cambios desde:
```bash
Working Directory → Staging Area
```
El punto **.** significa: Todo lo que está en esta carpeta y subcarpetas.

Siguiendo el ejemplo de nuevo.py, el resultado sería:
```bash
Changes to be committed:
  modified: nuevo.py
```
Eso significa:

Ya está en staging.
Está listo para el commit.

🧠 Internamente

git status compara:
```bash
Working Directory  vs  Staging Area
Staging Area       vs  Último Commit
```
Y te muestra diferencias.
---

🧠 Qué pasa internamente con **git add .**

Git:

1. Calcula hash del archivo
2. Guarda snapshot en staging
3. No crea commit aún

**Muy importante:**

git add NO guarda historial.
Solo prepara.
----
Ahora debemos hacer el primer $\color{red}{\text{COMMIT}}$ : 
```bash
git commit -m "MENSAJE"
```
Salida típica:
```bash
[main 3f5a2c1] Mensaje
 1 file changed, 2 insertions(+)
```

Eso significa:

**Rama**: main

**Hash** corto del commit: 3f5a2c1

**Mensaje**

**Archivos afectados**:  1 file changed

**Líneas agregadas/eliminadas**:2 insertions(+)

----
🧪 Con -v
```bash
git commit -v
```
Se abre el editor (por ejemplo Visual Studio Code).

Y verás:
```bash
# On branch main
# Changes to be committed:
#   modified: archivo.py

diff --git a/archivo.py b/archivo.py
+ nueva linea agregada
- linea eliminada
```
Eso es el diff completo.

Luego escribes el mensaje arriba, guardas y cierras.

----
🧠 Qué hace internamente git commit

Cuando haces commit:

1. Crea snapshot completo
2. Genera hash SHA único
3. Guarda autor
4. Guarda fecha
5. Guarda mensaje
6. Guarda referencia al commit anterior

Git NO guarda solo cambios.
Guarda un árbol completo del proyecto.

🔍 Ejemplo real de salida:
---
```bash
[main 91ac2f4] Agrega validación de entrada
 2 files changed, 10 insertions(+), 2 deletions(-)
```
Interpretación:

**main** → rama

**91ac2f4** → hash corto

**Mensaje**

**2 archivos cambiaron**

**10 líneas agregadas**

**2 eliminadas**

🔐 ¿Qué es el hash SHA en Git?
----


Cada commit en Git tiene un identificador único, algo como:
```bash
91ac2f4e8b3c2a7d9f6a1c0e4d...
```

Eso es un SHA-1 hash.

📌 Qué significa

Es un código generado a partir de:

**Contenido de los archivos**

**Mensaje del commit**

**Autor**

**Fecha**

**Commit padre**

Si cambias una sola letra, el hash cambia completamente.

🧠 Por qué es importante
----
Porque hace que Git sea:

🔒 Seguro

📦 Inmutable

🧾 Trazable

Git no dice “versión 5”.
Git dice “commit 91ac2f4”.

📌 Puedes verlo con:
---
```bash
git log
```
El resultado en consola es: 
```bash
commit e76321cd27af8d61c00f89cb9b4598faefeaf1f0 (HEAD -> main)
Author: rmcoronado <rmcoronado@uc.cl>
Date:   Fri Feb 20 16:06:12 2026 -0300
```

Cómo deshacer un commit
----
Hay varias formas. Aquí las más importantes:

A) Deshacer el último commit pero mantener cambios:
```bash
git reset --soft HEAD~1
```
Resultado:

Se borra el commit

Los cambios vuelven al staging

---
B) Borrar commit y sacar cambios del staging
```bash
git reset --mixed HEAD~1
```
(default)

Se borra commit

Cambios quedan en working directory

---
C) Borrar TODO (cuidado) 🔴
```bash
git reset --hard HEAD~1
```
Se borra commit

Se borran cambios

No hay vuelta atrás (salvo reflog)

---


---
### 4️⃣ Crear repositorio en GitHub
1. Ir a GitHub
2. Click en New repository
3. Poner nombre (RECOMENDADO QUE SEA EL MISMO NOMBRE DEL PROYECTO LOCAL)
4. ⚠ No marcar "Initialize with README"
5. Crear

GitHub te mostrará instrucciones tipo:
```bash
git remote add origin ...
```

```bash
git remote add origin git@github.com:USERNAME/REPO.git
```

Verificar:
```bash
git remote -v
```

git push -u origin main

🔄 Flujo Profesional de Trabajo

Siempre:

```bash
git status
git add .
git commit -m "mensaje claro"
git push
```

En equipo:

git pull


Antes de trabajar.


## Clonar un repositorio en local: 

A veces creamos el repositorio en github o queremos partir de uno ya existente. Para ello debemos aplicar los siguientes pasos: 

1. Listar la carpeta o directorio donde estamos parados:
   ```bash
   ls
   ```
2. Moverse a la carpeta o directorio donde queremos clonar el repositorio
   ```bash
   cd direccion_de_carpeta
   ```
3. Ir a tu repositorio en github y copiar la dirección ssh (ir a botón verde $\color{green}{\text{<> Code}}$:
    ```bash
   git@github.com:rmcoronado/Programacion-ACI106-406.git
   ```

5.  Hacer git clone en la consola de gitbash:
   ```bash
   git clone git@github.com:rmcoronado/Programacion-ACI106-406.git
   ```
6. Moverse a la carpeta del repositorio:
    ```bash
   cd Programacion-ACI106-406/
   ```
7. Comprobar que todo quedó bien:
   ```bash
  git remote -v
   ```

Debe mostrar algo como:

```bash
origin  git@github.com:usuario/mi-proyecto.git (fetch)
origin  git@github.com:usuario/mi-proyecto.git (push)
```

Verifica la rama: 
```bash
git branch
```

Debería aparecer que estas en la rama principal: **main**


   

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

