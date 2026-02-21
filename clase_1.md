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

Cómo cambiar entre versiones
----
Primero: qué es una “versión” en Git
---
En Git no existen “versiones” como v1, v2, v3 automáticamente.

Las versiones son:

🔹 Commits

🔹 Tags (versiones etiquetadas como v1.0)

🔹 Ramas (branch)

Moverte entre versiones casi siempre significa:

Cambiar el commit al que apunta tu HEAD.

Paso 1 — Ver los commits disponibles
---
```bash
git log --oneline
```
Salida de ejemplo:
```bash
a3f9d2c Agrega validación
91ac2f4 Corrige bug
5b7e123 Primera versión
```
Cada línea es una versión.

Moverte a un commit específico (modo exploración)
---
Comando:
```bash
git checkout 91ac2f4
```
O moderno:
```bash
git switch --detach 91ac2f4
```
**Qué pasa cuando lo haces**

Git muestra algo como:
```bash
You are in 'detached HEAD' state.
```

Eso significa:

Estás mirando una versión antigua, pero no estás en una rama.

Tu proyecto ahora está exactamente como estaba en ese commit.

¿Qué es HEAD?
---
HEAD es un puntero que normalmente apunta a:
```bash
HEAD → main → último commit
```
Cuando haces checkout a un commit:
```bash
HEAD → 91ac2f4 (sin rama)
```
Eso es estado detached.

🛑 Importante
----
Si modificas archivos en este estado y haces commit:

El commit queda “huérfano” si no creas una rama.

Forma correcta de trabajar desde una versión antigua 🌿
---
Si quieres modificar desde un commit antiguo:
```bash
git checkout -b nueva-rama 91ac2f4
```
O:
```bash
git switch -c nueva-rama 91ac2f4
```
Ahora:
```bash
HEAD → nueva-rama → 91ac2f4
```
Y puedes trabajar seguro.

Volver a la versión más reciente
---
Si estabas en detached:
```bash
git switch main
```

O:
```bash
git checkout main
```
Y vuelves al último commit de esa rama.

Diferencia importante: checkout vs reset
---
🔹 checkout / switch

Cambia lo que estás mirando.

🔹 reset

Reescribe historial.

Ejemplo:
```bash
git reset --hard 91ac2f4
```

Eso mueve la rama actual hacia atrás hasta un punto X y borra commits posteriores al punto X que hayas guardado.

⚠️ Mucho más peligroso.


Resumen de formas de moverte
---
| Objetivo                      | Comando                     | Seguro |
| ----------------------------- | --------------------------- | ------ |
| Solo mirar versión            | `git checkout <hash>`       | ✅      |
| Trabajar desde ahí            | `git switch -c rama <hash>` | ✅      |
| Volver atrás borrando commits | `git reset --hard <hash>`   | ⚠️     |
| Volver a rama principal       | `git switch main`           | ✅      |

Ejemplo completo paso a paso
---
Supongamos:
```bash
A --- B --- C --- D (main)
```
Quieres ir a B.

1. Ver historial
```bash
git log --oneline
```
2. Ir a B
```bash
git checkout <hash-de-B>
```
Ahora estás en: 
```bash
A --- B (HEAD)
```

3. Volver a main:
   ```bash
   git switch main
   ```
Y vuelves a:
  ```bash
   A --- B --- C --- D (HEAD)
   ```

Concepto clave

Moverte entre versiones ≠ borrar historia.

Solo estás cambiando el puntero HEAD.

¿Qué es realmente una rama (branch)?
----
Muchos creen que una rama es una copia del proyecto.

❌ No lo es.

Una rama es solo un puntero a un commit.

Ejemplo visual
---
Imagina esto:
```bash
A --- B --- C  (main)
```
Aquí:

**main** apunta a **C**

**HEAD** apunta a **main**

Crear una rama nueva
---
```bash
git switch -c feature-login
```

Ahora:
```bash
A --- B --- C  (main)
               \
                (feature-login)
```
Ambas ramas apuntan a C.

Haces un commit en feature-login
---
```bash
A --- B --- C  (main)
               \
                D  (feature-login)
```
Solo la nueva rama avanza.

**main** sigue en **C**.

¿Qué es un merge?
----
Un merge combina dos historias.

Supongamos que estás en <mark>main</mark> y quieres traer los cambios de <mark>feature-login</mark> .
```bash
git switch main
git merge feature-login
```
Resultado típico
---
Si no hubo conflictos:
```bash
A --- B --- C -------- E  (main)
               \      /
                D ----    (feature-login)
```
Git crea un commit especial llamado **merge commit (E)**.

Qué contiene un merge commit
---

1. Tiene dos padres (C y D)
2. Une ambos historiales
3. Conserva trazabilidad completa

¿Qué pasa si hay conflictos?
----
Git te dirá algo como:
```bash
CONFLICT (content): Merge conflict in archivo.py
```
El archivo quedará así:

```bash
<<<<<<< HEAD
codigo en main
=======
codigo en feature-login
>>>>>>> feature-login
```

Tú debes:
---

1. Editar manualmente
2. Resolver el conflicto
3. Guardar
4. Hacer:
   ```bash
   git add archivo.py
   git commit
   ```
   
  ¿Qué es un conflicto?
   ---
Un conflicto ocurre cuando:

Dos ramas modificaron la misma parte del mismo archivo de forma distinta.

Git no puede decidir cuál versión es correcta.

Entonces te pide que elijas manualmente.

Ejemplo visual paso a paso
----
Supongamos este historial:
```bash
A --- B --- C   (main)
       \
        D --- E  (feature)
```
Ambas ramas partieron desde B.

Supongamos que el archivo app.py era así en B:
---
```bash
def saludar():
    print("Hola")
```

En main lo cambiaste a:
```bash
def saludar():
    print("Hola mundo")
```
Commit C.

En feature lo cambiaste a:
---
```bash
def saludar():
    print("Hola usuario")
```
Commit E.

Intentas hacer merge
---
Te mueves a main:
```bash
git switch main
```
Luego:
```bash
git merge feature
```

💥 Git responde:
```bash
Auto-merging app.py
CONFLICT (content): Merge conflict in app.py
Automatic merge failed; fix conflicts and then commit the result.
```

Así queda el archivo
```bash
def saludar():
<<<<<<< HEAD
    print("Hola mundo")
=======
    print("Hola usuario")
>>>>>>> feature
```

Qué significa esto
---
| Parte     | Significado                  |
| --------- | ---------------------------- |
| `HEAD`    | Lo que estaba en main        |
| `=======` | Separador                    |
| `feature` | Lo que viene de la otra rama |

Cómo resolverlo correctamente
---
Debes editar el archivo; tienes 3 opciones:

Opción A — Elegir main

Dejas:
```bash
def saludar():
    print("Hola mundo")
```

Opción B — Elegir feature

Dejas:
```bash
def saludar():
    print("Hola usuario")
```

Opción C — Combinar

Dejas:
```bash
def saludar():
    print("Hola mundo")
    print("Hola usuario")
```

⚠️ Debes borrar completamente:
---
```bash
<<<<<<< HEAD
=======
>>>>>>> feature
```

Confirmar resolución
---
Después de editar y guardar:
```bash
git add app.py
```
Luego:
```bash
git commit
```
Git creará el commit de merge.

Resultado final
---
```bash
A --- B --- C -------- M (main)
       \              /
        D --- E ------
```
M es el merge commit.

Cómo ver qué archivos están en conflicto
---
Si estás en conflicto:
```bash
git status
```
Verás: 
```bash
Unmerged paths:
  both modified:   app.py
```

Si quieres cancelar el merge
---
Si te arrepientes:
```bash
git merge --abort
```

Todo vuelve al estado previo.

⚡ Herramientas visuales (muy útil)
---
Si usas Visual Studio Code:

Te mostrará botones como:

- Accept Current Change
- Accept Incoming Change
- Accept Both Changes

Mucho más cómodo que editar a mano.

Flujo profesional recomendado
-----
```bash
git switch main
git pull (se explica más adelante)
git merge feature
# resolver conflictos
git add .
git commit
git push (se explica más adelante)
```

Resumen clave
----
| Situación              | Qué hacer           |
| ---------------------- | ------------------- |
| Conflicto detectado    | Editar archivo      |
| Ver archivos afectados | `git status`        |
| Confirmar resolución   | `git add`           |
| Crear merge commit     | `git commit`        |
| Cancelar merge         | `git merge --abort` |

Consejo profesional importante
----
Para reducir conflictos:

1. Haz commits pequeños
2. Haz pull frecuente
3. No trabajes semanas sin sincronizar
4. Divide tareas por archivos si es posible

### Conectar el repositorio local con la Nube

Flujo profesional recomendado
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin git@github.com:usuario/proyecto.git
git branch -M main
git push -u origin main
```

#### Crear repositorio en GitHub
1. Ir a GitHub
2. Click en New repository
3. Poner nombre (RECOMENDADO QUE SEA EL MISMO NOMBRE DEL PROYECTO LOCAL)
4. ⚠ No marcar "Initialize with README"
5. Crear

Conectar tu repo local al remoto
---
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
Debe mostrar:
```bash
origin  https://github.com/usuario/simulador-mrf.git (fetch)
origin  https://github.com/usuario/simulador-mrf.git (push)
```

Asegurar nombre de rama principal
---
```bash
git branch -M main
```

Subir el proyecto
---
```bash
git push -u origin main
```
Salida típica:
```bash
Enumerating objects...
Writing objects...
To https://github.com/usuario/simulador-mrf.git
 * [new branch] main -> main
```

Listo 🎉 ya está conectado.

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

Diferencia entre fetch, pull y push
----
Porque Git distingue entre:

🔽 (fetch) → desde dónde DESCARGA cambios

🔼 (push) → hacia dónde ENVÍA cambios

Normalmente ambas URLs son iguales.

Pero podrían ser distintas (por ejemplo, en forks o servidores distintos).

git fetch
---
Descarga cambios del remoto, pero NO los mezcla con tu rama actual.
```bash
git fetch origin
```
Qué hace:
```bash
GitHub → tu repo local (pero en rama remota)
```
No modifica tus archivos de trabajo.

git pull
---
Es equivalente a:
```bash
git fetch
git merge
```
O sea:

1. Descarga cambios
2. Los combina con tu rama actual
```bash
GitHub → descarga → mezcla automáticamente
```
git push
---
Envía tus commits locales al remoto.
```bash
Tu máquina → GitHub
```

🧠 Visualización clara
----
Imagina esto:
```bash
Tu PC              GitHub
A---B---C   ←→     A---B
```
Otra persona dejó el repo en B.

Tú hiciste commit C localmente.

Si haces git push: Git sube C.
---
Si alguien hizo D en GitHub
---
```bash
Tu PC              GitHub
A---B---C          A---B---D
```

Si haces push ahora:

❌ Fallará.

¿Por qué hacer pull antes de push?
---
Porque tu historia puede estar desactualizada.

Si GitHub tiene commits que tú no tienes:
```bash
Tu PC:      A---B---C
GitHub:     A---B---D
```
Git no puede simplemente agregar C encima de D sin que tú lo revises.

Por eso te dirá:
```bash
rejected (non-fast-forward)
```

Flujo correcto profesional
---
Antes de subir cambios:
```bash
git pull --rebase
git push
```
Esto:

1. Descarga cambios remotos
2. Coloca tus commits encima
3. Luego sube todo limpio

Qué significa "non-fast-forward"
----
Un push es "fast-forward" cuando:
```bash
A---B---C
        ↑
     remoto
```
Tu commit simplemente avanza la rama.

Pero si hay divergencia:
```bash
      C
     /
A---B
     \
      D
```

Ya no es línea recta.

Hay que integrar primero.

Ejemplo real paso a paso
----
Supongamos:
```bash
git add .
git commit -m "Agrego función"
```
Luego haces:
```bash
git push
```
Y sale:
```bash
! [rejected] main -> main (non-fast-forward)
```
Solución:
```bash
git pull --rebase
git push
```

Resumen mental definitivo
-----

🔼 push = envío mis commits

🔽 fetch = miro lo que hay en remoto

🔽 pull = traigo y mezclo

⚠️ pull antes de push evita conflictos

Consejo profesional importante
-----
Configura pull con rebase por defecto:
```bash
git config --global pull.rebase true
```
Así evitas muchos commits de merge innecesarios.


## Buenas Prácticas

1. Commits pequeños y frecuentes

2. Mensajes claros

3. No subir archivos grandes innecesarios

3. Usar .gitignore

📄 Ejemplo de .gitignore (Python)
__pycache__/
*.pyc
.env
venv/

5. Hacer pull antes de push

6. Usar ramas para experimentar


## ❌ Errores Comunes

1. Hacer un commit gigante

2. Mensajes como "cambios"

2. No usar ramas

3. Subir claves privadas

4. No usar SSH


🧠 Tips Profesionales
----
1. Usa git log --oneline

2. Usa git diff

3. Usa git branch

4. Aprende a leer conflictos

5. Nunca subas archivos sensibles

6. Crea commits descriptivos

🧪 Checklist Profesional
----

☑ Git instalado
☑ Cuenta GitHub creada
☑ SSH configurado
☑ Primer repositorio creado
☑ Primer push realizado
☑ Rama creada y fusionada

🎯 Conclusión
----
1. Git no es solo una herramienta.

2. Es una competencia profesional obligatoria.

3. Si dominas Git:

4. Piensas como ingeniero

5. Trabajas como profesional

6. Colaboras como industria

Bienvenido al desarrollo profesional.
---
