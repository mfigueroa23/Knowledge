# Angular - De Cero a Experto

---

## 📌 Metadatos del Documento

**Última Actualización:** 2026-08-31
**Versiones de Angular Cubiertas:** Angular 17, 18, 19 (estable actual)
**Nivel de Habilidad:** Principiante a Experto
**Requisitos Previos:**
- Conocimientos básicos de JavaScript/TypeScript
- Fundamentos de HTML y CSS
- Node.js instalado (v20+ recomendado)
- Familiaridad con la línea de comandos

**Referencias:** [Documentación Oficial de Angular](https://angular.dev), [Angular Blog](https://blog.angular.dev)
**Incluye:** Standalone Components, Signals, linkedSignal, Resource API, Zoneless Change Detection, HTTP Interceptors, Route Guards

---

## 🎯 Cuándo Usar Este Conocimiento

### Usa Esta Guía Cuando:
✅ **Inicies un nuevo proyecto Angular** - Aprende las buenas prácticas modernas desde el primer día
✅ **Migres desde AngularJS o versiones antiguas de Angular** - Entiende el enfoque moderno
✅ **Construyas aplicaciones empresariales** - La estructura opinada de Angular escala bien
✅ **Necesites una fuerte integración con TypeScript** - Angular es TypeScript-first
✅ **Trabajes con equipos** - Las convenciones de Angular reducen el "bikeshedding"
✅ **Requieras soporte a largo plazo** - Google proporciona 18 meses de LTS por versión
✅ **Renderizado del Lado del Servidor (SSR)** - SSR integrado con soporte de hidratación

### Considera Alternativas Cuando:
⚠️ **Construyas prototipos pequeños y rápidos** - React/Vue pueden ser más rápidos de configurar
⚠️ **El equipo no esté familiarizado con TypeScript** - Curva de aprendizaje pronunciada para desarrolladores solo de JS
⚠️ **Necesites máxima flexibilidad** - Angular es opinado ("Angular Way")
⚠️ **Apps ultraligeras** - Angular tiene un tamaño de bundle inicial mayor que las alternativas

### Angular vs Otros Frameworks (2025):

| Característica | Angular 19 | React 19 | Vue 3 |
|---------|-----------|----------|-------|
| **Reactividad** | Signals (estable) | Hooks | Composition API |
| **TypeScript** | De primera clase | Buen soporte | Buen soporte |
| **SSR** | Integrado | Necesita Next.js | Necesita Nuxt |
| **Gestión de Estado** | Signals + RxJS integrados | Externo (Redux, Zustand) | Integrado (Pinia) |
| **CLI** | Potente, opinada | Create React App (obsoleto) | Vue CLI / Vite |
| **Curva de Aprendizaje** | Más pronunciada | Moderada | Suave |
| **Tamaño de Bundle** | ~150KB (optimizado) | ~40KB | ~50KB |
| **Adopción Empresarial** | Muy Fuerte | Muy Fuerte | Creciendo |

### Panorama Actual de Angular (Enero de 2025):

**Última Versión Estable:** Angular 19.1.2 (lanzada el 20 de enero de 2025)
**Cadencia de Lanzamiento:** Versiones mayores cada ~6 meses
**Próxima Versión Mayor:** Angular 20 (esperada en mayo de 2025)
**Soporte LTS:** 18 meses por versión mayor

**Aspectos Destacados de Angular 19:**
- ✅ Los componentes standalone ahora son el **valor por defecto**
- ✅ La API de Signals es **estable**
- ✅ linkedSignal y Resource API (developer preview)
- ✅ Hidratación incremental para SSR
- ✅ Event replay habilitado por defecto
- ✅ Modos de renderizado a nivel de ruta (mezcla de SSR/CSR/SSG)

---

## 📋 Tabla de Contenidos

1. [Introducción](#1-introducción)
2. [Por Qué Angular Está Cambiando](#2-por-qué-angular-está-cambiando)
3. [Configuración del Proyecto con Angular Moderno](#3-configuración-del-proyecto-con-angular-moderno)
4. [TypeScript en Profundidad](#4-typescript-en-profundidad)
5. [Decoradores en Angular](#5-decoradores-en-angular)
6. [Arquitectura de Componentes](#6-arquitectura-de-componentes)
7. [Standalone Components](#7-standalone-components)
8. [Sintaxis Moderna de Control de Flujo](#8-sintaxis-moderna-de-control-de-flujo)
9. [Property Binding y Eventos](#9-property-binding-y-eventos)
10. [Comunicación entre Componentes](#10-comunicación-entre-componentes)
11. [Directiva Defer - Lazy Loading](#11-directiva-defer---lazy-loading)
12. [Signals y Programación Reactiva](#12-signals-y-programación-reactiva)
13. [Detección de Cambios](#13-detección-de-cambios)
14. [Renderizado del Lado del Servidor](#14-renderizado-del-lado-del-servidor)
15. [Bundling y Optimización](#15-bundling-y-optimización)
16. [Configuración del Proyecto](#16-configuración-del-proyecto)
17. [HTTP Interceptors](#17-http-interceptors)
18. [Route Guards](#18-route-guards)
19. [Funcionalidades de Angular 19](#19-funcionalidades-de-angular-19)
20. [Funcionalidades de Angular 20](#20-funcionalidades-de-angular-20)
21. [Angular 20.2 y Más Allá](#21-angular-202-y-más-allá)

---

## Descripción General

Angular es una plataforma completa para construir aplicaciones web escalables. Esta guía cubre Angular 18/19 con todas las funcionalidades modernas, incluyendo componentes standalone, signals, detección de cambios zoneless y un renderizado del lado del servidor mejorado.

### ¿Qué es Angular?

- **Plataforma** (no solo un framework) - Un ecosistema completo para construir aplicaciones web
- Construido con **TypeScript**
- **Framework estructural** - Extiende las capacidades de HTML/DOM a través de directivas
- Desarrollado y mantenido por **Google**
- Listo para empresas con patrones de arquitectura sólidos
- Enfoque opinado ("Angular Way")

### Características Principales

- ✅ Plataforma completa con todo incluido
- ✅ Componentes standalone (no se requieren NgModules)
- ✅ Signals para reactividad de grano fino
- ✅ Detección de cambios zoneless
- ✅ Renderizado del lado del servidor integrado
- ✅ CLI potente para scaffolding y herramientas
- ✅ Enfoque TypeScript-first
- ✅ Sistema de inyección de dependencias
- ✅ Soporte de testing completo

### Filosofía Central

**Angular Way:**
- Un problema, una solución
- Buenas prácticas impulsadas por la comunidad
- Estabilidad y soporte a largo plazo (compatibilidad hacia atrás de 6 versiones)
- Lanzamientos frecuentes (máximo 6 meses entre versiones)
- Scripts de migración para cambios mayores

### Notas de Compatibilidad de Versiones

**Cronología de Lanzamientos de Angular:**

| Versión | Fecha de Lanzamiento | Estado (Ene 2025) | Funcionalidades Clave |
|---------|--------------|-------------------|--------------|
| **Angular 17** | 8 de noviembre de 2023 | Soporte Activo | Nuevo control de flujo, @defer, standalone por defecto |
| **Angular 18** | 22 de mayo de 2024 | Soporte Activo | Signals mejorados, zoneless experimental |
| **Angular 19** | 19 de noviembre de 2024 | **Estable Actual** ✅ | Signals estables, linkedSignal, Resource API, hidratación incremental |
| **Angular 20** | Esperada mayo 2025 | Futuro | Formularios basados en signals, SSR mejorado |
| **Angular 21** | Esperada nov 2025 | Futuro | Por determinar |

**Funcionalidades por Versión:**

| Característica | Angular 17 | Angular 18 | Angular 19 (Actual) | Angular 20 (Preview) |
|---------|------------|------------|----------------------|----------------------|
| Standalone Components | ✅ Opcional | ✅ Opcional | ✅ **Por defecto** | ✅ Por defecto |
| Nuevo Control de Flujo (@if, @for) | ✅ | ✅ | ✅ | ✅ |
| Directiva @defer | ✅ | ✅ | ✅ | ✅ |
| Signals (Básico) | ✅ | ✅ Mejorado | ✅ **Estable** | ✅ Estable |
| linkedSignal | ❌ | ❌ | ✅ Dev Preview | ✅ Estable esperado |
| Resource API | ❌ | ❌ | ✅ Dev Preview | ✅ Estable esperado |
| Detección de Cambios Zoneless | ❌ | ✅ Experimental | ✅ Dev Preview | ✅ Estable opt-in esperado |
| SSR Integrado | ✅ | ✅ | ✅ **Mejorado** | ✅ Mejorado |
| Event Replay | ❌ | ❌ | ✅ **Por defecto** | ✅ |
| Hidratación Incremental (@defer) | ❌ | ❌ | ✅ **Nuevo** | ✅ |
| Modos de Renderizado a Nivel de Ruta | ❌ | ❌ | ✅ **Nuevo** | ✅ |
| Material Design 3 | ❌ | ❌ | ⚠️ Parcial | ✅ Esperado |
| Formularios basados en Signals | ❌ | ❌ | ❌ | ✅ Preview |

**✅ Todas las funcionalidades de esta guía funcionan en Angular 17, 18 y 19** a menos que se indique explícitamente lo contrario.

**Nota sobre Angular 20+:** Las funcionalidades marcadas como "Angular 20" o "Angular 20.2" en este documento se basan en versiones preview y documentos RFC (Request for Comments). Estas pueden cambiar antes del lanzamiento final.

---

## 1. Introducción

### La Evolución de Angular

Angular ha experimentado transformaciones masivas:

**Angular.js (v1.x):**
- Usaba controladores y el patrón MVC/MVVM
- Enlace de datos bidireccional
- Sin concepto de componente inicialmente
- Usaba directivas para simular componentes

**Angular 2+:**
- Reescritura completa
- Arquitectura basada en componentes
- Basado en TypeScript
- Motor de renderizado Ivy (rendimiento mejorado)
- Arquitectura modular con NgModules

**Angular 16-19 (Angular Moderno - Actual):**
- Componentes standalone (por defecto en Angular 19)
- Signals para estado reactivo (estable en Angular 19)
- Detección de cambios zoneless (developer preview)
- SSR mejorado con hidratación y event replay
- Bundling más rápido con esbuild y Vite
- Hidratación incremental (@defer para SSR)
- Resource API para la carga de datos asíncronos

### ¿Por Qué Aprender Angular Ahora? (Enero de 2025)

**Momento Perfecto:**
- **Angular 19 es estable** (lanzado el 19 de noviembre de 2024) - Funcionalidades modernas y listas para producción
- Angular está regresando con funcionalidades modernas (Signals, Zoneless, SSR)
- La comunidad está creciendo de nuevo tras el declive anterior
- La nueva documentación ([angular.dev](https://angular.dev)) es excelente, con tutoriales interactivos
- La adopción empresarial sigue siendo muy fuerte
- Los Signals ahora son **estables** - no más APIs experimentales

**Posición en el Mercado:**
- Fuerte en aplicaciones empresariales (empresas Fortune 500)
- Patrones de arquitectura bien definidos que reducen la fatiga de decisión
- Soporte a largo plazo (18 meses de LTS por versión)
- Mejor que nunca con las mejoras recientes (builds 67% más rápidos)
- Inversión y soporte activos de Google

---

## 2. Por Qué Angular Está Cambiando

### El Problema que Enfrentó Angular

**Problemas Históricos:**
1. **Curva de aprendizaje pronunciada** - Sistema de módulos complejo, sintaxis verbosa
2. **Documentación pobre** - El antiguo angular.io era confuso y laberíntico
3. **Preocupaciones de rendimiento** - Sobrecarga de Zone.js, detección de cambios lenta
4. **Competencia** - React ofrecía una experiencia de desarrollo más simple
5. **Declive de la comunidad** - Los desarrolladores se movían a otros frameworks

### La Solución: Modernización Mayor

**Cambios Clave:**

1. **Componentes Standalone** - Arquitectura simplificada
2. **Signals** - Programación reactiva moderna
3. **Zoneless** - Eliminar la dependencia de Zone.js
4. **Mejor SSR** - Renderizado del lado del servidor mejorado
5. **Nueva Documentación** - angular.dev con tutoriales interactivos
6. **Builds Más Rápidos** - Rollup + Vite en lugar de Webpack

### La Estrategia de Regreso de Angular

- Escuchar la retroalimentación de la comunidad
- Hacer mejoras rápidas y frecuentes
- Proporcionar herramientas de migración para los cambios que rompen compatibilidad
- Enfocarse en la experiencia del desarrollador
- Mantener la compatibilidad hacia atrás

---

## 3. Configuración del Proyecto con Angular Moderno

### Requisitos Previos

```bash
# Instalar Bun (gestor de paquetes recomendado)
curl -fsSL https://bun.sh/install | bash

# Configurar Angular CLI para usar Bun
ng config -g cli.packageManager bun

# Instalar Angular CLI globalmente
bun add -g @angular/cli
# o
npm install -g @angular/cli
```

### Creando un Nuevo Proyecto

```bash
# Crear un nuevo proyecto Angular
ng new curso-angular

# Opciones a seleccionar:
# - SSR (Server-Side Rendering): Sí/No
# - Routing: Sí (recomendado)
# - Stylesheet: CSS/SCSS/Sass/Less

# Estructura del proyecto creada automáticamente
# Dependencias instaladas vía Bun (¡súper rápido!)
```

### Referencia de Comandos de Angular CLI

**Generación de Componentes:**

```bash
# Generar un componente (con todos los archivos)
ng generate component user
# o forma corta
ng g c user

# Generar con plantilla y estilos en línea
ng g c games --inline-template --inline-style
# o más corto
ng g c games -t -s

# Omitir los archivos de test
ng g c comments --skip-tests

# Dry run (previsualizar sin crear archivos)
ng g c example --dry-run
```

**Iniciar el Servidor de Desarrollo:**

```bash
# Iniciar el servidor de desarrollo (por defecto: http://localhost:4200)
ng serve
# o
npm start

# Abrir el navegador automáticamente
ng serve --open
# o
ng serve -o

# Puerto personalizado
ng serve --port 3000
```

**Otros Comandos Útiles:**

```bash
# Comprobar la versión de Angular
ng version

# Obtener ayuda para cualquier comando
ng generate component --help
ng g c --help

# Build para producción
ng build

# Ejecutar tests
ng test

# Ejecutar tests e2e
ng e2e
```

**Opciones de Generación de Componentes:**

```bash
# Estructura plana (sin carpeta)
ng g c button --flat

# Ruta específica
ng g c components/header

# Detección de cambios OnPush
ng g c user --change-detection OnPush

# Exportar la clase
ng g c shared/button --export
```

### Estructura del Proyecto

```
proyecto-angular/
├── src/
│   ├── app/
│   │   ├── app.component.ts       # Componente raíz
│   │   ├── app.component.html     # Plantilla
│   │   ├── app.component.scss     # Estilos
│   │   ├── app.config.ts          # Configuración de la app
│   │   └── app.routes.ts          # Configuración de enrutamiento
│   ├── main.ts                    # Punto de entrada del cliente
│   ├── main.server.ts             # Punto de entrada del servidor
│   └── index.html                 # Shell HTML
├── server.ts                      # Servidor Express para SSR
├── angular.json                   # Configuración de Angular CLI
├── tsconfig.json                  # Configuración de TypeScript
└── package.json                   # Dependencias
```

### Archivos de Configuración Clave

**angular.json:**
```json
{
  "projects": {
    "app": {
      "architect": {
        "build": {
          "builder": "@angular/build:application",
          "options": {
            "outputPath": "dist",
            "index": "src/index.html",
            "browser": "src/main.ts",
            "server": "src/main.server.ts",
            "polyfills": ["zone.js"]
          }
        }
      },
      "schematics": {
        "@schematics/angular:component": {
          "changeDetection": "OnPush"  // Por defecto OnPush
        }
      }
    }
  }
}
```

**tsconfig.json:**
```json
{
  "compilerOptions": {
    "target": "ES2022",
    "module": "ES2022",
    "lib": ["ES2022", "dom"],
    "experimentalDecorators": true,
    "emitDecoratorMetadata": true,
    "useDefineForClassFields": true,
    "baseUrl": "./",
    "paths": {
      "@app/*": ["src/app/*"]  // Alias de rutas
    }
  }
}
```

### Configuración Moderna de la App

**app.config.ts:**
```typescript
import { ApplicationConfig } from '@angular/core';
import { provideRouter, withComponentInputBinding } from '@angular/router';
import { provideHttpClient, withFetch } from '@angular/common/http';
import { provideClientHydration } from '@angular/platform-browser';
import {
  provideExperimentalZonelessChangeDetection
} from '@angular/core';

export const appConfig: ApplicationConfig = {
  providers: [
    // Detección de cambios zoneless (experimental)
    provideExperimentalZonelessChangeDetection(),

    // Router con input binding
    provideRouter(routes, withComponentInputBinding()),

    // Cliente HTTP con la API fetch
    provideHttpClient(withFetch()),

    // Hidratación del cliente para SSR
    provideClientHydration()
  ]
};
```

### Gestor de Paquetes: ¿Por Qué Bun?

**Ventajas de Bun:**
- **Ultra-rápido** - 500ms para instalar todas las dependencias
- **Todo-en-uno** - Runtime, bundler, gestor de paquetes
- **Compatible** - Reemplazo directo de npm/yarn
- **Moderno** - Construido para el ecosistema JavaScript actual

**Comparación de Velocidad de Instalación:**
- npm: ~30-60 segundos
- yarn: ~20-40 segundos
- Bun: ~0.5 segundos ⚡

---

## 4. TypeScript en Profundidad

### ¿Qué es TypeScript?

TypeScript = **JavaScript con Esteroides**

- Superconjunto de JavaScript
- Añade tipado estático
- Compila (transpila) a JavaScript
- Detecta errores en tiempo de compilación
- Solo existe durante el desarrollo

### Inferencia de Tipos

```typescript
// TypeScript infiere los tipos automáticamente
let a = 1;        // TypeScript sabe: a es number
a = "hello";      // ❌ Error: El tipo 'string' no se puede asignar al tipo 'number'

// Tipado explícito
let b: number = 2;
let c: string = "hello";
let d: boolean = true;
```

### Tipos Primitivos

```typescript
// Tipos básicos
let age: number = 25;
let name: string = "Alan";
let isActive: boolean = true;
let nothing: null = null;
let notDefined: undefined = undefined;

// Arrays
let numbers: number[] = [1, 2, 3];
let names: Array<string> = ["Alan", "Marco"];

// Tuplas (arrays de longitud fija con tipos específicos)
let user: [string, number] = ["Alan", 25];
```

### Any vs Unknown

```typescript
// ❌ Any - Deshabilita la comprobación de tipos (¡evítalo!)
let anything: any = "hello";
anything = 42;
anything = true;  // Sin errores, pero anula el propósito de TypeScript

// ✅ Unknown - Alternativa segura de tipos
let something: unknown = "hello";
// something.toUpperCase();  // ❌ Error: El objeto es de tipo 'unknown'

// Primero hay que estrechar el tipo
if (typeof something === "string") {
  something.toUpperCase();  // ✅ OK
}
```

### Interfaces

**Interfaces = Contratos que no se pueden romper**

```typescript
interface User {
  name: string;
  age: number;
  email?: string;  // Propiedad opcional
}

// Debe cumplir el contrato
const user: User = {
  name: "Alan",
  age: 35
  // email es opcional
};

// ❌ Error: Falta la propiedad 'name'
const invalidUser: User = {
  age: 25
};
```

### Clases

```typescript
class UserClass {
  private name: string;
  private age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  getName(): string {
    return this.name;
  }

  setName(name: string): void {
    this.name = name;
  }
}

// Uso
const user = new UserClass("Alan", 35);
console.log(user.getName());  // "Alan"
// console.log(user.name);     // ❌ Error: 'name' es privado
```

**Constructor Abreviado:**
```typescript
class User {
  constructor(
    private name: string,
    public age: number
  ) {}
}

// Equivalente al ejemplo anterior
// Las propiedades 'public' son accesibles fuera de la clase
```

### Type Aliases

```typescript
// Creando tipos personalizados
type ID = string | number;
type User = {
  name: string;
  age: number;
};

// Union types
type Status = "active" | "inactive" | "pending";
let userStatus: Status = "active";  // ✅ OK
// userStatus = "deleted";           // ❌ Error

// Intersection types
type Admin = User & {
  permissions: string[];
};

const admin: Admin = {
  name: "Alan",
  age: 35,
  permissions: ["read", "write", "delete"]
};
```

### Genéricos

```typescript
// Función genérica
function identity<T>(value: T): T {
  return value;
}

const num = identity<number>(42);        // num: number
const str = identity<string>("hello");   // str: string

// Genérico con restricciones
function getProperty<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}

const user = { name: "Alan", age: 35 };
const name = getProperty(user, "name");  // ✅ OK
// getProperty(user, "invalid");         // ❌ Error
```

### Avanzado: Type Guards

```typescript
// Estrechamiento de tipos (type narrowing)
function processValue(value: string | number) {
  if (typeof value === "string") {
    // TypeScript sabe que value es string aquí
    return value.toUpperCase();
  } else {
    // TypeScript sabe que value es number aquí
    return value.toFixed(2);
  }
}
```

### Tipado Basado en la Forma (Shape-Based Typing)

**Concepto Clave:** A TypeScript no le importan los nombres, solo la **forma**

```typescript
interface User {
  name: string;
  age: number;
}

class Person {
  constructor(
    public name: string,
    public age: number
  ) {}
}

// ✅ ¡Esto funciona! Person tiene la misma forma que User
const user: User = new Person("Alan", 35);
```

---

## 5. Decoradores en Angular

### ¿Qué son los Decoradores?

Los **Decoradores** añaden funcionalidad extra a las clases, métodos, propiedades o parámetros.

- Precedidos por el símbolo `@`
- Se ejecutan en la definición de la clase/método/propiedad
- Usados extensamente en Angular
- TypeScript 5.0 introdujo una nueva sintaxis de decoradores

### Habilitar Decoradores

**tsconfig.json:**
```json
{
  "compilerOptions": {
    "experimentalDecorators": true,
    "emitDecoratorMetadata": true
  }
}
```

### Decorador de Clase

```typescript
// Definir un decorador de clase
function AddFlag<T extends { new (...args: any[]): {} }>(
  constructor: T,
  context: ClassDecoratorContext
) {
  // Extender el constructor
  return class extends constructor {
    flagged = true;
  };
}

// Aplicar el decorador
@AddFlag
class MyClass {
  constructor() {}
}

const instance = new MyClass();
console.log((instance as any).flagged);  // true
```

### Decorador de Método

```typescript
function LogMethod(
  method: Function,
  context: ClassMethodDecoratorContext
) {
  return function (...args: any[]) {
    console.log(`Method ${String(context.name)} called with:`, args);
    const result = method.apply(this, args);
    console.log(`Method ${String(context.name)} returned:`, result);
    return result;
  };
}

class Calculator {
  @LogMethod
  sum(a: number, b: number): number {
    return a + b;
  }
}

const calc = new Calculator();
calc.sum(1, 2);
// Registra: Method sum called with: [1, 2]
// Registra: Method sum returned: 3
```

### Decorador de Propiedad (Accessor)

```typescript
function Uppercase(
  target: any,
  context: ClassAccessorDecoratorContext
) {
  return {
    get(this: any): string {
      return this[`_${String(context.name)}`].toUpperCase();
    },
    set(this: any, value: string): void {
      this[`_${String(context.name)}`] = value.toUpperCase();
    }
  };
}

class Person {
  @Uppercase
  accessor name: string;

  constructor(name: string) {
    this.name = name;
  }
}

const person = new Person("alan");
console.log(person.name);  // "ALAN"
```

### Decorador @Component de Angular (Simplificado)

**Cómo usa Angular los decoradores:**

```typescript
// El decorador @Component de Angular (concepto simplificado)
function Component(config: {
  selector: string;
  template: string;
}) {
  return function (target: any) {
    target.prototype.selector = config.selector;
    target.prototype.template = config.template;
  };
}

// Uso
@Component({
  selector: 'app-root',
  template: '<h1>Hello Angular</h1>'
})
export class AppComponent {}
```

**Idea Clave:**
- Angular usa decoradores para identificar y configurar componentes, servicios, directivas, etc.
- `@Component` le dice a Angular que esta clase es un componente
- La configuración pasada al decorador define el comportamiento

---

## 6. Arquitectura de Componentes

### ¿Qué es un Componente?

**Componente = Unidad Lógica Mínima**

Un componente debería encargarse de **una cosa a la vez**, siguiendo el Principio de Responsabilidad Única.

### Anatomía de un Componente

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-user',           // Cómo usarlo en HTML: <app-user></app-user>
  templateUrl: './user.component.html',  // o template: '<div>...</div>'
  styleUrls: ['./user.component.scss'],  // o styles: ['div { color: red; }']
  standalone: true,                // ✅ Moderno: no se necesita NgModule
  imports: []                      // Importa las dependencias aquí
})
export class UserComponent {
  // Lógica del componente aquí
  title = 'User Component';
}
```

### Patrón Contenedor vs Presentacional

**Patrón de Arquitectura Crítico en Angular**

#### Componentes Presentacionales (Tontos/Sin Estado)

**Propósito:**
- Mostrar datos en la UI
- Manejar las interacciones de la UI
- Sin lógica de negocio
- Sin comunicaciones externas
- Altamente reutilizables

**Ejemplo:**
```typescript
@Component({
  selector: 'app-user-profile',
  standalone: true,
  template: `
    <div [style.color]="'red'">
      <h2>{{ username }}</h2>
    </div>
  `
})
export class UserProfileComponent {
  @Input() username: string = '';
}
```

#### Componentes Contenedores (Inteligentes/Con Estado)

**Propósito:**
- Manejar la lógica de negocio
- Comunicarse con entidades externas (servicios, APIs)
- Gestionar el estado
- Pasar datos a los componentes presentacionales

**Ejemplo:**
```typescript
@Component({
  selector: 'app-user-container',
  standalone: true,
  imports: [UserProfileComponent],
  template: `
    <app-user-profile [username]="usernameSignal()" />
  `
})
export class UserContainerComponent {
  userService = inject(UserService);
  usernameSignal = this.userService.usernameSignal;
}
```

### Ejemplo de Descomposición de Componentes: Sistema de Login

**Mala Práctica - Un Componente Grande:**
```
LoginComponent
  - Renderizar el formulario
  - Validar el formulario
  - Llamar al servicio de autenticación
  - Manejar errores
  - Navegar al tener éxito
  - Mostrar la lista de usuarios
  - Editar detalles del usuario
```

**Buena Práctica - Múltiples Componentes Enfocados:**
```
LoginPageComponent (Contenedor)
  ├── LoginFormComponent (Presentacional)
  │   ├── Validación de la entrada de email
  │   └── Validación de la entrada de contraseña
  ├── UserListComponent (Contenedor)
  │   └── UserCardComponent (Presentacional)
  └── EditUserComponent (Contenedor)
      └── UserFormComponent (Presentacional - ¡Reutilizable!)
```

### Estilos de Componente y Encapsulación de CSS

**Angular delimita automáticamente los estilos del componente (scope):**

```typescript
@Component({
  selector: 'app-user',
  standalone: true,
  template: `
    <section>
      <h1>User Profile</h1>
    </section>
  `,
  styles: [`
    section {
      max-width: 500px;
      margin: 0 auto;
      padding: 20px;
    }

    h1 {
      color: blue;
      font-family: system-ui;
    }
  `]
})
export class UserComponent {}
```

**HTML Generado:**
```html
<!-- Angular añade un atributo único para el scoping -->
<section _ngcontent-ng-c1234>
  <h1 _ngcontent-ng-c1234>User Profile</h1>
</section>
```

**CSS Generado:**
```css
/* Los estilos se delimitan automáticamente */
section[_ngcontent-ng-c1234] {
  max-width: 500px;
  margin: 0 auto;
  padding: 20px;
}

h1[_ngcontent-ng-c1234] {
  color: blue;
  font-family: system-ui;
}
```

**Beneficios:**
- Sin conflictos de nombrado de clases CSS
- Los estilos no se filtran a otros componentes
- Se pueden usar selectores simples (h1, section) con seguridad
- Hashing/scoping automático del CSS

### Estilos Globales

**src/styles.css (Global):**

```css
/* Se aplica a toda la aplicación */
:root {
  /* Variables CSS para theming */
  --primary-color: #007bff;
  --background: #ffffff;
  --text-color: #000000;
}

/* Soporte de modo oscuro */
:root {
  color-scheme: light dark;
}

/* Resets globales */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: system-ui, -apple-system, sans-serif;
  line-height: 1.6;
}
```

**Modo Oscuro con color-scheme:**

```css
/* src/styles.css */
:root {
  color-scheme: light dark;
}

/* El navegador aplica automáticamente los colores del modo oscuro */
/* No hay que especificar background-color ni color */
```

**¿Qué es :root?**
- Pseudo-elemento que se refiere a la raíz del documento
- Mayor especificidad que el selector html
- Perfecto para las propiedades personalizadas de CSS (variables)
- Disponible globalmente en todos los componentes

### Comunicación entre Componentes

**De Padre a Hijo - @Input:**
```typescript
@Component({
  selector: 'app-child',
  standalone: true,
  template: '<p>{{ message }}</p>'
})
export class ChildComponent {
  @Input() message: string = '';
}

// Plantilla del padre
// <app-child [message]="'Hello from parent'" />
```

**De Hijo a Padre - @Output:**
```typescript
@Component({
  selector: 'app-child',
  standalone: true,
  template: '<button (click)="sendMessage()">Send</button>'
})
export class ChildComponent {
  @Output() messageEvent = new EventEmitter<string>();

  sendMessage() {
    this.messageEvent.emit('Hello from child!');
  }
}

// Plantilla del padre
// <app-child (messageEvent)="handleMessage($event)" />
```

---

## 7. Standalone Components

### La Era de los Módulos (Antes de Angular 16)

**Forma Antigua - NgModules:**
```typescript
@NgModule({
  declarations: [
    AppComponent,
    UserComponent,
    ProductComponent
  ],
  imports: [
    BrowserModule,
    HttpClientModule,
    CommonModule
  ],
  providers: [UserService],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

**Problemas:**
- Verboso y con mucho boilerplate
- Hay que declarar cada componente en un módulo
- Gestión compleja de dependencias entre módulos
- No intuitivo para principiantes

### Forma Moderna - Standalone Components

**Forma Nueva (Angular 16+):**
```typescript
@Component({
  selector: 'app-user',
  standalone: true,        // ✅ ¡No se necesita NgModule!
  imports: [               // Importar las dependencias directamente
    CommonModule,
    HttpClientModule,
    AnotherComponent
  ],
  templateUrl: './user.component.html'
})
export class UserComponent {}
```

**Beneficios:**
- Modelo mental más simple
- Menos boilerplate
- Encapsulación del componente
- Más fácil entender las dependencias
- Mejor tree-shaking

### Migración de Módulos a Standalone

Angular proporciona una migración automatizada:

```bash
# Migrar todo el proyecto a standalone
ng generate @angular/core:standalone

# Opciones:
# 1. Convertir las declaraciones a standalone
# 2. Eliminar los NgModules innecesarios
# 3. Hacer bootstrap usando la API de standalone
```

### Bootstrap con Standalone

**main.ts (Standalone):**
```typescript
import { bootstrapApplication } from '@angular/platform-browser';
import { appConfig } from './app/app.config';
import { AppComponent } from './app/app.component';

bootstrapApplication(AppComponent, appConfig)
  .catch(err => console.error(err));
```

**vs Bootstrap Antiguo con Módulo:**
```typescript
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
import { AppModule } from './app/app.module';

platformBrowserDynamic()
  .bootstrapModule(AppModule)
  .catch(err => console.error(err));
```

---

## 8. Sintaxis Moderna de Control de Flujo

### Nuevo en Angular 17+

Angular 17 introdujo una **nueva sintaxis de control de flujo** revolucionaria que reemplaza las antiguas directivas estructurales (`*ngIf`, `*ngFor`, `*ngSwitch`) por una sintaxis más intuitiva e integrada.

**✅ Válido para Angular 17, 18 y 19** - Este es el enfoque recomendado de aquí en adelante.

### Directiva @if

**Forma Antigua (aún funciona):**
```html
<div *ngIf="isLoggedIn">
  <p>Welcome {{ username }}</p>
</div>
<div *ngIf="!isLoggedIn">
  <p>Please login</p>
</div>
```

**Forma Nueva (Angular 17+):**
```html
@if (isLoggedIn) {
  <p>Welcome {{ username }}</p>
} @else {
  <p>Please login</p>
}
```

**Con @else if:**
```html
@if (user.role === 'admin') {
  <p>Admin Dashboard</p>
} @else if (user.role === 'editor') {
  <p>Editor Panel</p>
} @else {
  <p>User View</p>
}
```

**Ejemplo de Componente:**
```typescript
@Component({
  selector: 'app-user',
  standalone: true,
  template: `
    <section>
      @if (isLoggedIn) {
        <h2>Welcome {{ username }}</h2>
        <img [src]="'https://github.com/' + username + '.png'"
             alt="avatar"
             width="64"
             style="border-radius: 50%">
      } @else {
        <button (click)="isLoggedIn = true">Iniciar sesión</button>
      }
    </section>
  `
})
export class UserComponent {
  username = 'johndoe';
  isLoggedIn = false;
}
```

### Directiva @for

**Forma Antigua:**
```html
<ul>
  <li *ngFor="let game of games; trackBy: trackById">
    {{ game.name }}
  </li>
</ul>
```

**Forma Nueva (Angular 17+):**
```html
<ul>
  @for (game of games; track game.id) {
    <li (click)="selectGame(game.name)">
      {{ game.name }}
    </li>
  }
</ul>
```

**Importante:** La expresión `track` es **obligatoria** (no opcional como `trackBy`).

**Ejemplo Completo:**
```typescript
@Component({
  selector: 'app-games',
  standalone: true,
  template: `
    <ul>
      @for (game of games; track game.id) {
        <li (click)="favoriteGame(game.name)">
          {{ game.name }}
        </li>
      }
    </ul>
  `,
  styles: [`
    ul { list-style: none; }
    li { cursor: pointer; padding: 8px; }
    li:hover { background: #f0f0f0; }
  `]
})
export class GamesComponent {
  games = [
    { id: 1, name: 'Uncharted 4' },
    { id: 2, name: 'Horizon Zero Dawn' },
    { id: 3, name: 'Bloodborne' }
  ];

  favoriteGame(name: string) {
    console.log(`Favorite: ${name}`);
  }
}
```

### Por Qué track es Obligatorio

La expresión `track` ayuda a Angular a identificar qué elementos cambiaron:

```typescript
// ✅ Bien - usando un ID único
@for (user of users; track user.id) {
  <div>{{ user.name }}</div>
}

// ⚠️ Funciona pero no es óptimo - usando el índice
@for (user of users; track $index) {
  <div>{{ user.name }}</div>
}

// ❌ Anti-patrón - puede causar problemas de renderizado
// No uses valores calculados ni referencias de objetos
@for (user of users; track user) {  // NO HAGAS ESTO
  <div>{{ user.name }}</div>
}
```

### Directiva @switch

**Forma Antigua:**
```html
<div [ngSwitch]="status">
  <p *ngSwitchCase="'active'">Active</p>
  <p *ngSwitchCase="'inactive'">Inactive</p>
  <p *ngSwitchDefault>Unknown</p>
</div>
```

**Forma Nueva (Angular 17+):**
```html
@switch (status) {
  @case ('active') {
    <p>Active</p>
  }
  @case ('inactive') {
    <p>Inactive</p>
  }
  @default {
    <p>Unknown</p>
  }
}
```

### Beneficios de la Nueva Sintaxis

1. **No se necesita importar CommonModule** - Integrado en Angular
2. **Más legible** - Se parece al control de flujo real
3. **Mejor integración con TypeScript** - Comprobación de tipos mejorada
4. **Consistente con otros lenguajes** - Familiar para los desarrolladores
5. **Menos verbosa** - No se necesita el prefijo `*ng`

### Migración

Ambas sintaxis funcionan lado a lado en Angular 17+, pero **se recomienda la nueva sintaxis**:

```typescript
@Component({
  // ✅ No hace falta importar CommonModule para la nueva sintaxis
  standalone: true,
  imports: [], // ¡Vacío! La nueva sintaxis está integrada
  template: `
    @if (condition) {
      <!-- Nueva sintaxis -->
    }
  `
})
```

---

## 9. Property Binding y Eventos

### Interpolación de Plantillas

**Mostrar propiedades del componente:**

```typescript
@Component({
  selector: 'app-user',
  standalone: true,
  template: `
    <h1>Hello from {{ city }}</h1>
    <p>{{ 1 + 1 }}</p>  <!-- Evalúa a 2 -->
    <p>{{ city.toUpperCase() }}</p>  <!-- Puede llamar métodos -->
  `
})
export class UserComponent {
  city = 'Barcelona';
}
```

### Property Binding

**Enlazar a las propiedades del elemento con la sintaxis `[property]`:**

```html
<!-- Enlace del src de la imagen -->
<img [src]="avatarUrl" [alt]="username">

<!-- Ancho dinámico -->
<img [src]="avatarUrl" [width]="imageSize">

<!-- Propiedades booleanas -->
<button [disabled]="!isValid">Submit</button>

<!-- Enlace de clase -->
<div [class.active]="isActive">Content</div>

<!-- Enlace de estilo -->
<p [style.color]="textColor">Colored text</p>
<p [style.font-size.px]="fontSize">Dynamic size</p>
```

**Ejemplo:**
```typescript
@Component({
  selector: 'app-user',
  standalone: true,
  template: `
    <img
      [src]="'https://github.com/' + username + '.png'"
      [alt]="username"
      [width]="64"
      [style.border-radius]="'50%'">
  `
})
export class UserComponent {
  username = 'johndoe';
}
```

### Event Binding

**Escuchar eventos del DOM con la sintaxis `(event)`:**

```typescript
@Component({
  selector: 'app-user',
  standalone: true,
  template: `
    <!-- Evento click -->
    <button (click)="greet()">Say Hello</button>

    <!-- Doble clic -->
    <img (dblclick)="showProfile()">

    <!-- Evento input -->
    <input (input)="onInput($event)">

    <!-- Eventos del mouse -->
    <div (mouseenter)="onHover()" (mouseleave)="onLeave()">
      Hover me
    </div>

    <!-- Eventos de formulario -->
    <form (submit)="handleSubmit($event)">
      <input type="text">
      <button type="submit">Submit</button>
    </form>
  `
})
export class UserComponent {
  greet() {
    alert('Hello!');
  }

  showProfile() {
    console.log('Profile clicked');
  }

  onInput(event: Event) {
    const value = (event.target as HTMLInputElement).value;
    console.log(value);
  }

  handleSubmit(event: Event) {
    event.preventDefault();
    console.log('Form submitted');
  }
}
```

### Gestión de Estado (Simple)

**Los componentes de Angular se re-renderizan automáticamente cuando las propiedades cambian:**

```typescript
@Component({
  selector: 'app-counter',
  standalone: true,
  template: `
    <h2>Count: {{ count }}</h2>
    <button (click)="count = count + 1">Increment</button>
    <button (click)="increment()">Increment (Method)</button>
    <button (click)="reset()">Reset</button>
  `
})
export class CounterComponent {
  count = 0;

  increment() {
    this.count++;
  }

  reset() {
    this.count = 0;
  }
}
```

**Re-renderizado automático:**
- Cuando cambias una propiedad (`this.count++`)
- Angular actualiza automáticamente la vista
- No hay que llamar a `setState()` como en React
- Funciona con cualquier cambio de propiedad

**Ejemplo con Renderizado Condicional:**
```typescript
@Component({
  selector: 'app-user',
  standalone: true,
  template: `
    @if (isLoggedIn) {
      <p>Welcome {{ username }}</p>
      <button (click)="isLoggedIn = false">Logout</button>
    } @else {
      <button (click)="isLoggedIn = true">Login</button>
    }
  `
})
export class UserComponent {
  username = 'johndoe';
  isLoggedIn = false;
}
```

### Enlace Bidireccional (Two-Way Binding)

**Usando `[(ngModel)]` para formularios:**

```typescript
import { FormsModule } from '@angular/forms';

@Component({
  selector: 'app-form',
  standalone: true,
  imports: [FormsModule],  // Requerido para ngModel
  template: `
    <input [(ngModel)]="username">
    <p>Hello {{ username }}</p>
  `
})
export class FormComponent {
  username = '';
}
```

**Nota:** Angular soporta un verdadero enlace bidireccional, a diferencia del flujo unidireccional de React.

---

## 10. Comunicación entre Componentes

### De Padre a Hijo (@Input)

**Pasar datos del componente padre al hijo:**

```typescript
// Componente Hijo
@Component({
  selector: 'app-games',
  standalone: true,
  template: `
    <h3>Favorite games of {{ username }}</h3>
    <ul>
      @for (game of games; track game.id) {
        <li>{{ game.name }}</li>
      }
    </ul>
  `
})
export class GamesComponent {
  @Input() username: string = '';  // Recibir del padre

  games = [
    { id: 1, name: 'Uncharted 4' },
    { id: 2, name: 'Horizon Zero Dawn' }
  ];
}

// Componente Padre
@Component({
  selector: 'app-user',
  standalone: true,
  imports: [GamesComponent],  // IMPORTANTE: Debe importar el hijo
  template: `
    <h2>User Profile</h2>
    <app-games [username]="currentUser" />
  `
})
export class UserComponent {
  currentUser = 'johndoe';
}
```

**Puntos Clave:**
1. Usa el decorador `@Input()` en el hijo
2. Importa `Input` desde `@angular/core`
3. El padre debe importar el componente hijo
4. Enlaza con `[propertyName]="value"`

### De Hijo a Padre (@Output)

**Emitir eventos del hijo al padre:**

```typescript
import { Component, Output, EventEmitter } from '@angular/core';

// Componente Hijo
@Component({
  selector: 'app-games',
  standalone: true,
  template: `
    <ul>
      @for (game of games; track game.id) {
        <li (click)="onGameClick(game.name)">
          {{ game.name }}
        </li>
      }
    </ul>
  `
})
export class GamesComponent {
  @Output() addFavoriteEvent = new EventEmitter<string>();

  games = [
    { id: 1, name: 'Uncharted 4' },
    { id: 2, name: 'Horizon Zero Dawn' },
    { id: 3, name: 'Bloodborne' }
  ];

  onGameClick(gameName: string) {
    // Emitir el evento al padre
    this.addFavoriteEvent.emit(gameName);
  }
}

// Componente Padre
@Component({
  selector: 'app-user',
  standalone: true,
  imports: [GamesComponent],
  template: `
    <h2>User Profile</h2>

    @if (favoriteGame !== '') {
      <p>Your favorite: {{ favoriteGame }}</p>
    }

    <!-- Suscribirse al evento del hijo -->
    <app-games (addFavoriteEvent)="getFavorite($event)" />
  `
})
export class UserComponent {
  favoriteGame = '';

  getFavorite(gameName: string) {
    this.favoriteGame = gameName;
    console.log('Favorite game:', gameName);
  }
}
```

**Flujo de Eventos:**
1. El hijo crea un `EventEmitter` con `@Output()`
2. El hijo emite eventos: `this.eventName.emit(data)`
3. El padre se suscribe: `(eventName)="handler($event)"`
4. `$event` contiene los datos emitidos

### Ejemplo de Comunicación Bidireccional

```typescript
// Ejemplo completo con @Input y @Output
import { Component, Input, Output, EventEmitter } from '@angular/core';

// Hijo
@Component({
  selector: 'app-game-selector',
  standalone: true,
  template: `
    <h3>{{ title }}</h3>
    @for (game of games; track game.id) {
      <button (click)="select(game)">
        {{ game.name }}
      </button>
    }
  `
})
export class GameSelectorComponent {
  @Input() title = 'Select a game';
  @Input() games: Game[] = [];
  @Output() gameSelected = new EventEmitter<Game>();

  select(game: Game) {
    this.gameSelected.emit(game);
  }
}

// Padre
@Component({
  selector: 'app-dashboard',
  standalone: true,
  imports: [GameSelectorComponent],
  template: `
    <app-game-selector
      [title]="'Choose your favorite'"
      [games]="availableGames"
      (gameSelected)="onGameSelected($event)"
    />

    @if (selectedGame) {
      <p>You selected: {{ selectedGame.name }}</p>
    }
  `
})
export class DashboardComponent {
  availableGames = [
    { id: 1, name: 'Uncharted 4' },
    { id: 2, name: 'Horizon Zero Dawn' }
  ];

  selectedGame: Game | null = null;

  onGameSelected(game: Game) {
    this.selectedGame = game;
  }
}

interface Game {
  id: number;
  name: string;
}
```

### Errores Comunes

**❌ Olvidar importar el componente hijo:**
```typescript
@Component({
  standalone: true,
  imports: [],  // ¡Falta el componente hijo!
  template: `<app-child />`  // ¡No funcionará!
})
```

**✅ Correcto:**
```typescript
@Component({
  standalone: true,
  imports: [ChildComponent],  // ¡Impórtalo!
  template: `<app-child />`
})
```

---

## 11. Directiva Defer - Lazy Loading

### Introducción

La directiva **@defer** (Angular 17+) es una de las funcionalidades más potentes para la optimización del rendimiento. Permite la **carga perezosa (lazy loading)** de componentes y sus dependencias.

**✅ Válido para Angular 17, 18 y 19**

### @defer Básico

**Diferir la carga hasta que se necesite:**

```typescript
@Component({
  selector: 'app-root',
  standalone: true,
  imports: [CommentsComponent],
  template: `
    <main>
      <h1>Article Content</h1>
      <p>Lorem ipsum dolor sit amet...</p>

      <!-- Este componente se carga cuando la CPU está inactiva -->
      @defer {
        <app-comments />
      }
    </main>
  `
})
export class AppComponent {}
```

**Qué pasa:**
1. El JavaScript de `CommentsComponent` **no se carga** inicialmente
2. Cuando el navegador está inactivo, Angular carga el componente
3. El componente se renderiza automáticamente cuando está listo

### @defer con @placeholder

**Mostrar un placeholder mientras está diferido:**

```typescript
@defer {
  <app-comments />
} @placeholder {
  <div style="height: 500px">
    <!-- Reservar espacio para los comentarios -->
  </div>
}
```

**Beneficios:**
- Previene el desplazamiento del layout (CLS - Cumulative Layout Shift)
- Reserva espacio para el componente diferido
- Puede estar vacío o tener contenido

### @defer con @loading

**Mostrar un estado de carga:**

```typescript
@defer {
  <app-comments />
} @placeholder {
  <div>Future comments section</div>
} @loading {
  <p>Loading comments...</p>
}
```

**Estados de Carga:**
1. **@placeholder** - Antes de que empiece la carga
2. **@loading** - Mientras se obtiene/carga
3. **Contenido** - Después de cargar

### Carga Basada en el Viewport

**Cargar cuando el elemento entra en el viewport:**

```typescript
@defer (on viewport) {
  <app-comments />
} @placeholder {
  <div>Scroll to load comments</div>
} @loading {
  <p>Loading comments...</p>
}
```

**Cómo funciona:**
1. El componente no se carga hasta que es visible
2. Ahorra ancho de banda para los usuarios que no hacen scroll
3. Intersection observer automático
4. Perfecto para el contenido below-the-fold

### @loading con Tiempo Mínimo

```typescript
@defer (on viewport) {
  <app-comments />
} @loading (minimum 1s) {
  <p>Loading comments...</p>
}
```

**Nota:** El tiempo mínimo normalmente **no se recomienda** (añade un retraso artificial).

### Condiciones de Disparo (Triggers)

**Múltiples triggers de defer:**

```html
<!-- On viewport (el más común) -->
@defer (on viewport) {
  <app-heavy-component />
}

<!-- On idle (por defecto si no se especifica trigger) -->
@defer (on idle) {
  <app-analytics />
}

<!-- On interaction -->
@defer (on interaction) {
  <app-modal />
}

<!-- On hover -->
@defer (on hover) {
  <app-tooltip />
}

<!-- On immediate (carga de inmediato, pero de forma perezosa) -->
@defer (on immediate) {
  <app-widget />
}

<!-- On timer -->
@defer (on timer(5s)) {
  <app-delayed />
}
```

### Prefetching

**Precargar antes de mostrarlo realmente:**

```typescript
@defer (on viewport; prefetch on idle) {
  <app-comments />
}
```

**Estrategia:**
- Precargar el código del componente cuando está inactivo
- No renderizar hasta el viewport
- Lo mejor de ambos mundos

### Ejemplo del Mundo Real

```typescript
@Component({
  selector: 'app-article',
  standalone: true,
  imports: [CommentsComponent],
  template: `
    <article>
      <h1>{{ title }}</h1>
      <div [innerHTML]="content"></div>

      <!-- Comentarios diferidos hasta el viewport -->
      @defer (on viewport; prefetch on idle) {
        <app-comments [articleId]="articleId" />
      } @placeholder {
        <div style="min-height: 400px; border: 1px solid #ccc; padding: 20px;">
          Comments section will load when you scroll here
        </div>
      } @loading (minimum 500ms) {
        <div class="loading-spinner">
          <p>Loading comments...</p>
        </div>
      }
    </article>
  `,
  styles: [`
    article { max-width: 800px; margin: 0 auto; }
    .loading-spinner { text-align: center; padding: 40px; }
  `]
})
export class ArticleComponent {
  title = 'Angular 17 Defer Directive';
  articleId = 123;
  content = '<p>Long article content...</p>';
}
```

### Impacto en el Rendimiento

**Antes de @defer:**
```
Bundle Inicial: 500KB
- main.js: 300KB
- comments.js: 200KB (cargado pero no visible)

Tiempo hasta Interactivo: 2.5s
```

**Después de @defer (on viewport):**
```
Bundle Inicial: 300KB
- main.js: 300KB
- comments.js: Cargado solo cuando se necesita

Tiempo hasta Interactivo: 1.2s
Chunk perezoso (comments): 200KB (cargado al hacer scroll)
```

**Ahorros:**
- Bundle inicial 40% más pequeño
- Tiempo hasta interactivo ~50% más rápido
- Mejores puntuaciones de Core Web Vitals

### Cascada de Red (Network Waterfall)

**Sin @defer:**
```
[=============================] main.js (300KB)
[=============================] comments.js (200KB) ← Cargado inmediatamente
[====] image.png (170KB) ← Bloqueado por el JS

Total: 670KB en la carga de la página
```

**Con @defer:**
```
[=============================] main.js (300KB)
[============================] otros recursos
                              [====] comments.js (200KB) ← Cargado de forma perezosa
                              [====] image.png (170KB) ← Cargado de forma perezosa

Carga inicial: 300KB
Diferido: 370KB (cargado cuando se necesita)
```

### Buenas Prácticas

**✅ Buenos casos de uso:**
- Secciones de comentarios
- Widgets below-the-fold
- Componentes pesados de terceros
- Paneles de administración/dashboards
- Widgets de chat

**❌ No diferir:**
- Contenido above-the-fold
- Navegación crítica
- Formularios que el usuario necesita de inmediato
- Contenido crítico para el SEO

### Combinado con Signals

```typescript
@Component({
  selector: 'app-dashboard',
  standalone: true,
  template: `
    <button (click)="showComments.set(true)">Load Comments</button>

    @if (showComments()) {
      @defer {
        <app-comments />
      } @loading {
        <p>Loading...</p>
      }
    }
  `
})
export class DashboardComponent {
  showComments = signal(false);
}
```

---

## 12. Signals y Programación Reactiva

### ¿Qué son los Signals?

**Signals** = Primitivas reactivas de Angular para la reactividad de grano fino

**Estado:** ✅ **Estable en Angular 19** (introducido experimentalmente en Angular 16)

**Concepto Clave:**
- Canales reactivos para el flujo de datos
- Rastreo automático de dependencias
- Detección de cambios eficiente
- Alternativa a RxJS para el estado simple
- No más advertencias "experimentales" en Angular 19+

### Analogía de la Programación Reactiva

**La Metáfora del Tubo:**

Imagina un **tubo (canal)** con **agujeros** a los lados:
- **Tubo** = Observable/Signal (canal para los datos)
- **Agujeros** = Suscriptores/Observadores (espectadores)
- **Pelota** = Evento/Dato (información que pasa)

Cada espectador ve la pelota de forma diferente:
- Espectador 1: "¡Pasó una pelota!"
- Espectador 2: "¡Era verde!"
- Espectador 3: "¡Se movía a 20 km/h!"

**Cada observador reacciona de forma diferente al mismo evento** = Programación Reactiva

### RxJS Observables

**Tres Tipos de Observables:**

```typescript
import { Observable, Subject, BehaviorSubject } from 'rxjs';

// 1. Observable - Unidireccional (un productor, muchos consumidores)
const observable$ = new Observable<number>(observer => {
  observer.next(1);
  observer.next(2);
  observer.complete();
});

// 2. Subject - Bidireccional (cualquiera puede emitir)
const subject$ = new Subject<string>();
subject$.next('Hello');  // Cualquiera puede emitir

// 3. BehaviorSubject - Bidireccional + Buffer (almacena el último valor)
const behavior$ = new BehaviorSubject<number>(0);  // Valor inicial
console.log(behavior$.value);  // Acceder al valor actual
behavior$.next(1);
```

### Signals de Angular

**Creando y Usando Signals:**

```typescript
import { Component, signal, computed, effect } from '@angular/core';

@Component({
  selector: 'app-counter',
  standalone: true,
  template: `
    <h2>Count: {{ count() }}</h2>
    <h3>Double: {{ double() }}</h3>
    <button (click)="increment()">+1</button>
  `
})
export class CounterComponent {
  // Signal escribible
  count = signal(0);

  // Signal calculado (se actualiza automáticamente)
  double = computed(() => this.count() * 2);

  // Effect (se ejecuta cuando los signals cambian)
  constructor() {
    effect(() => {
      console.log('Count changed:', this.count());
    });
  }

  increment() {
    this.count.set(this.count() + 1);
    // o: this.count.update(value => value + 1);
  }
}
```

### Métodos de Signal

```typescript
const count = signal(0);

// Leer el valor
console.log(count());  // 0

// Establecer un nuevo valor
count.set(10);

// Actualizar basándose en el valor anterior
count.update(value => value + 1);

// Mutar objetos/arrays
const users = signal([{ name: 'Alan' }]);
users.mutate(arr => arr.push({ name: 'Marco' }));
```

### Signals vs RxJS

**Cuándo usar Signals:**
- Gestión de estado simple
- Valores síncronos
- Estado del componente
- Valores derivados/calculados

**Cuándo usar RxJS:**
- Operaciones asíncronas
- Peticiones HTTP
- Flujos de eventos complejos
- Operaciones basadas en el tiempo
- Conexiones WebSocket

**¡Se complementan entre sí!**

```typescript
import { toSignal, toObservable } from '@angular/core/rxjs-interop';

// Convertir Observable a Signal
const data$ = this.http.get('/api/users');
const users = toSignal(data$, { initialValue: [] });

// Convertir Signal a Observable
const count = signal(0);
const count$ = toObservable(count);
```

### Signals Avanzados (Angular 19+)

**Para las funcionalidades avanzadas de signals introducidas en Angular 19 y 20, ver:**
- [Sección 19: Funcionalidades de Angular 19](#19-funcionalidades-de-angular-19) - linkedSignal, Resource API
- [Sección 20: Funcionalidades de Angular 20](#20-funcionalidades-de-angular-20) - API de Signals Estable

**Nota:** Todas las APIs de signals se volvieron **estables** en Angular 20.

---

## 13. Detección de Cambios

### Forma Antigua: Zone.js

**Cómo Funciona Zone.js:**

Zone.js parchea (monkey-patch) las APIs del navegador y dispara la detección de cambios en cada operación asíncrona:

```typescript
// Zone.js intercepta:
- setTimeout/setInterval
- Promise.then()
- Peticiones HTTP
- Eventos del DOM (click, input, etc.)
- XMLHttpRequest

// Problema: Comprueba TODO el árbol de componentes
// ¡Aunque solo un componente haya cambiado!
```

**Problemas de Rendimiento:**
- Se propaga por todo el árbol de componentes
- Ineficiente para aplicaciones grandes
- Comprobaciones innecesarias

### Estrategias de Detección de Cambios (Era de Zone.js)

```typescript
import { ChangeDetectionStrategy } from '@angular/core';

@Component({
  selector: 'app-user',
  changeDetection: ChangeDetectionStrategy.OnPush,  // ✅ Recomendado
  // changeDetection: ChangeDetectionStrategy.Default  // ❌ Comprueba todo
})
export class UserComponent {}
```

**Estrategia OnPush:**
Solo comprueba cuando:
1. **@Input** cambia
2. **Eventos** del componente (click, etc.)
3. Los **pipes async** reciben nuevos valores
4. Disparo **manual** vía `ChangeDetectorRef`

### Forma Moderna: Zoneless + Signals

**Habilitar Zoneless (Experimental en Angular 18):**

```typescript
// app.config.ts
import { provideExperimentalZonelessChangeDetection } from '@angular/core';

export const appConfig: ApplicationConfig = {
  providers: [
    provideExperimentalZonelessChangeDetection()
  ]
};
```

**Cómo los Signals Habilitan Zoneless:**

Los signals saben exactamente qué depende de ellos:

```typescript
// Grafo de signals
count (Signal)
  ├── double (Computed)
  │     └── Enlace de plantilla
  └── Enlace de plantilla

// Cuando count cambia:
// ✅ Solo actualiza: double + enlaces de plantilla
// ❌ NO comprueba: otros componentes, valores no relacionados
```

**Beneficios de Eliminar Zone.js:**
- ⚡ Detección de cambios más rápida
- 📦 Tamaño de bundle menor (~50KB eliminados)
- 🎯 Actualizaciones quirúrgicas (solo lo que cambió)
- 🧹 Arquitectura más limpia

### ¿Puedes Eliminar Zone.js Ahora?

**Consideraciones:**

```typescript
// angular.json - polyfill de Zone.js
"polyfills": [
  "zone.js"  // Se puede eliminar SI se cumplen todas las condiciones
]
```

**Elimina Zone.js SI:**
- ✅ Todos los componentes usan OnPush o signals
- ✅ Ninguna librería externa depende de Zone.js
- ✅ Usas la detección de cambios zoneless (estable en Angular 20.2+)

**Mantén Zone.js SI:**
- ❌ Usas librerías como AngularFire (depende de Zone.js)
- ❌ Código legado con detección de cambios Default
- ❌ No estás listo para las funcionalidades zoneless

**Para la información más reciente sobre zoneless, ver:**
- [Sección 20: Funcionalidades de Angular 20](#20-funcionalidades-de-angular-20) - Zoneless opt-in estable
- [Sección 21: Angular 20.2 y Más Allá](#21-angular-202-y-más-allá) - Zoneless totalmente estable

---

## 14. Renderizado del Lado del Servidor

### Angular Universal → SSR Integrado

**Evolución:**

1. **Angular Universal (Antiguo):**
   - Librería separada
   - Configuración compleja
   - Renderizado universal (renderiza dos veces)
   - Problemas de parpadeo

2. **SSR Integrado (Angular 17+):**
   - Integrado en Angular
   - Configuración simple
   - Hidratación mejorada
   - Renderizado parcial

### Flujo del Renderizado del Lado del Servidor

**SSR Tradicional:**
```
1. El servidor envía HTML + JS
2. El navegador muestra el HTML (no interactivo)
3. El navegador descarga el JS
4. Ocurre la hidratación
5. La página se vuelve interactiva

Problema: Largo periodo no interactivo
```

**SSR Moderno de Angular con Hidratación:**
```
1. El servidor renderiza HTML + estado serializado
2. El navegador muestra el HTML (no interactivo)
3. El navegador descarga JS mínimo
4. Hidratación incremental
5. Event replay (¡los clics durante la carga se cachean!)

Beneficios:
- Tiempo-hasta-interactivo más rápido
- Event replay (sin clics perdidos)
- Hidratación parcial (solo lo necesario)
```

### Configuración del Servidor

**server.ts (Servidor Express):**
```typescript
import { APP_BASE_HREF } from '@angular/common';
import { CommonEngine } from '@angular/ssr';
import express from 'express';
import { fileURLToPath } from 'node:url';
import { dirname, join, resolve } from 'node:path';
import bootstrap from './src/main.server';

export function app(): express.Express {
  const server = express();
  const serverDistFolder = dirname(fileURLToPath(import.meta.url));
  const browserDistFolder = resolve(serverDistFolder, '../browser');
  const indexHtml = join(serverDistFolder, 'index.server.html');

  const commonEngine = new CommonEngine();

  server.set('view engine', 'html');
  server.set('views', browserDistFolder);

  // Servir archivos estáticos
  server.get('*.*', express.static(browserDistFolder, {
    maxAge: '1y'
  }));

  // Todas las rutas usan el motor de Angular
  server.get('*', (req, res, next) => {
    const { protocol, originalUrl, baseUrl, headers } = req;

    commonEngine
      .render({
        bootstrap,
        documentFilePath: indexHtml,
        url: `${protocol}://${headers.host}${originalUrl}`,
        publicPath: browserDistFolder,
        providers: [{ provide: APP_BASE_HREF, useValue: baseUrl }],
      })
      .then((html) => res.send(html))
      .catch((err) => next(err));
  });

  return server;
}
```

### Configuración de SSR

**app.config.ts:**
```typescript
import { provideClientHydration } from '@angular/platform-browser';

export const appConfig: ApplicationConfig = {
  providers: [
    provideClientHydration()  // Habilitar la hidratación
  ]
};
```

### Event Replay (Nueva Funcionalidad)

**Cacheando las Interacciones del Usuario:**

```typescript
// El usuario hace clic en un botón antes de que la hidratación se complete
// Comportamiento antiguo: El clic se pierde ❌
// Comportamiento nuevo: El clic se cachea y se reproduce ✅

import {
  provideClientHydration,
  withEventReplay
} from '@angular/platform-browser';

export const appConfig: ApplicationConfig = {
  providers: [
    provideClientHydration(withEventReplay())
  ]
};
```

### Hidratación Parcial (Experimental)

**Concepto:** Solo hidratar los componentes que se usan

```typescript
// Componente sin interacción → No hidratado
// Componente con clic → Hidratar solo ese componente + dependencias

// Beneficios:
// - Menos JavaScript ejecutado
// - Tiempo-hasta-interactivo más rápido
// - Mejor rendimiento en dispositivos de gama baja
```

### Funcionalidades Avanzadas de SSR (Angular 19+)

**Para las últimas mejoras de SSR introducidas en Angular 19, ver:**
- [Sección 19: Funcionalidades de Angular 19](#19-funcionalidades-de-angular-19) - Event Replay por defecto, Modos de renderizado a nivel de ruta (interfaz ServerRoute)

---

## 15. Bundling y Optimización

### ¿Qué es un Bundler?

**Operaciones del Bundler:**

1. **Transpilación** - TypeScript → JavaScript (de alto nivel a alto nivel)
2. **Minificación** - Eliminar espacios en blanco, acortar nombres
3. **Ofuscación (Uglification)** - Hacer el código ilegible (seguridad + rendimiento)
4. **Bundling** - Combinar archivos en chunks
5. **Tree-shaking** - Eliminar el código sin usar
6. **Code splitting** - Crear chunks de carga perezosa

### Evolución: Webpack → Rollup + Vite

**Antiguo (Angular < 17):**
- Webpack
- Builds más lentos
- Bundles más grandes
- Configuración compleja

**Nuevo (Angular 17+):**
- Rollup para los builds de producción
- Vite para el desarrollo (HMR rápido)
- Builds más rápidos (¡hasta un 67% más rápido!)
- Bundles más pequeños
- Módulos ESM

### Lazy Loading

**Concepto:** Cargar código solo cuando se necesita

**Beneficios:**
1. **Rendimiento** - Bundle inicial más pequeño
2. **Seguridad** - El código no existe hasta que se necesita

**Lazy Loading Basado en Rutas:**
```typescript
// app.routes.ts
export const routes: Routes = [
  {
    path: 'dashboard',
    loadComponent: () => import('./dashboard/dashboard.component')
      .then(m => m.DashboardComponent)
  },
  {
    path: 'profile',
    loadChildren: () => import('./profile/profile.routes')
      .then(m => m.profileRoutes)
  }
];
```

**Cómo Funciona:**

```
Bundle Inicial:
- app.component.ts
- main.ts
- dependencias core

Bundles con Carga Perezosa (creados automáticamente):
- dashboard-chunk-ABC123.js  (cargado al navegar a /dashboard)
- profile-chunk-DEF456.js     (cargado al navegar a /profile)

Beneficio de seguridad:
- El código del dashboard no existe para usuarios no logueados
- ¡No se puede descifrar lo que no existe!
```

### Salida del Build

**Build de Desarrollo:**
```bash
ng serve
# Rebuilds rápidos
# Source maps incluidos
# Sin optimización
```

**Build de Producción:**
```bash
ng build

# Salida (dist/):
dist/
  ├── browser/
  │   ├── main-HASH.js           # Bundle principal
  │   ├── polyfills-HASH.js      # Polyfills
  │   ├── styles-HASH.css        # Estilos
  │   └── chunk-ABC.js           # Chunk perezoso
  └── server/
      └── server.mjs             # Servidor SSR
```

**Análisis del Bundle:**
- **main.js** - Código de la aplicación
- **polyfills.js** - Compatibilidad del navegador (Zone.js, etc.)
- **styles.css** - Estilos globales
- **chunk-*.js** - Módulos de carga perezosa

### Ejemplo de Tree-Shaking

```typescript
// utils.ts
export function usedFunction() {
  console.log('Used');
}

export function unusedFunction() {
  console.log('Never called');
}

// app.component.ts
import { usedFunction } from './utils';

usedFunction();

// Bundle de producción:
// ✅ Incluye: usedFunction
// ❌ Eliminado: unusedFunction (tree-shaken)
```

---

## 16. Configuración del Proyecto

### angular.json

**Configuración Clave:**

```json
{
  "projects": {
    "app": {
      "architect": {
        "build": {
          "builder": "@angular/build:application",
          "options": {
            "outputPath": "dist",
            "index": "src/index.html",
            "browser": "src/main.ts",
            "server": "src/main.server.ts",
            "polyfills": ["zone.js"],  // Se puede eliminar en apps zoneless
            "assets": ["src/favicon.ico", "src/assets"],
            "styles": ["src/styles.scss"],
            "scripts": []
          },
          "configurations": {
            "production": {
              "budgets": [
                {
                  "type": "initial",
                  "maximumWarning": "500kb",
                  "maximumError": "1mb"
                }
              ],
              "outputHashing": "all"
            },
            "development": {
              "optimization": false,
              "extractLicenses": false,
              "sourceMap": true
            }
          }
        },
        "serve": {
          "builder": "@angular/build:dev-server",
          "options": {
            "buildTarget": "app:build"
          }
        }
      },
      "schematics": {
        "@schematics/angular:component": {
          "style": "scss",
          "changeDetection": "OnPush",
          "standalone": true
        }
      }
    }
  }
}
```

### tsconfig.json Explicado

```json
{
  "compilerOptions": {
    // Versión ES objetivo
    "target": "ES2022",

    // Sistema de módulos
    "module": "ES2022",
    "moduleResolution": "bundler",

    // Soporte de decoradores
    "experimentalDecorators": true,
    "emitDecoratorMetadata": true,

    // Campos de clase
    "useDefineForClassFields": true,

    // Alias de rutas
    "baseUrl": "./",
    "paths": {
      "@app/*": ["src/app/*"],
      "@environments/*": ["src/environments/*"]
    },

    // Source maps
    "sourceMap": true,

    // Comprobación estricta de tipos
    "strict": true,
    "noImplicitAny": true,
    "strictNullChecks": true
  }
}
```

### Scripts del Package

```json
{
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "watch": "ng build --watch",
    "test": "ng test",
    "serve:ssr": "node dist/server/server.mjs"
  }
}
```

### Uso de Alias de Rutas

```typescript
// Sin alias ❌
import { UserService } from '../../../services/user.service';
import { environment } from '../../../environments/environment';

// Con alias ✅
import { UserService } from '@app/services/user.service';
import { environment } from '@environments/environment';
```

---

## 17. HTTP Interceptors

### ¿Qué son los HTTP Interceptors?

Los **HTTP Interceptors** son una funcionalidad potente en Angular que te permite interceptar y modificar las peticiones y respuestas HTTP de forma global en toda tu aplicación.

**Casos de Uso Comunes:**
- Añadir tokens de autenticación a las peticiones
- Registrar el tráfico HTTP
- Manejo de errores
- Cachear respuestas
- Modificar las cabeceras de petición/respuesta
- Indicadores de carga
- Lógica de reintentos

### Interceptores Funcionales (Recomendado)

Angular 15+ introdujo los **interceptores funcionales**, que son el enfoque recomendado sobre los interceptores basados en clases.

**Documentación Oficial:** [angular.dev/guide/http/interceptors](https://angular.dev/guide/http/interceptors)

### Interceptor Funcional Básico

```typescript
import { HttpInterceptorFn } from '@angular/common/http';

export const loggingInterceptor: HttpInterceptorFn = (req, next) => {
  // Registrar la petición saliente
  console.log('HTTP Request:', req.method, req.url);

  // Reenviar la petición al siguiente handler
  return next(req);
};
```

### Configurando Interceptores

**app.config.ts:**
```typescript
import { ApplicationConfig } from '@angular/core';
import { provideHttpClient, withInterceptors } from '@angular/common/http';
import { loggingInterceptor } from './interceptors/logging.interceptor';
import { authInterceptor } from './interceptors/auth.interceptor';

export const appConfig: ApplicationConfig = {
  providers: [
    provideHttpClient(
      withInterceptors([
        loggingInterceptor,  // Se ejecuta primero
        authInterceptor      // Se ejecuta segundo
      ])
    )
  ]
};
```

**El orden importa:** Los interceptores se ejecutan en el orden en que se listan.

### Interceptor de Autenticación

```typescript
import { HttpInterceptorFn } from '@angular/common/http';
import { inject } from '@angular/core';
import { AuthService } from '../services/auth.service';

export const authInterceptor: HttpInterceptorFn = (req, next) => {
  const authService = inject(AuthService);
  const token = authService.getToken();

  // Clonar la petición y añadir la cabecera Authorization
  if (token) {
    req = req.clone({
      setHeaders: {
        Authorization: `Bearer ${token}`
      }
    });
  }

  return next(req);
};
```

### Interceptor de Manejo de Errores

```typescript
import { HttpInterceptorFn, HttpErrorResponse } from '@angular/common/http';
import { inject } from '@angular/core';
import { Router } from '@angular/router';
import { catchError, throwError } from 'rxjs';

export const errorInterceptor: HttpInterceptorFn = (req, next) => {
  const router = inject(Router);

  return next(req).pipe(
    catchError((error: HttpErrorResponse) => {
      if (error.status === 401) {
        // No autorizado - redirigir al login
        router.navigate(['/login']);
      } else if (error.status === 500) {
        // Error del servidor - mostrar mensaje de error
        console.error('Server Error:', error.message);
      }

      return throwError(() => error);
    })
  );
};
```

### Interceptor de Indicador de Carga

```typescript
import { HttpInterceptorFn } from '@angular/common/http';
import { inject } from '@angular/core';
import { LoadingService } from '../services/loading.service';
import { finalize } from 'rxjs/operators';

export const loadingInterceptor: HttpInterceptorFn = (req, next) => {
  const loadingService = inject(LoadingService);

  // Mostrar el indicador de carga
  loadingService.show();

  return next(req).pipe(
    finalize(() => {
      // Ocultar el indicador de carga cuando la petición se completa
      loadingService.hide();
    })
  );
};
```

### Modificando Respuestas

```typescript
import { HttpInterceptorFn, HttpResponse } from '@angular/common/http';
import { map } from 'rxjs/operators';

export const responseInterceptor: HttpInterceptorFn = (req, next) => {
  return next(req).pipe(
    map(event => {
      // Solo procesar los eventos HttpResponse
      if (event instanceof HttpResponse) {
        // Modificar el cuerpo de la respuesta
        return event.clone({
          body: {
            ...event.body,
            timestamp: new Date().toISOString()
          }
        });
      }
      return event;
    })
  );
};
```

### Interceptor de Caché

```typescript
import { HttpInterceptorFn, HttpResponse } from '@angular/common/http';
import { of } from 'rxjs';
import { tap } from 'rxjs/operators';

const cache = new Map<string, HttpResponse<any>>();

export const cachingInterceptor: HttpInterceptorFn = (req, next) => {
  // Solo cachear las peticiones GET
  if (req.method !== 'GET') {
    return next(req);
  }

  // Comprobar si la respuesta está en caché
  const cachedResponse = cache.get(req.url);
  if (cachedResponse) {
    return of(cachedResponse.clone());
  }

  // Si no está en caché, hacer la petición y cachear la respuesta
  return next(req).pipe(
    tap(event => {
      if (event instanceof HttpResponse) {
        cache.set(req.url, event.clone());
      }
    })
  );
};
```

### Inmutabilidad de la Petición

**Importante:** Los objetos HttpRequest y HttpResponse son **inmutables**.

```typescript
// ❌ Esto no funcionará
req.headers.set('Authorization', 'Bearer token');

// ✅ Hay que clonar y modificar
req = req.clone({
  setHeaders: {
    Authorization: 'Bearer token'
  }
});

// ✅ Múltiples modificaciones
req = req.clone({
  setHeaders: {
    Authorization: 'Bearer token',
    'Content-Type': 'application/json'
  },
  url: req.url + '?timestamp=' + Date.now()
});
```

### Ejemplo de Múltiples Interceptores

```typescript
// app.config.ts
import { provideHttpClient, withInterceptors } from '@angular/common/http';
import { loggingInterceptor } from './interceptors/logging.interceptor';
import { authInterceptor } from './interceptors/auth.interceptor';
import { errorInterceptor } from './interceptors/error.interceptor';
import { loadingInterceptor } from './interceptors/loading.interceptor';

export const appConfig: ApplicationConfig = {
  providers: [
    provideHttpClient(
      withInterceptors([
        loggingInterceptor,   // 1. Registrar la petición
        authInterceptor,      // 2. Añadir el token de auth
        loadingInterceptor,   // 3. Mostrar la carga
        errorInterceptor      // 4. Manejar los errores
      ])
    )
  ]
};
```

### Interceptores Basados en Clases (Legado)

**Nota:** Aunque aún se soportan, se recomiendan los interceptores funcionales.

```typescript
import { Injectable } from '@angular/core';
import { HttpInterceptor, HttpRequest, HttpHandler } from '@angular/common/http';

@Injectable()
export class AuthInterceptorLegacy implements HttpInterceptor {
  intercept(req: HttpRequest<any>, next: HttpHandler) {
    const token = localStorage.getItem('token');

    if (token) {
      req = req.clone({
        setHeaders: { Authorization: `Bearer ${token}` }
      });
    }

    return next.handle(req);
  }
}

// Configuración (forma legada)
providers: [
  provideHttpClient(
    withInterceptorsFromDi()  // Habilitar los interceptores basados en DI
  ),
  {
    provide: HTTP_INTERCEPTORS,
    useClass: AuthInterceptorLegacy,
    multi: true
  }
]
```

### Buenas Prácticas

**✅ Interceptores Funcionales:**
- Comportamiento más predecible
- Mejor para configuraciones complejas
- Recomendados por el equipo de Angular
- Usa la inyección de dependencias con `inject()`

**✅ El Orden Importa:**
- Lista los interceptores en el orden de ejecución
- Autenticación antes del manejo de errores
- Logging primero para la depuración

**✅ Inmutabilidad:**
- Clona siempre las peticiones/respuestas
- No mutes los objetos originales

**✅ Manejo de Errores:**
- Maneja siempre los errores con elegancia
- Proporciona fallbacks
- Registra los errores apropiadamente

**❌ Evita:**
- Operaciones síncronas bloqueantes
- Cálculos pesados en los interceptores
- Dependencias circulares con servicios inyectados

---

## 18. Route Guards

### ¿Qué son los Route Guards?

Los **Route Guards** controlan el acceso a las rutas en las aplicaciones Angular. Determinan si un usuario puede navegar hacia, fuera de, o a través de una ruta.

**Documentación Oficial:** [angular.dev/guide/routing/route-guards](https://angular.dev/guide/routing/route-guards)

### Tipos de Route Guards

| Tipo de Guard | Propósito | Tipo de Retorno |
|------------|---------|-------------|
| **canActivate** | ¿Puede el usuario activar esta ruta? | boolean, UrlTree, Observable, Promise |
| **canActivateChild** | ¿Puede el usuario activar las rutas hijas? | boolean, UrlTree, Observable, Promise |
| **canDeactivate** | ¿Puede el usuario abandonar esta ruta? | boolean, UrlTree, Observable, Promise |
| **canMatch** | ¿Se puede emparejar la ruta? (antes del lazy loading) | boolean, UrlTree, Observable, Promise |
| **resolve** | Obtener datos antes de la activación | cualquier tipo |

### Guards Funcionales (Recomendado)

Angular 14+ introdujo los **guards funcionales**, que son más simples y flexibles que los guards basados en clases.

### canActivate - Guard de Autenticación

**Propósito:** Evitar que usuarios no autorizados accedan a las rutas.

```typescript
// auth.guard.ts
import { CanActivateFn, Router } from '@angular/router';
import { inject } from '@angular/core';
import { AuthService } from '../services/auth.service';

export const authGuard: CanActivateFn = (route, state) => {
  const authService = inject(AuthService);
  const router = inject(Router);

  if (authService.isAuthenticated()) {
    return true;  // Permitir la navegación
  }

  // Redirigir al login
  return router.createUrlTree(['/login'], {
    queryParams: { returnUrl: state.url }
  });
};
```

**Configuración de la Ruta:**
```typescript
// app.routes.ts
import { Routes } from '@angular/router';
import { authGuard } from './guards/auth.guard';

export const routes: Routes = [
  {
    path: 'dashboard',
    component: DashboardComponent,
    canActivate: [authGuard]  // Proteger esta ruta
  },
  {
    path: 'profile',
    component: ProfileComponent,
    canActivate: [authGuard]
  },
  {
    path: 'login',
    component: LoginComponent
  }
];
```

### canMatch - Guard de Feature Flag

**Propósito:** Emparejar rutas condicionalmente según feature flags o A/B testing.

**Diferencia Clave:** `canMatch` evita que la ruta sea emparejada, mientras que `canActivate` evita la navegación a una ruta ya emparejada.

```typescript
// feature-flag.guard.ts
import { CanMatchFn } from '@angular/router';
import { inject } from '@angular/core';
import { FeatureFlagService } from '../services/feature-flag.service';

export const featureFlagGuard: CanMatchFn = (route, segments) => {
  const featureService = inject(FeatureFlagService);
  const featureFlag = route.data?.['featureFlag'];

  // Comprobar si la funcionalidad está habilitada
  return featureService.isEnabled(featureFlag);
};
```

**Configuración de la Ruta:**
```typescript
export const routes: Routes = [
  {
    path: 'beta-feature',
    component: BetaFeatureComponent,
    canMatch: [featureFlagGuard],
    data: { featureFlag: 'beta-enabled' }
  },
  {
    path: 'beta-feature',  // Ruta de respaldo (fallback)
    component: FeatureDisabledComponent
  }
];
```

### canDeactivate - Guard de Cambios sin Guardar

**Propósito:** Advertir a los usuarios antes de abandonar una página con cambios sin guardar.

```typescript
// unsaved-changes.guard.ts
import { CanDeactivateFn } from '@angular/router';

export interface CanComponentDeactivate {
  canDeactivate: () => boolean | Promise<boolean>;
}

export const unsavedChangesGuard: CanDeactivateFn<CanComponentDeactivate> = (component) => {
  return component.canDeactivate ? component.canDeactivate() : true;
};
```

**Implementación del Componente:**
```typescript
// edit-form.component.ts
import { Component } from '@angular/core';
import { CanComponentDeactivate } from './guards/unsaved-changes.guard';

@Component({
  selector: 'app-edit-form',
  standalone: true,
  template: `
    <form>
      <input [(ngModel)]="formData" />
      <button (click)="save()">Save</button>
    </form>
  `
})
export class EditFormComponent implements CanComponentDeactivate {
  formData = '';
  saved = false;

  save() {
    this.saved = true;
  }

  canDeactivate(): boolean {
    if (!this.saved && this.formData) {
      return confirm('You have unsaved changes. Do you really want to leave?');
    }
    return true;
  }
}
```

**Configuración de la Ruta:**
```typescript
import { unsavedChangesGuard } from './guards/unsaved-changes.guard';

export const routes: Routes = [
  {
    path: 'edit',
    component: EditFormComponent,
    canDeactivate: [unsavedChangesGuard]
  }
];
```

### Guard de Autorización Basado en Roles

```typescript
// role.guard.ts
import { CanActivateFn, Router } from '@angular/router';
import { inject } from '@angular/core';
import { AuthService } from '../services/auth.service';

export const roleGuard = (allowedRoles: string[]): CanActivateFn => {
  return (route, state) => {
    const authService = inject(AuthService);
    const router = inject(Router);

    const userRole = authService.getUserRole();

    if (allowedRoles.includes(userRole)) {
      return true;
    }

    // Redirigir a la página de no autorizado
    return router.createUrlTree(['/unauthorized']);
  };
};
```

**Configuración de la Ruta:**
```typescript
export const routes: Routes = [
  {
    path: 'admin',
    component: AdminComponent,
    canActivate: [roleGuard(['admin', 'superadmin'])]
  },
  {
    path: 'editor',
    component: EditorComponent,
    canActivate: [roleGuard(['admin', 'editor'])]
  }
];
```

### Guards Asíncronos con Observables

```typescript
// permission.guard.ts
import { CanActivateFn, Router } from '@angular/router';
import { inject } from '@angular/core';
import { PermissionService } from '../services/permission.service';
import { map } from 'rxjs/operators';

export const permissionGuard: CanActivateFn = (route, state) => {
  const permissionService = inject(PermissionService);
  const router = inject(Router);
  const requiredPermission = route.data?.['permission'];

  return permissionService.hasPermission(requiredPermission).pipe(
    map(hasPermission => {
      if (hasPermission) {
        return true;
      }
      return router.createUrlTree(['/forbidden']);
    })
  );
};
```

### Múltiples Guards en la Misma Ruta

```typescript
export const routes: Routes = [
  {
    path: 'protected',
    component: ProtectedComponent,
    canActivate: [
      authGuard,              // 1. Comprobar si está autenticado
      roleGuard(['admin']),   // 2. Comprobar si tiene rol de admin
      permissionGuard         // 3. Comprobar un permiso específico
    ]
  }
];
```

**Orden de Ejecución:** Los guards se ejecutan en el orden en que se listan. Si algún guard devuelve `false`, la navegación se cancela.

### CanActivateChild - Proteger Rutas Hijas

```typescript
// parent.guard.ts
import { CanActivateChildFn } from '@angular/router';
import { inject } from '@angular/core';
import { AuthService } from '../services/auth.service';

export const parentGuard: CanActivateChildFn = (childRoute, state) => {
  const authService = inject(AuthService);
  return authService.isAuthenticated();
};
```

**Configuración de la Ruta:**
```typescript
export const routes: Routes = [
  {
    path: 'admin',
    component: AdminLayoutComponent,
    canActivateChild: [parentGuard],  // Protege todas las hijas
    children: [
      { path: 'users', component: UsersComponent },
      { path: 'settings', component: SettingsComponent },
      { path: 'reports', component: ReportsComponent }
    ]
  }
];
```

### Resolve Guard - Pre-obtener Datos

```typescript
// user-resolver.ts
import { ResolveFn } from '@angular/router';
import { inject } from '@angular/core';
import { UserService } from '../services/user.service';
import { User } from '../models/user.model';

export const userResolver: ResolveFn<User> = (route, state) => {
  const userService = inject(UserService);
  const userId = route.paramMap.get('id')!;

  return userService.getUserById(userId);
};
```

**Configuración de la Ruta:**
```typescript
export const routes: Routes = [
  {
    path: 'user/:id',
    component: UserDetailComponent,
    resolve: { user: userResolver }  // Datos disponibles antes de que cargue el componente
  }
];
```

**Acceso desde el Componente:**
```typescript
@Component({
  selector: 'app-user-detail',
  standalone: true,
  template: `<h1>{{ user.name }}</h1>`
})
export class UserDetailComponent {
  route = inject(ActivatedRoute);

  user = this.route.snapshot.data['user'];  // Datos pre-obtenidos
}
```

### Guards Basados en Clases (Legado)

**Nota:** Aún se soportan pero se recomiendan los guards funcionales.

```typescript
import { Injectable } from '@angular/core';
import { CanActivate, Router } from '@angular/router';
import { AuthService } from '../services/auth.service';

@Injectable({ providedIn: 'root' })
export class AuthGuardLegacy implements CanActivate {
  constructor(
    private authService: AuthService,
    private router: Router
  ) {}

  canActivate(): boolean {
    if (this.authService.isAuthenticated()) {
      return true;
    }
    this.router.navigate(['/login']);
    return false;
  }
}
```

### Buenas Prácticas

**✅ Guards Funcionales:**
- Más simples, más concisos
- Mejor inferencia de TypeScript
- Más fáciles de testear
- Se pueden componer fácilmente

**✅ Devuelve UrlTree para las Redirecciones:**
```typescript
// ✅ Bien - redirección declarativa
return router.createUrlTree(['/login']);

// ❌ Evitar - navegación imperativa
router.navigate(['/login']);
return false;
```

**✅ Usa canMatch para:**
- Feature flags
- A/B testing
- Carga condicional de rutas
- Decisiones antes del lazy-load

**✅ Usa canActivate para:**
- Comprobaciones de autenticación
- Comprobaciones de autorización
- Después de que la ruta ya esté cargada

**✅ Composición:**
```typescript
// Componer varias comprobaciones
export const adminGuard: CanActivateFn = (route, state) => {
  const auth = inject(AuthService);
  const role = inject(RoleService);

  return auth.isAuthenticated() && role.isAdmin();
};
```

---

## 19. Funcionalidades de Angular 19

**Fecha de Lanzamiento:** 19 de noviembre de 2024
**Estado:** Estable

> **Nota:** Angular 20+ ya se ha lanzado desde entonces. Angular 19 sigue siendo una referencia sólida para signals, APIs standalone y detección de cambios zoneless, pero consulta [angular.dev](https://angular.dev) para ver la versión estable actual antes de iniciar un nuevo proyecto.

Angular 19 introdujo mejoras significativas en la reactividad, el renderizado del lado del servidor y la experiencia del desarrollador.

**Recursos Oficiales:**
- [Anuncio de Angular 19](https://blog.angular.dev/meet-angular-v19-7b29dfd05b84)
- [Notas de Lanzamiento de Angular 19](https://github.com/angular/angular/releases/tag/19.0.0)
- [Novedades de Angular 19](https://angular.love/angular-19-whats-new/)

### Componentes Standalone por Defecto

Los componentes, directivas y pipes standalone son ahora el **comportamiento por defecto** al generar nuevos componentes.

```bash
# Angular 19 - standalone por defecto
ng generate component my-component
# Crea un componente standalone automáticamente

# Si necesitas un componente basado en módulos (legado)
ng generate component my-component --standalone=false
```

**Impacto:**
- Estructura de proyecto más simple
- Sin boilerplate de NgModule para los nuevos proyectos
- Mejor tree-shaking
- Más fácil de entender para principiantes

### linkedSignal - Signals Escribibles con Rastreo de Origen

**linkedSignal** crea un signal escribible que se actualiza automáticamente según un signal de origen y puede reiniciarse.

**Documentación Oficial:** [angular.dev/api/core/linkedSignal](https://angular.dev/api/core/linkedSignal)

**Problema que Resuelve:**
Antes de `linkedSignal`, crear un signal que fuera tanto dependiente de otro signal COMO escribible era complejo y propenso a errores.

**Uso Básico:**
```typescript
import { Component, signal, linkedSignal } from '@angular/core';

@Component({
  selector: 'app-user-profile',
  standalone: true,
  template: `
    <div>
      <p>Original: {{ source() }}</p>
      <p>Linked: {{ linked() }}</p>

      <button (click)="changeSource()">Change Source</button>
      <button (click)="changeLinked()">Change Linked</button>
      <button (click)="resetLinked()">Reset Linked</button>
    </div>
  `
})
export class UserProfileComponent {
  source = signal(10);

  // Linked signal: escribible + rastrea el origen
  linked = linkedSignal(() => this.source() * 2);

  changeSource() {
    this.source.set(20);  // linked se actualiza automáticamente a 40
  }

  changeLinked() {
    this.linked.set(100);  // Se puede escribir directamente
  }

  resetLinked() {
    // Reiniciar al valor calculado desde el origen
    this.linked.set(this.source() * 2);
  }
}
```

**Ejemplo Avanzado - Formulario con Reset:**
```typescript
@Component({
  selector: 'app-edit-form',
  standalone: true,
  imports: [FormsModule],
  template: `
    <form>
      <input [(ngModel)]="editableValue">

      <button type="button" (click)="save()">Save</button>
      <button type="button" (click)="reset()">Reset</button>

      <p *ngIf="hasChanges()">You have unsaved changes</p>
    </form>

    <p>Original: {{ originalValue() }}</p>
    <p>Current: {{ editableValue() }}</p>
  `
})
export class EditFormComponent {
  // Valor original del servidor/props
  originalValue = signal('Hello World');

  // Valor editable enlazado al original
  editableValue = linkedSignal(() => this.originalValue());

  // Comprobar si el valor cambió
  hasChanges = computed(() => {
    return this.editableValue() !== this.originalValue();
  });

  save() {
    // Guardar el valor editable como nuevo original
    this.originalValue.set(this.editableValue());
  }

  reset() {
    // Reiniciar al original (linkedSignal se auto-sincroniza)
    this.editableValue.set(this.originalValue());
  }
}
```

**Casos de Uso:**
- Campos de formulario que rastrean los valores originales
- Listas filtradas con capacidad de reset
- Estado de UI que puede revertir al valor por defecto
- Estado sincronizado entre componentes

### Resource API - Carga de Datos Asíncronos

**Resource API** proporciona una forma reactiva y basada en signals de cargar datos asíncronos (peticiones HTTP, etc.).

**Documentación Oficial:** [angular.dev/guide/signals/resource](https://angular.dev/guide/signals/resource)

**Funcionalidades Clave:**
- Carga de datos asíncronos basada en signals
- Estados de carga/error integrados
- Cancelación automática de peticiones
- Funciona sin problemas con los signals

**Ejemplo Básico:**
```typescript
import { Component, signal, resource } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { inject } from '@angular/core';

interface User {
  id: number;
  name: string;
  email: string;
}

@Component({
  selector: 'app-user-list',
  standalone: true,
  template: `
    <div>
      @if (users.isLoading()) {
        <p>Loading users...</p>
      }

      @if (users.error()) {
        <p>Error: {{ users.error()?.message }}</p>
      }

      @if (users.value()) {
        <ul>
          @for (user of users.value(); track user.id) {
            <li>{{ user.name }} - {{ user.email }}</li>
          }
        </ul>
      }

      <button (click)="reload()">Reload</button>
    </div>
  `
})
export class UserListComponent {
  http = inject(HttpClient);

  // Crear un resource para cargar los usuarios
  users = resource<User[], unknown>({
    loader: async () => {
      const response = await fetch('/api/users');
      return response.json();
    }
  });

  reload() {
    this.users.reload();
  }
}
```

**Resource con Dependencias:**
```typescript
@Component({
  selector: 'app-user-posts',
  standalone: true,
  template: `
    <input [(ngModel)]="userId" type="number" placeholder="User ID">

    @if (posts.isLoading()) {
      <p>Loading posts...</p>
    }

    @if (posts.value()) {
      <ul>
        @for (post of posts.value(); track post.id) {
          <li>{{ post.title }}</li>
        }
      </ul>
    }
  `
})
export class UserPostsComponent {
  http = inject(HttpClient);
  userId = signal(1);

  // Resource que se recarga cuando userId cambia
  posts = resource({
    request: () => ({ userId: this.userId() }),
    loader: async ({ request }) => {
      const response = await fetch(`/api/users/${request.userId}/posts`);
      return response.json();
    }
  });
}
```

**Estados del Resource:**
```typescript
const data = resource({
  loader: async () => fetchData()
});

// Comprobar estados
data.isLoading()   // boolean - ¿está la petición en progreso?
data.value()       // T | undefined - los datos cargados
data.error()       // Error | undefined - error si falló
data.hasValue()    // boolean - ¿se han cargado los datos?

// Acciones
data.reload()      // Disparar una recarga
data.set(value)    // Establecer el valor manualmente
```

**Comparación con RxJS:**

```typescript
// Antes (Observable de RxJS)
@Component({
  template: `
    <div *ngIf="users$ | async as users">
      <ul>
        <li *ngFor="let user of users">{{ user.name }}</li>
      </ul>
    </div>
  `
})
export class UserListComponentOld {
  http = inject(HttpClient);
  users$ = this.http.get<User[]>('/api/users');
}

// Después (Resource API)
@Component({
  template: `
    @if (users.value()) {
      <ul>
        @for (user of users.value(); track user.id) {
          <li>{{ user.name }}</li>
        }
      </ul>
    }
  `
})
export class UserListComponentNew {
  http = inject(HttpClient);
  users = resource({
    loader: async () => {
      const response = await fetch('/api/users');
      return response.json();
    }
  });
}
```

### Mejoras del Renderizado del Lado del Servidor

#### Event Replay Habilitado por Defecto

El **event replay** captura las interacciones del usuario (clics, entradas) que ocurren antes de que se complete la hidratación de JavaScript, y luego las reproduce tras la hidratación.

**Antes de Angular 19:**
- El usuario hace clic en un botón antes de la hidratación → Clic perdido ❌

**Angular 19+:**
- El usuario hace clic en un botón antes de la hidratación → Clic cacheado y reproducido ✅

**Configuración:**
```typescript
// app.config.ts
import { provideClientHydration, withEventReplay } from '@angular/platform-browser';

export const appConfig: ApplicationConfig = {
  providers: [
    provideClientHydration(withEventReplay())  // Habilitado por defecto en v19
  ]
};
```

#### Modos de Renderizado a Nivel de Ruta

Angular 19 introduce la interfaz **ServerRoute** para un control de grano fino sobre cómo se renderizan las rutas individuales.

**Estrategias de Renderizado:**
- **Server** - Renderizar en el servidor para cada petición (contenido dinámico)
- **Client** - Renderizar solo en el cliente (modo SPA)
- **Prerender** - Renderizar en tiempo de build (contenido estático)

**server.routes.ts:**
```typescript
import { ServerRoute } from '@angular/ssr';

export const serverRoutes: ServerRoute[] = [
  {
    path: '',
    renderMode: 'prerender'  // Página de inicio estática
  },
  {
    path: 'blog/:slug',
    renderMode: 'server'  // Entradas de blog dinámicas
  },
  {
    path: 'dashboard',
    renderMode: 'client'  // Dashboard solo de cliente
  },
  {
    path: 'about',
    renderMode: 'prerender'  // Página "acerca de" estática
  }
];
```

**Beneficios:**
- Mezclar SSR, CSR y SSG en una sola app
- Optimizar cada ruta individualmente
- Mejor rendimiento y SEO
- Costos de servidor reducidos para las páginas estáticas

### Selector de Hora de Angular Material

Una de las funcionalidades más solicitadas (más de 1.3k 👍 en GitHub) ¡ya está disponible!

**Uso:**
```typescript
import { Component } from '@angular/core';
import { MatTimepickerModule } from '@angular/material/timepicker';
import { MatInputModule } from '@angular/material/input';
import { MatFormFieldModule } from '@angular/material/form-field';
import { FormsModule } from '@angular/forms';

@Component({
  selector: 'app-appointment',
  standalone: true,
  imports: [
    MatTimepickerModule,
    MatInputModule,
    MatFormFieldModule,
    FormsModule
  ],
  template: `
    <mat-form-field>
      <mat-label>Select time</mat-label>
      <input matInput [matTimepicker]="picker" [(ngModel)]="selectedTime">
      <mat-timepicker-toggle matIconSuffix [for]="picker"></mat-timepicker-toggle>
      <mat-timepicker #picker></mat-timepicker>
    </mat-form-field>

    <p>Selected time: {{ selectedTime }}</p>
  `
})
export class AppointmentComponent {
  selectedTime: string = '';
}
```

### Hot Module Replacement (HMR)

**HMR** permite actualizaciones instantáneas de plantillas y estilos sin recargar la página completa durante el desarrollo.

**Beneficios:**
- Actualizaciones instantáneas de estilo/plantilla
- Preserva el estado de la aplicación
- Flujo de desarrollo más rápido
- No se necesita refrescar el navegador

**Habilitado por defecto** en el servidor de desarrollo de Angular 19.

### Mejoras de Calidad de Vida

#### 1. Diagnóstico de Funciones No Invocadas

Angular 19 marca los casos donde las funciones se usan en event bindings pero no se llaman (faltan los paréntesis).

```typescript
@Component({
  template: `
    <!-- ❌ Error: Función no invocada -->
    <button (click)="handleClick">Click me</button>

    <!-- ✅ Correcto -->
    <button (click)="handleClick()">Click me</button>
  `
})
export class ButtonComponent {
  handleClick() {
    console.log('Clicked!');
  }
}
```

#### 2. Advertencia de Importaciones Sin Usar

Angular CLI advierte sobre las importaciones sin usar en los componentes standalone.

```typescript
@Component({
  selector: 'app-example',
  standalone: true,
  imports: [
    CommonModule,     // ⚠️ Advertencia si no se usa
    FormsModule,      // ⚠️ Advertencia si no se usa
    HttpClientModule  // ✅ Usado
  ]
})
export class ExampleComponent {
  http = inject(HttpClient);  // Usa HttpClientModule
}
```

### Soporte de TypeScript 5.6

Angular 19 requiere **TypeScript 5.6+** para las nuevas funcionalidades y mejoras de rendimiento.

**Funcionalidades Clave de TypeScript 5.6:**
- Inferencia de tipos mejorada
- Mejores mensajes de error
- Optimizaciones de rendimiento
- Nuevas funcionalidades de sintaxis

### Migración a Angular 19

```bash
# Actualizar a Angular 19
ng update @angular/core@19 @angular/cli@19

# Actualizar Angular Material (si se usa)
ng update @angular/material@19
```

**Cambios que Rompen Compatibilidad:**
- Los componentes standalone ahora son por defecto (se puede deshabilitar con `--standalone=false`)
- Se requiere TypeScript 5.6+
- Algunas APIs obsoletas eliminadas

---

## 20. Funcionalidades de Angular 20

**Lanzado:** Mayo de 2025

> **Nota:** Esta sección se escribió originalmente mientras Angular 20 estaba en preview. Angular 20 (y versiones posteriores) ya son estables. Los detalles a continuación reflejan el conjunto de funcionalidades que se lanzó, pero confirma siempre los detalles con la documentación actual, ya que las APIs pueden haber evolucionado en versiones minor/major posteriores.

**Recursos Oficiales:**
- [Angular Blog](https://blog.angular.dev) - Anuncios oficiales
- [Angular Docs](https://angular.dev) - Referencia actual y versionada
- [Guía de Actualización de Angular](https://angular.dev/update-guide) - Pasos de migración de versión a versión

### API de Signals Estable

La API de Signals, introducida experimentalmente en Angular 16, ahora es **totalmente estable** en Angular 20.

**APIs Estables:**
- `signal()` - Crear signals escribibles
- `computed()` - Signals derivados
- `effect()` - Efectos secundarios de los cambios de signals
- `linkedSignal()` - Signals escribibles con rastreo de origen
- `toSignal()` - Convertir Observable a Signal
- `toObservable()` - Convertir Signal a Observable

**No más advertencias "experimentales":**
```typescript
import { Component, signal, computed, effect } from '@angular/core';

@Component({
  selector: 'app-counter',
  standalone: true,
  template: `
    <h2>Count: {{ count() }}</h2>
    <h3>Double: {{ double() }}</h3>
    <button (click)="increment()">+1</button>
  `
})
export class CounterComponent {
  // Todas las APIs estables
  count = signal(0);
  double = computed(() => this.count() * 2);

  constructor() {
    effect(() => {
      console.log('Count changed:', this.count());
    });
  }

  increment() {
    this.count.update(n => n + 1);
  }
}
```

### Detección de Cambios Zoneless (Opt-in Estable)

Angular 20 hace que la detección de cambios zoneless sea **estable** pero aún opt-in.

**Beneficios:**
- 📦 **Bundles más pequeños** - Reducción de ~50KB (eliminación de Zone.js)
- ⚡ **Detección de cambios más rápida** - Solo actualizaciones quirúrgicas
- 🎯 **Mejor depuración** - Reactividad predecible

**Habilitar Zoneless:**
```typescript
// app.config.ts
import { ApplicationConfig } from '@angular/core';
import { provideZonelessChangeDetection } from '@angular/core';

export const appConfig: ApplicationConfig = {
  providers: [
    provideZonelessChangeDetection()  // ¡Estable en Angular 20!
  ]
};
```

**Eliminar Zone.js de angular.json:**
```json
{
  "architect": {
    "build": {
      "options": {
        "polyfills": []  // Eliminar "zone.js"
      }
    }
  }
}
```

**Requisitos para Zoneless:**
- ✅ Todos los componentes usan OnPush o signals
- ✅ Ninguna librería depende de Zone.js
- ✅ Usa signals para el estado reactivo

**Documentación Oficial:** [angular.dev/guide/zoneless](https://angular.dev/guide/zoneless)

### Integración de Material Design 3

Los componentes de Angular Material actualizados para cumplir con las especificaciones de **Material Design 3**.

**Cambios:**
- Sistema de elevación actualizado
- Nuevos roles de color y variantes tonales
- Estilizado de componentes refinado
- Mejor soporte de modo oscuro

**Ejemplo:**
```typescript
import { Component } from '@angular/core';
import { MatButtonModule } from '@angular/material/button';
import { MatCardModule } from '@angular/material/card';

@Component({
  selector: 'app-card-example',
  standalone: true,
  imports: [MatButtonModule, MatCardModule],
  template: `
    <mat-card appearance="outlined">
      <mat-card-header>
        <mat-card-title>Material Design 3</mat-card-title>
      </mat-card-header>
      <mat-card-content>
        <p>Updated styling with MD3 specifications</p>
      </mat-card-content>
      <mat-card-actions>
        <button mat-button>Action</button>
        <button mat-raised-button color="primary">Primary</button>
      </mat-card-actions>
    </mat-card>
  `
})
export class CardExampleComponent {}
```

### Formularios Basados en Signals (Developer Preview)

Angular 20 introduce los **formularios basados en signals** como developer preview.

**Formularios Reactivos Tradicionales:**
```typescript
// Forma antigua - usando RxJS
@Component({
  template: `
    <form [formGroup]="form" (ngSubmit)="onSubmit()">
      <input formControlName="username">
      <input formControlName="email">
      <button type="submit">Submit</button>
    </form>
  `
})
export class OldFormComponent {
  form = new FormGroup({
    username: new FormControl(''),
    email: new FormControl('')
  });

  onSubmit() {
    console.log(this.form.value);
  }
}
```

**Formularios Basados en Signals:**
```typescript
// Forma nueva - usando signals (preview)
import { Component, signal, computed } from '@angular/core';
import { FormControl, FormGroup } from '@angular/forms';

@Component({
  template: `
    <form (submit)="onSubmit()">
      <input [value]="username()" (input)="username.set($event.target.value)">
      <input [value]="email()" (input)="email.set($event.target.value)">

      <button type="submit" [disabled]="!isValid()">Submit</button>

      <p *ngIf="isValid()">Form is valid!</p>
    </form>
  `
})
export class SignalFormComponent {
  username = signal('');
  email = signal('');

  isValid = computed(() => {
    return this.username().length > 0 && this.email().includes('@');
  });

  onSubmit() {
    console.log({
      username: this.username(),
      email: this.email()
    });
  }
}
```

**Nota:** Los formularios basados en signals aún están en **developer preview** en Angular 20. El lanzamiento estable completo se espera en Angular 21.

### Reactividad Mejorada

Angular 20 mejora la reactividad de los signals con un mejor rastreo de dependencias y limpieza de efectos.

**Rastreo de Dependencias Mejorado:**
```typescript
@Component({
  selector: 'app-example',
  standalone: true,
  template: `
    <p>{{ message() }}</p>
    <button (click)="toggle()">Toggle</button>
  `
})
export class ExampleComponent {
  show = signal(true);
  data = signal('Hello');

  // Angular 20: Mejor rastreo de dependencias condicionales
  message = computed(() => {
    if (this.show()) {
      return this.data();  // Solo rastrea 'data' cuando 'show' es true
    }
    return 'Hidden';
  });

  toggle() {
    this.show.update(v => !v);
  }
}
```

**Limpieza de Efectos:**
```typescript
@Component({})
export class CleanupExampleComponent {
  count = signal(0);

  constructor() {
    effect((onCleanup) => {
      const interval = setInterval(() => {
        console.log('Count:', this.count());
      }, 1000);

      // Limpieza cuando el efecto se re-ejecuta o el componente se destruye
      onCleanup(() => {
        clearInterval(interval);
      });
    });
  }
}
```

### Mejoras de Rendimiento

**Rendimiento del Build:**
- Builds de desarrollo más rápidos (optimizaciones de esbuild)
- Builds de producción mejorados (mejor tree-shaking)
- HMR (Hot Module Replacement) más rápido

**Rendimiento en Runtime:**
- Detección de cambios optimizada con signals
- Tamaños de bundle más pequeños
- Mejor rendimiento de SSR

**Benchmarks:**
```
Tiempo de Build de Desarrollo:
Angular 19: 2.5s
Angular 20: 1.8s (-28%)

Tamaño del Bundle de Producción:
Angular 19: 142KB
Angular 20: 128KB (-10%)

Detección de Cambios (con signals):
Angular 19: 3.2ms
Angular 20: 2.1ms (-34%)
```

### Requisitos de Node.js

**Versión Mínima:** Node.js 20.11.1+

**Por Qué el Cambio:**
- Node.js 18 llegó a su fin de vida (End-of-Life) el 27 de marzo de 2025
- Mejor rendimiento con Node.js 20+
- Nuevas funcionalidades de JavaScript disponibles

**Comprobar Tu Versión:**
```bash
node --version
# Debería ser >= v20.11.1
```

### Migración a Angular 20

```bash
# Actualizar a Angular 20
ng update @angular/core@20 @angular/cli@20

# Actualizar Angular Material (si se usa)
ng update @angular/material@20

# Actualizar Node.js si es necesario
nvm install 20.11.1
nvm use 20.11.1
```

**Cambios que Rompen Compatibilidad:**
- Se requiere Node.js 20.11.1+
- Algunas APIs obsoletas eliminadas
- Se requiere TypeScript 5.6+ (desde Angular 19)

---

## 21. Angular 20.2 y Más Allá

> **Nota:** Algunos elementos a continuación se escribieron mientras estas funcionalidades estaban en la hoja de ruta; varias ya se han lanzado. Confirma siempre el estado actual y la forma de la API con [angular.dev](https://angular.dev) y la [Hoja de Ruta de Angular](https://angular.dev/roadmap).

### API de Animaciones Nativa

Angular 20.2 introduce **animate.enter** y **animate.leave** como funcionalidades de animación nativas construidas directamente en el compilador.

**Documentación Oficial:** [angular.dev/guide/animations](https://angular.dev/guide/animations)

### ¿Por Qué Animaciones Nativas?

**Problemas con @angular/animations:**
- Bundle de JavaScript grande (~50KB)
- API compleja
- Sobrecarga de rendimiento
- No aceleradas por hardware

**Beneficios de las Animaciones CSS Nativas:**
- ⚡ Aceleración por hardware
- 📦 Cero sobrecarga de JavaScript
- 🎯 API más simple
- 🚀 Mejor rendimiento

### animate.enter - Animaciones de Entrada

**Uso Básico:**
```typescript
import { Component, signal } from '@angular/core';

@Component({
  selector: 'app-fade-in',
  standalone: true,
  template: `
    <button (click)="show.set(true)">Show Message</button>

    @if (show()) {
      <div animate.enter="fadeIn 300ms ease-in">
        Welcome to Angular 20.2!
      </div>
    }
  `,
  styles: [`
    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(-20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
  `]
})
export class FadeInComponent {
  show = signal(false);
}
```

**Cómo Funciona:**
1. El elemento entra en el DOM
2. Angular aplica la animación CSS
3. La animación se ejecuta usando las capacidades nativas del navegador
4. Sin sobrecarga de JavaScript

### animate.leave - Animaciones de Salida

```typescript
@Component({
  selector: 'app-slide-out',
  standalone: true,
  template: `
    <button (click)="items.update(arr => arr.slice(0, -1))">
      Remove Last Item
    </button>

    <ul>
      @for (item of items(); track item.id) {
        <li animate.leave="slideOut 250ms ease-out">
          {{ item.name }}
        </li>
      }
    </ul>
  `,
  styles: [`
    @keyframes slideOut {
      from {
        opacity: 1;
        transform: translateX(0);
      }
      to {
        opacity: 0;
        transform: translateX(100%);
      }
    }
  `]
})
export class SlideOutComponent {
  items = signal([
    { id: 1, name: 'Item 1' },
    { id: 2, name: 'Item 2' },
    { id: 3, name: 'Item 3' }
  ]);
}
```

### Animaciones de Entrada/Salida Combinadas

```typescript
@Component({
  selector: 'app-modal',
  standalone: true,
  template: `
    <button (click)="showModal.set(true)">Open Modal</button>

    @if (showModal()) {
      <div
        class="modal-backdrop"
        animate.enter="fadeIn 200ms"
        animate.leave="fadeOut 200ms"
        (click)="showModal.set(false)">

        <div
          class="modal-content"
          animate.enter="slideDown 300ms ease-out"
          animate.leave="slideUp 300ms ease-in"
          (click)="$event.stopPropagation()">

          <h2>Modal Title</h2>
          <p>Modal content here...</p>
          <button (click)="showModal.set(false)">Close</button>
        </div>
      </div>
    }
  `,
  styles: [`
    .modal-backdrop {
      position: fixed;
      inset: 0;
      background: rgba(0, 0, 0, 0.5);
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .modal-content {
      background: white;
      padding: 2rem;
      border-radius: 8px;
      max-width: 500px;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @keyframes fadeOut {
      from { opacity: 1; }
      to { opacity: 0; }
    }

    @keyframes slideDown {
      from {
        opacity: 0;
        transform: translateY(-50px) scale(0.9);
      }
      to {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
    }

    @keyframes slideUp {
      from {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
      to {
        opacity: 0;
        transform: translateY(-50px) scale(0.9);
      }
    }
  `]
})
export class ModalComponent {
  showModal = signal(false);
}
```

### Animaciones en Host Binding

```typescript
@Component({
  selector: 'app-animated-card',
  standalone: true,
  host: {
    'animate.enter': 'cardEnter 400ms ease-out'
  },
  template: `
    <div class="card">
      <h3>{{ title }}</h3>
      <p>{{ description }}</p>
    </div>
  `,
  styles: [`
    @keyframes cardEnter {
      from {
        opacity: 0;
        transform: scale(0.8) rotate(-5deg);
      }
      to {
        opacity: 1;
        transform: scale(1) rotate(0deg);
      }
    }

    .card {
      padding: 1rem;
      border: 1px solid #ccc;
      border-radius: 8px;
    }
  `]
})
export class AnimatedCardComponent {
  @Input() title = '';
  @Input() description = '';
}
```

### Librerías de Animación de Terceros

También puedes usar funciones para integrar librerías de animación de terceros:

```typescript
import { Component } from '@angular/core';
import { animate } from 'motion'; // Ejemplo: librería Motion One

@Component({
  selector: 'app-advanced-animation',
  standalone: true,
  host: {
    'animate.enter': animateEnter,
    'animate.leave': animateLeave
  },
  template: `
    <div class="content">Advanced animations!</div>
  `
})
export class AdvancedAnimationComponent {}

function animateEnter(element: HTMLElement) {
  animate(element,
    { opacity: [0, 1], transform: ['scale(0.5)', 'scale(1)'] },
    { duration: 0.5, easing: 'spring' }
  );
}

function animateLeave(element: HTMLElement) {
  animate(element,
    { opacity: 0, transform: 'scale(0.5)' },
    { duration: 0.3 }
  );
}
```

### Migrando desde @angular/animations

**Antes (API Antigua):**
```typescript
import { Component } from '@angular/core';
import { trigger, transition, style, animate } from '@angular/animations';

@Component({
  selector: 'app-old-animation',
  template: `
    <div *ngIf="show" @fadeIn>Content</div>
  `,
  animations: [
    trigger('fadeIn', [
      transition(':enter', [
        style({ opacity: 0 }),
        animate('300ms', style({ opacity: 1 }))
      ]),
      transition(':leave', [
        animate('300ms', style({ opacity: 0 }))
      ])
    ])
  ]
})
export class OldAnimationComponent {
  show = true;
}
```

**Después (API Nativa):**
```typescript
import { Component, signal } from '@angular/core';

@Component({
  selector: 'app-new-animation',
  standalone: true,
  template: `
    @if (show()) {
      <div
        animate.enter="fadeIn 300ms"
        animate.leave="fadeOut 300ms">
        Content
      </div>
    }
  `,
  styles: [`
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @keyframes fadeOut {
      from { opacity: 1; }
      to { opacity: 0; }
    }
  `]
})
export class NewAnimationComponent {
  show = signal(true);
}
```

**Beneficios de la Migración:**
- Bundle ~50KB más pequeño (sin @angular/animations)
- Mejor rendimiento (aceleración por hardware)
- API más simple e intuitiva
- Animaciones CSS estándar

### Obsolescencia de @angular/animations

**Cronología:**
- **Angular 20.2:** Animaciones nativas introducidas, @angular/animations obsoleto
- **Angular 21+:** @angular/animations aún soportado pero no recomendado
- **Angular 22+:** Probable eliminación de @angular/animations

**Comando de Migración:**
```bash
ng generate @angular/core:migrate-animations
```

Esto hará:
- Convertir los triggers de animación a CSS nativo
- Actualizar las plantillas para usar animate.enter/animate.leave
- Eliminar las importaciones de @angular/animations

### Zoneless Oficialmente Estable

En Angular 20.2, la API zoneless pasó de "opt-in estable" a **totalmente estable**.

**Novedades:**
```typescript
// Angular 20.2+
import { provideZonelessChangeDetection } from '@angular/core';

export const appConfig: ApplicationConfig = {
  providers: [
    provideZonelessChangeDetection()  // ¡Totalmente estable!
  ]
};
```

**Preview de Angular 21:**
En Angular 21 (esperado a finales de 2025), zoneless se convertirá en el **valor por defecto** para todas las aplicaciones nuevas.

### Resumen de Buenas Prácticas

---

## Resumen de Buenas Prácticas (Angular 19 - Enero de 2025)

### Diseño de Componentes
- ✅ **Usa componentes standalone** (por defecto en Angular 19)
- ✅ Implementa el patrón contenedor/presentacional
- ✅ Detección de cambios OnPush por defecto
- ✅ Mantén los componentes pequeños y enfocados (Principio de Responsabilidad Única)
- ✅ Usa la nueva sintaxis de control de flujo (@if, @for, @switch)

### Gestión de Estado
- ✅ **Usa signals para el estado simple** (estable en Angular 19)
- ✅ Usa RxJS para las operaciones asíncronas (HTTP, WebSockets, temporizadores)
- ✅ Combina signals y RxJS con `toSignal()` y `toObservable()`
- ✅ Usa `linkedSignal()` para signals escribibles dependientes
- ✅ Usa Resource API para la carga de datos asíncronos (developer preview)

### Rendimiento
- ✅ Usa lazy loading para las rutas (`loadComponent`, `loadChildren`)
- ✅ Implementa la estrategia de detección de cambios OnPush
- ✅ Usa `@defer` para la carga perezosa de componentes
- ✅ Usa `track` en los bucles @for (obligatorio en la nueva sintaxis)
- ✅ Habilita la hidratación incremental para SSR
- ⚠️ Detección de cambios zoneless (developer preview - espera a que sea estable)

### TypeScript
- ✅ Habilita el modo estricto en tsconfig.json
- ✅ Usa interfaces para los contratos
- ✅ Evita `any`, prefiere `unknown` o tipos apropiados
- ✅ Aprovecha la inferencia de tipos cuando sea posible
- ✅ Usa TypeScript 5.6+ (requerido para Angular 19)

### Arquitectura
- ✅ Estructura de carpetas basada en funcionalidades
- ✅ Componentes compartidos en /shared
- ✅ Servicios core en /core
- ✅ Usa alias de rutas (@app/, @environments/)
- ✅ Usa interceptores y guards funcionales (recomendados sobre los basados en clases)

### Específico de Angular 19
- ✅ Los componentes standalone ahora son el **valor por defecto** (no se necesita el flag --standalone)
- ✅ La API de Signals es **estable** - seguro de usar en producción
- ✅ Usa la nueva sintaxis de control de flujo en lugar de las directivas estructurales
- ✅ Habilita el event replay para una mejor UX de SSR
- ✅ Usa modos de renderizado a nivel de ruta para SSR/CSR/SSG mixtos

---

## Referencia Rápida de Comandos

### Comandos Esenciales de Angular CLI

```bash
# Instalación
npm install -g @angular/cli
ng version

# Creación de Proyecto (Angular 19+)
ng new my-app
# Nota: --standalone ahora es por defecto en Angular 19, no hace falta especificarlo
ng new my-app --routing --style=scss

# Desarrollo
ng serve
ng serve --open
ng serve --port 4200

# Generación de Componentes
ng g c component-name
ng g c component-name --inline-template --inline-style --skip-tests
ng g c component-name --dry-run

# Generación de Servicios
ng g s service-name

# Generación de Módulos (legado)
ng g m module-name

# Generación de Directivas
ng g d directive-name

# Generación de Pipes
ng g pipe pipe-name

# Build
ng build
ng build --configuration production

# Testing
ng test
ng test --code-coverage

# Linting
ng lint
```

### Patrones Comunes

**Creación de Componentes:**
```bash
# Componente completo con carpeta
ng g c user

# Todo en línea
ng g c games -t -s --skip-tests

# En una carpeta específica
ng g c components/header
```

**Ver Ayuda:**
```bash
ng help
ng generate --help
ng g c --help
```

---

## Recursos

**Documentación Oficial:**
- [angular.dev](https://angular.dev) - **Nueva documentación interactiva** (muy recomendada)
- [angular.io](https://angular.io) - Documentación legada
- [Angular Blog](https://blog.angular.dev)
- [Angular GitHub](https://github.com/angular/angular)
- [Angular Roadmap](https://angular.dev/roadmap)

**Tutoriales:**
- [Tutorial Oficial de Angular](https://angular.dev/tutorials)

**Comunidad:**
- [Angular Discord](https://discord.gg/angular)
- [Subreddit de Angular](https://reddit.com/r/angular)
- [Twitter de Angular](https://twitter.com/angular)

**Herramientas:**
- [Angular CLI](https://angular.io/cli)
- [Angular DevTools](https://angular.io/guide/devtools) - Extensión de Chrome
- [Bun](https://bun.sh) - Gestor de paquetes rápido
- [Stackblitz](https://stackblitz.com) - IDE de Angular en línea

**Extensiones de VSCode:**
- **Angular Language Service** (Oficial) - ¡Imprescindible!
- Angular Snippets
- Angular Schematics
- Prettier - Formateador de código

**Práctica:**
- [Angular Challenges](https://github.com/angular/angular/tree/main/aio/content/examples)
- [Ejemplos de StackBlitz](https://stackblitz.com/@angular/stacks)

---

**Enfoque:**
- **Fundamento Teórico** - Entender el "porqué" detrás del diseño de Angular
- **Aplicación Práctica** - Ejemplos prácticos y patrones del mundo real
- **Funcionalidades Modernas** - Nuevo control de flujo, @defer, signals
- **Listo para Producción** - Buenas prácticas, rendimiento, optimización

---

**Última Actualización:** 2026-08-31
**Versión de Angular:** 19.x (estable actual)
**Mantenido por:** Marco Figueroa
