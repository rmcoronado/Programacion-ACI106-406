# 🛡️ MÓDULO 1 — Fundamentos de Git y GitHub  
### Introducción al Control de Versiones  
**Carrera:** Ingeniería / Programación  
**Nivel:** Primer Año  

---

# 📌 Índice

1. [¿Por qué necesitamos Git?](#-por-qué-necesitamos-git)
2. [¿Qué es Git?](#-qué-es-git)
3. [¿Qué es GitHub?](#-qué-es-github)
4. [Conceptos Fundamentales](#-conceptos-fundamentales)
5. [Flujo de Trabajo en Git](#-flujo-de-trabajo-en-git)
6. [Comandos Esenciales](#-comandos-esenciales)
7. [Ejemplo Práctico Paso a Paso](#-ejemplo-práctico-paso-a-paso)
8. [Buenas Prácticas](#-buenas-prácticas)
9. [Errores Comunes](#-errores-comunes)
10. [Conclusión](#-conclusión)

---

# 🚨 ¿Por qué necesitamos Git?

Antes de Git, los proyectos se veían así:

- proyecto_final.py  
- proyecto_final_v2.py  
- proyecto_final_definitivo.py  
- proyecto_final_definitivo_ahora_si.py  

Problemas:

- No sabemos qué cambió
- No podemos volver atrás fácilmente
- No podemos colaborar sin sobrescribir archivos
- Perdemos trabajo

Git resuelve estos problemas.

---

# 🧠 ¿Qué es Git?

## Definición

Git es un **sistema de control de versiones distribuido**.

Permite:

- Guardar el historial completo de un proyecto
- Volver a versiones anteriores
- Trabajar en paralelo sin romper el proyecto principal
- Colaborar de forma profesional

---

## Cómo funciona internamente (concepto simple)

Git guarda "fotografías" del proyecto llamadas **commits**.

Cada commit:

- Guarda el estado completo del proyecto
- Tiene un identificador único
- Tiene autor y fecha
- Tiene un mensaje descriptivo

Es como una máquina del tiempo para tu código.

---

# ☁️ ¿Qué es GitHub?

Git y GitHub no son lo mismo.

| Git | GitHub |
|------|--------|
| Herramienta local | Plataforma en la nube |
| Controla versiones | Aloja repositorios |
| Funciona sin internet | Permite colaboración |

GitHub permite:

- Respaldar tu proyecto
- Compartirlo
- Colaborar
- Crear portafolio profesional

---

# 📂 Conceptos Fundamentales

## 📁 Repositorio

Carpeta que está siendo controlada por Git.

```bash
git init
