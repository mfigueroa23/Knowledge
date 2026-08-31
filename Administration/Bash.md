# Bash y Terminal - De Cero a Avanzado

## 📌 Metadatos del Documento

**Última Actualización:** 2026-08-31
**Versión de Bash Cubierta:** 3.2+ (compatible con Bash 5.2+)
**Requisitos Previos:**
- Conocimientos básicos de informática
- Emulador de terminal instalado
- No se requiere experiencia previa en programación

**Nivel de Habilidad:** Principiante a Avanzado

**Cobertura de Plataformas:**
- ✅ Linux (todas las distribuciones)
- ✅ macOS (Bash 3.2 por defecto, actualizable a 5.2+)
- ✅ Windows (WSL 2 con Ubuntu/Debian)

---

## 🎯 Cuándo Usar Este Conocimiento

**Usa esta guía cuando necesites:**
- Navegar y gestionar servidores Linux/Unix (DevOps, SysAdmin)
- Escribir scripts de automatización para pipelines de CI/CD
- Realizar tareas de administración de sistemas
- Procesar archivos de texto y análisis de logs
- Configurar entornos de desarrollo
- Depurar problemas de producción vía SSH
- Integrarte con flujos de trabajo de Git, Docker y Kubernetes
- Trabajar con agentes de IA que ejecutan comandos de terminal
- Gestionar infraestructura en la nube (AWS, GCP, Azure)
- Realizar auditorías de seguridad y pruebas de penetración
- Procesar archivos por lotes y transformar datos
- Programar tareas automatizadas con cron

**Escenarios de Referencia Rápida:**

| Escenario | Ir a la Sección |
|----------|----------------|
| Necesitas encontrar archivos por nombre/tamaño/permisos | [Sección 13: Búsqueda y Localización](#13-búsqueda-y-localización) |
| Procesar archivos CSV/JSON/logs | [Sección 12: Comandos de Procesamiento de Texto](#12-comandos-de-procesamiento-de-texto) |
| Configurar acceso SSH | [Sección 14: Comandos de Red](#14-comandos-de-red) |
| Gestionar permisos de archivos | [Sección 15: Seguridad y Permisos](#15-seguridad-y-permisos) |
| Escribir tu primer script | [Sección 17: Fundamentos de Shell Scripting](#17-fundamentos-de-shell-scripting) |
| Seguir buenas prácticas | [Sección 18: Buenas Prácticas Modernas de Bash](#18-buenas-prácticas-modernas-de-bash) |

---

## 📋 Tabla de Contenidos

1. [Introducción](#1-introducción)
2. [Shell vs Terminal](#2-shell-vs-terminal)
3. [¿Por Qué Bash?](#3-por-qué-bash)
4. [Historia de Bash](#4-historia-de-bash)
5. [Instalación en Todos los Sistemas Operativos](#5-instalación-en-todos-los-sistemas-operativos)
6. [Emuladores de Terminal](#6-emuladores-de-terminal)
7. [Primeros Comandos - Hola Mundo](#7-primeros-comandos---hola-mundo)
8. [Comandos de Navegación](#8-comandos-de-navegación)
9. [Navegación del Sistema de Archivos](#9-navegación-del-sistema-de-archivos)
10. [La Terminal en la Era de la IA](#10-la-terminal-en-la-era-de-la-ia)
11. [Operaciones con Archivos](#11-operaciones-con-archivos)
12. [Comandos de Procesamiento de Texto](#12-comandos-de-procesamiento-de-texto)
13. [Búsqueda y Localización](#13-búsqueda-y-localización)
14. [Comandos de Red](#14-comandos-de-red)
15. [Seguridad y Permisos](#15-seguridad-y-permisos)
16. [Ejemplos Prácticos de OverTheWire](#16-ejemplos-prácticos-de-overthewire)
17. [Fundamentos de Shell Scripting](#17-fundamentos-de-shell-scripting)
18. [Buenas Prácticas Modernas de Bash](#18-buenas-prácticas-modernas-de-bash)
19. [Apéndice: Hoja de Referencia Rápida](#apéndice-hoja-de-referencia-rápida)

---

## Descripción General

Bash es el lenguaje de scripting más utilizado del mundo para trabajar desde la línea de comandos. Es el estándar de la industria sin importar si trabajas en Linux, Mac o Windows. La línea de comandos es la forma más natural de interactuar con la administración de sistemas, crear scripts, automatizar tareas e integrar tu entorno de desarrollo con todo tipo de herramientas.

### ¿Qué es Bash?

- **Lenguaje de scripting** para la interacción por línea de comandos
- **Estándar de la industria** en todos los sistemas operativos
- **Intérprete de shell** - el intérprete de comandos más popular y potente
- **Lenguaje universal de la computación** para desarrollo de software, DevOps, ciencia de datos y ciberseguridad
- **Preparado para la integración con IA** - esencial para las interacciones modernas con agentes de IA

### Características Principales

- ✅ Universal en Linux, macOS y Windows (WSL)
- ✅ Estándar para la gestión de servidores e infraestructura en la nube
- ✅ Esencial para herramientas de despliegue y control de versiones
- ✅ Base de la automatización y el scripting
- ✅ Requerido en DevOps, ciencia de datos y ciberseguridad
- ✅ Crítico para las interacciones con agentes de IA y la automatización

---

## 1. Introducción

### ¿Por Qué Aprender Bash?

En el mundo real del desarrollo de software, DevOps, ciencia de datos y ciberseguridad, la interfaz gráfica no siempre es una opción:

- **Servidores** - La infraestructura funciona por línea de comandos
- **Nube** - Los servicios en la nube se controlan vía terminal
- **Herramientas de despliegue** - Los pipelines de CI/CD usan scripts de bash
- **Control de versiones** - Git y otras herramientas operan por línea de comandos

**El lenguaje universal de la computación.**

### La Revolución de la IA y Bash

Con la revolución de la IA, el conocimiento de la terminal se ha vuelto aún más crítico:

- **Los agentes de IA** ejecutan acciones automáticas desde la línea de comandos
- **Las interacciones con modelos** suelen suceder a través de comandos de terminal
- **El control de la automatización** requiere entender qué está pasando en cada momento
- **Diferenciación profesional** - La experiencia en terminal separa a los principiantes de los profesionales

**La terminal está recuperando protagonismo gracias a la IA.**

---

## 2. Shell vs Terminal

### Entendiendo los Conceptos Fundamentales

#### ¿Qué es una Shell?

**Shell** = Programa intérprete de comandos

- Programa que interpreta los comandos del usuario
- Traduce comandos de texto en acciones del sistema
- Término genérico para intérprete de comandos

**Piénsalo así:**
- "Lenguajes de programación" es genérico
- Python, JavaScript, Java son lenguajes específicos
- "Shell" es genérico
- Bash, Zsh, PowerShell son shells específicas

#### ¿Qué es una Terminal?

**Terminal** = El programa que abres

- Interfaz gráfica (aunque sea basada en texto)
- Aplicación que ejecuta una shell
- Ventana visual donde escribes comandos

### Tipos de Shells

Ejemplos comunes de shells:

| Shell | Plataforma | Descripción |
|-------|----------|-------------|
| **Bash** | Linux, macOS, Unix | La más popular, estándar de la industria |
| **Zsh** | macOS (por defecto) | Evolución moderna de Bash |
| **sh** | Sistemas Unix | Bourne Shell original |
| **csh** | BSD Unix | Sintaxis similar a C |
| **PowerShell** | Windows | La shell de Microsoft |

### Tipos de Terminales

**Terminales integradas:**
- Windows Terminal (Windows)
- Terminal.app (macOS)
- GNOME Terminal (Linux)

**Terminales de terceros:**
- Ghostty - Rápida, acelerada por GPU, moderna (multiplataforma)
- iTerm2 - Terminal popular de macOS
- Alacritty / WezTerm - Multiplataforma, aceleradas por GPU
- Warp - Terminal potenciada por IA

**Multiplexores / gestores de espacios de trabajo:** Para sesiones persistentes y paneles divididos, combina la terminal con un multiplexor. `herdr` gestiona paneles y sesiones (un gestor moderno de espacios de trabajo de terminal orientado a agentes de codificación con IA); tmux y zellij son otras opciones.

---

## 3. ¿Por Qué Bash?

### Razones para Elegir Bash

#### 1. Estándar de la Industria

- **Linux** - Shell por defecto
- **Unix** - Intérprete estándar
- **macOS** - Basado en Unix (Bash/Zsh)
- **Servidores** - La mayoría ejecuta Linux
- **Infraestructura** - Controlada vía Bash

**La mayoría de la documentación asume un entorno Bash/Unix.**

#### 2. Portabilidad Multiplataforma

- Los scripts funcionan en sistemas Unix
- Modificaciones mínimas entre Linux y macOS
- WSL lleva Bash a Windows
- Escribe una vez, ejecuta en cualquier lugar (sistemas tipo Unix)

#### 3. Comunidad Masiva

- **Décadas de desarrollo** - Desde 1989
- **Documentación extensa** - Recursos infinitos
- **Estándares sólidos** - Buenas prácticas bien definidas
- **Integración perfecta con herramientas** - Ecosistema Unix

#### 4. Compatibilidad Universal

Los comandos aprendidos en Bash tienen equivalentes en otras shells:
- ¿Moverse entre directorios? Similar entre shells
- ¿Operaciones básicas? Conocimiento transferible
- Aprender Bash = Entender los fundamentos de las shells

**Como aprender programación:**
- Domina Python → Aprender JavaScript se vuelve más fácil
- Domina Bash → Aprender Zsh/PowerShell se vuelve más fácil

### Bash vs Otras Shells

#### Bash vs Zsh

**Zsh:**
- Evolución moderna de Bash
- Contiene todo lo que tiene Bash + extras
- Por defecto en macOS (desde Catalina)
- 99% compatible con Bash

**Conclusión:** Aprender Bash = Aprender la base de Zsh

#### Bash vs PowerShell

**PowerShell:**
- Por defecto en Windows
- Enfoque orientado a objetos
- Potente para la administración de Windows

**Sin embargo:**
- Sintaxis diferente
- Menos portable a sistemas Unix
- Bash es más común en la industria tecnológica

### Cuándo Usar Cada Shell

**Usa Bash para:**
- ✅ Gestión de servidores Linux/Unix
- ✅ Scripts multiplataforma
- ✅ DevOps y CI/CD
- ✅ Aprender los fundamentos de las shells
- ✅ Flujos de trabajo estándar de la industria

**Usa PowerShell para:**
- ✅ Administración específica de Windows
- ✅ Integración con .NET
- ✅ Automatización de Windows

**Usa Zsh para:**
- ✅ Desarrollo en macOS
- ✅ Funcionalidades mejoradas
- ✅ Ecosistemas de plugins (Oh My Zsh)

---

## 4. Historia de Bash

### Orígenes y Evolución

**Año de Lanzamiento:** 1989
- **Más de 35 años** como estándar de la industria
- Nacido del Proyecto GNU
- Licencia GPL (código abierto)

### Etimología

**Bash** = **B**ourne **A**gain **Sh**ell

- Evolución de la "Bourne Shell" original (sh)
- Creada por Brian Fox para el Proyecto GNU
- Nombrada como un juego de palabras sobre la shell original

### Contexto Histórico

**Bourne Shell (sh):**
- Creada por Stephen Bourne en Bell Labs
- Shell original de Unix
- Base de las shells modernas

**Innovación de Bash:**
- Mejoró la funcionalidad de la Bourne Shell
- Añadió características de programación
- Mejoró la interacción con el usuario
- Mantuvo compatibilidad hacia atrás

### Cumplimiento de POSIX

**POSIX** = Portable Operating System Interface

- Bash cumple con los estándares POSIX
- Garantiza la portabilidad de los scripts
- Compatible con otras shells POSIX
- Permite compatibilidad entre sistemas

### Integración con el Proyecto GNU

Bash surgió dentro del **Proyecto GNU** (GNU's Not Unix):
- Parte del movimiento de software libre
- Apoya la filosofía Unix
- Fundamento del ecosistema Linux
- Habilita la infraestructura de código abierto

**Hoy en día:**
- Sigue en mantenimiento activo
- Se actualiza continuamente
- Base de la computación moderna
- Usado en miles de millones de dispositivos

---

## 5. Instalación en Todos los Sistemas Operativos

### Linux y macOS

**Buenas noticias:** ¡Bash viene preinstalado!

#### Verificar la Versión de Bash

```bash
bash --version
# Salida: GNU bash, version X.X.X
```

#### Nota para macOS

**Shell por defecto:** Zsh (desde macOS Catalina)
**¿Bash sigue disponible?:** Sí, totalmente funcional

**Cambiar a Bash:**
```bash
chsh -s /bin/bash
```

**Sesión temporal de Bash:**
```bash
bash
```

---

### Instalación en Windows (WSL)

#### ¿Qué es WSL?

**WSL** = Windows Subsystem for Linux

- Ejecuta Linux en Windows de forma nativa
- Accede a Bash directamente desde Windows
- Entorno Linux completo
- No requiere arranque dual

#### Pasos de Instalación

**1. Abre PowerShell como Administrador**

**2. Instala WSL:**
```powershell
wsl --install
```

Este único comando:
- Instala WSL 2
- Instala Ubuntu Linux
- Configura todo automáticamente

**3. Reinicia el Equipo**

Requerido tras la instalación

**4. Primer Arranque**

- La terminal de Ubuntu se abrirá automáticamente
- Crea un usuario y contraseña
- Entorno Linux listo

#### Verificar la Instalación

```bash
bash --version
echo $SHELL  # Muestra la shell actual
```

#### Acceder a los Archivos de Windows desde WSL

Tu unidad C: de Windows está montada en:
```bash
/mnt/c/
```

**Ejemplo:**
```bash
cd /mnt/c/Users/TuUsuario
ls  # ¡Ver archivos de Windows desde Bash!
```

### Alternativa: Git Bash (No Recomendado)

**Git para Windows** incluye Git Bash:
- Funcionalidad limitada de Bash
- No es soporte completo de Bash
- Le faltan muchos comandos

**Descarga:** [gitforwindows.org](https://gitforwindows.org)

**Limitaciones:**
- ❌ Implementación incompleta de Bash
- ❌ Faltan herramientas Unix

**Recomendación:** Usa WSL en su lugar para una experiencia completa de Bash.

---

## 6. Emuladores de Terminal

Bash se ejecuta dentro de un emulador de terminal. Cualquiera funciona — elige uno por velocidad, ergonomía y las funcionalidades que quieras (renderizado por GPU, ligaduras, divisiones, persistencia de sesiones).

### Elegir una Terminal

| Terminal | Notas |
|----------|-------|
| **Ghostty** | Rápida, acelerada por GPU, configuración mínima; excelente experiencia por defecto |
| **iTerm2** | Rica en funcionalidades, solo macOS |
| **WezTerm / Alacritty** | Multiplataforma, aceleradas por GPU, configuración como código |
| **Warp** | Sugerencias de comandos asistidas por IA y salida basada en bloques |

### Establecer Bash como tu Shell

La mayoría de los sistemas usan por defecto Zsh (macOS) o la shell por defecto de la distro. Si quieres Bash como tu shell de inicio de sesión:

```bash
# Listar las shells disponibles
cat /etc/shells

# Cambiar tu shell por defecto a Bash
chsh -s /bin/bash
```

### Persistencia de Sesiones con un Multiplexor

Un multiplexor mantiene vivas tus sesiones de shell y la distribución de paneles entre desconexiones (esencial al trabajar por SSH) y te permite dividir una ventana en varios paneles.

- **herdr** — gestor moderno de espacios de trabajo de terminal orientado a agentes de codificación con IA; gestiona paneles, sesiones y worktrees.
- **tmux** — multiplexor veterano y omnipresente.
- **zellij** — basado en Rust, con atajos de teclado descubribles desde el inicio.

```bash
# herdr: lanzar o adjuntarse a la sesión persistente
herdr

# herdr: adjuntarse a una sesión con nombre
herdr session attach <nombre>
```

---

## 7. Primeros Comandos - Hola Mundo

### El Comando Echo

**Propósito:** Imprimir texto en la terminal

#### Uso Básico

```bash
echo "Hello Bash"
```

**Salida:**
```
Hello Bash
```

**Qué pasó:**
- El comando `echo` imprime texto
- El texto entre comillas se muestra
- ¡Así de simple!

### Comandos de Información del Sistema

#### Verificar la Shell Actual

**Método 1:**
```bash
echo $SHELL
```

**Salida:**
```
/bin/bash
```

**Método 2:**
```bash
echo $0
```

**Salida:**
```
bash
```

**Qué hacen:**
- `$SHELL` - Variable de entorno con la ruta de la shell
- `$0` - Nombre de la shell actual
- Confirman que estás usando Bash

---

## 8. Comandos de Navegación

### Entendiendo los Sistemas de Archivos

Al trabajar con terminales, navegas por directorios (carpetas) usando comandos en lugar de hacer clic.

**Concepto clave:** Siempre estás "dentro de" un directorio cuando usas la terminal.

### Comandos Esenciales de Navegación

#### pwd - Print Working Directory

**Propósito:** Mostrar la ubicación actual

```bash
pwd
```

**Ejemplo de salida:**
```
/Users/username/workspace/hello-bash
```

**Cuándo usarlo:**
- Perdido en la estructura de directorios
- Verificar la ubicación actual
- Depuración de scripts

#### ls - Listar Contenidos

**Propósito:** Mostrar archivos y directorios de la ubicación actual

**Uso básico:**
```bash
ls
```

**Ejemplo de salida:**
```
curso  imagenes  LICENSE  README.md
```

**Qué ves:**
- Directorios (carpetas)
- Archivos
- Con colores (en la mayoría de terminales)

### Opciones del Comando ls

Los comandos pueden tener **opciones** (flags) que modifican su comportamiento.

**Sintaxis:** `comando -opción`

#### Opción: -l (Formato Largo)

```bash
ls -l
```

**Salida:**
```
total 8
drwxr-xr-x  5 user  staff   160 Feb 11 10:00 curso
drwxr-xr-x  3 user  staff    96 Feb 11 10:00 imagenes
-rw-r--r--  1 user  staff  1234 Feb 11 10:00 LICENSE
-rw-r--r--  1 user  staff  5678 Feb 11 10:00 README.md
```

**Muestra:**
- Permisos (drwxr-xr-x)
- Número de enlaces
- Propietario
- Grupo
- Tamaño del archivo
- Fecha de modificación
- Nombre del archivo/directorio

#### Opción: -a (Todos los Archivos)

```bash
ls -a
```

**Muestra:**
- Archivos normales
- **Archivos ocultos** (que empiezan con .)
- `.` (directorio actual)
- `..` (directorio padre)

**Ejemplos de archivos ocultos:**
- `.git` - Repositorio Git
- `.DS_Store` - Metadatos de macOS
- `.bashrc` - Configuración de Bash

#### Opción: -lh (Formato Largo, Legible para Humanos)

```bash
ls -lh
```

**Salida:**
```
total 16K
drwxr-xr-x  5 user  staff   160 Feb 11 10:00 curso
drwxr-xr-x  3 user  staff    96 Feb 11 10:00 imagenes
-rw-r--r--  1 user  staff  5.0K Feb 11 10:00 LICENSE
-rw-r--r--  1 user  staff   11K Feb 11 10:00 README.md
```

**Beneficios:**
- Tamaños de archivo en K, M, G (no en bytes)
- Más fácil de leer
- Mejor para archivos grandes

#### Combinar Opciones

```bash
ls -lah
```

Combina:
- `-l` Formato largo
- `-a` Mostrar todos los archivos
- `-h` Tamaños legibles para humanos

### cd - Cambiar de Directorio

**Propósito:** Moverse entre directorios

#### Uso Básico

```bash
cd nombre_directorio
```

**Ejemplo:**
```bash
cd curso
```

**Resultado:**
- Ahora estás dentro del directorio `curso`
- El prompt muestra la nueva ubicación

#### Verificar la Nueva Ubicación

```bash
pwd
```

**Salida:**
```
/Users/username/workspace/hello-bash/curso
```

---

## 9. Navegación del Sistema de Archivos

### Concepto de Jerarquía de Directorios

Los sistemas de archivos se organizan como una **estructura de árbol**:

```
/ (root)
├── Users
│   └── username
│       ├── Documents
│       ├── Downloads
│       └── workspace
│           └── project
└── etc
```

**La navegación es nivel por nivel** - te mueves por este árbol usando `cd`.

### Símbolos Especiales de Directorios

#### Directorio Actual: `.`

```bash
.
```

Representa: El directorio actual en el que estás

#### Directorio Padre: `..`

```bash
..
```

Representa: Un nivel arriba en la jerarquía

#### Directorio Home: `~`

```bash
~
```

Representa: El directorio home de tu usuario

#### Directorio Raíz: `/`

```bash
/
```

Representa: La cima del sistema de archivos

### Ejemplos de Navegación con cd

#### Ir a un Subdirectorio

```bash
cd curso
```

#### Subir un Nivel

```bash
cd ..
```

**Antes:**
```
/Users/username/workspace/project
```

**Después:**
```
/Users/username/workspace
```

#### Ir al Directorio Home

**Método 1:**
```bash
cd ~
```

**Método 2:**
```bash
cd
```

(Sin argumentos = directorio home)

#### Ir a la Raíz

```bash
cd /
```

#### Rutas Absolutas vs Relativas

**Ruta absoluta** (desde la raíz):
```bash
cd /Users/username/workspace/project
```

**Ruta relativa** (desde la ubicación actual):
```bash
cd curso/lecciones
```

### Buenas Prácticas de Navegación

**1. Usa el Autocompletado con Tab**
```bash
cd curs<TAB>
# Se completa a: cd curso/
```

**2. Verifica la Ubicación**
```bash
pwd  # Después de cd, verifica que estás donde esperas
```

**3. Usa .. para Volver**
```bash
cd ..  # Subir un nivel
cd ../..  # Subir dos niveles
```

**4. Combina con ls**
```bash
cd curso && ls  # Cambiar de directorio y listar contenidos
```

### Patrones Comunes de Navegación

**Volver al directorio anterior:**
```bash
cd -
```

**Ir a un subdirectorio específico:**
```bash
cd ~/workspace/projects/myproject
```

**Navegar de forma relativa al directorio actual:**
```bash
cd ../../other-folder
```

---

## 10. La Terminal en la Era de la IA

### La Revolución de la IA y la Línea de Comandos

**Realidad de 2025:** La terminal está recuperando protagonismo gracias a la IA.

### ¿Por Qué Terminal + IA?

#### 1. Ejecución de Agentes de IA

**Los agentes de IA ejecutan acciones vía línea de comandos:**
- Despliegues automatizados
- Generación de código
- Gestión de infraestructura
- Testing y validación

**Tu rol:**
- Entender qué está pasando
- Mantener el control
- Verificar las acciones de los agentes

#### 2. Interacciones con Modelos

**Muchas herramientas de IA prefieren la terminal:**
- Interacciones con APIs
- Procesamiento por lotes
- Scripts de automatización
- Pipelines de integración

#### 3. Requisito Profesional

**El conocimiento de la terminal separa:**
- A los principiantes de los profesionales
- A los desarrolladores junior de los senior
- El trabajo manual de la automatización

### Terminales Asistidas por IA

Las herramientas modernas de IA se encuentran con la terminal de dos formas:

- **Terminales nativas de IA** (p. ej. Warp) convierten lenguaje natural en comandos y explican errores en línea.
- **CLIs agénticas** (p. ej. Claude Code) se ejecutan dentro de cualquier terminal, leen tu código y ejecutan comandos con tu aprobación.

**Ejemplo — de lenguaje natural a comando:**
```
Prompt: "encuentra todos los archivos Python modificados en los últimos 7 días"
Genera: find . -name "*.py" -mtime -7
```

Sea cual sea la herramienta, los fundamentos siguientes siguen aplicando: tú sigues siendo responsable de revisar lo que se ejecuta.

### Futuro del Uso de la Terminal

**Tendencias:**
- Más desarrollo asistido por IA
- Flujos de trabajo centrados en la terminal
- Automatización en todas partes
- Lenguaje natural → Comandos

**Prepararse para el futuro:**
- Domina los fundamentos de Bash
- Entiende la estructura de los comandos
- Aprende patrones de automatización
- Practica con herramientas de IA

---

## 11. Operaciones con Archivos

### Lectura de Archivos

#### cat - Concatenar y Mostrar Archivos

**Propósito:** Mostrar el contenido de archivos

**Uso básico:**
```bash
cat nombre_archivo
```

**Ejemplo:**
```bash
cat readme.txt
```

**Leer desde el directorio actual:**
```bash
cat ./readme
```

#### Nombres de Archivo Especiales

**Archivos con guiones:**
```bash
cat ./-
```

**¿Por qué?** El guion (-) solo puede interpretarse como stdin/stdout. Usa el prefijo `./`.

**Archivos con espacios:**
```bash
cat ./spaces\ in\ this\ filename
# o
cat "spaces in this filename"
# o
cat 'spaces in this filename'
```

**Escapar espacios:**
- Barra invertida: `\ `
- Comillas simples: `'archivo con espacios'`
- Comillas dobles: `"archivo con espacios"`

#### Archivos Ocultos

**Listar archivos ocultos:**
```bash
ls -a
```

**Leer archivos ocultos:**
```bash
cat .hidden-file
cat ./inhere/...Hiding-From-You
```

**Los archivos ocultos empiezan con `.` (punto)**

### Información de Archivos

#### file - Determinar el Tipo de Archivo

```bash
file nombre_archivo
```

**Ejemplo:**
```bash
file data.bin
# Salida: data.bin: gzip compressed data
```

**Verificar varios archivos:**
```bash
file ./inhere/*
```

**Usar con find:**
```bash
find ./inhere -type f -exec file {} \;
```

### Manipulación de Archivos

#### Encauzamiento (piping) con xargs

**Ejecutar un comando sobre los resultados de find:**
```bash
find ./inhere | xargs file
```

**Qué hace xargs:**
- Toma la salida de un comando
- La pasa como argumentos a otro
- Permite encadenar comandos

**Ejemplo con cat:**
```bash
find ./inhere -name "*.txt" | xargs cat
```

---

## 12. Comandos de Procesamiento de Texto

### grep - Buscar Patrones de Texto

**Propósito:** Buscar patrones en archivos

**Uso básico:**
```bash
grep "patrón" nombre_archivo
```

**Ejemplo:**
```bash
cat data.txt | grep "millionth"
```

**Extraer una columna específica con awk:**
```bash
cat data.txt | grep "millionth" | awk '{print $2}'
```

### sort - Ordenar Líneas

**Propósito:** Organizar las líneas en orden

```bash
sort nombre_archivo
```

**Ejemplo con piping:**
```bash
cat data.txt | sort
```

### uniq - Eliminar Duplicados

**Propósito:** Filtrar líneas repetidas

**Importante:** Solo funciona con datos **ordenados**

```bash
sort file.txt | uniq
```

**Encontrar líneas únicas (que aparecen solo una vez):**
```bash
sort data.txt | uniq -u
```

**Contar ocurrencias:**
```bash
sort data.txt | uniq -c
```

### strings - Extraer Texto Legible

**Propósito:** Extraer cadenas legibles por humanos de archivos binarios

```bash
strings binary-file
```

**Ejemplo:**
```bash
cat data.txt | strings | grep "="
```

**Caso de uso:** Encontrar texto en archivos binarios o de datos

### base64 - Codificar/Decodificar

**Decodificar base64:**
```bash
base64 -d nombre_archivo
```

**Ejemplo:**
```bash
cat data.txt | base64 -d
```

**Codificar a base64:**
```bash
echo "Hello" | base64
```

### tr - Traducir Caracteres

**Propósito:** Traducir o eliminar caracteres

**Cifrado ROT13 (rotar 13 posiciones):**
```bash
cat data.txt | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
```

**Cómo funciona:**
- A-M → N-Z
- N-Z → A-M
- a-m → n-z
- n-z → a-m

**Eliminar caracteres:**
```bash
echo "hello123" | tr -d '0-9'
# Salida: hello
```

**Reemplazar caracteres:**
```bash
echo "hello" | tr 'a-z' 'A-Z'
# Salida: HELLO
```

### awk - Procesamiento de Texto

**Propósito:** Escaneo y procesamiento de patrones

**Imprimir una columna específica:**
```bash
awk '{print $2}' nombre_archivo
```

**Con grep:**
```bash
grep "patrón" file.txt | awk '{print $1}'
```

**Ejemplo:**
```bash
cat data.txt | grep "millionth" | awk '{print $2}'
```

### xxd - Herramienta de Volcado Hexadecimal

**Propósito:** Crear un volcado hexadecimal o revertirlo

**Revertir el volcado hexadecimal:**
```bash
xxd -r hexfile > output
```

**Ejemplo:**
```bash
xxd -r data.txt > data.bin
```

**Crear un volcado hexadecimal:**
```bash
xxd nombre_archivo
```

### diff - Comparar Archivos

**Propósito:** Mostrar las diferencias entre archivos

```bash
diff file1 file2
```

**Ejemplo:**
```bash
diff password.old password.new
```

**Formato de salida:**
```
42c42
< old_password
---
> new_password
```

---

## 13. Búsqueda y Localización

### find - Buscar Archivos

**Propósito:** Buscar archivos en la jerarquía de directorios

#### Sintaxis Básica

```bash
find [ruta] [opciones] [expresión]
```

#### Buscar por Tipo

**Solo archivos:**
```bash
find . -type f
```

**Solo directorios:**
```bash
find . -type d
```

#### Buscar por Nombre

```bash
find . -name "nombre_archivo"
```

**Sin distinguir mayúsculas/minúsculas:**
```bash
find . -iname "nombre_archivo"
```

#### Buscar por Tamaño

```bash
find . -size 1033c    # Exactamente 1033 bytes
find . -size +10M     # Mayor que 10 MB
find . -size -100k    # Menor que 100 KB
```

**Unidades de tamaño:**
- `c` - bytes
- `k` - kilobytes
- `M` - megabytes
- `G` - gigabytes

#### Buscar por Permisos

**No ejecutables:**
```bash
find . -type f ! -perm /a+x
```

**Archivos legibles:**
```bash
find . -type f -readable
```

**Archivos ejecutables:**
```bash
find . -type f -executable
```

**Permisos específicos:**
```bash
find . -perm 644
find . -perm -u+w  # Escribible por el usuario
```

#### Buscar por Propietario

**Por usuario:**
```bash
find / -user username
```

**Por grupo:**
```bash
find / -group groupname
```

**Combinado:**
```bash
find / -user bandit7 -group bandit6 -size 33c
```

#### Ejemplos Complejos de find

**Múltiples condiciones:**
```bash
find ./inhere/ -type f -readable ! -executable -size 1033c
```

**Ejecutar un comando sobre los resultados:**
```bash
find ./inhere/ -type f -size 1033c -exec cat {} \;
```

**Con xargs:**
```bash
find ./inhere/ -type f -size 1033c | xargs cat
```

#### Redirigir Errores

**Ocultar los errores de permiso denegado:**
```bash
find / -name "*.txt" 2>/dev/null
```

**Qué hace `2>/dev/null`:**
- `2>` - Redirige stderr (mensajes de error)
- `/dev/null` - Descarta la salida
- Mantiene la salida limpia

---

## 14. Comandos de Red

### SSH - Secure Shell

**Propósito:** Conectarse a servidores remotos de forma segura

#### Conexión Básica

```bash
ssh username@hostname
```

**Ejemplo:**
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

**Opciones:**
- `-p` - Especificar el puerto (por defecto: 22)

#### SSH con Clave Privada

```bash
ssh -i keyfile username@hostname
```

**Ejemplo:**
```bash
ssh -i ./sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```

**Permisos de la clave:**
```bash
chmod 600 keyfile  # Requerido para claves privadas
```

#### Ejecutar un Comando vía SSH

```bash
ssh user@host comando
```

**Ejemplo:**
```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 bash
```

**Caso de uso:** Evitar el cierre de sesión del .bashrc

### nc - Netcat

**Propósito:** Conexiones de red (TCP/UDP)

#### Conexión Básica

```bash
nc hostname port
```

**Ejemplo:**
```bash
nc localhost 30000
```

#### Modo de Escucha

```bash
nc -nlvp port
```

**Opciones:**
- `-n` - Sin resolución DNS
- `-l` - Modo de escucha
- `-v` - Detallado (verbose)
- `-p` - Número de puerto

**Ejemplo:**
```bash
nc -nlvp 4646
```

### ncat - Netcat con SSL/TLS

**Propósito:** Conexiones de red seguras

```bash
ncat --ssl hostname port
```

**Ejemplo:**
```bash
ncat --ssl localhost 30001
```

### nmap - Escáner de Red

**Propósito:** Exploración de red y auditoría de seguridad

**Escanear puertos:**
```bash
nmap -p RANGO_PUERTOS hostname
```

**Ejemplo:**
```bash
nmap -sCV -p31000-32000 --open 127.0.0.1
```

**Opciones:**
- `-sC` - Scripts por defecto
- `-sV` - Detección de versión
- `-p` - Rango de puertos
- `--open` - Mostrar solo los puertos abiertos

---

## 15. Seguridad y Permisos

### Permisos de Archivos

#### Entendiendo los Permisos

**Formato:** `drwxrwxrwx`

**Desglose:**
- `d` - Directorio (o `-` para archivo)
- `rwx` - Permisos del propietario
- `rwx` - Permisos del grupo
- `rwx` - Permisos de otros

**Tipos de permisos:**
- `r` - Lectura (4)
- `w` - Escritura (2)
- `x` - Ejecución (1)

#### chmod - Cambiar Permisos

**Modo simbólico:**
```bash
chmod u+x file      # Añadir ejecución para el propietario
chmod g-w file      # Quitar escritura para el grupo
chmod o+r file      # Añadir lectura para otros
chmod a+x file      # Añadir ejecución para todos
```

**Modo numérico:**
```bash
chmod 644 file      # rw-r--r--
chmod 755 file      # rwxr-xr-x
chmod 600 file      # rw-------
chmod 777 file      # rwxrwxrwx
```

**Hacer un archivo legible/escribible para otros:**
```bash
chmod o+rwx nombre_archivo
```

### SUID (Set User ID)

**Propósito:** Ejecutar un archivo con los permisos del propietario

**Buscar archivos SUID:**
```bash
find / -perm -4000 -type f 2>/dev/null
```

**Ejemplo de explotación de SUID:**
```bash
./bandit20-do cat /etc/bandit_pass/bandit20
```

**Qué pasa:**
- El binario se ejecuta como el propietario (bandit20)
- Puede leer archivos a los que bandit20 tiene acceso
- Incluso cuando lo ejecuta otro usuario

### Trabajos de Cron (Cron Jobs)

**Propósito:** Tareas programadas

**Ver los trabajos de cron:**
```bash
ls /etc/cron.d/
```

**Leer un trabajo de cron:**
```bash
cat /etc/cron.d/cronjob_bandit22
```

**Analizar un script:**
```bash
cat /usr/bin/cronjob_bandit22.sh
```

**Sintaxis de cron:**
```
* * * * * comando
│ │ │ │ │
│ │ │ │ └─── Día de la semana (0-7)
│ │ │ └───── Mes (1-12)
│ │ └─────── Día del mes (1-31)
│ └───────── Hora (0-23)
└─────────── Minuto (0-59)
```

### md5sum - Generación de Hash

**Propósito:** Generar una suma de comprobación MD5

```bash
echo "text" | md5sum
```

**Ejemplo:**
```bash
myname=bandit23
mytarget=$(echo "I am user $myname" | md5sum | cut -d ' ' -f 1)
echo $mytarget
```

**Caso de uso:** Generar nombres de archivo únicos

---

## 16. Ejemplos Prácticos de OverTheWire

### Ejemplos de Comandos Nivel por Nivel

#### Nivel 0 → 1: Lectura Básica de Archivos

**Reto:** Leer la contraseña del archivo readme

```bash
cat ./readme
```

**Salida:** `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`

#### Nivel 1 → 2: Archivo con Nombre Especial

**Reto:** Leer un archivo llamado `-`

```bash
cat ./-
```

**¿Por qué `./-`?** Evita que `-` se interprete como una opción

#### Nivel 2 → 3: Espacios en el Nombre del Archivo

**Reto:** Leer "spaces in this filename"

```bash
cat ./spaces\ in\ this\ filename
# o
cat "./spaces in this filename"
```

#### Nivel 3 → 4: Archivos Ocultos

**Reto:** Archivo oculto en el directorio inhere

```bash
ls -a ./inhere
cat ./inhere/...Hiding-From-You
```

#### Nivel 4 → 5: Archivo Legible por Humanos

**Reto:** Encontrar el archivo legible por humanos

```bash
find ./inhere -type f | xargs file
cat ./inhere/-file07
```

#### Nivel 5 → 6: Archivo con Propiedades Específicas

**Reto:** 1033 bytes, no ejecutable, legible por humanos

```bash
find ./inhere/ -type f -readable ! -executable -size 1033c | xargs cat
```

#### Nivel 6 → 7: Búsqueda en Todo el Sistema

**Reto:** Usuario bandit7, grupo bandit6, 33 bytes

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null | xargs cat
```

#### Nivel 7 → 8: Grep y Awk

**Reto:** Encontrar la contraseña junto a "millionth"

```bash
cat data.txt | grep "millionth" | awk '{print $2}'
```

#### Nivel 8 → 9: Línea Única

**Reto:** Encontrar la línea que aparece solo una vez

```bash
sort data.txt | uniq -u
```

#### Nivel 9 → 10: Cadenas en un Binario

**Reto:** Cadenas legibles por humanos con "="

```bash
cat data.txt | strings | grep "="
```

#### Nivel 10 → 11: Decodificación Base64

**Reto:** Decodificar base64

```bash
cat data.txt | base64 -d
```

#### Nivel 11 → 12: ROT13

**Reto:** Rotar las letras 13 posiciones

```bash
cat data.txt | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
```

#### Nivel 12 → 13: Descompresión de Hexdump

**Reto:** Revertir el hexdump y descomprimir

```bash
xxd -r data.txt > data.bin
file data.bin
# Múltiples pasos de descompresión...
```

#### Nivel 13 → 14: SSH con Clave Privada

**Reto:** Usar una clave SSH para acceder al siguiente nivel

```bash
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
cat /etc/bandit_pass/bandit14
```

#### Nivel 14 → 15: Netcat a Localhost

**Reto:** Enviar la contraseña al puerto 30000

```bash
nc localhost 30000
# Pegar la contraseña
```

#### Nivel 15 → 16: Conexión SSL

**Reto:** Enviar la contraseña con SSL

```bash
ncat --ssl localhost 30001
# Pegar la contraseña
```

#### Nivel 16 → 17: Escaneo de Puertos

**Reto:** Encontrar el puerto SSL entre 31000-32000

```bash
nmap -sCV -p31000-32000 --open 127.0.0.1
ncat --ssl 127.0.0.1 31790
# Pegar la contraseña
```

#### Nivel 17 → 18: Diff de Dos Archivos

**Reto:** Encontrar la línea que cambió

```bash
diff password.old password.new
```

#### Nivel 18 → 19: Ejecución de Comandos por SSH

**Reto:** Evitar el cierre de sesión del .bashrc

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 bash
cat readme
```

#### Nivel 19 → 20: Binario SUID

**Reto:** Usar un binario SUID

```bash
./bandit20-do cat /etc/bandit_pass/bandit20
```

#### Nivel 20 → 21: Escucha de Red

**Reto:** Dos sesiones SSH con netcat

**Sesión 1:**
```bash
nc -nlvp 4646
```

**Sesión 2:**
```bash
./suconnect 4646
```

**Sesión 1:** Pegar la contraseña actual

#### Nivel 21 → 22: Análisis de un Cron Job

**Reto:** Analizar un trabajo de cron

```bash
ls /etc/cron.d/
cat /etc/cron.d/cronjob_bandit22
cat /usr/bin/cronjob_bandit22.sh
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

#### Nivel 22 → 23: Cron con MD5

**Reto:** Entender la lógica del script

```bash
myname=bandit23
mytarget=$(echo "I am user $myname" | md5sum | cut -d ' ' -f 1)
echo $mytarget
cat /tmp/8ca319486bfbbc3663ea0fbe81326349
```

#### Nivel 23 → 24: Escribir Scripts

**Reto:** Crear un script para cron

```bash
cd $(mktemp -d)
# Crear el script
cp script.sh /var/spool/bandit24/foo/
chmod o+rwx output.txt
```

### Patrones Comunes de Comandos

**Encauzar varios comandos:**
```bash
cat file | grep patrón | awk '{print $2}' | sort | uniq
```

**Buscar y ejecutar:**
```bash
find /ruta -opciones | xargs comando
```

**Redirigir errores:**
```bash
comando 2>/dev/null
```

**Sustitución de comandos:**
```bash
result=$(comando)
echo $result
```

**Directorios temporales:**
```bash
cd $(mktemp -d)
```

---

## 17. Fundamentos de Shell Scripting

### ¿Qué es un Shell Script?

Un shell script es un archivo de texto que contiene una serie de comandos que pueden ejecutarse juntos. Los scripts automatizan tareas repetitivas y crean flujos de trabajo potentes.

### Creando tu Primer Script

#### Estructura Básica de un Script

```bash
#!/bin/bash
# Esto es un comentario
# La primera línea (shebang) le indica al sistema que use Bash

echo "Hello, World!"
echo "This is my first script"
```

**Guardar como:** `hello.sh`

#### Hacer los Scripts Ejecutables

```bash
chmod +x hello.sh    # Añadir permiso de ejecución
./hello.sh           # Ejecutar el script
```

### Variables

#### Declarar Variables

```bash
#!/bin/bash

# Asignación de variables (sin espacios alrededor del =)
name="Marco"
age=30
project_path="/home/user/projects"

# Usar las variables
echo "Name: $name"
echo "Age: $age"
echo "Project: $project_path"
```

#### Sustitución de Comandos

```bash
#!/bin/bash

# Capturar la salida de un comando en variables
current_date=$(date +%Y-%m-%d)
user_count=$(who | wc -l)
disk_usage=$(df -h / | awk 'NR==2 {print $5}')

echo "Date: $current_date"
echo "Users logged in: $user_count"
echo "Disk usage: $disk_usage"
```

### Entrada del Usuario

```bash
#!/bin/bash

echo "What is your name?"
read name
echo "Hello, $name!"

# Leer con un prompt (una sola línea)
read -p "Enter your age: " age
echo "You are $age years old"

# Leer datos sensibles (contraseña)
read -sp "Enter password: " password
echo ""
echo "Password stored securely"
```

### Sentencias Condicionales

#### Sentencias if/else

```bash
#!/bin/bash

read -p "Enter a number: " num

if [ $num -gt 10 ]; then
    echo "Number is greater than 10"
elif [ $num -eq 10 ]; then
    echo "Number is exactly 10"
else
    echo "Number is less than 10"
fi
```

#### Comparaciones de Cadenas

```bash
#!/bin/bash

read -p "Enter environment (dev/prod): " env

if [ "$env" = "prod" ]; then
    echo "Running in PRODUCTION mode"
elif [ "$env" = "dev" ]; then
    echo "Running in DEVELOPMENT mode"
else
    echo "Unknown environment: $env"
fi
```

#### Pruebas sobre Archivos

```bash
#!/bin/bash

file="config.txt"

if [ -f "$file" ]; then
    echo "File exists"
    if [ -r "$file" ]; then
        echo "File is readable"
    fi
    if [ -w "$file" ]; then
        echo "File is writable"
    fi
    if [ -x "$file" ]; then
        echo "File is executable"
    fi
else
    echo "File does not exist"
fi
```

**Operadores de prueba comunes:**
- `-f file` - El archivo existe y es un archivo regular
- `-d dir` - El directorio existe
- `-e path` - La ruta existe (archivo o directorio)
- `-r file` - El archivo es legible
- `-w file` - El archivo es escribible
- `-x file` - El archivo es ejecutable
- `-s file` - El archivo existe y no está vacío

### Bucles

#### Bucle for

```bash
#!/bin/bash

# Iterar por una lista
for name in Alice Bob Charlie; do
    echo "Hello, $name"
done

# Iterar por archivos
for file in *.txt; do
    echo "Processing: $file"
    cat "$file"
done

# Bucle for estilo C
for ((i=1; i<=5; i++)); do
    echo "Iteration $i"
done
```

#### Bucle while

```bash
#!/bin/bash

counter=1
while [ $counter -le 5 ]; do
    echo "Count: $counter"
    ((counter++))
done

# Leer un archivo línea por línea
while IFS= read -r line; do
    echo "Line: $line"
done < input.txt
```

### Funciones

```bash
#!/bin/bash

# Definición de una función
greet() {
    local name=$1
    local time=$2
    echo "Good $time, $name!"
}

# Función con valor de retorno
add_numbers() {
    local sum=$(($1 + $2))
    echo $sum
}

# Usar las funciones
greet "Marco" "morning"
result=$(add_numbers 5 3)
echo "5 + 3 = $result"
```

### Códigos de Salida

```bash
#!/bin/bash

# Comprobar si el comando tuvo éxito
if git pull; then
    echo "Git pull successful"
else
    echo "Git pull failed"
    exit 1
fi

# Comprobar el código de salida explícitamente
command_output=$(some_command 2>&1)
exit_code=$?

if [ $exit_code -eq 0 ]; then
    echo "Command succeeded"
else
    echo "Command failed with code: $exit_code"
    exit $exit_code
fi
```

### Ejemplos Prácticos de Scripts

#### Script de Backup

```bash
#!/bin/bash
# backup.sh - Respaldar directorios importantes

# Configuración
BACKUP_DIR="/backup"
SOURCE_DIRS="/home/user/documents /home/user/projects"
DATE=$(date +%Y%m%d_%H%M%S)
BACKUP_FILE="backup_$DATE.tar.gz"

# Crear el directorio de backup si no existe
mkdir -p "$BACKUP_DIR"

# Crear el backup
echo "Creating backup: $BACKUP_FILE"
tar -czf "$BACKUP_DIR/$BACKUP_FILE" $SOURCE_DIRS

if [ $? -eq 0 ]; then
    echo "Backup created successfully"
    echo "Location: $BACKUP_DIR/$BACKUP_FILE"
else
    echo "Backup failed!"
    exit 1
fi

# Eliminar los backups de más de 7 días
find "$BACKUP_DIR" -name "backup_*.tar.gz" -mtime +7 -delete
echo "Old backups cleaned up"
```

#### Monitor del Sistema

```bash
#!/bin/bash
# monitor.sh - Mostrar información del sistema

echo "=== System Monitor ==="
echo ""

echo "Hostname: $(hostname)"
echo "Uptime: $(uptime -p)"
echo ""

echo "=== CPU Usage ==="
top -l 1 | grep "CPU usage" || mpstat 1 1

echo ""
echo "=== Memory Usage ==="
free -h || vm_stat

echo ""
echo "=== Disk Usage ==="
df -h | grep -E '^/dev/'

echo ""
echo "=== Top 5 Processes by Memory ==="
ps aux | sort -rk 4 | head -5
```

#### Script de Despliegue

```bash
#!/bin/bash
# deploy.sh - Desplegar la aplicación

set -e  # Salir ante cualquier error

APP_NAME="my-app"
BRANCH="main"
DEPLOY_DIR="/var/www/$APP_NAME"

echo "Deploying $APP_NAME..."

# Traer el último código
cd "$DEPLOY_DIR"
git fetch origin
git checkout "$BRANCH"
git pull origin "$BRANCH"

# Instalar dependencias
echo "Installing dependencies..."
npm install --production

# Compilar la aplicación
echo "Building application..."
npm run build

# Reiniciar el servicio
echo "Restarting service..."
sudo systemctl restart "$APP_NAME"

# Comprobar el estado
if systemctl is-active --quiet "$APP_NAME"; then
    echo "Deployment successful!"
else
    echo "Deployment failed - service not running"
    exit 1
fi
```

---

## 18. Buenas Prácticas Modernas de Bash

### Seguridad y Fiabilidad de los Scripts

#### Usa Siempre el Shebang

```bash
#!/bin/bash
# No #!/bin/sh (shell diferente)
# Usa la ruta absoluta por portabilidad
```

#### Establece Opciones Seguras

```bash
#!/bin/bash

# Salir ante un error
set -e

# Salir ante una variable indefinida
set -u

# Salir ante un fallo en una tubería
set -o pipefail

# Combinado (recomendado)
set -euo pipefail
```

**Qué hace cada opción:**
- `set -e` - Salir inmediatamente si algún comando falla
- `set -u` - Tratar las variables indefinidas como errores
- `set -o pipefail` - La tubería falla si algún comando de ella falla

#### Usa Entrecomillado Estricto de Variables

```bash
# Mal - problemas de división de palabras y globbing
cp $file $destination

# Bien - evita problemas con espacios y caracteres especiales
cp "$file" "$destination"

# Mal - vulnerabilidad de inyección de comandos
eval $user_input

# Bien - validar y entrecomillar
if [[ "$user_input" =~ ^[a-zA-Z0-9_]+$ ]]; then
    command "$user_input"
fi
```

### Calidad y Mantenibilidad del Código

#### Integración con ShellCheck

**ShellCheck** es una herramienta de análisis estático que detecta errores comunes de Bash.

```bash
# Instalar ShellCheck
# macOS
brew install shellcheck

# Ubuntu/Debian
apt install shellcheck

# Comprobar tu script
shellcheck myscript.sh
```

**Problemas comunes que ShellCheck detecta:**
- Variables sin entrecomillar
- Condicionales incorrectos
- Uso inútil de cat
- Falta de manejo de errores
- Sintaxis obsoleta

**Ejemplo de salida de ShellCheck:**
```bash
shellcheck deploy.sh

Line 12:
  if [ $status = "running" ]; then
       ^-- SC2086: Double quote to prevent word splitting
```

#### Nombres de Variables Significativos

```bash
# Mal
f="/tmp/data"
t=$(date +%s)
n=5

# Bien
temp_file="/tmp/data"
timestamp=$(date +%s)
max_retries=5
```

#### Usa Funciones para la Reutilización

```bash
#!/bin/bash

# Función para el manejo de errores
error_exit() {
    echo "ERROR: $1" >&2
    exit 1
}

# Función para el registro (logging)
log() {
    echo "[$(date +'%Y-%m-%d %H:%M:%S')] $1"
}

# Uso
log "Starting deployment"
git pull || error_exit "Git pull failed"
log "Deployment complete"
```

### Buenas Prácticas de Seguridad

#### Evita eval y Comandos Peligrosos Similares

```bash
# Mal - riesgo de inyección de comandos
user_command="$1"
eval "$user_command"

# Bien - usa arrays y ejecución directa
allowed_commands=("ls" "pwd" "date")
if [[ " ${allowed_commands[@]} " =~ " $1 " ]]; then
    "$1"
fi
```

#### Valida la Entrada del Usuario

```bash
#!/bin/bash

read -p "Enter filename: " filename

# Validar la entrada - solo alfanuméricos, guion bajo y guion
if [[ ! "$filename" =~ ^[a-zA-Z0-9._-]+$ ]]; then
    echo "Invalid filename"
    exit 1
fi

# Prevenir el directory traversal
if [[ "$filename" == *".."* ]] || [[ "$filename" == *"/"* ]]; then
    echo "Invalid filename - no paths allowed"
    exit 1
fi
```

#### Archivos Temporales Seguros

```bash
#!/bin/bash

# Mal - nombre de archivo predecible
temp_file="/tmp/myapp.tmp"

# Bien - usa mktemp para archivos temporales seguros
temp_file=$(mktemp) || exit 1
trap "rm -f '$temp_file'" EXIT  # Limpiar al salir

echo "data" > "$temp_file"
# Usar temp_file...
# Se elimina automáticamente al salir del script
```

#### Restringe los Permisos de Archivos

```bash
#!/bin/bash

# Crear un archivo de configuración con permisos restringidos
config_file="config.conf"
touch "$config_file"
chmod 600 "$config_file"  # Solo lectura/escritura del propietario

# Almacenar datos sensibles
echo "API_KEY=secret123" > "$config_file"
```

### Optimización del Rendimiento

#### Evita Subshells Innecesarias

```bash
# Lento - crea una subshell en cada iteración
for file in $(ls *.txt); do
    process "$file"
done

# Rápido - usa globbing
for file in *.txt; do
    process "$file"
done

# Lento - cat innecesario
cat file.txt | grep pattern

# Rápido - grep puede leer archivos directamente
grep pattern file.txt
```

#### Usa Comandos Integrados en Lugar de Externos

```bash
# Más lento - comando externo
basename /path/to/file.txt

# Más rápido - expansión de parámetros
filename="${path##*/}"

# Más lento - comando externo
dirname /path/to/file.txt

# Más rápido - expansión de parámetros
directory="${path%/*}"
```

#### Procesa Archivos Grandes de Forma Eficiente

```bash
# Mal - carga todo el archivo en memoria
while read line; do
    process "$line"
done < largefile.txt

# Bien - usa read de forma eficiente con IFS
while IFS= read -r line; do
    process "$line"
done < largefile.txt

# Lo mejor para patrones específicos - usa awk/sed
awk '/pattern/ {print $2}' largefile.txt
```

### Manejo de Errores y Logging

#### Manejo de Errores Exhaustivo

```bash
#!/bin/bash

set -euo pipefail

# Capturar errores
trap 'echo "Error on line $LINENO" >&2' ERR

# Capturar la limpieza al salir
cleanup() {
    rm -f "$temp_file"
    log "Cleanup completed"
}
trap cleanup EXIT

# Función con manejo de errores
safe_copy() {
    local source=$1
    local dest=$2

    if [ ! -f "$source" ]; then
        echo "Source file not found: $source" >&2
        return 1
    fi

    if ! cp "$source" "$dest"; then
        echo "Copy failed: $source -> $dest" >&2
        return 1
    fi

    return 0
}
```

#### Logging Estructurado

```bash
#!/bin/bash

# Niveles de log
LOG_LEVEL=${LOG_LEVEL:-INFO}
LOG_FILE=${LOG_FILE:-/var/log/myapp.log}

log() {
    local level=$1
    shift
    local message="$*"
    local timestamp=$(date +'%Y-%m-%d %H:%M:%S')

    echo "[$timestamp] [$level] $message" | tee -a "$LOG_FILE"
}

log_info() { log "INFO" "$@"; }
log_warn() { log "WARN" "$@"; }
log_error() { log "ERROR" "$@" >&2; }

# Uso
log_info "Application starting"
log_warn "Using default configuration"
log_error "Database connection failed"
```

### Funcionalidades Modernas de Bash (Bash 4.0+)

#### Arrays Asociativos (Bash 4.0+)

```bash
#!/bin/bash

# Declarar un array asociativo
declare -A config

# Establecer valores
config[host]="localhost"
config[port]="5432"
config[database]="mydb"

# Acceder a los valores
echo "Host: ${config[host]}"
echo "Port: ${config[port]}"

# Iterar por las claves
for key in "${!config[@]}"; do
    echo "$key = ${config[$key]}"
done
```

#### Globstar (Bash 4.0+)

```bash
#!/bin/bash

# Habilitar globstar para el globbing recursivo
shopt -s globstar

# Encontrar todos los archivos JavaScript recursivamente
for file in **/*.js; do
    echo "Processing: $file"
done
```

### Consideraciones de Portabilidad

#### Comprobar la Versión de Bash en los Scripts

```bash
#!/bin/bash

# Requiere Bash 4.0+
if [ "${BASH_VERSINFO[0]}" -lt 4 ]; then
    echo "This script requires Bash 4.0 or higher"
    exit 1
fi
```

#### Cumplimiento de POSIX para Máxima Portabilidad

```bash
#!/bin/sh
# Usa /bin/sh para scripts compatibles con POSIX

# Evita las funcionalidades específicas de Bash:
# - [[  ]] (usa [  ] en su lugar)
# - (( )) (usa expr o $(()) )
# - expansión {1..10}
# - arrays asociativos
# - operador de regex =~
```

### Testing y Depuración

#### Modo de Depuración

```bash
#!/bin/bash

# Habilitar el modo de depuración
set -x  # Imprimir cada comando antes de ejecutarlo

# Depurar solo secciones específicas
set -x
complex_operation
set +x  # Deshabilitar el modo de depuración
```

#### Modo de Simulación (Dry-Run)

```bash
#!/bin/bash

DRY_RUN=${DRY_RUN:-false}

run_command() {
    if [ "$DRY_RUN" = "true" ]; then
        echo "Would run: $*"
    else
        "$@"
    fi
}

# Uso
run_command rm -rf /important/data
run_command cp file.txt backup/

# Ejecutar el script en modo de simulación
# DRY_RUN=true ./script.sh
```

#### Framework de Testing Simple

```bash
#!/bin/bash

# Contador de tests
tests_run=0
tests_passed=0

# Aserción de test
assert_equals() {
    local expected=$1
    local actual=$2
    local message=${3:-"Assertion failed"}

    ((tests_run++))

    if [ "$expected" = "$actual" ]; then
        ((tests_passed++))
        echo "✓ PASS: $message"
    else
        echo "✗ FAIL: $message"
        echo "  Expected: $expected"
        echo "  Actual: $actual"
    fi
}

# Ejecutar los tests
test_addition() {
    local result=$((2 + 2))
    assert_equals 4 "$result" "2 + 2 should equal 4"
}

# Ejecutar los tests
test_addition

# Resumen
echo ""
echo "Tests run: $tests_run"
echo "Tests passed: $tests_passed"
[ $tests_run -eq $tests_passed ] || exit 1
```

### Estándares de Documentación

#### Plantilla de Cabecera de Script

```bash
#!/bin/bash
################################################################################
# Script Name: deploy.sh
# Description: Deploy application to production server
# Author: Marco Figueroa <mfigueroa@devsonic.cl>
# Created: 2025-01-15
# Last Modified: 2025-02-12
# Version: 1.2.0
#
# Usage: ./deploy.sh [environment] [branch]
#   environment: dev, staging, prod (default: dev)
#   branch: git branch to deploy (default: main)
#
# Examples:
#   ./deploy.sh prod main
#   ./deploy.sh staging develop
#
# Exit Codes:
#   0 - Success
#   1 - General error
#   2 - Invalid arguments
#   3 - Deployment failed
################################################################################

set -euo pipefail
```

#### Documentación de Funciones

```bash
# backup_database - Crear un backup de la base de datos
# Arguments:
#   $1 - Database name
#   $2 - Backup directory (optional, default: /backup)
# Returns:
#   0 on success, 1 on failure
# Example:
#   backup_database mydb /var/backups
backup_database() {
    local db_name=$1
    local backup_dir=${2:-/backup}
    # Implementación...
}
```

### Herramientas y Recursos

#### Herramientas Esenciales

| Herramienta | Propósito | Instalar |
|------|---------|---------|
| **shellcheck** | Análisis estático | `brew install shellcheck` |
| **shfmt** | Formateador de shell scripts | `brew install shfmt` |
| **bats** | Framework de testing de Bash | `brew install bats-core` |
| **bash-completion** | Autocompletado con Tab | `brew install bash-completion` |

#### Formateadores de Código

```bash
# Formatear un script con shfmt
shfmt -w script.sh

# Formatear con opciones específicas
shfmt -i 4 -bn -ci -sr -w script.sh
# -i 4: indentar con 4 espacios
# -bn: los operadores binarios como && y | pueden iniciar una línea
# -ci: los casos de switch se indentarán
# -sr: los operadores de redirección irán seguidos de un espacio
```

#### Hooks de Pre-commit

```bash
#!/bin/bash
# .git/hooks/pre-commit

# Comprobar todos los shell scripts con ShellCheck
for file in $(git diff --cached --name-only --diff-filter=ACM | grep '\.sh$'); do
    if ! shellcheck "$file"; then
        echo "ShellCheck failed for $file"
        exit 1
    fi
done

echo "All shell scripts passed ShellCheck"
```

### Ejemplos de Integración del Mundo Real

#### Script de Pipeline CI/CD

```bash
#!/bin/bash
################################################################################
# CI/CD Pipeline Script
################################################################################

set -euo pipefail

# Configuración
PROJECT_NAME="api-devsonic-cl"
DOCKER_REGISTRY="docker.io/username"
KUBE_NAMESPACE="devsonic-cl"

# Funciones
log_info() { echo "[INFO] $*"; }
log_error() { echo "[ERROR] $*" >&2; }

check_requirements() {
    log_info "Checking requirements..."
    command -v docker >/dev/null || { log_error "Docker not found"; exit 1; }
    command -v kubectl >/dev/null || { log_error "kubectl not found"; exit 1; }
}

run_tests() {
    log_info "Running tests..."
    npm run test || { log_error "Tests failed"; exit 1; }
}

build_image() {
    local tag=$1
    log_info "Building Docker image: $tag"
    docker build -t "$DOCKER_REGISTRY/$PROJECT_NAME:$tag" .
}

push_image() {
    local tag=$1
    log_info "Pushing image to registry..."
    docker push "$DOCKER_REGISTRY/$PROJECT_NAME:$tag"
}

deploy_to_kubernetes() {
    local tag=$1
    log_info "Deploying to Kubernetes..."
    kubectl set image "deployment/$PROJECT_NAME" \
        "$PROJECT_NAME=$DOCKER_REGISTRY/$PROJECT_NAME:$tag" \
        -n "$KUBE_NAMESPACE"
    kubectl rollout status "deployment/$PROJECT_NAME" -n "$KUBE_NAMESPACE"
}

# Ejecución principal
main() {
    local version=${1:-$(git rev-parse --short HEAD)}

    check_requirements
    run_tests
    build_image "$version"
    push_image "$version"
    deploy_to_kubernetes "$version"

    log_info "Deployment completed successfully"
}

main "$@"
```

---

## Recursos Adicionales

### Documentación Oficial
- [Manual de GNU Bash](https://www.gnu.org/software/bash/manual/)
- [Bash Guide for Beginners](https://tldp.org/LDP/Bash-Beginners-Guide/html/)

### Herramientas
- [ShellCheck](https://www.shellcheck.net/) - Análisis estático de scripts
- [Explain Shell](https://explainshell.com/) - Explicaciones de comandos
- [Google Shell Style Guide](https://google.github.io/styleguide/shellguide.html) - Convenciones ampliamente usadas

### Práctica
- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/) - Wargame de línea de comandos y seguridad

---

## Apéndice: Hoja de Referencia Rápida

### Comandos Esenciales

```bash
# Navegación
pwd                 # Imprimir el directorio de trabajo
ls -lah            # Listar todos los archivos con detalles
cd /path           # Cambiar de directorio
cd -               # Volver al directorio anterior

# Operaciones con Archivos
cat file.txt       # Mostrar el contenido del archivo
less file.txt      # Paginar el archivo
head -n 20 file    # Primeras 20 líneas
tail -f file.log   # Seguir las actualizaciones del archivo
touch newfile      # Crear un archivo vacío
cp src dst         # Copiar un archivo
mv old new         # Mover/renombrar un archivo
rm file            # Eliminar un archivo

# Procesamiento de Texto
grep "pattern" file           # Buscar un patrón
grep -r "pattern" /path      # Búsqueda recursiva
sed 's/old/new/g' file       # Reemplazar texto
awk '{print $1}' file        # Imprimir la primera columna
sort file                     # Ordenar líneas
uniq -c                       # Contar líneas únicas

# Búsqueda
find /path -name "*.txt"              # Buscar por nombre
find /path -type f -size +1M          # Buscar archivos grandes
find /path -mtime -7                  # Modificados en los últimos 7 días
grep -r "TODO" --include="*.js" .     # Buscar en archivos JS

# Permisos
chmod 755 script.sh     # Hacer ejecutable
chmod 600 secret.txt    # Solo lectura/escritura del propietario
chown user:group file   # Cambiar el propietario

# Gestión de Procesos
ps aux                  # Listar todos los procesos
top                     # Monitorear procesos
kill PID               # Terminar un proceso
pkill name             # Matar por nombre
jobs                   # Listar los trabajos en segundo plano
bg %1                  # Reanudar un trabajo en segundo plano
fg %1                  # Traer un trabajo al primer plano

# Red
curl https://api.example.com         # Petición HTTP
wget https://example.com/file.zip    # Descargar un archivo
ssh user@host                        # Conectar vía SSH
scp file user@host:/path            # Copia segura
ping -c 4 google.com                # Probar la conectividad

# Información del Sistema
df -h                  # Espacio en disco
du -sh /path          # Tamaño del directorio
free -h               # Uso de memoria
uname -a              # Información del sistema
uptime                # Tiempo de actividad del sistema
whoami                # Usuario actual

# Archivos Comprimidos
tar -czf archive.tar.gz /path    # Crear un archivo comprimido
tar -xzf archive.tar.gz          # Extraer un archivo
zip -r archive.zip /path         # Crear un zip
unzip archive.zip                # Extraer un zip

# Redirección
command > file        # Redirigir stdout a un archivo
command >> file       # Añadir stdout a un archivo
command 2> file       # Redirigir stderr a un archivo
command &> file       # Redirigir tanto stdout como stderr
command 2>&1         # Redirigir stderr a stdout
```

### Patrones Comunes

```bash
# Iterar por archivos
for file in *.txt; do
    echo "$file"
done

# Leer un archivo línea por línea
while IFS= read -r line; do
    echo "$line"
done < file.txt

# Comprobar si un comando existe
if command -v docker >/dev/null 2>&1; then
    echo "Docker is installed"
fi

# Lógica de reintentos
for i in {1..5}; do
    if command; then
        break
    fi
    sleep 5
done

# Ejecución en paralelo
for i in {1..10}; do
    process_item "$i" &
done
wait  # Esperar a todos los trabajos en segundo plano

# Manejo de errores
command || { echo "Command failed" >&2; exit 1; }
```

---

**Última Actualización:** 2026-08-31
**Versión de Bash Cubierta:** 3.2 - 5.2+
**Plataforma:** Multiplataforma (Linux, macOS, Windows WSL)
**Ejemplos Prácticos:** Retos de OverTheWire Bandit integrados
