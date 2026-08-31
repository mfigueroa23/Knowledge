# Tailwind CSS - De Cero a Experto

## 📊 Metadatos del Documento

**Versión de Tailwind CSS:** v4.0
**Última Actualización:** 2026-08-31
**Requisitos Previos:** Conocimientos básicos de HTML, CSS y JavaScript
**Nivel de Habilidad:** Principiante a Avanzado

---

## 🎯 Cuándo Usar Este Conocimiento

**Esta guía es perfecta para:**
- Iniciar nuevos proyectos con Tailwind CSS v4.0
- Migrar de v3.x a v4.0
- Aprender la metodología de CSS utility-first
- Construir aplicaciones listas para producción
- Entender las buenas prácticas de Tailwind en 2025+

**Deberías consultarla cuando:**
- Configures Tailwind en proyectos de React, Vue, Angular o vanilla
- Configures temas personalizados y sistemas de diseño
- Optimices builds de producción
- Implementes diseños responsive con funcionalidades modernas de CSS
- Decidas entre @apply y la extracción de componentes

**Nota:** Este documento cubre Tailwind CSS v4.0, que trae cambios significativos respecto a v3.x, incluyendo configuración simplificada, builds más rápidos y funcionalidades modernas de CSS. Si usas v3.x, algunas instrucciones de configuración pueden diferir.

---

## 📋 Tabla de Contenidos

1. [Introducción a Tailwind CSS](#1-introducción-a-tailwind-css)
2. [¿Qué es Tailwind CSS?](#2-qué-es-tailwind-css)
3. [Concepto Utility-First](#3-concepto-utility-first)
4. [Instalación y Configuración](#4-instalación-y-configuración)
5. [Extensiones y Herramientas de VSCode](#5-extensiones-y-herramientas-de-vscode)
6. [Clases de Utilidad Básicas](#6-clases-de-utilidad-básicas)
7. [Diseño Responsive](#7-diseño-responsive)
8. [Variantes y Estados](#8-variantes-y-estados)
9. [Colores y Personalización](#9-colores-y-personalización)
10. [Utilidades de Layout](#10-utilidades-de-layout)
11. [Tipografía y Utilidades de Texto](#11-tipografía-y-utilidades-de-texto)
12. [Espaciado y Dimensionado](#12-espaciado-y-dimensionado)
13. [Flexbox y Grid](#13-flexbox-y-grid)
14. [Fondos y Gradientes](#14-fondos-y-gradientes)
15. [Bordes y Efectos](#15-bordes-y-efectos)
16. [Funcionalidades Avanzadas](#16-funcionalidades-avanzadas)
17. [Proyecto Práctico: Links in Bio](#17-proyecto-práctico-links-in-bio)
18. [Rendimiento y Optimización](#18-rendimiento-y-optimización)
19. [Nuevas Funcionalidades de Tailwind CSS 4](#19-nuevas-funcionalidades-de-tailwind-css-4)
20. [Buenas Prácticas](#20-buenas-prácticas)
21. [Buenas Prácticas de Tailwind en Profundidad](#21-buenas-prácticas-de-tailwind-en-profundidad)
22. [Ordenamiento de Clases y Sistema de Prioridad](#22-ordenamiento-de-clases-y-sistema-de-prioridad)
23. [Configuración de Proyecto Vite + React](#23-configuración-de-proyecto-vite--react)
24. [Extensión de Tema Personalizado (Práctico)](#24-extensión-de-tema-personalizado-práctico)
25. [Variantes para Estilos Dinámicos (Avanzado)](#25-variantes-para-estilos-dinámicos-avanzado)
26. [La Directiva @apply - Cuándo Sí y Cuándo No](#26-la-directiva-apply---cuándo-sí-y-cuándo-no)
27. [Técnicas de Edición Multi-Cursor](#27-técnicas-de-edición-multi-cursor)
28. [Proyecto Práctico: Cuadrícula de Videojuegos](#28-proyecto-práctico-cuadrícula-de-videojuegos)
29. [Estrategias de Extracción de Componentes](#29-estrategias-de-extracción-de-componentes)
30. [Hoja de Referencia y Recursos de Tailwind](#30-hoja-de-referencia-y-recursos-de-tailwind)
31. [Herramientas de IA para el Desarrollo con Tailwind](#31-herramientas-de-ia-para-el-desarrollo-con-tailwind)

---

## Descripción General

Tailwind CSS es un framework de CSS utility-first que proporciona clases de utilidad de bajo nivel para construir diseños personalizados directamente en tu HTML. A diferencia de los frameworks de CSS tradicionales como Bootstrap, Tailwind no proporciona componentes prefabricados, sino que te da los bloques de construcción para crear tus propios diseños únicos.

### ¿Qué es Tailwind CSS?

- **Framework de CSS utility-first** para el desarrollo rápido de UI
- Creado por Adam Wathan y Steve Schoger
- Proporciona clases de utilidad de bajo nivel en lugar de componentes prefabricados
- Altamente personalizable a través de la configuración
- **Versión 4.0** lanzada el 22 de enero de 2025 con mejoras importantes
- Construido sobre funcionalidades modernas de CSS (cascade layers, @property, color-mix)
- Impulsado por Lightning CSS (basado en Rust) para un rendimiento extremo
- Configuración cero en la mayoría de los casos

### Características Principales (v4.0)

- ✅ **Builds ultrarrápidos** - Builds completos 5x más rápidos, incrementales 100x+ más rápidos
- ✅ **Configuración simplificada** - Un solo import de CSS, cero configuración requerida
- ✅ **Base de CSS moderna** - Cascade layers nativas, container queries, color-mix
- ✅ **Configuración basada en CSS** - Define el tema en CSS usando la directiva @theme
- ✅ **Enfoque utility-first** - Máxima flexibilidad y consistencia
- ✅ **Diseño responsive** - Breakpoints mobile-first integrados
- ✅ **Modo oscuro** - Soporte de preferencia del sistema o toggle manual
- ✅ **Builds de producción diminutos** - Tree-shaking automático de los estilos sin usar
- ✅ **Amplio gamut de color** - Soporte de P3, Rec2020, oklch
- ✅ **Amigable con componentes** - Funciona con React, Vue, Angular, Svelte, etc.

### Conceptos Fundamentales

**Filosofía de Diseño:**
- Componer componentes complejos a partir de clases de utilidad
- Diseñar directamente en HTML/JSX
- Sin cambio de contexto entre HTML y CSS
- Sistema de diseño basado en restricciones
- Enfoque responsive mobile-first

**Patrón de Arquitectura:**
- Clases de utilidad de bajo nivel
- Tokens de diseño configurables
- Generación de CSS en tiempo de build
- Tree-shaking de estilos sin usar
- Sobrecarga mínima en runtime

---

## 1. Introducción a Tailwind CSS

### ¿Qué Hace a Tailwind Diferente?

Tailwind CSS representa un cambio de paradigma en cómo escribimos CSS. En lugar de crear nombres de clase personalizados y escribir CSS por separado, compones los estilos usando clases de utilidad preexistentes directamente en tu marcado.

**Enfoque de CSS Tradicional:**
```css
/* styles.css */
.card {
  background-color: white;
  border-radius: 0.5rem;
  padding: 1rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.card-title {
  font-size: 1.25rem;
  font-weight: 700;
  color: #333;
}
```

```html
<div class="card">
  <h2 class="card-title">Title</h2>
</div>
```

**Enfoque de Tailwind:**
```html
<div class="bg-white rounded-lg p-4 shadow-md">
  <h2 class="text-xl font-bold text-gray-800">Title</h2>
</div>
```

### Ventajas Clave

**1. Sin Fatiga de Nombrado:**
- No hay que inventar nombres de clase como `.card-wrapper`, `.content-container`, etc.
- Enfócate en el diseño, no en las convenciones de nombrado

**2. Sistema de Diseño Consistente:**
- Espaciado, colores y tamaños predefinidos
- Mantén la consistencia en todo tu proyecto
- Fácil crear tokens de diseño

**3. Desarrollo Más Rápido:**
- Escribe estilos sin salir de tu HTML
- Prototipado rápido
- Ve los cambios inmediatamente

**4. Bundle de CSS Más Pequeño:**
- Solo incluye las utilidades que usas
- PurgeCSS elimina los estilos sin usar en producción
- Normalmente resulta en <10KB de CSS en producción

**5. Responsive por Defecto:**
- Enfoque mobile-first
- Modificadores responsive simples
- Sistema de breakpoints consistente

---

## 2. ¿Qué es Tailwind CSS?

### Framework Utility-First

Tailwind CSS es fundamentalmente diferente de los frameworks de CSS tradicionales como Bootstrap, Foundation o Bulma. Mientras que esos frameworks proporcionan componentes prefabricados (botones, tarjetas, navbars), Tailwind proporciona clases de utilidad de bajo nivel que te permiten construir diseños completamente personalizados.

**Comparación con Otros Frameworks:**

| Característica | Bootstrap | Tailwind CSS |
|---------|-----------|--------------|
| **Enfoque** | Basado en componentes | Utility-first |
| **Personalización** | Sobrescribir con CSS personalizado | Componer utilidades |
| **Diseño** | Opinado (aspecto Bootstrap) | Sin opinión (tu diseño) |
| **Tamaño de Bundle** | ~150KB (minificado) | ~10KB (purgado) |
| **Curva de Aprendizaje** | Componentes primero | Utilidades primero |
| **Flexibilidad** | Limitada por los componentes | Muy flexible |

### Filosofía

Tailwind sigue tres principios fundamentales:

**1. Diseño basado en restricciones:**
- Conjunto limitado de valores de espaciado (0.25rem, 0.5rem, 1rem, etc.)
- Paleta de colores predefinida
- Tamaños de fuente estándar
- Fomenta la consistencia

**2. Composición sobre herencia:**
- Construir componentes complejos a partir de utilidades simples
- Sin estilos en cascada
- Estilizado explícito

**3. Utility-first, componente-después:**
- Empieza con utilidades
- Extrae componentes cuando veas repetición
- Los patrones reutilizables emergen de forma natural

### El Flujo de Trabajo de Tailwind

```
1. Escribe HTML con clases de utilidad
   ↓
2. Ves patrones repetidos
   ↓
3. Extrae componentes (React, Vue, etc.)
   ↓
4. Mantén las clases de utilidad para casos únicos
```

---

## 3. Concepto Utility-First

### Entendiendo las Clases de Utilidad

Una clase de utilidad hace una cosa y la hace bien. Cada clase se mapea a una única propiedad CSS o a un conjunto pequeño y enfocado de propiedades.

**Ejemplos:**

```html
<!-- Color de texto -->
<p class="text-blue-500">Blue text</p>

<!-- Padding -->
<div class="p-4">Padding on all sides</div>

<!-- Display flex -->
<div class="flex">Flexbox container</div>

<!-- Combinar varias utilidades -->
<button class="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600">
  Click me
</button>
```

### Convención de Nombrado de Clases de Utilidad

Tailwind usa un patrón de nombrado consistente:

```
{property}-{value}
{property}{side}-{value}
{property}-{color}-{shade}
```

**Ejemplos:**

- `p-4` → padding: 1rem (todos los lados)
- `px-4` → padding-left + padding-right: 1rem
- `pt-4` → padding-top: 1rem
- `text-blue-500` → color: #3b82f6
- `bg-red-100` → background-color: #fee2e2

### Patrones Comunes de Utilidad

**Espaciado:**
```html
<!-- Margin -->
<div class="m-4">margin: 1rem</div>
<div class="mx-4">margin-left y margin-right: 1rem</div>
<div class="my-4">margin-top y margin-bottom: 1rem</div>
<div class="mt-4">margin-top: 1rem</div>

<!-- Padding -->
<div class="p-4">padding: 1rem</div>
<div class="px-4">padding-left y padding-right: 1rem</div>
<div class="py-4">padding-top y padding-bottom: 1rem</div>
<div class="pt-4">padding-top: 1rem</div>
```

**Tipografía:**
```html
<!-- Tamaño de fuente -->
<p class="text-xs">Extra small text</p>
<p class="text-sm">Small text</p>
<p class="text-base">Base text</p>
<p class="text-lg">Large text</p>
<p class="text-xl">Extra large text</p>
<p class="text-2xl">2X large text</p>

<!-- Peso de la fuente -->
<p class="font-thin">Thin</p>
<p class="font-normal">Normal</p>
<p class="font-bold">Bold</p>

<!-- Alineación del texto -->
<p class="text-left">Left aligned</p>
<p class="text-center">Center aligned</p>
<p class="text-right">Right aligned</p>
```

**Colores:**
```html
<!-- Colores de texto -->
<p class="text-gray-500">Gray text</p>
<p class="text-blue-600">Blue text</p>
<p class="text-red-500">Red text</p>

<!-- Colores de fondo -->
<div class="bg-white">White background</div>
<div class="bg-gray-100">Light gray background</div>
<div class="bg-blue-500">Blue background</div>

<!-- Colores de borde -->
<div class="border border-gray-300">Gray border</div>
```

### Beneficios de Utility-First

**1. Consistencia:**
```html
<!-- Todos los botones usan la misma escala de espaciado -->
<button class="px-4 py-2">Button 1</button>
<button class="px-6 py-3">Button 2</button>
<!-- vs valores aleatorios en CSS -->
```

**2. Mantenibilidad:**
```html
<!-- Fácil ver qué estilos se aplican -->
<div class="flex items-center justify-between p-4 bg-white shadow-md">
  <!-- Contenido -->
</div>
```

**3. Sin hinchazón de CSS:**
- Reutiliza las mismas clases en todas partes
- Sin CSS duplicado
- Menor tamaño de bundle

---

## 4. Instalación y Configuración

### Método 1: CDN (Solo Desarrollo)

La forma más rápida de probar Tailwind CSS es usando el CDN. **Nota: Esto es solo para desarrollo/aprendizaje, no para producción.**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tailwind CSS CDN</title>

  <!-- Tailwind CSS 4 CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body>
  <div class="min-h-screen bg-gray-100 flex items-center justify-center">
    <div class="bg-white p-8 rounded-lg shadow-md">
      <h1 class="text-3xl font-bold text-gray-800 mb-4">
        Hello Tailwind!
      </h1>
      <p class="text-gray-600">
        This is using the CDN version.
      </p>
    </div>
  </div>
</body>
</html>
```

**Configuración del CDN:**
```html
<script src="https://cdn.tailwindcss.com"></script>
<script>
  tailwind.config = {
    theme: {
      extend: {
        colors: {
          'custom-blue': '#1e40af',
        }
      }
    }
  }
</script>
```

**Limitaciones del CDN:**
- ❌ Tamaño de archivo mayor (no optimizado)
- ❌ Sin tree-shaking
- ❌ Personalización limitada
- ❌ No apto para producción
- ✅ Genial para aprender y prototipar

### Método 2: Herramientas de Build (Recomendado para Producción - v4)

**Tailwind v4.0** simplifica la configuración significativamente. Este es el enfoque moderno:

**Paso 1: Inicializar el Proyecto**
```bash
# Crear el directorio del proyecto
mkdir my-tailwind-project
cd my-tailwind-project

# Inicializar npm
npm init -y
```

**Paso 2: Instalar Tailwind CSS v4**
```bash
# Instalar Tailwind v4. La CLI standalone se movió a su propio paquete en v4:
npm install -D tailwindcss@latest @tailwindcss/cli

# ¡No se necesita postcss.config.js en muchos casos!
# ¡No se necesita tailwind.config.js para el uso básico!
```

**Paso 3: Crear el Archivo CSS (Simplificado en v4)**

`src/styles.css`:
```css
/* v4: ¡Una sola línea de import! */
@import "tailwindcss";

/* Opcional: Configuración de tema personalizado en CSS */
@theme {
  --color-primary: #3b82f6;
  --color-secondary: #8b5cf6;
  --font-display: "Inter", sans-serif;
  --breakpoint-2xl: 1400px;
}
```

**Alternativa: Sintaxis Tradicional de v3 (Aún Soportada)**

`src/input.css`:
```css
/* la sintaxis de v3 aún funciona en v4 */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

**Paso 4: Configurar las Rutas de Contenido (Opcional)**

Para rutas personalizadas, crea `tailwind.config.js`:
```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./src/**/*.{html,js,jsx,ts,tsx}",
    "./public/**/*.html"
  ],
}
```

**Nota:** ¡v4 detecta automáticamente los patrones de archivo comunes, por lo que la configuración a menudo es innecesaria!

**Paso 5: Proceso de Build**

Añade a `package.json`:
```json
{
  "scripts": {
    "dev": "npx @tailwindcss/cli -i ./src/styles.css -o ./dist/output.css --watch",
    "build": "npx @tailwindcss/cli -i ./src/styles.css -o ./dist/output.css --minify"
  }
}
```

**Paso 6: Ejecutar el Servidor de Desarrollo**
```bash
# Observar los cambios
npm run dev

# Build para producción
npm run build
```

**Paso 7: Usar en HTML**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tailwind Project</title>
  <link href="/dist/output.css" rel="stylesheet">
</head>
<body>
  <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>
</body>
</html>
```

### Método 3: Con Herramientas de Build (Vite, Webpack, etc.)

**Configuración de Vite (v4 - recomendado, usa el plugin de Vite de primera parte):**
```bash
# Crear el proyecto Vite
npm create vite@latest my-project -- --template vanilla

# Instalar Tailwind v4 y su plugin de Vite
npm install -D tailwindcss@latest @tailwindcss/vite
```

**Añade el plugin a `vite.config.js`:**
```javascript
import { defineConfig } from 'vite'
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  plugins: [tailwindcss()],
})
```

**Crear el archivo CSS:**
```css
/* src/style.css */
@import "tailwindcss";
```

**Importar en tu JS principal:**
```javascript
// src/main.js
import './style.css'
```

> En v4, el plugin de Vite reemplaza la configuración de PostCSS. Si debes usar PostCSS (p. ej. otros plugins), usa el paquete `@tailwindcss/postcss` en lugar de la antigua combinación de `tailwindcss` + `autoprefixer` — autoprefixer y `postcss-import` ya no son necesarios en v4.

**Configuración de Webpack:**
```bash
# Instalar dependencias
npm install -D tailwindcss postcss postcss-loader autoprefixer
```

`webpack.config.js`:
```javascript
module.exports = {
  module: {
    rules: [
      {
        test: /\.css$/,
        use: [
          'style-loader',
          'css-loader',
          'postcss-loader'
        ]
      }
    ]
  }
}
```

### Método 4: Integración con Frameworks

**React/Next.js:**
```bash
# Next.js incluye Tailwind automáticamente
npx create-next-app@latest my-app
# Selecciona "Yes" para Tailwind CSS durante la configuración
```

**Vue.js:**
```bash
# Instalar Tailwind en un proyecto Vue
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

**Angular:**
```bash
# Instalar Tailwind en un proyecto Angular
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init
```

---

## 5. Extensiones y Herramientas de VSCode

### Extensiones Esenciales

**1. Tailwind CSS IntelliSense**
- **ID de Extensión:** `bradlc.vscode-tailwindcss`
- **Funcionalidades:**
  - Autocompletado para los nombres de clase
  - Vistas previas al pasar el cursor mostrando el CSS
  - Linting y validación
  - Vistas previas de color
  - Resaltado de sintaxis

**Instalación:**
```bash
# Vía el marketplace de VSCode o la paleta de comandos
# Buscar: "Tailwind CSS IntelliSense"
```

**Beneficios:**
```html
<!-- Mientras escribes, obtienes sugerencias de autocompletado -->
<div class="bg-[presiona espacio para ver sugerencias]">

<!-- Pasa el cursor sobre las clases para ver el CSS real -->
<div class="flex items-center">
  <!-- Al pasar el cursor muestra: display: flex; align-items: center; -->
</div>
```

**2. PostCSS Language Support**
- **ID de Extensión:** `csstools.postcss`
- Resaltado de sintaxis para PostCSS
- Autocompletado para las directivas @tailwind

**3. Headwind**
- **ID de Extensión:** `heybourn.headwind`
- Ordena automáticamente las clases de Tailwind
- Mantiene un orden de clases consistente

**Ejemplo:**
```html
<!-- Antes de Headwind -->
<div class="text-white p-4 bg-blue-500 flex">

<!-- Después de Headwind -->
<div class="flex bg-blue-500 p-4 text-white">
```

**4. Tailwind Fold**
- **ID de Extensión:** `stivo.tailwind-fold`
- Colapsa las cadenas de clases largas
- Mejora la legibilidad

### Configuración de VSCode

Añade a `.vscode/settings.json`:
```json
{
  "tailwindCSS.experimental.classRegex": [
    ["class:\\s*?[\"'`]([^\"'`]*).*?[\"'`]", "[\"'`]([^\"'`]*).*?[\"'`]"]
  ],
  "editor.quickSuggestions": {
    "strings": true
  },
  "css.validate": false,
  "tailwindCSS.emmetCompletions": true,
  "files.associations": {
    "*.css": "tailwindcss"
  }
}
```

### DevTools del Navegador

**Tailwind DevTools (Extensión de Chrome):**
- Inspeccionar las clases de Tailwind
- Ver los valores calculados
- Depurar diseños responsive

**Instalación:**
```
1. Visita la Chrome Web Store
2. Busca "Tailwind CSS DevTools"
3. Añádelo a Chrome
```

---

## 6. Clases de Utilidad Básicas

### Utilidades de Display

```html
<!-- Block -->
<div class="block">Block element</div>

<!-- Inline Block -->
<div class="inline-block">Inline block</div>

<!-- Inline -->
<span class="inline">Inline element</span>

<!-- Flex -->
<div class="flex">Flexbox container</div>

<!-- Grid -->
<div class="grid">Grid container</div>

<!-- Hidden -->
<div class="hidden">Hidden element</div>

<!-- Inline Flex -->
<div class="inline-flex">Inline flex</div>
```

### Ancho y Alto

```html
<!-- Ancho fijo -->
<div class="w-32">width: 8rem (128px)</div>
<div class="w-64">width: 16rem (256px)</div>

<!-- Ancho en porcentaje -->
<div class="w-1/2">width: 50%</div>
<div class="w-1/3">width: 33.333333%</div>
<div class="w-full">width: 100%</div>

<!-- Ancho de pantalla -->
<div class="w-screen">width: 100vw</div>

<!-- Ancho Min/Max -->
<div class="min-w-0">min-width: 0</div>
<div class="max-w-md">max-width: 28rem</div>

<!-- Alto -->
<div class="h-32">height: 8rem</div>
<div class="h-full">height: 100%</div>
<div class="h-screen">height: 100vh</div>

<!-- Alto Min/Max -->
<div class="min-h-screen">min-height: 100vh</div>
<div class="max-h-64">max-height: 16rem</div>
```

### Margin y Padding

```html
<!-- Margin en todos los lados -->
<div class="m-4">margin: 1rem</div>
<div class="m-8">margin: 2rem</div>

<!-- Margin horizontal/vertical -->
<div class="mx-4">margin-left y margin-right: 1rem</div>
<div class="my-4">margin-top y margin-bottom: 1rem</div>

<!-- Margin en lados individuales -->
<div class="mt-4">margin-top: 1rem</div>
<div class="mr-4">margin-right: 1rem</div>
<div class="mb-4">margin-bottom: 1rem</div>
<div class="ml-4">margin-left: 1rem</div>

<!-- Margin negativo -->
<div class="-mt-4">margin-top: -1rem</div>
<div class="-mx-2">margin-left y margin-right: -0.5rem</div>

<!-- Padding -->
<div class="p-4">padding: 1rem</div>
<div class="px-4">padding-left y padding-right: 1rem</div>
<div class="py-4">padding-top y padding-bottom: 1rem</div>
<div class="pt-4">padding-top: 1rem</div>

<!-- Espacio entre los hijos -->
<div class="space-x-4">
  <!-- gap para el espaciado horizontal -->
  <div>Item 1</div>
  <div>Item 2</div>
</div>

<div class="space-y-4">
  <!-- gap para el espaciado vertical -->
  <div>Item 1</div>
  <div>Item 2</div>
</div>
```

### Utilidades de Texto

```html
<!-- Tamaño de fuente -->
<p class="text-xs">Extra small (0.75rem)</p>
<p class="text-sm">Small (0.875rem)</p>
<p class="text-base">Base (1rem)</p>
<p class="text-lg">Large (1.125rem)</p>
<p class="text-xl">Extra large (1.25rem)</p>
<p class="text-2xl">2XL (1.5rem)</p>
<p class="text-3xl">3XL (1.875rem)</p>
<p class="text-4xl">4XL (2.25rem)</p>
<p class="text-5xl">5XL (3rem)</p>

<!-- Peso de la fuente -->
<p class="font-thin">Thin (100)</p>
<p class="font-light">Light (300)</p>
<p class="font-normal">Normal (400)</p>
<p class="font-medium">Medium (500)</p>
<p class="font-semibold">Semibold (600)</p>
<p class="font-bold">Bold (700)</p>
<p class="font-black">Black (900)</p>

<!-- Color de texto -->
<p class="text-black">Black text</p>
<p class="text-white">White text</p>
<p class="text-gray-500">Gray text</p>
<p class="text-blue-600">Blue text</p>

<!-- Alineación del texto -->
<p class="text-left">Left aligned</p>
<p class="text-center">Center aligned</p>
<p class="text-right">Right aligned</p>
<p class="text-justify">Justified</p>

<!-- Decoración del texto -->
<p class="underline">Underlined text</p>
<p class="line-through">Strikethrough</p>
<p class="no-underline">No underline</p>

<!-- Transformación del texto -->
<p class="uppercase">UPPERCASE TEXT</p>
<p class="lowercase">lowercase text</p>
<p class="capitalize">Capitalized Text</p>

<!-- Altura de línea -->
<p class="leading-tight">Tight line height</p>
<p class="leading-normal">Normal line height</p>
<p class="leading-loose">Loose line height</p>
```

### Utilidades de Fondo

```html
<!-- Color de fondo -->
<div class="bg-white">White background</div>
<div class="bg-gray-100">Light gray</div>
<div class="bg-blue-500">Blue background</div>
<div class="bg-transparent">Transparent</div>

<!-- Opacidad del fondo -->
<div class="bg-blue-500 bg-opacity-50">50% opacity</div>
<div class="bg-red-500 bg-opacity-75">75% opacity</div>

<!-- Tamaño del fondo -->
<div class="bg-cover">background-size: cover</div>
<div class="bg-contain">background-size: contain</div>

<!-- Posición del fondo -->
<div class="bg-center">background-position: center</div>
<div class="bg-top">background-position: top</div>

<!-- Repetición del fondo -->
<div class="bg-repeat">background-repeat: repeat</div>
<div class="bg-no-repeat">background-repeat: no-repeat</div>
```

---

## 7. Diseño Responsive

### Enfoque Mobile-First

Tailwind usa un sistema de breakpoints mobile-first. Las utilidades sin prefijo se aplican a todos los tamaños de pantalla, mientras que las utilidades con prefijo se aplican en breakpoints específicos y superiores.

**Breakpoints por Defecto:**

| Breakpoint | Ancho Mínimo | CSS |
|------------|-----------|-----|
| `sm` | 640px | `@media (min-width: 640px)` |
| `md` | 768px | `@media (min-width: 768px)` |
| `lg` | 1024px | `@media (min-width: 1024px)` |
| `xl` | 1280px | `@media (min-width: 1280px)` |
| `2xl` | 1536px | `@media (min-width: 1536px)` |

### Sintaxis Responsive

```html
<!-- Móvil: 100% de ancho, Escritorio: 50% de ancho -->
<div class="w-full md:w-1/2">
  Responsive width
</div>

<!-- Móvil: apilar, Escritorio: fila flex -->
<div class="flex-col md:flex-row">
  <div>Item 1</div>
  <div>Item 2</div>
</div>

<!-- Múltiples breakpoints -->
<div class="text-sm md:text-base lg:text-lg xl:text-xl">
  Responsive text size
</div>
```

### Ejemplos Responsive

**Cuadrícula Responsive:**
```html
<!-- 1 columna en móvil, 2 en tablet, 3 en escritorio -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
  <div class="bg-blue-500">Card 1</div>
  <div class="bg-blue-500">Card 2</div>
  <div class="bg-blue-500">Card 3</div>
</div>
```

**Navegación Responsive:**
```html
<nav class="flex flex-col md:flex-row items-center justify-between p-4">
  <div class="text-xl font-bold mb-4 md:mb-0">Logo</div>
  <div class="flex flex-col md:flex-row space-y-2 md:space-y-0 md:space-x-4">
    <a href="#" class="text-gray-700 hover:text-blue-500">Home</a>
    <a href="#" class="text-gray-700 hover:text-blue-500">About</a>
    <a href="#" class="text-gray-700 hover:text-blue-500">Contact</a>
  </div>
</nav>
```

**Padding/Margin Responsive:**
```html
<!-- Padding pequeño en móvil, grande en escritorio -->
<div class="p-4 md:p-8 lg:p-12">
  Content with responsive padding
</div>

<!-- Márgenes responsive -->
<div class="mx-4 md:mx-8 lg:mx-auto lg:max-w-4xl">
  Centered container on desktop
</div>
```

**Ocultar/Mostrar en Breakpoints:**
```html
<!-- Mostrar solo en móvil -->
<div class="block md:hidden">
  Mobile menu
</div>

<!-- Ocultar en móvil, mostrar en escritorio -->
<div class="hidden md:block">
  Desktop menu
</div>

<!-- Contenido distinto en tamaños distintos -->
<div>
  <span class="inline md:hidden">Mobile text</span>
  <span class="hidden md:inline">Desktop text</span>
</div>
```

### Breakpoints Personalizados

Añade breakpoints personalizados en `tailwind.config.js`:

```javascript
module.exports = {
  theme: {
    screens: {
      'xs': '475px',
      'sm': '640px',
      'md': '768px',
      'lg': '1024px',
      'xl': '1280px',
      '2xl': '1536px',
      '3xl': '1920px',
    }
  }
}
```

Uso:
```html
<div class="text-sm xs:text-base md:text-lg 3xl:text-2xl">
  Custom breakpoint text
</div>
```

---

## 8. Variantes y Estados

### Estado Hover

```html
<!-- Color de fondo en hover -->
<button class="bg-blue-500 hover:bg-blue-600">
  Hover me
</button>

<!-- Color de texto en hover -->
<a href="#" class="text-blue-500 hover:text-blue-700">
  Link
</a>

<!-- Escala en hover -->
<div class="transform hover:scale-105 transition">
  Hover to scale
</div>

<!-- Sombra en hover -->
<div class="shadow hover:shadow-lg transition">
  Hover for shadow
</div>
```

### Estado Focus

```html
<!-- Anillo de foco -->
<input
  type="text"
  class="border border-gray-300 focus:border-blue-500 focus:ring focus:ring-blue-200"
  placeholder="Focus me"
>

<!-- Contorno de foco -->
<button class="bg-blue-500 focus:outline-none focus:ring-4 focus:ring-blue-300">
  Accessible button
</button>
```

### Estado Active

```html
<!-- Estado active (presionado) -->
<button class="bg-blue-500 active:bg-blue-700">
  Click me
</button>

<!-- Escala en active -->
<button class="transform active:scale-95 transition">
  Press me
</button>
```

### Estado Disabled

```html
<!-- Estilizado deshabilitado -->
<button
  disabled
  class="bg-blue-500 text-white disabled:bg-gray-300 disabled:cursor-not-allowed"
>
  Disabled button
</button>

<input
  type="text"
  disabled
  class="border disabled:bg-gray-100 disabled:text-gray-500"
>
```

### Group Hover

```html
<!-- El hover del padre afecta a los hijos -->
<div class="group">
  <img
    src="image.jpg"
    class="group-hover:opacity-75 transition"
  >
  <p class="text-gray-600 group-hover:text-blue-500">
    Hover the parent to change both
  </p>
</div>

<!-- Tarjeta con group hover -->
<div class="group bg-white p-4 hover:bg-gray-50 cursor-pointer">
  <h3 class="font-bold group-hover:text-blue-500">Card Title</h3>
  <p class="text-gray-600">Card description</p>
  <button class="mt-2 text-blue-500 opacity-0 group-hover:opacity-100 transition">
    Read more
  </button>
</div>
```

### Otros Estados

```html
<!-- Primer hijo -->
<ul>
  <li class="first:border-t-0 border-t">Item 1</li>
  <li class="first:border-t-0 border-t">Item 2</li>
</ul>

<!-- Último hijo -->
<ul>
  <li class="last:border-b-0 border-b">Item 1</li>
  <li class="last:border-b-0 border-b">Item 2</li>
</ul>

<!-- Impar/Par (Odd/Even) -->
<ul>
  <li class="odd:bg-gray-100">Item 1</li>
  <li class="odd:bg-gray-100">Item 2</li>
  <li class="odd:bg-gray-100">Item 3</li>
</ul>

<!-- Estado checked (checkboxes/radio) -->
<input
  type="checkbox"
  class="checked:bg-blue-500 checked:border-transparent"
>

<!-- Placeholder -->
<input
  type="text"
  class="placeholder:text-gray-400 placeholder:italic"
  placeholder="Enter text..."
>

<!-- Solo lectura (Read-only) -->
<input
  type="text"
  readonly
  class="read-only:bg-gray-100"
  value="Read-only value"
>
```

### Combinando Variantes

```html
<!-- Responsive + Hover -->
<button class="bg-blue-500 hover:bg-blue-600 md:hover:bg-blue-700">
  Responsive hover
</button>

<!-- Modo oscuro + Hover -->
<button class="bg-white text-black hover:bg-gray-100 dark:bg-black dark:text-white dark:hover:bg-gray-900">
  Dark mode button
</button>

<!-- Group + Responsive + Hover -->
<div class="group">
  <img class="group-hover:opacity-75 md:group-hover:scale-105 transition">
</div>
```

---

## 9. Colores y Personalización

### Paleta de Colores por Defecto

Tailwind incluye una paleta de colores completa con tonos del 50 al 950:

```html
<!-- Grises -->
<div class="bg-gray-50">Lightest gray</div>
<div class="bg-gray-100">Very light gray</div>
<div class="bg-gray-500">Medium gray</div>
<div class="bg-gray-900">Very dark gray</div>

<!-- Azules -->
<div class="bg-blue-50">Lightest blue</div>
<div class="bg-blue-500">Medium blue</div>
<div class="bg-blue-900">Dark blue</div>

<!-- Otros colores -->
<div class="bg-red-500">Red</div>
<div class="bg-green-500">Green</div>
<div class="bg-yellow-500">Yellow</div>
<div class="bg-purple-500">Purple</div>
<div class="bg-pink-500">Pink</div>
<div class="bg-indigo-500">Indigo</div>
```

### Valores Arbitrarios

Tailwind 3+ soporta valores arbitrarios para colores personalizados:

```html
<!-- Color hex personalizado -->
<div class="bg-[#1da1f2]">Twitter blue</div>

<!-- RGB personalizado -->
<div class="bg-[rgb(255,0,0)]">Custom red</div>

<!-- RGBA personalizado -->
<div class="bg-[rgba(255,0,0,0.5)]">Transparent red</div>

<!-- Personalizado con variables -->
<div class="bg-[var(--my-color)]">CSS variable color</div>

<!-- Color de texto arbitrario -->
<p class="text-[#ff6b6b]">Custom text color</p>

<!-- Color de borde arbitrario -->
<div class="border-2 border-[#4ecdc4]">Custom border</div>
```

### Modificadores de Opacidad

```html
<!-- Fondo con opacidad -->
<div class="bg-blue-500/50">50% opacity blue</div>
<div class="bg-blue-500/75">75% opacity blue</div>
<div class="bg-blue-500/100">100% opacity blue</div>

<!-- Texto con opacidad -->
<p class="text-gray-900/80">80% opacity text</p>

<!-- Borde con opacidad -->
<div class="border-2 border-blue-500/30">Transparent border</div>
```

### Colores Personalizados en la Config

Añade colores personalizados en `tailwind.config.js`:

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        'brand-blue': '#1da1f2',
        'brand-dark': '#14171a',
        'brand-gray': '#657786',
        'custom': {
          50: '#f0f9ff',
          100: '#e0f2fe',
          500: '#0ea5e9',
          900: '#0c4a6e',
        }
      }
    }
  }
}
```

Uso:
```html
<div class="bg-brand-blue">Brand color</div>
<div class="text-custom-500">Custom color</div>
<button class="bg-brand-blue hover:bg-brand-dark">
  Button
</button>
```

### Utilidades de Color

```html
<!-- Color de texto -->
<p class="text-blue-500">Blue text</p>

<!-- Color de fondo -->
<div class="bg-green-500">Green background</div>

<!-- Color de borde -->
<div class="border-2 border-red-500">Red border</div>

<!-- Color de divide (entre los hijos) -->
<div class="divide-y divide-gray-200">
  <div>Item 1</div>
  <div>Item 2</div>
</div>

<!-- Color de ring (anillos de foco) -->
<input class="focus:ring-2 focus:ring-blue-500">

<!-- Color del placeholder -->
<input class="placeholder:text-gray-400" placeholder="Enter...">
```

---

## 10. Utilidades de Layout

### Container

```html
<!-- Contenedor centrado con max-width responsive -->
<div class="container mx-auto">
  Content centered and responsive
</div>

<!-- Contenedor con padding -->
<div class="container mx-auto px-4">
  Content with horizontal padding
</div>
```

**Breakpoints del container:**
- `sm` (640px): max-width: 640px
- `md` (768px): max-width: 768px
- `lg` (1024px): max-width: 1024px
- `xl` (1280px): max-width: 1280px
- `2xl` (1536px): max-width: 1536px

### Box Sizing

```html
<!-- Border box -->
<div class="box-border">box-sizing: border-box</div>

<!-- Content box -->
<div class="box-content">box-sizing: content-box</div>
```

### Position

```html
<!-- Static (por defecto) -->
<div class="static">position: static</div>

<!-- Relative -->
<div class="relative">
  position: relative
  <div class="absolute top-0 right-0">Positioned child</div>
</div>

<!-- Absolute -->
<div class="absolute top-0 left-0">position: absolute</div>

<!-- Fixed -->
<div class="fixed bottom-4 right-4">Fixed to viewport</div>

<!-- Sticky -->
<div class="sticky top-0">Sticky header</div>
```

### Top/Right/Bottom/Left

```html
<!-- Posicionamiento absoluto -->
<div class="relative h-32">
  <div class="absolute top-0 left-0">Top left</div>
  <div class="absolute top-0 right-0">Top right</div>
  <div class="absolute bottom-0 left-0">Bottom left</div>
  <div class="absolute bottom-0 right-0">Bottom right</div>
</div>

<!-- Centrar de forma absoluta -->
<div class="relative h-32">
  <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2">
    Centered
  </div>
</div>

<!-- Cobertura completa -->
<div class="relative h-32">
  <div class="absolute inset-0">Covers entire parent</div>
</div>
```

### Z-Index

```html
<!-- Valores de z-index -->
<div class="z-0">z-index: 0</div>
<div class="z-10">z-index: 10</div>
<div class="z-20">z-index: 20</div>
<div class="z-30">z-index: 30</div>
<div class="z-40">z-index: 40</div>
<div class="z-50">z-index: 50</div>

<!-- z-index negativo -->
<div class="-z-10">z-index: -10</div>

<!-- Auto -->
<div class="z-auto">z-index: auto</div>
```

### Overflow

```html
<!-- Overflow visible -->
<div class="overflow-visible">Content can overflow</div>

<!-- Overflow hidden -->
<div class="overflow-hidden">Clip overflow</div>

<!-- Overflow scroll -->
<div class="overflow-scroll">Always show scrollbars</div>

<!-- Overflow auto -->
<div class="overflow-auto">Scrollbars when needed</div>

<!-- Overflow direccional -->
<div class="overflow-x-auto">Horizontal scroll</div>
<div class="overflow-y-auto">Vertical scroll</div>

<!-- Overflow con puntos suspensivos -->
<p class="truncate">Text overflow with ellipsis...</p>
```

### Visibility

```html
<!-- Visible -->
<div class="visible">Visible element</div>

<!-- Invisible (ocupa espacio) -->
<div class="invisible">Invisible but takes space</div>

<!-- Hidden (sin espacio) -->
<div class="hidden">Removed from flow</div>
```

---

## 11. Tipografía y Utilidades de Texto

### Familia de Fuente

```html
<!-- Sans-serif (por defecto) -->
<p class="font-sans">System sans-serif font</p>

<!-- Serif -->
<p class="font-serif">Serif font</p>

<!-- Monospace -->
<p class="font-mono">Monospace font</p>
```

Fuentes personalizadas en la config:
```javascript
module.exports = {
  theme: {
    extend: {
      fontFamily: {
        'custom': ['Inter', 'sans-serif'],
        'display': ['Poppins', 'sans-serif'],
      }
    }
  }
}
```

```html
<h1 class="font-display">Display font</h1>
<p class="font-custom">Custom font</p>
```

### Tamaño de Fuente

```html
<p class="text-xs">Extra small (0.75rem / 12px)</p>
<p class="text-sm">Small (0.875rem / 14px)</p>
<p class="text-base">Base (1rem / 16px)</p>
<p class="text-lg">Large (1.125rem / 18px)</p>
<p class="text-xl">XL (1.25rem / 20px)</p>
<p class="text-2xl">2XL (1.5rem / 24px)</p>
<p class="text-3xl">3XL (1.875rem / 30px)</p>
<p class="text-4xl">4XL (2.25rem / 36px)</p>
<p class="text-5xl">5XL (3rem / 48px)</p>
<p class="text-6xl">6XL (3.75rem / 60px)</p>
<p class="text-7xl">7XL (4.5rem / 72px)</p>
<p class="text-8xl">8XL (6rem / 96px)</p>
<p class="text-9xl">9XL (8rem / 128px)</p>

<!-- Tamaño arbitrario -->
<p class="text-[14px]">Custom 14px</p>
<p class="text-[1.375rem]">Custom 1.375rem</p>
```

### Peso de la Fuente

```html
<p class="font-thin">Thin (100)</p>
<p class="font-extralight">Extra light (200)</p>
<p class="font-light">Light (300)</p>
<p class="font-normal">Normal (400)</p>
<p class="font-medium">Medium (500)</p>
<p class="font-semibold">Semibold (600)</p>
<p class="font-bold">Bold (700)</p>
<p class="font-extrabold">Extra bold (800)</p>
<p class="font-black">Black (900)</p>
```

### Altura de Línea (Leading)

```html
<p class="leading-none">line-height: 1</p>
<p class="leading-tight">line-height: 1.25</p>
<p class="leading-snug">line-height: 1.375</p>
<p class="leading-normal">line-height: 1.5</p>
<p class="leading-relaxed">line-height: 1.625</p>
<p class="leading-loose">line-height: 2</p>

<!-- Valores específicos -->
<p class="leading-3">line-height: 0.75rem</p>
<p class="leading-10">line-height: 2.5rem</p>

<!-- Arbitrario -->
<p class="leading-[3rem]">Custom line height</p>
```

### Espaciado entre Letras (Tracking)

```html
<p class="tracking-tighter">letter-spacing: -0.05em</p>
<p class="tracking-tight">letter-spacing: -0.025em</p>
<p class="tracking-normal">letter-spacing: 0</p>
<p class="tracking-wide">letter-spacing: 0.025em</p>
<p class="tracking-wider">letter-spacing: 0.05em</p>
<p class="tracking-widest">letter-spacing: 0.1em</p>
```

### Transformación del Texto

```html
<p class="uppercase">UPPERCASE TEXT</p>
<p class="lowercase">lowercase text</p>
<p class="capitalize">Capitalized Text</p>
<p class="normal-case">Normal Case</p>
```

### Decoración del Texto

```html
<p class="underline">Underlined text</p>
<p class="overline">Overline text</p>
<p class="line-through">Strikethrough text</p>
<p class="no-underline">No underline</p>

<!-- Estilo de decoración -->
<p class="underline decoration-solid">Solid underline</p>
<p class="underline decoration-double">Double underline</p>
<p class="underline decoration-dotted">Dotted underline</p>
<p class="underline decoration-dashed">Dashed underline</p>
<p class="underline decoration-wavy">Wavy underline</p>

<!-- Color de decoración -->
<p class="underline decoration-blue-500">Blue underline</p>

<!-- Grosor de decoración -->
<p class="underline decoration-2">Thick underline</p>
```

### Overflow del Texto

```html
<!-- Truncar con puntos suspensivos -->
<p class="truncate w-32">
  This text will be truncated with ellipsis
</p>

<!-- Overflow con puntos suspensivos -->
<p class="overflow-hidden text-ellipsis w-32">
  Long text with ellipsis
</p>

<!-- Line clamp (limitar líneas) -->
<p class="line-clamp-2">
  This text will be limited to 2 lines and show ellipsis if it exceeds
  that limit. Very useful for cards and previews.
</p>
```

---

## 12. Espaciado y Dimensionado

### Escala de Espaciado

Tailwind usa una escala de espaciado basada en unidades rem:

| Clase | rem | px (con base de 16px) |
|-------|-----|-------------------|
| `0` | 0 | 0px |
| `px` | 1px | 1px |
| `0.5` | 0.125rem | 2px |
| `1` | 0.25rem | 4px |
| `2` | 0.5rem | 8px |
| `3` | 0.75rem | 12px |
| `4` | 1rem | 16px |
| `5` | 1.25rem | 20px |
| `6` | 1.5rem | 24px |
| `8` | 2rem | 32px |
| `10` | 2.5rem | 40px |
| `12` | 3rem | 48px |
| `16` | 4rem | 64px |
| `20` | 5rem | 80px |
| `24` | 6rem | 96px |
| `32` | 8rem | 128px |
| `40` | 10rem | 160px |
| `48` | 12rem | 192px |
| `56` | 14rem | 224px |
| `64` | 16rem | 256px |

### Ejemplos de Padding

```html
<!-- Todos los lados -->
<div class="p-4">padding: 1rem (16px)</div>
<div class="p-8">padding: 2rem (32px)</div>

<!-- Horizontal (izquierda + derecha) -->
<div class="px-4">padding-left: 1rem; padding-right: 1rem;</div>

<!-- Vertical (arriba + abajo) -->
<div class="py-4">padding-top: 1rem; padding-bottom: 1rem;</div>

<!-- Lados individuales -->
<div class="pt-4">padding-top: 1rem</div>
<div class="pr-4">padding-right: 1rem</div>
<div class="pb-4">padding-bottom: 1rem</div>
<div class="pl-4">padding-left: 1rem</div>

<!-- Padding responsive -->
<div class="p-4 md:p-8 lg:p-12">
  Responsive padding
</div>
```

### Ejemplos de Margin

```html
<!-- Margin positivo -->
<div class="m-4">margin: 1rem</div>
<div class="mx-auto">margin-left: auto; margin-right: auto (centrado)</div>

<!-- Margin negativo -->
<div class="-mt-4">margin-top: -1rem</div>
<div class="-mx-2">negative horizontal margin</div>

<!-- Margin auto -->
<div class="mx-auto max-w-4xl">Centered container</div>
```

### Gap (para Flex/Grid)

```html
<!-- Gap de flexbox -->
<div class="flex gap-4">
  <div>Item 1</div>
  <div>Item 2</div>
</div>

<!-- Gap de grid -->
<div class="grid grid-cols-3 gap-4">
  <div>Cell 1</div>
  <div>Cell 2</div>
  <div>Cell 3</div>
</div>

<!-- Gap direccional -->
<div class="flex gap-x-4 gap-y-2">
  Different horizontal and vertical gaps
</div>
```

### Dimensionado de Ancho

```html
<!-- Anchos fijos -->
<div class="w-32">width: 8rem (128px)</div>
<div class="w-64">width: 16rem (256px)</div>

<!-- Anchos fraccionarios -->
<div class="w-1/2">width: 50%</div>
<div class="w-1/3">width: 33.333%</div>
<div class="w-2/3">width: 66.667%</div>
<div class="w-1/4">width: 25%</div>
<div class="w-3/4">width: 75%</div>

<!-- Ancho completo -->
<div class="w-full">width: 100%</div>
<div class="w-screen">width: 100vw</div>

<!-- Ancho Min/Max -->
<div class="min-w-0">min-width: 0</div>
<div class="max-w-xs">max-width: 20rem</div>
<div class="max-w-sm">max-width: 24rem</div>
<div class="max-w-md">max-width: 28rem</div>
<div class="max-w-lg">max-width: 32rem</div>
<div class="max-w-xl">max-width: 36rem</div>
<div class="max-w-2xl">max-width: 42rem</div>
<div class="max-w-4xl">max-width: 56rem</div>
<div class="max-w-full">max-width: 100%</div>

<!-- Ancho arbitrario -->
<div class="w-[350px]">Custom width 350px</div>
```

### Dimensionado de Alto

```html
<!-- Altos fijos -->
<div class="h-32">height: 8rem</div>
<div class="h-64">height: 16rem</div>

<!-- Alto completo -->
<div class="h-full">height: 100%</div>
<div class="h-screen">height: 100vh</div>

<!-- Alto Min/Max -->
<div class="min-h-screen">min-height: 100vh</div>
<div class="max-h-64">max-height: 16rem</div>

<!-- Alto arbitrario -->
<div class="h-[500px]">Custom 500px height</div>
```

---

## 13. Flexbox y Grid

### Fundamentos de Flexbox

```html
<!-- Contenedor flex -->
<div class="flex">
  <div>Item 1</div>
  <div>Item 2</div>
</div>

<!-- Inline flex -->
<div class="inline-flex">
  <div>Item 1</div>
  <div>Item 2</div>
</div>

<!-- Dirección del flex -->
<div class="flex flex-row">Horizontal (por defecto)</div>
<div class="flex flex-row-reverse">Horizontal invertido</div>
<div class="flex flex-col">Vertical</div>
<div class="flex flex-col-reverse">Vertical invertido</div>

<!-- Flex wrap -->
<div class="flex flex-wrap">Items wrap to new line</div>
<div class="flex flex-nowrap">Items don't wrap (por defecto)</div>
<div class="flex flex-wrap-reverse">Wrap reversed</div>
```

### Alineación en Flex

```html
<!-- Justify content (eje principal) -->
<div class="flex justify-start">Start (por defecto)</div>
<div class="flex justify-center">Center</div>
<div class="flex justify-end">End</div>
<div class="flex justify-between">Space between</div>
<div class="flex justify-around">Space around</div>
<div class="flex justify-evenly">Space evenly</div>

<!-- Align items (eje transversal) -->
<div class="flex items-start">Start</div>
<div class="flex items-center">Center</div>
<div class="flex items-end">End</div>
<div class="flex items-stretch">Stretch (por defecto)</div>
<div class="flex items-baseline">Baseline</div>

<!-- Align content (múltiples líneas) -->
<div class="flex flex-wrap content-start">Content start</div>
<div class="flex flex-wrap content-center">Content center</div>
<div class="flex flex-wrap content-end">Content end</div>
<div class="flex flex-wrap content-between">Content between</div>
```

### Propiedades de los Items Flex

```html
<!-- Flex grow -->
<div class="flex">
  <div class="flex-grow">Grows to fill space</div>
  <div>Fixed size</div>
</div>

<!-- Flex shrink -->
<div class="flex">
  <div class="flex-shrink">Can shrink</div>
  <div class="flex-shrink-0">Won't shrink</div>
</div>

<!-- Flex basis -->
<div class="flex">
  <div class="basis-1/4">25% basis</div>
  <div class="basis-1/2">50% basis</div>
  <div class="basis-1/4">25% basis</div>
</div>

<!-- Flex abreviado -->
<div class="flex">
  <div class="flex-1">flex: 1 1 0%</div>
  <div class="flex-auto">flex: 1 1 auto</div>
  <div class="flex-none">flex: none</div>
</div>

<!-- Order -->
<div class="flex">
  <div class="order-2">Second</div>
  <div class="order-1">First</div>
  <div class="order-3">Third</div>
</div>
```

### Ejemplos Prácticos de Flexbox

```html
<!-- Tarjeta centrada -->
<div class="min-h-screen flex items-center justify-center bg-gray-100">
  <div class="bg-white p-8 rounded-lg shadow-md">
    Centered content
  </div>
</div>

<!-- Barra de navegación -->
<nav class="flex items-center justify-between p-4 bg-white shadow">
  <div class="text-xl font-bold">Logo</div>
  <div class="flex space-x-4">
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
  </div>
</nav>

<!-- Layout de tarjetas -->
<div class="flex flex-wrap gap-4">
  <div class="flex-1 min-w-[200px] bg-white p-4 rounded shadow">Card 1</div>
  <div class="flex-1 min-w-[200px] bg-white p-4 rounded shadow">Card 2</div>
  <div class="flex-1 min-w-[200px] bg-white p-4 rounded shadow">Card 3</div>
</div>
```

### Fundamentos de Grid

```html
<!-- Contenedor grid -->
<div class="grid">
  <div>Cell 1</div>
  <div>Cell 2</div>
</div>

<!-- Columnas del grid -->
<div class="grid grid-cols-2">2 columns</div>
<div class="grid grid-cols-3">3 columns</div>
<div class="grid grid-cols-4">4 columns</div>
<div class="grid grid-cols-6">6 columns</div>
<div class="grid grid-cols-12">12 columns</div>

<!-- Filas del grid -->
<div class="grid grid-rows-2">2 rows</div>
<div class="grid grid-rows-3">3 rows</div>

<!-- Combinado -->
<div class="grid grid-cols-3 grid-rows-2 gap-4">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

### Gap del Grid

```html
<!-- Gap (se aplica tanto a filas como a columnas) -->
<div class="grid grid-cols-3 gap-4">
  <div>Cell</div>
  <div>Cell</div>
  <div>Cell</div>
</div>

<!-- Gaps direccionales -->
<div class="grid grid-cols-3 gap-x-4 gap-y-2">
  Different horizontal and vertical gaps
</div>
```

### Grid Column/Row Span

```html
<!-- Column span -->
<div class="grid grid-cols-3 gap-4">
  <div class="col-span-2">Spans 2 columns</div>
  <div>Normal</div>
  <div>Normal</div>
  <div class="col-span-2">Spans 2 columns</div>
</div>

<!-- Row span -->
<div class="grid grid-cols-3 grid-rows-3 gap-4">
  <div class="row-span-2">Spans 2 rows</div>
  <div>Normal</div>
  <div>Normal</div>
</div>

<!-- Full span -->
<div class="grid grid-cols-4 gap-4">
  <div class="col-span-full">Spans all columns</div>
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
</div>
```

### Colocación en el Grid

```html
<!-- Column start/end -->
<div class="grid grid-cols-6 gap-4">
  <div class="col-start-1 col-end-3">Columns 1-3</div>
  <div class="col-start-4 col-end-7">Columns 4-7</div>
</div>

<!-- Row start/end -->
<div class="grid grid-rows-4 gap-4">
  <div class="row-start-1 row-end-3">Rows 1-3</div>
  <div class="row-start-3 row-end-5">Rows 3-5</div>
</div>
```

### Grid Responsive

```html
<!-- Móvil: 1 col, Tablet: 2 cols, Escritorio: 4 cols -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
  <div class="bg-blue-500 p-4">Card 1</div>
  <div class="bg-blue-500 p-4">Card 2</div>
  <div class="bg-blue-500 p-4">Card 3</div>
  <div class="bg-blue-500 p-4">Card 4</div>
</div>
```

---

## 14. Fondos y Gradientes

### Imágenes de Fondo

```html
<!-- Imagen de fondo -->
<div
  class="bg-[url('/images/hero.jpg')]"
  style="background-image: url('/images/hero.jpg')"
>
  Background image
</div>

<!-- Tamaño del fondo -->
<div class="bg-cover">background-size: cover</div>
<div class="bg-contain">background-size: contain</div>
<div class="bg-auto">background-size: auto</div>

<!-- Posición del fondo -->
<div class="bg-center">Center</div>
<div class="bg-top">Top</div>
<div class="bg-bottom">Bottom</div>
<div class="bg-left">Left</div>
<div class="bg-right">Right</div>
<div class="bg-left-top">Left top</div>

<!-- Repetición del fondo -->
<div class="bg-repeat">Repeat (por defecto)</div>
<div class="bg-no-repeat">No repeat</div>
<div class="bg-repeat-x">Repeat horizontally</div>
<div class="bg-repeat-y">Repeat vertically</div>
```

### Fondos con Gradiente

```html
<!-- Gradientes lineales -->
<div class="bg-gradient-to-r from-blue-500 to-purple-500">
  Left to right gradient
</div>

<div class="bg-gradient-to-l from-blue-500 to-purple-500">
  Right to left gradient
</div>

<div class="bg-gradient-to-t from-blue-500 to-purple-500">
  Bottom to top gradient
</div>

<div class="bg-gradient-to-b from-blue-500 to-purple-500">
  Top to bottom gradient
</div>

<!-- Gradientes diagonales -->
<div class="bg-gradient-to-br from-blue-500 to-purple-500">
  Top-left to bottom-right
</div>

<div class="bg-gradient-to-tr from-blue-500 to-purple-500">
  Bottom-left to top-right
</div>

<!-- Gradientes de tres colores -->
<div class="bg-gradient-to-r from-blue-500 via-purple-500 to-pink-500">
  Three color gradient
</div>

<!-- Gradiente con transparencia -->
<div class="bg-gradient-to-r from-blue-500/50 to-purple-500/50">
  Semi-transparent gradient
</div>
```

### Ejemplos Avanzados de Gradiente

```html
<!-- Hero con superposición de gradiente -->
<div class="relative h-96 bg-[url('/hero.jpg')] bg-cover bg-center">
  <div class="absolute inset-0 bg-gradient-to-b from-transparent to-black/70"></div>
  <div class="relative z-10 flex items-center justify-center h-full">
    <h1 class="text-white text-5xl font-bold">Hero Title</h1>
  </div>
</div>

<!-- Efecto de borde con gradiente -->
<div class="p-1 bg-gradient-to-r from-blue-500 to-purple-500 rounded-lg">
  <div class="bg-white p-8 rounded-lg">
    Content with gradient border
  </div>
</div>

<!-- Texto con gradiente -->
<h1 class="text-6xl font-bold bg-gradient-to-r from-blue-500 to-purple-500 bg-clip-text text-transparent">
  Gradient Text
</h1>
```

### Modos de Mezcla del Fondo

```html
<!-- Multiply -->
<div class="bg-blue-500 bg-blend-multiply">
  Multiply blend
</div>

<!-- Screen -->
<div class="bg-blue-500 bg-blend-screen">
  Screen blend
</div>

<!-- Overlay -->
<div class="bg-blue-500 bg-blend-overlay">
  Overlay blend
</div>
```

---

## 15. Bordes y Efectos

### Grosor del Borde

```html
<!-- Todos los lados -->
<div class="border">border-width: 1px (por defecto)</div>
<div class="border-2">border-width: 2px</div>
<div class="border-4">border-width: 4px</div>
<div class="border-8">border-width: 8px</div>

<!-- Lados individuales -->
<div class="border-t">Top border</div>
<div class="border-r">Right border</div>
<div class="border-b">Bottom border</div>
<div class="border-l">Left border</div>

<!-- Combinaciones -->
<div class="border-x">Left + right border</div>
<div class="border-y">Top + bottom border</div>

<!-- Sin borde -->
<div class="border-0">No border</div>
```

### Border Radius

```html
<!-- Todas las esquinas -->
<div class="rounded">border-radius: 0.25rem</div>
<div class="rounded-md">border-radius: 0.375rem</div>
<div class="rounded-lg">border-radius: 0.5rem</div>
<div class="rounded-xl">border-radius: 0.75rem</div>
<div class="rounded-2xl">border-radius: 1rem</div>
<div class="rounded-3xl">border-radius: 1.5rem</div>
<div class="rounded-full">border-radius: 9999px (círculo)</div>

<!-- Esquinas individuales -->
<div class="rounded-t-lg">Top corners rounded</div>
<div class="rounded-r-lg">Right corners rounded</div>
<div class="rounded-b-lg">Bottom corners rounded</div>
<div class="rounded-l-lg">Left corners rounded</div>
<div class="rounded-tl-lg">Top-left corner</div>
<div class="rounded-tr-lg">Top-right corner</div>
<div class="rounded-br-lg">Bottom-right corner</div>
<div class="rounded-bl-lg">Bottom-left corner</div>

<!-- Sin radius -->
<div class="rounded-none">No border radius</div>
```

### Box Shadow

```html
<!-- Tamaños de sombra -->
<div class="shadow-sm">Small shadow</div>
<div class="shadow">Default shadow</div>
<div class="shadow-md">Medium shadow</div>
<div class="shadow-lg">Large shadow</div>
<div class="shadow-xl">Extra large shadow</div>
<div class="shadow-2xl">2XL shadow</div>

<!-- Sombra interior -->
<div class="shadow-inner">Inner shadow</div>

<!-- Sin sombra -->
<div class="shadow-none">No shadow</div>

<!-- Sombras de color -->
<div class="shadow-lg shadow-blue-500/50">Blue shadow</div>
<div class="shadow-lg shadow-red-500/50">Red shadow</div>
```

### Drop Shadow

```html
<!-- Drop shadow (para formas irregulares) -->
<svg class="drop-shadow">SVG with drop shadow</svg>
<svg class="drop-shadow-md">Medium drop shadow</svg>
<svg class="drop-shadow-lg">Large drop shadow</svg>
<svg class="drop-shadow-xl">XL drop shadow</svg>
<svg class="drop-shadow-2xl">2XL drop shadow</svg>

<!-- Sin drop shadow -->
<svg class="drop-shadow-none">No drop shadow</svg>
```

### Opacidad

```html
<!-- Niveles de opacidad -->
<div class="opacity-0">Fully transparent</div>
<div class="opacity-25">25% opacity</div>
<div class="opacity-50">50% opacity</div>
<div class="opacity-75">75% opacity</div>
<div class="opacity-100">Fully opaque</div>

<!-- Opacidad responsive -->
<div class="opacity-0 md:opacity-100">
  Hidden on mobile, visible on desktop
</div>

<!-- Opacidad en hover -->
<img class="opacity-100 hover:opacity-75 transition">
```

### Transformaciones

```html
<!-- Scale -->
<div class="scale-50">50% size</div>
<div class="scale-75">75% size</div>
<div class="scale-100">Original size (por defecto)</div>
<div class="scale-125">125% size</div>
<div class="scale-150">150% size</div>

<!-- Rotate -->
<div class="rotate-0">No rotation</div>
<div class="rotate-45">45 degrees</div>
<div class="rotate-90">90 degrees</div>
<div class="rotate-180">180 degrees</div>
<div class="-rotate-45">-45 degrees</div>

<!-- Translate -->
<div class="translate-x-4">Move right 1rem</div>
<div class="translate-y-4">Move down 1rem</div>
<div class="-translate-x-4">Move left 1rem</div>
<div class="-translate-y-4">Move up 1rem</div>

<!-- Skew -->
<div class="skew-x-12">Skew X axis</div>
<div class="skew-y-12">Skew Y axis</div>

<!-- Origen de la transformación -->
<div class="origin-center">Center origin (por defecto)</div>
<div class="origin-top-left">Top-left origin</div>
```

### Transiciones

```html
<!-- Propiedad de transición -->
<div class="transition">Transition all properties</div>
<div class="transition-colors">Transition colors only</div>
<div class="transition-transform">Transition transforms only</div>
<div class="transition-opacity">Transition opacity only</div>

<!-- Duración de la transición -->
<div class="duration-75">75ms</div>
<div class="duration-150">150ms (por defecto)</div>
<div class="duration-300">300ms</div>
<div class="duration-500">500ms</div>
<div class="duration-1000">1000ms (1s)</div>

<!-- Timing de la transición -->
<div class="ease-linear">Linear</div>
<div class="ease-in">Ease in</div>
<div class="ease-out">Ease out</div>
<div class="ease-in-out">Ease in-out (por defecto)</div>

<!-- Retraso de la transición -->
<div class="delay-75">75ms delay</div>
<div class="delay-150">150ms delay</div>
<div class="delay-300">300ms delay</div>

<!-- Ejemplo práctico -->
<button class="bg-blue-500 hover:bg-blue-600 transform hover:scale-105 transition duration-200 ease-out">
  Hover me
</button>
```

### Filtros

```html
<!-- Blur -->
<img class="blur">Slight blur</img>
<img class="blur-md">Medium blur</img>
<img class="blur-lg">Large blur</img>

<!-- Brightness -->
<img class="brightness-50">50% brightness</img>
<img class="brightness-75">75% brightness</img>
<img class="brightness-125">125% brightness</img>

<!-- Contrast -->
<img class="contrast-50">Low contrast</img>
<img class="contrast-125">High contrast</img>

<!-- Grayscale -->
<img class="grayscale">Full grayscale</img>
<img class="grayscale-0">No grayscale</img>

<!-- Sepia -->
<img class="sepia">Sepia tone</img>
```

---

## 16. Funcionalidades Avanzadas

### Modo Oscuro

Habilita el modo oscuro en la config:
```javascript
// tailwind.config.js
module.exports = {
  darkMode: 'class', // o 'media'
  // ...
}
```

**Modo oscuro basado en clases:**
```html
<!-- Añade la clase 'dark' a html/body para habilitar -->
<html class="dark">
  <body class="bg-white dark:bg-gray-900 text-black dark:text-white">
    <div class="bg-gray-100 dark:bg-gray-800 p-4">
      Content adapts to dark mode
    </div>
  </body>
</html>

<!-- Alternar el modo oscuro con JavaScript -->
<script>
  document.documentElement.classList.toggle('dark');
</script>
```

**Ejemplos de modo oscuro:**
```html
<!-- Fondo y texto -->
<div class="bg-white dark:bg-gray-800 text-gray-900 dark:text-gray-100">
  Content
</div>

<!-- Bordes -->
<div class="border border-gray-300 dark:border-gray-700">
  Adaptive border
</div>

<!-- Botones -->
<button class="bg-blue-500 dark:bg-blue-600 hover:bg-blue-600 dark:hover:bg-blue-700">
  Dark mode button
</button>

<!-- Tarjetas -->
<div class="bg-white dark:bg-gray-800 shadow dark:shadow-none border dark:border-gray-700 p-6">
  <h3 class="text-gray-900 dark:text-white">Card Title</h3>
  <p class="text-gray-600 dark:text-gray-400">Card description</p>
</div>
```

### Propiedades Arbitrarias

Usa corchetes para valores CSS personalizados:

```html
<!-- Espaciado personalizado -->
<div class="m-[13px]">Custom margin 13px</div>
<div class="p-[2.375rem]">Custom padding</div>

<!-- Colores personalizados -->
<div class="bg-[#1da1f2]">Twitter blue</div>
<div class="text-[rgb(123,45,67)]">Custom RGB text</div>

<!-- Tamaños personalizados -->
<div class="w-[347px]">Custom width</div>
<div class="h-[calc(100vh-64px)]">Calculated height</div>

<!-- Variables CSS -->
<div class="bg-[var(--my-color)]">CSS variable</div>
<div class="text-[length:var(--my-length)]">Variable with type</div>

<!-- Cualquier propiedad CSS -->
<div class="[mask-type:luminance]">Custom CSS property</div>
<div class="[backdrop-filter:blur(10px)]">Custom backdrop filter</div>
```

### Funciones CSS

```html
<!-- Calc -->
<div class="w-[calc(100%-2rem)]">Calculated width</div>
<div class="h-[calc(100vh-4rem)]">Calculated height</div>

<!-- Min/Max -->
<div class="w-[min(100%,48rem)]">Responsive width with max</div>
<div class="text-[clamp(1rem,5vw,3rem)]">Fluid typography</div>

<!-- Funciones de CSS Grid -->
<div class="grid-cols-[repeat(auto-fit,minmax(250px,1fr))]">
  Auto-responsive grid
</div>
```

### Utilidades Personalizadas con @layer

Crea utilidades personalizadas en tu CSS:

```css
@layer utilities {
  .content-auto {
    content-visibility: auto;
  }

  .scroll-snap-x {
    scroll-snap-type: x mandatory;
  }

  .scroll-snap-y {
    scroll-snap-type: y mandatory;
  }

  .text-shadow {
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
  }
}
```

### Animaciones

```html
<!-- Spin -->
<div class="animate-spin">
  <svg class="w-5 h-5">...</svg>
</div>

<!-- Ping -->
<div class="animate-ping">
  Pulsing dot
</div>

<!-- Pulse -->
<div class="animate-pulse">
  Loading skeleton
</div>

<!-- Bounce -->
<div class="animate-bounce">
  Bouncing arrow
</div>

<!-- Ejemplo de spinner de carga -->
<div class="flex items-center space-x-2">
  <div class="animate-spin rounded-full h-8 w-8 border-b-2 border-blue-500"></div>
  <span>Loading...</span>
</div>
```

### Animaciones Personalizadas

Añade a `tailwind.config.js`:

```javascript
module.exports = {
  theme: {
    extend: {
      keyframes: {
        wiggle: {
          '0%, 100%': { transform: 'rotate(-3deg)' },
          '50%': { transform: 'rotate(3deg)' },
        },
        fadeIn: {
          '0%': { opacity: '0' },
          '100%': { opacity: '1' },
        }
      },
      animation: {
        wiggle: 'wiggle 1s ease-in-out infinite',
        fadeIn: 'fadeIn 0.5s ease-out',
      }
    }
  }
}
```

Uso:
```html
<div class="animate-wiggle">Wiggling element</div>
<div class="animate-fadeIn">Fading in element</div>
```

### Backdrop Filters

```html
<!-- Backdrop blur -->
<div class="backdrop-blur-sm">Light backdrop blur</div>
<div class="backdrop-blur">Default backdrop blur</div>
<div class="backdrop-blur-lg">Large backdrop blur</div>

<!-- Backdrop brightness -->
<div class="backdrop-brightness-50">Darken backdrop</div>
<div class="backdrop-brightness-125">Brighten backdrop</div>

<!-- Backdrop saturate -->
<div class="backdrop-saturate-50">Desaturate backdrop</div>
<div class="backdrop-saturate-200">Saturate backdrop</div>

<!-- Efecto glassmorphism -->
<div class="bg-white/30 backdrop-blur-md border border-white/20 rounded-lg p-6">
  Glassmorphism card
</div>
```

### Mix Blend Mode

```html
<div class="mix-blend-multiply">Multiply</div>
<div class="mix-blend-screen">Screen</div>
<div class="mix-blend-overlay">Overlay</div>
<div class="mix-blend-darken">Darken</div>
<div class="mix-blend-lighten">Lighten</div>
<div class="mix-blend-difference">Difference</div>
```

---

## 17. Proyecto Práctico: Links in Bio

Esta sección cubre la construcción de una página práctica de "Links in Bio" similar a Linktree.

### Estructura del Proyecto

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Links in Bio - Links in Bio</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gradient-to-br from-purple-500 via-pink-500 to-red-500 min-h-screen">
  <!-- El contenido va aquí -->
</body>
</html>
```

### Sección de Perfil

```html
<!-- Contenedor del perfil -->
<div class="max-w-md mx-auto px-4 py-8">
  <!-- Avatar -->
  <div class="flex justify-center mb-4">
    <img
      src="https://unavatar.io/yourhandle"
      alt="Profile"
      class="w-24 h-24 rounded-full ring-4 ring-white shadow-lg"
    >
  </div>

  <!-- Nombre y bio -->
  <div class="text-center text-white mb-8">
    <h1 class="text-2xl font-bold mb-2">@yourhandle</h1>
    <p class="text-sm opacity-90">
      Developer & content creator
    </p>
  </div>
</div>
```

### Botones de Enlace

```html
<!-- Contenedor de enlaces -->
<div class="space-y-4">
  <!-- Enlace de YouTube -->
  <a
    href="https://youtube.com/@yourhandle"
    target="_blank"
    class="block bg-white/90 backdrop-blur-sm hover:bg-white hover:scale-105 transform transition duration-200 rounded-lg p-4 shadow-md"
  >
    <div class="flex items-center space-x-3">
      <svg class="w-6 h-6 text-red-600" fill="currentColor" viewBox="0 0 24 24">
        <!-- Ruta SVG del icono de YouTube -->
      </svg>
      <span class="font-semibold text-gray-800">YouTube</span>
    </div>
  </a>

  <!-- Enlace de Twitch -->
  <a
    href="https://twitch.tv/yourhandle"
    target="_blank"
    class="block bg-white/90 backdrop-blur-sm hover:bg-white hover:scale-105 transform transition duration-200 rounded-lg p-4 shadow-md"
  >
    <div class="flex items-center space-x-3">
      <svg class="w-6 h-6 text-purple-600" fill="currentColor" viewBox="0 0 24 24">
        <!-- Ruta SVG del icono de Twitch -->
      </svg>
      <span class="font-semibold text-gray-800">Twitch</span>
    </div>
  </a>

  <!-- Enlace de Twitter/X -->
  <a
    href="https://twitter.com/yourhandle"
    target="_blank"
    class="block bg-white/90 backdrop-blur-sm hover:bg-white hover:scale-105 transform transition duration-200 rounded-lg p-4 shadow-md"
  >
    <div class="flex items-center space-x-3">
      <svg class="w-6 h-6 text-blue-500" fill="currentColor" viewBox="0 0 24 24">
        <!-- Ruta SVG del icono de Twitter -->
      </svg>
      <span class="font-semibold text-gray-800">Twitter/X</span>
    </div>
  </a>

  <!-- Enlace de GitHub -->
  <a
    href="https://github.com/yourhandle"
    target="_blank"
    class="block bg-white/90 backdrop-blur-sm hover:bg-white hover:scale-105 transform transition duration-200 rounded-lg p-4 shadow-md"
  >
    <div class="flex items-center space-x-3">
      <svg class="w-6 h-6 text-gray-800" fill="currentColor" viewBox="0 0 24 24">
        <!-- Ruta SVG del icono de GitHub -->
      </svg>
      <span class="font-semibold text-gray-800">GitHub</span>
    </div>
  </a>
</div>
```

### Componente Completo

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Links in Bio - @yourhandle</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gradient-to-br from-purple-500 via-pink-500 to-red-500 min-h-screen">

  <!-- Contenedor principal -->
  <div class="max-w-md mx-auto px-4 py-8">

    <!-- Sección de perfil -->
    <div class="text-center mb-8">
      <!-- Avatar con anillo -->
      <div class="flex justify-center mb-4">
        <img
          src="https://unavatar.io/yourhandle"
          alt="Your Name"
          class="w-24 h-24 rounded-full ring-4 ring-white shadow-lg hover:scale-110 transition duration-300"
        >
      </div>

      <!-- Nombre y bio -->
      <h1 class="text-3xl font-bold text-white mb-2 drop-shadow-lg">
        @yourhandle
      </h1>
      <p class="text-white/90 text-sm max-w-xs mx-auto">
        Developer & content creator — JavaScript, React and web development
      </p>
    </div>

    <!-- Enlaces sociales -->
    <div class="space-y-3">
      <!-- YouTube -->
      <a
        href="https://youtube.com/@yourhandle"
        target="_blank"
        rel="noopener noreferrer"
        class="group block bg-white/90 backdrop-blur-sm hover:bg-white hover:shadow-xl hover:-translate-y-1 transform transition-all duration-200 rounded-2xl p-4"
      >
        <div class="flex items-center justify-between">
          <div class="flex items-center space-x-3">
            <div class="bg-red-100 p-2 rounded-lg group-hover:bg-red-200 transition">
              <svg class="w-6 h-6 text-red-600" fill="currentColor" viewBox="0 0 24 24">
                <path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/>
              </svg>
            </div>
            <span class="font-semibold text-gray-800">YouTube</span>
          </div>
          <svg class="w-5 h-5 text-gray-400 group-hover:text-gray-600 group-hover:translate-x-1 transition" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
          </svg>
        </div>
      </a>

      <!-- Twitch -->
      <a
        href="https://twitch.tv/yourhandle"
        target="_blank"
        rel="noopener noreferrer"
        class="group block bg-white/90 backdrop-blur-sm hover:bg-white hover:shadow-xl hover:-translate-y-1 transform transition-all duration-200 rounded-2xl p-4"
      >
        <div class="flex items-center justify-between">
          <div class="flex items-center space-x-3">
            <div class="bg-purple-100 p-2 rounded-lg group-hover:bg-purple-200 transition">
              <svg class="w-6 h-6 text-purple-600" fill="currentColor" viewBox="0 0 24 24">
                <path d="M11.571 4.714h1.715v5.143H11.57zm4.715 0H18v5.143h-1.714zM6 0L1.714 4.286v15.428h5.143V24l4.286-4.286h3.428L22.286 12V0zm14.571 11.143l-3.428 3.428h-3.429l-3 3v-3H6.857V1.714h13.714Z"/>
              </svg>
            </div>
            <span class="font-semibold text-gray-800">Twitch</span>
          </div>
          <svg class="w-5 h-5 text-gray-400 group-hover:text-gray-600 group-hover:translate-x-1 transition" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
          </svg>
        </div>
      </a>

      <!-- Twitter/X -->
      <a
        href="https://twitter.com/yourhandle"
        target="_blank"
        rel="noopener noreferrer"
        class="group block bg-white/90 backdrop-blur-sm hover:bg-white hover:shadow-xl hover:-translate-y-1 transform transition-all duration-200 rounded-2xl p-4"
      >
        <div class="flex items-center justify-between">
          <div class="flex items-center space-x-3">
            <div class="bg-blue-100 p-2 rounded-lg group-hover:bg-blue-200 transition">
              <svg class="w-6 h-6 text-blue-500" fill="currentColor" viewBox="0 0 24 24">
                <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/>
              </svg>
            </div>
            <span class="font-semibold text-gray-800">Twitter/X</span>
          </div>
          <svg class="w-5 h-5 text-gray-400 group-hover:text-gray-600 group-hover:translate-x-1 transition" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
          </svg>
        </div>
      </a>

      <!-- GitHub -->
      <a
        href="https://github.com/yourhandle"
        target="_blank"
        rel="noopener noreferrer"
        class="group block bg-white/90 backdrop-blur-sm hover:bg-white hover:shadow-xl hover:-translate-y-1 transform transition-all duration-200 rounded-2xl p-4"
      >
        <div class="flex items-center justify-between">
          <div class="flex items-center space-x-3">
            <div class="bg-gray-100 p-2 rounded-lg group-hover:bg-gray-200 transition">
              <svg class="w-6 h-6 text-gray-800" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
              </svg>
            </div>
            <span class="font-semibold text-gray-800">GitHub</span>
          </div>
          <svg class="w-5 h-5 text-gray-400 group-hover:text-gray-600 group-hover:translate-x-1 transition" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
          </svg>
        </div>
      </a>
    </div>

    <!-- Footer -->
    <div class="mt-8 text-center">
      <p class="text-white/70 text-sm">
        Hecho con <span class="text-red-400">❤️</span> usando Tailwind CSS
      </p>
    </div>

  </div>

</body>
</html>
```

### Conceptos Clave de Tailwind Usados

**1. Gradiente de Fondo:**
```html
<body class="bg-gradient-to-br from-purple-500 via-pink-500 to-red-500">
```

**2. Efecto Glassmorphism:**
```html
<a class="bg-white/90 backdrop-blur-sm">
```

**3. Efectos Hover:**
```html
<a class="hover:bg-white hover:shadow-xl hover:-translate-y-1 transform transition-all duration-200">
```

**4. Group Hover:**
```html
<a class="group">
  <svg class="group-hover:translate-x-1 transition">
</a>
```

**5. Contenedor Responsive:**
```html
<div class="max-w-md mx-auto px-4 py-8">
```

---

## 18. Rendimiento y Optimización

### Configuración de PurgeCSS

Tailwind elimina automáticamente los estilos sin usar en producción:

```javascript
// tailwind.config.js
module.exports = {
  content: [
    './src/**/*.{html,js,jsx,ts,tsx}',
    './public/**/*.html',
  ],
  // Tailwind escaneará estos archivos y solo incluirá las clases usadas
}
```

### Comparación de Tamaño de Archivo

**Desarrollo:**
- Tailwind CSS completo: ~3MB (todas las utilidades)
- No optimizado para producción

**Producción (con PurgeCSS):**
- Tamaño típico: 5-10KB (gzipped)
- Solo incluye las clases que realmente usas
- 99% más pequeño que el build de desarrollo

### Build para Producción

```bash
# Build con minificación
npm run build

# O con la CLI de Tailwind
npx tailwindcss -i ./src/input.css -o ./dist/output.css --minify
```

### Consejos de Optimización

**1. Usa la Configuración de Content:**
```javascript
module.exports = {
  content: [
    './src/**/*.{js,jsx,ts,tsx}', // React
    './pages/**/*.{js,ts,jsx,tsx}', // Next.js
    './components/**/*.{js,ts,jsx,tsx}',
    './*.html', // Archivos HTML
  ],
}
```

**2. Evita los Nombres de Clase Dinámicos:**
```html
<!-- ❌ Mal: Las clases no se detectarán -->
<div class="text-{{ userColor }}">

<!-- ✅ Bien: Usa nombres de clase completos -->
<div class="{{ isActive ? 'text-blue-500' : 'text-gray-500' }}">
```

**3. Añade Clases Importantes al Safelist:**
```javascript
module.exports = {
  safelist: [
    'bg-red-500',
    'bg-blue-500',
    {
      pattern: /bg-(red|green|blue)-(400|500|600)/,
    },
  ],
}
```

**4. Rendimiento en v4:**
- Motor Lightning CSS (basado en Rust) para una velocidad extrema
- Builds incrementales en microsegundos
- Todas las utilidades generadas bajo demanda
- No se necesita configuración para la optimización del rendimiento

---

## 19. Nuevas Funcionalidades de Tailwind CSS 4

**Fecha de Lanzamiento:** 22 de enero de 2025

Tailwind CSS v4.0 es una reescritura mayor del framework, optimizada para el rendimiento y construida sobre funcionalidades modernas de CSS. Esta versión representa la mayor actualización de Tailwind desde su lanzamiento inicial.

### 🚀 Cambios Principales

**1. Rendimiento Increíble:**
- **Builds completos:** Hasta 5x más rápidos que v3
- **Builds incrementales:** Más de 100x más rápidos (medidos en microsegundos)
- Nuevo motor de alto rendimiento escrito en Rust vía Lightning CSS
- Compilación casi instantánea para proyectos grandes

**2. Configuración Simplificada:**
- **Cero configuración** requerida para empezar
- **Menos dependencias** (no se necesitan plugins de PostCSS en muchos casos)
- **Una sola línea de CSS:** Solo `@import "tailwindcss";` en tu archivo CSS
- No se requiere `tailwind.config.js` para el uso básico

**3. Base de CSS Moderna:**
- **CSS Cascade Layers:** Mejor control sobre la especificidad
- **@property:** Propiedades personalizadas registradas con comprobación de tipos
- **color-mix():** Manipulación de color nativa de CSS
- **Amplio gamut de color:** Soporte de espacios de color P3 y Rec2020
- **Anidamiento nativo de CSS:** No se requiere preprocesador

**4. Nuevo Sistema de Configuración:**
- Configuración basada en CSS usando la directiva `@theme`
- Sintaxis más limpia e intuitiva
- Mejor soporte de IntelliSense
- Actualizaciones del tema en vivo sin recompilar

### 🎨 Nuevas Funcionalidades

**1. CSS Container Queries (Soporte Nativo):**

```html
<!-- Contenedor -->
<div class="@container">
  <!-- Responde al tamaño del contenedor, no del viewport -->
  <div class="@md:text-lg @lg:text-xl">
    Responsive to container width
  </div>
</div>

<!-- Contenedores con nombre -->
<div class="@container/main">
  <div class="@lg/main:flex">
    Content
  </div>
</div>
```

**2. Valores Arbitrarios Mejorados:**

```html
<!-- Usar valores del tema en cálculos -->
<div class="w-[calc(100%-theme(spacing.4))]">
  Access theme values directly
</div>

<!-- Type hints para mejor IntelliSense -->
<div class="bg-[color:var(--my-color)]">
  Better autocomplete
</div>

<!-- Soporte de variables CSS -->
<div class="text-[var(--brand-color)]">
  Use CSS variables anywhere
</div>
```

**3. Soporte de Amplio Gamut de Color:**

```html
<!-- Espacio de color P3 -->
<div class="bg-[color(display-p3 1 0 0)]">
  Vivid P3 red
</div>

<!-- Espacio de color oklch -->
<div class="bg-[oklch(0.7_0.15_180)]">
  Modern color syntax
</div>
```

**4. Variantes de Modo Oscuro Integradas:**

```html
<!-- Modo oscuro mejorado -->
<div class="bg-white dark:bg-slate-900">
  <!-- Preferencia del sistema o toggle manual -->
</div>

<!-- Modo oscuro con clases (por defecto en v4) -->
<html class="dark">
  <!-- Todas las variantes dark: se activan -->
</html>
```

**5. Anidamiento Nativo de CSS:**

```css
/* No se necesita preprocesador */
.card {
  @apply rounded-lg shadow;

  & h2 {
    @apply text-xl font-bold;
  }

  & p {
    @apply text-gray-600;
  }
}
```

### ⚙️ Cambios de Configuración (v4 vs v3)

**Configuración de v3 (JavaScript):**
```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: '#3b82f6'
      }
    }
  }
}
```

**Configuración de v4 (basada en CSS):**
```css
/* styles.css */
@import "tailwindcss";

@theme {
  --color-primary: #3b82f6;
  --font-display: "Inter", sans-serif;
  --breakpoint-2xl: 1400px;
}
```

### 🔄 Migración de v3 a v4

**Cambios que Rompen Compatibilidad:**
- La configuración del plugin de PostCSS cambió
- Las directivas `@tailwind` reemplazadas por `@import "tailwindcss"`
- La configuración se movió de JS a CSS (opcional, pero recomendado)
- Algunos nombres de clase de utilidad actualizados por consistencia

**Pasos de Migración:**
```bash
# 1. Actualizar las dependencias
npm install tailwindcss@latest

# 2. Actualizar el archivo CSS
# Antiguo (v3):
@tailwind base;
@tailwind components;
@tailwind utilities;

# Nuevo (v4):
@import "tailwindcss";

# 3. (Opcional) Convertir la config a basada en CSS
# Mueve los valores del tema de tailwind.config.js a @theme en el CSS
```

### 📊 Comparación de Rendimiento

| Métrica | v3 | v4 | Mejora |
|--------|----|----|-------------|
| Tiempo de build completo | ~500ms | ~100ms | 5x más rápido |
| Build incremental | ~50ms | <1ms | 100x+ más rápido |
| Tamaño del archivo CSS | Igual | Igual | Igual |
| Uso de memoria | Mayor | Menor | Reducido |

### 🔗 Recursos

- [Anuncio Oficial de v4.0](https://tailwindcss.com/blog/tailwindcss-v4)
- [Documentación de v4](https://tailwindcss.com/docs)
- [Guía de Migración](https://tailwindcss.com/docs/upgrade-guide)
- [Release de GitHub](https://github.com/tailwindlabs/tailwindcss/releases)

---

## 20. Buenas Prácticas

### Extracción de Componentes

Cuando veas repetición, extrae componentes:

**Antes:**
```html
<button class="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600">
  Button 1
</button>
<button class="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600">
  Button 2
</button>
```

**Después (React):**
```jsx
function Button({ children }) {
  return (
    <button className="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600">
      {children}
    </button>
  );
}
```

### Usa @apply con Moderación

Usa `@apply` solo para patrones que se reutilizan con frecuencia:

```css
/* ✅ Buen caso de uso */
@layer components {
  .btn-primary {
    @apply bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600 transition;
  }
}

/* ❌ Evítalo para estilos de un solo uso */
@layer components {
  .my-unique-card {
    @apply bg-white p-4 shadow; /* Simplemente usa utilidades en el HTML */
  }
}
```

### Organiza las Clases de Forma Lógica

**Orden recomendado:**
1. Layout (display, position, flex/grid)
2. Modelo de caja (width, height, padding, margin)
3. Tipografía (font, text)
4. Visual (background, border, shadow)
5. Varios (cursor, transitions)

```html
<div class="
  flex items-center justify-between
  w-full max-w-4xl mx-auto p-4
  text-lg font-semibold
  bg-white border border-gray-200 rounded-lg shadow-md
  hover:shadow-lg transition
">
```

### Diseño Responsive Mobile-First

```html
<!-- ✅ Bien: Mobile-first -->
<div class="text-sm md:text-base lg:text-lg">
  <!-- La base es móvil, escala hacia arriba -->
</div>

<!-- ❌ Evitar: Desktop-first -->
<div class="text-lg md:text-base sm:text-sm">
  <!-- Más difícil de mantener -->
</div>
```

### Convenciones de Nombrado Consistentes

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        'brand-primary': '#1da1f2',
        'brand-secondary': '#14171a',
        // Usa nombres descriptivos y consistentes
      }
    }
  }
}
```

### Accesibilidad

```html
<!-- Incluye siempre estados de foco -->
<button class="
  bg-blue-500
  hover:bg-blue-600
  focus:outline-none
  focus:ring-4
  focus:ring-blue-300
">
  Accessible button
</button>

<!-- Contraste adecuado -->
<div class="bg-gray-900 text-white"> <!-- Buen contraste -->
  Content
</div>
```

### Consejos de Rendimiento

**1. Limita los valores arbitrarios:**
```html
<!-- ❌ Evítalo cuando sea posible -->
<div class="w-[347px]">

<!-- ✅ Usa valores del tema -->
<div class="w-80"> <!-- 20rem = 320px -->
```

**2. Reutiliza las clases:**
```html
<!-- ✅ Las clases se reutilizan -->
<div class="bg-blue-500"></div>
<div class="bg-blue-500"></div>

<!-- El tamaño del archivo no aumenta -->
```

**3. Minimiza el anidamiento:**
```html
<!-- ✅ Estructura plana -->
<div class="p-4">
  <h1 class="text-2xl">Title</h1>
</div>

<!-- ❌ Envoltorio innecesario -->
<div class="p-4">
  <div class="container">
    <div class="wrapper">
      <h1 class="text-2xl">Title</h1>
    </div>
  </div>
</div>
```

---

## 21. Buenas Prácticas de Tailwind en Profundidad

Esta sección cubre buenas prácticas avanzadas de aplicaciones de producción del mundo real, incluyendo apps bancarias empresariales y proyectos profesionales.

### Cuándo Usar Tailwind

**✅ Perfecto para:**
- Proyectos personales y side projects
- Landing pages
- Aplicaciones simples a medianas
- Aplicaciones personalizadas donde tú eres dueño del diseño
- Iteración y prototipado rápidos

**⚠️ Considera alternativas para:**
- Aplicaciones empresariales grandes con sistemas de diseño estrictos
- Proyectos con catálogos de componentes existentes
- Aplicaciones con requisitos de diseño muy específicos y rígidos
- Equipos ya invertidos en otras soluciones de CSS

### Contexto Profesional

Tailwind destaca cuando:
- Necesitas flexibilidad en el diseño
- Construyes desde cero
- Creas interfaces únicas y personalizadas
- Trabajas en frameworks basados en componentes (React, Vue, Angular)
- La velocidad y la productividad son prioridades

---

## 22. Ordenamiento de Clases y Sistema de Prioridad

### Entendiendo el Sistema de Prioridad de Tailwind

Las clases de Tailwind siguen las reglas de la cascada de CSS, lo que significa que **el orden importa**. La última clase de la misma propiedad gana.

**Ejemplo de Conflictos de Prioridad:**

```html
<!-- ❌ Problema: ¿Qué color gana? -->
<h1 className="text-white text-black">
  Which color am I?
</h1>

<!-- Resultado: text-black gana (es el último en la cascada) -->
```

**Cambia el orden:**
```html
<h1 className="text-black text-white">
  Which color am I?
</h1>

<!-- Resultado: text-white gana (es el último en la cascada) -->
```

### Prioridad de Tono de Color

Incluso dentro de la misma familia de color, la especificidad importa:

```html
<!-- text-red-100 gana (tono más específico) -->
<p className="text-red-50 text-black text-red-100">
  Red 100 color
</p>

<!-- Cambia el orden -->
<p className="text-red-100 text-red-50">
  Red 50 wins now
</p>
```

### Sistema de Prioridad Interno

Tailwind tiene un sistema de prioridad interno para utilidades similares:

```jsx
// text-red-100 tiene mayor prioridad que text-red-50
<div className="text-red-50 text-black text-red-100">
  // Red 100 gana
</div>

// Incluso al principio, el tono más alto gana
<div className="text-red-100 text-red-50 text-black">
  // Sigue siendo red-100
</div>
```

### Orden de Clases Recomendado

**El ordenamiento lógico previene conflictos:**

1. **Layout** - Propiedades de display, position, flex/grid
2. **Display** - Block, inline, flex, grid
3. **Spacing** - Margin, padding
4. **Borders** - Grosor, color, radius del borde
5. **Colors** - Colores de fondo y texto
6. **Typography** - Tamaño de fuente, peso, altura de línea
7. **Effects** - Sombras, opacidad, transiciones

**Ejemplo:**
```html
<div class="
  flex items-center justify-between
  w-full max-w-4xl mx-auto
  p-4 m-2
  border border-gray-300 rounded-lg
  bg-white text-gray-900
  text-base font-semibold
  shadow-md hover:shadow-lg
  transition-all duration-300
">
  Properly ordered classes
</div>
```

### Depuración de Prioridad

**Al depurar problemas de prioridad:**

```html
<!-- Usa las DevTools del navegador -->
<!-- Inspecciona el elemento y comprueba los estilos calculados -->
<!-- Ve qué clases están siendo sobrescritas -->

<!-- Fuerza un estado hover en las DevTools para probar -->
<button class="bg-blue-500 hover:bg-blue-700">
  Inspect me with :hov in DevTools
</button>
```

---

## 23. Configuración de Proyecto Vite + React

### Configuración Rápida con Vite (Tailwind v4)

**Crear un nuevo proyecto Vite:**

```bash
# Usando npm
npm create vite@latest

# Nombre del proyecto
tailwind-best-practices

# Selecciona React
# Selecciona TypeScript

# Navega al proyecto
cd tailwind-best-practices

# Instala las dependencias
npm install
```

**Instalar Tailwind v4:**

```bash
# Instalar Tailwind v4 (¡simplificado!)
npm install -D tailwindcss@latest

# ¡No se necesita postcss.config.js en la mayoría de los casos!
# Vite maneja los imports de CSS automáticamente
```

### Archivos de Configuración (Opcionales en v4)

**tailwind.config.js (OPCIONAL):**

Solo se necesita si quieres personalizar las rutas de contenido:

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  // la configuración del tema se movió a CSS en v4
}
```

**Nota:** ¡En v4, la detección de contenido es automática para los patrones comunes, así que puede que no necesites este archivo en absoluto!

### Por Qué la Configuración es Más Simple en v4

**Cambios de Tailwind v4:**
- ✅ PostCSS ahora es opcional (integrado directamente)
- ✅ Cero configuración en la mayoría de los proyectos
- ✅ Vite procesa automáticamente `@import "tailwindcss"`
- ✅ Builds más rápidos (motor Lightning CSS)
- ✅ No se necesita `postcss.config.js`
- ✅ Configuración del tema en CSS, no en JavaScript

**Si aún necesitas PostCSS (para otros plugins):**

`postcss.config.js`:
```javascript
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {}, // Opcional en v4
  },
}
```

### Configuración de CSS

**src/index.css (v4 - Simplificado):**

```css
/* Sintaxis moderna de v4 - ¡solo una línea! */
@import "tailwindcss";

/* Opcional: Tema personalizado en CSS */
@theme {
  --color-primary: #3b82f6;
  --color-secondary: #8b5cf6;
  --font-display: "Inter", sans-serif;
}
```

**Alternativa: Sintaxis tradicional (aún soportada):**

```css
/* la sintaxis de v3 aún funciona en v4 */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

**Qué hacen estas directivas:**
- `@import "tailwindcss"` (v4) - Importa todo con CSS moderno
- `@tailwind base` (v3) - Estilos de reset, tipografía base
- `@tailwind components` (v3) - Clases de componente (si usas @apply)
- `@tailwind utilities` (v3) - Todas las clases de utilidad

### Importar en main.tsx

```tsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.tsx'
import './index.css' // Importar los estilos de Tailwind

ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
)
```

### Ejecutar el Servidor de Desarrollo

```bash
# Iniciar el servidor de desarrollo de Vite
npm run dev

# Visita http://localhost:5173
```

### Verificar la Instalación

```tsx
// App.tsx
function App() {
  return (
    <div className="min-h-screen bg-gray-100 flex items-center justify-center">
      <h1 className="text-4xl font-bold text-blue-600">
        Tailwind is working!
      </h1>
    </div>
  )
}

export default App
```

---

## 24. Extensión de Tema Personalizado (Práctico)

### Extendiendo el Tema por Defecto

En lugar de poner colores fijos, crea un tema personalizado en `tailwind.config.js`:

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: ["./src/**/*.{js,jsx,ts,tsx}"],
  theme: {
    extend: {
      colors: {
        primary: {
          50: '#f0f9ff',
          100: '#e0f2fe',
          200: '#bae6fd',
          300: '#7dd3fc',
          400: '#38bdf8',
          500: '#0ea5e9',
          600: '#0284c7',
          700: '#0369a1',
          800: '#075985',
          900: '#0c4a6e',
        },
        secondary: {
          50: '#faf5ff',
          100: '#f3e8ff',
          200: '#e9d5ff',
          300: '#d8b4fe',
          400: '#c084fc',
          500: '#a855f7',
          600: '#9333ea',
          700: '#7e22ce',
          800: '#6b21a8',
          900: '#581c87',
        }
      }
    }
  },
  plugins: [],
}
```

### Usando Colores del Tema Personalizado

**Antes (fijos):**
```html
<p class="text-blue-500">Blue text</p>
<p class="text-purple-600">Purple text</p>
```

**Después (colores del tema):**
```html
<p class="text-primary-500">Primary brand color</p>
<p class="text-secondary-600">Secondary brand color</p>
```

### Autocompletado de IntelliSense

Después de añadir colores personalizados, el IntelliSense de VSCode los mostrará:

```html
<!-- Escribe "text-primary" y ve el autocompletado -->
<p class="text-primary-">
  <!-- Muestra: 50, 100, 200, 300, 400, 500, 600, 700, 800, 900 -->
</p>

<!-- Pasa el cursor sobre la clase para ver el valor hex -->
<p class="text-primary-500">
  <!-- Al pasar el cursor muestra: #0ea5e9 -->
</p>
```

### Espaciado Personalizado

```javascript
export default {
  theme: {
    extend: {
      spacing: {
        '72': '18rem',
        '84': '21rem',
        '96': '24rem',
        '128': '32rem',
      }
    }
  }
}
```

Uso:
```html
<div class="w-72 h-84 p-96 m-128">
  Custom spacing values
</div>
```

### Fuentes Personalizadas

```javascript
export default {
  theme: {
    extend: {
      fontFamily: {
        'display': ['Poppins', 'sans-serif'],
        'body': ['Inter', 'sans-serif'],
      }
    }
  }
}
```

Uso:
```html
<h1 class="font-display text-4xl">Display Font</h1>
<p class="font-body text-base">Body Font</p>
```

---

## 25. Variantes para Estilos Dinámicos (Avanzado)

### Entendiendo las Variantes

Las variantes son modificadores que aplican estilos condicionalmente según el estado o el contexto.

### Variante Hover con Transiciones

```html
<!-- Hover con cambio de color -->
<h1 class="text-primary-500 hover:text-secondary-100">
  Hover me to change color
</h1>

<!-- Hover con opacidad -->
<div class="
  text-primary-500
  text-opacity-100
  hover:text-opacity-20
  transition-opacity
  duration-300
">
  Smooth opacity transition
</div>
```

### Combinando Múltiples Variantes

```html
<!-- Hover + Transición + Opacidad -->
<div class="
  text-primary-500
  text-opacity-100
  hover:text-secondary-100
  hover:text-opacity-20
  transition-colors
  duration-300
">
  Multiple effects on hover
</div>
```

### Variantes Focus

```html
<!-- Focus con múltiples estados -->
<input class="
  border border-gray-300
  focus:border-blue-500
  focus:ring-2
  focus:ring-blue-200
  focus:outline-none
  sm:text-sm
">
```

### Variantes Responsive

```html
<!-- Distintos estilos en distintos breakpoints -->
<div class="
  text-primary-500
  sm:text-secondary-100
  md:text-secondary-200
  lg:text-primary-500
">
  Color changes with screen size
</div>
```

### Propiedades de Transición

```html
<!-- Transición de propiedades específicas -->
<button class="
  bg-blue-500
  hover:bg-blue-600
  transition-colors
  duration-300
">
  Only color transitions
</button>

<!-- Transición de transform -->
<div class="
  transform
  hover:scale-105
  transition-transform
  duration-200
">
  Scales on hover
</div>

<!-- Transición de todo -->
<div class="
  bg-blue-500
  hover:bg-blue-600
  hover:scale-105
  transition-all
  duration-300
">
  All properties transition
</div>
```

### Duraciones de Animación

```html
<!-- Rápida: 75ms -->
<div class="transition duration-75"></div>

<!-- Por defecto: 150ms -->
<div class="transition duration-150"></div>

<!-- Media: 300ms -->
<div class="transition duration-300"></div>

<!-- Lenta: 500ms -->
<div class="transition duration-500"></div>

<!-- Muy lenta: 1000ms -->
<div class="transition duration-1000"></div>
```

---

## 26. La Directiva @apply - Cuándo Sí y Cuándo No

### ¿Qué es @apply?

La directiva `@apply` te permite extraer utilidades de Tailwind en clases CSS personalizadas.

```css
/* src/index.css */
@tailwind base;
@tailwind components;
@tailwind utilities;

/* Componentes personalizados */
@layer components {
  .btn-primary {
    @apply bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600 transition;
  }
}
```

### Cuándo Usar @apply

**✅ Usa @apply para:**

**1. Componentes del Sistema de Diseño:**
```css
@layer components {
  .container {
    @apply min-h-screen bg-gray-900 px-4 py-12 sm:px-6 lg:px-8;
  }

  .page-content {
    @apply max-w-7xl mx-auto;
  }

  .card {
    @apply bg-gray-800 rounded-lg shadow-lg overflow-hidden
           hover:shadow-xl transform hover:scale-105
           transition-all duration-300;
  }
}
```

**2. Patrones que se Repiten con Frecuencia:**
```css
@layer components {
  .title {
    @apply text-white font-bold mb-2;
  }

  .subtitle {
    @apply text-gray-300 text-lg mb-3;
  }

  .description {
    @apply text-gray-400 text-sm;
  }
}
```

**3. Elementos Sin Acceso Fácil al HTML:**
```css
/* Estilizar elementos que no puedes modificar fácilmente */
@layer components {
  .prose h1 {
    @apply text-4xl font-bold text-gray-900 mb-4;
  }

  .prose p {
    @apply text-base text-gray-700 mb-4;
  }
}
```

### Cuándo NO Usar @apply

**❌ No uses @apply para:**

**1. Estilos de un Solo Uso:**
```html
<!-- ❌ Mal: Crear una clase para un solo uso -->
<!-- CSS: .my-special-div { @apply bg-white p-4 shadow; } -->
<div class="my-special-div"></div>

<!-- ✅ Bien: Simplemente usa utilidades -->
<div class="bg-white p-4 shadow"></div>
```

**2. Estilos Específicos de Componente en React/Vue:**
```jsx
// ❌ Mal: @apply en un archivo CSS
// .header-title { @apply text-2xl font-bold text-blue-500; }

// ✅ Bien: Extraer a un componente
function Header() {
  return (
    <h1 className="text-2xl font-bold text-blue-500">
      Title
    </h1>
  )
}
```

**3. Estilos que Cambian con Frecuencia:**
```css
/* ❌ Mal: Requiere cambios en el archivo CSS */
.hero-section {
  @apply bg-blue-500 text-white p-8;
}

/* ✅ Bien: Cambia directamente en el HTML */
<section className="bg-blue-500 text-white p-8">
```

### El Problema de la Prioridad

**⚠️ Advertencia:** Las clases de `@apply` pierden el sistema de prioridad inline de Tailwind:

```html
<!-- Con utilidades inline, la última gana -->
<div class="text-red-500 text-blue-500">
  Blue wins (predecible)
</div>

<!-- Con @apply, aplican las reglas de la cascada de CSS -->
<div class="custom-class text-blue-500">
  Depends on CSS order (impredecible)
</div>
```

### Reglas de Buenas Prácticas

**Reglas para @apply:**

1. **Úsalo solo para componentes verdaderamente reutilizables**
2. **Evítalo para estilos de un solo uso**
3. **Prefiere componentes de React/Vue sobre @apply**
4. **Úsalo para elementos del sistema de diseño**
5. **Documenta las clases de @apply con claridad**

**Ejemplo de buen uso de @apply:**

```css
/* TW Elements - Reutilizable en toda la app */
@layer components {
  /* Layout de Página */
  .page-container {
    @apply min-h-screen bg-gray-900 px-4 py-12 sm:px-6 lg:px-8;
  }

  .page-content {
    @apply max-w-7xl mx-auto;
  }

  /* Sistema de Tarjetas */
  .card {
    @apply bg-gray-800 rounded-lg shadow-lg overflow-hidden
           hover:shadow-xl transition-all duration-300;
  }

  .card-image-container {
    @apply relative h-48 overflow-hidden;
  }

  .card-overlay {
    @apply absolute inset-0 bg-black bg-opacity-40
           flex items-center justify-center
           opacity-0 hover:opacity-100
           transition-opacity duration-300;
  }

  .card-content {
    @apply p-6;
  }

  /* Sistema de Tipografía */
  .title {
    @apply text-white font-bold mb-2;
  }

  .subtitle {
    @apply text-gray-300 text-lg mb-3;
  }

  .description {
    @apply text-gray-400 text-sm;
  }
}
```

---

## 27. Técnicas de Edición Multi-Cursor

### ¿Por Qué Multi-Cursor en Lugar de @apply?

El equipo de Tailwind recomienda usar la edición multi-cursor para cambiar utilidades en varios elementos en lugar de crear clases @apply.

### Funcionalidades Multi-Cursor de VSCode

**1. Seleccionar Todas las Ocurrencias:**

```html
<!-- Selecciona "text-primary-500" y presiona Cmd+Shift+L (Mac) o Ctrl+Shift+L (Windows) -->
<div class="text-primary-500">Item 1</div>
<div class="text-primary-500">Item 2</div>
<div class="text-primary-500">Item 3</div>

<!-- Todas las instancias seleccionadas, escribe para reemplazar todas -->
<div class="text-secondary-100">Item 1</div>
<div class="text-secondary-100">Item 2</div>
<div class="text-secondary-100">Item 3</div>
```

**2. Buscar y Reemplazar:**

```
Cmd+F (Mac) o Ctrl+F (Windows)
Buscar: text-primary-500
Reemplazar: text-secondary-100
Reemplazar Todo
```

**3. Añadir Cursor Arriba/Abajo:**

```
Cmd+Option+Up/Down (Mac)
Ctrl+Alt+Up/Down (Windows)
```

**4. Seleccionar la Siguiente Ocurrencia:**

```
Cmd+D (Mac) o Ctrl+D (Windows)
- Selecciona la palabra
- Presiona Cmd+D para seleccionar la siguiente ocurrencia
- Sigue presionando para seleccionar más
- Edita todas a la vez
```

### Extraer al Contenedor Padre

En lugar de crear clases, extrae los estilos comunes al padre:

**❌ Antes (repetitivo):**
```html
<div>
  <h1 class="text-primary-500 font-bold">Title 1</h1>
  <h1 class="text-primary-500 font-bold">Title 2</h1>
  <h1 class="text-primary-500 font-bold">Title 3</h1>
</div>
```

**✅ Después (extraído al padre):**
```html
<div class="text-primary-500 font-bold">
  <h1>Title 1</h1>
  <h1>Title 2</h1>
  <h1>Title 3</h1>
</div>
```

### Extracción de Componentes (React)

**❌ No crees clases @apply:**
```css
/* Mal enfoque */
.game-title {
  @apply text-primary-500 font-bold mb-2;
}
```

**✅ Extrae a un componente de React:**
```tsx
// Buen enfoque
interface TitleProps {
  children: React.ReactNode;
}

function GameTitle({ children }: TitleProps) {
  return (
    <h3 className="text-primary-500 font-bold mb-2">
      {children}
    </h3>
  );
}

// Uso
<GameTitle>The Witcher 3</GameTitle>
<GameTitle>Cyberpunk 2077</GameTitle>
```

---

## 28. Proyecto Práctico: Cuadrícula de Videojuegos

Esta sección recorre la construcción de una aplicación completa de cuadrícula de videojuegos usando todas las buenas prácticas cubiertas.

### Estructura del Proyecto

```
src/
├── videogames/
│   ├── VideoGameGrid.tsx
│   ├── GameItem.tsx
│   └── videogame.ts
├── App.tsx
├── index.css
└── main.tsx
```

### Definiciones de Tipos

**src/videogames/videogame.ts:**

```typescript
export interface VideoGame {
  id: string;
  title: string;
  subtitle: string;
  description: string;
  image: string;
}
```

### Datos de Prueba (Mock)

**src/App.tsx:**

```tsx
import VideoGameGrid from './videogames/VideoGameGrid';
import { VideoGame } from './videogames/videogame';

const games: VideoGame[] = [
  {
    id: '1',
    title: 'The Witcher 3: Wild Hunt',
    subtitle: 'CD Projekt Red',
    description: 'An epic open-world RPG filled with danger and adventure.',
    image: 'https://images.igdb.com/igdb/image/upload/t_cover_big/co1wyy.jpg'
  },
  {
    id: '2',
    title: 'Cyberpunk 2077',
    subtitle: 'CD Projekt Red',
    description: 'An open-world action-adventure set in Night City.',
    image: 'https://images.igdb.com/igdb/image/upload/t_cover_big/co2qkt.jpg'
  },
  {
    id: '3',
    title: 'Red Dead Redemption 2',
    subtitle: 'Rockstar Games',
    description: 'An epic tale of life in America\'s unforgiving heartland.',
    image: 'https://images.igdb.com/igdb/image/upload/t_cover_big/co1q1f.jpg'
  },
  {
    id: '4',
    title: 'Elden Ring',
    subtitle: 'FromSoftware',
    description: 'Rise, Tarnished, and be guided by grace.',
    image: 'https://images.igdb.com/igdb/image/upload/t_cover_big/co4jni.jpg'
  },
];

function App() {
  return <VideoGameGrid games={games} />;
}

export default App;
```

### Componente VideoGameGrid

**src/videogames/VideoGameGrid.tsx:**

```tsx
import { VideoGame } from './videogame';
import GameItem from './GameItem';

interface Props {
  games: VideoGame[];
}

function VideoGameGrid({ games }: Props) {
  return (
    <div className="page-container">
      <div className="page-content">
        <h1 className="title text-4xl mb-8">Featured Games</h1>

        <div className="grid-container">
          {games.map((game) => (
            <GameItem
              key={game.id}
              title={game.title}
              subtitle={game.subtitle}
              description={game.description}
              image={game.image}
            />
          ))}
        </div>
      </div>
    </div>
  );
}

export default VideoGameGrid;
```

### Componente GameItem

**src/videogames/GameItem.tsx:**

```tsx
import { Gamepad2 } from 'lucide-react';
import { VideoGame } from './videogame';

type Props = Omit<VideoGame, 'id'>;

function GameItem({ title, subtitle, description, image }: Props) {
  return (
    <div className="card">
      <div className="card-image-container">
        <img
          src={image}
          alt={title}
          className="w-full h-full object-cover object-center"
        />

        <div className="card-overlay">
          <Gamepad2 className="card-icon" />
        </div>
      </div>

      <div className="card-content">
        <h3 className="title">{title}</h3>
        <h4 className="subtitle">{subtitle}</h4>
        <p className="description">{description}</p>
      </div>
    </div>
  );
}

export default GameItem;
```

### Estilos Personalizados con @apply

**src/index.css:**

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

/* TW Elements - Componentes reutilizables del sistema de diseño */
@layer components {
  /* Layout de Página */
  .page-container {
    @apply min-h-screen bg-gray-900 px-4 py-12 sm:px-6 lg:px-8;
  }

  .page-content {
    @apply max-w-7xl mx-auto;
  }

  /* Sistema de Grid */
  .grid-container {
    @apply grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6;
  }

  /* Componente de Tarjeta */
  .card {
    @apply bg-gray-800 rounded-lg shadow-lg overflow-hidden
           hover:shadow-xl transform hover:scale-105
           transition-all duration-300;
  }

  .card-image-container {
    @apply relative h-48 overflow-hidden;
  }

  .card-overlay {
    @apply absolute inset-0 bg-black bg-opacity-40
           flex items-center justify-center
           opacity-0 hover:opacity-100
           transition-opacity duration-300;
  }

  .card-icon {
    @apply text-4xl text-white;
  }

  .card-content {
    @apply p-6;
  }

  /* Sistema de Tipografía */
  .title {
    @apply text-white font-bold mb-2;
  }

  .subtitle {
    @apply text-gray-300 text-lg mb-3;
  }

  .description {
    @apply text-gray-400 text-sm;
  }
}
```

### Funcionalidades Clave Demostradas

**1. Grid Responsive:**
- 1 columna en móvil
- 2 columnas en pantallas pequeñas (sm:)
- 3 columnas en pantallas medianas (md:)
- 4 columnas en pantallas grandes (lg:)

**2. Efectos Hover de la Tarjeta:**
- Transform de escala en hover
- Aumento de la intensidad de la sombra
- Transiciones suaves

**3. Superposición de Imagen:**
- La superposición aparece en hover
- Icono centrado con flexbox
- Transición de opacidad para un efecto suave

**4. Sistema de Diseño:**
- Tipografía consistente (title, subtitle, description)
- Componentes de tarjeta reutilizables
- Contenedores de layout centralizados

**5. Integración con TypeScript:**
- Props con seguridad de tipos usando interfaces
- Tipo de utilidad Omit para las props de GameItem
- Tipado adecuado en todo momento

---

## 29. Estrategias de Extracción de Componentes

### Cuándo Extraer Componentes

**Extrae cuando veas:**

1. **Repetición** - El mismo patrón usado 3+ veces
2. **Complejidad** - Más de 10-15 clases de utilidad
3. **Reutilización** - Patrón usado en distintas páginas
4. **Mantenibilidad** - Los cambios deberían suceder en un solo lugar

### Niveles de Extracción

**Nivel 1: Utilidades Inline (Por Defecto)**

```tsx
// Empieza aquí - simple, claro, rápido
<button className="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600">
  Click me
</button>
```

**Nivel 2: Extracción al Contenedor Padre**

```tsx
// Cuando varios elementos comparten estilos
<div className="text-primary-500 font-bold">
  <h1>Title 1</h1>
  <h2>Title 2</h2>
  <h3>Title 3</h3>
</div>
```

**Nivel 3: Extracción a un Componente de React**

```tsx
// Para patrones que se reutilizan con frecuencia
interface ButtonProps {
  children: React.ReactNode;
  onClick?: () => void;
}

function PrimaryButton({ children, onClick }: ButtonProps) {
  return (
    <button
      onClick={onClick}
      className="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600 transition"
    >
      {children}
    </button>
  );
}
```

**Nivel 4: Clases CSS con @apply**

```css
/* Solo para elementos del sistema de diseño */
@layer components {
  .btn-primary {
    @apply bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600 transition;
  }
}
```

### Árbol de Decisión

```
¿El patrón se usa más de una vez?
├─ No → Usa utilidades inline
└─ Sí → ¿Se usa en el mismo padre?
    ├─ Sí → Extrae al contenedor padre
    └─ No → ¿Es una app de React/Vue?
        ├─ Sí → Crea un componente
        └─ No → Considera @apply (con cuidado)
```

### Ejemplo: Evolución de un Botón

**Etapa 1: Inline (Primer uso)**

```tsx
<button className="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600">
  Submit
</button>
```

**Etapa 2: Múltiples Botones (Aún inline)**

```tsx
<button className="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600">
  Submit
</button>
<button className="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600">
  Save
</button>
```

**Etapa 3: Extraer un Componente (3+ usos)**

```tsx
function Button({ children, variant = 'primary' }) {
  const variants = {
    primary: 'bg-blue-500 hover:bg-blue-600',
    secondary: 'bg-gray-500 hover:bg-gray-600',
  };

  return (
    <button className={`${variants[variant]} text-white px-4 py-2 rounded transition`}>
      {children}
    </button>
  );
}

// Uso
<Button>Submit</Button>
<Button variant="secondary">Cancel</Button>
```

### Patrón: Componentes Compuestos

```tsx
// Card.tsx
export function Card({ children, className = '' }) {
  return (
    <div className={`bg-white rounded-lg shadow-md overflow-hidden ${className}`}>
      {children}
    </div>
  );
}

Card.Image = function CardImage({ src, alt }) {
  return (
    <div className="relative h-48 overflow-hidden">
      <img src={src} alt={alt} className="w-full h-full object-cover" />
    </div>
  );
};

Card.Content = function CardContent({ children }) {
  return <div className="p-6">{children}</div>;
};

Card.Title = function CardTitle({ children }) {
  return <h3 className="text-xl font-bold mb-2">{children}</h3>;
};

// Uso
<Card>
  <Card.Image src="/game.jpg" alt="Game" />
  <Card.Content>
    <Card.Title>Game Title</Card.Title>
    <p>Description</p>
  </Card.Content>
</Card>
```

---

## 30. Hoja de Referencia y Recursos de Tailwind

### Hoja de Referencia Esencial

**Referencia Rápida:** [Tailwind CSS Cheat Sheet](https://nerdcave.com/tailwind-cheat-sheet)

Esta hoja de referencia incluye:
- Todas las clases de utilidad organizadas por categoría
- Ejemplos visuales de cada utilidad
- Funcionalidad de búsqueda
- Variantes responsive
- Variantes de estado
- Paletas de colores

### Usando la Hoja de Referencia

**Buscar utilidades:**
```
1. Abre la hoja de referencia
2. Ctrl+F o Cmd+F
3. Busca "margin" o "m-"
4. Ve todas las utilidades de margin
5. Haz clic para ver la salida CSS
```

**Ejemplos de búsquedas:**
- "transition" - Todas las utilidades de transición
- "flex" - Utilidades de flexbox
- "grid" - Utilidades de grid
- "text" - Utilidades de tipografía
- "bg" - Utilidades de fondo

### IntelliSense de VSCode

**Habilitar el autocompletado:**

1. Instala la extensión "Tailwind CSS IntelliSense"
2. El autocompletado aparece mientras escribes
3. Pasa el cursor para ver los valores CSS reales
4. Ve las vistas previas de color en línea

```tsx
// Escribe "m-" y ve todas las opciones de margin
<div className="m-">
  {/* El autocompletado muestra: m-0, m-1, m-2, m-px, m-auto, etc. */}
</div>

// Pasa el cursor sobre cualquier clase para ver el CSS
<div className="flex">
  {/* Al pasar el cursor muestra: display: flex; */}
</div>
```

### Referencia de Organización de Clases

**Orden de clases recomendado:**

```html
<div class="
  [1. Layout]
  flex items-center justify-between

  [2. Display]
  block relative

  [3. Spacing]
  w-full max-w-4xl mx-auto p-4 space-y-4

  [4. Borders]
  border border-gray-300 rounded-lg

  [5. Colors]
  bg-white text-gray-900

  [6. Typography]
  text-base font-semibold leading-tight

  [7. Effects]
  shadow-md hover:shadow-lg transition-all duration-300
">
```

### Recursos Oficiales

**Documentación:**
- [Documentación Oficial](https://tailwindcss.com/docs)
- [Playground](https://play.tailwindcss.com/)
- [Ejemplos de Componentes](https://tailwindui.com/components)

**Comunidad:**
- [GitHub Discussions](https://github.com/tailwindlabs/tailwindcss/discussions)
- [Servidor de Discord](https://tailwindcss.com/discord)
- [Twitter @tailwindcss](https://twitter.com/tailwindcss)

---

## 31. Herramientas de IA para el Desarrollo con Tailwind

### v0.dev de Vercel

**Qué es:**
- Generador de componentes de UI impulsado por IA
- Crea componentes de React con Tailwind CSS
- Genera código listo para producción

**Cómo usarlo:**

1. Visita [v0.dev](https://v0.dev)
2. Describe tu componente:
   ```
   "Create a video game grid with cards showing game title,
   subtitle, description, and image. Make it responsive
   with hover effects."
   ```
3. Revisa el código generado
4. Copia y personaliza

### Claude/ChatGPT para Tailwind

**Prompts efectivos:**

```
"Create a responsive navbar with Tailwind CSS that:
- Has logo on the left
- Navigation links in the center
- CTA button on the right
- Mobile hamburger menu
- Dark mode support"
```

**Ejemplo de generación de código:**

```
"Convert this CSS to Tailwind utilities:
.card {
  background: white;
  padding: 2rem;
  border-radius: 0.5rem;
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
}"
```

### Tailwind CSS IntelliSense

**Funcionalidades impulsadas por IA:**
- Autocompletado de clases
- Vista previa del CSS al pasar el cursor
- Linting y validación
- Visualización de color

### Buenas Prácticas con Herramientas de IA

**✅ Haz:**
- Usa la IA para el scaffolding inicial
- Genera la estructura de los componentes
- Obtén inspiración de diseño
- Aprende nuevos patrones

**❌ No hagas:**
- Copiar sin entender
- Saltarte el aprendizaje de los fundamentos
- Depender enteramente de la IA
- Ignorar la accesibilidad

### Ejemplo de Flujo de Trabajo

1. **Describe con IA:**
   ```
   "Create a game card component with image, title, and description"
   ```

2. **Revisa el código generado:**
   ```tsx
   // La IA genera el componente
   function GameCard({ title, image, description }) {
     return (
       <div className="bg-white rounded-lg shadow-md overflow-hidden">
         <img src={image} alt={title} className="w-full h-48 object-cover" />
         <div className="p-4">
           <h3 className="text-xl font-bold">{title}</h3>
           <p className="text-gray-600">{description}</p>
         </div>
       </div>
     );
   }
   ```

3. **Personaliza para que coincida con tu diseño:**
   ```tsx
   // Personaliza con tu tema
   function GameCard({ title, image, description }) {
     return (
       <div className="card"> {/* Usando clases @apply */}
         <div className="card-image-container">
           <img src={image} alt={title} className="w-full h-full object-cover" />
         </div>
         <div className="card-content">
           <h3 className="title">{title}</h3>
           <p className="description">{description}</p>
         </div>
       </div>
     );
   }
   ```

4. **Refina y optimiza:**
   - Añade efectos hover
   - Asegura el diseño responsive
   - Prueba la accesibilidad
   - Extrae patrones reutilizables

---

## Resumen

Tailwind CSS es un framework de CSS utility-first que revoluciona cómo escribimos estilos para aplicaciones web. En lugar de escribir clases CSS personalizadas y mantener hojas de estilo separadas, Tailwind proporciona clases de utilidad de bajo nivel que compones directamente en tu HTML.

### Puntos Clave

**1. Paradigma Utility-First:**
- Construir diseños complejos a partir de utilidades simples
- Sin fatiga de nombrado
- Sistema de diseño consistente
- Flujo de trabajo de desarrollo más rápido

**2. Responsive Mobile-First:**
- Modificadores responsive (`sm:`, `md:`, `lg:`, `xl:`, `2xl:`)
- Gestión fácil de breakpoints
- Consistente entre proyectos

**3. Variantes de Estado:**
- Estados hover, focus, active
- Group hover para interacciones padre-hijo
- Soporte de modo oscuro
- Pseudo-clases first, last, odd, even

**4. Rendimiento:**
- PurgeCSS elimina los estilos sin usar
- Los builds de producción suelen ser de 5-10KB
- Compilador JIT para builds instantáneos
- Tree-shaking para un tamaño óptimo

**5. Personalización:**
- Extender el tema en el archivo de config
- Colores, espaciado, fuentes personalizados
- Valores arbitrarios para casos únicos
- Plugins para utilidades adicionales

**6. Experiencia del Desarrollador:**
- Soporte de IntelliSense
- Autocompletado de clases
- Pasa el cursor para ver el CSS
- Excelente documentación

### Cuándo Usar Tailwind

**✅ Genial para:**
- Prototipado rápido
- Frameworks basados en componentes (React, Vue, Angular)
- Sistemas de diseño consistentes
- Equipos que iteran rápido
- Proyectos que requieren diseños personalizados

**❌ Puede no encajar:**
- Sitios estáticos simples (el CSS vanilla puede ser suficiente)
- Equipos resistentes al enfoque utility-first
- Proyectos con requisitos estrictos de componentes de diseño
- Proyectos legados con arquitectura CSS existente

### Checklist de Producción

- [ ] Configurar las rutas de `content` para PurgeCSS
- [ ] Habilitar la minificación en el build
- [ ] Configurar el modo oscuro si es necesario
- [ ] Configurar los valores del tema personalizado
- [ ] Probar los breakpoints responsive
- [ ] Verificar la accesibilidad (estados de foco, contraste)
- [ ] Extraer los patrones repetidos en componentes
- [ ] Documentar las utilidades personalizadas
- [ ] Configurar las extensiones de VSCode
- [ ] Ejecutar el build de producción y comprobar el tamaño del archivo

---

## Recursos

### Documentación Oficial
- [Documentación de Tailwind CSS](https://tailwindcss.com/docs)
- [GitHub de Tailwind CSS](https://github.com/tailwindlabs/tailwindcss)
- [Tailwind Play (Playground en Línea)](https://play.tailwindcss.com/)

### Recursos de Aprendizaje
- [Screencasts Oficiales](https://tailwindcss.com/screencasts)
- [Tailwind Cheat Sheet](https://nerdcave.com/tailwind-cheat-sheet)

### Herramientas y Extensiones
- [Tailwind CSS IntelliSense (VSCode)](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
- [Headwind (Ordenador de Clases)](https://marketplace.visualstudio.com/items?itemName=heybourn.headwind)
- [Generador de Colores de Tailwind CSS](https://uicolors.app/create)
- [Librería de Componentes de Tailwind](https://tailwindui.com/)

### Librerías de Componentes
- [Tailwind UI](https://tailwindui.com/) (Oficial, de pago)
- [Flowbite](https://flowbite.com/) (Componentes gratuitos)
- [DaisyUI](https://daisyui.com/) (Clases de componente)
- [Headless UI](https://headlessui.com/) (Componentes sin estilizar)

### Comunidad
- [Discord de Tailwind CSS](https://tailwindcss.com/discord)
- [Reddit de Tailwind CSS](https://www.reddit.com/r/tailwindcss/)
- [Awesome Tailwind CSS](https://github.com/aniftyco/awesome-tailwindcss)

---

Esta guía cubre Tailwind CSS desde los fundamentos hasta conceptos avanzados, incluyendo dos proyectos prácticos: una página "Links in Bio" y una "Cuadrícula de Videojuegos".

**Temas Cubiertos:**

**Fundamentos (Secciones 1-20):**
- Conceptos del framework de CSS utility-first
- Instalación y configuración (CDN, herramientas de build, frameworks)
- Todas las clases de utilidad (layout, tipografía, colores, espaciado)
- Diseño responsive y variantes
- Funcionalidades avanzadas (modo oscuro, animaciones, filtros)
- Dos proyectos prácticos que demuestran los conceptos fundamentales

**Buenas Prácticas (Secciones 21-31):**
- Ordenamiento de clases y sistema de prioridad
- Configuración de proyecto Vite + React
- Estrategias de extensión de tema personalizado
- Cuándo usar y cuándo no usar @apply
- Técnicas de edición multi-cursor
- Estrategias de extracción de componentes
- Flujo de trabajo profesional con herramientas de IA
- Patrones listos para producción

**Siguientes Pasos:**
1. **Prueba las funcionalidades de v4**: Experimenta con `@import "tailwindcss"` y la directiva `@theme`
2. **Construye proyectos de práctica**: Crea las aplicaciones "Links in Bio" y "Cuadrícula de Videojuegos"
3. **Explora las container queries**: Usa `@container` para diseño responsive con alcance de componente
4. **Prueba el CSS moderno**: Prueba el amplio gamut de color (P3, oklch) en tus diseños
5. **Optimiza la configuración**: Aprovecha la configuración cero para una inicialización de proyecto más rápida
6. **Practica el ordenamiento de clases**: Mantén una organización de clases consistente
7. **Configura IntelliSense**: Instala las extensiones de VSCode para una mejor experiencia de desarrollo
8. **Crea temas personalizados**: Usa la configuración @theme basada en CSS
9. **Integra frameworks**: Configura Tailwind en proyectos de React/Vue/Angular
10. **Construye apps de producción**: Aplica las buenas prácticas a proyectos del mundo real

**Checklist de Migración a v4 (si actualizas desde v3):**
- [ ] Actualizar a `tailwindcss@latest`
- [ ] Reemplazar las directivas `@tailwind` por `@import "tailwindcss"`
- [ ] Mover la config del tema de JS a CSS usando `@theme`
- [ ] Probar el rendimiento del build (debería ser mucho más rápido)
- [ ] Actualizar los pipelines de CI/CD si es necesario
- [ ] Revisar los cambios que rompen compatibilidad en la [guía de migración](https://tailwindcss.com/docs/upgrade-guide)

**Referencias:**
- [Anuncio de Tailwind CSS v4](https://tailwindcss.com/blog/tailwindcss-v4)

---

## 📅 Historial de Versiones

**Tailwind CSS Cubierto:** v4.0
**Última Actualización:** 2026-08-31

**Referencias:**
- [Lanzamiento Oficial de Tailwind CSS v4.0](https://tailwindcss.com/blog/tailwindcss-v4)
- [Documentación de Tailwind CSS](https://tailwindcss.com/docs)
