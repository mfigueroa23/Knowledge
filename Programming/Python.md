# Python - De los Fundamentos a la Automatización y la Ciencia de Datos

## 📊 Metadatos del Documento

**Última Actualización:** 2026-08-31
**Versión de Python Cubierta:** 3.13.x
**Requisitos Previos:** Ninguno - apto para principiantes
**Nivel de Habilidad:** Principiante a Intermedio
**Proyectos de Práctica:** Web scraping, automatización, análisis de datos

---

## 🎯 Cuándo Usar Este Conocimiento

**Usa esta guía cuando necesites:**
- Aprender Python desde cero absoluto hasta aplicaciones prácticas
- Entender los fundamentos de la resolución de problemas antes de programar
- Construir scripts de web scraping y automatización
- Iniciarte en los conceptos de ciencia de datos
- Prepararte para caminos de aprendizaje de análisis de datos o ML/IA
- Consultar la sintaxis y las buenas prácticas de Python

**Esto NO es para:**
- Patrones de diseño OOP avanzados (cubiertos en otro lugar)
- Desarrollo web de producción (ver NestJS.md para el backend)
- Deep learning o algoritmos de ML avanzados
- Desarrollo de apps móviles
- Desarrollo de videojuegos con Python

**Más adecuado para:**
- Principiantes completos sin experiencia en programación
- Desarrolladores que vienen de otros lenguajes
- Analistas de datos que quieren automatizar tareas
- Cualquiera que construya scripts de automatización rápidos

---

## 📋 Tabla de Contenidos

1. [Introducción](#1-introducción)
2. [Historia y Filosofía](#2-historia-y-filosofía)
3. [¿Por Qué Aprender Python?](#3-por-qué-aprender-python)
4. [Instalación y Configuración](#4-instalación-y-configuración)
5. [Entorno de Desarrollo](#5-entorno-de-desarrollo)
6. [Primer Programa - Hola Mundo](#6-primer-programa---hola-mundo)
7. [La Función Print](#7-la-función-print)
8. [Tipos de Datos](#8-tipos-de-datos)
9. [Conversión de Tipos (Type Casting)](#9-conversión-de-tipos-type-casting)
10. [Comentarios](#10-comentarios)
11. [Funcionalidades Modernas de Python (3.10+)](#11-funcionalidades-modernas-de-python-310)
12. [Fundamentos de la Resolución de Problemas](#12-fundamentos-de-la-resolución-de-problemas)
13. [Algoritmos](#13-algoritmos)
14. [Pseudocódigo](#14-pseudocódigo)
15. [Diagramas de Flujo](#15-diagramas-de-flujo)
16. [Algoritmos de Búsqueda](#16-algoritmos-de-búsqueda)
17. [Algoritmos de Ordenamiento](#17-algoritmos-de-ordenamiento)
18. [Introducción a la Ciencia de Datos](#18-introducción-a-la-ciencia-de-datos)
19. [Web Scraping con Pandas](#19-web-scraping-con-pandas)
20. [Extraer Tablas de PDFs](#20-extraer-tablas-de-pdfs)
21. [Fundamentos de HTML para Web Scraping](#21-fundamentos-de-html-para-web-scraping)
22. [XPath para la Selección de Elementos](#22-xpath-para-la-selección-de-elementos)
23. [Automatización Web con Selenium](#23-automatización-web-con-selenium)
24. [Construyendo un Proyecto de Web Scraping](#24-construyendo-un-proyecto-de-web-scraping)
25. [Exportar Datos a CSV](#25-exportar-datos-a-csv)
26. [Resumen de Automatización con Python](#26-resumen-de-automatización-con-python)

---

## Descripción General

Python es hoy uno de los lenguajes de programación más populares del mundo, con licencia de código abierto. Creado por Guido van Rossum y lanzado por primera vez en 1991, Python ha evolucionado hasta convertirse en una herramienta fundamental en el desarrollo de software, la ciencia de datos, la inteligencia artificial y la automatización.

### ¿Qué es Python?

- **Lenguaje interpretado** - No requiere compilación, el código se ejecuta directamente
- **Lenguaje de alto nivel** - Sintaxis más cercana al lenguaje humano que al código máquina
- **De propósito general** - Se puede usar para prácticamente cualquier tipo de proyecto
- **Multiparadigma** - Soporta programación funcional, imperativa y orientada a objetos
- **Multiplataforma** - Se ejecuta en Windows, macOS, Linux y más

### Características Principales

- ✅ Sintaxis fácil e intuitiva, tan potente como los grandes competidores
- ✅ Proyecto de código abierto para el desarrollo colaborativo
- ✅ Código tan legible como el inglés llano
- ✅ Adecuado para tareas diarias y prototipado rápido
- ✅ Amplia librería estándar
- ✅ Gran comunidad y ecosistema rico
- ✅ Fuerte portabilidad entre plataformas

### Filosofía Central

Según su creador Guido van Rossum, Python se construye sobre cuatro pilares:

1. **Fácil e Intuitivo** - Tan potente como los grandes competidores pero simple de aprender
2. **Código Abierto** - Cualquiera puede contribuir al proyecto
3. **Código Legible** - Tan comprensible como un texto en inglés llano
4. **Uso Diario** - Permite el desarrollo rápido de prototipos

---

## 1. Introducción

### Visión General de Python

Python no es un lenguaje reciente - apareció por primera vez el 20 de febrero de 1991, cuando su creador Guido van Rossum lanzó públicamente la versión 0.9. Sin embargo, el desarrollo comenzó mucho antes, en diciembre de 1989.

**Hitos Clave:**
- **1989** - Comienza el desarrollo
- **1991** - Primera versión pública (0.9)
- **1994** - Se lanza la versión 1.0
- **2025** - Versión actual 3.13.1

### Características del Lenguaje

**1. Lenguaje Interpretado**
- No se necesita compilador
- El código se ejecuta directamente
- Ciclo de desarrollo más rápido
- Mayor portabilidad
- Depuración más fácil
- Nota: Existen opciones de compilación para optimización

**2. Lenguaje de Alto Nivel**
- Sintaxis más cercana al lenguaje humano
- Comparado con lenguajes de bajo nivel como C (más cercanos a la máquina)
- No hay que gestionar la memoria manualmente
- Estructuras fáciles de entender
- A veces sintaxis verbosa que se lee como el inglés

**3. Lenguaje de Propósito General**
Python se puede usar para:
- Desarrollo web
- Interfaces de aplicaciones (GUI)
- Computación científica y numérica
- Desarrollo de software
- Administración de sistemas
- Ciencia de datos
- Machine learning
- Videojuegos
- Automatización y scripting

**4. Multiparadigma**
- Soporta múltiples paradigmas de programación:
  - Programación imperativa (principal)
  - Programación orientada a objetos (soporte parcial)
  - Programación funcional
- Se adapta a distintos estilos y preferencias de programación

**5. Multiplataforma**
- Disponible en todos los sistemas operativos principales:
  - Windows
  - macOS
  - Linux
  - Y prácticamente cualquier otro SO

**6. Librería Estándar Rica**
- Amplia colección de módulos integrados
- A menudo no hay que instalar paquetes externos
- Los módulos nativos cubren muchos casos de uso comunes

---

## 2. Historia y Filosofía

### El Creador: Guido van Rossum

**Información Personal:**
- Nacido el 31 de enero de 1956
- De los Países Bajos
- Trabajó en las mejores empresas:
  - Google
  - Dropbox
  - Microsoft (su posición más reciente)

### ¿Por Qué "Python"?

Contrario a la creencia popular, Python NO lleva el nombre de la serpiente. El nombre es un homenaje a **Monty Python**, un grupo de comedia británico que el creador admiraba. El logo actual puede sugerir una serpiente, pero la inspiración original fue el grupo de comedia.

### Los Cuatro Pilares de Python

1. Python debe ser **fácil, intuitivo y tan potente** como sus principales competidores
2. El proyecto debe ser **de código abierto** para que cualquiera pueda colaborar
3. El código escrito en Python debe ser **tan comprensible como un texto en inglés llano**
4. Python debe ser **adecuado para las actividades diarias**, permitiendo el prototipado rápido

---

## 3. ¿Por Qué Aprender Python?

### Ventajas

**1. Sintaxis Legible**
- Clara y fácil de entender
- Curva de aprendizaje pronunciada pero rápida
- Escribe menos código para lograr más

**2. Versatilidad**
- Amplia gama de aplicaciones
- Especialmente dominante en el campo de la inteligencia artificial
- Auge actual de popularidad impulsado por la adopción de IA/ML

**3. Multiplataforma y Portabilidad**
- El mismo código se ejecuta en cualquier sistema operativo
- Cambios mínimos o nulos para distintas plataformas

**4. Gran Comunidad y Ecosistema**
- Amplia red de soporte
- Ecosistema de paquetes rico
- Sin embargo: Muchos paquetes hacen lo mismo (puede confundir)
- Algunas librerías pueden estar sin mantenimiento o inmaduras

**5. Demanda del Mercado**

Según los datos de GitHub 2024:
- **#1** Lenguaje de programación más usado (por contribuidores únicos)
- Superó a JavaScript (#2) y TypeScript (#3)
- La mayoría de los contribuidores trabajando en proyectos Python

Según Dev Jobs Scanner:
- **Top 2** Lenguaje más demandado del mundo
- JavaScript/TypeScript combinados son el #1
- Python es el #2 en demanda del mercado laboral

### Uso en el Mundo Real

**Grandes Empresas que Usan Python:**

**YouTube**
- Arquitectura del lado del servidor
- Construido sobre la plataforma Python

**Netflix**
- Uso extenso en todos sus servicios
- Scripts de servidor
- Cálculos matemáticos
- Algoritmos de recomendación

**NASA**
- Múltiples proyectos de código abierto
- Python usado en toda la organización
- Aplicaciones científicas y de ingeniería

**OpenAI**
- Lenguaje principal para las demostraciones
- Desarrollo de modelos de IA/ML

### Desventajas

**1. Velocidad de Ejecución**
- No es el lenguaje más rápido
- Ser interpretado afecta al rendimiento
- Generalmente suficiente para la mayoría de casos de uso

**2. Limitaciones de Multi-threading**
- No diseñado nativamente para multi-threading
- Existen soluciones alternativas (similar a JavaScript)
- Puede afectar al rendimiento en escenarios concurrentes

**3. Consumo de Memoria**
- Mayor uso de memoria comparado con algunos lenguajes
- Contrapartida por la facilidad de uso y la flexibilidad

**4. Sin Detección de Errores en Tiempo de Compilación**
- Los errores solo se detectan en tiempo de ejecución
- No hay paso de compilación para detectar problemas temprano

**5. Desarrollo Móvil Limitado**
- El desarrollo móvil es posible pero no popular
- Comunidad muy pequeña para apps móviles
- No recomendado para proyectos centrados en móvil

**6. Retos del Ecosistema**
- Demasiados paquetes haciendo cosas similares
- Difícil elegir la librería correcta
- Algunos paquetes carecen de madurez
- Las librerías pueden ser abandonadas

**7. Estilo de Sintaxis (Subjetivo)**
- Sin llaves, usa la indentación
- La indentación es obligatoria y significativa
- Algunos desarrolladores prefieren marcadores de bloque explícitos

---

## 4. Instalación y Configuración

### Comprobar si Python está Instalado

Python a menudo viene preinstalado en macOS y Linux.

**Comprobar la versión:**
```bash
python --version
# o
python3 --version
```

### Métodos de Instalación

**Sitio Web Oficial:**
1. Visita [python.org](https://www.python.org/)
2. Ve a la sección Downloads
3. Descarga el instalador para tu SO

**macOS:**
- Xcode Command Line Tools (incluye Python)
- Homebrew: `brew install python3`
- Instalador oficial de python.org

**Linux:**
- APT (Debian/Ubuntu): `sudo apt install python3`
- YUM (Red Hat/CentOS): `sudo yum install python3`
- Depende de la distribución

**Windows:**
- Descarga el instalador oficial de python.org
- Ejecuta el instalador y sigue el asistente
- **Importante:** Marca "Add Python to PATH" durante la instalación

### Entornos Virtuales (Buena Práctica)

Siempre aísla las dependencias del proyecto en un entorno virtual en lugar de instalar paquetes globalmente:

```bash
# Crear y activar un entorno virtual
python3 -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

# Instalar y fijar las dependencias
pip install <package>
pip freeze > requirements.txt
```

**Por qué importa:**
- Builds reproducibles (versiones fijadas en `requirements.txt`)
- Sin conflictos de dependencias entre proyectos
- Higiene de la cadena de suministro: audita lo que cada proyecto instala realmente (`pip audit` marca los CVEs conocidos)

### Playgrounds en Línea (Sin Instalación)

**Recomendado:** [pythonsandbox.com](https://pythonsandbox.com)
- Escribe código en el panel izquierdo
- Haz clic en "Run" para ejecutar
- Los resultados aparecen inmediatamente
- No requiere registro
- Gratis y simple
- Se ejecuta en el navegador

**Características:**
- Ejecución instantánea
- Sin configuración necesaria
- Bueno para aprender y probar
- Desplazamiento automático a la salida

---

## 5. Entorno de Desarrollo

### Recomendaciones de Editores

#### Opción 1: PyCharm (JetBrains)

**Descripción:**
- IDE diseñado específicamente para Python
- Optimizado para ciencia de datos y desarrollo web
- Funciones de nivel profesional

**Precios:**
- Community Edition gratuita disponible
- Gratis para:
  - Estudiantes y profesores
  - Proyectos de código abierto
  - Uso no comercial
  - Educadores académicos

**Mejor para:**
- Desarrollo solo en Python
- Proyectos Python profesionales
- Trabajo de ciencia de datos

#### Opción 2: Visual Studio Code (Recomendado)

**Descripción:**
- Editor todo-en-uno
- Soporte multi-lenguaje
- Gratis y de código abierto
- Excelente soporte de Python
- Incluye el nivel gratuito de GitHub Copilot

**Descarga:** [code.visualstudio.com](https://code.visualstudio.com/)

**Extensiones Requeridas:**

1. **Python** (Microsoft)
   - Soporte del lenguaje
   - Resaltado de sintaxis
   - Refactorización de código
   - Ejecución de scripts

2. **Pylance** (Microsoft)
   - IntelliSense avanzado
   - Comprobación de tipos
   - Auto-importaciones

3. **Python Debugger** (Microsoft)
   - Soporte de depuración
   - Breakpoints
   - Inspección de variables

**Instalación:**
1. Abre VS Code
2. Busca "Python" en Extensions
3. Instala las tres extensiones de Microsoft
4. Reinicia si es necesario

### Shell Interactiva de Python (REPL)

**REPL:** Read-Eval-Print-Loop (Leer-Evaluar-Imprimir-Bucle)

**Acceso:**
```bash
python3
# o
python
```

**Uso:**
```python
>>> 2 + 2
4
>>> print("Hello World")
Hello World
>>> quit()  # Salir del REPL
```

**Propósito:**
- Pruebas rápidas
- Experimentación
- Aprendizaje
- No para escribir programas completos

---

## 6. Primer Programa - Hola Mundo

### Convenciones de Nombrado de Archivos

**Extensión de Archivo de Python:** `.py`

**Convención de Nombrado:**
- Todo en minúsculas
- Palabras separadas por guiones bajos (snake_case)
- Ejemplo: `01_basic.py`, `hello_world.py`

**¿Por qué snake_case?**
- Python lleva el nombre de una serpiente (snake)
- Consistente con la guía de estilo de Python (PEP 8)

### Creando Tu Primer Programa

**Archivo:** `01_print.py`

```python
print("Hello World")
```

### Ejecutando Archivos de Python

#### Método 1: Terminal/Línea de Comandos

```bash
# Navegar a la ubicación del archivo
cd 01_basic

# Ejecutar el archivo
python3 01_print.py
```

**Salida:**
```
Hello World
```

#### Método 2: Botón Run de VS Code

1. Abre el archivo de Python
2. Haz clic en el icono "Run Python File" (arriba a la derecha)
3. O usa el atajo de teclado (configurable, por defecto: `Cmd+Enter` en macOS)
4. La salida aparece en la terminal integrada

**Funciones de VS Code:**
- Vista dividida (código + terminal lado a lado)
- Auto-desplazamiento a la última salida
- Depuración integrada
- La terminal permanece abierta para varias ejecuciones

---

## 7. La Función Print

### Uso Básico

La función `print()` muestra información en la consola. Es la primera función que aprenderás y probablemente la última que seguirás usando.

**Sintaxis:**
```python
print(value)
```

### Comillas de Cadenas

Python soporta comillas simples y dobles para las cadenas:

```python
print("Hello Twitch")  # Comillas dobles
print('Hello Twitch')  # Comillas simples - equivalente
```

**Cuándo usar cuál:**
- Usa comillas dobles si la cadena contiene comillas simples
- Usa comillas simples si la cadena contiene comillas dobles

**Ejemplo:**
```python
print("It's working")     # Comillas dobles para cadena con apóstrofo
print('He said "Hello"')  # Comillas simples para cadena con comillas dobles
```

### Múltiples Valores

Print puede aceptar varios valores separados por comas:

```python
print("Python", "is", "great")
# Salida: Python is great
```

**Separador por Defecto:**
- Los valores se separan por un espacio por defecto
- Esto es configurable

### Separador Personalizado (sep)

Cambia el separador entre los valores usando el parámetro `sep`:

```python
print("Python", "is", "awesome", sep="-")
# Salida: Python-is-awesome
```

**Parámetro Nombrado:**
- Debe usar el nombre del parámetro: `sep=`
- Puede ser cualquier cadena

### Parámetro End

Controla lo que se imprime al final de la línea usando `end`:

**Comportamiento por defecto:**
```python
print("First line")
print("Second line")
# Salida:
# First line
# Second line
```

**End personalizado:**
```python
print("This prints ", end="")
print("on one line")
# Salida: This prints on one line
```

**Otro ejemplo:**
```python
print("Word", end="!")
print("Another")
# Salida: Word!Another
```

### Valores por Defecto

**Ver la firma de la función en VS Code:**
- Pasa el cursor sobre la función `print()`
- Verás un popup con la documentación

**Firma:**
```python
print(*values, sep=' ', end='\n')
```

**Valores por defecto:**
- `sep=' '` - Separador de espacio
- `end='\n'` - Salto de línea al final

**Parámetros:**
- `sep` - Separador entre los valores (por defecto: espacio)
- `end` - Lo que se imprime al final (por defecto: salto de línea)

### Ejemplos

```python
# Print básico
print("Hello World")

# Múltiples valores con separador por defecto
print("Python", "es", "genial")
# Salida: Python es genial

# Separador personalizado
print("Python", "es", "brutal", sep="-")
# Salida: Python-es-brutal

# Carácter de fin personalizado
print("Esto se imprime", end=" ")
print("en una línea")
# Salida: Esto se imprime en una línea

# Combinando ambos
print("A", "B", "C", sep=":", end="!\n")
print("Next line")
# Salida:
# A:B:C!
# Next line
```

---

## 8. Tipos de Datos

### Visión General

Python tiene varios tipos de datos integrados:

1. **Enteros** (int) - Números enteros
2. **Flotantes** (float) - Números decimales
3. **Cadenas** (str) - Texto
4. **Booleanos** (bool) - True/False
5. **None** (NoneType) - Ausencia de valor
6. **Listas** - Colecciones ordenadas
7. **Tuplas** - Colecciones ordenadas inmutables
8. **Diccionarios** (dict) - Pares clave-valor
9. **Conjuntos (Sets)** - Colecciones únicas sin orden
10. **Rangos** - Secuencias de números
11. **Complejos** - Números complejos

### La Función type()

Comprueba el tipo de cualquier valor:

```python
type(value)
```

### Enteros (int)

Números enteros sin puntos decimales:

```python
print(type(10))        # <class 'int'>
print(type(0))         # <class 'int'>
print(type(-5))        # <class 'int'>
print(type(1234567890123456789012345))  # <class 'int'>
```

**Característica Importante:**
- Los enteros de Python tienen **precisión arbitraria**
- Sin problemas de overflow como en JavaScript u otros lenguajes
- Pueden representar números extremadamente grandes con precisión

**Ejemplo de la ventaja de Python:**
```python
# Python
big_number = 12345678901234567890
print(big_number + 1)  # Imprime correctamente: 12345678901234567891

# JavaScript tendría problemas de precisión con números tan grandes
```

**Sin limitaciones de tamaño:**
- No hay que especificar 8-bit, 16-bit, 32-bit, 64-bit
- Python gestiona la asignación de memoria automáticamente
- Funciona con números de cualquier tamaño

### Flotantes (float)

Números con puntos decimales:

```python
print(type(3.14))      # <class 'float'>
print(type(1.0))       # <class 'float'> - aunque el valor sea entero
print(type(0.0))       # <class 'float'>
print(type(-2.5))      # <class 'float'>
```

**Notación Científica:**
```python
print(type(1e3))       # <class 'float'> - representa 1000.0
print(1e3)             # Salida: 1000.0
```

**Puntos Clave:**
- Cualquier número con punto decimal es float
- La notación científica siempre produce float
- `1.0` es float, `1` es int

### Cadenas (str)

Datos de texto encerrados entre comillas:

```python
print(type("Hello"))           # <class 'str'>
print(type('Hello'))           # <class 'str'>
print(type(""))                # <class 'str'> - cadena vacía
print(type("123"))             # <class 'str'> - número como cadena
```

**Cadenas Multilínea:**
```python
# Triples comillas para cadenas multilínea
multiline = """
This is
a multi-line
string
"""
print(type(multiline))  # <class 'str'>

# También funciona con comillas simples
multiline2 = '''
Another
multi-line
string
'''
```

### Booleanos (bool)

Valores True o False:

```python
print(type(True))      # <class 'bool'>
print(type(False))     # <class 'bool'>
```

**A partir de Comparaciones:**
```python
print(type(1 > 2))     # <class 'bool'> - evalúa a False
print(type(1 < 2))     # <class 'bool'> - evalúa a True
print(1 > 2)           # Salida: False
print(1 < 2)           # Salida: True
```

**Nota:**
- En mayúscula: `True`, `False` (no `true`, `false`)
- Cualquier operación lógica devuelve un bool

### None (NoneType)

Representa la ausencia de valor:

```python
print(type(None))      # <class 'NoneType'>
```

**Propósito:**
- Un solo valor para representar la ausencia
- A diferencia de JavaScript (tiene tanto `null` como `undefined`)
- Más simple y menos confuso

**Casos de Uso:**
- Valores por defecto de parámetros
- Retornos de función cuando no se devuelve ningún valor
- Marcador de posición para datos faltantes

### Números Complejos

Para la computación matemática y científica:

```python
complex_num = 3 + 4j
print(type(complex_num))  # <class 'complex'>
```

**Estructura:**
- Parte real + Parte imaginaria
- Usa `j` o `J` para la unidad imaginaria (no `i`)
- Útil en la computación científica

---

## 9. Conversión de Tipos (Type Casting)

### Visión General

**Conversión de Tipos (Type Casting):** Convertir un valor de un tipo a otro

Python tiene **tipado fuerte** - NO convierte automáticamente entre tipos incompatibles. Debes convertir los tipos explícitamente cuando sea necesario.

### Por Qué Importa la Conversión de Tipos

**Ejemplo de Error de Tipo:**
```python
print("100" + 2)  # ERROR: can only concatenate str to str, not int
```

Python no convertirá automáticamente una cadena a número o viceversa.

### Conversión a Entero: int()

**Cadena a Entero:**
```python
print(int("100"))          # 100
print(type(int("100")))    # <class 'int'>

# Ahora podemos hacer matemáticas
print(int("100") + 2)      # 102
```

**Flotante a Entero (pierde precisión):**
```python
print(int(3.14))           # 3 (parte decimal eliminada, no redondeada)
print(int(3.9))            # 3 (parte decimal eliminada)
print(int(-2.7))           # -2 (parte decimal eliminada)
```

**Importante:**
- `int()` trunca, NO redondea
- Todo lo que está después del punto decimal se descarta

### Conversión a Flotante: float()

**Cadena a Flotante:**
```python
print(float("3.14"))       # 3.14
print(type(float("3.14"))) # <class 'float'>
```

**Entero a Flotante:**
```python
print(float(100))          # 100.0
print(float(5))            # 5.0
```

### Conversión a Cadena: str()

**Número a Cadena:**
```python
print(str(100))            # "100"
print(type(str(100)))      # <class 'str'>

# La concatenación ahora funciona
print("100" + str(2))      # "1002" (concatenación de cadenas)
print(str(2) + "100")      # "2100"
```

### Conversión a Booleano: bool()

**Números a Booleano:**
```python
print(bool(3))             # True
print(bool(0))             # False (solo el cero es False)
print(bool(-1))            # True (los números negativos son True)
```

**Regla Importante:**
- Solo `0` se convierte en `False`
- Cualquier otro número (positivo o negativo) se convierte en `True`

**Cadenas a Booleano:**
```python
print(bool(""))            # False (cadena vacía)
print(bool(" "))           # True (el espacio es contenido)
print(bool("false"))       # True (cualquier cadena no vacía es True)
print(bool("0"))           # True (la cadena "0" no está vacía)
```

**Regla Importante:**
- Solo la cadena vacía `""` se convierte en `False`
- Cualquier cadena con contenido (incluso un espacio) se convierte en `True`

### Redondeo: round()

**Diferente del truncamiento de int():**
```python
# int() trunca
print(int(2.5))            # 2 (truncado)
print(int(3.6))            # 3 (truncado)

# round() redondea
print(round(3.6))          # 4 (redondeado hacia arriba)
print(round(3.4))          # 3 (redondeado hacia abajo)
```

**Redondeo del Banquero (redondea al par):**
```python
print(round(2.5))          # 2 (redondea al par más cercano)
print(round(3.5))          # 4 (redondea al par más cercano)
print(round(4.5))          # 4 (redondea al par más cercano)
```

**¿Por qué "Redondeo del Banquero"?**
- Cuando está exactamente a la mitad (x.5), redondea al número par más cercano
- Reduce el sesgo de redondeo acumulado
- Convención matemática para prevenir el sesgo sistemático

**Ejemplos:**
```python
print(round(2.5))          # 2 (par)
print(round(3.5))          # 4 (par)
print(round(4.5))          # 4 (par)
print(round(5.5))          # 6 (par)
```

### Errores de Conversión de Tipos

**Conversiones Inválidas:**
```python
# Esto dará ERROR
print(int("Hello World"))
# ValueError: invalid literal for int() with base 10: 'Hello World'
```

**No todas las conversiones son posibles:**
- No se pueden convertir cadenas arbitrarias a números
- Debe ser una representación válida
- Python lanza `ValueError` para conversiones inválidas

### Ejemplos Prácticos

**Aritmética de Tipos Mixtos:**
```python
# ERROR - no se pueden mezclar tipos
print(2 + "100")           # ERROR

# Solución 1: Convertir la cadena a int
print(2 + int("100"))      # 102

# Solución 2: Convertir ambos a cadenas
print(str(2) + "100")      # "2100"
```

**Conversión de la Entrada del Usuario:**
```python
# input siempre devuelve una cadena
age = input("Enter age: ")  # Devuelve una cadena
age_num = int(age)          # Convertir a entero
print(age_num + 1)          # Ahora podemos hacer matemáticas
```

### Tabla Resumen

| Función | Propósito | Ejemplo | Resultado |
|----------|---------|---------|--------|
| `int()` | Convertir a entero | `int("100")` | `100` |
| `float()` | Convertir a flotante | `float("3.14")` | `3.14` |
| `str()` | Convertir a cadena | `str(100)` | `"100"` |
| `bool()` | Convertir a booleano | `bool(0)` | `False` |
| `round()` | Redondear al entero más cercano | `round(3.6)` | `4` |
| `type()` | Obtener el tipo de un valor | `type(100)` | `<class 'int'>` |

---

## 10. Comentarios

### Comentarios de Una Línea

Usa el símbolo de almohadilla `#`:

```python
# Esto es un comentario
print("Hello")  # Esto también es un comentario

# Los comentarios son ignorados por Python
# Son solo para los lectores humanos
```

**Uso:**
- Explicar código complejo
- Deshabilitar código temporalmente
- Añadir notas y documentación

### Comentarios Multilínea

**Método 1: Múltiples almohadillas**
```python
# Esto es un
# comentario
# multilínea
```

**Método 2: Cadenas con triples comillas (docstrings)**
```python
"""
Esto es un comentario multilínea
usando triples comillas dobles.
A menudo usado para documentación.
"""

'''
Esto también funciona
con triples comillas simples.
'''
```

**Nota sobre el Método 2:**
- Técnicamente crea una cadena
- Si no se asigna a una variable, actúa como un comentario
- Preferido para cadenas de documentación (docstrings)
- Se prefiere el `#` simple para comentarios reales

### Buenas Prácticas

```python
# Bien: Explica el PORQUÉ
# Calcular el interés compuesto usando la fórmula estándar
result = principal * (1 + rate) ** time

# Mal: Explica el QUÉ (obvio del código)
# Sumar 1 y 2
result = 1 + 2
```

**Guía de Estilo PEP 8:**
- Mantén los comentarios actualizados
- Escribe los comentarios en oraciones completas
- Usa los comentarios con moderación - el buen código se autodocumenta
- Prefiere `#` para comentarios
- Usa `"""docstrings"""` para la documentación de funciones/clases

---

## Recursos Adicionales

### Documentación Oficial
- [Python.org](https://www.python.org/) - Sitio web oficial
- [Python Documentation](https://docs.python.org/) - Referencia completa

### Plataformas de Práctica
- [pythonsandbox.com](https://pythonsandbox.com) - Editor de Python en línea
- [replit.com](https://replit.com) - IDE en línea
- [leetcode.com](https://leetcode.com) - Retos de programación
- [hackerrank.com](https://hackerrank.com) - Práctica de Python

### Recursos de Aprendizaje
- Tutorial oficial de Python
- Tutoriales de Real Python
- Comunidad del subreddit de Python
- Stack Overflow para preguntas

---

## 11. Funcionalidades Modernas de Python (3.10+)

### Pattern Matching (3.10+)

Python 3.10 introdujo el pattern matching estructural usando sentencias `match`/`case` (similar a switch/case en otros lenguajes, pero más potente).

**Uso Básico:**
```python
def http_status(status):
    match status:
        case 200:
            return "OK"
        case 404:
            return "Not Found"
        case 500:
            return "Internal Server Error"
        case _:  # Caso por defecto (comodín)
            return "Unknown"

print(http_status(404))  # Salida: Not Found
```

**Pattern Matching con Estructura:**
```python
def process_command(command):
    match command.split():
        case ["quit"]:
            return "Exiting..."
        case ["load", filename]:
            return f"Loading {filename}"
        case ["save", filename]:
            return f"Saving {filename}"
        case _:
            return "Unknown command"

print(process_command("load data.csv"))  # Salida: Loading data.csv
```

**Coincidencia de Estructuras de Datos:**
```python
def describe_point(point):
    match point:
        case (0, 0):
            return "Origin"
        case (0, y):
            return f"On Y-axis at {y}"
        case (x, 0):
            return f"On X-axis at {x}"
        case (x, y):
            return f"Point at ({x}, {y})"

print(describe_point((0, 5)))  # Salida: On Y-axis at 5
```

### Operador de Tipo Unión (3.10+)

**Nueva Sintaxis para las Anotaciones de Tipo:**
```python
# Forma antigua (aún funciona)
from typing import Union

def process_id(id: Union[int, str]) -> str:
    return str(id)

# Nueva forma (Python 3.10+)
def process_id(id: int | str) -> str:
    return str(id)

# Múltiples tipos
def format_value(value: int | float | str | None) -> str:
    if value is None:
        return "No value"
    return str(value)
```

### Grupos de Excepciones (3.11+)

**Manejo de Múltiples Excepciones:**
```python
# Lanzar múltiples excepciones
def process_data(data):
    errors = []
    for item in data:
        try:
            validate(item)
        except ValueError as e:
            errors.append(e)

    if errors:
        raise ExceptionGroup("Validation errors", errors)

# Capturar grupos de excepciones
try:
    process_data(items)
except* ValueError as eg:  # Nota el * (captura de un grupo de excepciones)
    print(f"Got {len(eg.exceptions)} validation errors")
except* TypeError as eg:
    print(f"Got {len(eg.exceptions)} type errors")
```

### Mensajes de Error Mejorados (3.10+, 3.11+)

Python 3.10+ proporciona mensajes de error mucho mejores:

```python
# Error de Python 3.9 y anteriores:
# NameError: name 'dictionary' is not defined

# Error de Python 3.10+:
# NameError: name 'dictionary' is not defined. Did you mean: 'dict'?

# Python 3.11+ con mejores tracebacks:
some_dict = {"key": "value"}
result = some_dict["missing_key"]
# KeyError: 'missing_key'
# El error ahora apunta exactamente a la parte problemática
```

### Mejoras en las F-Strings (3.12+)

**Expresiones en Línea y Depuración:**
```python
# F-string básica
name = "Alice"
print(f"Hello, {name}")  # Salida: Hello, Alice

# Python 3.8+: depuración con f-string
value = 42
print(f"{value=}")  # Salida: value=42

# Python 3.12+: F-strings multilínea
message = f"""
User: {name}
Value: {value}
Result: {value * 2}
"""

# F-strings reutilizables (3.12+)
formatted = f"Hello, {name}"
```

### Sintaxis de Parámetros de Tipo (3.12+ / PEP 695)

**Tipos Genéricos Simplificados:**
```python
# Forma antigua (antes de 3.12)
from typing import TypeVar, Generic

T = TypeVar('T')

class Box(Generic[T]):
    def __init__(self, content: T):
        self.content = content

# Nueva forma (Python 3.12+)
class Box[T]:
    def __init__(self, content: T):
        self.content = content

# Funciones genéricas
def first[T](items: list[T]) -> T:
    return items[0]
```

### Mejoras de Rendimiento

**Rendimiento de Python 3.11+:**
- Hasta un 60% más rápido que Python 3.10 (media del 25% más rápido)
- Tiempo de arranque más rápido
- Mejor eficiencia de memoria
- Pila de frames optimizada

**Funcionalidades de Python 3.13+:**
- Modo free-threaded experimental (sin GIL)
- Experimentos con compilador Just-In-Time (JIT)
- Mejoras de rendimiento continuas

### Buenas Prácticas para Python Moderno

**1. Usa Anotaciones de Tipo:**
```python
# Bien: Los tipos claros ayudan con el soporte del IDE y la documentación
def calculate_total(price: float, quantity: int) -> float:
    return price * quantity

# Usar para tipos complejos
from typing import Any

def process_data(data: list[dict[str, Any]]) -> dict[str, int]:
    return {"count": len(data)}
```

**2. Usa match/case para Condiciones Complejas:**
```python
# En lugar de múltiples if/elif
# Mal:
if action == "start":
    start_process()
elif action == "stop":
    stop_process()
elif action == "restart":
    restart_process()

# Bien (Python 3.10+):
match action:
    case "start":
        start_process()
    case "stop":
        stop_process()
    case "restart":
        restart_process()
```

**3. Prefiere el Operador Unión para los Tipos:**
```python
# Moderno (3.10+)
def get_user(user_id: int | str) -> dict | None:
    pass

# En lugar de la sintaxis antigua de Union
from typing import Union, Optional
def get_user(user_id: Union[int, str]) -> Optional[dict]:
    pass
```

**4. Usa el operador walrus (3.8+) cuando sea apropiado:**
```python
# Leer las líneas de un archivo que tengan más de 10 caracteres
with open("file.txt") as f:
    while (line := f.readline()) and len(line) > 10:
        print(line)

# Comprobar y usar un valor
if (value := expensive_function()) is not None:
    use_value(value)
```

---

## 12. Fundamentos de la Resolución de Problemas

### ¿Qué es la Resolución de Problemas en Ciencias de la Computación?

La resolución de problemas en ciencias de la computación implica dos pasos principales:

1. **Formalizar una solución general** que funcione para cada instancia de un problema
2. **Hacer que esa solución se ejecute en una computadora** usando lenguajes de programación

**Concepto Clave:**
- Algunos problemas son fáciles de resolver, otros son difíciles y algunos son irresolubles
- Cuando necesitas resolver el mismo problema repetidamente con datos distintos (instancias), la **automatización** es la opción óptima
- Python hace que la transición de la resolución del problema a la solución en ejecución sea mucho más fácil y rápida

### El Marco Problema-Solución

**Escenario de Ejemplo:**
Imagina que necesitas encontrar el correo del cliente con las ventas máximas cada 8 horas a partir de los registros de ventas.

**Características del Problema:**
- **Mismo problema** - Encontrar el cliente con ventas máximas
- **Instancias distintas** - Datos de ventas distintos cada 8 horas
- **Repetitivo** - Necesita hacerse una y otra vez
- **Automatizable** - Candidato perfecto para una solución de programación

### Solución Paso a Paso (Algoritmo)

Una solución general para encontrar el cliente con ventas máximas:

```
1. Empezar desde el primer registro
2. Enfocarse en la columna de ventas
3. Ir a cada registro siguiente uno por uno
4. Encontrar el registro con las ventas máximas
5. Si varios registros tienen las ventas máximas, elegir el primero (de arriba a abajo)
6. Enfocarse en la columna de correo de ese registro
7. Escribir esa dirección de correo en los registros de prioridad
8. Repetir este procedimiento cada 8 horas
```

**Conceptos Importantes:**
- **Solución general** - Funciona para CUALQUIER instancia del problema
- **Paso a paso** - Secuencia clara de operaciones
- **Sin ambigüedad** - Cada paso tiene un significado preciso
- **Repetible** - Se puede ejecutar varias veces

### ¿Qué Hace a una Buena Solución?

**Requisitos:**
1. **Completitud** - Cubre todos los casos posibles
2. **Claridad** - Los pasos son fáciles de entender
3. **Precisión** - Sin instrucciones ambiguas
4. **Generalidad** - Funciona para cualquier entrada válida
5. **Eficiencia** - Resuelve el problema de forma óptima

**Comunicación:**
- Las soluciones deben comunicarse con claridad
- El formato paso a paso permite la comprensión
- Puede ser en lenguaje natural, pero tiene limitaciones

---

## 13. Algoritmos

### ¿Qué es un Algoritmo?

**Definición:** Un algoritmo es un procedimiento paso a paso para resolver un problema que funciona para cada instancia de ese problema.

**Características:**
- **Secuencial** - Los pasos se ejecutan en orden
- **Sin ambigüedad** - Cada paso tiene un significado claro
- **Finito** - Eventualmente termina
- **Efectivo** - Cada paso es alcanzable
- **General** - Resuelve todas las instancias del problema

### Del Lenguaje Natural a los Algoritmos Formales

**Problema con el Lenguaje Natural:**
- Expresivo pero ambiguo
- Múltiples interpretaciones posibles
- No es lo suficientemente preciso para las computadoras

**Solución:**
- Usar formas estructuradas de expresar los algoritmos
- Introducir palabras clave con significados únicos
- Seguir convenciones consistentes
- Pasar del inglés a una notación más formal

### Ejemplo de Algoritmo: Calcular el Salario de un Empleado

**Problema:** Calcular el salario de los empleados según las horas trabajadas y la tarifa por hora

**Variables:**
- `hours` - Número de horas trabajadas (varía según el empleado)
- `rate` - Tarifa de pago por hora (varía según el empleado)
- `pay` - Salario calculado

**Pasos del Algoritmo:**
1. Ingresar las horas trabajadas
2. Ingresar la tarifa por hora
3. Calcular: `pay = hours × rate`
4. Mostrar el valor del salario

**Idea Clave:**
- Mismo procedimiento para cada empleado
- Valores distintos (instancias) para cada empleado
- El algoritmo permanece constante, los datos cambian

---

## 14. Pseudocódigo

### ¿Qué es el Pseudocódigo?

**Definición:** Una forma estructurada de expresar algoritmos usando una sintaxis simplificada similar a la programación sin seguir las reglas de ningún lenguaje específico.

**Beneficios:**
- Más preciso que el lenguaje natural
- Menos complejo que el código real
- Agnóstico al lenguaje
- Fácil de convertir a cualquier lenguaje de programación
- Se enfoca en la lógica, no en la sintaxis

### Convenciones del Pseudocódigo

**Palabras clave:** Usa palabras clave consistentes y significativas en todo momento

Palabras clave comunes:
- `BEGIN` / `END` - Marcan el inicio y el fin del programa
- `INPUT` - Obtener datos del usuario/sistema
- `OUTPUT` / `PRINT` - Mostrar resultados
- `IF...THEN...ELSE` - Lógica condicional
- `WHILE...END WHILE` - Bucles/repetición
- `=` o `←` - Asignación

### Ejemplo: Salario de Empleado (Pseudocódigo)

```
BEGIN
    INPUT hours
    INPUT rate
    pay ← hours × rate
    OUTPUT pay
END
```

o de forma más verbosa:

```
BEGIN
    GET hours
    GET rate
    MULTIPLY hours AND rate
    STORE result in pay
    DISPLAY pay
END
```

### Indentación y Estructura

**Regla Importante:** Usa la indentación para mostrar los bloques de código y la jerarquía

```
WHILE condition is true
    statement 1
    statement 2
    statement 3
END WHILE
```

**Cuerpo del bucle** - Las sentencias indentadas muestran lo que hay dentro del bucle

### Ejemplo: Hacer Té (Pseudocódigo)

```
PROGRAM MakeTea

    PUT teabag in cup

    WHILE water NOT boiled
        BOIL water
    END WHILE

    POUR water in cup

    WHILE sugar needed
        ADD sugar
    END WHILE

    WHILE milk needed
        ADD milk
    END WHILE

    WHILE need to stir
        STIR tea
    END WHILE

    SERVE tea

END PROGRAM
```

**Características Clave:**
- **Bucles** - Repetir acciones hasta que se cumpla una condición
- **Secuencia** - Pasos en orden lógico
- **Claridad** - Lógica fácil de entender

---

## 15. Diagramas de Flujo

### ¿Qué son los Diagramas de Flujo?

**Definición:** Representación gráfica de algoritmos usando formas estandarizadas y flechas.

### Símbolos Estándar de Diagramas de Flujo

| Forma | Significado | Uso |
|-------|---------|-------|
| **Óvalo** | Inicio/Fin | Comienzo o final del proceso |
| **Paralelogramo** | Entrada/Salida | Operaciones de entrada o salida de datos |
| **Rectángulo** | Proceso | Cálculo o acción |
| **Rombo** | Decisión | Ramificación condicional (Sí/No) |
| **Flecha** | Flujo | Dirección del flujo del proceso |
| **Círculo** | Conector | Conectar distintas partes del diagrama |

### Ejemplo de Diagrama de Flujo: Salario de Empleado

```
┌─────────┐
│  START  │
└────┬────┘
     │
     ▼
┌─────────────┐
│ INPUT hours │
└─────┬───────┘
      │
      ▼
┌─────────────┐
│ INPUT rate  │
└─────┬───────┘
      │
      ▼
┌──────────────────┐
│ pay = hours × rate│
└─────┬────────────┘
      │
      ▼
┌─────────────┐
│ OUTPUT pay  │
└─────┬───────┘
      │
      ▼
┌─────────┐
│   END   │
└─────────┘
```

### Ejemplo de Diagrama de Flujo: Hacer Té (con Bucles)

```
┌─────────┐
│  START  │
└────┬────┘
     │
     ▼
┌──────────────┐
│ Put teabag   │
│   in cup     │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│  Boil water  │
└──────┬───────┘
       │
       ▼
    ┌──────────────┐
    │ Water boiled?│◄───┐
    └──┬────────┬──┘    │
       │ No     │ Yes   │
       │        │       │
       └────────┘       │
       (loop back)      │
                        │
                        ▼
                ┌───────────────┐
                │ Pour water    │
                └───────┬───────┘
                        │
                        ▼
                ┌───────────────┐
            ┌───│ Need sugar?   │
            │   └───┬───────┬───┘
            │  Yes  │       │ No
            │       ▼       │
            │  ┌─────────┐  │
            └──│Add sugar│  │
               └─────────┘  │
                           ▼
                     ┌──────────┐
                     │   END    │
                     └──────────┘
```

### Diagramas de Flujo vs Pseudocódigo

**Diagramas de Flujo:**
- ✅ Visuales e intuitivos
- ✅ Buenos para pruebas de concepto
- ✅ Fáciles de explicar a no programadores
- ❌ Tediosos para problemas complejos
- ❌ Más difíciles de convertir a código

**Pseudocódigo:**
- ✅ Más cercano al código de programación real
- ✅ Más fácil de escribir para lógica compleja
- ✅ Simple de convertir a Python/cualquier lenguaje
- ✅ Más factible para proyectos grandes
- ❌ Menos visual que los diagramas de flujo

**Buena Práctica:** Usa diagramas de flujo para el diseño inicial, luego conviértelos a pseudocódigo antes de programar.

---

## 16. Algoritmos de Búsqueda

### Problema: Encontrar el Valor Mínimo en una Lista

**Dado:** Una lista de números
**Tarea:** Encontrar el valor más pequeño y su posición

**Ejemplo:**
```
Lista: [23, -4, 0, 73, -10, 13]
Resultado: Valor mínimo = -10, Posición = 5
```

### Algoritmo: Buscar el Mínimo de una Lista

**Pseudocódigo:**

```
ALGORITHM SearchMinFromList(L, n)
    // L es la lista, n es el tamaño

    // Inicializar con el primer elemento
    minValue ← L[1]
    idx ← 1
    counter ← 2

    // Recorrer el resto de la lista
    WHILE counter ≤ n
        v ← L[counter]

        IF v < minValue THEN
            minValue ← v
            idx ← counter
        END IF

        counter ← counter + 1
    END WHILE

    RETURN minValue, idx
END ALGORITHM
```

### Ejemplo de Ejecución Paso a Paso

**Lista:** `[23, -4, 0, 73, -10, 13]`, **n = 6**

| Paso | counter | v | minValue | idx | Acción |
|------|---------|---|----------|-----|--------|
| Init | 2 | - | 23 | 1 | Empezar con el primer elemento |
| 1 | 2 | -4 | -4 | 2 | -4 < 23, actualizar min |
| 2 | 3 | 0 | -4 | 2 | 0 > -4, sin cambio |
| 3 | 4 | 73 | -4 | 2 | 73 > -4, sin cambio |
| 4 | 5 | -10 | -10 | 5 | -10 < -4, actualizar min |
| 5 | 6 | 13 | -10 | 5 | 13 > -10, sin cambio |
| 6 | 7 | - | -10 | 5 | counter > n, salir del bucle |

**Resultado:** minValue = -10, idx = 5

### Conceptos Clave

**1. Recorrido:**
- Visitar cada elemento una vez
- Usar un contador/índice para rastrear la posición

**2. Comparación:**
- Comparar el elemento actual con el mínimo actual
- Actualizar si se encuentra un valor menor

**3. Rastreo:**
- Mantener el rastro tanto del valor como de la posición
- Esencial para muchos algoritmos

---

## 17. Algoritmos de Ordenamiento

### Problema: Ordenar una Lista en Orden Ascendente

**Dado:** Una lista de números sin ordenar
**Tarea:** Organizar los números de menor a mayor

**Ejemplo:**
```
Entrada:  [14, 0, 35, 7]
Salida: [0, 7, 14, 35]
```

### Algoritmo: Selection Sort (Ordenamiento por Selección)

**Concepto:** Encontrar repetidamente el elemento mínimo y moverlo a una lista ordenada.

**Pseudocódigo:**

```
ALGORITHM SortList(L, n)
    // L es la lista original, n es el tamaño
    L2 ← []  // Lista vacía para los valores ordenados
    counter ← 1

    WHILE counter ≤ n
        // Encontrar el mínimo de la lista restante
        minValue, idx ← SearchMinFromList(L, n)

        // Añadir el mínimo a la lista ordenada
        INSERT minValue in L2

        // Eliminar el mínimo de la lista original
        DELETE L[idx] from L

        // Disminuir el contador de tamaño
        n ← n - 1

        counter ← counter + 1
    END WHILE

    RETURN L2
END ALGORITHM
```

### Ejemplo de Ejecución Paso a Paso

**Lista Inicial:** `[14, 0, 35, 7]`, **n = 4**

| Iteración | L (sin ordenar) | Encontrar Min | L2 (ordenada) | n |
|-----------|--------------|----------|-------------|---|
| 0 | [14, 0, 35, 7] | - | [] | 4 |
| 1 | [14, 0, 35, 7] | 0 (idx=2) | [0] | 3 |
| 2 | [14, 35, 7] | 7 (idx=3) | [0, 7] | 2 |
| 3 | [14, 35] | 14 (idx=1) | [0, 7, 14] | 1 |
| 4 | [35] | 35 (idx=1) | [0, 7, 14, 35] | 0 |

**Resultado Final:** `[0, 7, 14, 35]`

### Reutilización de Algoritmos

**Concepto Importante:**
- El algoritmo `SortList` **usa** el algoritmo `SearchMinFromList`
- Descomponer problemas complejos en subproblemas más pequeños
- Enfoque modular para la resolución de problemas
- Reutilización de código

### Nota sobre Complejidad

Selection Sort es un algoritmo de ordenamiento simple usado aquí con **fines didácticos**. Existen algoritmos de ordenamiento más eficientes (Quick Sort, Merge Sort, Heap Sort) usados en sistemas de producción.

---

## 18. Introducción a la Ciencia de Datos

### Áreas de Enfoque

**Áreas Centrales:**

1. **Resolución de Problemas** - Lógica fundamental y pensamiento algorítmico
2. **Programación en Python** - Dominio completo del lenguaje desde lo básico hasta lo avanzado
3. **Paquetes de Ciencia de Datos** - NumPy, Pandas, Matplotlib para el análisis de datos
4. **Aplicaciones Prácticas** - Problemas de ciencia de datos del mundo real

### ¿Por Qué Python para la Ciencia de Datos?

**Ventajas Clave:**

1. **Fácil de Aprender**
   - Sintaxis simple
   - Curva de aprendizaje rápida
   - Código legible

2. **Librerías Potentes**
   - NumPy - Computación numérica
   - Pandas - Manipulación de datos
   - Matplotlib - Visualización de datos
   - Scikit-learn - Machine learning

3. **Procesamiento Rápido de Datos**
   - Manejar grandes conjuntos de datos
   - Cálculos eficientes
   - Librerías optimizadas

4. **Versátil**
   - Limpieza de datos
   - Procesamiento de datos
   - Visualización
   - Análisis estadístico
   - Machine learning

### Lo Que NO Vamos a Cubrir

**Fuera del Alcance:**
- Programación Orientada a Objetos (OOP)
- Manejo de Excepciones
- Desarrollo Web
- Tareas generales de Python no relacionadas con la ciencia de datos

**Enfoque:**
Este es material de ciencia de datos de **nivel principiante** que asume:
- Sin experiencia previa en programación
- Sin formación en ciencias de la computación
- Empezando desde cero absoluto

### Camino de Aprendizaje

**Fase 1: Fundamentos**
1. Paradigmas de resolución de problemas
2. Por qué Python para la ciencia de datos
3. Instalación y configuración de Python
4. Sintaxis y conceptos básicos

**Fase 2: Dominio de Python**
1. Variables y tipos de datos
2. Estructuras de control (if, while, for)
3. Estructuras de datos (listas, tuplas, diccionarios)
4. Funciones y módulos
5. Manejo de archivos

**Fase 3: Ciencia de Datos**
1. NumPy para la computación numérica
2. Pandas para la manipulación de datos
3. Matplotlib para la visualización
4. Proyectos de datos del mundo real

### De Pseudocódigo a Python

**La Transición:**
El pseudocódigo que hemos aprendido se convierte fácilmente a Python:

**Pseudocódigo:**
```
minValue ← L[1]
WHILE counter ≤ n
    IF v < minValue THEN
        minValue ← v
    END IF
END WHILE
```

**Python:**
```python
min_value = L[0]
while counter <= n:
    if v < min_value:
        min_value = v
```

**Diferencias Clave:**
- Python usa `def` para definir funciones
- La indentación es obligatoria (no solo estilo)
- Los dos puntos `:` marcan el comienzo de los bloques
- Estructura muy similar al pseudocódigo

### Flujo de Trabajo de la Ciencia de Datos

**Proceso Típico de Ciencia de Datos:**

1. **Definición del Problema**
   - Entender la pregunta de negocio
   - Definir las métricas de éxito

2. **Recolección de Datos**
   - Reunir datos relevantes
   - Importar de varias fuentes

3. **Limpieza de Datos**
   - Manejar valores faltantes
   - Eliminar duplicados
   - Corregir inconsistencias

4. **Exploración de Datos**
   - Entender la distribución de los datos
   - Encontrar patrones
   - Visualizar relaciones

5. **Análisis de Datos**
   - Análisis estadístico
   - Ingeniería de características (feature engineering)
   - Construcción de modelos

6. **Comunicación de Resultados**
   - Crear visualizaciones
   - Presentar hallazgos
   - Hacer recomendaciones

### Paquetes Esenciales de Ciencia de Datos

**NumPy:**
- Arrays numéricos
- Operaciones matemáticas
- Álgebra lineal
- Cálculos rápidos

**Pandas:**
- DataFrames para datos tabulares
- Herramientas de limpieza de datos
- Transformación de datos
- Análisis de series temporales

**Matplotlib:**
- Gráficos 2D
- Diagramas y gráficas
- Visualizaciones personalizables
- Figuras de calidad para publicación

### Siguientes Pasos

Después de dominar los fundamentos de Python:
1. Profundizar en los arrays de NumPy
2. Aprender los DataFrames de Pandas
3. Crear visualizaciones con Matplotlib
4. Trabajar con conjuntos de datos reales
5. Construir proyectos de ciencia de datos

---

## 19. Web Scraping con Pandas

### Extraer Tablas de Sitios Web

Pandas proporciona un método simple para extraer tablas directamente de páginas HTML como Wikipedia.

#### Instalación

```bash
pip install pandas
```

#### Uso Básico

```python
import pandas as pd

# Extraer todas las tablas de un sitio web
url = "https://en.wikipedia.org/wiki/List_of_The_Simpsons_episodes"
tables = pd.read_html(url)

# Comprobar cuántas tablas se encontraron
print(len(tables))  # Devuelve el número de tablas

# Acceder a una tabla específica (índice desde 0)
first_table = tables[0]
second_table = tables[1]
```

**Puntos Clave:**
- `pd.read_html()` devuelve una **lista** de DataFrames
- Cada tabla del HTML se convierte en un DataFrame separado
- Analiza automáticamente la estructura de la tabla HTML

### Extraer Archivos CSV de URLs

En lugar de descargar archivos CSV manualmente, léelos directamente desde URLs:

```python
import pandas as pd

# URL directa al archivo CSV
csv_url = "https://www.football-data.co.uk/mmz4281/2122/E0.csv"

# Leer el CSV desde la URL
df_premier = pd.read_csv(csv_url)

# Mostrar los datos
print(df_premier.head())
```

#### Renombrar Columnas

```python
# Renombrar columnas específicas para mayor claridad
df_premier.rename(
    columns={
        'FTHG': 'home_goals',  # Full Time Home Goals
        'FTAG': 'away_goals'   # Full Time Away Goals
    },
    inplace=True
)

# Verificar los cambios
print(df_premier.columns)
```

**Casos de Uso:**
- Recolección automatizada de datos
- Actualizaciones de datos programadas
- Procesamiento por lotes de varios archivos
- Flujos de trabajo de web scraping

### Buenas Prácticas de Web Scraping

**Cuándo Usar Pandas:**
- ✅ Datos estructurados (tablas, CSV)
- ✅ Tareas de extracción simples
- ✅ Prototipado rápido

**Limitaciones:**
- ❌ Estructuras de página complejas
- ❌ Contenido renderizado con JavaScript
- ❌ Requiere autenticación
- ❌ Contenido dinámico

---

## 20. Extraer Tablas de PDFs

### Usando la Librería Camelot

Camelot permite extraer tablas de archivos PDF a CSV u otros formatos.

#### Instalación

**Dependencias Requeridas:**
```bash
# Dependencia del sistema (macOS; usa apt/yum en Linux)
brew install ghostscript

# Instalar Camelot con soporte de OpenCV
pip install "camelot-py[cv]"
```

#### Extracción Básica de Tablas de PDF

```python
import camelot

# Leer el archivo PDF
tables = camelot.read_pdf(
    'foo.pdf',           # Nombre del archivo PDF
    pages='1',           # Número de página
    flavor='lattice'     # Método de análisis (por defecto)
)

# Comprobar el número de tablas encontradas
print(tables)  # <TableList n=1>

# Exportar a CSV
tables[0].to_csv('foo.csv')
```

#### Métodos de Análisis

**Lattice (Por Defecto):**
- Funciona con tablas que tienen líneas visibles
- Más preciso para tablas con bordes

**Stream (Alternativo):**
```python
tables = camelot.read_pdf(
    'document.pdf',
    pages='1',
    flavor='stream'  # Prueba si lattice falla
)
```

- Usar cuando el método lattice falle
- Mejor para tablas sin bordes
- Se basa en el espaciado entre columnas

#### Opciones de Exportación

```python
# Exportar una sola tabla a CSV
tables[0].to_csv('output.csv')

# Exportar todas las tablas
tables.export('output.csv', f='csv', compress=True)

# Exportar a otros formatos
tables.export('output.xlsx', f='excel')
tables.export('output.json', f='json')
```

**Casos de Uso Comunes:**
- Informes financieros
- Artículos científicos
- Documentos gubernamentales
- Extracción de datos legados

---

## 21. Fundamentos de HTML para Web Scraping

### ¿Qué es HTML?

**HTML** (HyperText Markup Language) define la estructura y el significado del contenido web. Entender HTML es esencial para un web scraping efectivo.

### Sintaxis del Marcado HTML

#### Componentes de un Elemento HTML

```html
<h1 class="title">Titanic</h1>
```

**Partes:**
1. **Etiqueta de apertura:** `<h1>`
2. **Etiqueta de cierre:** `</h1>` (con barra diagonal)
3. **Atributo:** `class="title"`
4. **Contenido:** `Titanic`

**Estructura completa = Elemento HTML (o Nodo)**

#### Etiquetas Auto-Cerradas

Algunas etiquetas no necesitan etiquetas de cierre:
```html
<img src="image.jpg" />
<br />
<input type="text" />
```

### Etiquetas HTML Esenciales para Web Scraping

#### Etiquetas de Estructura del Documento

| Etiqueta | Propósito | Ejemplo |
|-----|---------|---------|
| `<head>` | Metadatos del documento | `<head><title>Page</title></head>` |
| `<body>` | Contenido principal | `<body>Content here</body>` |
| `<header>` | Contenido introductorio | `<header>Logo and nav</header>` |
| `<footer>` | Contenido del pie | `<footer>Copyright</footer>` |

#### Etiquetas de Contenido

| Etiqueta | Propósito | Ejemplo |
|-----|---------|---------|
| `<article>` | Bloque de contenido independiente | `<article>Blog post</article>` |
| `<p>` | Párrafo | `<p>Text paragraph</p>` |
| `<h1>` a `<h6>` | Encabezados (niveles 1-6) | `<h1>Main Title</h1>` |
| `<div>` | Contenedor genérico | `<div class="container">...</div>` |

#### Navegación y Listas

| Etiqueta | Propósito | Ejemplo |
|-----|---------|---------|
| `<nav>` | Sección de navegación | `<nav>Menu items</nav>` |
| `<ul>` | Lista sin orden | `<ul><li>Item</li></ul>` |
| `<ol>` | Lista ordenada | `<ol><li>First</li></ol>` |
| `<li>` | Elemento de lista | `<li>List item</li>` |
| `<a>` | Hipervínculo (ancla) | `<a href="url">Link</a>` |

#### Etiquetas de Tabla

| Etiqueta | Propósito | Ejemplo |
|-----|---------|---------|
| `<table>` | Contenedor de tabla | `<table>...</table>` |
| `<tr>` | Fila de tabla | `<tr><td>Data</td></tr>` |
| `<td>` | Celda de datos de tabla | `<td>Cell content</td>` |
| `<th>` | Celda de encabezado de tabla | `<th>Header</th>` |

#### Etiquetas Especiales

| Etiqueta | Propósito | Notas |
|-----|---------|-------|
| `<iframe>` | Página incrustada | Puede complicar el scraping |
| `<button>` | Botón clicable | Usado con formularios |
| `<form>` | Formulario de entrada | Contiene elementos de entrada |
| `<input>` | Campo de entrada de formulario | Varios tipos |

### Inspeccionar HTML en el Navegador

**Chrome/Edge/Firefox:**
1. Haz clic derecho en un elemento de la página
2. Selecciona "Inspeccionar" o "Inspeccionar Elemento"
3. Ve la estructura HTML en las Herramientas de Desarrollador

**Herramientas de Desarrollador:**
- Ver la estructura del árbol HTML
- Ver los estilos CSS
- Probar expresiones XPath
- Monitorear las peticiones de red

### Ejemplo de Estructura de Árbol HTML

```
<article class="main-article">
  └── <h1>Titanic</h1>
  └── <p class="plot">Plot description</p>
  └── <div class="full-script">
      └── Transcript text
  </div>
</article>
```

**Terminología del Árbol:**
- **Raíz (Root):** Elemento de nivel superior (`<article>`)
- **Padre (Parent):** Elemento que contiene a otros (`<article>` es padre de `<h1>`)
- **Hijos (Children):** Elementos dentro de otro (`<h1>` es hijo de `<article>`)
- **Hermanos (Siblings):** Elementos con el mismo padre (`<h1>`, `<p>`, `<div>` son hermanos)

---

## 22. XPath para la Selección de Elementos

### ¿Qué es XPath?

**XPath** (XML Path Language) es un lenguaje de consulta para seleccionar nodos de documentos XML/HTML. Esencial para el web scraping con Selenium y Scrapy.

### Sintaxis Básica de XPath

#### Seleccionar Elementos

```xpath
//h1                    Seleccionar todos los elementos h1
//p                     Seleccionar todos los elementos p
//div                   Seleccionar todos los elementos div
```

**Doble barra (`//`)** = Seleccionar en cualquier nivel del documento

#### Seleccionar por Posición

```xpath
//h1[1]                 Primer elemento h1
//h1[2]                 Segundo elemento h1
//p[last()]             Último elemento p
```

#### Seleccionar por Atributo

**Formato estándar:**
```xpath
//tag[@attribute="value"]
```

**Ejemplos:**
```xpath
//div[@class="container"]
//a[@href="https://example.com"]
//input[@id="username"]
//p[@class="plot"]
```

### Funciones de XPath

#### Función contains()

Encontrar elementos que contienen un texto específico en los atributos:

```xpath
//div[contains(@class, "plot")]
//a[contains(@href, "http")]
//p[contains(text(), "description")]
```

**Sintaxis:**
```xpath
//tag[contains(@attribute, "value")]
```

#### Función starts-with()

Encontrar elementos cuyo atributo empieza con un texto específico:

```xpath
//div[starts-with(@class, "main")]
//a[starts-with(@href, "https")]
```

#### Función text()

Obtener el contenido de texto de los elementos:

```xpath
//h1/text()              Obtener el texto dentro de h1
//p/text()               Obtener el texto dentro de p
```

### Operadores de XPath

#### AND Lógico

```xpath
//div[@class="container" and @id="main"]
//p[@class="plot" and contains(text(), "movie")]
```

#### OR Lógico

```xpath
//p[@class="plot" or @class="plot2"]
//div[@id="content" or @class="content"]
```

**Importante:** Usa paréntesis para expresiones complejas:
```xpath
//(p[@class="plot"] or p[@class="plot2"])
```

### Caracteres Especiales de XPath

#### Barra Simple (/)

Selecciona **hijos inmediatos**:

```xpath
/article/h1             h1 que es hijo directo de article
/article/div/p          p dentro de div dentro de article
```

#### Doble Barra (//)

Selecciona elementos en **cualquier nivel**:

```xpath
//article                Todos los elementos article en cualquier lugar
//article//h1            Todos los descendientes h1 de article
```

#### Punto (.)

Se refiere al **nodo actual**:

```xpath
.                       Nodo actual
.//p                    Todos los descendientes p del nodo actual
```

#### Doble Punto (..)

Se refiere al **nodo padre**:

```xpath
//h1/..                 Padre del elemento h1
//div[@class="plot"]/.. Padre del div específico
```

#### Asterisco (*)

**Comodín** - coincide con cualquier elemento:

```xpath
//*                     Todos los elementos
//article/*             Todos los hijos de article
//*[@class="title"]     Cualquier elemento con class="title"
```

#### Arroba (@)

Selecciona **atributos**:

```xpath
//@href                 Todos los atributos href
//a/@href               Atributos href de las etiquetas a
//@class                Todos los atributos class
```

### Ejemplos Prácticos de XPath

#### Ejemplo 1: Navegar Hacia Abajo en el Árbol

```xpath
//article              Elemento article raíz
//article/h1           Título (hijo inmediato)
//article/p            Párrafos (hijos inmediatos)
//article//text()      Todo el texto dentro de article
```

#### Ejemplo 2: Selección Compleja

```xpath
//div[@class="card"]//h2[@class="title"]/text()
```

**Desglose:**
- `//div[@class="card"]` - Encontrar todos los div con class="card"
- `//h2[@class="title"]` - Luego encontrar h2 con class="title" en cualquier nivel
- `/text()` - Obtener el contenido de texto

#### Ejemplo 3: Usando contains()

```xpath
//div[contains(@class, "article")]
//a[contains(@href, "wikipedia")]
//p[contains(text(), "description")]
```

### Probar XPath en el Navegador

**Chrome DevTools:**
1. Inspecciona el elemento (F12)
2. Presiona `Ctrl+F` en la pestaña Elements
3. Escribe la expresión XPath
4. Ve los elementos coincidentes resaltados

**Consola:**
```javascript
$x("//h1")              Devuelve un array de elementos coincidentes
$x("//div[@class='container']")
```

### XPath vs Selectores CSS

| Característica | XPath | Selector CSS |
|---------|-------|--------------|
| Sintaxis | Más verbosa | Más concisa |
| Selección de padre | ✅ Soportada | ❌ Limitada |
| Contenido de texto | ✅ Fácil | ❌ Difícil |
| Selección de atributo | ✅ Flexible | ✅ Buena |
| Rendimiento | Más lento | Más rápido |
| Legibilidad | Menos legible | Más legible |

**Recomendación:** Usa XPath por flexibilidad, CSS por rendimiento.

---

## 23. Automatización Web con Selenium

### ¿Qué es Selenium?

Selenium es una herramienta potente para automatizar navegadores web. Perfecta para:
- Web scraping de contenido dinámico
- Pruebas automatizadas
- Envío de formularios
- Tareas de automatización web

### Instalación

```bash
pip install selenium
```

Desde Selenium 4.6, **Selenium Manager** (incluido con la librería) descarga y gestiona automáticamente el driver correcto para tu navegador instalado — sin necesidad de descargar ChromeDriver manualmente ni configurar el `PATH`.

### Configuración Básica de Selenium

```python
from selenium import webdriver

# Crear el driver (Selenium Manager resuelve el driver automáticamente)
driver = webdriver.Chrome()

# Abrir un sitio web
driver.get("https://www.example.com")
```

**Opcional: modo headless (para servidores/CI):**
```python
options = webdriver.ChromeOptions()
options.add_argument("--headless=new")
driver = webdriver.Chrome(options=options)
```

### Localizar Elementos

#### Por XPath (Recomendado)

```python
from selenium.webdriver.common.by import By

# Encontrar un solo elemento
element = driver.find_element(By.XPATH, "//h1[@class='title']")

# Encontrar varios elementos
elements = driver.find_elements(By.XPATH, "//div[@class='card']")
```

**Diferencia Clave:**
- `find_element()` - Devuelve un solo elemento (primera coincidencia)
- `find_elements()` - Devuelve una lista de todos los elementos coincidentes

#### Otros Métodos de Localización

```python
# Por ID
driver.find_element(By.ID, "username")

# Por Class Name
driver.find_element(By.CLASS_NAME, "btn-primary")

# Por Tag Name
driver.find_element(By.TAG_NAME, "h1")

# Por Selector CSS
driver.find_element(By.CSS_SELECTOR, "div.container > h1")

# Por Link Text
driver.find_element(By.LINK_TEXT, "Click Here")

# Por Partial Link Text
driver.find_element(By.PARTIAL_LINK_TEXT, "Click")
```

### Extraer Datos

#### Obtener el Contenido de Texto

```python
# Obtener el texto de un elemento
element = driver.find_element(By.XPATH, "//h1")
title = element.text

print(title)  # Imprime el contenido de texto
```

#### Obtener Valores de Atributos

```python
# Obtener el atributo href
link = driver.find_element(By.XPATH, "//a[@class='news-link']")
url = link.get_attribute("href")

# Obtener el atributo class
element = driver.find_element(By.XPATH, "//div")
class_name = element.get_attribute("class")

# Obtener cualquier atributo
value = element.get_attribute("data-value")
```

### Trabajar con Múltiples Elementos

```python
# Encontrar todas las tarjetas
containers = driver.find_elements(By.XPATH, "//div[@class='news-card']")

# Iterar por los elementos
for container in containers:
    # Usar punto (.) para XPath relativo dentro del contenedor
    title = container.find_element(By.XPATH, ".//h2").text
    subtitle = container.find_element(By.XPATH, ".//p").text
    link = container.find_element(By.XPATH, ".//a").get_attribute("href")

    print(f"Title: {title}")
    print(f"Subtitle: {subtitle}")
    print(f"Link: {link}")
    print("---")
```

**Notación de Punto (`.//`):**
- Busca **dentro del elemento actual**
- Más eficiente que el XPath completo
- Evita seleccionar elementos incorrectos

### Control del Navegador

```python
# Maximizar la ventana
driver.maximize_window()

# Navegar
driver.get("https://www.example.com")

# Ir atrás
driver.back()

# Ir adelante
driver.forward()

# Recargar la página
driver.refresh()

# Cerrar la pestaña actual
driver.close()

# Salir del navegador (todas las pestañas)
driver.quit()
```

### Esperar por Elementos

```python
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.common.by import By

# Espera explícita (hasta 10 segundos)
element = WebDriverWait(driver, 10).until(
    EC.presence_of_element_located((By.XPATH, "//h1"))
)

# Condiciones esperadas comunes
EC.presence_of_element_located()    # El elemento existe en el DOM
EC.visibility_of_element_located()  # El elemento es visible
EC.element_to_be_clickable()        # El elemento es clicable
EC.title_contains("text")           # El título de la página contiene el texto
```

---

## 24. Construyendo un Proyecto de Web Scraping

### Proyecto: Agregador de Noticias

**Objetivo:** Extraer títulos, subtítulos y enlaces de noticias de un sitio web automáticamente.

### Paso 1: Inspeccionar el Sitio Web

1. Abre el sitio web en el navegador
2. Haz clic derecho → Inspeccionar
3. Identifica la estructura HTML
4. Encuentra patrones comunes en los elementos

### Paso 2: Construir Expresiones XPath

```python
# Encontrar todos los contenedores de noticias
containers_xpath = "//div[@class='news-card-container']"

# Dentro de cada contenedor, encontrar:
title_xpath = ".//a/h2"
subtitle_xpath = ".//a/p"
link_xpath = ".//a"
```

**Probar XPath en DevTools:**
- Presiona `Ctrl+F` en la pestaña Elements
- Pega el XPath
- Verifica que se resalten los elementos correctos

### Paso 3: Script de Scraping Completo

```python
from selenium import webdriver
from selenium.webdriver.common.by import By

# Configuración
website = "https://www.thefootballmind.com/ramble/articles"

driver = webdriver.Chrome()
driver.get(website)

# Crear listas vacías
titles = []
subtitles = []
links = []

# Encontrar todos los contenedores
containers = driver.find_elements(
    By.XPATH,
    "//div[@class='row feature-post-row']"
)

# Extraer los datos de cada contenedor
for container in containers:
    # Título
    title = container.find_element(By.XPATH, ".//a/h2").text
    titles.append(title)

    # Subtítulo
    subtitle = container.find_element(By.XPATH, ".//a/p").text
    subtitles.append(subtitle)

    # Enlace
    link = container.find_element(By.XPATH, ".//a").get_attribute("href")
    links.append(link)

# Cerrar el navegador
driver.quit()

# Mostrar los resultados
for i in range(len(titles)):
    print(f"Title: {titles[i]}")
    print(f"Subtitle: {subtitles[i]}")
    print(f"Link: {links[i]}")
    print("---")
```

### Problemas Comunes y Soluciones

**Problema 1: Elemento no encontrado**
```python
# Solución: Añadir un tiempo de espera
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

wait = WebDriverWait(driver, 10)
element = wait.until(
    EC.presence_of_element_located((By.XPATH, "//h1"))
)
```

**Problema 2: StaleElementReferenceException**
```python
# Solución: Volver a encontrar el elemento
try:
    element.click()
except StaleElementReferenceException:
    element = driver.find_element(By.XPATH, xpath)
    element.click()
```

**Problema 3: XPath devuelve elementos incorrectos**
```python
# Solución: Usar un XPath más específico
# Mal: //div
# Bien: //div[@class='specific-class']
```

---

## 25. Exportar Datos a CSV

### Usando Pandas para Exportar

Después de hacer scraping de los datos, expórtalos a CSV para su análisis:

```python
import pandas as pd

# Crear un DataFrame a partir de las listas
df = pd.DataFrame({
    'title': titles,
    'subtitle': subtitles,
    'link': links
})

# Exportar a CSV
df.to_csv('news_data.csv', index=False)

# Mostrar el DataFrame
print(df.head())
```

### Ejemplo Completo de Scraping + Exportación

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
import pandas as pd

# Configuración
website = "https://www.thefootballmind.com/ramble/articles"

driver = webdriver.Chrome()
driver.get(website)

# Crear listas vacías
titles = []
subtitles = []
links = []

# Encontrar y extraer los datos
containers = driver.find_elements(
    By.XPATH,
    "//div[@class='row feature-post-row']"
)

for container in containers:
    title = container.find_element(By.XPATH, ".//a/h2").text
    subtitle = container.find_element(By.XPATH, ".//a/p").text
    link = container.find_element(By.XPATH, ".//a").get_attribute("href")

    titles.append(title)
    subtitles.append(subtitle)
    links.append(link)

driver.quit()

# Crear el DataFrame
df = pd.DataFrame({
    'title': titles,
    'subtitle': subtitles,
    'link': links
})

# Exportar a CSV
df.to_csv('football_news.csv', index=False)

print(f"Scraped {len(df)} articles successfully!")
print(df.head())
```

### Opciones de Exportación a CSV

```python
# Sin la columna de índice
df.to_csv('data.csv', index=False)

# Con una codificación específica
df.to_csv('data.csv', encoding='utf-8', index=False)

# Separador distinto
df.to_csv('data.tsv', sep='\t', index=False)

# Solo columnas específicas
df[['title', 'link']].to_csv('minimal.csv', index=False)
```

---

## 26. Resumen de Automatización con Python

### Lo Que Has Aprendido

#### Técnicas de Web Scraping

1. **Pandas para Extracción Simple**
   - Extraer tablas de HTML
   - Leer CSV desde URLs
   - Recolección rápida de datos

2. **Camelot para Tablas de PDF**
   - Extraer tablas de PDFs
   - Exportar a varios formatos
   - Manejar distintos métodos de análisis

3. **Selenium para Contenido Dinámico**
   - Automatizar interacciones del navegador
   - Manejar páginas renderizadas con JavaScript
   - Extraer datos de sitios complejos

#### Habilidades Esenciales

**Comprensión de HTML:**
- ✅ Etiquetas y estructura HTML
- ✅ Atributos y valores
- ✅ Jerarquía del árbol del documento

**Dominio de XPath:**
- ✅ Sintaxis básica de selección
- ✅ Selección basada en atributos
- ✅ Funciones (contains, starts-with)
- ✅ Operadores lógicos
- ✅ Navegación padre/hijo

**Automatización con Selenium:**
- ✅ Configuración del driver
- ✅ Estrategias de localización de elementos
- ✅ Métodos de extracción de datos
- ✅ Manejo de múltiples elementos

### Casos de Uso de Automatización

**Recolección de Datos:**
- Agregación de noticias
- Monitoreo de precios
- Analítica de redes sociales
- Recopilación de datos de investigación

**Inteligencia de Negocios:**
- Análisis de competidores
- Investigación de mercado
- Seguimiento de tendencias
- Generación de informes

**Productividad Personal:**
- Descargas automatizadas
- Monitoreo web
- Backup de datos
- Archivado de contenido

### Buenas Prácticas

**Legal y Ético:**
- ⚠️ Comprueba el robots.txt del sitio web
- ⚠️ Respeta los Términos de Servicio
- ⚠️ No sobrecargues los servidores (rate limiting)
- ⚠️ Da la atribución adecuada

**Técnico:**
- ✅ Maneja los errores con elegancia
- ✅ Usa tiempos de espera apropiados
- ✅ Cierra las sesiones del navegador
- ✅ Valida los datos extraídos
- ✅ Registra las actividades de scraping

**Eficiencia:**
- ✅ Cachea los resultados cuando sea posible
- ✅ Usa operaciones por lotes
- ✅ Minimiza los reinicios del navegador
- ✅ Optimiza las expresiones XPath

### Siguientes Pasos en la Automatización

1. **Selenium Avanzado:**
   - Manejo de formularios y autenticación
   - Trabajar con iframes
   - Ejecución de JavaScript
   - Captura de pantallas

2. **Framework Scrapy:**
   - Scraping a gran escala
   - Pipelines de datos integrados
   - Scraping distribuido

3. **Integración de APIs:**
   - APIs REST con la librería requests
   - Manejo de autenticación
   - Rate limiting
   - Validación de datos

4. **Automatización de Tareas:**
   - Operaciones con archivos
   - Automatización de correo
   - Generación de informes
   - Tareas programadas con cron

---

## Resumen: Camino de Aprendizaje de Python

### Etapa 1: Fundamentos (Completada)
✅ Conceptos de resolución de problemas
✅ Diseño de algoritmos
✅ Escritura de pseudocódigo
✅ Fundamentos de Python (print, tipos de datos, casting)

### Etapa 2: Programación en Python (Siguiente)
- Variables y operadores
- Flujo de control (if/else, bucles)
- Funciones y módulos
- Estructuras de datos (listas, diccionarios, sets)
- E/S de archivos

### Etapa 3: Ciencia de Datos (Futuro)
- Arrays y operaciones de NumPy
- DataFrames de Pandas
- Limpieza y preprocesamiento de datos
- Visualización de datos
- Proyectos del mundo real

---

**Última Actualización:** 2026-08-31
**Versión de Python:** 3.13.x (cubriendo funcionalidades hasta Python 3.13)

**Temas Cubiertos:**
- Fundamentos de Python (tipos de datos, funciones, flujo de control)
- Funcionalidades Modernas de Python (pattern matching 3.10+, tipos unión, grupos de excepciones, mejoras de f-string)
- Resolución de Problemas y Algoritmos (búsqueda, ordenamiento, pseudocódigo)
- Web Scraping (Pandas, Selenium, XPath, HTML)
- Automatización (extracción de PDF, manejo de CSV, exportación de datos)
- Introducción a la Ciencia de Datos (adelanto de NumPy, Pandas, Matplotlib)

**Estado:** Base completa de Python desde principiante hasta automatización y ciencia de datos, incluyendo las funcionalidades modernas de Python 3.10-3.13

**Notas de Compatibilidad:**
- El contenido central funciona con Python 3.7+
- La sección de funcionalidades modernas requiere Python 3.10+ (pattern matching, tipos unión)
- Los grupos de excepciones requieren Python 3.11+
- La sintaxis de parámetros de tipo y las mejoras de f-string requieren Python 3.12+
- Las funcionalidades de free-threading y JIT son experimentales en Python 3.13+
