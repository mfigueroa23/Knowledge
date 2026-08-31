# React - De Cero a Experto

**Versión de React:** 18.x / 19.x (compatible con ambas)
**Última Actualización:** 2026-08-31
**Requisitos Previos:** JavaScript ES6+, HTML, CSS, fundamentos de TypeScript
**Nivel de Habilidad:** Principiante a Experto

---

## 🎯 Cuándo Usar Este Conocimiento

### Ideal Para:
- ✅ **Nuevos Desarrolladores de React** - Aprender React desde los fundamentos hasta conceptos avanzados
- ✅ **Desarrolladores en Transición** - Que vienen de Angular, Vue o JavaScript vanilla
- ✅ **Ingenieros Full-Stack** - Que necesitan una base sólida de React para apps web modernas
- ✅ **Referencia Rápida** - Desarrolladores experimentados que necesitan refrescar patrones
- ✅ **Preparación para Entrevistas** - Entender los conceptos fundamentales de React y las buenas prácticas

### Usa Esta Guía Cuando:
- Inicies un nuevo proyecto React con Vite + TypeScript
- Construyas SPAs (Single Page Applications) sin renderizado del lado del servidor
- Crees herramientas internas, dashboards o paneles de administración
- Aprendas React antes que los frameworks (Next.js, Remix)
- Migres de Create React App a Vite
- Entiendas las nuevas funcionalidades de React 19 manteniendo la compatibilidad con React 18

### No Cubierto Aquí:
- ❌ Server Components (específico de Next.js)
- ❌ React Server Actions (específico del framework)
- ❌ Librerías avanzadas de gestión de estado (Redux, Zustand) - solo fundamentos
- ❌ Estrategias de testing (Jest, React Testing Library)
- ❌ Despliegue y optimización en producción
- ❌ Desarrollo móvil con React Native

### Camino de Aprendizaje Recomendado:
1. **JavaScript/TypeScript** → 2. **React (esta guía)** → 3. **Frameworks de React** (Next.js, Remix)

---

## 📋 Tabla de Contenidos

1. [Introducción](#1-introducción)
2. [React vs Frameworks - Cuándo Usar Cada Uno](#2-react-vs-frameworks---cuándo-usar-cada-uno)
3. [Configuración del Proyecto](#3-configuración-del-proyecto)
4. [Detección de Cambios](#4-detección-de-cambios)
5. [Componentes de React](#5-componentes-de-react)
6. [useState - Gestión de Estado](#6-usestate---gestión-de-estado)
7. [useEffect - Efectos Secundarios](#7-useeffect---efectos-secundarios)
8. [Custom Hooks](#8-custom-hooks)
9. [Patrón de Composición](#9-patrón-de-composición)
10. [Nuevas Funcionalidades de React 19](#10-nuevas-funcionalidades-de-react-19)
11. [Formularios con Zod](#11-formularios-con-zod)
12. [Context API](#12-context-api)
13. [useRef vs useCallback](#13-useref-vs-usecallback)
14. [Portals](#14-portals)
15. [Error Boundaries](#15-error-boundaries)
16. [Interceptores de Axios](#16-interceptores-de-axios)
17. [React Router DOM](#17-react-router-dom)

---

## Descripción General

React es una de las librerías de JavaScript más populares para construir interfaces de usuario, particularmente para aplicaciones de una sola página (SPAs). Esta guía cubre React desde los fundamentos hasta conceptos avanzados, con un enfoque en TypeScript, patrones modernos y prácticas listas para producción.

### ¿Qué es React?

- **Librería de JavaScript** (no un framework) para construir interfaces de usuario
- Creada por Facebook (ahora Meta) en 2013
- **Última versión: React 19** (lanzada en 2024) - estable y lista para producción
- Se enfoca en la arquitectura basada en componentes
- Usa el Virtual DOM para un renderizado eficiente
- Modelo de programación declarativo
- Enfoque TypeScript-first para la seguridad de tipos
- Compatible hacia atrás (el código de React 18 funciona en React 19)

### Características Principales

- ✅ Arquitectura basada en componentes
- ✅ Virtual DOM para la optimización del rendimiento
- ✅ Flujo de datos unidireccional
- ✅ Ecosistema y comunidad ricos
- ✅ React Hooks para la gestión de estado y del ciclo de vida
- ✅ Sintaxis JSX/TSX para plantillas de componentes legibles
- ✅ Fuerte soporte de TypeScript

### Conceptos Fundamentales

**Modelo de Programación:**
- UI declarativa
- Composición de componentes
- Gestión de props y estado
- Enlace de datos unidireccional (con excepciones)

**Patrón de Arquitectura:**
- Los componentes son funciones que devuelven JSX/TSX
- El estado dispara los re-renderizados
- Algoritmo de diffing del Virtual DOM
- Proceso de reconciliación

---

## 1. Introducción

React se ha convertido en la librería más utilizada en el mercado laboral para el desarrollo frontend. Es versátil y te permite:

- Construir aplicaciones de una sola página (SPAs)
- Crear apps móviles con React Native
- Desarrollar aplicaciones de escritorio con Electron
- Construir sitios estáticos con Next.js o Gatsby
- Escalar desde pequeños prototipos hasta aplicaciones empresariales

### Ventajas Clave

**1. Librería vs Framework:**
- React es una librería, no un framework
- Ligera y enfocada en el renderizado de UI
- Flexible - eliges tus propias herramientas y librerías
- Menor curva de aprendizaje para los conceptos básicos

**2. Demanda del Mercado:**
- #1 en el mercado laboral para puestos de frontend
- Gran comunidad y ecosistema
- Amplias librerías de terceros
- Fuerte respaldo corporativo (Meta)

**3. Experiencia del Desarrollador:**
- Flujo de trabajo de desarrollo rápido
- Reemplazo de módulos en caliente (hot module replacement)
- Excelentes herramientas de depuración
- Ecosistema rico de herramientas de desarrollo

### Herramientas Requeridas

**Software Necesario:**
1. **Node.js** - Versión 18+ recomendada (20 LTS o 22 para las últimas funcionalidades)
2. **Editor de Código** - VS Code recomendado
3. **Gestor de Paquetes** - npm, yarn, pnpm o bun (bun recomendado por velocidad)

**Extensiones de VS Code Recomendadas:**
1. **ES7+ React/Redux/React-Native snippets**
   - Generación rápida de componentes
2. **ESLint**
   - Calidad y consistencia del código
3. **Prettier**
   - Formateo de código
4. **TypeScript React code snippets**
   - Snippets específicos de TypeScript

---

## 2. React vs Frameworks - Cuándo Usar Cada Uno

Entender cuándo usar React vanilla frente a un framework es crucial para el éxito del proyecto.

### Cuándo Usar React Vanilla

#### ✅ Mejor Para:

**1. Aplicaciones Personalizadas:**
- Necesitas control completo sobre la arquitectura
- Requisitos específicos no cubiertos por los frameworks
- Quieres elegir cada librería individualmente

**2. Simplicidad y Flexibilidad:**
- Tamaño de bundle mínimo
- Añade solo lo que necesitas
- Sin opiniones ni restricciones del framework

**3. Prototipado Rápido:**
- MVPs y pruebas de concepto rápidas
- Startups descubriendo su producto
- Funcionalidades de A/B testing

**4. Aplicaciones Privadas/Internas:**
- Paneles de administración y dashboards
- Herramientas internas y CRMs
- Aplicaciones detrás de autenticación
- SEO no requerido

**5. Aprendizaje y Comprensión:**
- Primera vez aprendiendo React
- Entender los conceptos fundamentales
- Construir conocimiento fundacional

#### 📦 Características de React:

```typescript
// React puro - Tú controlas todo
import { useState } from 'react';

// Elige el tuyo:
// - Router (react-router-dom, wouter, etc.)
// - Gestión de estado (Redux, Zustand, Jotai, etc.)
// - Formularios (React Hook Form, Formik, etc.)
// - Cliente HTTP (axios, fetch, etc.)
// - Estilos (CSS modules, styled-components, Tailwind, etc.)
```

### Comparación de Frameworks de React

### Next.js

**Cuándo Usarlo:**
- ✅ El SEO es crítico
- ✅ Mezcla de aplicación pública + privada (e-commerce, blogs)
- ✅ Se necesita renderizado del lado del servidor
- ✅ Generación de sitios estáticos
- ✅ La optimización de imágenes es importante
- ✅ Se prefiere el enrutamiento integrado

**Características:**
- Renderizado del lado del servidor por defecto
- Enrutamiento basado en archivos
- Optimizaciones integradas (imágenes, fuentes)
- Integración con Vercel
- Rutas de API
- Opiniones fuertes sobre la arquitectura

**Precauciones:**
- ⚠️ Todo se renderiza en el servidor por defecto
- ⚠️ Hay que optar explícitamente por los componentes de cliente con `'use client'`
- ⚠️ Puede ser excesivo para SPAs simples
- ⚠️ Curva de aprendizaje para los conceptos de SSR

### Remix

**Cuándo Usarlo:**
- ✅ El SEO es crucial
- ✅ El rendimiento es primordial
- ✅ Patrones avanzados de obtención de datos
- ✅ Requisitos de enrutamiento complejos
- ✅ Mejora progresiva

**Características:**
- Enfocado en el renderizado del lado del servidor
- Excelentes patrones de carga de datos
- Enrutamiento anidado
- Enfocado en los estándares web
- Transiciones de página rápidas

**Precauciones:**
- ⚠️ Mercado laboral limitado
- ⚠️ Curva de aprendizaje más pronunciada
- ⚠️ Mejor para aplicaciones complejas

### Solid.js (Alternativa similar a React)

**Cuándo Usarlo:**
- ✅ Aplicaciones críticas en rendimiento
- ✅ Proyectos personales
- ✅ Aprender patrones reactivos modernos

**Características:**
- Familiaridad con la sintaxis de React
- Verdadera reactividad con Signals
- Sin la sobrecarga del Virtual DOM
- Extremadamente rápido
- Tamaño de bundle diminuto (~7KB)

**Precauciones:**
- ⚠️ Mercado laboral mínimo
- ⚠️ Ecosistema más pequeño
- ⚠️ Aprende React primero, luego Solid

### Árbol de Decisión

```
¿Necesitas SEO?
  ├─ SÍ → ¿Necesitas funciones de framework (routing, SSR, etc.)?
  │         ├─ SÍ → Next.js o Remix
  │         └─ NO → React + Vite
  └─ NO → ¿Aplicación privada?
            ├─ SÍ → React + Vite (SPA)
            └─ NO → Considera Next.js para páginas públicas
```

### Filosofía Importante

**Empieza siempre por la base:**
- Aprende JavaScript antes que React
- Aprende React antes que los frameworks
- Domina los fundamentos antes que las abstracciones
- Más conocimiento de React = Más conocimiento de frameworks

El principio se aplica en todas partes:
```
JavaScript → React → Next.js/Remix
React → Solid.js
React → React Native
```

---

## 3. Configuración del Proyecto

Configuración moderna de un proyecto React con Vite y TypeScript.

### Usando Vite (Recomendado)

Vite es la herramienta de build moderna y rápida recomendada por el equipo de React (reemplaza a Create React App).

#### Instalación

```bash
# Usando npm
npm create vite@latest my-react-app -- --template react-ts

# Usando yarn
yarn create vite my-react-app --template react-ts

# Usando pnpm
pnpm create vite my-react-app --template react-ts

# Usando bun (el más rápido)
bun create vite my-react-app --template react-ts
```

#### Estructura del Proyecto

```
my-react-app/
├── node_modules/          # Dependencias
├── public/                # Assets estáticos
│   └── vite.svg          # Archivos públicos (no procesados por Vite)
├── src/                   # Código fuente
│   ├── assets/           # Assets procesados por Vite
│   ├── components/       # Componentes de React
│   ├── App.tsx           # Componente raíz
│   ├── App.css           # Estilos del componente
│   ├── main.tsx          # Punto de entrada de la aplicación
│   └── index.css         # Estilos globales
├── .eslintrc.cjs         # Configuración de ESLint
├── .gitignore            # Reglas de ignorado de Git
├── index.html            # Punto de entrada HTML
├── package.json          # Dependencias y scripts del proyecto
├── tsconfig.json         # Configuración de TypeScript
├── tsconfig.node.json    # Configuración de TypeScript para Node
└── vite.config.ts        # Configuración de Vite
```

### Entendiendo los Archivos Clave

#### `index.html` - Punto de Entrada

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vite + React + TS</title>
  </head>
  <body>
    <!-- Raíz de React - todo se renderiza aquí -->
    <div id="root"></div>
    <!-- Script de módulo - carga la aplicación React -->
    <script type="module" src="/src/main.tsx"></script>
  </body>
</html>
```

#### `main.tsx` - Arranque de la Aplicación

```typescript
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.tsx'
import './index.css'

// Crear la raíz y renderizar la aplicación
ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
)
```

**Notas Importantes:**
- `!` - Aserción de no-nulo (TypeScript)
- `React.StrictMode` - Ayudante de desarrollo que:
  - Identifica ciclos de vida inseguros
  - Advierte sobre el uso de APIs heredadas
  - Detecta efectos secundarios inesperados
  - **Renderiza los componentes dos veces en desarrollo** (no en producción)
  - ¿Por qué? Para asegurar que los componentes puedan manejar múltiples renderizados

#### `App.tsx` - Componente Raíz

```typescript
import { useState } from 'react'
import './App.css'

function App() {
  const [count, setCount] = useState(0)

  return (
    <>
      <h1>Vite + React</h1>
      <button onClick={() => setCount((count) => count + 1)}>
        count is {count}
      </button>
    </>
  )
}

export default App
```

### Scripts del Package

```json
{
  "scripts": {
    "dev": "vite",                // Servidor de desarrollo
    "build": "tsc && vite build", // Build de producción
    "lint": "eslint . --ext ts,tsx", // Ejecutar el linter
    "preview": "vite preview"     // Previsualizar el build de producción
  }
}
```

#### Comandos Comunes

```bash
# Desarrollo
npm run dev          # Iniciar el servidor de desarrollo (http://localhost:5173)
npm run build        # Build para producción
npm run preview      # Previsualizar el build de producción localmente
npm run lint         # Comprobar la calidad del código

# Dependencias
npm install          # Instalar todas las dependencias
npm install <package> # Añadir una nueva dependencia
```

### Conceptos de Bundler

#### ¿Qué es Vite?

Vite (del francés "rápido") es una herramienta de build moderna que proporciona:

**1. Servidor de Desarrollo Rápido:**
- Módulos ES nativos (sin bundling en dev)
- Reemplazo de Módulos en Caliente (HMR)
- Arranque instantáneo del servidor

**2. Build de Producción Optimizado:**
- Usa Rollup para el bundling
- Tree-shaking (elimina el código sin usar)
- Code splitting
- Minificación
- Ofuscación (uglification)

**3. Sistema de Plugins:**
- Plugin de React para soporte de JSX/TSX
- Soporte de TypeScript de fábrica
- Preprocesamiento de CSS
- Manejo de assets

#### Proceso de Build Explicado

**Desarrollo (`npm run dev`):**
```
Código Fuente → Servidor de Desarrollo de Vite → Navegador
     ↓
  (Sin bundling, módulos ES nativos)
     ↓
  Actualizaciones HMR rápidas
```

**Producción (`npm run build`):**
```
Código Fuente → Comprobación de TypeScript → Build de Vite (Rollup) → Bundle Optimizado
                                       ↓
                            - Minificación
                            - Ofuscación
                            - Tree-shaking
                            - Code splitting
                                       ↓
                                   dist/
```

#### Salida del Bundle (`dist/`)

Después de ejecutar `npm run build`, obtienes:

```
dist/
├── assets/
│   ├── index-a1b2c3d4.js     # Bundle principal de la aplicación
│   ├── index-e5f6g7h8.css    # Estilos compilados
│   └── vendor-i9j0k1l2.js    # Librerías de terceros
└── index.html                 # HTML de entrada
```

**Características:**
- **Minificado** - Elimina espacios en blanco, acorta los nombres de variables
- **Ofuscado** - Hace el código ilegible para proteger la propiedad intelectual
- **Nombres de archivo con hash** - Para invalidación de caché (`index-a1b2c3d4.js`)
- **Code splitting** - Separa el código de vendor y de la app
- **Tree-shaken** - Las importaciones sin usar se eliminan

### Configuración de TypeScript

#### `tsconfig.json`

```json
{
  "compilerOptions": {
    "target": "ES2020",           // Versión de JavaScript a la que compilar
    "useDefineForClassFields": true,
    "lib": ["ES2020", "DOM", "DOM.Iterable"],
    "module": "ESNext",           // Sistema de módulos
    "skipLibCheck": true,

    /* Modo bundler */
    "moduleResolution": "bundler",
    "allowImportingTsExtensions": true,
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true,
    "jsx": "react-jsx",           // Modo de compilación de JSX

    /* Linting */
    "strict": true,               // Habilitar todas las comprobaciones de tipos estrictas
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noFallthroughCasesInSwitch": true
  },
  "include": ["src"],
  "references": [{ "path": "./tsconfig.node.json" }]
}
```

### Configuración de ESLint

#### `.eslintrc.cjs`

```javascript
module.exports = {
  root: true,
  env: { browser: true, es2020: true },
  extends: [
    'eslint:recommended',
    'plugin:@typescript-eslint/recommended',
    'plugin:react-hooks/recommended',
  ],
  ignorePatterns: ['dist', '.eslintrc.cjs'],
  parser: '@typescript-eslint/parser',
  plugins: ['react-refresh'],
  rules: {
    'react-refresh/only-export-components': [
      'warn',
      { allowConstantExport: true },
    ],
  },
}
```

### React Sin Herramientas de Build

Con fines de aprendizaje o para prototipos rápidos, puedes usar React directamente desde un CDN sin ninguna herramienta de build.

```html
<!DOCTYPE html>
<html>
<head>
  <title>React Without Build Tools</title>
</head>
<body>
  <div id="root"></div>

  <script type="module">
    // Importar React desde el CDN
    import React from 'https://esm.sh/react@18'
    import ReactDOM from 'https://esm.sh/react-dom@18/client'

    // Obtener el elemento raíz
    const rootElement = document.getElementById('root')

    // Crear la raíz de React
    const root = ReactDOM.createRoot(rootElement)

    // Crear y renderizar el elemento
    const button = React.createElement(
      'button',
      { onClick: () => alert('Clicked!') },
      'Click me'
    )

    root.render(button)
  </script>
</body>
</html>
```

**Puntos Clave:**
- React puede ejecutarse en cualquier lugar donde se ejecute JavaScript
- No se requieren herramientas de build para aprender
- Perfecto para entender los fundamentos
- Las apps de producción deberían usar herramientas de build

---

## 3.5. JSX en Profundidad

JSX **no** es HTML dentro de JavaScript - es una extensión de sintaxis que se transforma en JavaScript.

### Entendiendo la Transformación de JSX

#### Qué es Realmente JSX

```tsx
// Lo que escribes (JSX)
const element = <button onClick={handleClick}>Click me</button>

// En lo que se convierte (JavaScript)
const element = React.createElement(
  'button',
  { onClick: handleClick },
  'Click me'
)
```

**JSX es azúcar sintáctico** para las llamadas a `React.createElement()`.

#### Firma de React.createElement

```typescript
React.createElement(
  type,        // Etiqueta HTML o Componente
  props,       // Atributos/propiedades (o null)
  ...children  // Contenido dentro del elemento
)
```

### Ejemplos Completos de Transformación

#### Elemento Simple

```tsx
// JSX
<div>Hello World</div>

// Se transforma en:
React.createElement('div', null, 'Hello World')
```

#### Elemento con Atributos

```tsx
// JSX
<button className="btn" disabled>
  Submit
</button>

// Se transforma en:
React.createElement(
  'button',
  { className: 'btn', disabled: true },
  'Submit'
)
```

#### Elementos Anidados

```tsx
// JSX
<div className="container">
  <h1>Title</h1>
  <p>Description</p>
</div>

// Se transforma en:
React.createElement(
  'div',
  { className: 'container' },
  React.createElement('h1', null, 'Title'),
  React.createElement('p', null, 'Description')
)
```

### Transpiladores de JSX

#### Babel

[Babel REPL](https://babeljs.io/repl) - Ve las transformaciones de JSX en tiempo real

```tsx
// Entrada (JSX)
const App = () => {
  return <div>Hello {name}</div>
}

// Salida (JavaScript - Transformación Clásica)
const App = () => {
  return React.createElement('div', null, 'Hello ', name)
}
```

#### SWC (Alternativa Súper Rápida)

[SWC Playground](https://swc.rs/playground)

```tsx
// SWC está escrito en Rust y es mucho más rápido que Babel
// Usado por Vite, Next.js 12+ y otras herramientas modernas
// La misma transformación, pero 20x más rápida
```

**React Moderno (Transformación Automática):**
```typescript
// React 17+ con runtime automático
import { jsx as _jsx } from 'react/jsx-runtime'

const App = () => {
  return _jsx('div', { children: ['Hello ', name] })
}
```

### Reglas y Restricciones de JSX

#### 1. Debe Devolver un Solo Elemento

```tsx
// ❌ Error - Múltiples elementos raíz
function App() {
  return (
    <h1>Title</h1>
    <p>Description</p>
  )
}

// ✅ Solución 1: Elemento contenedor
function App() {
  return (
    <div>
      <h1>Title</h1>
      <p>Description</p>
    </div>
  )
}

// ✅ Solución 2: Fragment (recomendado)
function App() {
  return (
    <>
      <h1>Title</h1>
      <p>Description</p>
    </>
  )
}

// ✅ Solución 3: Fragment explícito
function App() {
  return (
    <React.Fragment>
      <h1>Title</h1>
      <p>Description</p>
    </React.Fragment>
  )
}
```

**¿Por qué?** Porque `React.createElement()` solo puede crear un elemento a la vez.

#### 2. Expresiones de JavaScript en JSX

```tsx
function Greeting({ name }: { name: string }) {
  const greeting = 'Hello'

  return (
    <div>
      {/* ✅ Variables */}
      <h1>{greeting}, {name}!</h1>

      {/* ✅ Expresiones */}
      <p>Random: {Math.random()}</p>

      {/* ✅ Llamadas a funciones */}
      <p>Uppercase: {name.toUpperCase()}</p>

      {/* ✅ Operadores ternarios */}
      <p>{name.length > 5 ? 'Long name' : 'Short name'}</p>

      {/* ✅ AND lógico */}
      {name && <p>Name exists: {name}</p>}

      {/* ❌ No se permiten sentencias */}
      {/* {if (name) return 'Hi'} - ¡Error! */}
      {/* {const x = 5} - ¡Error! */}
    </div>
  )
}
```

**Regla:** Solo **expresiones** dentro de `{}`, no **sentencias**

#### 3. Atributos en camelCase

```tsx
// ❌ Atributos HTML (no funcionan en JSX)
<div class="container" tabindex="0" onclick="handleClick()">

// ✅ Atributos JSX (camelCase)
<div className="container" tabIndex={0} onClick={handleClick}>

// Conversiones comunes:
// class → className
// for → htmlFor
// tabindex → tabIndex
// onclick → onClick
// stroke-width → strokeWidth
```

**¿Por qué?** JSX es JavaScript, y `class` es una palabra reservada.

#### 4. Etiquetas Auto-Cerradas

```tsx
// ❌ Estilo HTML (algunas funcionan, pero no de forma consistente)
<img src="image.jpg">
<input type="text">

// ✅ Estilo JSX (deben ser auto-cerradas)
<img src="image.jpg" />
<input type="text" />
<MyComponent />
```

#### 5. Props de String vs Expresión

```tsx
<Component
  // ✅ Valor string
  name="John"

  // ✅ Expresión (número)
  age={30}

  // ✅ Expresión (booleano)
  isActive={true}

  // ✅ Booleano abreviado (igual que isActive={true})
  isActive

  // ✅ Expresión (objeto)
  user={{ name: 'John', age: 30 }}

  // ✅ Expresión (array)
  items={[1, 2, 3]}

  // ❌ Incorrecto - intenta convertir el objeto a string
  user="{{ name: 'John' }}"
/>
```

### Protección contra XSS

JSX escapa automáticamente el contenido para prevenir ataques de Cross-Site Scripting (XSS).

```tsx
const userInput = '<script>alert("XSS")</script>'

// ✅ Seguro - React escapa la cadena
function Safe() {
  return <div>{userInput}</div>
  // Renderiza: <div>&lt;script&gt;alert("XSS")&lt;/script&gt;</div>
}

// ⚠️ Inseguro - dangerouslySetInnerHTML (¡evítalo!)
function Unsafe() {
  return <div dangerouslySetInnerHTML={{ __html: userInput }} />
  // ¡Ejecuta realmente el script!
}
```

**Idea Clave:** React escapa todo el texto por defecto, proporcionando protección XSS integrada.

### Declarativo vs Imperativo

#### Imperativo (JavaScript Vanilla)

```javascript
// Imperativo: Decir CÓMO hacerlo paso a paso
const button = document.createElement('button')
button.textContent = 'Click me'
button.className = 'btn'

button.addEventListener('click', () => {
  button.textContent = 'Clicked!'
  button.disabled = true
})

document.body.appendChild(button)
```

#### Declarativo (React)

```tsx
// Declarativo: Decir QUÉ quieres, React averigua CÓMO
function Button() {
  const [clicked, setClicked] = useState(false)

  return (
    <button
      className="btn"
      disabled={clicked}
      onClick={() => setClicked(true)}
    >
      {clicked ? 'Clicked!' : 'Click me'}
    </button>
  )
}
```

**Ventaja de React:** Describes cómo debería verse la UI, y React se encarga de las actualizaciones del DOM.

---

## 4. Detección de Cambios

Entender cómo React detecta y aplica los cambios es fundamental para escribir aplicaciones de alto rendimiento.

### Cómo Funciona React Internamente

React usa un mecanismo sofisticado de detección de cambios basado en:
1. **Triggers (Disparadores)** - Eventos que inician el proceso de renderizado
2. **Virtual DOM** - Representación en memoria de la UI
3. **Reconciliación** - Comparar el Virtual DOM antiguo y el nuevo
4. **Commit** - Aplicar los cambios al DOM real

### Triggers

Un **trigger** es cualquier evento que inicia un proceso de renderizado.

#### Tipos de Triggers

**1. Trigger Inicial (Montaje):**
```typescript
// El componente se monta por primera vez
function App() {
  // El renderizado inicial ocurre aquí
  return <div>Hello World</div>
}
```

**2. Cambio de Estado:**
```typescript
function Counter() {
  const [count, setCount] = useState(0)

  // Hacer clic en el botón dispara un re-renderizado
  return <button onClick={() => setCount(count + 1)}>
    Count: {count}
  </button>
}
```

**3. Re-renderizado del Padre:**
```typescript
function Parent() {
  const [value, setValue] = useState(0)
  return (
    <>
      <button onClick={() => setValue(value + 1)}>Update</button>
      {/* El hijo se re-renderiza cuando el padre se re-renderiza */}
      <Child data={value} />
    </>
  )
}
```

**4. Operaciones Asíncronas:**
```typescript
function DataFetcher() {
  const [data, setData] = useState(null)

  useEffect(() => {
    // La llamada a la API dispara un re-renderizado al completarse
    fetch('/api/data')
      .then(res => res.json())
      .then(data => setData(data)) // ¡Trigger!
  }, [])

  return <div>{data ? data.title : 'Loading...'}</div>
}
```

### El Proceso de Renderizado

#### ¿Qué es Renderizar?

**Renderizar = Ejecutar la función del componente**

```typescript
// Esto es un componente
function Dashboard() {
  // Cuando React "renderiza", ejecuta esta función
  console.log('Rendering Dashboard!')

  return <div>Dashboard Content</div>
}

// Llamar a <Dashboard /> en JSX es como llamar a Dashboard()
```

#### El Ciclo de Renderizado Completo

```
1. Trigger
   ↓
2. Render (Ejecutar la función del componente)
   ↓
3. Crear el Virtual DOM
   ↓
4. Reconciliación (Comparar con el Virtual DOM anterior)
   ↓
5. Commit (Actualizar el DOM real solo con los cambios)
   ↓
6. Pintado del Navegador
```

### Virtual DOM

El Virtual DOM es el arma secreta de React para el rendimiento.

#### DOM Real vs Virtual DOM

```typescript
// DOM Real (lento de manipular)
document.getElementById('root').innerHTML = '<div>New Content</div>'

// Virtual DOM (objeto JavaScript rápido)
const virtualDOM = {
  type: 'div',
  props: { children: 'New Content' }
}
```

#### Cómo Funciona el Virtual DOM

**1. Renderizado Inicial:**
```typescript
function App() {
  return <div>Hello</div>
}

// Crea el Virtual DOM:
{
  type: 'div',
  props: { children: 'Hello' }
}

// Hace commit al DOM Real:
<div>Hello</div>
```

**2. Actualización (Re-renderizado):**
```typescript
function App() {
  const [text, setText] = useState('Hello')

  return <div>{text}</div>
}

// Después de setText('Goodbye'):
// Nuevo Virtual DOM:
{
  type: 'div',
  props: { children: 'Goodbye' }
}

// React compara:
// Virtual DOM antiguo: { children: 'Hello' }
// Virtual DOM nuevo: { children: 'Goodbye' }
// Diferencia: El contenido de texto cambió
// Commit: Actualiza SOLO el contenido de texto en el DOM Real
```

### Algoritmo de Reconciliación

El algoritmo de diffing de React compara los árboles del Virtual DOM de forma eficiente.

#### Principios Clave

**1. Tipos de Elementos Diferentes:**
```typescript
// Antes:
<div>Content</div>

// Después:
<span>Content</span>

// React: Desmonta <div>, monta <span> (re-renderizado completo)
```

**2. Mismo Tipo de Elemento:**
```typescript
// Antes:
<div className="before">Content</div>

// Después:
<div className="after">Content</div>

// React: Actualiza solo el atributo className (sin re-montaje)
```

**3. Keys para Listas:**
```typescript
// ❌ Mal - Sin keys
{items.map(item => <div>{item.name}</div>)}

// ✅ Bien - Con keys
{items.map(item => <div key={item.id}>{item.name}</div>)}

// Las keys ayudan a React a identificar qué elementos cambiaron, se añadieron o se eliminaron
```

### Fase de Commit

La fase de commit aplica los cambios al DOM real.

```typescript
function Example() {
  const [count, setCount] = useState(0)

  // Fase de render: React llama a esta función, crea el Virtual DOM
  console.log('Rendering with count:', count)

  // Fase de commit: React actualiza el DOM real
  return <div>Count: {count}</div>
}

// Proceso:
// 1. Trigger: setCount(1)
// 2. Render: Ejecutar Example(), crear un nuevo Virtual DOM
// 3. Reconciliación: Comparar el Virtual DOM antiguo (count: 0) vs el nuevo (count: 1)
// 4. Commit: Actualizar el nodo de texto del DOM Real de "0" a "1"
```

### Implicaciones de Rendimiento

#### Los Re-renderizados Son Normales

```typescript
function Parent() {
  const [count, setCount] = useState(0)

  return (
    <>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
      {/* El hijo se re-renderiza aunque las props no cambien */}
      <ExpensiveChild />
    </>
  )
}
```

**Importante:** Cada cambio de estado en un padre causa que todos los hijos se re-rendericen. Aprenderemos técnicas de optimización más adelante (React.memo, useCallback, useMemo).

#### Analogía Culinaria

Piensa en el renderizado como la cocina de un restaurante:

1. **Trigger** = El cliente pide comida (clic de botón, cambio de estado)
2. **Render** = El chef prepara el plato (ejecutar la función del componente)
3. **Commit** = El camarero lo lleva a la mesa (actualizar el DOM)

Si el cliente cambia su pedido:
- Trigger: "En realidad, quiero papas fritas en lugar de ensalada"
- Render: El chef prepara las papas fritas nuevas
- Reconciliación: Comparar el pedido antiguo vs el nuevo
- Commit: Entregar solo el elemento cambiado (papas fritas), mantener el resto

---

## 5. Componentes de React

Los componentes son los bloques de construcción de las aplicaciones React. Entender los patrones de componentes es esencial para aplicaciones escalables.

### Fundamentos de los Componentes

#### ¿Qué es un Componente?

**Un componente es una función que devuelve JSX/TSX.**

```typescript
// Componente básico
function Welcome() {
  return <h1>Hello, World!</h1>
}

// Componente con TypeScript
function Greeting(): JSX.Element {
  return <h1>Hello, TypeScript!</h1>
}
```

#### Función Component vs Arrow Function

```typescript
// Declaración de función (tradicional)
function Button() {
  return <button>Click me</button>
}

// Arrow function (moderna, preferida)
const Button = () => {
  return <button>Click me</button>
}

// Arrow function con retorno implícito
const Button = () => <button>Click me</button>
```

### JSX vs TSX

#### Extensiones de Archivo

**Cuándo usar `.tsx`:**
```typescript
// Button.tsx - Contiene JSX/TSX
import { FC } from 'react'

export const Button: FC = () => {
  return <button>Click me</button>
}
```

**Cuándo usar `.ts`:**
```typescript
// types.ts - Sin JSX
export interface User {
  name: string
  lastName: string
}

// utils.ts - Sin JSX
export const formatName = (firstName: string, lastName: string) => {
  return `${firstName} ${lastName}`
}
```

**Regla:** Si el archivo devuelve JSX/TSX → usa `.tsx`, de lo contrario usa `.ts`

### Convención de Nombrado de Componentes

```tsx
// ❌ Mal - minúscula (React lo trata como un elemento HTML)
function button() {
  return <button>Click</button>
}

// Uso: <button /> - React lo renderiza como la etiqueta HTML <button>, ¡no como componente!

// ✅ Correcto - PascalCase
function Button() {
  return <button>Click</button>
}

// Uso: <Button /> - React lo reconoce como componente
```

**¿Por qué PascalCase?**
- React necesita distinguir entre elementos HTML y componentes
- Elementos HTML: minúscula (`<div>`, `<button>`, `<input>`)
- Componentes: PascalCase (`<Button>`, `<UserCard>`, `<NavBar>`)

```tsx
// Esto es confuso - no lo hagas
<custom-button />  // ¿Elemento personalizado de HTML?
<customButton />   // ¿Componente? ¿HTML?
<CustomButton />   // ✅ Claro: ¡Es un componente!
```

### Elemento vs Componente (Distinción Crítica)

**Este es uno de los conceptos más malentendidos en React.**

#### ¿Qué es un Componente?

**Un Componente es una fábrica de elementos** - es una función que crea elementos.

```typescript
// Componente = Función
function Button() {
  return <button>Click me</button>
}

// El componente crea elementos cuando se le llama
const element1 = <Button />  // Crea un elemento
const element2 = <Button />  // Crea otro elemento
```

#### ¿Qué es un Elemento?

**Un Elemento es lo que React renderiza** - es el valor de retorno de un componente.

```typescript
// Elemento = Objeto que describe qué renderizar
const element = {
  type: 'button',
  props: {
    children: 'Click me'
  }
}
```

#### La Diferencia Clave

```tsx
// ❌ Error Común - Intentar renderizar un componente
function App() {
  return <div>{Button}</div>  // Renderiza [object Object] o una función
}

// ✅ Correcto - Renderizar el elemento que crea el componente
function App() {
  return <div><Button /></div>  // Llama a Button() y renderiza el resultado
}

// O con createElement:
function App() {
  return React.createElement('div', null, React.createElement(Button))
}
```

#### Comparación Visual

```tsx
// Componente (Fábrica)
function UserCard() {
  return <div>User Profile</div>
}

// Elemento (Producto)
const userCardElement = <UserCard />

// Lo que React realmente renderiza:
{
  type: UserCard,  // Referencia a la función del componente
  props: {},
  key: null
}
```

#### Ejemplo Práctico

```tsx
function App() {
  // ❌ Mal - Evaluar el componente como expresión
  const component = UserCard  // Solo una referencia a la función
  return <div>{component}</div>  // No se renderizará correctamente

  // ✅ Correcto - Crear un elemento a partir del componente
  const element = <UserCard />  // Llama a UserCard() → devuelve un elemento
  return <div>{element}</div>  // Renderiza el elemento

  // ✅ También correcto - Uso directo
  return (
    <div>
      <UserCard />
    </div>
  )
}
```

#### Múltiples Instancias

```tsx
function App() {
  // Mismo componente, pero crea distintas instancias de elemento
  return (
    <>
      <Button />  {/* Instancia de elemento 1 */}
      <Button />  {/* Instancia de elemento 2 */}
      <Button />  {/* Instancia de elemento 3 */}
    </>
  )
}

// Cada llamada a <Button />:
// 1. Ejecuta la función Button()
// 2. Crea un nuevo objeto de elemento
// 3. React gestiona cada elemento de forma independiente
```

**Idea Clave:**
- Los componentes NO renderizan - crean elementos
- Los elementos renderizan - son lo que React pone en el DOM
- Cuando escribes `<Button />`, estás creando un elemento a partir del componente Button

### Tipos de Componentes

#### 1. Componentes Inteligentes (Con Estado)

Componentes que gestionan estado y lógica de negocio.

```typescript
// Componente inteligente - Tiene estado y lógica
import { useState } from 'react'

interface User {
  name: string
  email: string
}

const UserDashboard = () => {
  const [user, setUser] = useState<User | null>(null)
  const [loading, setLoading] = useState(true)

  // Lógica de negocio
  const fetchUser = async () => {
    try {
      setLoading(true)
      const response = await fetch('/api/user')
      const data = await response.json()
      setUser(data)
    } catch (error) {
      console.error('Failed to fetch user:', error)
    } finally {
      setLoading(false)
    }
  }

  // Efecto secundario
  useEffect(() => {
    fetchUser()
  }, [])

  if (loading) return <LoadingSpinner />
  if (!user) return <ErrorMessage />

  return (
    <div>
      <h1>Welcome, {user.name}</h1>
      <UserProfile user={user} />
    </div>
  )
}
```

**Características:**
- ✅ Contiene `useState`, `useEffect` u otros hooks
- ✅ Tiene lógica de negocio
- ✅ Gestiona el estado local
- ✅ Hace llamadas a APIs
- ✅ Maneja eventos y pasa callbacks hacia abajo

#### 2. Componentes Tontos (De Presentación)

Componentes que solo muestran la UI y reciben datos vía props.

```typescript
// Componente tonto - Solo presentación
interface ButtonProps {
  label: string
  onClick: () => void
  variant?: 'primary' | 'secondary'
}

const Button = ({ label, onClick, variant = 'primary' }: ButtonProps) => {
  return (
    <button
      className={`btn btn-${variant}`}
      onClick={onClick}
    >
      {label}
    </button>
  )
}
```

**Características:**
- ✅ Sin gestión de estado
- ✅ Recibe datos vía props
- ✅ Se enfoca en la presentación visual
- ✅ Reutilizable en toda la aplicación
- ✅ Emite eventos al padre (no contiene lógica)

### Props y TypeScript

#### Definiendo Interfaces de Props

```typescript
// ✅ Bien - Interface para las props
interface UserCardProps {
  name: string
  email: string
  age?: number  // Prop opcional
  onEdit?: () => void  // Callback opcional
}

const UserCard = ({ name, email, age, onEdit }: UserCardProps) => {
  return (
    <div className="user-card">
      <h2>{name}</h2>
      <p>{email}</p>
      {age && <p>Age: {age}</p>}
      {onEdit && <button onClick={onEdit}>Edit</button>}
    </div>
  )
}
```

#### Props children

```typescript
interface CardProps {
  children: React.ReactNode
  title: string
}

const Card = ({ children, title }: CardProps) => {
  return (
    <div className="card">
      <h3>{title}</h3>
      <div className="card-content">
        {children}
      </div>
    </div>
  )
}

// Uso
<Card title="User Info">
  <p>This is the card content</p>
  <button>Action</button>
</Card>
```

### Props en Profundidad

Las props son el mecanismo para pasar datos de los componentes padre a los hijo.

#### Pasando Distintos Tipos de Props

##### 1. Props de String

```tsx
// Valor string directo
<UserCard name="John Doe" />

// Expresión (template literal)
<UserCard name={`${firstName} ${lastName}`} />
```

##### 2. Props de Número

```tsx
// ❌ Mal - Esto es un string "25"
<UserCard age="25" />

// ✅ Correcto - Esto es un número 25
<UserCard age={25} />
```

##### 3. Props Booleanas

```tsx
// ✅ Forma larga
<UserCard isActive={true} />
<UserCard isActive={false} />

// ✅ Abreviado (igual que isActive={true})
<UserCard isActive />

// ❌ No hay abreviatura para false (debe usar {false})
<UserCard !isActive />  // ¡Esto no funciona!
<UserCard isActive={false} />  // Usa esto en su lugar
```

**Regla de Abreviatura:** La sola presencia del nombre de la prop = `true`

```tsx
<input disabled />        // disabled={true}
<input required />        // required={true}
<Component loading />     // loading={true}
```

##### 4. Props de Función (Callbacks)

```tsx
interface ButtonProps {
  label: string
  onClick: () => void  // Prop de función
}

function Button({ label, onClick }: ButtonProps) {
  return (
    <button onClick={onClick}>
      {label}
    </button>
  )
}

// Uso
function App() {
  const handleClick = () => {
    console.log('Clicked!')
  }

  return <Button label="Click me" onClick={handleClick} />
}
```

**Importante:** ¡Pasa la referencia de la función, no la llamada a la función!

```tsx
// ❌ Mal - Se ejecuta inmediatamente
<Button onClick={handleClick()} />

// ✅ Correcto - Pasa la referencia de la función
<Button onClick={handleClick} />

// ✅ También correcto - Envoltorio de arrow function (cuando necesitas argumentos)
<Button onClick={() => handleClick(id)} />
```

##### 5. Props de Objeto

```tsx
interface UserCardProps {
  user: {
    name: string
    age: number
    email: string
  }
}

function UserCard({ user }: UserCardProps) {
  return (
    <div>
      <h2>{user.name}</h2>
      <p>Age: {user.age}</p>
      <p>Email: {user.email}</p>
    </div>
  )
}

// Uso
const userData = {
  name: 'John',
  age: 30,
  email: 'john@example.com'
}

<UserCard user={userData} />
```

**Operador Spread para las Props:**

```tsx
// Objeto con props
const userProps = {
  name: 'John',
  age: 30,
  isActive: true
}

// ❌ Menos claro
<UserCard name={userProps.name} age={userProps.age} isActive={userProps.isActive} />

// ✅ Operador spread
<UserCard {...userProps} />

// Equivalente a:
// <UserCard name="John" age={30} isActive={true} />
```

**⚠️ Precaución con Spread:**
- Puede pasar props innecesarias
- Hace más difícil ver qué props recibe un componente
- Puede causar re-renderizados innecesarios
- Úsalo con moderación e intencionalmente

##### 6. Props de Elemento (Avanzado)

¡Puedes pasar elementos de React como props!

```tsx
interface UserCardProps {
  name: string
  icon: React.ReactNode  // Prop de elemento
}

function UserCard({ name, icon }: UserCardProps) {
  return (
    <div className="user-card">
      {icon}
      <h2>{name}</h2>
    </div>
  )
}

// Uso
<UserCard
  name="John"
  icon={<img src="/avatar.jpg" alt="User" />}
/>

// O con un componente
<UserCard
  name="John"
  icon={<UserIcon size={24} />}
/>
```

#### Valores por Defecto para las Props

```tsx
interface ButtonProps {
  label: string
  variant?: 'primary' | 'secondary'
}

// ✅ Valores por defecto con destructuring
function Button({ label, variant = 'primary' }: ButtonProps) {
  return (
    <button className={`btn-${variant}`}>
      {label}
    </button>
  )
}

// Uso - variant toma 'primary' por defecto
<Button label="Submit" />
<Button label="Cancel" variant="secondary" />
```

#### La Prop Especial `children`

`children` es una prop especial que representa el contenido entre las etiquetas del componente.

```tsx
interface CardProps {
  children: React.ReactNode
}

function Card({ children }: CardProps) {
  return <div className="card">{children}</div>
}

// Uso - Todo lo que hay entre las etiquetas es `children`
<Card>
  <h1>Title</h1>
  <p>Content</p>
</Card>
```

**children Puede Ser Cualquier Cosa:**

```tsx
// Texto
<Card>Hello World</Card>

// Elementos
<Card>
  <h1>Title</h1>
  <p>Description</p>
</Card>

// Componentes
<Card>
  <UserProfile user={user} />
</Card>

// Mixto
<Card>
  <h1>Welcome {userName}</h1>
  <UserProfile user={user} />
  <Button onClick={handleClick}>Click</Button>
</Card>
```

**Cuándo Usar `children` vs Props Normales:**

```tsx
// ❌ Menos flexible - Estructura fija
function Card({ title, content }: { title: string; content: string }) {
  return (
    <div className="card">
      <h2>{title}</h2>
      <p>{content}</p>
    </div>
  )
}
// Uso: <Card title="Hello" content="World" />

// ✅ Más flexible - Acepta cualquier contenido
function Card({ children }: { children: React.ReactNode }) {
  return <div className="card">{children}</div>
}
// Uso:
<Card>
  <h2>Hello</h2>
  <p>World</p>
  <Button>Action</Button>
  <img src="..." />
</Card>
```

**Usa children cuando:**
- La estructura del contenido varía entre usos
- Quieres máxima flexibilidad
- Sigues patrones similares a HTML
- Construyes componentes de layout/contenedor

**Usa props normales cuando:**
- El contenido tiene un tipo/estructura específica
- Necesitas validación o procesamiento
- Variaciones limitadas/predecibles

#### Las Props Son Inmutables

**REGLA CRÍTICA:** ¡Nunca mutes las props directamente!

```tsx
function UserCard({ user }: { user: User }) {
  // ❌ NUNCA HAGAS ESTO - Mutar las props
  user.name = 'Modified'  // ¡NO!

  // ✅ Crea un nuevo valor si es necesario
  const displayName = user.name.toUpperCase()

  return <div>{displayName}</div>
}
```

**Por Qué las Props Deben Ser Inmutables:**

1. **Optimización de React:** React asume que las props no cambian para optimizar el renderizado
2. **Previsibilidad:** El componente padre es dueño de los datos
3. **Depuración:** Más fácil rastrear el flujo de datos
4. **Funciones Puras:** Los componentes deberían ser puros (mismas props = misma salida)

**Qué Hacer en Su Lugar:**

```tsx
function UserCard({ users }: { users: string[] }) {
  // ❌ No mutes la prop
  users.push('New user')

  // ✅ Crea un nuevo array
  const updatedUsers = [...users, 'New user']

  // ✅ O usa estado si se necesita modificación
  const [localUsers, setLocalUsers] = useState(users)
}
```

#### Convenciones de Nombrado de Props

```tsx
// ✅ Buenos nombres de props
interface UserCardProps {
  // Props de datos: sustantivos
  user: User
  title: string
  items: Item[]

  // Props booleanas: is/has/can/should
  isActive: boolean
  hasPermission: boolean
  canEdit: boolean

  // Props de callback: on + NombreEvento
  onClick: () => void
  onSubmit: (data: FormData) => void
  onChange: (value: string) => void
  onUserSelect: (user: User) => void
}

// ❌ Evitar
interface BadProps {
  // Nombres vagos
  data: any
  func: Function

  // Nombrado inconsistente
  clickHandler: () => void  // Debería ser onClick
  active: boolean           // Debería ser isActive
}
```

#### Patrones de Props de Componente

##### Patrón 1: Destructuring con Tipos

```tsx
// ✅ Recomendado
interface Props {
  name: string
  age: number
}

function User({ name, age }: Props) {
  return <div>{name} is {age}</div>
}
```

##### Patrón 2: Rest Props (Avanzado)

```tsx
interface ButtonProps {
  label: string
  variant?: 'primary' | 'secondary'
}

function Button({ label, variant, ...rest }: ButtonProps & React.ButtonHTMLAttributes<HTMLButtonElement>) {
  return (
    <button className={`btn-${variant}`} {...rest}>
      {label}
    </button>
  )
}

// Uso - Puede pasar cualquier atributo HTML de botón
<Button
  label="Submit"
  variant="primary"
  disabled={true}
  onClick={handleClick}
  aria-label="Submit form"
/>
```

#### Consejos de Props con TypeScript

```tsx
// Tipo para props de función
type OnClick = () => void
type OnChange = (value: string) => void
type OnSubmit = (data: FormData) => Promise<void>

// Union types para variantes
type Variant = 'primary' | 'secondary' | 'danger'
type Size = 'sm' | 'md' | 'lg'

// Opcional vs requerido
interface Props {
  required: string      // Debe proporcionarse
  optional?: string     // Puede omitirse
  withDefault: string   // Puede proporcionar un valor por defecto en el componente
}

// Tipos de props complejos
interface UserCardProps {
  user: User | null              // Union type
  users: User[]                  // Tipo array
  metadata: Record<string, any>  // Objeto con cualquier clave
  render: (user: User) => JSX.Element  // Render prop
  children: React.ReactNode      // Children
}
```

### Arquitectura de Componentes

#### Patrón de Diseño Atómico (Atomic Design)

Organiza los componentes por nivel de complejidad:

```
src/
├── components/
│   ├── atoms/           # Los componentes más pequeños
│   │   ├── Button/
│   │   │   ├── Button.tsx
│   │   │   ├── Button.css
│   │   │   └── index.ts
│   │   └── Input/
│   │       ├── Input.tsx
│   │       ├── Input.css
│   │       └── index.ts
│   ├── molecules/       # Combinaciones de átomos
│   │   └── FormField/
│   │       ├── FormField.tsx
│   │       └── index.ts
│   ├── organisms/       # Secciones de UI complejas
│   │   └── LoginForm/
│   │       ├── LoginForm.tsx
│   │       └── index.ts
│   └── templates/       # Layouts de página
│       └── DashboardLayout/
│           ├── DashboardLayout.tsx
│           └── index.ts
```

#### Barrel Exports (Archivos Index)

**¿Por qué usar archivos index?**

```typescript
// ❌ Sin barrel exports
import { Button } from './components/Button/Button'
import { Input } from './components/Input/Input'
import { Card } from './components/Card/Card'

// ✅ Con barrel exports
import { Button, Input, Card } from './components'
```

**Creando barrel exports:**

```typescript
// components/Button/index.ts
export { Button } from './Button'
export type { ButtonProps } from './Button'

// components/index.ts
export * from './Button'
export * from './Input'
export * from './Card'
```

### Buenas Prácticas de Componentes

#### 1. Principio de Responsabilidad Única

```typescript
// ❌ Mal - El componente hace demasiado
const UserDashboard = () => {
  const [user, setUser] = useState(null)
  const [posts, setPosts] = useState([])
  const [comments, setComments] = useState([])

  // Demasiada lógica en un solo componente...
  return (
    <div>
      <UserProfile user={user} />
      <UserPosts posts={posts} />
      <UserComments comments={comments} />
    </div>
  )
}

// ✅ Bien - Separar responsabilidades
const UserDashboard = () => {
  return (
    <div>
      <UserProfileContainer />
      <UserPostsContainer />
      <UserCommentsContainer />
    </div>
  )
}
```

#### 2. Evita Funciones en Línea en JSX

```typescript
// ❌ Mal - Crea una nueva función en cada render
const Button = ({ label, parentMethod }: ButtonProps) => {
  return (
    <button onClick={() => parentMethod()}>
      {label}
    </button>
  )
}

// ✅ Bien - Pasa la referencia de la función
const Button = ({ label, parentMethod }: ButtonProps) => {
  return (
    <button onClick={parentMethod}>
      {label}
    </button>
  )
}
```

**¿Por qué?** Crear funciones en cada render:
- Usa más memoria
- Puede causar re-renderizados innecesarios en los componentes hijo
- Impacta el rendimiento en listas grandes

#### 3. Composición de Componentes

```typescript
// ✅ Compón componentes pequeños y reutilizables
interface DashboardProps {
  userName: string
}

const Dashboard = ({ userName }: DashboardProps) => {
  return (
    <div className="dashboard">
      <Header title={`Welcome, ${userName}`} />
      <Sidebar />
      <MainContent>
        <StatsCards />
        <RecentActivity />
      </MainContent>
      <Footer />
    </div>
  )
}
```

### Ejemplo del Mundo Real

#### Componente Completo con TypeScript

```typescript
// components/Button/Button.tsx
import { FC } from 'react'
import './Button.css'

interface ButtonProps {
  label: string
  onClick: () => void
  variant?: 'primary' | 'secondary' | 'danger'
  disabled?: boolean
  loading?: boolean
}

export const Button: FC<ButtonProps> = ({
  label,
  onClick,
  variant = 'primary',
  disabled = false,
  loading = false
}) => {
  const handleClick = () => {
    if (!disabled && !loading) {
      onClick()
    }
  }

  return (
    <button
      className={`btn btn-${variant} ${loading ? 'btn-loading' : ''}`}
      onClick={handleClick}
      disabled={disabled || loading}
      aria-busy={loading}
    >
      {loading ? 'Loading...' : label}
    </button>
  )
}
```

```typescript
// components/Button/index.ts
export { Button } from './Button'
export type { ButtonProps } from './Button'
```

```css
/* components/Button/Button.css */
.btn {
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
  transition: all 0.2s;
}

.btn-primary {
  background-color: #007bff;
  color: white;
}

.btn-secondary {
  background-color: #6c757d;
  color: white;
}

.btn-danger {
  background-color: #dc3545;
  color: white;
}

.btn:hover:not(:disabled) {
  opacity: 0.9;
  transform: translateY(-1px);
}

.btn:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

.btn-loading {
  position: relative;
  color: transparent;
}
```

#### Uso en el Componente Padre

```typescript
// App.tsx
import { useState } from 'react'
import { Button } from './components'

const App = () => {
  const [count, setCount] = useState(0)
  const [loading, setLoading] = useState(false)

  const handleIncrement = () => {
    setLoading(true)
    setTimeout(() => {
      setCount(prev => prev + 1)
      setLoading(false)
    }, 1000)
  }

  return (
    <div className="app">
      <h1>Count is: {count}</h1>
      <Button
        label="Increment"
        onClick={handleIncrement}
        loading={loading}
        variant="primary"
      />
      <Button
        label={`Current: ${count}`}
        onClick={() => console.log(count)}
        variant="secondary"
      />
    </div>
  )
}

export default App
```

### Enfoques de Estilizado de Componentes

#### 1. CSS Modules (Recomendado)

```typescript
// Button.module.css
.button {
  padding: 0.5rem 1rem;
  border-radius: 4px;
}

.primary {
  background-color: blue;
  color: white;
}
```

```typescript
// Button.tsx
import styles from './Button.module.css'

const Button = () => {
  return (
    <button className={`${styles.button} ${styles.primary}`}>
      Click me
    </button>
  )
}
```

#### 2. Styled Components

```typescript
import styled from 'styled-components'

const StyledButton = styled.button<{ variant: 'primary' | 'secondary' }>`
  padding: 0.5rem 1rem;
  background-color: ${props => props.variant === 'primary' ? 'blue' : 'gray'};
  color: white;
  border: none;
  border-radius: 4px;
`

const Button = () => {
  return <StyledButton variant="primary">Click me</StyledButton>
}
```

#### 3. Tailwind CSS

```typescript
const Button = () => {
  return (
    <button className="px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600">
      Click me
    </button>
  )
}
```

#### 4. Estilos en Línea

Los estilos en línea en React son **objetos**, no strings como en HTML.

```typescript
// ❌ Forma HTML (¡no funciona en React!)
<div style="color: red; background-color: blue;">

// ✅ Forma React - Objeto con propiedades en camelCase
<div style={{ color: 'red', backgroundColor: 'blue' }}>

// ✅ Almacenado en una variable
const buttonStyle = {
  backgroundColor: 'blue',
  color: 'white',
  padding: '0.5rem 1rem',
  border: 'none',
  borderRadius: '4px',
  cursor: 'pointer'
}

<button style={buttonStyle}>Click me</button>

// ✅ Estilos dinámicos
const Button = ({ variant }: { variant: 'primary' | 'secondary' }) => {
  const style = {
    backgroundColor: variant === 'primary' ? 'blue' : 'gray',
    color: 'white',
    padding: '0.5rem 1rem'
  }

  return <button style={style}>Click me</button>
}
```

**Reglas Importantes para los Estilos en Línea:**

1. **Sintaxis de objeto, no de string**
2. **Nombres de propiedad en camelCase** (`backgroundColor`, no `background-color`)
3. **Valores string** para la mayoría de las propiedades
4. **Valores numéricos** (sin unidades) para píxeles

```typescript
// Distintos tipos de valores
const styles = {
  // Strings
  color: 'red',
  backgroundColor: '#fff',

  // Números (se asumen píxeles)
  width: 200,        // → '200px'
  padding: 10,       // → '10px'

  // Otras unidades necesitan strings
  width: '50%',
  height: '100vh',
  margin: '1rem'
}
```

**Cuándo Usar Estilos en Línea:**

✅ **Bueno para:**
- Estilos dinámicos basados en props/estado
- Prototipado rápido
- React Native (método principal)
- Estilos específicos del componente

```typescript
// Buen ejemplo: Opacidad dinámica
const Image = ({ loading }: { loading: boolean }) => {
  return (
    <img
      src="..."
      style={{ opacity: loading ? 0.5 : 1 }}
    />
  )
}
```

❌ **Evitar para:**
- Layouts complejos
- Estados hover (usa CSS)
- Media queries
- Pseudo-elementos (::before, ::after)
- Definiciones de estilo grandes

#### 5. Archivos CSS Normales

```typescript
// App.tsx
import './App.css'

function App() {
  return (
    <div className="app">
      <header className="app-header">
        <h1>My App</h1>
      </header>
    </div>
  )
}
```

```css
/* App.css */
.app {
  text-align: center;
}

.app-header {
  background-color: #282c34;
  padding: 20px;
  color: white;
}
```

**⚠️ Precaución:**
- Los estilos son **globales** (pueden afectar a otros componentes)
- Usa convenciones de nombrado (BEM, SMACSS) para evitar conflictos
- Considera CSS Modules para estilos con alcance (scoped)

#### className vs class

```tsx
// ❌ Atributo HTML (no funciona en React)
<div class="container">

// ✅ Prop de React
<div className="container">

// ❌ Error común
<label for="input">

// ✅ Correcto en React
<label htmlFor="input">
```

**¿Por qué `className`?**
- `class` es una palabra reservada en JavaScript
- JSX es JavaScript, no HTML
- React eligió `className` por consistencia

#### Convenciones de Nombrado de CSS

**BEM (Block Element Modifier):**
```tsx
<article className="tw-follow-card">
  <header className="tw-follow-card__header">
    <img className="tw-follow-card__avatar" />
    <div className="tw-follow-card__info">
      <strong className="tw-follow-card__username">Name</strong>
      <span className="tw-follow-card__handle">@handle</span>
    </div>
  </header>
</article>
```

**SUIT CSS:**
```tsx
<div className="tw-FollowCard">
  <div className="tw-FollowCard-header">
    <img className="tw-FollowCard-avatar" />
  </div>
</div>
```

#### Estilos de Contenedor vs Componente

**❌ Mala Práctica:** Añadir espaciado a los componentes

```tsx
// ❌ No hagas esto
const UserCard = () => {
  return (
    <div style={{ marginBottom: '20px' }}>
      {/* Contenido de la tarjeta */}
    </div>
  )
}

// Problema: UserCard siempre tiene margen, incluso cuando no lo quieres
```

**✅ Buena Práctica:** El contenedor controla el espaciado

```tsx
// ✅ El componente no tiene espaciado
const UserCard = () => {
  return <div className="user-card">...</div>
}

// ✅ El contenedor controla el espaciado
const UserList = () => {
  return (
    <section style={{ display: 'flex', flexDirection: 'column', gap: '1rem' }}>
      <UserCard />
      <UserCard />
      <UserCard />
    </section>
  )
}
```

**¿Por qué?**
- Los componentes deberían ser reutilizables
- El espaciado depende del contexto (dónde se usa el componente)
- El contenedor conoce los requisitos del layout

#### className Dinámico

```typescript
// Condicional básico
const Button = ({ active }: { active: boolean }) => {
  return (
    <button className={active ? 'btn btn-active' : 'btn'}>
      Click
    </button>
  )
}

// Template literal (más legible)
const Button = ({ variant, loading }: ButtonProps) => {
  return (
    <button className={`btn btn-${variant} ${loading ? 'btn-loading' : ''}`}>
      Click
    </button>
  )
}

// Usando la librería classnames (recomendada para escenarios complejos)
import classNames from 'classnames'

const Button = ({ variant, loading, disabled }: ButtonProps) => {
  return (
    <button
      className={classNames('btn', {
        [`btn-${variant}`]: variant,
        'btn-loading': loading,
        'btn-disabled': disabled
      })}
    >
      Click
    </button>
  )
}
```

### Buenas Prácticas de Estilizado

1. **Enfoque consistente** - Elige un método de estilizado por proyecto
2. **Estilos con alcance de componente** - Evita la contaminación de estilos globales
3. **Separación de responsabilidades** - El contenedor gestiona el espaciado, el componente gestiona la apariencia
4. **Mobile-first** - Diseña para móvil, mejora para escritorio
5. **Accesibilidad** - Usa HTML semántico, contraste adecuado, estados de foco

```typescript
// ❌ Mal - Todo en línea, difícil de mantener
<button style={{
      backgroundColor: 'blue',
      color: 'white',
      padding: '0.5rem 1rem'
    }}>
      Click me
    </button>
  )
}
```

---

## 6. useState - Gestión de Estado

`useState` es el hook fundamental para gestionar el estado de un componente en React.

### Uso Básico

#### Declarando Estado

```typescript
import { useState } from 'react'

function Counter() {
  // Sintaxis: const [state, setState] = useState(valorInicial)
  const [count, setCount] = useState(0)

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>
        Increment
      </button>
    </div>
  )
}
```

#### Con TypeScript

```typescript
// Tipos primitivos (inferidos)
const [count, setCount] = useState(0) // number
const [name, setName] = useState('') // string
const [isOpen, setIsOpen] = useState(false) // boolean

// Tipos complejos (explícitos)
interface User {
  id: number
  name: string
  email: string
}

const [user, setUser] = useState<User | null>(null)

// Array
const [items, setItems] = useState<string[]>([])

// Objeto
interface FormData {
  username: string
  password: string
}

const [formData, setFormData] = useState<FormData>({
  username: '',
  password: ''
})
```

### Patrones de Actualización de Estado

#### Actualización Directa

```typescript
const [count, setCount] = useState(0)

// ❌ Mal - No mutes el estado directamente
count = count + 1 // ¡Esto no disparará un re-renderizado!

// ✅ Correcto - Usa la función setter
setCount(count + 1)
```

#### Actualización Funcional

```typescript
const [count, setCount] = useState(0)

// ❌ Puede ser incorrecto con actualizaciones rápidas
setCount(count + 1)

// ✅ Mejor - Usa la actualización funcional
setCount(prevCount => prevCount + 1)
```

**¿Por qué actualizaciones funcionales?**

```typescript
// Problema con las actualizaciones directas:
const handleMultipleUpdates = () => {
  setCount(count + 1) // count = 0, establece a 1
  setCount(count + 1) // count sigue en 0, establece a 1 de nuevo
  setCount(count + 1) // count sigue en 0, establece a 1 de nuevo
  // Resultado: count = 1 (¡se esperaba 3!)
}

// Solución con actualizaciones funcionales:
const handleMultipleUpdates = () => {
  setCount(prev => prev + 1) // 0 + 1 = 1
  setCount(prev => prev + 1) // 1 + 1 = 2
  setCount(prev => prev + 1) // 2 + 1 = 3
  // Resultado: count = 3 ✓
}
```

### Trabajando con Objetos

#### Actualizando el Estado de un Objeto

```typescript
interface User {
  name: string
  email: string
  age: number
}

const [user, setUser] = useState<User>({
  name: 'John',
  email: 'john@example.com',
  age: 30
})

// ❌ Mal - Muta el estado
user.name = 'Jane'
setUser(user)

// ❌ Mal - Pierde las otras propiedades
setUser({ name: 'Jane' })

// ✅ Correcto - El operador spread preserva las otras propiedades
setUser({ ...user, name: 'Jane' })

// ✅ También correcto - Actualización funcional
setUser(prevUser => ({
  ...prevUser,
  name: 'Jane'
}))
```

#### Actualizaciones de Objetos Anidados

```typescript
interface Address {
  street: string
  city: string
  country: string
}

interface User {
  name: string
  address: Address
}

const [user, setUser] = useState<User>({
  name: 'John',
  address: {
    street: '123 Main St',
    city: 'New York',
    country: 'USA'
  }
})

// ✅ Actualizar el objeto anidado
setUser(prevUser => ({
  ...prevUser,
  address: {
    ...prevUser.address,
    city: 'Los Angeles'
  }
}))
```

### Trabajando con Arrays

#### Añadiendo Elementos

```typescript
const [items, setItems] = useState<string[]>([])

// ❌ Mal - Muta el estado
items.push('new item')
setItems(items)

// ✅ Correcto - Operador spread
setItems([...items, 'new item'])

// ✅ Añadir al principio
setItems(['new item', ...items])

// ✅ Añadir en una posición específica
const insertAt = 2
setItems([
  ...items.slice(0, insertAt),
  'new item',
  ...items.slice(insertAt)
])
```

#### Eliminando Elementos

```typescript
const [items, setItems] = useState<string[]>(['a', 'b', 'c'])

// Eliminar por índice
const removeAt = 1
setItems(items.filter((_, index) => index !== removeAt))

// Eliminar por valor
setItems(items.filter(item => item !== 'b'))
```

#### Actualizando Elementos

```typescript
interface Todo {
  id: number
  text: string
  completed: boolean
}

const [todos, setTodos] = useState<Todo[]>([
  { id: 1, text: 'Learn React', completed: false },
  { id: 2, text: 'Build app', completed: false }
])

// Alternar la completitud de un todo
const toggleTodo = (id: number) => {
  setTodos(todos.map(todo =>
    todo.id === id
      ? { ...todo, completed: !todo.completed }
      : todo
  ))
}
```

### Inicialización Perezosa (Lazy)

```typescript
// ❌ Mal - Ejecuta el cálculo costoso en cada render
const [data, setData] = useState(expensiveComputation())

// ✅ Bien - Se ejecuta solo una vez en el render inicial
const [data, setData] = useState(() => expensiveComputation())

// Ejemplo: Leer desde localStorage
const [user, setUser] = useState<User | null>(() => {
  const saved = localStorage.getItem('user')
  return saved ? JSON.parse(saved) : null
})
```

### Patrones Comunes

#### Alternar Booleano

```typescript
const [isOpen, setIsOpen] = useState(false)

// ❌ Verboso
setIsOpen(!isOpen)

// ✅ Conciso con actualización funcional
setIsOpen(prev => !prev)
```

#### Incrementar/Decrementar

```typescript
const [count, setCount] = useState(0)

const increment = () => setCount(prev => prev + 1)
const decrement = () => setCount(prev => prev - 1)
const reset = () => setCount(0)
```

#### Manejo de Formularios

```typescript
interface FormState {
  username: string
  email: string
  password: string
}

const [formData, setFormData] = useState<FormState>({
  username: '',
  email: '',
  password: ''
})

const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
  const { name, value } = e.target
  setFormData(prev => ({
    ...prev,
    [name]: value
  }))
}

return (
  <form>
    <input
      name="username"
      value={formData.username}
      onChange={handleChange}
    />
    <input
      name="email"
      value={formData.email}
      onChange={handleChange}
    />
    <input
      name="password"
      type="password"
      value={formData.password}
      onChange={handleChange}
    />
  </form>
)
```

### Las Actualizaciones de Estado Son Asíncronas

```typescript
const [count, setCount] = useState(0)

const handleClick = () => {
  setCount(count + 1)
  console.log(count) // ¡Sigue en 0! El estado aún no se ha actualizado
}

// Solución: Usa useEffect para reaccionar a los cambios de estado
useEffect(() => {
  console.log('Count changed:', count)
}, [count])
```

### Múltiples Variables de Estado vs Un Solo Objeto

```typescript
// ❌ Múltiples estados relacionados
const [firstName, setFirstName] = useState('')
const [lastName, setLastName] = useState('')
const [email, setEmail] = useState('')
const [age, setAge] = useState(0)

// ✅ Mejor - Agrupar el estado relacionado
const [user, setUser] = useState({
  firstName: '',
  lastName: '',
  email: '',
  age: 0
})

// Pero mantén separado el estado no relacionado
const [isLoading, setIsLoading] = useState(false) // Responsabilidad separada
```

### Buenas Prácticas

#### 1. No Almacenes Valores Derivados

```typescript
// ❌ Mal - Duplica datos
const [items, setItems] = useState<Item[]>([])
const [itemCount, setItemCount] = useState(0) // ¡Redundante!

// ✅ Bien - Calcula los valores derivados
const [items, setItems] = useState<Item[]>([])
const itemCount = items.length // Calculado en cada render
```

#### 2. Usa Múltiples useState para Datos No Relacionados

```typescript
// ✅ Bien - Separar responsabilidades
const [user, setUser] = useState<User | null>(null)
const [theme, setTheme] = useState<'light' | 'dark'>('light')
const [isMenuOpen, setIsMenuOpen] = useState(false)
```

#### 3. Colocación del Estado (State Colocation)

```typescript
// ❌ Mal - Estado demasiado alto en el árbol
function App() {
  const [modalContent, setModalContent] = useState('')

  return (
    <>
      <Header />
      <Dashboard />
      <Modal content={modalContent} /> {/* Solo Modal necesita esto */}
    </>
  )
}

// ✅ Bien - Estado cerca de donde se usa
function Modal() {
  const [content, setContent] = useState('')

  return <div>{content}</div>
}
```

---

## 7. useEffect - Efectos Secundarios

`useEffect` maneja los efectos secundarios en los componentes funcionales - operaciones que van más allá del componente.

### ¿Qué Son los Efectos Secundarios?

Los efectos secundarios son operaciones que:
- Obtienen datos de APIs
- Interactúan con APIs del navegador (localStorage, DOM)
- Configuran suscripciones o temporizadores
- Cambian manualmente el DOM
- Registran en la consola

### Sintaxis Básica

```typescript
import { useEffect } from 'react'

useEffect(() => {
  // El código del efecto se ejecuta aquí

  return () => {
    // Código de limpieza (opcional)
  }
}, [dependencies])
```

### Patrones del Array de Dependencias

#### 1. Sin Dependencias - Se Ejecuta en Cada Render

```typescript
// ⚠️ Se ejecuta después de cada render (rara vez necesario)
useEffect(() => {
  console.log('Component rendered')
})
```

#### 2. Dependencias Vacías - Se Ejecuta Una Vez al Montar

```typescript
// ✅ Se ejecuta una vez cuando el componente se monta
useEffect(() => {
  console.log('Component mounted')

  return () => {
    console.log('Component will unmount')
  }
}, [])
```

#### 3. Con Dependencias - Se Ejecuta Cuando las Dependencias Cambian

```typescript
const [count, setCount] = useState(0)
const [name, setName] = useState('')

// Se ejecuta cuando count cambia
useEffect(() => {
  console.log('Count changed:', count)
}, [count])

// Se ejecuta cuando count o name cambian
useEffect(() => {
  console.log('Count or name changed')
}, [count, name])
```

### Casos de Uso Comunes

#### Obtención de Datos

```typescript
interface User {
  id: number
  name: string
  email: string
}

function UserProfile({ userId }: { userId: number }) {
  const [user, setUser] = useState<User | null>(null)
  const [loading, setLoading] = useState(true)
  const [error, setError] = useState<string | null>(null)

  useEffect(() => {
    const fetchUser = async () => {
      try {
        setLoading(true)
        setError(null)

        const response = await fetch(`/api/users/${userId}`)
        if (!response.ok) throw new Error('Failed to fetch')

        const data = await response.json()
        setUser(data)
      } catch (err) {
        setError(err instanceof Error ? err.message : 'An error occurred')
      } finally {
        setLoading(false)
      }
    }

    fetchUser()
  }, [userId]) // Volver a obtener cuando userId cambia

  if (loading) return <div>Loading...</div>
  if (error) return <div>Error: {error}</div>
  if (!user) return <div>No user found</div>

  return (
    <div>
      <h1>{user.name}</h1>
      <p>{user.email}</p>
    </div>
  )
}
```

#### Event Listeners

```typescript
function WindowSize() {
  const [size, setSize] = useState({
    width: window.innerWidth,
    height: window.innerHeight
  })

  useEffect(() => {
    const handleResize = () => {
      setSize({
        width: window.innerWidth,
        height: window.innerHeight
      })
    }

    // Añadir el event listener
    window.addEventListener('resize', handleResize)

    // Limpieza: eliminar el event listener
    return () => {
      window.removeEventListener('resize', handleResize)
    }
  }, []) // Array vacío = ejecutar una vez al montar

  return (
    <div>
      Window size: {size.width} x {size.height}
    </div>
  )
}
```

#### Temporizadores e Intervalos

```typescript
function Timer() {
  const [seconds, setSeconds] = useState(0)
  const [isRunning, setIsRunning] = useState(false)

  useEffect(() => {
    if (!isRunning) return

    const interval = setInterval(() => {
      setSeconds(prev => prev + 1)
    }, 1000)

    // Limpieza: limpiar el intervalo
    return () => clearInterval(interval)
  }, [isRunning]) // Volver a ejecutar cuando isRunning cambia

  return (
    <div>
      <p>Seconds: {seconds}</p>
      <button onClick={() => setIsRunning(!isRunning)}>
        {isRunning ? 'Stop' : 'Start'}
      </button>
      <button onClick={() => setSeconds(0)}>Reset</button>
    </div>
  )
}
```

#### Sincronización con LocalStorage

```typescript
function usePersistentState<T>(key: string, initialValue: T) {
  // Inicializar desde localStorage
  const [value, setValue] = useState<T>(() => {
    const saved = localStorage.getItem(key)
    return saved ? JSON.parse(saved) : initialValue
  })

  // Sincronizar a localStorage cuando el valor cambia
  useEffect(() => {
    localStorage.setItem(key, JSON.stringify(value))
  }, [key, value])

  return [value, setValue] as const
}

// Uso
function App() {
  const [theme, setTheme] = usePersistentState('theme', 'light')

  return (
    <div className={theme}>
      <button onClick={() => setTheme(theme === 'light' ? 'dark' : 'light')}>
        Toggle Theme
      </button>
    </div>
  )
}
```

### Funciones de Limpieza (Cleanup)

#### ¿Por Qué Limpiar?

La limpieza previene:
- Fugas de memoria
- Datos obsoletos (stale)
- Condiciones de carrera (race conditions)
- Suscripciones duplicadas

```typescript
// ❌ Sin limpieza - ¡Fuga de memoria!
useEffect(() => {
  const interval = setInterval(() => {
    console.log('Running...')
  }, 1000)
  // ¡El intervalo continúa incluso después de que el componente se desmonte!
}, [])

// ✅ Con limpieza
useEffect(() => {
  const interval = setInterval(() => {
    console.log('Running...')
  }, 1000)

  return () => {
    clearInterval(interval) // Detener el intervalo al desmontar
  }
}, [])
```

#### Limpieza Asíncrona con AbortController

```typescript
function SearchResults({ query }: { query: string }) {
  const [results, setResults] = useState([])

  useEffect(() => {
    const controller = new AbortController()

    const fetchResults = async () => {
      try {
        const response = await fetch(`/api/search?q=${query}`, {
          signal: controller.signal // Pasar la señal de abortar
        })
        const data = await response.json()
        setResults(data)
      } catch (error) {
        if (error.name === 'AbortError') {
          console.log('Fetch aborted')
        }
      }
    }

    fetchResults()

    // Limpieza: abortar el fetch si el componente se desmonta o query cambia
    return () => {
      controller.abort()
    }
  }, [query])

  return <div>{/* Renderizar resultados */}</div>
}
```

### Errores Comunes

#### 1. Dependencias Faltantes

```typescript
// ❌ ESLint advertirá - dependencia faltante
const [count, setCount] = useState(0)

useEffect(() => {
  console.log(count) // Usa count pero no está en las dependencias
}, []) // ¡Falta count!

// ✅ Incluye todas las variables usadas
useEffect(() => {
  console.log(count)
}, [count])
```

#### 2. Dependencias de Objeto/Función

```typescript
// ❌ Bucle infinito - objeto creado en cada render
function Component() {
  const config = { api: '/api/data' } // Nuevo objeto en cada render

  useEffect(() => {
    fetch(config.api)
  }, [config]) // ¡El efecto se ejecuta en cada render!
}

// ✅ Mueve el objeto fuera o usa useMemo
const config = { api: '/api/data' } // Fuera del componente

function Component() {
  useEffect(() => {
    fetch(config.api)
  }, []) // config es estable
}
```

#### 3. Actualizar el Estado desde las Props

```typescript
// ❌ Crea un bucle de sincronización
function Component({ value }: { value: number }) {
  const [state, setState] = useState(value)

  useEffect(() => {
    setState(value) // Puede causar problemas
  }, [value])
}

// ✅ Simplemente usa la prop directamente
function Component({ value }: { value: number }) {
  return <div>{value}</div>
}

// ✅ O usa estado solo para modificaciones
function Component({ initialValue }: { initialValue: number }) {
  const [value, setValue] = useState(initialValue)
  // initialValue solo se usa para la inicialización
}
```

### Mejoras de React 19 para useEffect

React 19 mejora el comportamiento de `useEffect` con una limpieza más estricta y un mejor manejo asíncrono:

```typescript
// La sintaxis sigue siendo la misma en React 19
useEffect(() => {
  // Código del efecto
  return () => {
    // Limpieza
  }
}, [deps])

// Pero el comportamiento está mejorado:
// - Aplicación de limpieza más estricta (previene fugas de memoria)
// - Mejor manejo de los efectos asíncronos
// - Orden de ejecución más predecible
// - Mejores advertencias en modo desarrollo
```

**Cambios Clave:**
1. **Limpieza más estricta:** Los efectos deben limpiar correctamente o aparecerán advertencias
2. **Efectos asíncronos:** Mejor manejo cuando el componente se desmonta durante operaciones asíncronas
3. **Doble renderizado en Dev:** El doble renderizado de React 18 en Strict Mode continúa en React 19
4. **Mejores mensajes de error:** Información de depuración más útil

**Nota de Migración:** Todos los patrones de `useEffect` de esta guía funcionan tanto en React 18 como en React 19. Los nuevos patrones de obtención de datos usando el hook `use()` (ver [Sección 10](#10-nuevas-funcionalidades-de-react-19)) proporcionan alternativas a `useEffect` para los datos asíncronos.

---

## 8. Custom Hooks

Los custom hooks son la funcionalidad más potente para la reutilización de código en React. Te permiten extraer la lógica de un componente en funciones reutilizables.

### ¿Qué Son los Custom Hooks?

- Funciones que empiezan con `use`
- Pueden llamar a otros hooks en su interior
- Encapsulan lógica con estado
- Reutilizables entre componentes

### Custom Hook Básico

```typescript
// hooks/useCounter.ts
import { useState } from 'react'

export const useCounter = (initialValue = 0) => {
  const [count, setCount] = useState(initialValue)

  const increment = () => setCount(prev => prev + 1)
  const decrement = () => setCount(prev => prev - 1)
  const reset = () => setCount(initialValue)

  return { count, increment, decrement, reset }
}

// Uso en un componente
function CounterApp() {
  const { count, increment, decrement, reset } = useCounter(0)

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>+</button>
      <button onClick={decrement}>-</button>
      <button onClick={reset}>Reset</button>
    </div>
  )
}
```

### Custom Hooks Comunes

#### useFetch

```typescript
interface UseFetchResult<T> {
  data: T | null
  loading: boolean
  error: string | null
  refetch: () => void
}

export function useFetch<T>(url: string): UseFetchResult<T> {
  const [data, setData] = useState<T | null>(null)
  const [loading, setLoading] = useState(true)
  const [error, setError] = useState<string | null>(null)

  const fetchData = async () => {
    try {
      setLoading(true)
      setError(null)

      const response = await fetch(url)
      if (!response.ok) throw new Error(`HTTP error! status: ${response.status}`)

      const json = await response.json()
      setData(json)
    } catch (err) {
      setError(err instanceof Error ? err.message : 'An error occurred')
    } finally {
      setLoading(false)
    }
  }

  useEffect(() => {
    fetchData()
  }, [url])

  return { data, loading, error, refetch: fetchData }
}

// Uso
function UserList() {
  const { data: users, loading, error, refetch } = useFetch<User[]>('/api/users')

  if (loading) return <div>Loading...</div>
  if (error) return <div>Error: {error}</div>

  return (
    <div>
      {users?.map(user => <div key={user.id}>{user.name}</div>)}
      <button onClick={refetch}>Refresh</button>
    </div>
  )
}
```

#### useLocalStorage

```typescript
export function useLocalStorage<T>(
  key: string,
  initialValue: T
): [T, (value: T) => void] {
  // Obtener el valor inicial de localStorage o usar initialValue
  const [storedValue, setStoredValue] = useState<T>(() => {
    try {
      const item = window.localStorage.getItem(key)
      return item ? JSON.parse(item) : initialValue
    } catch (error) {
      console.error('Error reading from localStorage:', error)
      return initialValue
    }
  })

  // Actualizar localStorage cuando el valor cambia
  const setValue = (value: T) => {
    try {
      setStoredValue(value)
      window.localStorage.setItem(key, JSON.stringify(value))
    } catch (error) {
      console.error('Error writing to localStorage:', error)
    }
  }

  return [storedValue, setValue]
}

// Uso
function App() {
  const [theme, setTheme] = useLocalStorage('theme', 'light')

  return (
    <div className={theme}>
      <button onClick={() => setTheme(theme === 'light' ? 'dark' : 'light')}>
        Toggle Theme
      </button>
    </div>
  )
}
```

#### useDebounce

```typescript
export function useDebounce<T>(value: T, delay: number): T {
  const [debouncedValue, setDebouncedValue] = useState<T>(value)

  useEffect(() => {
    const handler = setTimeout(() => {
      setDebouncedValue(value)
    }, delay)

    return () => {
      clearTimeout(handler)
    }
  }, [value, delay])

  return debouncedValue
}

// Uso para una búsqueda
function SearchComponent() {
  const [searchTerm, setSearchTerm] = useState('')
  const debouncedSearchTerm = useDebounce(searchTerm, 500)

  useEffect(() => {
    if (debouncedSearchTerm) {
      // La llamada a la API solo ocurre 500ms después de que el usuario deja de escribir
      fetch(`/api/search?q=${debouncedSearchTerm}`)
    }
  }, [debouncedSearchTerm])

  return (
    <input
      value={searchTerm}
      onChange={(e) => setSearchTerm(e.target.value)}
      placeholder="Search..."
    />
  )
}
```

#### useToggle

```typescript
export function useToggle(initialValue = false): [boolean, () => void] {
  const [value, setValue] = useState(initialValue)

  const toggle = () => setValue(prev => !prev)

  return [value, toggle]
}

// Uso
function Modal() {
  const [isOpen, toggleModal] = useToggle(false)

  return (
    <>
      <button onClick={toggleModal}>Open Modal</button>
      {isOpen && (
        <div className="modal">
          <button onClick={toggleModal}>Close</button>
        </div>
      )}
    </>
  )
}
```

#### useWindowSize

```typescript
interface WindowSize {
  width: number
  height: number
}

export function useWindowSize(): WindowSize {
  const [size, setSize] = useState<WindowSize>({
    width: window.innerWidth,
    height: window.innerHeight
  })

  useEffect(() => {
    const handleResize = () => {
      setSize({
        width: window.innerWidth,
        height: window.innerHeight
      })
    }

    window.addEventListener('resize', handleResize)
    return () => window.removeEventListener('resize', handleResize)
  }, [])

  return size
}

// Uso
function ResponsiveComponent() {
  const { width } = useWindowSize()

  return (
    <div>
      {width < 768 ? (
        <MobileLayout />
      ) : (
        <DesktopLayout />
      )}
    </div>
  )
}
```

### Buenas Prácticas

#### 1. Empieza Siempre con "use"

```typescript
// ✅ Bien
export const useCounter = () => { /* ... */ }
export const useAuth = () => { /* ... */ }

// ❌ Mal - No se reconocen como hooks
export const counter = () => { /* ... */ }
export const getAuth = () => { /* ... */ }
```

#### 2. Devuelve Objetos para Múltiples Valores

```typescript
// ✅ Bien - Retornos nombrados
export const useCounter = () => {
  return { count, increment, decrement }
}

// Uso con destructuring
const { count, increment } = useCounter()

// ❌ Menos flexible - Retornos en array
export const useCounter = () => {
  return [count, increment, decrement]
}
```

#### 3. Tipa Tus Custom Hooks

```typescript
// ✅ Bien - Totalmente tipado
interface UseCounterReturn {
  count: number
  increment: () => void
  decrement: () => void
  reset: () => void
}

export const useCounter = (initialValue = 0): UseCounterReturn => {
  // Implementación
}
```

---

## 9. Patrón de Composición

La composición es un patrón potente para construir componentes flexibles y reutilizables.

### ¿Qué es la Composición?

En lugar de usar props para todo, compón los componentes como bloques de LEGO.

### Composición Básica

```typescript
// ❌ Enfoque basado en props (menos flexible)
interface CardProps {
  title: string
  content: string
  footer: string
}

function Card({ title, content, footer }: CardProps) {
  return (
    <div className="card">
      <h2>{title}</h2>
      <p>{content}</p>
      <div>{footer}</div>
    </div>
  )
}

// ✅ Enfoque de composición (más flexible)
interface CardProps {
  children: React.ReactNode
}

function Card({ children }: CardProps) {
  return <div className="card">{children}</div>
}

function CardHeader({ children }: CardProps) {
  return <div className="card-header">{children}</div>
}

function CardBody({ children }: CardProps) {
  return <div className="card-body">{children}</div>
}

function CardFooter({ children }: CardProps) {
  return <div className="card-footer">{children}</div>
}

// Uso - ¡Mucho más flexible!
function App() {
  return (
    <Card>
      <CardHeader>
        <h2>User Profile</h2>
      </CardHeader>
      <CardBody>
        <p>Name: John Doe</p>
        <button>Edit</button>
      </CardBody>
      <CardFooter>
        <small>Last updated: Today</small>
      </CardFooter>
    </Card>
  )
}
```

### Patrón de Componentes Compuestos (Compound Components)

```typescript
// Modal.tsx
interface ModalContextValue {
  isOpen: boolean
  open: () => void
  close: () => void
}

const ModalContext = createContext<ModalContextValue | null>(null)

export function Modal({ children }: { children: React.ReactNode }) {
  const [isOpen, setIsOpen] = useState(false)

  const value = {
    isOpen,
    open: () => setIsOpen(true),
    close: () => setIsOpen(false)
  }

  return (
    <ModalContext.Provider value={value}>
      {children}
    </ModalContext.Provider>
  )
}

Modal.Trigger = function ModalTrigger({ children }: { children: React.ReactNode }) {
  const context = useContext(ModalContext)
  if (!context) throw new Error('Modal.Trigger must be used within Modal')

  return <button onClick={context.open}>{children}</button>
}

Modal.Content = function ModalContent({ children }: { children: React.ReactNode }) {
  const context = useContext(ModalContext)
  if (!context) throw new Error('Modal.Content must be used within Modal')

  if (!context.isOpen) return null

  return (
    <div className="modal-overlay" onClick={context.close}>
      <div className="modal-content" onClick={(e) => e.stopPropagation()}>
        {children}
      </div>
    </div>
  )
}

Modal.Close = function ModalClose({ children }: { children: React.ReactNode }) {
  const context = useContext(ModalContext)
  if (!context) throw new Error('Modal.Close must be used within Modal')

  return <button onClick={context.close}>{children}</button>
}

// Uso
function App() {
  return (
    <Modal>
      <Modal.Trigger>
        Open Modal
      </Modal.Trigger>

      <Modal.Content>
        <h2>Modal Title</h2>
        <p>Modal content goes here...</p>
        <Modal.Close>
          Close
        </Modal.Close>
      </Modal.Content>
    </Modal>
  )
}
```

---

## 10. Nuevas Funcionalidades de React 19

React 19 introduce potentes nuevas funcionalidades para construir aplicaciones web modernas. Aunque estas funcionalidades son opcionales y los patrones de React 18 siguen funcionando, proporcionan mejor rendimiento y experiencia de desarrollo.

### Nota de Compatibilidad

**Esta guía enseña patrones compatibles tanto con React 18 como con React 19.**
- Todos los conceptos fundamentales (componentes, hooks, estado) siguen siendo los mismos
- Las funcionalidades de React 19 son aditivas, no rompen nada
- Las apps de producción pueden actualizarse gradualmente
- Frameworks como Next.js pueden adoptar estas funcionalidades a distintos ritmos

---

### Nuevos Hooks en React 19

#### 1. Hook `use()` - Lectura de Recursos

El hook `use()` permite a los componentes leer recursos como Promises y Context de forma síncrona durante el render.

```typescript
import { use } from 'react'

// Leer una Promise
async function fetchUser(id: string) {
  const res = await fetch(`/api/users/${id}`)
  return res.json()
}

function UserProfile({ userPromise }: { userPromise: Promise<User> }) {
  // use() suspende el componente hasta que la Promise se resuelva
  const user = use(userPromise)

  return <div>{user.name}</div>
}

// Uso con Suspense
function App() {
  const userPromise = fetchUser('123')

  return (
    <Suspense fallback={<div>Loading...</div>}>
      <UserProfile userPromise={userPromise} />
    </Suspense>
  )
}
```

**Beneficios Clave:**
- ✅ Simplifica la obtención de datos asíncronos
- ✅ Funciona con Suspense para los estados de carga
- ✅ Se puede usar condicionalmente (¡a diferencia de los hooks!)
- ✅ Más limpio que useEffect para la carga de datos

**Leer Context:**
```typescript
import { use, createContext } from 'react'

const ThemeContext = createContext('light')

function Button() {
  // use() puede leer context (alternativa a useContext)
  const theme = use(ThemeContext)
  return <button className={theme}>Click me</button>
}
```

**Diferencia Importante con los Hooks:**
```typescript
// ✅ use() puede ser condicional
function Component({ shouldLoad }: { shouldLoad: boolean }) {
  if (shouldLoad) {
    const data = use(dataPromise) // ¡OK!
  }
}

// ❌ Los hooks normales no pueden ser condicionales
function Component({ shouldLoad }: { shouldLoad: boolean }) {
  if (shouldLoad) {
    const [state, setState] = useState(0) // ¡ERROR!
  }
}
```

---

#### 2. `useOptimistic()` - Actualizaciones Optimistas

Actualiza la UI de forma optimista mientras esperas a que las operaciones asíncronas se completen.

```typescript
import { useOptimistic, useState } from 'react'

interface Message {
  id: string
  text: string
  sending?: boolean
}

function ChatRoom() {
  const [messages, setMessages] = useState<Message[]>([])
  const [optimisticMessages, addOptimisticMessage] = useOptimistic(
    messages,
    (state, newMessage: string) => [
      ...state,
      { id: Date.now().toString(), text: newMessage, sending: true }
    ]
  )

  const sendMessage = async (text: string) => {
    // Mostrar la actualización optimista inmediatamente
    addOptimisticMessage(text)

    try {
      // Enviar al servidor
      const response = await fetch('/api/messages', {
        method: 'POST',
        body: JSON.stringify({ text })
      })
      const newMessage = await response.json()

      // Reemplazar el mensaje optimista con el real
      setMessages(prev => [...prev, newMessage])
    } catch (error) {
      // La actualización optimista se revertirá automáticamente
      console.error('Failed to send message')
    }
  }

  return (
    <div>
      {optimisticMessages.map(msg => (
        <div key={msg.id} style={{ opacity: msg.sending ? 0.5 : 1 }}>
          {msg.text}
        </div>
      ))}
      <form onSubmit={(e) => {
        e.preventDefault()
        sendMessage(e.currentTarget.message.value)
      }}>
        <input name="message" />
        <button type="submit">Send</button>
      </form>
    </div>
  )
}
```

**Casos de Uso:**
- ✅ Aplicaciones de chat
- ✅ Likes/comentarios de redes sociales
- ✅ Envíos de formularios
- ✅ Actualizaciones del carrito de compras
- ✅ Cualquier UI que necesite retroalimentación instantánea

---

#### 3. `useFormStatus()` - Estado de Envío de Formularios

Accede al estado de envío de un formulario desde dentro de los componentes del formulario.

```typescript
import { useFormStatus } from 'react-dom'

function SubmitButton() {
  const { pending, data, method, action } = useFormStatus()

  return (
    <button type="submit" disabled={pending}>
      {pending ? 'Submitting...' : 'Submit'}
    </button>
  )
}

function LoginForm() {
  const handleSubmit = async (formData: FormData) => {
    const username = formData.get('username')
    const password = formData.get('password')

    // Simular llamada a la API
    await new Promise(resolve => setTimeout(resolve, 2000))
    console.log('Logged in:', username)
  }

  return (
    <form action={handleSubmit}>
      <input name="username" required />
      <input name="password" type="password" required />
      {/* SubmitButton conoce automáticamente el estado del formulario */}
      <SubmitButton />
    </form>
  )
}
```

**Beneficios:**
- ✅ Sin gestión manual del estado de carga
- ✅ Estado deshabilitado automático durante el envío
- ✅ Funciona con server actions (Next.js)

---

#### 4. `useFormState()` - Mejora Progresiva

Maneja el estado del formulario con server actions mientras soporta escenarios sin JS.

```typescript
import { useFormState } from 'react-dom'

interface FormState {
  message: string
  errors?: Record<string, string>
}

async function createTodo(
  prevState: FormState,
  formData: FormData
): Promise<FormState> {
  const title = formData.get('title') as string

  if (!title) {
    return {
      message: 'Error',
      errors: { title: 'Title is required' }
    }
  }

  // Server action
  await fetch('/api/todos', {
    method: 'POST',
    body: JSON.stringify({ title })
  })

  return { message: 'Todo created!' }
}

function TodoForm() {
  const [state, formAction] = useFormState(createTodo, { message: '' })

  return (
    <form action={formAction}>
      <input name="title" />
      {state.errors?.title && <p>{state.errors.title}</p>}
      <button type="submit">Add Todo</button>
      {state.message && <p>{state.message}</p>}
    </form>
  )
}
```

---

### Actions (Manejo de Formularios Integrado)

React 19 introduce soporte nativo para funciones asíncronas en los formularios.

```typescript
function SearchForm() {
  const [results, setResults] = useState([])
  const [isPending, startTransition] = useTransition()

  // Función de action
  async function search(formData: FormData) {
    const query = formData.get('query') as string

    const response = await fetch(`/api/search?q=${query}`)
    const data = await response.json()

    startTransition(() => {
      setResults(data)
    })
  }

  return (
    <form action={search}>
      <input name="query" placeholder="Search..." />
      <button type="submit">Search</button>
      {isPending && <div>Searching...</div>}
      <ul>
        {results.map(item => <li key={item.id}>{item.title}</li>)}
      </ul>
    </form>
  )
}
```

**Ventajas sobre los formularios tradicionales:**
- ✅ No se necesita `onSubmit` ni `preventDefault()`
- ✅ Funciona sin JavaScript (mejora progresiva)
- ✅ Estados de carga integrados con `useFormStatus()`
- ✅ Código más limpio y declarativo

---

### Soporte de Metadatos del Documento

React 19 permite renderizar las etiquetas `<title>`, `<meta>` y `<link>` directamente en los componentes.

```typescript
function ProductPage({ product }: { product: Product }) {
  return (
    <>
      {/* Estas se elevan automáticamente al <head> */}
      <title>{product.name} - My Store</title>
      <meta name="description" content={product.description} />
      <meta property="og:title" content={product.name} />
      <meta property="og:image" content={product.image} />
      <link rel="canonical" href={`https://mystore.com/products/${product.id}`} />

      {/* Contenido normal del componente */}
      <div>
        <h1>{product.name}</h1>
        <p>{product.description}</p>
      </div>
    </>
  )
}
```

**Beneficios:**
- ✅ No se necesita react-helmet ni librerías externas
- ✅ Metadatos con alcance de componente
- ✅ Mejor SEO sin frameworks
- ✅ Código de componente más limpio

---

### Ref como Prop

En React 19, `ref` se puede pasar como una prop normal (¡no más `forwardRef`!).

```typescript
// React 18 - forwardRef complejo
import { forwardRef } from 'react'

const Input = forwardRef<HTMLInputElement, InputProps>(
  (props, ref) => {
    return <input ref={ref} {...props} />
  }
)

// React 19 - Prop simple
interface InputProps {
  ref?: React.Ref<HTMLInputElement>
  placeholder?: string
}

function Input({ ref, ...props }: InputProps) {
  return <input ref={ref} {...props} />
}

// Uso (igual en ambas versiones)
function Form() {
  const inputRef = useRef<HTMLInputElement>(null)

  return <Input ref={inputRef} />
}
```

**Patrones Simplificados:**
- ✅ No se necesita el envoltorio `forwardRef`
- ✅ Tipos de TypeScript más limpios
- ✅ La ref es solo otra prop más

---

### Mejor Reporte de Errores

React 19 proporciona mejores mensajes de error y depuración:

```typescript
// Mejores error boundaries
class ErrorBoundary extends React.Component {
  state = { hasError: false, error: null }

  static getDerivedStateFromError(error: Error) {
    return { hasError: true, error }
  }

  componentDidCatch(error: Error, errorInfo: React.ErrorInfo) {
    // React 19 proporciona mejores stack traces
    console.error('Error details:', error)
    console.error('Component stack:', errorInfo.componentStack)
  }

  render() {
    if (this.state.hasError) {
      return <div>Something went wrong: {this.state.error?.message}</div>
    }
    return this.props.children
  }
}
```

**Mejoras:**
- ✅ Mensajes de error más detallados
- ✅ Mejores stack traces de componentes
- ✅ Depuración más fácil en desarrollo
- ✅ Advertencias de desajuste de hidratación mejoradas

---

### React Compiler (Experimental)

React 19 incluye un compilador opcional que optimiza automáticamente los componentes.

**Qué hace:**
- Memoriza automáticamente los componentes y valores
- Elimina la necesidad de `useMemo`, `useCallback`, `React.memo` en muchos casos
- Analiza el código en tiempo de build
- Solo re-renderiza cuando es realmente necesario

**Enfoque tradicional:**
```typescript
// React 18 - Optimización manual
function ExpensiveComponent({ data }: { data: Data[] }) {
  const processedData = useMemo(() => {
    return data.map(item => /* operación costosa */)
  }, [data])

  const handleClick = useCallback(() => {
    console.log('clicked')
  }, [])

  return <List data={processedData} onClick={handleClick} />
}
```

**Con React Compiler:**
```typescript
// React 19 con compilador - Optimización automática
function ExpensiveComponent({ data }: { data: Data[] }) {
  // El compilador memoriza esto automáticamente
  const processedData = data.map(item => /* operación costosa */)

  // El compilador memoriza esto automáticamente
  const handleClick = () => {
    console.log('clicked')
  }

  return <List data={processedData} onClick={handleClick} />
}
```

**Estado:** Experimental - aún no recomendado para producción.

---

### Migración de React 18 a React 19

**Qué Cambia:**
1. ✅ `ref` como prop (no más `forwardRef` necesario)
2. ✅ Limpieza más estricta en los efectos
3. ✅ Mejores tipos de TypeScript
4. ✅ Mejores mensajes de error

**Qué Permanece Igual:**
1. ✅ Todos los hooks existentes (`useState`, `useEffect`, etc.)
2. ✅ Los patrones de componentes
3. ✅ La sintaxis JSX
4. ✅ El manejo de eventos
5. ✅ La Context API

**Cambios que Rompen (Menores):**
- `forwardRef` sigue funcionando pero ya no es necesario
- Algunos casos límite en el comportamiento de limpieza de `useEffect`
- Los tipos de TypeScript para las refs se simplificaron

**Estrategia de Actualización:**
```bash
# Instalar React 19
npm install react@19 react-dom@19

# Actualizar los tipos de TypeScript
npm install -D @types/react@19 @types/react-dom@19

# Probar tu app a fondo
npm run test
npm run build
```

**Enfoque Recomendado:**
- Empieza con apps pequeñas y no críticas
- Prueba a fondo en desarrollo
- Monitorea las advertencias de la consola
- Adopta las nuevas funcionalidades gradualmente
- Mantén los patrones de React 18 como respaldo

---

### Cuándo Usar las Funcionalidades de React 19

| Funcionalidad | Usar Cuando | Evitar Cuando |
|---------|----------|------------|
| **Hook `use()`** | Cargar datos asíncronos con Suspense | Gestión de estado simple |
| **`useOptimistic()`** | Apps de chat, funciones sociales, formularios | Mutaciones simples sin retroalimentación de UI |
| **`useFormStatus()`** | Formularios complejos con estados de carga | Formularios simples con una sola entrada |
| **Actions** | Se necesita mejora progresiva | Apps solo de cliente |
| **Metadatos en componentes** | SEO importante, sin framework | Usando Next.js (lo tiene integrado) |
| **`ref` como prop** | Siempre (más simple que forwardRef) | N/A - siempre es mejor |

---

### Buenas Prácticas de React 19

1. **Usa `use()` para la obtención de datos con Suspense:**
   ```typescript
   function UserProfile({ userPromise }) {
     const user = use(userPromise)
     return <div>{user.name}</div>
   }
   ```

2. **Actualizaciones optimistas para una mejor UX:**
   ```typescript
   const [optimisticLikes, addOptimisticLike] = useOptimistic(likes)
   ```

3. **Simplifica las refs (sin forwardRef):**
   ```typescript
   function Input({ ref }) {
     return <input ref={ref} />
   }
   ```

4. **Usa actions para los formularios:**
   ```typescript
   <form action={async (formData) => { /* handle */ }}>
   ```

5. **Añade metadatos directamente en los componentes:**
   ```typescript
   return (
     <>
       <title>Page Title</title>
       <Content />
     </>
   )
   ```

---

## Temas Adicionales

Temas para desarrollar más a fondo:

- **11. Formularios con Zod** - Validación de formularios con seguridad de tipos
- **12. Context API** - Gestión de estado global
- **13. useRef & useCallback** - Optimizaciones de rendimiento
- **14. Portals** - Renderizar fuera del árbol del DOM
- **15. Error Boundaries** - Manejo de errores
- **16. Interceptores de Axios** - Configuración del cliente HTTP
- **17. React Router DOM** - Navegación y enrutamiento

---

## Notas Importantes

### Buenas Prácticas de TypeScript

1. **Tipa siempre tus props:**
```typescript
interface ComponentProps {
  name: string
  age?: number
}
```

2. **Usa la inferencia de tipos cuando sea posible:**
```typescript
const [count, setCount] = useState(0) // Tipo inferido como number
```

3. **Tipos explícitos para estructuras complejas:**
```typescript
const [user, setUser] = useState<User | null>(null)
```

### React 18 vs React 19

**Compatibilidad:**
- ✅ Todos los patrones de esta guía funcionan en React 18 y React 19
- ✅ Las funcionalidades de React 19 son opcionales y aditivas
- ✅ Ver [Sección 10: Nuevas Funcionalidades de React 19](#10-nuevas-funcionalidades-de-react-19) para las últimas capacidades
- ✅ Los conceptos fundamentales (componentes, hooks, estado) permanecen sin cambios

**Adiciones Clave de React 19:**
- Hook `use()` para leer Promises y Context
- `useOptimistic()` para actualizaciones optimistas de la UI
- `useFormStatus()` y `useFormState()` para el manejo de formularios
- Actions para envíos de formularios asíncronos
- `ref` como una prop normal (sin `forwardRef` necesario)
- Soporte de metadatos del documento (`<title>`, `<meta>` en componentes)
- React Compiler experimental para optimizaciones automáticas

**Migración:**
- El código de React 18 sigue funcionando en React 19
- Se recomienda la adopción gradual de nuevas funcionalidades
- Las apps de producción pueden actualizarse cuando estén listas

### Puntos Clave

1. **Aprende los fundamentos primero** - JavaScript → React → Frameworks
2. **Los componentes son funciones** - Que devuelven JSX/TSX
3. **El estado dispara los re-renderizados** - Entiende el ciclo de renderizado
4. **Composición sobre props** - Construye componentes flexibles y reutilizables
5. **Custom hooks para la lógica** - Extrae y reutiliza la lógica con estado
6. **TypeScript es esencial** - Detecta errores en tiempo de compilación

---

## Temas Cubiertos

### Fundamentales y Avanzados:
- Árbol de decisión React vs Frameworks
- Configuración moderna del proyecto con Vite
- Internos de la detección de cambios
- Virtual DOM y reconciliación
- Hooks (useState, useEffect, custom hooks)
- Patrones avanzados (Composición, Context, Error Boundaries)
- Técnicas de optimización del rendimiento

### Análisis en Profundidad de Fundamentos:
- **JSX en Profundidad:**
  - Cómo JSX se transforma en JavaScript
  - Transpilación con Babel y SWC
  - Reglas y restricciones de JSX
  - Protección contra XSS
  - Programación declarativa vs imperativa

- **Elemento vs Componente:**
  - Distinción crítica entre componentes (fábricas) y elementos (productos)
  - Por qué los componentes no renderizan, los elementos sí
  - El requisito de nombrado en PascalCase explicado

- **Props en Profundidad:**
  - Pasar todos los tipos de props (strings, números, booleanos, funciones, objetos, elementos)
  - Abreviatura de props booleanas
  - Buenas prácticas de props de función (callbacks)
  - Operador spread para las props (con precauciones)
  - Valores por defecto
  - La prop especial `children` en profundidad
  - Inmutabilidad de las props (concepto crítico)
  - Convenciones de nombrado de props

- **Estilizado en React:**
  - Estilos en línea como objetos (no strings)
  - Nombres de propiedad en camelCase
  - className vs class
  - Convenciones de nombrado de CSS (BEM, SUIT)
  - Espaciado de Contenedor vs Componente
  - Patrones de className dinámico
  - Cuándo usar cada enfoque de estilizado

- **React sin Herramientas de Build:**
  - Usar React directamente desde el CDN
  - Aprender los fundamentos de React sin complejidad

- **Buenas Prácticas:**
  - Los componentes no deberían controlar su propio espaciado
  - El contenedor controla el layout y el espaciado
  - La inmutabilidad de las props no es negociable
  - Convenciones de nombrado consistentes

---

## Metadatos del Documento

**Última Actualización:** 2026-08-31
**Versión de React Cubierta:** 18.x / 19.x (compatible con ambas)
**Requisitos Previos:**
- JavaScript ES6+ (arrow functions, destructuring, módulos, async/await)
- Fundamentos de HTML5 y CSS3
- Fundamentos de TypeScript (interfaces, tipos, genéricos)
- Node.js y npm/gestores de paquetes

**Nivel de Habilidad:** Principiante a Experto
**Camino Recomendado:** JavaScript → React → Frameworks (Next.js, Remix)

**Referencias:**
- [React 19 Release Notes](https://react.dev/blog/2024/04/25/react-19)
- [Documentación Oficial de React](https://react.dev)
