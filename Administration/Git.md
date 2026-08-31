# Git y GitHub - Control de Versiones y Contribución a Código Abierto

## 📌 Metadatos del Documento

**Versión de Git Cubierta:** v2.39+ (última estable)
**Funciones de GitHub:** Actions, Pages, CLI, Desktop, Codespaces
**Última Actualización:** 2026-08-31
**Nivel de Habilidad:** Principiante a Avanzado
**Requisitos Previos:**
- Conocimientos básicos de línea de comandos
- Computadora con Git instalado
- Cuenta de GitHub (el nivel gratuito funciona)
- Editor de texto (VS Code, Sublime, etc.)

---

## 🎯 Cuándo Usar Este Conocimiento

Usa esta guía cuando necesites:

✅ **Iniciar el control de versiones de un proyecto**
- Inicializar un repositorio Git
- Configurar nombre de usuario y correo
- Crear mensajes de commit significativos

✅ **Colaborar con un equipo**
- Trabajar con ramas de forma efectiva
- Fusionar código y resolver conflictos
- Usar GitHub para revisiones de código

✅ **Contribuir a código abierto**
- Hacer fork de repositorios correctamente
- Crear Pull Requests de calidad
- Seguir las guías de contribución del proyecto
- Sincronizar tu fork con el upstream

✅ **Automatizar flujos de trabajo con GitHub Actions**
- Configurar pipelines de CI/CD
- Construir y probar código automáticamente
- Desplegar a servidores de producción
- Programar tareas automatizadas con cron
- Construir y enviar imágenes de Docker
- Desplegar a clústeres de Kubernetes

✅ **Gestionar repositorios remotos**
- Enviar y traer código hacia/desde GitHub
- Trabajar con múltiples remotos
- Configurar autenticación SSH
- Usar la CLI de GitHub para mayor eficiencia

✅ **Depurar y recuperar**
- Deshacer commits de forma segura
- Navegar por el historial de commits
- Recuperar commits eliminados con reflog
- Guardar cambios en progreso con stash

✅ **Referencia rápida durante el desarrollo**
- Consultar comandos específicos de Git
- Comprobar la sintaxis de GitHub Actions
- Encontrar buenas prácticas para commits y PRs
- Solucionar problemas comunes de Git

**Consejos de Navegación Rápida:**
- Salta a secciones específicas usando la Tabla de Contenidos
- Cada sección incluye ejemplos prácticos y fragmentos de código
- Las buenas prácticas están marcadas con ✅
- Los errores comunes están marcados con ❌
- Las advertencias están marcadas con ⚠️
- Parte 1: Fundamentos de Git y GitHub (Secciones 1-35)
- Parte 2: GitHub Actions - CI/CD (Secciones 36-46)
- Parte 3: Contribución a Código Abierto (Secciones 47-61)

---

## 📋 Tabla de Contenidos

### Parte 1: Fundamentos de Git y GitHub

1. [Introducción a Git](#1-introducción-a-git)
2. [Historia de Git](#2-historia-de-git)
3. [Instalación de Git](#3-instalación-de-git)
4. [Comandos Básicos de Terminal](#4-comandos-básicos-de-terminal)
5. [Configuración de Git](#5-configuración-de-git)
6. [git init](#6-git-init)
7. [Ramas en Git](#7-ramas-en-git)
8. [git add y git commit](#8-git-add-y-git-commit)
9. [git log y git status](#9-git-log-y-git-status)
10. [git checkout y git reset](#10-git-checkout-y-git-reset)
11. [git alias](#11-git-alias)
12. [Archivo .gitignore](#12-archivo-gitignore)
13. [git diff](#13-git-diff)
14. [Moverse Entre Commits](#14-moverse-entre-commits)
15. [git reset --hard y git reflog](#15-git-reset---hard-y-git-reflog)
16. [git tag](#16-git-tag)
17. [git branch y git switch](#17-git-branch-y-git-switch)
18. [git merge](#18-git-merge)
19. [Resolución de Conflictos](#19-resolución-de-conflictos)
20. [git stash](#20-git-stash)
21. [Reintegración de Ramas](#21-reintegración-de-ramas)
22. [Eliminar Ramas](#22-eliminar-ramas)
23. [Introducción a GitHub](#23-introducción-a-github)
24. [Primeros Pasos en GitHub](#24-primeros-pasos-en-github)
25. [Local y Remoto](#25-local-y-remoto)
26. [Autenticación SSH](#26-autenticación-ssh)
27. [git remote](#27-git-remote)
28. [git fetch y git pull](#28-git-fetch-y-git-pull)
29. [git clone](#29-git-clone)
30. [git push](#30-git-push)
31. [Fork en GitHub](#31-fork-en-github)
32. [Pull Requests (PR)](#32-pull-requests-pr)
33. [GitHub Flow](#33-github-flow)
34. [git cherry-pick y git rebase](#34-git-cherry-pick-y-git-rebase)
35. [GitHub Pages](#35-github-pages)

### Parte 2: GitHub Actions - Automatización de CI/CD

36. [Introducción a GitHub Actions](#36-introducción-a-github-actions)
37. [Precios de GitHub Actions](#37-precios-de-github-actions)
38. [Conceptos Fundamentales: Workflows, Jobs, Steps](#38-conceptos-fundamentales-workflows-jobs-steps)
39. [Creando Tu Primera Action](#39-creando-tu-primera-action)
40. [Disparadores de Workflow](#40-disparadores-de-workflow)
41. [Usando Actions del Marketplace](#41-usando-actions-del-marketplace)
42. [Gestión de Secretos](#42-gestión-de-secretos)
43. [Build y Push de Docker](#43-build-y-push-de-docker)
44. [Despliegue en Kubernetes](#44-despliegue-en-kubernetes)
45. [Ver Logs y Depurar](#45-ver-logs-y-depurar)
46. [Trabajos Programados con Cron](#46-trabajos-programados-con-cron)

### Parte 3: Contribuir a Código Abierto

47. [Por Qué Contribuir a Código Abierto](#47-por-qué-contribuir-a-código-abierto)
48. [Encontrar Proyectos para Contribuir](#48-encontrar-proyectos-para-contribuir)
49. [Entendiendo el Flujo de Fork](#49-entendiendo-el-flujo-de-fork)
50. [Estrategias de Clonado](#50-estrategias-de-clonado)
51. [Trabajando con Upstream](#51-trabajando-con-upstream)
52. [Creando Pull Requests de Calidad](#52-creando-pull-requests-de-calidad)
53. [Buenas Prácticas de PR](#53-buenas-prácticas-de-pr)
54. [Archivos CONTRIBUTING.md](#54-archivos-contributingmd)
55. [Guías de Mensajes de Commit](#55-guías-de-mensajes-de-commit)
56. [Sincronizar Tu Fork](#56-sincronizar-tu-fork)
57. [GitHub CLI (gh)](#57-github-cli-gh)
58. [GitHub Desktop](#58-github-desktop)
59. [GitHub Codespaces](#59-github-codespaces)
60. [git switch vs git checkout](#60-git-switch-vs-git-checkout)
61. [Múltiples Repositorios Remotos](#61-múltiples-repositorios-remotos)

---

## Descripción General

Git y GitHub son dos herramientas fundamentales en el mundo del desarrollo de software. Git es el sistema de control de versiones más popular, y GitHub es la plataforma colaborativa de código líder.

### ¿Qué es Git?

- **Sistema de Control de Versiones (VCS)**: Rastrea los cambios en archivos y código a lo largo del tiempo
- **Sistema Distribuido**: Cada desarrollador tiene una copia completa del repositorio
- **Creado por**: Linus Torvalds (creador de Linux) en 2005
- **Código Abierto**: Todo el código de Git está disponible en GitHub
- **Estándar de la Industria**: Más del 93% de los desarrolladores usan Git (encuesta de Stack Overflow)

### ¿Qué es GitHub?

- **Plataforma Remota**: Servicio de alojamiento en la nube para repositorios Git
- **Colaboración**: Permite el desarrollo en equipo y compartir código
- **94 Millones de Desarrolladores**: La mayor comunidad de desarrolladores del mundo
- **Más del 90% de las Empresas Fortune 500**: Usan GitHub para su código
- **Funciones**: Issues, Pull Requests, Actions, Pages, Projects

### Alternativas a GitHub

Aunque GitHub es el más popular, existen otras plataformas de alojamiento de Git:

| Plataforma | Ventajas | Desventajas |
|----------|------|------|
| **GitHub** | ✅ La mayor comunidad<br>✅ Las mejores funciones<br>✅ Respaldo de Microsoft<br>✅ Copilot AI | ⚠️ Puede ser caro para equipos |
| **GitLab** | ✅ Gran CI/CD<br>✅ Opción autoalojada<br>✅ Nivel gratuito generoso | ⚠️ Comunidad más pequeña |
| **Bitbucket** | ✅ Integración con Jira<br>✅ Bueno para empresas | ⚠️ UI menos intuitiva |
| **Azure Repos** | ✅ Integración con Azure | ⚠️ El menos popular<br>⚠️ Funciones limitadas |

**Recomendación**: Usa GitHub para:
- Proyectos de código abierto
- Proyectos personales
- Construir un portafolio
- El mejor soporte de la comunidad

### Diferencias Clave: Git vs GitHub

| Git | GitHub |
|-----|--------|
| Software de control de versiones | Servicio de alojamiento web |
| Funciona localmente en tu máquina | Funciona en la nube |
| Herramienta de línea de comandos | Interfaz web gráfica |
| Gestiona el historial del código | Facilita la colaboración |
| Creado en 2005 | Fundado en 2008 |
| Gratis y de código abierto | Nivel gratuito + planes de pago |

---

## 1. Introducción a Git

**Por Qué Git es Esencial:**

Git resuelve el problema de gestionar versiones de código sin crear múltiples carpetas como:
- `proyecto_final`
- `proyecto_final_v2`
- `proyecto_final_final`
- `proyecto_final_final_definitivo`

**Beneficios Principales:**

✅ Rastrear el historial completo de cambios
✅ Crear "instantáneas" seguras de tu código
✅ Colaborar con múltiples desarrolladores
✅ Revertir a versiones anteriores fácilmente
✅ Trabajar en funcionalidades de forma aislada (ramas)
✅ No volver a perder código nunca

**Adopción en la Industria:**

Según la encuesta a desarrolladores de Stack Overflow:
- El **93%** de los desarrolladores usan Git
- El **97%** de los desarrolladores profesionales usan Git
- El **87%** usa GitHub específicamente
- El **55%** de las empresas usa GitHub profesionalmente

---

## 2. Historia de Git

**Historia de su Creación:**

- **Creador**: Linus Torvalds (creador del kernel de Linux)
- **Año**: 7 de abril de 2005
- **Motivación**: Necesitaba un mejor control de versiones para el desarrollo de Linux
- **Solución**: Construyó su propio VCS en unas pocas semanas

**Por Qué Linus Creó Git:**

1. Los VCS existentes no cumplían las necesidades del kernel de Linux
2. Necesitaba un sistema distribuido (no centralizado)
3. Requería un rendimiento rápido para proyectos grandes
4. Quería una herramienta simple y confiable

**Evolución:**

- **2005**: Lanzamiento inicial
- **2005-Presente**: Desarrollo continuo
- **Actual**: Versión 2.39+ (mantenido activamente, nuevos lanzamientos cada pocos meses)
- **Activo**: Nuevos lanzamientos cada pocos meses

---

## 3. Instalación de Git

**Sitio Web Oficial:**
[https://git-scm.com](https://git-scm.com)

**Instalación por Plataforma:**

#### macOS
```bash
# Usando Homebrew
brew install git

# Verificar la instalación
git --version
git -v
```

#### Windows
```bash
# Descargar desde git-scm.com
# O usar winget
winget install Git.Git

# Verificar la instalación
git --version
```

#### Linux (Ubuntu/Debian)
```bash
# Usando apt
sudo apt update
sudo apt install git

# Verificar la instalación
git --version
```

**Comprobación Post-Instalación:**

```bash
# Comprobar la versión de Git
git --version

# Obtener ayuda
git --help
git -h
```

**Sistemas con Git Integrado:**
- **macOS**: Git viene preinstalado
- **Linux**: Normalmente preinstalado
- **Windows**: Requiere instalación manual

---

## 4. Comandos Básicos de Terminal

Antes de trabajar con Git, aprende la navegación básica de terminal:

#### Comandos Esenciales

```bash
# Listar archivos y directorios
ls

# Cambiar de directorio
cd Desktop
cd ..  # Subir un nivel

# Imprimir el directorio de trabajo (ubicación actual)
pwd

# Crear un directorio
mkdir hello-git

# Crear un archivo
touch hello-git.py

# Limpiar la terminal
clear

# Autocompletar con Tab
cd Des[TAB]  # Se completa a Desktop
```

#### Ejemplos de Navegación

```bash
# Navegar al proyecto
cd ~/Desktop/hello-git

# Ver dónde estás
pwd
# Salida: /Users/username/Desktop/hello-git

# Listar contenidos
ls

# Volver al home
cd ~
```

---

## 5. Configuración de Git

**Configuración Obligatoria:**

Antes de usar Git, DEBES configurar:
1. **Nombre de usuario**
2. **Correo del usuario**

Estos identifican quién hace cada commit.

#### Establecer el Nombre de Usuario

```bash
git config --global user.name "Your Name"
```

#### Establecer el Correo del Usuario

```bash
git config --global user.email "you@example.com"
```

> **Consejo:** Usa el mismo correo registrado en tu host de Git (p. ej. GitHub) para que los commits se atribuyan correctamente. Por privacidad, GitHub puede proporcionar un correo `noreply` (`Settings → Emails → Keep my email address private`).

#### Ver la Configuración

```bash
# Ver todos los ajustes
git config --list

# Ver un ajuste específico
git config user.name
git config user.email
```

#### Ubicación del Archivo de Configuración

```bash
# La configuración global se almacena en:
# macOS/Linux: ~/.gitconfig
# Windows: C:\Users\YourName\.gitconfig
```

**Niveles de Configuración:**

| Nivel | Alcance | Flag |
|-------|-------|------|
| `--system` | Todos los usuarios de la computadora | Rara vez usado |
| `--global` | Tu cuenta de usuario | El más común |
| `--local` | Repositorio específico | Específico del proyecto |

---

## 6. git init

**Inicializar un Repositorio Git:**

```bash
# Crear el directorio del proyecto
mkdir hello-git
cd hello-git

# Inicializar Git
git init

# Resultado: Crea la carpeta oculta .git/
```

**Qué Pasa:**

1. Crea el directorio `.git/` (oculto)
2. El repositorio ya está listo para rastrear
3. Crea la rama inicial (Master/Main)

**Conceptos Importantes:**

- **Repositorio**: Carpeta del proyecto gestionada por Git
- **Carpeta oculta .git**: Contiene todos los datos de Git
- **Nunca elimines .git**: Perderás todo el historial

#### Renombrar la Rama por Defecto

La práctica moderna usa "main" en lugar de "master":

```bash
# Renombrar master a main
git branch -m main

# O configurar el valor por defecto para nuevos repos
git config --global init.defaultBranch main
```

---

## 7. Ramas en Git

**Concepto de Rama:**

Una rama es una línea de desarrollo independiente, como un universo paralelo para tu código.

**Rama por Defecto:**
- Tradicionalmente: `master`
- Estándar moderno: `main`

**Por Qué Usar Ramas:**

✅ Desarrollar funcionalidades de forma aislada
✅ Mantener el código principal estable
✅ Probar sin romper producción
✅ Que varias personas trabajen simultáneamente
✅ Experimentar con seguridad

**Visualización de Ramas:**

```
main:     A---B---C---D
               \
login:          E---F---G
```

---

## 8. git add y git commit

**Áreas del Flujo de Trabajo de Git:**

1. **Directorio de Trabajo (Working Directory)**: Donde editas los archivos
2. **Área de Staging (Staging Area)**: Archivos listos para commitear
3. **Repositorio (Repository)**: Instantáneas commiteadas

#### Añadir Archivos al Staging

```bash
# Añadir un archivo específico
git add hello-git.py

# Añadir todos los archivos
git add .

# Añadir varios archivos
git add file1.py file2.py
```

#### Commitear Cambios

```bash
# Commitear con un mensaje
git commit -m "Este es mi primer commit"

# Commitear con un mensaje multilínea (abre el editor)
git commit

# Commitear con un mensaje en línea
git commit -m "$(cat <<'EOF'
Add new feature

This commit implements the login functionality
with proper error handling.
EOF
)"
```

**Buenas Prácticas de Commit:**

✅ Escribe mensajes claros y descriptivos
✅ Usa el tiempo presente ("Add feature" no "Added")
✅ Empieza con un verbo (Add, Fix, Update, Remove)
✅ Mantén la primera línea por debajo de 50 caracteres
✅ Añade detalles en las líneas siguientes si es necesario

**Ejemplos de Mensajes de Commit:**

```bash
# Bien
git commit -m "Add user authentication"
git commit -m "Fix login validation bug"
git commit -m "Update README with installation steps"

# Mal
git commit -m "changes"
git commit -m "stuff"
git commit -m "asdf"
```

---

## 9. git log y git status

#### git status

Muestra el estado actual del directorio de trabajo y el área de staging.

```bash
# Comprobar el estado
git status

# Estado corto (más compacto)
git status -s

# Ejemplo de salida:
# On branch main
# Changes not staged for commit:
#   modified:   hello-git.py
#
# Untracked files:
#   hello-git2.py
```

**Estados del Status:**

- **Untracked**: Archivos nuevos que Git no conoce
- **Modified**: Archivos cambiados que no están en staging
- **Staged**: Archivos listos para commitear
- **Committed**: Guardados en el repositorio

**Símbolos del Status Corto:**

```bash
# Salida de git status -s:
M  file.txt    # Modificado y en staging
 M file2.txt   # Modificado pero no en staging
A  file3.txt   # Añadido (archivo nuevo en staging)
?? file4.txt   # Sin rastrear (untracked)
```

#### git log

Muestra el historial de commits.

```bash
# Log completo
git log

# Log compacto (una línea por commit) - RECOMENDADO
git log --oneline

# Log gráfico
git log --graph

# Log bonito con decoraciones
git log --graph --oneline --decorate --all
```

**Por Qué `--oneline` es Mejor:**

El `git log` por defecto muestra demasiada información y usa un paginador que requiere:
- Barra espaciadora para desplazarse
- 'q' para salir

El formato `--oneline` muestra:
- Hash del commit (corto)
- Mensaje del commit
- Tags y ramas
- Todo en una línea por commit

**Ejemplo de Salida del Log:**

```bash
# git log --oneline
cd7110a (HEAD -> main, tag: clase-1) Se actualiza el texto
1369f8a Se añade .gitignore
2a3b4c5 Este es mi segundo commit
9d8e7f6 Este es mi primer commit
```

**Entendiendo el Log:**
- **Hash**: ID único del commit (cd7110a) - identificador de cada commit
- **HEAD**: Posición actual (dónde estás ahora)
- **Author**: Quién hizo el commit
- **Date**: Cuándo se hizo el commit
- **Message**: Descripción del commit

**Por Qué el Hash es Importante:**

Cada commit tiene un hash único que sirve como su identificador. Esto es crítico porque:
- ✅ Puedes referenciar commits específicos
- ✅ Navegar a cualquier punto del historial
- ✅ Hacer cherry-pick de cambios específicos
- ✅ Revertir a versiones anteriores
- ✅ Depurar y encontrar cuándo se introdujeron bugs

**Navegación:**

```bash
# Salir del visor del log (si estás en modo paginador)
q

# ¡Por esto se prefiere --oneline!
# No se necesita paginador para un historial razonable
```

---

## 10. git checkout y git reset

**Moverse Entre Commits:**

#### git checkout

Navegar a commits o ramas específicas.

```bash
# Ir a un commit específico
git checkout abc123

# Descartar los cambios de un archivo
git checkout hello-git.py

# Volver al último commit
git checkout main
```

#### git reset

Deshacer cambios y mover HEAD.

```bash
# Sacar un archivo del staging (mantiene los cambios)
git reset hello-git.py

# Ir a un commit específico (mantiene los cambios)
git reset abc123

# Descartar todos los cambios (PELIGROSO)
git reset --hard abc123
```

**Diferencias Clave:**

| Comando | Propósito | Seguridad |
|---------|---------|--------|
| `checkout` | Navegar, temporal | Seguro |
| `reset` | Deshacer, permanente | Usar con cuidado |
| `reset --hard` | Eliminar todo | PELIGROSO |

**⚠️ Advertencia:**
`git reset --hard` ¡elimina permanentemente el trabajo no commiteado!

---

## 11. git alias

**Crear Atajos:**

Los alias ahorran escritura para comandos comunes.

#### Crear un Alias

```bash
# Crear el alias "tree" para un log bonito
git config --global alias.tree "log --graph --decorate --all --oneline"

# Ahora úsalo
git tree
```

#### Alias Comunes Útiles

```bash
# Atajo de status
git config --global alias.s "status"

# Log compacto
git config --global alias.lg "log --oneline --graph"

# Último commit
git config --global alias.last "log -1 HEAD"

# Sacar archivos del staging
git config --global alias.unstage "reset HEAD --"
```

#### Ver Todos los Alias

```bash
# En el archivo de configuración
cat ~/.gitconfig

# Ejemplo de salida:
[alias]
    tree = log --graph --decorate --all --oneline
    s = status
    lg = log --oneline --graph
```

---

## 12. Archivo .gitignore

**Ignorar Archivos:**

`.gitignore` le dice a Git qué archivos no rastrear nunca.

#### Crear .gitignore

```bash
# Crear el archivo
touch .gitignore

# O desde el editor
code .gitignore
```

#### Sintaxis de .gitignore

```bash
# Ignorar un archivo específico
.DS_Store

# Ignorar todos los archivos con una extensión
*.log
*.tmp

# Ignorar un directorio
node_modules/
.env

# Ignorar archivos en cualquier directorio
**/*.pyc

# Negar un patrón (rastrear este archivo)
!important.log
```

#### Patrones Comunes de .gitignore

```bash
# macOS
.DS_Store
.AppleDouble

# Windows
Thumbs.db
desktop.ini

# Node.js
node_modules/
npm-debug.log

# Python
__pycache__/
*.pyc
*.pyo
.env

# IDEs
.vscode/
.idea/
*.swp

# Salidas de build
dist/
build/
*.exe
```

**Notas Importantes:**

- Debe llamarse exactamente `.gitignore`
- Colócalo en la raíz del repositorio
- Commitea el propio archivo .gitignore
- Los archivos ya rastreados no serán ignorados (primero hay que dejar de rastrearlos)

---

## 13. git diff

**Ver Cambios:**

`git diff` muestra las diferencias entre versiones.

```bash
# Ver los cambios sin stage (directorio de trabajo vs staging)
git diff

# Ver los cambios en staging (staging vs último commit)
git diff --staged
# o
git diff --cached

# Comparar ramas
git diff main login

# Comparar commits
git diff abc123 def456

# Comparar un archivo específico
git diff hello-git.py
```

**Entendiendo las Tres Áreas:**

```
Directorio de Trabajo  →  Área de Staging  →  Repositorio (.git)
     (editar)          →   (git add)       →   (git commit)
```

**Casos de Uso de Diff:**

```bash
# 1. Ver qué cambió pero AÚN NO está en staging
git diff
# Muestra: Directorio de Trabajo vs Área de Staging

# 2. Ver qué SE VA A commitear (lo que está en staging)
git diff --staged
# Muestra: Área de Staging vs Último Commit
# ¡Esto es MUY ÚTIL antes de commitear!

# 3. Ver TODOS los cambios (staging + sin stage)
git diff HEAD
# Muestra: Directorio de Trabajo vs Último Commit
```

**Ejemplo Práctico:**

```bash
# 1. Editar el archivo
echo "New line" >> file.txt

# 2. Comprobar los cambios (aún no en staging)
git diff
# Muestra tus ediciones

# 3. Poner algunos cambios en staging
git add file.txt

# 4. ¡Ahora git diff no muestra nada!
git diff
# (vacío - nada sin stage)

# 5. Pero los cambios en staging son visibles con:
git diff --staged
# Muestra lo que se va a commitear

# 6. Editar el archivo de nuevo
echo "Another line" >> file.txt

# 7. Ahora tienes cambios TANTO en staging como sin stage
git diff           # Muestra "Another line" (sin stage)
git diff --staged  # Muestra "New line" (en staging)
```

**Leyendo la Salida de Diff:**

```diff
diff --git a/hello-git.py b/hello-git.py
index 1234567..abcdefg 100644
--- a/hello-git.py
+++ b/hello-git.py
@@ -1,1 +1,1 @@
-print("Hello Git")
+print("New Hello Git with changes")
```

**Entendiendo los Símbolos:**
- **-** (rojo): Línea eliminada
- **+** (verde): Línea añadida
- **@@**: Números de línea
- **---**: Archivo original
- **+++**: Archivo modificado

**Consejo Pro:**

¡Ejecuta siempre `git diff --staged` ANTES de commitear para revisar exactamente lo que estás a punto de commitear!

```bash
# Buen flujo de trabajo
git add .
git diff --staged    # Revisar los cambios
git commit -m "Message"
```

---

## 14. Moverse Entre Commits

**Navegar el Historial del Repositorio:**

```bash
# Ver el historial de commits
git log --oneline

# Ejemplo de salida:
# cd7110a (HEAD -> main) Se actualiza el texto
# 1369f8a Se añade .gitignore
# 2a3b4c5 Este es mi segundo commit
# 9d8e7f6 Este es mi primer commit

# Ir a un commit específico
git checkout 9d8e7f6

# Los archivos vuelven a ese estado
ls  # Muestra los archivos como estaban

# Volver al presente
git checkout main
```

**Concepto de HEAD:**

`HEAD` es un puntero a tu posición actual:
- Normalmente apunta al último commit de una rama
- Puede apuntar a cualquier commit (HEAD desprendido / detached HEAD)
- Se mueve cuando commiteas o haces checkout

---

## 15. git reset --hard y git reflog

**Reset Duro:**

Elimina commits de forma permanente (usar con extrema precaución).

```bash
# PELIGRO: Elimina todos los commits después de abc123
git reset --hard abc123

# Los archivos y commits desaparecen
git log  # Muestra solo los commits hasta abc123
```

**Recuperar Commits Perdidos:**

`git reflog` muestra TODAS las acciones, incluso los commits eliminados.

```bash
# Ver el historial completo
git reflog

# Ejemplo de salida:
# abc123 HEAD@{0}: reset: moving to abc123
# def456 HEAD@{1}: commit: Se actualiza texto
# cd7110 HEAD@{2}: commit: Se añade .gitignore

# Recuperar el commit eliminado
git reset --hard def456

# ¡Los archivos han vuelto!
git log  # Muestra todos los commits de nuevo
```

**Importante:**

✅ Es casi imposible perder commits
✅ `reflog` guarda el historial por ~90 días
✅ Usa `reset --hard` solo cuando estés seguro
⚠️ No lo uses en commits ya enviados (rompe el historial del equipo)

---

## 16. git tag

**Etiquetar Commits:**

Los tags marcan puntos importantes (releases, versiones).

```bash
# Crear un tag en el commit actual
git tag clase-1

# Crear un tag en un commit específico
git tag v1.0 abc123

# Listar todos los tags
git tag

# Ver los commits etiquetados en el log
git log --oneline
# Salida: cd7110a (HEAD -> main, tag: clase-1) Commit message
```

**Buenas Prácticas de Tags:**

```bash
# Versionado semántico
git tag v1.0.0    # Release mayor
git tag v1.1.0    # Actualización menor
git tag v1.1.1    # Parche/corrección de bug

# Tags descriptivos
git tag clase-1
git tag release-2024-02-10
git tag beta-testing
```

**Navegar a Tags:**

```bash
# Saltar a un commit etiquetado
git checkout tags/clase-1

# Volver a la rama
git checkout main
```

**Por Qué Usar Tags:**

✅ Marcar releases (v1.0, v2.0)
✅ Referenciar hitos importantes
✅ Navegación fácil a puntos clave
✅ Desplegar versiones específicas

---

## 17. git branch y git switch

**Entendiendo el Desarrollo Lineal vs con Ramas:**

**Flujo Lineal (Sin Ramas):**

```
A ← B ← C ← D ← E
```

Todos trabajan en la misma línea. Problemas:
- ❌ Conflictos cuando trabajan varios desarrolladores
- ❌ Las funcionalidades sin terminar rompen producción
- ❌ No se puede trabajar de forma independiente
- ❌ Difícil probar funcionalidades de forma aislada

**Flujo con Ramas (Con Ramas):**

```
main:     A ← B ← C ───────────← F (merge)
              ↓                   ↗
feature:      D ← E (trabajo independiente)
```

Beneficios:
- ✅ Trabajar de forma independiente sin conflictos
- ✅ Mantener la rama main estable
- ✅ Probar funcionalidades de forma aislada
- ✅ Múltiples desarrolladores, múltiples funcionalidades
- ✅ Fácil descartar experimentos fallidos
- ✅ Fusionar solo cuando la funcionalidad esté completa

**Escenario del Mundo Real:**

```
Imagina esta línea de tiempo sin ramas:
- El Desarrollador 1 empieza la función de login (rompe los tests)
- El Desarrollador 2 necesita arreglar un bug urgente (no puede porque los tests están rotos)
- El Desarrollador 3 quiere añadir una nueva función (el código es inestable)

Con ramas:
- El Desarrollador 1 trabaja en la rama 'feature/login'
- El Desarrollador 2 arregla el bug en la rama 'hotfix/security' desde una main estable
- El Desarrollador 3 crea la rama 'feature/dashboard'
- Cada uno trabaja de forma independiente, fusionan cuando están listos
```

**Crear y Cambiar de Rama:**

#### Crear una Rama

```bash
# Crear una nueva rama
git branch login

# Listar ramas
git branch

# Salida:
# * main
#   login
```

#### Cambiar de Rama

```bash
# Cambiar a una rama (forma moderna)
git switch login

# Cambiar a una rama (forma antigua, aún funciona)
git checkout login

# Crear y cambiar en un solo comando
git switch -c new-feature
git checkout -b new-feature  # Sintaxis antigua
```

**Convenciones de Nombrado de Ramas:**

```bash
# Buenos nombres (descriptivos, organizados)
feature/user-authentication
bugfix/login-validation
hotfix/security-patch
release/v1.2.0
feat/SS-4515  # Usando números de ticket

# Evitar (poco claros, inútiles)
branch1
test
stuff
my-branch
```

**Trabajando con Ramas:**

```bash
# Ver la rama actual
git branch
# Salida: * login  (el asterisco muestra la actual)

# Ver todas las ramas con su último commit
git branch -v

# Ver las ramas fusionadas
git branch --merged

# Ver las ramas no fusionadas
git branch --no-merged
```

**Cómo las Ramas Aíslan el Trabajo:**

```bash
# Crear una rama y hacer cambios
git switch -c feature-b
echo "New feature" > file.txt
git add file.txt
git commit -m "Add feature B"

# Volver a main
git switch main
cat file.txt
# El archivo no tiene "New feature" - ¡versión distinta!

# Volver a la rama
git switch feature-b
cat file.txt
# El archivo tiene "New feature" - ¡cambios preservados!
```

**Ejemplo Visual:**

```
# Estás en main
main (HEAD) → archivo1.txt contiene "Hello"

# Crear y cambiar a la rama feature
git switch -c feature-branch

# Editar el archivo
feature-branch (HEAD) → archivo1.txt ahora contiene "Hello\nWorld"

# Volver a main
main (HEAD) → archivo1.txt aún contiene solo "Hello"

# ¡Los cambios existen en universos paralelos hasta que se fusionan!
```

---

## 18. git merge

**Combinar Ramas:**

El merge trae los cambios de una rama a otra.

```bash
# Cambiar a la rama receptora
git switch main

# Fusionar la otra rama en la actual
git merge login

# Resultado: los cambios de login ahora están en main
```

**Tipos de Merge:**

**1. Merge Fast-Forward:**
```bash
# Cuando no hay commits en main desde que se creó la rama
git merge login
# Salida: Fast-forward
```

**2. Merge de Tres Vías (Three-Way):**
```bash
# Cuando ambas ramas tienen nuevos commits
git merge login
# Crea un commit de merge
```

**Flujo de Trabajo de Merge:**

```bash
# 1. Comprobar el estado de la rama
git switch main
git log --oneline

# 2. Previsualizar el merge
git diff main login

# 3. Realizar el merge
git merge login

# 4. Verificar el merge
git log --graph --oneline
```

**Representación Visual:**

```
Antes del merge:
main:     A---B---C
               \
login:          D---E

Después del merge:
main:     A---B---C---F (commit de merge)
               \       /
login:          D---E
```

---

## 19. Resolución de Conflictos

**Cuando los Merges Fallan:**

Los conflictos ocurren cuando las mismas líneas se modifican en ambas ramas.

#### Ejemplo de Conflicto

```bash
# Intentar fusionar
git merge login

# Salida:
# CONFLICT (content): Merge conflict in hello-git.py
# Automatic merge failed; fix conflicts and then commit
```

#### Marcadores de Conflicto en el Archivo

```python
<<<<<<< HEAD
print("Hello Git v3")
=======
print("Hello Git V login")
>>>>>>> login
```

**Entendiendo los Marcadores:**
- `<<<<<<< HEAD`: Los cambios de tu rama actual
- `=======`: Separador
- `>>>>>>> login`: Los cambios de la rama entrante

#### Resolver el Conflicto

```bash
# 1. Abrir el archivo en conflicto
code hello-git.py

# 2. Elegir qué versión conservar
# Eliminar los marcadores de conflicto
# Conservar el código deseado

# 3. Poner el archivo resuelto en staging
git add hello-git.py

# 4. Completar el merge
git commit -m "Resolve merge conflict"

# 5. Verificar
git status
```

**Estrategias de Resolución:**

**Conservar los tuyos:**
```python
print("Hello Git v3")
```

**Conservar los de ellos:**
```python
print("Hello Git V login")
```

**Combinar ambos:**
```python
print("Hello Git v3")
print("Hello Git V login")
```

**Escribir una nueva solución:**
```python
print("Hello Git - Merged Version")
```

**Prevención de Conflictos:**

✅ Comunícate con el equipo
✅ Sincroniza las ramas con frecuencia
✅ Trabaja en archivos distintos
✅ Fusiona a menudo (cambios pequeños)
⚠️ No modifiques las mismas líneas

---

## 20. git stash

**Almacenamiento Temporal:**

Stash guarda el trabajo en progreso sin commitear.

```bash
# Guardar los cambios actuales
git stash

# O con un mensaje
git stash save "Work in progress on login"

# Cambiar de rama de forma segura
git switch main

# Hacer trabajo...

# Volver a la rama original
git switch login

# Restaurar los cambios guardados
git stash pop
```

**Comandos de Stash:**

```bash
# Listar los stashes
git stash list

# Salida:
# stash@{0}: WIP on login: abc123 Login v2
# stash@{1}: WIP on main: def456 Update text

# Aplicar un stash sin eliminarlo
git stash apply

# Aplicar un stash específico
git stash apply stash@{1}

# Eliminar un stash
git stash drop

# Eliminar todos los stashes
git stash clear
```

**Casos de Uso:**

✅ Corrección de bug de emergencia en otra rama
✅ Traer los últimos cambios antes de commitear
✅ Cambiar de contexto rápidamente
✅ Experimentar sin commitear

**Ejemplo de Flujo de Trabajo:**

```bash
# Trabajando en una función
code login.py

# ¡Emergencia! Bug en producción
git stash

# Arreglar el bug
git switch main
# Arreglar y commitear

# Retomar el trabajo de la función
git switch login
git stash pop
```

---

## 21. Reintegración de Ramas

**Completar una Función:**

Cuando la función está lista, fusiónala de vuelta a main.

```bash
# Función completa en la rama login
git switch login
git log --oneline

# Fusionar a main
git switch main
git merge login

# Resultado: la función ya está en producción
```

**Flujo de Reintegración:**

```bash
# 1. Terminar la función
git switch login
git add .
git commit -m "Complete login feature"

# 2. Actualizar desde main
git switch main
git pull  # Si trabajas con un remoto

# 3. Probar la rama de la función
git switch login
git merge main  # Obtener los últimos cambios de main

# 4. Resolver conflictos si los hay
# Arreglar conflictos
git add .
git commit -m "Resolve conflicts"

# 5. Fusionar a main
git switch main
git merge login

# 6. Limpiar
git branch -d login  # Eliminar la rama
```

---

## 22. Eliminar Ramas

**Eliminar Ramas Completadas:**

```bash
# Eliminar una rama fusionada
git branch -d login

# Forzar la eliminación de una rama no fusionada (PELIGROSO)
git branch -D login

# Listar las ramas restantes
git branch
```

**Por Qué Eliminar Ramas:**

✅ Mantener el repositorio limpio
✅ Eliminar funcionalidades completadas
✅ Evitar confusión
✅ Navegación más fácil

**Notas Importantes:**

- Elimina solo ramas fusionadas
- Las ramas de funcionalidad son temporales
- La rama main nunca debe eliminarse
- Se puede recuperar desde reflog si es necesario

**Ciclo de Vida de una Rama:**

```
1. Crear:   git branch feature
2. Trabajar: git switch feature
3. Commitear: git commit -m "Add feature"
4. Fusionar: git merge feature (desde main)
5. Eliminar: git branch -d feature
```

---

## 23. Introducción a GitHub

**Git vs GitHub:**

| Git | GitHub |
|-----|--------|
| Software de control de versiones | Plataforma de alojamiento en la nube |
| Funciona localmente | Funciona de forma remota |
| Línea de comandos | Interfaz web |
| Gratis, de código abierto | Niveles gratuitos + de pago |
| Desde 2005 | Desde 2008 (comprado por Microsoft en 2018) |

**Por Qué GitHub:**

✅ Respaldar el código en la nube
✅ Colaborar con equipos
✅ Compartir proyectos de código abierto
✅ Portafolio para desarrolladores
✅ Integrar con herramientas (CI/CD)
✅ Documentación y wikis

**Estadísticas de GitHub:**

- **94 millones de desarrolladores** en todo el mundo
- El **90% de las empresas Fortune 500** lo usan
- **Más de 100 millones de repositorios**
- Los más populares: proyectos de JavaScript, Python, Java

**Funciones Clave:**

- **Repositorios**: Almacenar proyectos
- **Issues**: Rastrear bugs y tareas
- **Pull Requests**: Proponer cambios
- **Actions**: Automatizar flujos de trabajo
- **Pages**: Alojar sitios web
- **Projects**: Organizar el trabajo

---

## 24. Primeros Pasos en GitHub

**Crear una Cuenta:**

1. Ve a [github.com](https://github.com)
2. Haz clic en "Sign up"
3. Introduce correo, contraseña, nombre de usuario
4. Verifica el correo
5. Completa el perfil

**Configuración del Perfil:**

```bash
# Añade información del perfil:
- Foto de perfil
- Descripción (bio)
- Ubicación
- Sitio web
- Enlaces de Twitter/redes sociales
```

**Crear un Perfil README:**

El repositorio especial `username/username` se muestra en el perfil.

```bash
# 1. Crea un repositorio con tu nombre de usuario
# Ejemplo: tu-usuario/tu-usuario

# 2. Añade un README.md
# Esto se muestra en la página de tu perfil

# 3. Escribe el contenido del perfil
# Usa Markdown para el formato
```

**Ejemplo de README.md:**

```markdown
# Hi, I'm Your Name 👋

## 🚀 About Me
Full Stack Developer | DevSecOps

## 🛠️ Technologies
- Python, TypeScript
- React, Node.js, NestJS
- Git, Docker, Kubernetes

## 📫 Contact
- Website: example.com
- LinkedIn: linkedin.com/in/your-handle
```

---

## 25. Local y Remoto

**Entendiendo el Remoto:**

**Repositorio Local:**
- Tu computadora
- Todos los commits, ramas
- Trabajar sin conexión

**Repositorio Remoto:**
- Servidor de GitHub
- Compartido con el equipo
- Backup y colaboración

**Flujo de Conexión:**

```
Tu Computadora          →  Push   →    GitHub
(Repositorio Local)                 (Repositorio Remoto)

Tu Computadora          ←  Pull    ←    GitHub
(Repositorio Local)                 (Repositorio Remoto)
```

**Por Qué el Remoto:**

✅ Respaldar el código de forma segura
✅ Compartir con el equipo
✅ Acceder desde cualquier lugar
✅ Colaborar fácilmente
✅ Desplegar a producción

---

## 26. Autenticación SSH

**Configurar Claves SSH:**

SSH proporciona autenticación segura sin contraseñas.

#### Generar una Clave SSH

```bash
# Crear una clave SSH
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"

# Ubicación de guardado (presiona Enter para el valor por defecto)
# Enter file: /Users/username/.ssh/id_rsa

# Establecer una passphrase (o dejar vacío)
# Enter passphrase: [presiona Enter]
```

#### Añadir al Agente SSH

```bash
# Iniciar ssh-agent
eval "$(ssh-agent -s)"

# Añadir la clave al agente
ssh-add ~/.ssh/id_rsa
```

#### Añadir a GitHub

```bash
# 1. Copiar la clave pública
cat ~/.ssh/id_rsa.pub
# Copiar la salida

# 2. GitHub → Settings → SSH and GPG keys
# 3. New SSH key
# 4. Pegar la clave
# 5. Add SSH key
```

#### Probar la Conexión

```bash
# Probar la conexión SSH
ssh -T git@github.com

# Salida de éxito:
# Hi username! You've successfully authenticated
```

**Archivos de Clave SSH:**

```bash
~/.ssh/
  ├── id_rsa        # Clave privada (NUNCA compartir)
  ├── id_rsa.pub    # Clave pública (añadir a GitHub)
  └── config        # Configuración de SSH
```

---

## 27. git remote

**Conectar Local con Remoto:**

```bash
# Añadir un repositorio remoto
git remote add origin git@github.com:username/repo.git

# Ver los remotos
git remote -v

# Salida:
# origin  git@github.com:username/repo.git (fetch)
# origin  git@github.com:username/repo.git (push)

# Cambiar la URL del remoto
git remote set-url origin new-url

# Eliminar un remoto
git remote remove origin

# Renombrar un remoto
git remote rename origin upstream
```

**Origin:**

`origin` es el nombre por defecto del repositorio remoto principal.

---

## 28. git fetch y git pull

**Obtener Cambios Remotos:**

#### git fetch

Descarga los cambios SIN fusionar.

```bash
# Traer desde el remoto
git fetch origin

# Comprobar qué hay de nuevo
git log origin/main

# Fusionar manualmente si se desea
git merge origin/main
```

#### git pull

Descarga y fusiona en un solo paso.

```bash
# Pull = fetch + merge
git pull origin main

# O si la rama de seguimiento está configurada
git pull
```

**Diferencia:**

| Comando | Fetch | Merge | Seguridad |
|---------|-------|-------|--------|
| `fetch` | ✅ | ❌ | Seguro |
| `pull` | ✅ | ✅ | Puede haber conflictos |

**Buena Práctica:**

```bash
# Flujo más seguro
git fetch origin
git log origin/main
git merge origin/main

# Flujo rápido
git pull origin main
```

---

## 29. git clone

**Descargar un Repositorio:**

```bash
# Clonar un repositorio
git clone git@github.com:username/repo.git

# Clonar en una carpeta específica
git clone git@github.com:username/repo.git my-folder

# Clonar una rama específica
git clone -b develop git@github.com:username/repo.git
```

**Qué Hace el Clone:**

1. Crea el directorio
2. Inicializa Git
3. Descarga todos los archivos
4. Configura el remoto (origin)
5. Hace checkout de la rama por defecto

---

## 30. git push

**Subir al Remoto:**

```bash
# Enviar al remoto
git push origin main

# Enviar y establecer el upstream
git push -u origin main

# Enviar todas las ramas
git push --all

# Enviar los tags
git push --tags
```

**Primer Push:**

```bash
# Establecer el upstream y enviar
git push -u origin main

# Pushes futuros
git push  # Usa automáticamente el upstream
```

#### Autenticación con Personal Access Token (PAT)

**Al Usar HTTPS (No Recomendado):**

Si no has configurado SSH, GitHub solicitará autenticación. NO puedes usar tu contraseña de GitHub directamente - debes usar un Personal Access Token.

**Creando un Personal Access Token:**

1. **Ve a Settings**
   ```
   GitHub → Haz clic en tu foto de perfil → Settings
   ```

2. **Developer Settings**
   ```
   Baja hasta el final → Developer settings
   ```

3. **Personal Access Tokens**
   ```
   Personal access tokens → Tokens (classic)
   ```

4. **Generate New Token**
   ```
   Generate new token → Generate new token (classic)
   ```

5. **Configurar el Token**
   ```
   Note: Dale un nombre (p. ej. "my-macbook", "work-laptop")
   Expiration: Elige la duración (30 días, 90 días, 1 año, sin expiración)
   Scopes: Selecciona "repo" (otorga acceso total al repositorio)
   ```

6. **Generar y Copiar**
   ```
   Generate token
   Copia el token inmediatamente (¡no lo verás de nuevo!)
   ```

**Usando el Token:**

```bash
# Cuando se solicite la contraseña, pega tu token
Username for 'https://github.com': your-username
Password for 'https://your-username@github.com': [paste-token-here]
```

**⚠️ Notas Importantes:**

- Los tokens reemplazan las contraseñas al usar HTTPS
- Almacena los tokens de forma segura (gestor de contraseñas)
- Nunca commitees tokens a los repositorios
- Los tokens se pueden revocar en cualquier momento
- Se recomienda SSH sobre HTTPS + tokens

**Scopes del Token (Qué Seleccionar):**

| Scope | Propósito |
|-------|---------|
| `repo` | Acceso total al repositorio (el más común) |
| `workflow` | Actualizar workflows de GitHub Actions |
| `write:packages` | Subir paquetes |
| `delete_repo` | Eliminar repositorios |
| `admin:org` | Gestión de organizaciones |

**Recomendado: Usa SSH en su Lugar**

```bash
# SSH es más conveniente y seguro
# Ver la Sección 26 para la configuración de SSH
# ¡No se necesitan tokens con SSH!
```

---

## 31. Fork en GitHub

**Hacer Fork de un Repositorio:**

Copia el repositorio de otra persona a tu cuenta.

**Pasos:**

1. Ve al repositorio en GitHub
2. Haz clic en el botón "Fork"
3. El fork aparece en tu cuenta
4. Clona tu fork
5. Haz cambios
6. Crea un Pull Request

---

## 32. Pull Requests (PR)

**Proponer Cambios:**

Pull Request = "Por favor, fusiona mis cambios"

**Flujo de Trabajo de PR:**

1. Hacer fork del repositorio
2. Crear una rama
3. Hacer cambios
4. Enviar a tu fork
5. Abrir un Pull Request
6. Revisión de código
7. Fusionar o rechazar

---

## 33. GitHub Flow

**Flujo de Trabajo Estándar:**

```
1. rama main (producción)
2. Crear una rama de funcionalidad
3. Commitear los cambios
4. Abrir un Pull Request
5. Revisar el código
6. Fusionar a main
7. Desplegar
```

---

## 34. git cherry-pick y git rebase

**Operaciones Avanzadas:**

```bash
# Cherry-pick de un commit específico
git cherry-pick abc123

# Rebase de una rama
git rebase main
```

---

## 35. GitHub Pages

**GitHub Pages:**

GitHub Pages te permite alojar sitios web estáticos directamente desde tu repositorio de forma gratuita.

**Casos de Uso:**
- Sitios web de portafolio personal
- Documentación de proyectos
- Alojamiento de blogs
- Landing pages

**Cómo Habilitarlo:**

1. Ve a Settings del repositorio
2. Baja a la sección "Pages"
3. Selecciona la rama de origen (normalmente `main` o `gh-pages`)
4. Elige la carpeta (`/` o `/docs`)
5. Haz clic en Save

**Tu sitio estará disponible en:**
```
https://username.github.io/repository-name
```

**Dominios Personalizados:**

Puedes usar dominios personalizados:
1. Añade un archivo `CNAME` al repositorio con tu dominio
2. Configura los registros DNS en tu proveedor de dominios
3. Habilita HTTPS en la configuración de Pages

---

## Parte 2: GitHub Actions - Automatización de CI/CD

---

## 36. Introducción a GitHub Actions

**¿Qué es GitHub Actions?**

GitHub Actions es una potente plataforma de **CI/CD (Integración Continua / Despliegue Continuo)** que te permite automatizar tus flujos de trabajo de desarrollo de software directamente en GitHub.

**Funciones Clave:**

✅ **Automatización**: Construir, probar y desplegar código automáticamente
✅ **Nivel gratuito**: Uso gratuito generoso para repos públicos y privados
✅ **Integrado**: Incorporado en GitHub, no se necesitan herramientas externas
✅ **Seguro**: Se ejecuta en entornos aislados
✅ **Marketplace**: Miles de actions prefabricadas disponibles
✅ **Multi-plataforma**: Soporta runners de Linux, macOS, Windows
✅ **Multi-lenguaje**: Node.js, Python, Java, Ruby, PHP, Go, Rust, .NET y más

**¿Por Qué Usar GitHub Actions?**

Deja de hacer tareas manuales y automatiza:
- **Construir proyectos**: Compilar código automáticamente
- **Ejecutar tests**: Ejecutar las suites de tests en cada commit
- **Desplegar aplicaciones**: Publicar en servidores de producción
- **Comprobaciones de calidad de código**: Linting, formateo, escaneos de seguridad
- **Generar documentación**: Auto-actualizar la documentación
- **Publicar paquetes**: Publicar en npm, PyPI, Docker Hub, etc.

**Beneficios del Mundo Real:**

```
Antes de GitHub Actions:
1. Escribir código
2. Ejecutar los tests manualmente en local
3. Construir el proyecto manualmente
4. Desplegar al servidor manualmente
5. Esperar que nada se rompa
⏱️  Tiempo: 30-60 minutos

Con GitHub Actions:
1. Escribir código
2. Hacer push a GitHub
3. ☕ Tomar un café mientras Actions se encarga de todo
⏱️  Tiempo: 2 minutos de tu tiempo
```

**Ejemplo de Integración:**

Imagina que haces push de código a GitHub:
```bash
git push origin main
```

GitHub Actions puede automáticamente:
1. Ejecutar todos los tests
2. Comprobar la calidad del código
3. Construir la versión de producción
4. Desplegar al servidor
5. Enviar una notificación a Slack/Discord
6. Actualizar la documentación

¡Todo sin que muevas un dedo!

---

## 37. Precios de GitHub Actions

**Resumen de Precios:**

GitHub Actions es **GRATIS** para repositorios públicos con uso ilimitado.

**Para Repositorios Privados:**

| Plan | Costo Mensual | Minutos Incluidos | Almacenamiento |
|------|--------------|------------------|---------|
| **Free** | $0 | 2,000 minutos | 500 MB |
| **Pro** | $4/usuario | 3,000 minutos | 2 GB |
| **Team** | $4/usuario | 3,000 minutos | 2 GB |
| **Enterprise** | Personalizado | 50,000 minutos | 50 GB |

**Datos Importantes:**

✅ **Repos públicos**: Uso gratuito ilimitado para siempre
✅ **2,000 minutos** = más de 33 horas de automatización al mes (plan Free)
✅ **Muy generoso**: Difícil exceder los límites en proyectos personales
⚠️ Solo se cobra si excedes el límite

**Multiplicadores de Minutos por SO:**

Los distintos sistemas operativos consumen minutos de forma diferente:

| SO | Multiplicador | Minutos Reales por Minuto Facturado |
|----|------------|----------------------------------|
| **Linux** | 1x | 1 minuto = 1 minuto |
| **Windows** | 2x | 1 minuto = 2 minutos facturados |
| **macOS** | 10x | 1 minuto = 10 minutos facturados |

**Costo por Minuto (si se excede):**

| SO | Costo por Minuto |
|----|-----------------|
| Linux (2 CPU) | $0.008 |
| Windows (2 CPU) | $0.016 |
| macOS (3 CPU) | $0.08 |

**Recomendación:**

✅ Usa runners de **Linux (Ubuntu)** - los más baratos y comunes
✅ Usa **macOS** solo cuando sea absolutamente necesario (builds de iOS)
⚠️ Monitorea el uso en Settings → Billing

**Ejemplo de Uso Mensual:**

```bash
# Proyecto pequeño típico:
- 30 commits/mes
- 3 minutos por ejecución de workflow
- Total: 90 minutos/mes

# Tienes 2,000 minutos GRATIS
# Estás usando: 4.5% de tu cuota
# ¡Sin cargo!
```

---

## 38. Conceptos Fundamentales: Workflows, Jobs, Steps

**Arquitectura de GitHub Actions:**

```
Workflow (automatización completa)
  └── Jobs (tareas paralelas o secuenciales)
       └── Steps (acciones individuales)
            └── Actions (comandos reutilizables)
```

### 1. Workflow

Un **workflow** es un proceso automatizado definido en un archivo YAML.

**Características:**
- Se almacena en el directorio `.github/workflows/`
- Se dispara por eventos (push, PR, schedule, etc.)
- Puede contener uno o más jobs
- Cada repositorio puede tener varios workflows

**Ejemplo:**
```yaml
# File: .github/workflows/ci.yml
name: CI Pipeline
```

### 2. Jobs

Un **job** es un conjunto de steps que se ejecutan en el mismo runner.

**Características:**
- Los jobs se ejecutan en paralelo por defecto
- Se pueden configurar para ejecutarse secuencialmente
- Cada job se ejecuta en un entorno virtual limpio
- Los jobs pueden depender de otros jobs

**Ejemplo:**
```yaml
jobs:
  build:
    runs-on: ubuntu-latest

  test:
    runs-on: ubuntu-latest
    needs: build  # Se ejecuta después de que build termine
```

### 3. Steps

Un **step** es una tarea individual dentro de un job.

**Características:**
- Los steps se ejecutan secuencialmente dentro de un job
- Pueden ejecutar comandos o usar actions
- Comparten datos dentro del mismo job
- Cada step puede tener un nombre para mayor claridad

**Ejemplo:**
```yaml
steps:
  - name: Checkout code
    uses: actions/checkout@v4

  - name: Run tests
    run: npm test
```

### 4. Actions

Una **action** es una unidad de código reutilizable.

**Tipos:**
- **Actions del Marketplace**: Prefabricadas por la comunidad
- **Actions personalizadas**: Crea las tuyas
- **Actions de contenedor Docker**: Se ejecutan en contenedores
- **Actions de JavaScript**: Basadas en Node.js

**Jerarquía Visual:**

```
📁 .github/workflows/
   │
   ├── 📄 ci.yml (Workflow)
   │     │
   │     ├── 🔧 build (Job 1)
   │     │     ├── ✓ Checkout code (Step 1)
   │     │     ├── ✓ Setup Node.js (Step 2)
   │     │     └── ✓ Build project (Step 3)
   │     │
   │     └── 🧪 test (Job 2)
   │           ├── ✓ Checkout code (Step 1)
   │           ├── ✓ Setup Node.js (Step 2)
   │           └── ✓ Run tests (Step 3)
   │
   └── 📄 deploy.yml (Otro Workflow)
```

---

## 39. Creando Tu Primera Action

**Guía Paso a Paso:**

### Paso 1: Crear el Directorio de Workflows

```bash
# En la raíz de tu repositorio
mkdir -p .github/workflows
```

### Paso 2: Crear el Archivo de Workflow

```bash
# Crear el archivo YAML
touch .github/workflows/ci.yml
```

### Paso 3: Estructura Básica del Workflow

```yaml
# .github/workflows/ci.yml
name: CI Pipeline

# Cuándo disparar
on:
  push:
    branches: [ main ]

# Qué ejecutar
jobs:
  build:
    # Qué SO usar
    runs-on: ubuntu-latest

    # Steps a ejecutar
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Setup Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.13'

      - name: Run script
        run: python script.py
```

**Anatomía de un Workflow:**

#### 1. Name (Opcional pero Recomendado)

```yaml
name: My Awesome Workflow
```

Se muestra en la pestaña de GitHub Actions para una fácil identificación.

#### 2. Disparadores (`on`)

```yaml
on:
  push:
    branches: [ main ]
```

Define cuándo se ejecuta el workflow.

#### 3. Jobs

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      # ... steps aquí
```

**Runners Disponibles:**

```yaml
runs-on: ubuntu-latest      # Ubuntu Linux (Recomendado)
runs-on: windows-latest     # Windows Server
runs-on: macos-latest       # macOS
```

#### 4. Steps

**Usando una Action:**

```yaml
- name: Checkout code
  uses: actions/checkout@v4
```

**Ejecutando Comandos:**

```yaml
- name: Run tests
  run: npm test
```

**Con Configuración:**

```yaml
- name: Setup Node.js
  uses: actions/setup-node@v4
  with:
    node-version: '20'
```

### Ejemplo Completo: Generador de Estadísticas en Python

```yaml
name: Generate Statistics

on:
  push:
    branches: [ main ]

jobs:
  generate-stats:
    runs-on: ubuntu-latest

    permissions:
      contents: write  # Permitir escribir en el repo

    steps:
      # Paso 1: Obtener el código
      - name: Checkout repository
        uses: actions/checkout@v4

      # Paso 2: Configurar Python
      - name: Setup Python 3.11
        uses: actions/setup-python@v5
        with:
          python-version: '3.13'

      # Paso 3: Ejecutar el script
      - name: Generate statistics
        run: python roadmap/stats.py

      # Paso 4: Commitear y enviar los cambios
      - name: Commit and push stats
        uses: stefanzweifel/git-auto-commit-action@v5
        with:
          commit_message: "Update stats"
          commit_user_name: "GitHub Actions"
          commit_user_email: "actions@github.com"
          commit_author: "GitHub Actions <actions@github.com>"
```

### Viendo Tu Action

1. **Haz push del archivo de workflow:**
   ```bash
   git add .github/workflows/ci.yml
   git commit -m "Add CI workflow"
   git push origin main
   ```

2. **Ve al repositorio de GitHub → pestaña Actions**

3. **¡Ve tu workflow ejecutándose!**

---

## 40. Disparadores de Workflow

**Tipos de Disparadores:**

### 1. Disparador Push

Se ejecuta cuando se hace push de código a ramas específicas.

```yaml
on:
  push:
    branches:
      - main
      - develop
```

**Filtrar por rutas:**

```yaml
on:
  push:
    paths:
      - 'src/**'      # Solo cuando cambian los archivos de src/
      - '**.py'       # Solo cuando cambian los archivos de Python
```

### 2. Disparador Pull Request

Se ejecuta cuando se abren, actualizan o fusionan PRs.

```yaml
on:
  pull_request:
    branches: [ main ]
```

**Filtrar por tipos:**

```yaml
on:
  pull_request:
    types:
      - opened
      - synchronize  # Nuevos commits enviados
      - reopened
```

### 3. Disparador Schedule (Cron)

Se ejecuta según un horario usando la sintaxis de cron.

```yaml
on:
  schedule:
    # Ejecutar a medianoche UTC todos los días
    - cron: '0 0 * * *'
```

**Sintaxis de Cron:**

```
 ┌───────────── minuto (0 - 59)
 │ ┌───────────── hora (0 - 23)
 │ │ ┌───────────── día del mes (1 - 31)
 │ │ │ ┌───────────── mes (1 - 12)
 │ │ │ │ ┌───────────── día de la semana (0 - 6) (Domingo a Sábado)
 │ │ │ │ │
 * * * * *
```

**Ejemplos Comunes de Cron:**

```yaml
# Cada 15 minutos
- cron: '*/15 * * * *'

# Cada hora
- cron: '0 * * * *'

# Cada día a medianoche UTC
- cron: '0 0 * * *'

# Cada día a las 8:30 AM UTC
- cron: '30 8 * * *'

# Cada lunes a las 9 AM UTC
- cron: '0 9 * * 1'

# Dos veces al día (6 AM y 6 PM UTC)
- cron: '0 6,18 * * *'

# Cada día laborable al mediodía UTC
- cron: '0 12 * * 1-5'
```

**⚠️ Importante:**
- Cron se ejecuta en la **zona horaria UTC**
- Intervalo mínimo: cada 5 minutos
- Los workflows programados pueden tener ligeros retrasos

### 4. Disparador Manual (workflow_dispatch)

Se ejecuta manualmente desde la UI de GitHub.

```yaml
on:
  workflow_dispatch:
    inputs:
      environment:
        description: 'Environment to deploy'
        required: true
        default: 'staging'
        type: choice
        options:
          - staging
          - production
```

### 5. Disparadores Múltiples

Combina varios disparadores:

```yaml
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
  schedule:
    - cron: '0 0 * * *'
  workflow_dispatch:
```

### 6. Otros Disparadores

```yaml
# Cuando se publica un release
on:
  release:
    types: [ published ]

# Cuando se abre un issue
on:
  issues:
    types: [ opened ]

# Cuando se revisa un PR
on:
  pull_request_review:
    types: [ submitted ]

# Cuando un workflow de otro repo se completa
on:
  workflow_run:
    workflows: [ "CI" ]
    types: [ completed ]
```

**Eligiendo el Disparador Correcto:**

| Caso de Uso | Disparador |
|----------|---------|
| Ejecutar tests en cada commit | `push` |
| Validar PRs antes del merge | `pull_request` |
| Desplegar builds nocturnos | `schedule` (cron) |
| Generar informes diarios | `schedule` (cron) |
| Despliegues manuales | `workflow_dispatch` |
| Publicar paquetes en un release | `release` |

---

## 41. Usando Actions del Marketplace

**GitHub Actions Marketplace:**

[github.com/marketplace?type=actions](https://github.com/marketplace?type=actions)

**Más de 21,000 actions prefabricadas** creadas por GitHub y la comunidad.

**¿Por Qué Usar Actions del Marketplace?**

✅ **Ahorra tiempo**: No reinventes la rueda
✅ **Probadas en batalla**: Usadas por miles de proyectos
✅ **Mantenidas**: Actualizaciones y correcciones de la comunidad
✅ **Documentadas**: Ejemplos de uso claros

### Encontrando Actions

**Método 1: GitHub Marketplace**

1. Ve a [github.com/marketplace](https://github.com/marketplace)
2. Haz clic en la pestaña "Actions"
3. Busca lo que necesitas (p. ej. "docker", "kubernetes", "npm")
4. Comprueba las estrellas, descargas y mantenimiento

**Método 2: En el Editor de Workflows**

1. Ve al repositorio → Actions → New workflow
2. Ve las actions sugeridas en la barra lateral derecha
3. Explora por lenguaje/framework

### Actions Populares del Marketplace

#### 1. Checkout del Repositorio

```yaml
- uses: actions/checkout@v4
```

**Qué hace**: Clona el código de tu repositorio

**Por qué se necesita**: Las actions se ejecutan en un entorno vacío, necesitan el código primero

#### 2. Setup de Lenguajes

```yaml
# Node.js
- uses: actions/setup-node@v4
  with:
    node-version: '20'

# Python
- uses: actions/setup-python@v5
  with:
    python-version: '3.13'

# Java
- uses: actions/setup-java@v4
  with:
    java-version: '17'
    distribution: 'temurin'

# Go
- uses: actions/setup-go@v5
  with:
    go-version: '1.21'
```

#### 3. Cacheado de Dependencias

```yaml
- uses: actions/cache@v4
  with:
    path: ~/.npm
    key: ${{ runner.os }}-node-${{ hashFiles('**/package-lock.json') }}
```

**Acelera los workflows** cacheando las dependencias.

#### 4. Auto-commit de Cambios

```yaml
- uses: stefanzweifel/git-auto-commit-action@v5
  with:
    commit_message: "Auto-generated changes"
    commit_user_name: "GitHub Actions"
    commit_user_email: "actions@github.com"
```

**Perfecto para**: Generar archivos, actualizar docs, formatear código

#### 5. Build y Push de Docker

```yaml
- uses: docker/build-push-action@v5
  with:
    context: .
    push: true
    tags: user/app:latest
```

#### 6. Desplegar a la Nube

```yaml
# Desplegar a Azure
- uses: azure/webapps-deploy@v2
  with:
    app-name: 'my-app'

# Desplegar a AWS
- uses: aws-actions/configure-aws-credentials@v4

# Desplegar a Google Cloud
- uses: google-github-actions/setup-gcloud@v2
```

### Sintaxis de Actions

**Formato:**

```yaml
uses: owner/repository@version
```

**Ejemplos:**

```yaml
# Action oficial de GitHub
uses: actions/checkout@v4

# Action de la comunidad
uses: stefanzweifel/git-auto-commit-action@v5

# Commit específico
uses: actions/checkout@8e5e7e5

# Rama (no recomendado para producción)
uses: actions/checkout@main
```

### Configurando Actions con `with`

```yaml
- uses: actions/setup-python@v5
  with:
    python-version: '3.13'      # Parámetro requerido
    cache: 'pip'                # Parámetro opcional
    cache-dependency-path: |    # Parámetro multilínea
      requirements.txt
      requirements-dev.txt
```

### Encontrando Opciones de Configuración

1. Ve al repositorio de la action (p. ej. `actions/setup-python`)
2. Lee el README.md
3. Comprueba la sección "Inputs"
4. Mira los ejemplos

### Evaluando Actions

**Comprueba antes de usar:**

✅ **Estrellas**: Más de 500 es buena señal
✅ **Última actualización**: Dentro de los últimos 6 meses
✅ **Número de usuarios**: Comprueba el contador "Used by"
✅ **Mantenimiento**: Issues/PRs activos siendo atendidos
✅ **Documentación**: README claro con ejemplos

**Señales de alerta:**

❌ Última actualización hace más de 2 años
❌ Muchos issues abiertos, sin respuestas
❌ Documentación pobre
❌ Muy pocos usuarios

### Actions Recomendadas Principales

| Action | Propósito | Repositorio |
|--------|---------|------------|
| **Checkout** | Clonar el repositorio | `actions/checkout` |
| **Setup Node** | Instalar Node.js | `actions/setup-node` |
| **Setup Python** | Instalar Python | `actions/setup-python` |
| **Cache** | Cachear dependencias | `actions/cache` |
| **Upload Artifact** | Guardar salidas de build | `actions/upload-artifact` |
| **Docker Build/Push** | Construir imágenes de Docker | `docker/build-push-action` |
| **Auto-commit** | Commitear cambios | `stefanzweifel/git-auto-commit-action` |
| **Super-Linter** | Lint de varios lenguajes | `github/super-linter` |

---

## 42. Gestión de Secretos

**¿Qué son los Secretos?**

Los secretos son variables de entorno cifradas para datos sensibles:
- Claves de API
- Contraseñas
- Tokens de acceso
- Claves SSH
- Credenciales de bases de datos

**¿Por Qué Usar Secretos?**

❌ **NUNCA** pongas credenciales directamente en el código:

```yaml
# ❌ INCORRECTO - ¡Credenciales expuestas!
- name: Deploy to server
  run: |
    ssh user@server.com
    PASSWORD=mypassword123
```

✅ **Siempre** usa secretos:

```yaml
# ✅ CORRECTO - Credenciales ocultas
- name: Deploy to server
  env:
    PASSWORD: ${{ secrets.SERVER_PASSWORD }}
  run: |
    # La contraseña está disponible como variable de entorno
```

### Creando Secretos

**Paso 1: Ve a Settings del Repositorio**

```
Repository → Settings → Secrets and variables → Actions
```

**Paso 2: Crear un Nuevo Secreto**

1. Haz clic en "New repository secret"
2. Nombre: `DOCKER_USERNAME` (mayúsculas, guiones bajos)
3. Valor: Tu nombre de usuario de Docker Hub
4. Haz clic en "Add secret"

**Paso 3: Repite para Todos los Secretos**

Secretos comunes a añadir:
- `DOCKER_USERNAME`
- `DOCKER_PASSWORD`
- `KUBE_CONFIG` (codificado en base64)
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `API_TOKEN`

### Usando Secretos en Workflows

```yaml
name: Deploy Application

on: [push]

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Login to Docker Hub
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_PASSWORD }}

      - name: Build and push
        run: |
          docker build -t ${{ secrets.DOCKER_USERNAME }}/app:latest .
          docker push ${{ secrets.DOCKER_USERNAME }}/app:latest
```

**Sintaxis:**

```yaml
${{ secrets.SECRET_NAME }}
```

### Funciones de Seguridad de los Secretos

✅ **Cifrados en reposo**: Almacenados de forma segura por GitHub
✅ **Enmascarados en los logs**: Nunca se imprimen en los logs del workflow
✅ **Acceso controlado**: Solo disponibles para los workflows de ese repo
✅ **Registro de auditoría**: Rastrea el uso de los secretos

**Ejemplo de Salida del Log:**

```bash
# Los secretos se enmascaran automáticamente
Docker password: ***
Login successful!
```

### Secretos de Organización vs Repositorio

**Secretos de Repositorio:**
- Disponibles solo para un repositorio
- Gestionados por repositorio

**Secretos de Organización:**
- Disponibles para varios repositorios
- Gestionados de forma centralizada
- Perfectos para credenciales compartidas

### Secretos de Entorno

Para distintos entornos (staging, producción):

```yaml
jobs:
  deploy:
    runs-on: ubuntu-latest
    environment: production  # Usa los secretos de producción

    steps:
      - name: Deploy
        env:
          API_KEY: ${{ secrets.PROD_API_KEY }}
        run: ./deploy.sh
```

### Buenas Prácticas

✅ **Usa nombres descriptivos**: `AWS_ACCESS_KEY_ID` no `KEY1`
✅ **Rota regularmente**: Actualiza los secretos periódicamente
✅ **Acceso mínimo**: Otorga solo los permisos necesarios
✅ **Nunca registres secretos**: No hagas `echo` ni `print` de los secretos
✅ **Usa secretos de entorno**: Separa dev/staging/prod
❌ **Nunca commitees** archivos `.env` al repositorio

### Codificando Secretos

**Para archivos binarios (kubeconfig, certificados):**

```bash
# Codificar el archivo a base64
cat kubeconfig.yml | base64

# Añadir la cadena base64 al secreto KUBE_CONFIG

# Decodificar en el workflow
- name: Setup Kubernetes
  run: |
    echo "${{ secrets.KUBE_CONFIG }}" | base64 -d > ~/.kube/config
```

---

## 43. Build y Push de Docker

**Objetivo**: Construir imágenes de Docker y enviarlas a Docker Hub automáticamente.

### Ejemplo de Workflow Completo

```yaml
name: Docker Build and Push

on:
  push:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      # Paso 1: Obtener el código
      - name: Checkout repository
        uses: actions/checkout@v4

      # Paso 2: Construir y enviar a Docker Hub
      - name: Build and push Docker image
        uses: docker/build-push-action@v5
        with:
          context: .
          push: true
          tags: |
            ${{ secrets.DOCKER_USERNAME }}/myapp:latest
            ${{ secrets.DOCKER_USERNAME }}/myapp:${{ github.sha }}
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_PASSWORD }}
```

### Explicación Paso a Paso

#### Paso 1: Checkout del Código

```yaml
- uses: actions/checkout@v4
```

Descarga el código de tu repositorio al runner.

#### Paso 2: Login en Docker Hub (Método Alternativo)

```yaml
- name: Login to Docker Hub
  uses: docker/login-action@v3
  with:
    username: ${{ secrets.DOCKER_USERNAME }}
    password: ${{ secrets.DOCKER_PASSWORD }}
```

#### Paso 3: Build y Push

```yaml
- name: Build and push
  uses: docker/build-push-action@v5
  with:
    context: .              # Contexto de build (directorio actual)
    file: ./Dockerfile      # Ubicación del Dockerfile (opcional)
    push: true              # Enviar al registry
    tags: user/app:latest   # Tags de la imagen
```

### Configuración Avanzada

**Múltiples Tags:**

```yaml
tags: |
  ${{ secrets.DOCKER_USERNAME }}/app:latest
  ${{ secrets.DOCKER_USERNAME }}/app:${{ github.sha }}
  ${{ secrets.DOCKER_USERNAME }}/app:v1.0.0
```

**Argumentos de Build:**

```yaml
- uses: docker/build-push-action@v5
  with:
    context: .
    push: true
    tags: user/app:latest
    build-args: |
      NODE_VERSION=20
      APP_ENV=production
```

**Apuntar a una Etapa Específica:**

```yaml
# Para Dockerfiles multi-etapa
- uses: docker/build-push-action@v5
  with:
    context: .
    target: production
    push: true
    tags: user/app:latest
```

**Cachear Capas:**

```yaml
- uses: docker/build-push-action@v5
  with:
    context: .
    push: true
    tags: user/app:latest
    cache-from: type=gha      # Caché de GitHub Actions
    cache-to: type=gha,mode=max
```

### Ejemplo Real Completo

```yaml
name: CI/CD Pipeline

on:
  push:
    branches: [ main ]

env:
  IMAGE_NAME: ${{ secrets.DOCKER_USERNAME }}/webapp

jobs:
  build-and-push:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Set up Docker Buildx
        uses: docker/setup-buildx-action@v3

      - name: Login to Docker Hub
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_PASSWORD }}

      - name: Extract metadata
        id: meta
        uses: docker/metadata-action@v5
        with:
          images: ${{ env.IMAGE_NAME }}
          tags: |
            type=sha
            type=raw,value=latest

      - name: Build and push
        uses: docker/build-push-action@v5
        with:
          context: .
          push: true
          tags: ${{ steps.meta.outputs.tags }}
          labels: ${{ steps.meta.outputs.labels }}
          cache-from: type=gha
          cache-to: type=gha,mode=max
```

### Usando el SHA del Commit de Git como Tag

```yaml
tags: |
  user/app:latest
  user/app:${{ github.sha }}
```

**¿Por qué?**
- Identificador único para cada build
- Fácil rollback a una versión específica
- Trazabilidad

**Acceso en pasos posteriores:**

```yaml
- name: Get short SHA
  id: vars
  run: echo "sha_short=$(git rev-parse --short HEAD)" >> $GITHUB_OUTPUT

- name: Use short SHA
  run: echo "Image tag: app:${{ steps.vars.outputs.sha_short }}"
```

---

## 44. Despliegue en Kubernetes

**Objetivo**: Desplegar imágenes de Docker en un clúster de Kubernetes automáticamente.

### Requisitos Previos

1. **Clúster de Kubernetes** en ejecución (puede ser local, en la nube o on-premise)
2. **kubectl** configurado localmente
3. **Manifiesto de deployment** (archivo YAML)

### Preparando el Secreto kubeconfig

**Paso 1: Codificar kubeconfig**

```bash
# Obtener tu archivo kubeconfig
cat ~/.kube/config | base64
```

**Paso 2: Añadir a los Secretos de GitHub**

1. Repository → Settings → Secrets
2. Nuevo secreto: `KUBE_CONFIG`
3. Pega el kubeconfig codificado en base64

### Workflow de Despliegue Completo

```yaml
name: Deploy to Kubernetes

on:
  push:
    branches: [ main ]

env:
  IMAGE_NAME: ${{ secrets.DOCKER_USERNAME }}/webapp

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest

    steps:
      # Construir y enviar la imagen de Docker
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Build and push Docker image
        uses: docker/build-push-action@v5
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_PASSWORD }}
          repository: ${{ env.IMAGE_NAME }}
          tags: latest,${{ github.sha }}

      # Desplegar en Kubernetes
      - name: Deploy to Kubernetes
        uses: steebchen/kubectl@v2.0.0
        with:
          config: ${{ secrets.KUBE_CONFIG }}
          command: set image deployment/webapp webapp=${{ env.IMAGE_NAME }}:${{ github.sha }}

      - name: Verify deployment
        uses: steebchen/kubectl@v2.0.0
        with:
          config: ${{ secrets.KUBE_CONFIG }}
          command: rollout status deployment/webapp
```

### Configuración de la Action Kubectl

**Uso Básico:**

```yaml
- name: Deploy to Kubernetes
  uses: steebchen/kubectl@v2.0.0
  with:
    config: ${{ secrets.KUBE_CONFIG }}
    command: apply -f k8s/deployment.yaml
```

**Set Image (Actualizar el Deployment):**

```yaml
- name: Update deployment image
  uses: steebchen/kubectl@v2.0.0
  with:
    config: ${{ secrets.KUBE_CONFIG }}
    command: set image deployment/myapp myapp=${{ env.IMAGE_NAME }}:${{ github.sha }} --record
```

**Comprobar el Estado del Rollout:**

```yaml
- name: Verify deployment
  uses: steebchen/kubectl@v2.0.0
  with:
    config: ${{ secrets.KUBE_CONFIG }}
    command: rollout status deployment/myapp
```

### Ejemplo Completo de CI/CD

```yaml
name: Complete CI/CD to Kubernetes

on:
  push:
    branches: [ main ]

env:
  IMAGE_NAME: ${{ secrets.DOCKER_USERNAME }}/myapp
  DEPLOYMENT_NAME: myapp
  CONTAINER_NAME: myapp

jobs:
  ci-cd:
    runs-on: ubuntu-latest

    steps:
      # CI: Build y Test
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Run tests
        run: |
          npm install
          npm test

      # CD: Construir la Imagen de Docker
      - name: Login to Docker Hub
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_PASSWORD }}

      - name: Build and push
        uses: docker/build-push-action@v5
        with:
          context: .
          push: true
          tags: |
            ${{ env.IMAGE_NAME }}:latest
            ${{ env.IMAGE_NAME }}:${{ github.sha }}

      # CD: Desplegar en Kubernetes
      - name: Setup kubectl
        uses: steebchen/kubectl@v2.0.0
        with:
          config: ${{ secrets.KUBE_CONFIG }}
          version: v1.28.0

      - name: Update deployment
        uses: steebchen/kubectl@v2.0.0
        with:
          config: ${{ secrets.KUBE_CONFIG }}
          command: set image deployment/${{ env.DEPLOYMENT_NAME }} ${{ env.CONTAINER_NAME }}=${{ env.IMAGE_NAME }}:${{ github.sha }} --record

      - name: Verify rollout
        uses: steebchen/kubectl@v2.0.0
        with:
          config: ${{ secrets.KUBE_CONFIG }}
          command: rollout status deployment/${{ env.DEPLOYMENT_NAME }}

      - name: Get deployment status
        uses: steebchen/kubectl@v2.0.0
        with:
          config: ${{ secrets.KUBE_CONFIG }}
          command: get pods -l app=${{ env.DEPLOYMENT_NAME }}
```

### Alternativa: Usando manifiestos

```yaml
- name: Deploy with manifests
  uses: steebchen/kubectl@v2.0.0
  with:
    config: ${{ secrets.KUBE_CONFIG }}
    command: apply -f k8s/
```

**Requiere un directorio k8s/ con:**
- `deployment.yaml`
- `service.yaml`
- `ingress.yaml`

### Estrategias de Despliegue

**Rolling Update (por defecto):**

```yaml
command: set image deployment/app app=${{ env.IMAGE_NAME }}:${{ github.sha }}
```

**Recreate:**

```yaml
# En deployment.yaml
spec:
  strategy:
    type: Recreate
```

**Blue-Green:**

```yaml
- name: Deploy green
  run: kubectl apply -f k8s/deployment-green.yaml

- name: Switch traffic
  run: kubectl patch service myapp -p '{"spec":{"selector":{"version":"green"}}}'
```

---

## 45. Ver Logs y Depurar

**Accediendo a los Logs del Workflow:**

### Paso 1: Ve a la Pestaña Actions

```
Repository → Actions
```

### Paso 2: Selecciona una Ejecución del Workflow

Haz clic en cualquier ejecución de workflow para ver los detalles.

### Paso 3: Ver los Logs del Job

**Estructura del Workflow:**

```
Ejecución del Workflow
  └── Jobs
       └── Steps
            └── Logs
```

**Ejemplo de Vista:**

```
✓ Set up job                    (2s)
✓ Checkout repository          (3s)
✓ Setup Python 3.11            (5s)
✓ Run script                   (12s)
✓ Commit and push changes      (4s)
✓ Post setup Python            (1s)
✓ Complete job                 (1s)
```

### Paso 4: Expandir un Step para Ver los Logs

Haz clic en cualquier step para ver su salida detallada:

```
Run python roadmap/stats.py
Reading repository data...
Found 904 solutions
Found 360 users
Generating statistics...
✓ Statistics saved to stats.json
```

### Funciones de los Logs

**Codificación por Colores:**

```
✓ Check verde = Éxito
✗ X roja = Falló
○ Círculo gris = Omitido
⟳ Spinner amarillo = En ejecución
```

**Marcas de Tiempo:**

```
2024-01-26T10:30:45.123Z  Starting workflow
2024-01-26T10:30:48.456Z  Checkout complete
2024-01-26T10:30:52.789Z  Tests passed
```

**Descargar Logs:**

Haz clic en el menú "..." → Download log archive

### Debug Logging

**Habilitar Logs de Depuración:**

1. Repository → Settings → Secrets
2. Añade el secreto: `ACTIONS_STEP_DEBUG` = `true`
3. Vuelve a ejecutar el workflow
4. ¡Salida mucho más detallada!

**En el Workflow:**

```yaml
- name: Debug step
  run: echo "Debug info"
  env:
    ACTIONS_STEP_DEBUG: true
```

### Patrones de Error Comunes

#### Error: Permiso Denegado

```
Error: Resource not accessible by integration
```

**Solución**: Añade permisos

```yaml
permissions:
  contents: write
```

#### Error: Secreto No Encontrado

```
Error: secrets.DOCKER_PASSWORD not found
```

**Solución**: Crea el secreto en la configuración del repositorio

#### Error: Comando No Encontrado

```
/bin/sh: python: command not found
```

**Solución**: Instala el software requerido

```yaml
- uses: actions/setup-python@v5
  with:
    python-version: '3.13'
```

#### Error: Timeout

```
Error: The job running on runner has exceeded the maximum execution time
```

**Solución**: Aumenta el timeout

```yaml
jobs:
  build:
    timeout-minutes: 60  # El valor por defecto es 360 (6 horas)
```

### Re-ejecutar Workflows

**Re-ejecutar Todos los Jobs:**

```
Actions → Workflow Run → Re-run all jobs
```

**Re-ejecutar los Jobs Fallidos:**

```
Actions → Workflow Run → Re-run failed jobs
```

**Disparador Manual:**

Para workflows con `workflow_dispatch`:

```
Actions → Workflow name → Run workflow
```

### Consejos de Depuración

**Añade Prints de Depuración:**

```yaml
- name: Debug environment
  run: |
    echo "Current directory: $(pwd)"
    echo "Files: $(ls -la)"
    echo "Git SHA: ${{ github.sha }}"
    echo "Branch: ${{ github.ref }}"
    env
```

**Comprobar el Contenido de un Archivo:**

```yaml
- name: Show file content
  run: cat package.json
```

**Dormir para Investigar:**

```yaml
- name: Sleep
  run: sleep 600  # 10 minutos para investigar
```

**Usar tmate para Acceso SSH:**

```yaml
- name: Setup tmate session
  uses: mxschmitt/action-tmate@v3
```

¡Te da acceso SSH al runner!

---

## 46. Trabajos Programados con Cron

**Sintaxis de Cron en GitHub Actions:**

```yaml
on:
  schedule:
    - cron: '0 0 * * *'  # Medianoche UTC todos los días
```

### Formato de Cron

```
┌─────────── minuto (0 - 59)
│ ┌───────── hora (0 - 23)
│ │ ┌─────── día del mes (1 - 31)
│ │ │ ┌───── mes (1 - 12)
│ │ │ │ ┌─── día de la semana (0 - 6) (Dom - Sáb)
│ │ │ │ │
* * * * *
```

### Horarios de Cron Comunes

```yaml
# Cada minuto (no recomendado - ¡usar con moderación!)
- cron: '* * * * *'

# Cada 5 minutos
- cron: '*/5 * * * *'

# Cada 15 minutos
- cron: '*/15 * * * *'

# Cada hora
- cron: '0 * * * *'

# Cada 6 horas
- cron: '0 */6 * * *'

# Cada día a medianoche UTC
- cron: '0 0 * * *'

# Cada día a las 2:30 AM UTC
- cron: '30 2 * * *'

# Cada lunes a las 9 AM UTC
- cron: '0 9 * * 1'

# Cada día laborable al mediodía UTC
- cron: '0 12 * * 1-5'

# Primer día de cada mes
- cron: '0 0 1 * *'

# Cada domingo a las 3 AM UTC
- cron: '0 3 * * 0'

# Dos veces al día (6 AM y 6 PM UTC)
- cron: '0 6,18 * * *'
```

### Notas Importantes

⏰ **Zona Horaria UTC**: Todos los trabajos de cron se ejecutan en UTC

```yaml
# Para ejecutar a las 9 AM EST (UTC-5)
- cron: '0 14 * * *'  # 14:00 UTC = 9:00 AM EST

# Para ejecutar a las 9 AM PST (UTC-8)
- cron: '0 17 * * *'  # 17:00 UTC = 9:00 AM PST
```

⚠️ **Intervalo Mínimo**: 5 minutos (no se recomienda ir más rápido)

⚠️ **Retrasos**: Los trabajos programados pueden retrasarse durante alta carga de GitHub

### Ejemplo Completo

```yaml
name: Daily Statistics Generator

on:
  schedule:
    - cron: '0 0 * * *'  # Medianoche UTC diariamente
  workflow_dispatch:     # Permitir disparo manual

jobs:
  generate-stats:
    runs-on: ubuntu-latest

    permissions:
      contents: write

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Setup Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.13'

      - name: Generate statistics
        run: python scripts/generate_stats.py

      - name: Commit and push
        uses: stefanzweifel/git-auto-commit-action@v5
        with:
          commit_message: "Update daily statistics"
          commit_user_name: "GitHub Actions Bot"
          commit_user_email: "bot@github-actions.com"
```

### Múltiples Horarios

```yaml
on:
  schedule:
    - cron: '0 0 * * *'    # Diariamente a medianoche
    - cron: '0 12 * * *'   # Diariamente al mediodía
    - cron: '0 0 * * 0'    # Semanalmente el domingo
```

### Probando Horarios de Cron

**Herramientas:**

- [crontab.guru](https://crontab.guru/) - Validador de expresiones cron
- [cron tab](https://crontab.cronhub.io/) - Otro validador

**Prueba Manual:**

```yaml
on:
  schedule:
    - cron: '0 0 * * *'
  workflow_dispatch:  # ¡Añade esto para pruebas manuales!
```

Luego haz clic en "Run workflow" en la pestaña Actions.

### Casos de Uso para Trabajos Programados

✅ **Informes diarios**: Generar estadísticas, dashboards
✅ **Builds nocturnos**: Construir y probar proyectos diariamente
✅ **Sincronización de datos**: Sincronizar datos de APIs externas
✅ **Tareas de limpieza**: Eliminar artefactos y cachés antiguos
✅ **Actualizaciones de dependencias**: Comprobar paquetes desactualizados
✅ **Backups**: Backups regulares de bases de datos o archivos
✅ **Monitoreo**: Comprobar la salud del servicio periódicamente

---

## Parte 3: Contribuir a Código Abierto

---

## 47. Por Qué Contribuir a Código Abierto

**Beneficios de Contribuir:**

✅ **Visibilidad**: Tu perfil de GitHub se convierte en un portafolio
✅ **Aprendizaje**: Aprende de proyectos del mundo real
✅ **Networking**: Conecta con desarrolladores de todo el mundo
✅ **Impacto**: Ayuda a proyectos usados por miles
✅ **Experiencia**: Gana habilidades prácticas de colaboración en equipo
✅ **Carrera**: Mejora tus perspectivas laborales y credibilidad

**Gráfico de Contribuciones de GitHub:**

Tu perfil de GitHub muestra un gráfico de contribuciones (los "cuadrados verdes"). Aunque se puede "hackear" con commits automatizados, las contribuciones genuinas importan más:
- Muestra consistencia y actividad
- Demuestra experiencia del mundo real
- Prueba habilidades colaborativas
- Actúa como un portafolio público

**Un Poco de Realidad:**

- El gráfico de contribuciones NO lo es todo
- Calidad > Cantidad
- El trabajo privado no aparece
- Los commits automatizados son detectables
- Lo que importa: contribuciones reales a proyectos reales

---

## 48. Encontrar Proyectos para Contribuir

**Recursos Principales:**

### 1. GitHub Digital Public Goods
[github.com/github/digital-public-goods](https://github.com/github/digital-public-goods)

Proyectos con impacto social:
- Educación
- Cambio climático
- Salud
- Reducción de la pobreza
- Paz y justicia

**Filtra por:**
- Lenguaje de programación
- Etiquetas de issues
- Tipo de organización

### 2. Good First Issue
[goodfirstissue.dev](https://goodfirstissue.dev)

Lista curada de issues aptos para principiantes:

```bash
# Filtrar por lenguaje
- JavaScript
- Python
- TypeScript
- Go
- Rust
```

### 3. Good First Issues (Alternativa)
[goodfirstissues.com](https://goodfirstissues.com)

Similar al anterior pero con más filtros:
- Número de estrellas
- Lenguaje
- Organización
- Dificultad del issue

### 4. Búsqueda Directa en el Repositorio

Busca la etiqueta `good-first-issue`:

```bash
# Buscar en GitHub
is:issue is:open label:"good-first-issue" language:JavaScript
```

### 5. Proyectos de la Comunidad

Proyectos populares que dan la bienvenida a contribuciones:
- **Astro**: Framework web moderno
- **Next.js**: Framework de React
- **React**: Librería de UI de Meta
- **VS Code**: Editor de Microsoft
- **TypeScript**: Lenguaje de Microsoft

**Cómo Encontrar Issues:**

1. Ve al repositorio
2. Haz clic en la pestaña "Issues"
3. Filtra por etiqueta: `good-first-issue`
4. Lee los comentarios existentes (comprueba si alguien lo reclamó)
5. Comprueba si el proyecto tiene un CONTRIBUTING.md

---

## 49. Entendiendo el Flujo de Fork

**¿Qué es un Fork?**

Un fork es una copia completa de un repositorio bajo tu cuenta.

**Representación Visual:**

```
Repositorio Original (upstream-owner/project)
          |
          | (botón Fork)
          ↓
Tu Fork (you/project)
```

**Fork vs Clone:**

| Fork | Clone |
|------|-------|
| Crea una copia en GitHub | Descarga a la máquina local |
| Cambia la propiedad | Mantiene el mismo remoto |
| Obtienes acceso de escritura | Solo lectura (normalmente) |
| Copia permanente | Copia local |
| Puede divergir de forma independiente | Permanece conectado al origin |

**Flujo de Trabajo de Fork:**

```
1. Repo Original (upstream)
   └── No tienes acceso de escritura

2. Fork a tu cuenta
   └── Ahora tienes acceso de escritura a TU fork

3. Clona TU fork localmente
   └── Haz cambios localmente

4. Envía (push) a TU fork
   └── Los cambios van a tu copia

5. Crea un Pull Request
   └── Pídele al repo original que fusione tus cambios
```

**Creando un Fork:**

1. Ve al repositorio en GitHub
2. Haz clic en el botón "Fork" (arriba a la derecha)
3. Elige el destino (tu cuenta u organización)
4. Opcional: Desmarca "Copy main branch only" para obtener todas las ramas
5. Haz clic en "Create fork"

**Notas Importantes:**

- ✅ El fork copia todo el historial y los commits
- ✅ El fork mantiene la conexión con el original
- ✅ Puedes hacer fork de forks (cadenas de forks)
- ⚠️ La licencia importa (comprueba MIT, Apache, etc.)
- ⚠️ Algunos repos no permiten forks comerciales

---

## 50. Estrategias de Clonado

**Tres Métodos de Clonado:**

### 1. HTTPS (No Recomendado)

```bash
git clone https://github.com/username/repo.git
```

**Problemas:**
- Requiere usuario/contraseña cada vez
- Menos seguro
- Molesto para operaciones frecuentes

### 2. SSH (Recomendado)

```bash
git clone git@github.com:username/repo.git
```

**Ventajas:**
- ✅ Sin solicitudes de contraseña
- ✅ Más seguro
- ✅ Una vez configurado, funciona para siempre
- ✅ Misma máquina, sin autenticación repetida

**Configurar SSH:** Ver [Autenticación SSH](#26-autenticación-ssh)

### 3. GitHub CLI (Forma Moderna)

```bash
# Instalar GitHub CLI
brew install gh  # macOS
winget install GitHub.cli  # Windows

# Autenticarse
gh auth login

# Clonar un repositorio
gh repo clone username/repo
```

**Ventajas:**
- ✅ Autenticación automática
- ✅ Configura automáticamente el upstream para los forks
- ✅ Sintaxis más simple
- ✅ Funciones específicas de GitHub

### Clon Superficial (Clon Rápido)

**Problema:** Los repositorios grandes tardan una eternidad en clonarse.

**Solución:** Clon superficial con `--depth 1`

```bash
# Clon normal (descarga TODO el historial)
git clone git@github.com:facebook/react.git
# Descarga más de 50 MB, tarda minutos

# Clon superficial (solo el último commit)
git clone --depth 1 git@github.com:facebook/react.git
# Descarga 6 MB, tarda segundos
```

**Cuándo Usarlo:**

✅ Contribuir a proyectos grandes
✅ No necesitas el historial completo
✅ Solo quieres el último código
✅ Ahorrar espacio en disco

⚠️ No puedes ver el historial completo
⚠️ No puedes acceder a commits antiguos

**Opciones de Depth:**

```bash
# Solo el último commit
git clone --depth 1 <url>

# Los últimos 10 commits
git clone --depth 10 <url>

# Rama específica con depth
git clone --depth 1 -b develop <url>
```

---

## 51. Trabajando con Upstream

**Entendiendo los Remotos:**

Cuando haces fork de un repositorio, tienes DOS remotos importantes:

```
origin    → Tu fork (you/project)
upstream  → Repo original (upstream-owner/project)
```

**Diagrama Visual:**

```
┌─────────────────────┐
│  Repo Original      │
│  (upstream-owner/project)       │
│  [upstream]         │
└──────────┬──────────┘
           │ fork
           ↓
┌─────────────────────┐       ┌──────────────┐
│  Tu Fork            │←──────│ Tu Máquina   │
│  (you/project)     │ push  │ Local        │
│  [origin]           │──────→│              │
└─────────────────────┘ pull  └──────────────┘
```

**Configurando el Upstream:**

### Método Manual:

```bash
# 1. Clona tu fork
git clone git@github.com:you/project.git

# 2. Añade el remoto upstream
git remote add upstream git@github.com:upstream-owner/project.git

# 3. Verifica los remotos
git remote -v
# Salida:
# origin    git@github.com:you/project.git (fetch)
# origin    git@github.com:you/project.git (push)
# upstream  git@github.com:upstream-owner/project.git (fetch)
# upstream  git@github.com:upstream-owner/project.git (push)
```

### Método con GitHub CLI (Automático):

```bash
# El clone configura automáticamente el upstream para los forks
gh repo clone you/project

# Comprueba los remotos - ¡upstream ya está configurado!
git remote -v
```

**Por Qué Importa el Upstream:**

1. **Mantenerse sincronizado**: Obtener los últimos cambios del repo original
2. **Evitar conflictos**: Mantener tu fork actualizado
3. **PRs fluidos**: Más fácil de fusionar cuando estás sincronizado

**Trayendo (Fetch) desde el Upstream:**

```bash
# Obtener los últimos cambios del repo original
git fetch upstream

# Ver qué hay de nuevo
git log upstream/main

# Fusionar los cambios en tu main local
git switch main
git merge upstream/main

# Enviar a tu fork
git push origin main
```

---

## 52. Creando Pull Requests de Calidad

**Flujo de Trabajo Completo de PR:**

### Paso 1: Fork y Clone

```bash
# Fork en GitHub (haz clic en el botón Fork)

# Clona TU fork
gh repo clone you/project
# o
git clone git@github.com:you/project.git

# Añade el upstream
git remote add upstream git@github.com:upstream-owner/project.git
```

### Paso 2: Crear una Rama de Funcionalidad

```bash
# ¡NUNCA trabajes en main!
# Crea una nueva rama
git switch -c fix-accessibility-issues
```

**¿Por Qué No Trabajar en Main?**
- ⚠️ Main debería reflejar upstream/main
- ⚠️ Sincronizar se vuelve complicado
- ⚠️ No puedes tener varios PRs fácilmente
- ✅ Las ramas mantienen el trabajo aislado

### Paso 3: Hacer Cambios

**Buenas Prácticas:**

✅ **Sé Quirúrgico**: Cambia solo lo necesario
✅ **Mantente Enfocado**: Una funcionalidad/corrección por PR
✅ **Sin Formateo**: No reformatees el código existente
✅ **Sin Refactorización**: A menos que ese sea el propósito del PR
✅ **Sigue el Estilo**: Iguala el estilo de código del proyecto

**Mal Ejemplo:**

```javascript
// NO HAGAS ESTO en un PR de accesibilidad
// Estás arreglando la accesibilidad pero también:
- Renombrando variables
- Reformateando código
- Cambiando lógica no relacionada
- Añadiendo funcionalidades
```

**Buen Ejemplo:**

```javascript
// HAZ ESTO - Solo cambios de accesibilidad
// Antes:
<div hidden>
  <button>Click me</button>
</div>

// Después:
<article>
  <button aria-label="Submit form">Click me</button>
</article>
```

### Paso 4: Commitear los Cambios

```bash
# Poner en staging archivos específicos
git add card.tsx navbar.tsx

# Commitear con un mensaje claro
git commit -m "♿ Fix accessibility issues

- Make card visible to screen readers
- Add ARIA labels to navbar links"
```

### Paso 5: Enviar a Tu Fork

```bash
# Enviar la rama a TU fork
git push origin fix-accessibility-issues
```

### Paso 6: Crear el PR en GitHub

**Opción A: Interfaz Web de GitHub**

Tras hacer push, GitHub muestra un banner:
```
fix-accessibility-issues had recent pushes
[Compare & pull request]
```

**Opción B: GitHub CLI**

```bash
gh pr create --title "Fix accessibility issues" --body "Description here"
```

**Opción C: VS Code**

Haz clic en el botón del panel de Source Control

### Paso 7: Rellenar la Plantilla del PR

**Buen Título de PR:**

```bash
# Bien
♿ Fix accessibility issues in navigation
🐛 Fix login validation bug
✨ Add dark mode toggle

# Mal
Update files
Changes
Fix stuff
```

**Buena Descripción de PR:**

```markdown
## Summary
Fixes accessibility issues found via Lighthouse audit.

## Changes
- Changed `<div hidden>` to `<article>` for screen reader visibility
- Added `aria-label` attributes to navigation links
- Improved color contrast for better readability

## Before/After
### Before
![Accessibility score: 83](before.png)

### After
![Accessibility score: 100](after.png)

## Testing
- ✅ Tested with screen reader (VoiceOver)
- ✅ Lighthouse audit passes
- ✅ Visual appearance unchanged
```

**Adjuntos:**

- Capturas de pantalla (antes/después)
- Grabaciones de pantalla (mostrar la funcionalidad)
- Informes de Lighthouse
- Resultados de tests

---

## 53. Buenas Prácticas de PR

**Reglas de Oro:**

### 1. PRs Pequeños y Enfocados

✅ **Bien**: 3-20 líneas cambiadas
⚠️ **Aceptable**: 20-100 líneas
❌ **Mal**: Más de 100 líneas

**¿Por Qué Pequeños?**
- Más fácil de revisar
- Más rápido de fusionar
- Menos probabilidad de conflictos
- Propósito más claro

### 2. Un Propósito por PR

```bash
# Bien - PRs separados
PR #1: Fix accessibility
PR #2: Add dark mode
PR #3: Update documentation

# Mal - Un PR masivo
PR #1: Fix accessibility + dark mode + docs + refactor + new feature
```

### 3. Comprueba CONTRIBUTING.md Primero

```bash
# Busca las guías de contribución
- CONTRIBUTING.md
- CODE_OF_CONDUCT.md
- README.md (sección Contributing)
```

**Guías Típicas:**

- Requisitos de estilo de código
- Formato de mensajes de commit
- Nombrado de ramas
- Requisitos de testing
- Plantilla de PR

**Ejemplo - CONTRIBUTING.md de Astro:**

```markdown
Prerequisites:
- Node.js 16.6+
- pnpm 7.0+

Development:
1. Fork repository
2. npm install
3. npm run dev
4. npm test

PR Requirements:
- Add tests for new features
- Pass existing tests
- Follow code style
- Write clear commit messages
```

### 4. Buenas Prácticas de Mensajes de Commit

**Formato:**

```bash
# Título (50 caracteres o menos)
Fix accessibility issues in navigation

# Cuerpo (opcional, ajustar a 72 caracteres)
Changed div elements to semantic HTML and added
ARIA labels for screen reader compatibility.

Fixes #123
```

**Reglas:**

✅ Modo imperativo ("Fix" no "Fixed" ni "Fixes")
✅ Sin punto al final del título
✅ Primera letra en mayúscula
✅ Referencia issues (#123)
✅ Explica el PORQUÉ, no solo el QUÉ

**Mal:**

```bash
git commit -m "changed some stuff."
git commit -m "updates"
git commit -m "Fixed the bug."
```

**Bien:**

```bash
git commit -m "Fix navigation keyboard accessibility"
git commit -m "Add dark mode toggle"
git commit -m "Remove deprecated API calls"
```

**Emojis (Opcional):**

Muchos proyectos usan conventional commits con emojis:

```bash
✨ feat: Add new feature
🐛 fix: Fix bug
📝 docs: Update documentation
♻️  refactor: Refactor code
✅ test: Add tests
🎨 style: Format code
⚡ perf: Performance improvement
♿ a11y: Accessibility
```

### 5. Prueba Antes de Enviar

```bash
# Ejecutar los tests
npm test
npm run build

# Comprobar el linting
npm run lint

# Ejecutar localmente
npm run dev
```

### 6. Permitir Ediciones de los Mantenedores

Al crear el PR, marca:
```
☑ Allow edits from maintainers
```

Esto permite a los mantenedores:
- Arreglar pequeños problemas
- Resolver conflictos de merge
- Acelerar el proceso de merge

### 7. Responder a las Revisiones

**Cuando el Mantenedor Comenta:**

✅ Responde con prontitud
✅ Haz los cambios solicitados
✅ Explica tu razonamiento (con cortesía)
✅ Marca las conversaciones como resueltas
✅ Envía los cambios a la misma rama

**Si el PR es Rechazado:**

✅ Pide feedback
✅ Aprende de ello
✅ No te lo tomes personalmente
✅ Prueba con otra contribución

---

## 54. Archivos CONTRIBUTING.md

**¿Qué es CONTRIBUTING.md?**

Archivo que explica cómo contribuir a un proyecto.

**Contenido Típico:**

1. **Requisitos Previos**
   ```markdown
   ## Prerequisites
   - Node.js 18+
   - pnpm 8.0+
   - Python 3.10+
   ```

2. **Instrucciones de Configuración**
   ```markdown
   ## Development Setup
   1. Fork repository
   2. Clone your fork
   3. Install dependencies: `pnpm install`
   4. Run dev server: `pnpm dev`
   ```

3. **Estructura del Proyecto**
   ```markdown
   ## Project Structure
   /src
     /components  - React components
     /utils       - Helper functions
     /types       - TypeScript types
   ```

4. **Estándares de Código**
   ```markdown
   ## Code Style
   - Use TypeScript
   - Run Prettier: `pnpm format`
   - Follow Airbnb style guide
   ```

5. **Testing**
   ```markdown
   ## Testing
   - Add tests for new features
   - Run tests: `pnpm test`
   - Coverage must stay above 80%
   ```

6. **Guías de Commit**
   ```markdown
   ## Commits
   - Follow Conventional Commits
   - Format: `type(scope): description`
   - Examples: `feat(api): add user endpoint`
   ```

7. **Proceso de PR**
   ```markdown
   ## Pull Requests
   1. Create feature branch
   2. Make changes
   3. Add tests
   4. Update documentation
   5. Submit PR with description
   ```

**Encontrando CONTRIBUTING.md:**

```bash
# Normalmente en la raíz del repositorio
/CONTRIBUTING.md
/docs/CONTRIBUTING.md
/.github/CONTRIBUTING.md
```

**Si No Hay CONTRIBUTING.md:**

1. Comprueba README.md por si tiene guías
2. Mira los PRs recientes para ver patrones
3. Revisa el historial de commits por el estilo
4. Pregunta a los mantenedores en un issue/discussion

---

## 55. Guías de Mensajes de Commit

**La Regla de Oro:**

**Los títulos de commit son TÍTULOS, no oraciones**

❌ **No añadas puntos a los títulos**

```bash
# Mal
git commit -m "Fix navigation bug."
git commit -m "Add dark mode."

# Bien
git commit -m "Fix navigation bug"
git commit -m "Add dark mode"
```

**¿Por Qué Sin Punto?**

Los títulos de libros no tienen puntos:
- "The Great Gatsby" ✅
- "The Great Gatsby." ❌

Los títulos de commit son lo mismo:
- "Fix critical security bug" ✅
- "Fix critical security bug." ❌

**Mira los Propios Commits de Git:**

```bash
# Mira los commits oficiales de Git
git log --oneline

# Ejemplos (¡sin puntos!):
# merge: fix error messages
# commit: allow --no-edit
# push: support push options
```

**Anatomía de un Gran Commit:**

```bash
# Línea de título (imperativo, sin punto)
Add user authentication system

# Línea en blanco

# Cuerpo (opcional, explica el PORQUÉ)
Previous implementation used insecure session cookies.
New system implements JWT tokens with refresh mechanism.

# Pie (referencia issues)
Fixes #123
Related to #456
```

**Modo Imperativo:**

Piensa: "Este commit va a ___"

```bash
# Bien (imperativo)
Add feature
Fix bug
Update documentation
Remove deprecated code

# Mal (tiempo pasado)
Added feature
Fixed bug
Updated documentation
Removed deprecated code
```

**Guías de Longitud:**

- **Título**: 50 caracteres máximo
- **Línea del cuerpo**: 72 caracteres máximo
- **Cuerpo**: Explica qué y por qué, no cómo

**Prefijos Comunes:**

```bash
Add       - Nueva funcionalidad/archivo
Fix       - Corrección de bug
Update    - Modificar funcionalidad existente
Remove    - Eliminar código/archivo
Refactor  - Reestructurar el código
Docs      - Solo documentación
Test      - Añadir/actualizar tests
Style     - Formateo, sin cambio de código
Perf      - Mejora de rendimiento
Chore     - Tareas de mantenimiento
```

---

## 56. Sincronizar Tu Fork

**El Problema:**

El repositorio original se actualiza → Tu fork se queda atrás

```
Original (upstream): A--B--C--D--E
Tu fork (origin):    A--B--C
```

**Solución: Sincroniza Tu Fork**

### Método 1: UI Web de GitHub (Lo Más Fácil)

1. Ve a TU fork en GitHub
2. Verás un banner: "This branch is 5 commits behind upstream-owner:main"
3. Haz clic en el botón "Sync fork"
4. Haz clic en "Update branch"
5. ¡Listo!

### Método 2: Línea de Comandos

```bash
# 1. Traer del upstream
git fetch upstream

# 2. Cambiar a main
git switch main

# 3. Fusionar los cambios del upstream
git merge upstream/main

# 4. Enviar a tu fork
git push origin main
```

### Método 3: Pull desde el Upstream

```bash
# Un comando (fetch + merge)
git pull upstream main

# Enviar a tu fork
git push origin main
```

### Flujo de Sincronización Completo:

```bash
# Empieza en tu rama de funcionalidad
git switch fix-bug

# Sincroniza primero la rama main
git switch main
git pull upstream main
git push origin main

# Actualiza la rama de funcionalidad con la última main
git switch fix-bug
git merge main

# O rebase (historial más limpio)
git rebase main

# Enviar la rama actualizada
git push origin fix-bug --force-with-lease
```

**Cuándo Sincronizar:**

✅ Antes de empezar una nueva funcionalidad
✅ Antes de crear un PR
✅ Cuando el PR tiene conflictos de merge
✅ Periódicamente (semanal/mensual)

---

## 57. GitHub CLI (gh)

**¿Qué es GitHub CLI?**

Herramienta oficial de línea de comandos para operaciones de GitHub.

**Instalación:**

```bash
# macOS
brew install gh

# Windows
winget install GitHub.cli
# o
scoop install gh

# Linux
sudo apt install gh  # Debian/Ubuntu
```

**Autenticación:**

```bash
# Iniciar sesión en GitHub
gh auth login

# Sigue las indicaciones:
# 1. GitHub.com o Enterprise
# 2. HTTPS o SSH
# 3. Login vía navegador o token
```

**Clonar con Beneficios:**

```bash
# git clone normal
git clone git@github.com:you/project.git
# Solo configura origin

# Clone de GitHub CLI
gh repo clone you/project
# ¡Configura TANTO origin COMO upstream (para forks)!
```

**Operaciones Comunes:**

### Repositorios

```bash
# Clonar un repositorio
gh repo clone owner/repo

# Crear un repositorio
gh repo create my-project

# Ver un repositorio
gh repo view owner/repo

# Fork de un repositorio
gh repo fork owner/repo
```

### Pull Requests

```bash
# Crear un PR
gh pr create --title "Fix bug" --body "Description"

# Crear un PR (interactivo)
gh pr create

# Listar PRs
gh pr list

# Ver un PR
gh pr view 123

# Hacer checkout de un PR localmente
gh pr checkout 123

# Revisar un PR
gh pr review 123 --approve
gh pr review 123 --request-changes

# Fusionar un PR
gh pr merge 123
```

### Issues

```bash
# Crear un issue
gh issue create

# Listar issues
gh issue list

# Ver un issue
gh issue view 123

# Cerrar un issue
gh issue close 123
```

### Comandos de Flujo de Trabajo:

```bash
# Ver el repositorio en el navegador
gh repo view --web

# Ver el PR en el navegador
gh pr view --web

# Crear un PR desde la rama actual
gh pr create --web

# Clonar y auto-configurar el fork
gh repo fork owner/repo --clone
```

**¿Por Qué Usar GitHub CLI?**

✅ Más rápido que la interfaz web
✅ Flujos de trabajo automatizables (scripts)
✅ Configura automáticamente los upstreams
✅ Funciona sin conexión (datos cacheados)
✅ Integrado con Git
✅ Sin cambio de contexto

---

## 58. GitHub Desktop

**¿Qué es GitHub Desktop?**

Aplicación oficial con interfaz gráfica para Git y GitHub.

**Descarga:**

[desktop.github.com](https://desktop.github.com)

**Plataformas:**
- macOS (Intel y Apple Silicon)
- Windows
- Linux (versión de la comunidad)

**Funciones Clave:**

### 1. Operaciones Visuales de Git

```
Sin necesidad de terminal:
- Clonar repositorios
- Crear ramas
- Poner cambios en staging
- Commitear
- Push/Pull
- Resolver conflictos
- Ver el historial
```

### 2. Fácil de Aprender

- Tutorial integrado
- Visor de diff visual
- UI de resolución de conflictos
- Visualización de ramas

### 3. Integración con GitHub

- Autenticación automática
- Crear PRs
- Ver issues
- Fork de repositorios
- Sincronización con un clic

**Flujo de Trabajo Básico:**

1. **Clonar un Repositorio**
   ```
   File → Clone Repository
   Buscar el repositorio de GitHub
   Elegir la ubicación
   Clone
   ```

2. **Crear una Rama**
   ```
   Current Branch → New Branch
   Introducir el nombre
   Create
   ```

3. **Hacer Cambios**
   ```
   Editar archivos en el editor
   Los cambios aparecen en GitHub Desktop
   Revisar los diffs
   ```

4. **Commitear**
   ```
   Introducir el mensaje de commit
   Commit to branch
   ```

5. **Push**
   ```
   Botón Push origin
   ```

6. **Crear un PR**
   ```
   Branch → Create Pull Request
   Abre el navegador con el formulario del PR
   ```

**¿Quién Debería Usar GitHub Desktop?**

✅ Principiantes aprendiendo Git
✅ Personas que aprenden mejor de forma visual
✅ Quienes prefieren GUIs sobre la terminal
✅ Quienes quieren flujos de trabajo simples
✅ Usuarios ocasionales de Git

**Alternativas:**

- **GitKraken**: Más funciones, de pago
- **SourceTree**: Gratis, potente
- **Fork**: macOS/Windows, UI limpia
- **VS Code**: Soporte de Git integrado
- **LazyGit**: UI de terminal

---

## 59. GitHub Codespaces

**¿Qué es Codespaces?**

Entorno de desarrollo basado en la nube (VS Code en el navegador).

**Funciones Clave:**

✅ VS Code completo en el navegador
✅ Sin configuración local necesaria
✅ Entornos preconfigurados
✅ 60 horas/mes GRATIS
✅ Máquinas de 2-4 núcleos disponibles

**Cómo Usarlo:**

### Método 1: Desde el Repositorio

```
1. Ve al repositorio de GitHub
2. Haz clic en el botón verde "Code"
3. Selecciona la pestaña "Codespaces"
4. Haz clic en "Create codespace on main"
5. Espera a que cargue el entorno
6. ¡Empieza a programar!
```

### Método 2: Desde un PR

```
1. Ve un Pull Request
2. Haz clic en el desplegable "Code"
3. "Open with Codespaces"
4. Revisa el código en un IDE completo
```

**Qué Proporciona Codespaces:**

```
✅ Entorno Linux completo
✅ Extensiones de VS Code
✅ Acceso a terminal
✅ Git preconfigurado
✅ Node.js, Python, etc. preinstalados
✅ Reenvío de puertos (previsualizar apps)
✅ 32GB de espacio en disco
```

**Perfecto Para:**

✅ Correcciones/contribuciones rápidas
✅ Probar los PRs de otros
✅ Sin configuración local
✅ Máquina distinta
✅ Tablet/Chromebook
✅ Aprendizaje/tutoriales

**Ejemplo de Flujo de Trabajo:**

```bash
1. Encuentra un issue en el repositorio
2. Haz fork del repositorio
3. Crea un Codespace en tu fork
4. Haz cambios en el navegador
5. Commitea en el Codespace
6. Crea un PR desde el Codespace
7. Elimina el Codespace cuando termines
```

**Creando un PR desde el Codespace:**

```
1. Haz cambios
2. Pon los archivos en staging (panel de Source Control)
3. Commitea
4. Push
5. GitHub sugiere "Create PR"
6. Rellena la plantilla del PR
7. Envía
```

**Costo:**

- **Nivel gratuito**: 60 horas/mes (máquina de 2 núcleos)
- **Pro**: 90 horas/mes
- **Team**: 180 horas/mes
- Deja de cobrar cuando está inactivo (se detiene automáticamente tras 30 min)

**Cuándo NO Usarlo:**

❌ Cálculos pesados
❌ Builds grandes
❌ Tareas de larga duración
❌ Necesitas hardware específico
❌ Trabajo sin conexión

---

## 60. git switch vs git checkout

**La Filosofía:**

**Filosofía Unix**: Cada comando debe hacer UNA cosa bien.

**Problema con `git checkout`:**

```bash
git checkout branch-name   # Cambiar de rama
git checkout -- file.txt   # Descartar cambios
git checkout -b new-branch # Crear rama
git checkout tag-name      # Hacer checkout de un tag
git checkout commit-hash   # Desprender HEAD
```

Un comando, DEMASIADOS propósitos = viola la filosofía Unix

**Solución: git switch (Git 2.23+)**

### git switch

**Propósito**: SOLO cambiar/crear ramas

```bash
# Cambiar a una rama existente
git switch main

# Crear y cambiar
git switch -c new-feature

# Cambiar a la rama anterior
git switch -

# Crear desde un remoto
git switch -c local-name origin/remote-name
```

### git restore

**Propósito**: SOLO restaurar archivos

```bash
# Descartar los cambios de un archivo
git restore file.txt

# Restaurar desde un commit específico
git restore --source=abc123 file.txt

# Sacar un archivo del staging
git restore --staged file.txt

# Restaurar todos los archivos
git restore .
```

**Comparación:**

| Tarea | Antiguo (checkout) | Nuevo (switch/restore) |
|------|---------------|---------------------|
| Cambiar de rama | `git checkout main` | `git switch main` |
| Crear rama | `git checkout -b feat` | `git switch -c feat` |
| Descartar cambios | `git checkout -- file.txt` | `git restore file.txt` |
| Sacar del staging | `git checkout HEAD file.txt` | `git restore --staged file.txt` |

**¿Cuál Usar?**

✅ **Usa `git switch`** (moderno, propósito claro)
✅ **Usa `git restore`** (intención explícita)
⚠️ **`git checkout` aún funciona** (compatible hacia atrás)

**Por Qué Importa switch:**

1. **Claridad**: Los comandos se autodocumentan
2. **Seguridad**: Más difícil descartar cambios por accidente
3. **Aprendizaje**: Más fácil para principiantes
4. **Buena Práctica**: Recomendado por el proyecto Git

**Recomendación del Equipo de Git:**

> "Usa git switch para cambiar de rama y git restore para restaurar archivos. git checkout hace ambas cosas y más, lo que puede ser confuso."

---

## 61. Múltiples Repositorios Remotos

**Más allá de origin y upstream:**

¡Puedes tener repositorios remotos ILIMITADOS!

**Escenarios Comunes:**

### Escenario 1: Colaboración en Equipo

```bash
# Tu fork
origin    → github.com/you/project

# Proyecto original
upstream  → github.com/original/project

# Fork de un compañero
teammate  → github.com/teammate/project

# Otro compañero
john      → github.com/john/project
```

**¿Por qué?**

Traer cambios específicos de compañeros antes de que se fusionen:

```bash
# Añadir el fork del compañero
git remote add teammate git@github.com:teammate/project.git

# Traer sus cambios
git fetch teammate

# Comprobar su rama
git log teammate/feature-branch

# Fusionar sus cambios
git merge teammate/feature-branch
```

### Escenario 2: Múltiples Plataformas de Alojamiento

```bash
# GitHub
github    → github.com/you/project

# GitLab
gitlab    → gitlab.com/you/project

# Bitbucket
bitbucket → bitbucket.org/you/project

# Autoalojado
company   → git.company.com/you/project
```

**Sincronizar a todos:**

```bash
# Enviar a todos los remotos
git push github main
git push gitlab main
git push bitbucket main

# O crear un alias
git config alias.pushall '!git push github main && git push gitlab main'
git pushall
```

### Escenario 3: Múltiples Forks

```bash
# Fork personal
personal  → github.com/you/project

# Fork de la organización del trabajo
work      → github.com/company/project

# Fork de código abierto
opensource → github.com/oss-org/project
```

**Gestionando Remotos:**

```bash
# Listar todos los remotos
git remote -v

# Añadir un remoto
git remote add name url

# Eliminar un remoto
git remote remove name

# Renombrar un remoto
git remote rename old-name new-name

# Cambiar la URL
git remote set-url name new-url

# Mostrar la info del remoto
git remote show origin
```

**Ejemplo Práctico:**

```bash
# 1. Clona tu fork
git clone git@github.com:you/react.git

# 2. Añade el repositorio original
git remote add upstream git@github.com:facebook/react.git

# 3. Añade a un compañero para colaborar
git remote add teammate git@github.com:teammate/react.git

# 4. Ver todos los remotos
git remote -v
# origin    git@github.com:you/react.git
# upstream  git@github.com:facebook/react.git
# teammate  git@github.com:teammate/react.git

# 5. Traer de todos
git fetch --all

# 6. Traer de un remoto específico
git pull upstream main
git pull teammate feature-branch

# 7. Enviar a un remoto específico
git push origin main
```

**Estructura de Repositorios Remotos:**

```
Tu Repositorio Local
├── origin (tu fork)
├── upstream (original)
├── teammate1 (colaborador 1)
├── teammate2 (colaborador 2)
└── company (organización)
```

**Buenas Prácticas:**

✅ Nombra los remotos de forma descriptiva
✅ `origin` = tu fork
✅ `upstream` = repo original
✅ Otros nombres = propósito específico
✅ Documenta el propósito del remoto
✅ Elimina los remotos que no uses

---

## 📚 Recursos

**Enlaces Esenciales:**

- **Sitio Oficial de Git**: [git-scm.com](https://git-scm.com)
- **Libro Pro Git**: [git-scm.com/book](https://git-scm.com/book)
- **Documentación de GitHub**: [docs.github.com](https://docs.github.com)
- **Hoja de Referencia de Git**: [training.github.com/downloads/github-git-cheat-sheet](https://training.github.com/downloads/github-git-cheat-sheet/)

**Contribuir a Código Abierto:**
- **Good First Issue**: [goodfirstissue.dev](https://goodfirstissue.dev)
- **Good First Issues**: [goodfirstissues.com](https://goodfirstissues.com)
- **GitHub CLI**: [cli.github.com](https://cli.github.com)
- **GitHub Desktop**: [desktop.github.com](https://desktop.github.com)

---

## Comandos de Referencia Rápida

```bash
# Configuración
git config --global user.name "Your Name"
git config --global user.email "email@example.com"

# Inicializar
git init

# Estado e Historial
git status
git log
git log --oneline --graph

# Staging y Commit
git add .
git commit -m "Message"

# Ramas
git branch feature
git switch feature
git merge feature
git branch -d feature

# Deshacer
git checkout file.txt
git reset HEAD file.txt
git reset --hard abc123

# Remoto
git remote add origin url
git clone url
git pull
git push

# Stash
git stash
git stash pop
git stash list
```

---

## Resumen

Esta guía cubre Git y GitHub desde los fundamentos hasta prácticas profesionales de DevOps:

**Parte 1 - Fundamentos de Git y GitHub:**
- Fundamentos de Git desde la instalación hasta comandos avanzados
- Gestión de repositorios locales
- Flujos de trabajo con ramas y merging
- Resolución de conflictos
- Fundamentos de GitHub y configuración de SSH
- Temas avanzados: cherry-pick, rebase, GitHub Pages

**Parte 2 - GitHub Actions CI/CD:**
- Arquitectura de Workflow, Jobs y Steps
- Disparadores: push, pull_request, schedule (cron)
- Usando actions del Marketplace
- Gestión de secretos
- Automatización de build y push de Docker
- Automatización de despliegue en Kubernetes
- Ver logs y depurar
- Ejemplos de CI/CD del mundo real

**Parte 3 - Contribución a Código Abierto:**
- Encontrar proyectos para contribuir
- Dominio del flujo de trabajo de fork
- Crear Pull Requests de calidad
- Buenas prácticas para la colaboración
- GitHub CLI, Desktop y Codespaces
- Sincronizar forks y gestionar múltiples remotos

**Lo Que Aprenderás:**
- ✅ Dominio del control de versiones con Git
- ✅ Flujos de trabajo de colaboración en GitHub
- ✅ Automatización de CI/CD con GitHub Actions
- ✅ Despliegue con Docker y Kubernetes
- ✅ Habilidades de contribución a código abierto
- ✅ Prácticas profesionales de DevOps

---

**Última Actualización**: 2026-08-31
