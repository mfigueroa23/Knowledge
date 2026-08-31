# NestJS - Framework de Backend para Node.js

## 📌 Metadatos del Documento

**Versión de NestJS Cubierta:** v10+ (última estable)
**Node.js Requerido:** v20.0.0 o superior (v22+ recomendado)
**Última Actualización:** 2026-08-31
**Nivel de Habilidad:** Principiante a Intermedio
**Requisitos Previos:**
- Conocimientos básicos de JavaScript/TypeScript
- Comprensión de los fundamentos de Node.js
- Familiaridad con los conceptos de API REST
- Competencia básica en línea de comandos

---

## 🎯 Cuándo Usar Este Conocimiento

Usa esta guía cuando necesites:

✅ **Construir un nuevo proyecto NestJS desde cero**
- Consultar los pasos de instalación y la estructura del proyecto
- Configurar el entorno de desarrollo correctamente

✅ **Implementar los patrones fundamentales de NestJS**
- Crear módulos, controladores y servicios
- Implementar la inyección de dependencias
- Añadir validación con DTOs y pipes

✅ **Trabajar con bases de datos**
- Integrar PostgreSQL/MySQL con TypeORM
- Usar MongoDB con Mongoose
- Configurar el ORM Prisma (ver api.devsonic.cl para un ejemplo de producción)

✅ **Añadir funcionalidades de API**
- Manejar métodos HTTP (GET, POST, PUT, PATCH, DELETE)
- Implementar guards para autenticación/autorización
- Crear middlewares para el procesamiento de peticiones
- Generar documentación automática de la API con Swagger

✅ **Desplegar a producción**
- Configurar CORS para la integración con el frontend
- Preparar para el despliegue (Heroku, Railway, Render, Docker)
- Configurar las variables de entorno correctamente

✅ **Referencia rápida durante el desarrollo**
- Consultar decoradores y su uso
- Encontrar patrones de manejo de errores
- Comprobar reglas de validación y pipes
- Revisar las buenas prácticas

**Consejos de Navegación Rápida:**
- Salta a secciones específicas usando la Tabla de Contenidos
- Cada sección incluye ejemplos prácticos y fragmentos de código
- Las buenas prácticas están marcadas con ✅
- Los errores comunes están marcados con ❌
- Las advertencias están marcadas con ⚠️

---

## 📋 Tabla de Contenidos

1. [Introducción](#1-introducción)
2. [Instalación](#2-instalación)
3. [Estructura del Proyecto](#3-estructura-del-proyecto)
4. [Servicio-Módulo-Controlador](#4-servicio-módulo-controlador)
5. [Módulos en NestJS](#5-módulos-en-nestjs)
6. [Servicios](#6-servicios)
7. [Response](#7-response)
8. [Validaciones](#8-validaciones)
9. [Errores de Estado HTTP](#9-errores-de-estado-http)
10. [Pipes](#10-pipes)
11. [Guards](#11-guards)
12. [Middlewares](#12-middlewares)
13. [Resources](#13-resources)
14. [Base de Datos](#14-base-de-datos)
15. [Swagger](#15-swagger)
16. [CORS](#16-cors)
17. [Despliegue](#17-despliegue)

---

## Descripción General

NestJS es uno de los frameworks de Node.js más populares que se usan actualmente para crear aplicaciones web de backend profesionales y escalables. Este framework tiene una arquitectura limpia para escribir código y crear APIs REST, APIs GraphQL, WebSockets y microservicios, todo usando la sintaxis y los paquetes de TypeScript.

### ¿Qué es NestJS?

- Framework de código abierto para crear aplicaciones de backend escalables en Node.js
- Construido con TypeScript
- Combina programación orientada a objetos, funcional y reactiva
- Construido sobre Express (pero también soporta Fastify)
- Inspirado en Angular para la estructura y organización del código
- Usa inyección de dependencias y módulos

### Características Principales

- ✅ Arquitectura modular y escalable
- ✅ Soporte nativo de TypeScript
- ✅ Decoradores para una sintaxis limpia
- ✅ Integración con TypeORM, Mongoose, Sequelize
- ✅ Validación de datos integrada
- ✅ Documentación automática con Swagger
- ✅ Soporte para WebSockets, GraphQL y Microservicios

---

## 1. Introducción

NestJS es un framework muy versátil usado en muchos proyectos de producción que permite un flujo de desarrollo rápido para crear aplicaciones de backend. Con NestJS puedes:

- Conectar bases de datos (SQL y NoSQL)
- Crear aplicaciones en tiempo real con WebSockets
- Desarrollar APIs GraphQL
- Implementar microservicios
- Escalar desde proyectos pequeños hasta aplicaciones empresariales

### Conceptos Clave

**Paradigmas de Programación:**
- Programación Orientada a Objetos (OOP)
- Programación Funcional
- Programación Reactiva

**Tecnologías Relacionadas:**
- TypeScript como lenguaje principal
- Express o Fastify como motor HTTP subyacente
- Módulos del ecosistema npm

### Herramientas Requeridas

**Software Necesario:**
1. **Node.js** - Versión 18.0.0 o superior (**se recomienda v20 LTS o v22 LTS** para mejor compatibilidad)
2. **Visual Studio Code** (recomendado) o cualquier editor de código moderno
3. **npm** (v9+), **yarn** (v1.22+) o **pnpm** (v8+) - Gestor de paquetes
4. **Git** - Para el control de versiones y clonar repositorios

**Extensiones de VS Code Recomendadas:**

1. **Material Icon Theme** (PKief.material-icon-theme)
   - Proporciona iconos visuales para los archivos de NestJS

2. **Thunder Client**
   - Cliente HTTP integrado para probar endpoints
   - Alternativa a Postman dentro de VS Code

3. **JSON Viewer** (extensión de navegador)
   - Para Chrome, Brave, Opera, Edge
   - Formatea las respuestas JSON en el navegador

### Verificar la Instalación de Node.js

```bash
# Comprobar la versión de Node.js
node --version

# Debería mostrar v18.x.x o superior (v20.x.x o v22.x.x recomendado)

# Comprobar la versión de npm
npm --version

# Debería mostrar v9.x.x o superior
```

### Conocimientos Previos Recomendados

- Conocimientos básicos de JavaScript/TypeScript
- Comprensión de Node.js
- Familiaridad con las APIs REST
- Conceptos de HTTP (GET, POST, PUT, DELETE)

---

## 2. Instalación

### Instalar la CLI de NestJS Globalmente

La CLI de NestJS es una herramienta de línea de comandos que facilita la creación y gestión de proyectos.

```bash
# Instalar la CLI de NestJS globalmente (última versión)
npm install -g @nestjs/cli

# O con una versión específica (por estabilidad)
npm install -g @nestjs/cli@10

# Verificar la instalación
nest --version
# O también
nest -v

# Salida esperada: 10.x.x o superior

# Alternativa: Usar sin instalación global (npx)
npx @nestjs/cli new my-project
```

### Comandos Principales de la CLI

```bash
# Ver todos los comandos disponibles
nest

# Comandos principales:
# - new       : Crear un nuevo proyecto
# - generate  : Generar código (módulos, controladores, etc.)
# - build     : Compilar la aplicación
# - start     : Iniciar la aplicación
# - info      : Ver información del proyecto
# - add       : Añadir librerías
```

### Crear un Nuevo Proyecto

```bash
# Navegar al directorio deseado
cd Desktop

# Crear un nuevo proyecto
nest new my-first-app

# Seleccionar el gestor de paquetes (npm, yarn, pnpm)
# Seleccionar: npm
```

**Qué hace el comando:**
1. Crea una carpeta con el nombre del proyecto
2. Genera la estructura base del proyecto
3. Instala todas las dependencias necesarias
4. Configura TypeScript, ESLint y Prettier

### Estructura de Archivos Generada

```
my-first-app/
├── node_modules/
├── src/
│   ├── app.controller.ts
│   ├── app.controller.spec.ts
│   ├── app.module.ts
│   ├── app.service.ts
│   └── main.ts
├── test/
├── .eslintrc.js
├── .gitignore
├── .prettierrc
├── nest-cli.json
├── package.json
├── tsconfig.json
└── tsconfig.build.json
```

### Abrir el Proyecto

```bash
# Abrir con Visual Studio Code
code my-first-app

# O navegar al directorio
cd my-first-app
```

### Comandos de Ejecución

**Modo Desarrollo (con hot-reload):**

```bash
# Iniciar en modo desarrollo
npm run start:dev

# El servidor arranca en http://localhost:3000
```

**Modo Producción:**

```bash
# Compilar el proyecto
npm run build

# Iniciar en producción
npm start
```

**Otros Comandos Útiles:**

```bash
# Ejecutar el linter (ESLint)
npm run lint

# Ejecutar los tests unitarios
npm run test

# Ejecutar los tests e2e
npm run test:e2e
```

### Probar la Aplicación

1. **Iniciar el servidor:**
   ```bash
   npm run start:dev
   ```

2. **Abrir el navegador:**
   ```
   http://localhost:3000
   ```

3. **Respuesta esperada:**
   ```
   Hello World!
   ```

### Modificar el Mensaje de Bienvenida

**Archivo:** `src/app.service.ts`

```typescript
import { Injectable } from '@nestjs/common';

@Injectable()
export class AppService {
  getHello(): string {
    return 'Hello World'; // Cambiar el mensaje
  }
}
```

Al guardar, el servidor se recarga automáticamente y el cambio se refleja al refrescar el navegador.

### Conceptos Importantes

**Hot Reload:**
- En modo desarrollo (`start:dev`), los cambios se reflejan automáticamente
- No hay que reiniciar el servidor manualmente

**Build vs Start:**
- `npm run build` - Compila TypeScript a JavaScript (carpeta `dist/`)
- `npm start` - Ejecuta el código compilado (producción)
- `npm run start:dev` - Ejecuta con modo watch (desarrollo)

### Buenas Prácticas

✅ **Usa `start:dev` durante el desarrollo** - Recarga automática
✅ **Usa `build` y `start` en producción** - Código optimizado
✅ **Ejecuta `lint` antes de los commits** - Mantén el código limpio

---

## 3. Estructura del Proyecto

### Carpetas Principales

#### `dist/`
- Contiene el código compilado de TypeScript a JavaScript
- Generado por `npm run build`
- Este es el código que se ejecuta en producción
- **No debe editarse manualmente**

#### `node_modules/`
- Contiene todas las dependencias del proyecto
- Gestionado automáticamente por npm
- **No se sube al repositorio** (incluido en `.gitignore`)

#### `src/`
- **La carpeta más importante** - Todo nuestro código va aquí
- Contiene la lógica de la aplicación
- Rutas, controladores, servicios, módulos

#### `test/`
- Tests de extremo a extremo (e2e)
- Tests de integración completa de la aplicación

### Archivos de Configuración

#### `.eslintrc.js`
- Configuración de ESLint
- Define reglas de calidad de código
- Detecta errores y malas prácticas

**Configuración personalizada para Windows:**

```javascript
module.exports = {
  parser: '@typescript-eslint/parser',
  parserOptions: {
    project: 'tsconfig.json',
    tsconfigRootDir: __dirname,
    sourceType: 'module',
  },
  plugins: ['@typescript-eslint/eslint-plugin'],
  extends: [
    'plugin:@typescript-eslint/recommended',
    'plugin:prettier/recommended',
  ],
  root: true,
  env: {
    node: true,
    jest: true,
  },
  ignorePatterns: ['.eslintrc.js'],
  rules: {
    '@typescript-eslint/interface-name-prefix': 'off',
    '@typescript-eslint/explicit-function-return-type': 'off',
    '@typescript-eslint/explicit-module-boundary-types': 'off',
    '@typescript-eslint/no-explicit-any': 'off',
    'prettier/prettier': [
      'error',
      {
        endOfLine: 'auto', // Añade esta configuración para Windows
      },
    ],
  },
};
```

#### `.gitignore`
- Archivos y carpetas que no se suben a Git
- Variables de entorno (`.env`)
- Secretos y claves privadas
- `node_modules/`, `dist/`

#### `.prettierrc`
- Configuración de Prettier (formateador de código)
- Define reglas de formato (indentación, comillas, etc.)

#### `nest-cli.json`
- Configuración interna de la CLI de NestJS
- Rara vez se modifica

#### `package.json`
- Dependencias del proyecto
- Scripts de npm
- Metadatos del proyecto

#### `package-lock.json`
- Versiones exactas de las dependencias
- Garantiza instalaciones consistentes

#### `tsconfig.json`
- Configuración base de TypeScript
- Reglas del compilador

#### `tsconfig.build.json`
- Configuración de TypeScript para producción
- Extiende `tsconfig.json`

### Archivos en `src/`

#### `main.ts`
- **Punto de entrada de la aplicación**
- Inicia el servidor de NestJS
- Configura el puerto y otras opciones globales

```typescript
import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(3000);
}
bootstrap();
```

#### `app.module.ts`
- **Módulo raíz** de la aplicación
- Importa todos los demás módulos
- Punto central de configuración

#### `app.controller.ts`
- Controlador de ejemplo
- Maneja las rutas HTTP

#### `app.service.ts`
- Servicio de ejemplo
- Contiene la lógica de negocio

#### `app.controller.spec.ts`
- Tests unitarios del controlador
- Generado automáticamente

### Personalizar los Iconos en VS Code

Para que los archivos de NestJS muestren los iconos correctos:

1. **Presiona F1** en VS Code
2. Busca: `Open Workspace Settings (JSON)`
3. Añade la siguiente configuración:

```json
{
  "material-icon-theme.activeIconPack": "nest"
}
```

Esto cambiará los iconos de Angular (por defecto) a los iconos de NestJS.

### Arquitectura de una Aplicación NestJS

```
┌─────────────────────────────────────────┐
│         Aplicación NestJS               │
│  ┌───────────────────────────────────┐  │
│  │       AppModule (Raíz)            │  │
│  │  ┌─────────────────────────────┐  │  │
│  │  │   AuthModule                │  │  │
│  │  │  - AuthController           │  │  │
│  │  │  - AuthService              │  │  │
│  │  └─────────────────────────────┘  │  │
│  │  ┌─────────────────────────────┐  │  │
│  │  │   UsersModule               │  │  │
│  │  │  - UsersController          │  │  │
│  │  │  - UsersService             │  │  │
│  │  └─────────────────────────────┘  │  │
│  │  ┌─────────────────────────────┐  │  │
│  │  │   ProductsModule            │  │  │
│  │  │  - ProductsController       │  │  │
│  │  │  - ProductsService          │  │  │
│  │  └─────────────────────────────┘  │  │
│  └───────────────────────────────────┘  │
└─────────────────────────────────────────┘
```

### Organización por Módulos

Cada módulo puede contener:
- **Controllers** - Manejan las peticiones HTTP
- **Services** - Lógica de negocio y acceso a datos
- **DTOs** - Data Transfer Objects (validación de datos)
- **Entities** - Modelos de la base de datos
- **Interceptors** - Transforman las respuestas
- **Guards** - Autenticación y autorización
- **Middlewares** - Procesan las peticiones antes de llegar al controlador

### Limpiar el Proyecto Base

Para un proyecto limpio, puedes eliminar los archivos de ejemplo:

```bash
# Eliminar archivos innecesarios
rm src/app.controller.ts
rm src/app.controller.spec.ts
rm src/app.service.ts
```

**Actualizar `app.module.ts`:**

```typescript
import { Module } from '@nestjs/common';

@Module({
  imports: [],
  controllers: [],
  providers: [],
})
export class AppModule {}
```

Al ejecutar `npm run start:dev` y visitar `http://localhost:3000`, verás:
```json
{
  "statusCode": 404,
  "message": "Cannot GET /",
  "error": "Not Found"
}
```

Esto es correcto - aún no hay rutas definidas.

---

## 4. Servicio-Módulo-Controlador

### El Patrón MVC en NestJS

NestJS usa una arquitectura basada en tres componentes principales que trabajan juntos:

```
┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│              │     │              │     │              │
│   Module     │────▶│  Controller  │────▶│   Service    │
│              │     │              │     │              │
└──────────────┘     └──────────────┘     └──────────────┘
    Agrupa            Rutas HTTP          Lógica de
  componentes        y endpoints          negocio
```

### ¿Qué es un Módulo?

Un módulo es una clase anotada con el decorador `@Module()` que organiza componentes relacionados.

**Características:**
- Agrupa funcionalidad relacionada
- Encapsula controladores, servicios y otros providers
- Puede importar otros módulos
- Facilita la reutilización de código

**Ejemplo: Módulo de Tareas**

```typescript
// task/task.module.ts
import { Module } from '@nestjs/common';

@Module({
  imports: [],      // Otros módulos que necesita
  controllers: [],  // Controladores de este módulo
  providers: [],    // Servicios y otros providers
  exports: [],      // Lo que este módulo exporta para otros
})
export class TaskModule {}
```

### Relación entre Componentes

Un módulo completo incluye:

```
TaskModule/
├── task.module.ts       - Definición del módulo
├── task.controller.ts   - Maneja las rutas HTTP
├── task.service.ts      - Lógica de negocio
└── task.controller.spec.ts - Tests (opcional)
```

### Registrar un Módulo

Los módulos deben registrarse en el módulo raíz (`AppModule`):

```typescript
// app.module.ts
import { Module } from '@nestjs/common';
import { TaskModule } from './task/task.module';

@Module({
  imports: [
    TaskModule, // Importar el módulo de tareas
  ],
  controllers: [],
  providers: [],
})
export class AppModule {}
```

### Flujo de una Petición HTTP

```
1. Cliente HTTP (navegador/app)
        ↓
2. Ruta HTTP (/tasks)
        ↓
3. Controller (TaskController)
        ↓
4. Service (TaskService)
        ↓
5. Base de Datos / Lógica
        ↓
6. Respuesta al Cliente
```

### Ejemplo Completo

**1. Crear la estructura manualmente:**

```typescript
// task/task.module.ts
import { Module } from '@nestjs/common';

@Module({})
export class TaskModule {}
```

**2. Importar en AppModule:**

```typescript
// app.module.ts
import { Module } from '@nestjs/common';
import { TaskModule } from './task/task.module';

@Module({
  imports: [TaskModule],
})
export class AppModule {}
```

### Ventajas de esta Arquitectura

✅ **Separación de responsabilidades** - Cada componente tiene un propósito claro
✅ **Reutilización** - Los servicios pueden usarse en varios controladores
✅ **Testeable** - Cada componente puede probarse de forma independiente
✅ **Escalable** - Fácil añadir nuevos módulos sin afectar a los existentes
✅ **Mantenible** - Código organizado, fácil de encontrar

### Errores Comunes

❌ **No importar el módulo en AppModule** - El módulo no estará disponible
❌ **Olvidar registrar controladores/servicios** - No funcionarán
❌ **Importaciones circulares** - Pueden causar errores en tiempo de ejecución

---

## 5. Módulos en NestJS

### Crear Módulos Manualmente

Crear un módulo manualmente implica varios pasos:

**1. Crear la carpeta:**
```bash
mkdir src/tasks
```

**2. Crear el archivo del módulo:**
```typescript
// src/tasks/task.module.ts
import { Module } from '@nestjs/common';

@Module({
  imports: [],
  controllers: [],
  providers: [],
})
export class TaskModule {}
```

**3. Importar en AppModule:**
```typescript
// src/app.module.ts
import { Module } from '@nestjs/common';
import { TaskModule } from './tasks/task.module';

@Module({
  imports: [TaskModule],
})
export class AppModule {}
```

### Generar Módulos con la CLI

**Mucho más rápido y sin errores:**

```bash
# Sintaxis completa
nest generate module projects

# Forma abreviada
nest g module auth

# Forma más corta
nest g mo users
```

**Qué hace automáticamente:**
1. ✅ Crea la carpeta del módulo
2. ✅ Genera el archivo `*.module.ts`
3. ✅ Importa el módulo en `AppModule`
4. ✅ Configura la estructura básica

### Comandos de Generación

```bash
# Ver la ayuda de generate
nest generate --help

# Ver las opciones específicas de módulo
nest g module --help
```

### Ejemplos Prácticos

```bash
# Generar el módulo de projects
nest g mo projects
# CREATE src/projects/projects.module.ts
# UPDATE src/app.module.ts

# Generar el módulo de autenticación
nest g mo auth
# CREATE src/auth/auth.module.ts
# UPDATE src/app.module.ts

# Generar el módulo de users
nest g mo users
# CREATE src/users/users.module.ts
# UPDATE src/app.module.ts
```

### Resultado en AppModule

```typescript
// app.module.ts - Generado automáticamente
import { Module } from '@nestjs/common';
import { TaskModule } from './tasks/task.module';
import { ProjectsModule } from './projects/projects.module';
import { AuthModule } from './auth/auth.module';
import { UsersModule } from './users/users.module';

@Module({
  imports: [
    TaskModule,
    ProjectsModule,
    AuthModule,
    UsersModule,
  ],
  controllers: [],
  providers: [],
})
export class AppModule {}
```

### Estructura del Decorador @Module()

```typescript
@Module({
  // Módulos que este módulo necesita
  imports: [
    OtherModule,
    DatabaseModule,
  ],

  // Controladores de este módulo
  controllers: [
    TaskController,
  ],

  // Servicios y providers
  providers: [
    TaskService,
  ],

  // Lo que exporta para otros módulos
  exports: [
    TaskService,
  ],
})
```

### Organización por Funcionalidad

Cada módulo debería agrupar funcionalidad relacionada:

```
src/
├── auth/           - Autenticación y autorización
│   └── auth.module.ts
├── users/          - Gestión de usuarios
│   └── users.module.ts
├── products/       - Catálogo de productos
│   └── products.module.ts
├── orders/         - Gestión de pedidos
│   └── orders.module.ts
└── app.module.ts   - Módulo raíz
```

### Módulos Compartidos

Un módulo puede ser usado por otros módulos:

```typescript
// database/database.module.ts
@Module({
  providers: [DatabaseService],
  exports: [DatabaseService], // Exportar para otros módulos
})
export class DatabaseModule {}

// users/users.module.ts
@Module({
  imports: [DatabaseModule], // Importar el módulo compartido
  controllers: [UsersController],
  providers: [UsersService],
})
export class UsersModule {}
```

### Buenas Prácticas

✅ **Un módulo por funcionalidad** - No mezcles responsabilidades
✅ **Nombres descriptivos** - `UsersModule`, no `Module1`
✅ **Usa la CLI para generar** - Evita errores manuales
✅ **Exporta solo lo necesario** - Principio de encapsulación
✅ **Agrupa importaciones relacionadas** - Mejor organización

### Comandos Útiles

```bash
# Generar módulo
nest g mo name

# Generar módulo sin archivo de test
nest g mo name --no-spec

# Previsualizar lo que se generará sin crearlo
nest g mo name --dry-run

# Generar en una ruta específica
nest g mo modules/name
```

### Verificar la Aplicación

```bash
# Iniciar en modo desarrollo
npm run start:dev

# La consola muestra los módulos cargados
```

---

## 6. Servicios

### ¿Qué es un Servicio?

Un servicio es una clase que contiene la lógica de negocio de la aplicación. Se usa para:

- Consultas a la base de datos
- Lógica reutilizable
- Operaciones complejas
- Integración con APIs externas

**Principio:** Los controladores deben ser delgados, los servicios contienen la lógica.

### Crear un Servicio Manualmente

```typescript
// tasks/task.service.ts
import { Injectable } from '@nestjs/common';

@Injectable()
export class TaskService {
  getTask() {
    return ['Task 1', 'Task 2', 'Task 3'];
  }
}
```

**Registrar en el módulo:**

```typescript
// tasks/task.module.ts
import { Module } from '@nestjs/common';
import { TaskController } from './task.controller';
import { TaskService } from './task.service';

@Module({
  controllers: [TaskController],
  providers: [TaskService], // Registrar el servicio
})
export class TaskModule {}
```

### Inyección de Dependencias

Para usar un servicio en un controlador:

```typescript
// tasks/task.controller.ts
import { Controller, Get } from '@nestjs/common';
import { TaskService } from './task.service';

@Controller('tasks')
export class TaskController {
  // Forma 1: Inyección por constructor (verbosa)
  private taskService: TaskService;

  constructor(taskService: TaskService) {
    this.taskService = taskService;
  }

  @Get()
  getAllTasks() {
    return this.taskService.getTask();
  }
}
```

**Forma abreviada (recomendada):**

```typescript
@Controller('tasks')
export class TaskController {
  constructor(private taskService: TaskService) {}

  @Get()
  getAllTasks() {
    return this.taskService.getTask();
  }
}
```

### Generar Servicios con la CLI

```bash
# Sintaxis completa
nest generate service users

# Forma abreviada
nest g service projects

# Forma más corta
nest g s auth

# Sin archivo de test
nest g s auth --no-spec
```

**Qué hace:**
1. ✅ Crea el archivo `*.service.ts`
2. ✅ Añade el decorador `@Injectable()`
3. ✅ Lo registra en los `providers` del módulo
4. ✅ Crea el archivo de test `*.service.spec.ts` (opcional)

### Ejemplo Completo: Servicio de Usuarios

**Generar el servicio:**

```bash
nest g s users --no-spec
```

**Implementar la lógica:**

```typescript
// users/users.service.ts
import { Injectable } from '@nestjs/common';

@Injectable()
export class UsersService {
  private users = [
    { id: 1, name: 'John Doe', phone: '123456789' },
    { id: 2, name: 'Jane Smith', phone: '987654321' },
  ];

  getUsers() {
    return this.users;
  }

  getUserById(id: number) {
    return this.users.find(user => user.id === id);
  }

  createUser(name: string, phone: string) {
    const newUser = {
      id: this.users.length + 1,
      name,
      phone,
    };
    this.users.push(newUser);
    return newUser;
  }

  updateUser(id: number, name: string, phone: string) {
    const user = this.getUserById(id);
    if (user) {
      user.name = name;
      user.phone = phone;
    }
    return user;
  }

  deleteUser(id: number) {
    const index = this.users.findIndex(user => user.id === id);
    if (index !== -1) {
      this.users.splice(index, 1);
      return { deleted: true };
    }
    return { deleted: false };
  }
}
```

**Usar en el controlador:**

```typescript
// users/users.controller.ts
import { Controller, Get } from '@nestjs/common';
import { UsersService } from './users.service';

@Controller('users')
export class UsersController {
  constructor(private usersService: UsersService) {}

  @Get()
  getUsers() {
    return this.usersService.getUsers();
  }
}
```

### El Decorador @Injectable()

```typescript
@Injectable()
export class UserService {
  // Este decorador permite:
  // 1. Inyectar este servicio en otros componentes
  // 2. Inyectar otras dependencias en este servicio
  // 3. Gestión automática del ciclo de vida (Singleton por defecto)
}
```

### Servicios Reutilizables

Un servicio puede ser usado por varios controladores:

```typescript
// users/users.service.ts
@Injectable()
export class UsersService {
  getUsers() { /* ... */ }
}

// users/users.controller.ts
@Controller('users')
export class UsersController {
  constructor(private usersService: UsersService) {}
}

// auth/auth.controller.ts
@Controller('auth')
export class AuthController {
  constructor(private usersService: UsersService) {}
  // Puede usar el mismo servicio
}
```

### Servicios Anidados

Un servicio puede inyectar otros servicios:

```typescript
@Injectable()
export class EmailService {
  sendEmail(to: string, subject: string) {
    console.log(`Sending email to ${to}`);
  }
}

@Injectable()
export class UsersService {
  constructor(private emailService: EmailService) {}

  createUser(email: string) {
    // Lógica de creación
    this.emailService.sendEmail(email, 'Welcome');
    return { created: true };
  }
}
```

### Alcance (Scope) de los Servicios

Por defecto, los servicios son **Singleton** (una sola instancia compartida):

```typescript
@Injectable()
export class TaskService {
  // Una sola instancia para toda la aplicación
}

// También puedes especificar el alcance:
@Injectable({ scope: Scope.REQUEST })
export class TaskService {
  // Nueva instancia por cada petición HTTP
}
```

### Buenas Prácticas

✅ **Un servicio por responsabilidad** - Principio de responsabilidad única
✅ **Nombres descriptivos** - `UsersService`, `AuthService`
✅ **Lógica de negocio en los servicios** - No en los controladores
✅ **Métodos pequeños y enfocados** - Fáciles de testear
✅ **Usa la inyección de dependencias** - No instancies manualmente
✅ **Exporta los servicios si se usan en otros módulos**

### Errores Comunes

❌ **No registrar en providers** - El servicio no estará disponible
❌ **Olvidar `@Injectable()`** - La inyección no funcionará
❌ **Lógica de negocio en los controladores** - Difícil de testear y reutilizar
❌ **No exportar el servicio cuando se usa en otro módulo**

### Probar el Servicio

```bash
# Iniciar el servidor
npm run start:dev

# Probar el endpoint
curl http://localhost:3000/users
```

**Con Thunder Client en VS Code:**
1. Abre Thunder Client
2. New Request
3. GET `http://localhost:3000/users`
4. Send

---

## 7. Response

### Métodos HTTP en NestJS

NestJS soporta todos los métodos HTTP estándar:

```typescript
import { Controller, Get, Post, Put, Delete, Patch } from '@nestjs/common';

@Controller('tasks')
export class TaskController {
  @Get()    // GET - Recuperar recursos
  getTasks() {}

  @Post()   // POST - Crear recursos
  createTask() {}

  @Put()    // PUT - Actualización completa
  updateTask() {}

  @Patch()  // PATCH - Actualización parcial
  patchTask() {}

  @Delete() // DELETE - Eliminar recursos
  deleteTask() {}
}
```

### Diferencia entre PUT y PATCH

**PUT - Actualización completa:**
```typescript
// El cliente debe enviar TODOS los campos
PUT /tasks/1
{
  "title": "Updated task",
  "description": "New description",
  "status": true
}
```

**PATCH - Actualización parcial:**
```typescript
// El cliente envía SOLO los campos a actualizar
PATCH /tasks/1
{
  "status": true  // Solo actualizar el status
}
```

### Ejemplo Completo de CRUD

```typescript
// tasks/task.service.ts
import { Injectable } from '@nestjs/common';

@Injectable()
export class TaskService {
  private tasks = [];

  getTasks() {
    return this.tasks;
  }

  createTask(title: string) {
    const task = { id: Date.now(), title, status: false };
    this.tasks.push(task);
    return task;
  }

  updateTask(id: number, title: string, status: boolean) {
    const task = this.tasks.find(t => t.id === id);
    if (task) {
      task.title = title;
      task.status = status;
    }
    return task;
  }

  updateTaskStatus(id: number, status: boolean) {
    const task = this.tasks.find(t => t.id === id);
    if (task) {
      task.status = status;
    }
    return task;
  }

  deleteTask(id: number) {
    const index = this.tasks.findIndex(t => t.id === id);
    if (index !== -1) {
      this.tasks.splice(index, 1);
      return { deleted: true };
    }
    return { deleted: false };
  }
}
```

**Controlador completo:**

```typescript
// tasks/task.controller.ts
import { Controller, Get, Post, Put, Patch, Delete } from '@nestjs/common';
import { TaskService } from './task.service';

@Controller('tasks')
export class TaskController {
  constructor(private taskService: TaskService) {}

  @Get()
  getTasks() {
    return this.taskService.getTasks();
  }

  @Post()
  createTask() {
    return this.taskService.createTask('New task');
  }

  @Put()
  updateTask() {
    return this.taskService.updateTask(1, 'Updated task', true);
  }

  @Patch()
  updateTaskStatus() {
    return this.taskService.updateTaskStatus(1, true);
  }

  @Delete()
  deleteTask() {
    return this.taskService.deleteTask(1);
  }
}
```

### Probar con Thunder Client

**Petición GET:**
```
GET http://localhost:3000/tasks
Response: []
```

**Petición POST:**
```
POST http://localhost:3000/tasks
Response: { "id": 1, "title": "New task", "status": false }
```

**Petición PUT:**
```
PUT http://localhost:3000/tasks
Response: { "id": 1, "title": "Updated task", "status": true }
```

**Petición PATCH:**
```
PATCH http://localhost:3000/tasks
Response: { "id": 1, "title": "Updated task", "status": true }
```

**Petición DELETE:**
```
DELETE http://localhost:3000/tasks
Response: { "deleted": true }
```

### Prefijos de Ruta

Evita repetir el prefijo en cada método:

```typescript
// ❌ Mal - Repetitivo
@Controller()
export class TaskController {
  @Get('tasks')
  getTasks() {}

  @Post('tasks')
  createTask() {}
}

// ✅ Bien - Prefijo en el Controller
@Controller('tasks')
export class TaskController {
  @Get()  // /tasks
  getTasks() {}

  @Post() // /tasks
  createTask() {}
}
```

### Múltiples Rutas en un Controlador

```typescript
@Controller()
export class AppController {
  @Get()  // /
  index() {
    return 'Home page';
  }

  @Get('about')  // /about
  about() {
    return 'About';
  }

  @Get('contact')  // /contact
  contact() {
    return 'Contact';
  }
}
```

### Tipos de Respuesta

NestJS puede devolver distintos tipos de datos:

```typescript
@Controller('api')
export class ApiController {
  // String
  @Get('text')
  getText() {
    return 'Hello World';
  }

  // Number
  @Get('number')
  getNumber() {
    return 42;
  }

  // Boolean
  @Get('boolean')
  getBoolean() {
    return true;
  }

  // Object
  @Get('object')
  getObject() {
    return { message: 'Hello', status: 'ok' };
  }

  // Array
  @Get('array')
  getArray() {
    return [1, 2, 3, 4, 5];
  }

  // Array de objetos
  @Get('users')
  getUsers() {
    return [
      { id: 1, name: 'John' },
      { id: 2, name: 'Jane' },
    ];
  }
}
```

Todas las respuestas se serializan automáticamente a JSON (excepto las cadenas simples).

### Buenas Prácticas

✅ **Usa el método HTTP apropiado** - GET para leer, POST para crear
✅ **Prefijos en @Controller()** - Evita repetición
✅ **PUT para actualización completa** - Todos los campos
✅ **PATCH para actualización parcial** - Solo los campos necesarios
✅ **DELETE devuelve confirmación** - `{ deleted: true }`
✅ **Devuelve objetos consistentes** - Facilita el trabajo del cliente

---

## 8. Validaciones

### ¿Por Qué Validar?

Las validaciones aseguran que los datos recibidos:
- ✅ Tengan el formato correcto
- ✅ Cumplan las reglas de negocio
- ✅ Sean seguros de procesar
- ✅ Eviten errores en la base de datos

### Instalar Dependencias

```bash
# Instalar class-validator y class-transformer
npm install class-validator class-transformer
```

**class-validator:** Decoradores para la validación
**class-transformer:** Transforma objetos planos en instancias de clase

### Habilitar la Validación Global

```typescript
// main.ts
import { NestFactory } from '@nestjs/core';
import { ValidationPipe } from '@nestjs/common';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);

  // Habilitar la validación global
  app.useGlobalPipes(new ValidationPipe());

  await app.listen(3000);
}
bootstrap();
```

### DTOs (Data Transfer Objects)

Los DTOs definen la estructura de datos esperada:

```bash
# Crear la carpeta para los DTOs
mkdir src/tasks/dto

# Crear el archivo DTO
touch src/tasks/dto/create-task.dto.ts
```

**Ejemplo de DTO:**

```typescript
// tasks/dto/create-task.dto.ts
import { IsString, IsBoolean, IsOptional, MinLength, MaxLength } from 'class-validator';

export class CreateTaskDto {
  @IsString()
  @MinLength(3)
  @MaxLength(100)
  title: string;

  @IsString()
  @IsOptional()
  description?: string;

  @IsBoolean()
  @IsOptional()
  status?: boolean;
}
```

### Decoradores de Validación Comunes

```typescript
import {
  IsString,
  IsNumber,
  IsInt,
  IsBoolean,
  IsEmail,
  IsUrl,
  IsDate,
  IsArray,
  IsEnum,
  IsOptional,
  IsNotEmpty,
  MinLength,
  MaxLength,
  Min,
  Max,
  Matches,
} from 'class-validator';

export class UserDto {
  @IsString()
  @IsNotEmpty()
  @MinLength(3)
  @MaxLength(50)
  name: string;

  @IsEmail()
  email: string;

  @IsInt()
  @Min(18)
  @Max(120)
  age: number;

  @IsUrl()
  @IsOptional()
  website?: string;

  @IsBoolean()
  isActive: boolean;

  @IsEnum(['admin', 'user', 'guest'])
  role: string;

  @Matches(/^[0-9]{10}$/)
  phone: string;
}
```

### Usar DTOs en los Controladores

```typescript
// tasks/task.controller.ts
import { Controller, Post, Body } from '@nestjs/common';
import { CreateTaskDto } from './dto/create-task.dto';
import { TaskService } from './task.service';

@Controller('tasks')
export class TaskController {
  constructor(private taskService: TaskService) {}

  @Post()
  createTask(@Body() createTaskDto: CreateTaskDto) {
    return this.taskService.createTask(createTaskDto);
  }
}
```

**El decorador @Body():**
- Extrae el body de la petición HTTP
- Valida automáticamente si hay un DTO tipado
- Transforma a instancia de clase

### Actualizar el Servicio

```typescript
// tasks/task.service.ts
import { Injectable } from '@nestjs/common';
import { CreateTaskDto } from './dto/create-task.dto';

@Injectable()
export class TaskService {
  private tasks = [];

  createTask(createTaskDto: CreateTaskDto) {
    const task = {
      id: Date.now(),
      ...createTaskDto,
      status: createTaskDto.status ?? false,
    };
    this.tasks.push(task);
    return task;
  }
}
```

### Probar las Validaciones

**Petición válida:**

```bash
POST http://localhost:3000/tasks
Content-Type: application/json

{
  "title": "My first task",
  "description": "Task description"
}

# Respuesta: 201 Created
{
  "id": 1672531200000,
  "title": "My first task",
  "description": "Task description",
  "status": false
}
```

**Petición inválida (título demasiado corto):**

```bash
POST http://localhost:3000/tasks
Content-Type: application/json

{
  "title": "AB",
  "description": "Description"
}

# Respuesta: 400 Bad Request
{
  "statusCode": 400,
  "message": [
    "title must be longer than or equal to 3 characters"
  ],
  "error": "Bad Request"
}
```

**Petición inválida (tipo incorrecto):**

```bash
POST http://localhost:3000/tasks
Content-Type: application/json

{
  "title": 12345,
  "status": "true"
}

# Respuesta: 400 Bad Request
{
  "statusCode": 400,
  "message": [
    "title must be a string",
    "status must be a boolean value"
  ],
  "error": "Bad Request"
}
```

### DTO para Actualización

```typescript
// tasks/dto/update-task.dto.ts
import { IsString, IsBoolean, IsOptional, MinLength } from 'class-validator';

export class UpdateTaskDto {
  @IsString()
  @MinLength(3)
  @IsOptional()
  title?: string;

  @IsString()
  @IsOptional()
  description?: string;

  @IsBoolean()
  @IsOptional()
  status?: boolean;
}
```

**Usar en PATCH:**

```typescript
import { Patch, Param, Body } from '@nestjs/common';
import { UpdateTaskDto } from './dto/update-task.dto';

@Controller('tasks')
export class TaskController {
  @Patch(':id')
  updateTask(
    @Param('id') id: string,
    @Body() updateTaskDto: UpdateTaskDto
  ) {
    return this.taskService.updateTask(+id, updateTaskDto);
  }
}
```

### Opciones de ValidationPipe

```typescript
// main.ts
app.useGlobalPipes(new ValidationPipe({
  whitelist: true,        // Elimina las propiedades no definidas en el DTO
  forbidNonWhitelisted: true, // Lanza error si hay props extra
  transform: true,        // Transforma a instancia de clase
  transformOptions: {
    enableImplicitConversion: true, // Convierte tipos automáticamente
  },
}));
```

**Ejemplo con whitelist:**

```typescript
// DTO
export class CreateTaskDto {
  @IsString()
  title: string;
}

// Petición
POST /tasks
{ "title": "Task", "extra": "data" }

// Con whitelist: true
// Elimina "extra", solo guarda "title"

// Con forbidNonWhitelisted: true
// Error: "property extra should not exist"
```

### Validaciones Personalizadas

```typescript
import { registerDecorator, ValidationOptions } from 'class-validator';

// Crear un validador personalizado
export function IsNotOnlySpaces(validationOptions?: ValidationOptions) {
  return function (object: Object, propertyName: string) {
    registerDecorator({
      name: 'isNotOnlySpaces',
      target: object.constructor,
      propertyName: propertyName,
      options: validationOptions,
      validator: {
        validate(value: any) {
          return typeof value === 'string' && value.trim().length > 0;
        },
        defaultMessage() {
          return 'Field cannot contain only spaces';
        },
      },
    });
  };
}

// Usar en el DTO
export class CreateTaskDto {
  @IsString()
  @IsNotOnlySpaces()
  title: string;
}
```

### Buenas Prácticas

✅ **Valida siempre los datos de entrada** - Nunca confíes en el cliente
✅ **DTOs para cada operación** - CreateDto, UpdateDto separados
✅ **Mensajes de error claros** - Ayuda al desarrollador frontend
✅ **whitelist: true** - Seguridad contra propiedades extra
✅ **Valida en el controlador** - Antes de llegar al servicio
✅ **Documenta las validaciones** - Comentarios en DTOs complejos

### Errores Comunes

❌ **No instalar las dependencias** - class-validator y class-transformer
❌ **No habilitar ValidationPipe** - Las validaciones no funcionarán
❌ **Olvidar @IsOptional()** - Los campos opcionales dan error
❌ **No tipar con DTO en el controlador** - No validará automáticamente

---

## 9. Errores de Estado HTTP

### Códigos de Estado HTTP

Los códigos HTTP comunican el resultado de una petición:

**2xx - Éxito:**
- 200 OK - Petición exitosa
- 201 Created - Recurso creado
- 204 No Content - Exitosa sin contenido

**4xx - Error del cliente:**
- 400 Bad Request - Datos inválidos
- 401 Unauthorized - No autenticado
- 403 Forbidden - No autorizado
- 404 Not Found - Recurso no encontrado

**5xx - Error del servidor:**
- 500 Internal Server Error - Error del servidor
- 503 Service Unavailable - Servicio no disponible

### Lanzar Excepciones en NestJS

NestJS proporciona excepciones HTTP predefinidas:

```typescript
import {
  NotFoundException,
  BadRequestException,
  UnauthorizedException,
  ForbiddenException,
  ConflictException,
  InternalServerErrorException,
} from '@nestjs/common';
```

### Ejemplos Prácticos

**404 Not Found:**

```typescript
// tasks/task.service.ts
import { Injectable, NotFoundException } from '@nestjs/common';

@Injectable()
export class TaskService {
  private tasks = [];

  getTaskById(id: number) {
    const task = this.tasks.find(t => t.id === id);

    if (!task) {
      throw new NotFoundException(`Task with ID ${id} not found`);
    }

    return task;
  }
}
```

**400 Bad Request:**

```typescript
import { BadRequestException } from '@nestjs/common';

@Injectable()
export class TaskService {
  createTask(createTaskDto: CreateTaskDto) {
    if (!createTaskDto.title) {
      throw new BadRequestException('Title is required');
    }

    // Lógica de creación
  }
}
```

**409 Conflict:**

```typescript
import { ConflictException } from '@nestjs/common';

@Injectable()
export class UsersService {
  createUser(email: string) {
    const exists = this.users.find(u => u.email === email);

    if (exists) {
      throw new ConflictException('Email already registered');
    }

    // Crear usuario
  }
}
```

### Controlador con Manejo de Errores

```typescript
// tasks/task.controller.ts
import { Controller, Get, Param, NotFoundException } from '@nestjs/common';
import { TaskService } from './task.service';

@Controller('tasks')
export class TaskController {
  constructor(private taskService: TaskService) {}

  @Get(':id')
  getTask(@Param('id') id: string) {
    const task = this.taskService.getTaskById(+id);

    if (!task) {
      throw new NotFoundException(`Task ${id} not found`);
    }

    return task;
  }
}
```

### Personalizar la Respuesta de Error

```typescript
throw new NotFoundException({
  statusCode: 404,
  message: 'Resource not found',
  error: 'Not Found',
  timestamp: new Date().toISOString(),
  path: '/tasks/123',
});
```

### HttpException Genérica

Para códigos de estado personalizados:

```typescript
import { HttpException, HttpStatus } from '@nestjs/common';

throw new HttpException('Custom message', HttpStatus.PAYMENT_REQUIRED);

// O con objeto
throw new HttpException({
  status: HttpStatus.FORBIDDEN,
  error: 'Access denied',
}, HttpStatus.FORBIDDEN);
```

### Filtros de Excepciones Personalizados

Para el manejo global de excepciones:

```typescript
// common/filters/http-exception.filter.ts
import {
  ExceptionFilter,
  Catch,
  ArgumentsHost,
  HttpException,
} from '@nestjs/common';

@Catch(HttpException)
export class HttpExceptionFilter implements ExceptionFilter {
  catch(exception: HttpException, host: ArgumentsHost) {
    const ctx = host.switchToHttp();
    const response = ctx.getResponse();
    const request = ctx.getRequest();
    const status = exception.getStatus();

    response.status(status).json({
      statusCode: status,
      timestamp: new Date().toISOString(),
      path: request.url,
      message: exception.message,
    });
  }
}
```

**Aplicar globalmente:**

```typescript
// main.ts
import { HttpExceptionFilter } from './common/filters/http-exception.filter';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  app.useGlobalFilters(new HttpExceptionFilter());
  await app.listen(3000);
}
bootstrap();
```

### Probar los Errores

**404 Not Found:**
```bash
GET http://localhost:3000/tasks/999

Response:
{
  "statusCode": 404,
  "message": "Task with ID 999 not found",
  "error": "Not Found"
}
```

**400 Bad Request:**
```bash
POST http://localhost:3000/tasks
{ "title": "" }

Response:
{
  "statusCode": 400,
  "message": "Title is required",
  "error": "Bad Request"
}
```

### Buenas Prácticas

✅ **Usa excepciones específicas** - NotFoundException mejor que HttpException
✅ **Mensajes descriptivos** - Ayuda al frontend a mostrar errores
✅ **Lanza errores en los servicios** - No en los controladores cuando sea posible
✅ **No expongas detalles técnicos** - En producción, mensajes genéricos
✅ **Logging de errores** - Registra para depuración

### Todas las Excepciones HTTP

```typescript
import {
  BadRequestException,        // 400
  UnauthorizedException,      // 401
  NotFoundException,          // 404
  ForbiddenException,         // 403
  NotAcceptableException,     // 406
  RequestTimeoutException,    // 408
  ConflictException,          // 409
  GoneException,              // 410
  PayloadTooLargeException,   // 413
  UnsupportedMediaTypeException, // 415
  UnprocessableEntityException,  // 422
  InternalServerErrorException,  // 500
  NotImplementedException,    // 501
  BadGatewayException,        // 502
  ServiceUnavailableException,// 503
  GatewayTimeoutException,    // 504
} from '@nestjs/common';
```

---

## 10. Pipes

### ¿Qué son los Pipes?

Los pipes son funciones que procesan y transforman los datos antes de llegar al controlador:

- **Transformación:** Convertir datos al tipo deseado
- **Validación:** Verificar que los datos son correctos

```
Request → Pipe → Controller → Service
           ↓
      Transformar/Validar
```

### Pipes Integrados

NestJS incluye pipes predefinidos:

```typescript
import {
  ValidationPipe,    // Valida con class-validator
  ParseIntPipe,      // Convierte a entero
  ParseFloatPipe,    // Convierte a decimal
  ParseBoolPipe,     // Convierte a booleano
  ParseArrayPipe,    // Convierte a array
  ParseUUIDPipe,     // Valida UUID
  ParseEnumPipe,     // Valida enum
  DefaultValuePipe,  // Valor por defecto
} from '@nestjs/common';
```

### ParseIntPipe

Convierte cadenas a números:

```typescript
import { Controller, Get, Param, ParseIntPipe } from '@nestjs/common';

@Controller('tasks')
export class TaskController {
  @Get(':id')
  getTask(@Param('id', ParseIntPipe) id: number) {
    // se garantiza que id es un number
    console.log(typeof id); // 'number'
    return this.taskService.getTaskById(id);
  }
}
```

**Sin ParseIntPipe:**
```typescript
@Get(':id')
getTask(@Param('id') id: string) {
  console.log(typeof id); // 'string'
  const numId = +id; // Conversión manual
}
```

**Pruebas:**
```bash
# Válido
GET /tasks/10
Response: { id: 10, ... }

# Inválido
GET /tasks/abc
Response:
{
  "statusCode": 400,
  "message": "Validation failed (numeric string is expected)",
  "error": "Bad Request"
}
```

### ParseBoolPipe

```typescript
@Get()
getTasks(@Query('completed', ParseBoolPipe) completed: boolean) {
  return this.taskService.getTasks(completed);
}
```

```bash
GET /tasks?completed=true  # boolean true
GET /tasks?completed=false # boolean false
GET /tasks?completed=1     # boolean true
GET /tasks?completed=0     # boolean false
```

### ParseUUIDPipe

```typescript
@Get(':uuid')
getByUUID(@Param('uuid', ParseUUIDPipe) uuid: string) {
  return this.taskService.getByUUID(uuid);
}
```

```bash
# Válido
GET /tasks/550e8400-e29b-41d4-a716-446655440000

# Inválido
GET /tasks/123
Response: "Validation failed (uuid is expected)"
```

### ParseArrayPipe

```typescript
@Get()
getTasks(@Query('ids', ParseArrayPipe) ids: number[]) {
  console.log(ids); // [1, 2, 3]
}
```

```bash
GET /tasks?ids=1,2,3
```

### DefaultValuePipe

```typescript
@Get()
getTasks(
  @Query('page', new DefaultValuePipe(1), ParseIntPipe) page: number
) {
  // Si 'page' no se envía, usa 1 por defecto
}
```

```bash
GET /tasks         # page = 1 (por defecto)
GET /tasks?page=5  # page = 5
```

### Pipes en el Body

```typescript
@Post()
createTask(@Body(ValidationPipe) createTaskDto: CreateTaskDto) {
  return this.taskService.createTask(createTaskDto);
}
```

### Pipes a Nivel de Parámetro

```typescript
@Get(':id')
getTask(
  @Param('id', new ParseIntPipe({ errorHttpStatusCode: 404 })) id: number
) {
  // Personalizar el código de error
}
```

### Pipe Personalizado

Crear un pipe personalizado:

```bash
nest g pipe common/pipes/positive-int
```

```typescript
// common/pipes/positive-int.pipe.ts
import { PipeTransform, Injectable, BadRequestException } from '@nestjs/common';

@Injectable()
export class PositiveIntPipe implements PipeTransform {
  transform(value: any) {
    const val = parseInt(value, 10);

    if (isNaN(val)) {
      throw new BadRequestException('Must be a number');
    }

    if (val <= 0) {
      throw new BadRequestException('Must be a positive number');
    }

    return val;
  }
}
```

**Usar:**

```typescript
@Get(':id')
getTask(@Param('id', PositiveIntPipe) id: number) {
  // se garantiza que id es un número positivo
}
```

### Pipe para Transformar Datos

```typescript
// common/pipes/to-uppercase.pipe.ts
import { PipeTransform, Injectable } from '@nestjs/common';

@Injectable()
export class ToUpperCasePipe implements PipeTransform {
  transform(value: string): string {
    return value.toUpperCase();
  }
}
```

```typescript
@Post()
createTask(@Body('title', ToUpperCasePipe) title: string) {
  console.log(title); // "MY TASK" (mayúsculas)
}
```

### Combinar Múltiples Pipes

```typescript
@Get(':id')
getTask(
  @Param('id', ParseIntPipe, PositiveIntPipe) id: number
) {
  // Primero ParseIntPipe, luego PositiveIntPipe
}
```

### Pipes Globales

```typescript
// main.ts
import { ValidationPipe } from '@nestjs/common';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);

  app.useGlobalPipes(new ValidationPipe({
    whitelist: true,
    forbidNonWhitelisted: true,
    transform: true,
  }));

  await app.listen(3000);
}
bootstrap();
```

### Opciones de ParseIntPipe

```typescript
@Get(':id')
getTask(
  @Param('id', new ParseIntPipe({
    errorHttpStatusCode: HttpStatus.NOT_FOUND,
    exceptionFactory: () => new NotFoundException('Invalid ID'),
  }))
  id: number
) {}
```

### Buenas Prácticas

✅ **Usa los pipes integrados cuando sea posible** - Ya están probados
✅ **ParseIntPipe para IDs numéricos** - Evita conversiones manuales
✅ **ValidationPipe global** - Valida todos los DTOs automáticamente
✅ **Pipes personalizados para lógica específica** - Reutilizables
✅ **Mensajes de error claros** - Facilita la depuración

### Errores Comunes

❌ **No validar los tipos** - Causa errores en tiempo de ejecución
❌ **Conversiones manuales** - Usa pipes en su lugar
❌ **No manejar los errores del pipe** - El pipe lanza excepciones

---

## 11. Guards

### ¿Qué son los Guards?

Los guards determinan si una petición debe ser manejada por el route handler:

- **Autenticación:** ¿El usuario ha iniciado sesión?
- **Autorización:** ¿El usuario tiene permisos?
- **Lógica condicional:** ¿Se cumple una cierta condición?

```
Request → Guard → Controller → Service
           ↓
    ¿Permitir acceso?
     Sí/No (403)
```

### Crear un Guard

```bash
nest g guard common/guards/auth
```

```typescript
// common/guards/auth.guard.ts
import { Injectable, CanActivate, ExecutionContext } from '@nestjs/common';
import { Observable } from 'rxjs';

@Injectable()
export class AuthGuard implements CanActivate {
  canActivate(
    context: ExecutionContext,
  ): boolean | Promise<boolean> | Observable<boolean> {
    const request = context.switchToHttp().getRequest();

    // Lógica de autenticación
    const token = request.headers['authorization'];

    if (!token) {
      return false; // Bloquear el acceso
    }

    // Validar el token (ejemplo simplificado)
    return token === 'my-secret-token';
  }
}
```

### Aplicar un Guard a una Ruta

```typescript
import { Controller, Get, UseGuards } from '@nestjs/common';
import { AuthGuard } from './guards/auth.guard';

@Controller('tasks')
export class TaskController {
  @Get()
  @UseGuards(AuthGuard)
  getTasks() {
    return this.taskService.getTasks();
  }
}
```

### Aplicar un Guard a Todo el Controlador

```typescript
@Controller('tasks')
@UseGuards(AuthGuard)
export class TaskController {
  // Todas las rutas requieren autenticación

  @Get()
  getTasks() {}

  @Post()
  createTask() {}
}
```

### Guard Global

```typescript
// main.ts
import { AuthGuard } from './common/guards/auth.guard';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  app.useGlobalGuards(new AuthGuard());
  await app.listen(3000);
}
bootstrap();
```

### Guard con Inyección de Dependencias

```typescript
// common/guards/roles.guard.ts
import { Injectable, CanActivate, ExecutionContext } from '@nestjs/common';
import { Reflector } from '@nestjs/core';

@Injectable()
export class RolesGuard implements CanActivate {
  constructor(private reflector: Reflector) {}

  canActivate(context: ExecutionContext): boolean {
    const roles = this.reflector.get<string[]>('roles', context.getHandler());

    if (!roles) {
      return true;
    }

    const request = context.switchToHttp().getRequest();
    const user = request.user;

    return roles.includes(user?.role);
  }
}
```

### Decorador Personalizado para Roles

```typescript
// common/decorators/roles.decorator.ts
import { SetMetadata } from '@nestjs/common';

export const Roles = (...roles: string[]) => SetMetadata('roles', roles);
```

**Usar:**

```typescript
import { Roles } from './decorators/roles.decorator';
import { RolesGuard } from './guards/roles.guard';

@Controller('admin')
@UseGuards(RolesGuard)
export class AdminController {
  @Get('users')
  @Roles('admin', 'superadmin')
  getUsers() {
    // Solo admin y superadmin pueden acceder
  }

  @Get('dashboard')
  @Roles('admin')
  getDashboard() {
    // Solo admin
  }
}
```

### Guard con Excepciones Personalizadas

```typescript
import { Injectable, CanActivate, ExecutionContext, UnauthorizedException } from '@nestjs/common';

@Injectable()
export class AuthGuard implements CanActivate {
  canActivate(context: ExecutionContext): boolean {
    const request = context.switchToHttp().getRequest();
    const token = request.headers['authorization'];

    if (!token) {
      throw new UnauthorizedException('Token not provided');
    }

    if (!this.validateToken(token)) {
      throw new UnauthorizedException('Invalid token');
    }

    return true;
  }

  private validateToken(token: string): boolean {
    // Lógica de validación
    return token === 'valid-token';
  }
}
```

### Probar los Guards

**Sin token:**
```bash
GET http://localhost:3000/tasks

Response:
{
  "statusCode": 401,
  "message": "Token not provided",
  "error": "Unauthorized"
}
```

**Con token válido:**
```bash
GET http://localhost:3000/tasks
Authorization: my-secret-token

Response: [...]
```

### Múltiples Guards

```typescript
@Get()
@UseGuards(AuthGuard, RolesGuard)
getTasks() {
  // Primero AuthGuard, luego RolesGuard
}
```

### Buenas Prácticas

✅ **Un guard por responsabilidad** - AuthGuard separado de RolesGuard
✅ **Guards para autenticación** - No lógica de negocio
✅ **Excepciones claras** - UnauthorizedException, ForbiddenException
✅ **Combina con decoradores** - Metadatos para los roles
✅ **Tests unitarios** - Verifica la lógica del guard

### Diferencia: Guard vs Middleware

**Guard:**
- Después de los middlewares
- Acceso al contexto de ejecución
- Para autorización/autenticación

**Middleware:**
- Antes de los guards
- Procesa las peticiones
- Para logging, parsing, etc.

---

## 12. Middlewares

### ¿Qué son los Middlewares?

Los middlewares son funciones que se ejecutan **antes** de que la petición llegue al route handler:

```
Request → Middleware → Guard → Pipe → Controller → Service
            ↓
    Procesar la petición
    (logging, auth, etc.)
```

### Crear un Middleware

```bash
nest g middleware common/middlewares/logger
```

```typescript
// common/middlewares/logger.middleware.ts
import { Injectable, NestMiddleware } from '@nestjs/common';
import { Request, Response, NextFunction } from 'express';

@Injectable()
export class LoggerMiddleware implements NestMiddleware {
  use(req: Request, res: Response, next: NextFunction) {
    console.log(`[${new Date().toISOString()}] ${req.method} ${req.url}`);
    next(); // Importante: llamar a next() para continuar
  }
}
```

### Aplicar un Middleware en un Módulo

```typescript
// app.module.ts
import { Module, NestModule, MiddlewareConsumer } from '@nestjs/common';
import { LoggerMiddleware } from './common/middlewares/logger.middleware';
import { TaskModule } from './tasks/task.module';

@Module({
  imports: [TaskModule],
})
export class AppModule implements NestModule {
  configure(consumer: MiddlewareConsumer) {
    consumer
      .apply(LoggerMiddleware)
      .forRoutes('*'); // Aplicar a todas las rutas
  }
}
```

### Aplicar a Rutas Específicas

```typescript
configure(consumer: MiddlewareConsumer) {
  consumer
    .apply(LoggerMiddleware)
    .forRoutes('tasks'); // Solo /tasks
}

// Múltiples rutas
configure(consumer: MiddlewareConsumer) {
  consumer
    .apply(LoggerMiddleware)
    .forRoutes('tasks', 'users', 'products');
}
```

### Aplicar a Controladores Específicos

```typescript
import { TaskController } from './tasks/task.controller';

configure(consumer: MiddlewareConsumer) {
  consumer
    .apply(LoggerMiddleware)
    .forRoutes(TaskController);
}
```

### Aplicar a Métodos HTTP Específicos

```typescript
import { RequestMethod } from '@nestjs/common';

configure(consumer: MiddlewareConsumer) {
  consumer
    .apply(LoggerMiddleware)
    .forRoutes({ path: 'tasks', method: RequestMethod.POST });
}
```

### Excluir Rutas

```typescript
configure(consumer: MiddlewareConsumer) {
  consumer
    .apply(LoggerMiddleware)
    .exclude(
      { path: 'tasks', method: RequestMethod.GET },
      { path: 'tasks/:id', method: RequestMethod.DELETE },
    )
    .forRoutes('*');
}
```

### Múltiples Middlewares

```typescript
configure(consumer: MiddlewareConsumer) {
  consumer
    .apply(LoggerMiddleware, AuthMiddleware, CorsMiddleware)
    .forRoutes('*');
}
```

### Middleware de Autenticación

```typescript
// common/middlewares/auth.middleware.ts
import { Injectable, NestMiddleware, UnauthorizedException } from '@nestjs/common';
import { Request, Response, NextFunction } from 'express';

@Injectable()
export class AuthMiddleware implements NestMiddleware {
  use(req: Request, res: Response, next: NextFunction) {
    const token = req.headers['authorization'];

    if (!token) {
      throw new UnauthorizedException('Token required');
    }

    // Validar el token y añadir el usuario a la petición
    req['user'] = { id: 1, name: 'John', role: 'admin' };

    next();
  }
}
```

### Middleware Funcional

Para middlewares simples, usa funciones:

```typescript
// common/middlewares/logger.middleware.ts
import { Request, Response, NextFunction } from 'express';

export function loggerMiddleware(req: Request, res: Response, next: NextFunction) {
  console.log(`Request: ${req.method} ${req.url}`);
  next();
}
```

**Aplicar:**

```typescript
configure(consumer: MiddlewareConsumer) {
  consumer
    .apply(loggerMiddleware)
    .forRoutes('*');
}
```

### Middleware Global (Funcional)

```typescript
// main.ts
import { loggerMiddleware } from './common/middlewares/logger.middleware';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  app.use(loggerMiddleware); // Middleware funcional global
  await app.listen(3000);
}
bootstrap();
```

### Middleware con Configuración

```typescript
// common/middlewares/cors.middleware.ts
import { Injectable, NestMiddleware } from '@nestjs/common';
import { Request, Response, NextFunction } from 'express';

@Injectable()
export class CorsMiddleware implements NestMiddleware {
  use(req: Request, res: Response, next: NextFunction) {
    res.header('Access-Control-Allow-Origin', '*');
    res.header('Access-Control-Allow-Methods', 'GET,PUT,POST,DELETE');
    res.header('Access-Control-Allow-Headers', 'Content-Type, Authorization');

    if (req.method === 'OPTIONS') {
      res.sendStatus(200);
    } else {
      next();
    }
  }
}
```

### Middleware para Medir el Tiempo

```typescript
// common/middlewares/timer.middleware.ts
import { Injectable, NestMiddleware } from '@nestjs/common';
import { Request, Response, NextFunction } from '@nestjs/common';

@Injectable()
export class TimerMiddleware implements NestMiddleware {
  use(req: Request, res: Response, next: NextFunction) {
    const start = Date.now();

    res.on('finish', () => {
      const duration = Date.now() - start;
      console.log(`${req.method} ${req.url} - ${duration}ms`);
    });

    next();
  }
}
```

### Orden de Ejecución

```
1. Middlewares globales (app.use)
2. Middlewares de módulo
3. Guards globales
4. Guards de ruta
5. Interceptors (antes)
6. Pipes
7. Controller/Route handler
8. Interceptors (después)
9. Filtros de excepciones
```

### Buenas Prácticas

✅ **Llama siempre a next()** - O la petición se queda colgada
✅ **Middlewares para lógica común** - Logging, parsing, CORS
✅ **Guards para autorización** - No middlewares
✅ **Middlewares funcionales para casos simples** - Menos código
✅ **El orden de los middlewares importa** - Auth antes del logging del usuario

### Errores Comunes

❌ **Olvidar next()** - La petición nunca continúa
❌ **Lógica de negocio en los middlewares** - Debería ir en los servicios
❌ **No manejar los errores** - Usa try/catch cuando sea necesario

---

## 13. Resources

### Generar un CRUD Completo

La CLI de NestJS puede generar un módulo CRUD completo con un solo comando:

```bash
nest g resource name
```

**El comando pregunta:**
1. ¿Qué capa de transporte? → REST API
2. ¿Generar puntos de entrada CRUD? → Sí

### Lo Que se Genera

```bash
nest g resource products

CREATE src/products/products.controller.ts
CREATE src/products/products.controller.spec.ts
CREATE src/products/products.module.ts
CREATE src/products/products.service.ts
CREATE src/products/products.service.spec.ts
CREATE src/products/dto/create-product.dto.ts
CREATE src/products/dto/update-product.dto.ts
CREATE src/products/entities/product.entity.ts
UPDATE src/app.module.ts
```

### Estructura Generada

```
src/products/
├── dto/
│   ├── create-product.dto.ts
│   └── update-product.dto.ts
├── entities/
│   └── product.entity.ts
├── products.controller.ts
├── products.controller.spec.ts
├── products.module.ts
├── products.service.ts
└── products.service.spec.ts
```

### Controlador Generado

```typescript
// products/products.controller.ts
import { Controller, Get, Post, Body, Patch, Param, Delete } from '@nestjs/common';
import { ProductsService } from './products.service';
import { CreateProductDto } from './dto/create-product.dto';
import { UpdateProductDto } from './dto/update-product.dto';

@Controller('products')
export class ProductsController {
  constructor(private readonly productsService: ProductsService) {}

  @Post()
  create(@Body() createProductDto: CreateProductDto) {
    return this.productsService.create(createProductDto);
  }

  @Get()
  findAll() {
    return this.productsService.findAll();
  }

  @Get(':id')
  findOne(@Param('id') id: string) {
    return this.productsService.findOne(+id);
  }

  @Patch(':id')
  update(@Param('id') id: string, @Body() updateProductDto: UpdateProductDto) {
    return this.productsService.update(+id, updateProductDto);
  }

  @Delete(':id')
  remove(@Param('id') id: string) {
    return this.productsService.remove(+id);
  }
}
```

### Servicio Generado

```typescript
// products/products.service.ts
import { Injectable } from '@nestjs/common';
import { CreateProductDto } from './dto/create-product.dto';
import { UpdateProductDto } from './dto/update-product.dto';

@Injectable()
export class ProductsService {
  create(createProductDto: CreateProductDto) {
    return 'This action adds a new product';
  }

  findAll() {
    return `This action returns all products`;
  }

  findOne(id: number) {
    return `This action returns a #${id} product`;
  }

  update(id: number, updateProductDto: UpdateProductDto) {
    return `This action updates a #${id} product`;
  }

  remove(id: number) {
    return `This action removes a #${id} product`;
  }
}
```

### DTOs Generados

```typescript
// dto/create-product.dto.ts
export class CreateProductDto {}

// dto/update-product.dto.ts
import { PartialType } from '@nestjs/mapped-types';
import { CreateProductDto } from './create-product.dto';

export class UpdateProductDto extends PartialType(CreateProductDto) {}
```

**PartialType:** Hace todos los campos opcionales automáticamente

### Entity Generada

```typescript
// entities/product.entity.ts
export class Product {}
```

### Completar el CRUD

**1. Definir la Entity:**

```typescript
// entities/product.entity.ts
export class Product {
  id: number;
  name: string;
  price: number;
  description: string;
  inStock: boolean;
}
```

**2. Definir el CreateDTO:**

```typescript
// dto/create-product.dto.ts
import { IsString, IsNumber, IsBoolean, Min } from 'class-validator';

export class CreateProductDto {
  @IsString()
  name: string;

  @IsNumber()
  @Min(0)
  price: number;

  @IsString()
  description: string;

  @IsBoolean()
  inStock: boolean;
}
```

**3. Implementar el Servicio:**

```typescript
// products.service.ts
import { Injectable, NotFoundException } from '@nestjs/common';
import { CreateProductDto } from './dto/create-product.dto';
import { UpdateProductDto } from './dto/update-product.dto';
import { Product } from './entities/product.entity';

@Injectable()
export class ProductsService {
  private products: Product[] = [];
  private idCounter = 1;

  create(createProductDto: CreateProductDto): Product {
    const product: Product = {
      id: this.idCounter++,
      ...createProductDto,
    };
    this.products.push(product);
    return product;
  }

  findAll(): Product[] {
    return this.products;
  }

  findOne(id: number): Product {
    const product = this.products.find(p => p.id === id);
    if (!product) {
      throw new NotFoundException(`Product ${id} not found`);
    }
    return product;
  }

  update(id: number, updateProductDto: UpdateProductDto): Product {
    const product = this.findOne(id);
    Object.assign(product, updateProductDto);
    return product;
  }

  remove(id: number): void {
    const index = this.products.findIndex(p => p.id === id);
    if (index === -1) {
      throw new NotFoundException(`Product ${id} not found`);
    }
    this.products.splice(index, 1);
  }
}
```

### Generar Resource sin Tests

```bash
nest g resource products --no-spec
```

### Opciones de Resource

**GraphQL:**
```bash
nest g resource products
# Seleccionar: GraphQL (code first)
```

**Microservicios:**
```bash
nest g resource products
# Seleccionar: Microservice (non-HTTP)
```

**WebSockets:**
```bash
nest g resource products
# Seleccionar: WebSockets
```

### Probar el CRUD

```bash
# POST - Crear producto
POST http://localhost:3000/products
{
  "name": "Laptop",
  "price": 999.99,
  "description": "Gaming laptop",
  "inStock": true
}

# GET - Listar todos
GET http://localhost:3000/products

# GET - Obtener uno
GET http://localhost:3000/products/1

# PATCH - Actualizar
PATCH http://localhost:3000/products/1
{
  "price": 899.99
}

# DELETE - Eliminar
DELETE http://localhost:3000/products/1
```

### Buenas Prácticas

✅ **Usa `nest g resource` para CRUDs completos** - Ahorra tiempo
✅ **DTOs completos con validaciones** - Seguridad
✅ **Implementa la lógica real en los servicios** - No dejes cadenas de ejemplo
✅ **Añade manejo de errores** - NotFoundException, etc.
✅ **Documenta con Swagger** - Facilita el consumo de la API

---

## 14. Base de Datos

### Opciones de Base de Datos

NestJS soporta múltiples bases de datos:

**SQL:**
- PostgreSQL (con TypeORM, Prisma)
- MySQL (con TypeORM, Sequelize)
- SQLite (con TypeORM)

**NoSQL:**
- MongoDB (con Mongoose)
- Redis

### TypeORM con PostgreSQL

**1. Instalar dependencias:**

```bash
npm install @nestjs/typeorm typeorm pg
```

**2. Configurar en AppModule:**

```typescript
// app.module.ts
import { Module } from '@nestjs/common';
import { TypeOrmModule } from '@nestjs/typeorm';

@Module({
  imports: [
    TypeOrmModule.forRoot({
      type: 'postgres',
      host: 'localhost',
      port: 5432,
      username: 'postgres',
      password: 'password',
      database: 'nestjs_db',
      entities: [],
      synchronize: true, // Solo en desarrollo
    }),
  ],
})
export class AppModule {}
```

**3. Crear la Entity:**

```typescript
// users/entities/user.entity.ts
import { Entity, Column, PrimaryGeneratedColumn } from 'typeorm';

@Entity()
export class User {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  name: string;

  @Column({ unique: true })
  email: string;

  @Column()
  password: string;

  @Column({ default: true })
  isActive: boolean;

  @Column({ type: 'timestamp', default: () => 'CURRENT_TIMESTAMP' })
  createdAt: Date;
}
```

**4. Registrar la Entity en el módulo:**

```typescript
// users/users.module.ts
import { Module } from '@nestjs/common';
import { TypeOrmModule } from '@nestjs/typeorm';
import { User } from './entities/user.entity';
import { UsersService } from './users.service';
import { UsersController } from './users.controller';

@Module({
  imports: [TypeOrmModule.forFeature([User])],
  controllers: [UsersController],
  providers: [UsersService],
})
export class UsersModule {}
```

**5. Usar en el Servicio:**

```typescript
// users/users.service.ts
import { Injectable } from '@nestjs/common';
import { InjectRepository } from '@nestjs/typeorm';
import { Repository } from 'typeorm';
import { User } from './entities/user.entity';
import { CreateUserDto } from './dto/create-user.dto';

@Injectable()
export class UsersService {
  constructor(
    @InjectRepository(User)
    private usersRepository: Repository<User>,
  ) {}

  async create(createUserDto: CreateUserDto): Promise<User> {
    const user = this.usersRepository.create(createUserDto);
    return await this.usersRepository.save(user);
  }

  async findAll(): Promise<User[]> {
    return await this.usersRepository.find();
  }

  async findOne(id: number): Promise<User> {
    return await this.usersRepository.findOne({ where: { id } });
  }

  async update(id: number, updateUserDto: any): Promise<User> {
    await this.usersRepository.update(id, updateUserDto);
    return this.findOne(id);
  }

  async remove(id: number): Promise<void> {
    await this.usersRepository.delete(id);
  }
}
```

### Variables de Entorno

```bash
npm install @nestjs/config
```

**.env:**
```env
DB_TYPE=postgres
DB_HOST=localhost
DB_PORT=5432
DB_USERNAME=postgres
DB_PASSWORD=mypassword
DB_DATABASE=nestjs_db
```

**Configurar:**

```typescript
// app.module.ts
import { ConfigModule, ConfigService } from '@nestjs/config';

@Module({
  imports: [
    ConfigModule.forRoot({
      isGlobal: true,
    }),
    TypeOrmModule.forRootAsync({
      imports: [ConfigModule],
      useFactory: (configService: ConfigService) => ({
        type: configService.get('DB_TYPE') as any,
        host: configService.get('DB_HOST'),
        port: +configService.get('DB_PORT'),
        username: configService.get('DB_USERNAME'),
        password: configService.get('DB_PASSWORD'),
        database: configService.get('DB_DATABASE'),
        entities: [__dirname + '/**/*.entity{.ts,.js}'],
        synchronize: true,
      }),
      inject: [ConfigService],
    }),
  ],
})
export class AppModule {}
```

### Mongoose con MongoDB

**1. Instalar:**

```bash
npm install @nestjs/mongoose mongoose
```

**2. Configurar:**

```typescript
import { MongooseModule } from '@nestjs/mongoose';

@Module({
  imports: [
    MongooseModule.forRoot('mongodb://localhost/nestjs'),
  ],
})
export class AppModule {}
```

**3. Crear el Schema:**

```typescript
// users/schemas/user.schema.ts
import { Prop, Schema, SchemaFactory } from '@nestjs/mongoose';
import { Document } from 'mongoose';

@Schema()
export class User extends Document {
  @Prop({ required: true })
  name: string;

  @Prop({ required: true, unique: true })
  email: string;

  @Prop()
  password: string;

  @Prop({ default: Date.now })
  createdAt: Date;
}

export const UserSchema = SchemaFactory.createForClass(User);
```

**4. Registrar:**

```typescript
import { MongooseModule } from '@nestjs/mongoose';
import { User, UserSchema } from './schemas/user.schema';

@Module({
  imports: [
    MongooseModule.forFeature([{ name: User.name, schema: UserSchema }])
  ],
})
export class UsersModule {}
```

**5. Usar:**

```typescript
import { Model } from 'mongoose';
import { InjectModel } from '@nestjs/mongoose';

@Injectable()
export class UsersService {
  constructor(@InjectModel(User.name) private userModel: Model<User>) {}

  async create(createUserDto: CreateUserDto): Promise<User> {
    const user = new this.userModel(createUserDto);
    return user.save();
  }

  async findAll(): Promise<User[]> {
    return this.userModel.find().exec();
  }
}
```

### Relaciones en TypeORM

```typescript
// user.entity.ts
@Entity()
export class User {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  name: string;

  @OneToMany(() => Task, task => task.user)
  tasks: Task[];
}

// task.entity.ts
@Entity()
export class Task {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  title: string;

  @ManyToOne(() => User, user => user.tasks)
  user: User;
}
```

### Buenas Prácticas

✅ **Variables de entorno para las credenciales** - No las pongas fijas
✅ **synchronize: false en producción** - Usa migraciones
✅ **Valida los DTOs** - Antes de guardar en la BD
✅ **Maneja los errores de la BD** - try/catch en las operaciones
✅ **Índices en columnas frecuentes** - Optimiza las consultas

---

## 15. Swagger

### ¿Qué es Swagger?

Swagger (OpenAPI) genera documentación interactiva automática para tu API.

### Instalación

```bash
npm install @nestjs/swagger
```

### Configuración Básica

```typescript
// main.ts
import { NestFactory } from '@nestjs/core';
import { SwaggerModule, DocumentBuilder } from '@nestjs/swagger';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);

  const config = new DocumentBuilder()
    .setTitle('Tasks API')
    .setDescription('Task management API documentation')
    .setVersion('1.0')
    .addTag('tasks')
    .build();

  const document = SwaggerModule.createDocument(app, config);
  SwaggerModule.setup('api', app, document);

  await app.listen(3000);
}
bootstrap();
```

Visita: `http://localhost:3000/api`

### Documentar DTOs

```typescript
// dto/create-task.dto.ts
import { ApiProperty } from '@nestjs/swagger';
import { IsString, IsBoolean, IsOptional } from 'class-validator';

export class CreateTaskDto {
  @ApiProperty({
    description: 'Task title',
    example: 'Complete NestJS project',
  })
  @IsString()
  title: string;

  @ApiProperty({
    description: 'Detailed task description',
    example: 'Finish all course sections',
    required: false,
  })
  @IsString()
  @IsOptional()
  description?: string;

  @ApiProperty({
    description: 'Completion status',
    example: false,
    default: false,
  })
  @IsBoolean()
  @IsOptional()
  status?: boolean;
}
```

### Documentar Endpoints

```typescript
import { ApiTags, ApiOperation, ApiResponse } from '@nestjs/swagger';

@ApiTags('tasks')
@Controller('tasks')
export class TaskController {
  @Post()
  @ApiOperation({ summary: 'Create a new task' })
  @ApiResponse({ status: 201, description: 'Task created successfully' })
  @ApiResponse({ status: 400, description: 'Invalid data' })
  create(@Body() createTaskDto: CreateTaskDto) {
    return this.taskService.create(createTaskDto);
  }

  @Get()
  @ApiOperation({ summary: 'Get all tasks' })
  @ApiResponse({ status: 200, description: 'List of tasks' })
  findAll() {
    return this.taskService.findAll();
  }
}
```

### Autenticación en Swagger

```typescript
const config = new DocumentBuilder()
  .setTitle('Tasks API')
  .setDescription('API documentation')
  .setVersion('1.0')
  .addBearerAuth()
  .build();
```

```typescript
@ApiBearerAuth()
@Controller('tasks')
export class TaskController {}
```

### Buenas Prácticas

✅ **Documenta todos los endpoints** - Facilita la integración
✅ **Ejemplos en los DTOs** - Ayuda a entender el formato
✅ **Describe las respuestas** - Posibles estados HTTP
✅ **Agrupa con @ApiTags** - Organiza los endpoints

---

## 16. CORS

### ¿Qué es CORS?

CORS (Cross-Origin Resource Sharing) permite que las aplicaciones frontend de otros dominios accedan a tu API.

### Habilitar CORS

```typescript
// main.ts
async function bootstrap() {
  const app = await NestFactory.create(AppModule);

  app.enableCors(); // Habilitar CORS para todos los orígenes

  await app.listen(3000);
}
bootstrap();
```

### CORS con Configuración

```typescript
app.enableCors({
  origin: 'http://localhost:4200',
  methods: 'GET,HEAD,PUT,PATCH,POST,DELETE',
  credentials: true,
});
```

### Múltiples Orígenes

```typescript
app.enableCors({
  origin: ['http://localhost:4200', 'https://myapp.com'],
  credentials: true,
});
```

### CORS Dinámico

```typescript
app.enableCors({
  origin: (origin, callback) => {
    const allowedOrigins = ['http://localhost:4200', 'https://myapp.com'];
    if (!origin || allowedOrigins.includes(origin)) {
      callback(null, true);
    } else {
      callback(new Error('Not allowed by CORS'));
    }
  },
});
```

---

## 17. Despliegue

### Preparar para Producción

**1. Variables de entorno:**

```bash
# .env.production
NODE_ENV=production
PORT=3000
DB_HOST=production-db-host
```

**2. Build:**

```bash
npm run build
```

**3. Iniciar:**

```bash
npm run start:prod
```

### Desplegar en Heroku

```bash
# Instalar la CLI de Heroku
heroku login

# Crear la app
heroku create my-nestjs-api

# Añadir base de datos
heroku addons:create heroku-postgresql:hobby-dev

# Configurar variables
heroku config:set NODE_ENV=production

# Desplegar
git push heroku main
```

### Desplegar en Railway

1. Crea una cuenta en Railway.app
2. New Project → Deploy from GitHub
3. Selecciona el repositorio
4. Añade las variables de entorno
5. Despliegue automático

### Desplegar en Render

1. Crea una cuenta en Render.com
2. New → Web Service
3. Conecta el repositorio de GitHub
4. Build Command: `npm install && npm run build`
5. Start Command: `npm run start:prod`

### Docker

**Dockerfile (multi-etapa, no-root, instalación reproducible):**

```dockerfile
# --- Etapa de build ---
FROM node:22-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build && npm prune --omit=dev

# --- Etapa de runtime ---
FROM node:22-alpine
ENV NODE_ENV=production
WORKDIR /app
# Ejecutar como el usuario no-root 'node' integrado
COPY --from=builder --chown=node:node /app/node_modules ./node_modules
COPY --from=builder --chown=node:node /app/dist ./dist
COPY --from=builder --chown=node:node /app/package.json ./
USER node
EXPOSE 3000
CMD ["node", "dist/main.js"]
```

**docker-compose.yml:**

```yaml
services:
  app:
    build: .
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=production
      - DB_HOST=db
      # Lee los secretos de un archivo .env, nunca los pongas fijos
      - DB_PASSWORD=${DB_PASSWORD}
    depends_on:
      - db

  db:
    image: postgres:17-alpine
    environment:
      POSTGRES_PASSWORD: ${DB_PASSWORD}
      POSTGRES_DB: nestjs_db
    volumes:
      - pgdata:/var/lib/postgresql/data

volumes:
  pgdata:
```

```bash
docker compose up -d
```

### Buenas Prácticas

✅ **Usa variables de entorno** - Configuración flexible
✅ **Logs estructurados** - Para depuración en producción
✅ **Health checks** - Endpoint `/health`
✅ **Rate limiting** - Protege contra abusos
✅ **Helmet** - Cabeceras HTTP de seguridad
✅ **Compresión** - Reduce el tamaño de las respuestas

---

## 📚 Recursos Adicionales

### Documentación Oficial
- [NestJS Docs](https://docs.nestjs.com/)
- [TypeORM Docs](https://typeorm.io/)
- [Mongoose Docs](https://mongoosejs.com/)

### Comunidad
- [Discord NestJS](https://discord.gg/nestjs)
- [GitHub NestJS](https://github.com/nestjs/nest)

### Temas Relacionados
- Fundamentos de Node.js
- TypeScript
- PostgreSQL/MongoDB

---

## 🎯 Conceptos Clave para Agentes de IA

### Arquitectura de NestJS
- **Modules**: Agrupan funcionalidad relacionada
- **Controllers**: Manejan las peticiones HTTP
- **Services**: Contienen la lógica de negocio
- **Providers**: Inyección de dependencias
- **DTOs**: Validación y transformación de datos

### Flujo de una Petición
```
Request → Middleware → Guard → Interceptor → Pipe → Controller → Service → Repository → Database
```

### Decoradores Principales
- `@Module()` - Definir un módulo
- `@Controller()` - Definir un controlador
- `@Injectable()` - Definir un servicio/provider
- `@Get/@Post/@Put/@Patch/@Delete()` - Métodos HTTP
- `@Param/@Query/@Body()` - Extraer datos de la petición

### Comandos Esenciales de la CLI
```bash
nest new project                  # Crear proyecto
nest g module name               # Generar módulo
nest g controller name           # Generar controlador
nest g service name              # Generar servicio
nest g resource name             # Generar CRUD completo
```

---

## 🚀 Buenas Prácticas Modernas

### Recomendaciones de Gestor de Paquetes

**Recomendado:** Usa `pnpm` para mejor rendimiento y eficiencia de espacio en disco:

```bash
# Instalar pnpm globalmente
npm install -g pnpm

# Crear un nuevo proyecto NestJS con pnpm
pnpm create nest my-project

# O con la CLI de NestJS
nest new my-project
# Seleccionar: pnpm
```

**¿Por qué pnpm?**
- Tiempos de instalación más rápidos
- Uso de disco más eficiente (almacenamiento direccionable por contenido)
- Resolución de dependencias estricta (previene dependencias fantasma)
- Mejor soporte de monorepos

### Actualizaciones de la Configuración de TypeScript

Recomendaciones de `tsconfig.json` moderno para NestJS v10+:

```json
{
  "compilerOptions": {
    "target": "ES2022",
    "module": "Node16",
    "moduleResolution": "Node16",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "resolveJsonModule": true,
    "declaration": true,
    "removeComments": true,
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "allowSyntheticDefaultImports": true,
    "sourceMap": true,
    "outDir": "./dist",
    "baseUrl": "./",
    "incremental": true,
    "paths": {
      "@/*": ["src/*"]
    }
  }
}
```

### Integración Mejorada con Prisma (Preferido sobre TypeORM)

Para proyectos NestJS modernos, **Prisma** ahora se prefiere sobre TypeORM:

```bash
# Instalar Prisma
npm install @prisma/client
npm install -D prisma

# Inicializar Prisma
npx prisma init

# Generar el Prisma Client tras cambios en el schema
npx prisma generate

# Crear y aplicar migraciones
npx prisma migrate dev --name init
```

**¿Por qué Prisma?**
- Consultas a la base de datos con seguridad de tipos (type-safe)
- Mejor integración con TypeScript
- Sistema de migraciones moderno
- Excelente experiencia de desarrollo
- Desarrollo y comunidad activos

**Ejemplo:** Ver `/Users/sysadmin/Workspace/DevSonic/api.devsonic.cl/src/prisma.service.ts`

### Buenas Prácticas de Variables de Entorno

Usa `@nestjs/config` con validación:

```bash
npm install @nestjs/config class-validator class-transformer
```

```typescript
// config/env.validation.ts
import { plainToInstance } from 'class-transformer';
import { IsEnum, IsNumber, IsString, validateSync } from 'class-validator';

enum Environment {
  Development = 'development',
  Production = 'production',
  Test = 'test',
}

class EnvironmentVariables {
  @IsEnum(Environment)
  NODE_ENV: Environment;

  @IsNumber()
  PORT: number;

  @IsString()
  DATABASE_URL: string;
}

export function validate(config: Record<string, unknown>) {
  const validatedConfig = plainToInstance(EnvironmentVariables, config, {
    enableImplicitConversion: true,
  });

  const errors = validateSync(validatedConfig, { skipMissingProperties: false });

  if (errors.length > 0) {
    throw new Error(errors.toString());
  }
  return validatedConfig;
}
```

### Cabeceras de Seguridad con Helmet

```bash
npm install helmet
```

```typescript
// main.ts
import helmet from 'helmet';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  app.use(helmet());
  await app.listen(3000);
}
bootstrap();
```

### Rate Limiting

```bash
npm install @nestjs/throttler
```

```typescript
// app.module.ts
import { ThrottlerModule, ThrottlerGuard } from '@nestjs/throttler';
import { APP_GUARD } from '@nestjs/core';

@Module({
  imports: [
    ThrottlerModule.forRoot([{
      ttl: 60000,
      limit: 10,
    }]),
  ],
  providers: [
    {
      provide: APP_GUARD,
      useClass: ThrottlerGuard,
    },
  ],
})
export class AppModule {}
```

### Optimización de Rendimiento con Fastify

**Usa Fastify en lugar de Express para un rendimiento 2x mejor:**

```bash
npm install @nestjs/platform-fastify
```

```typescript
// main.ts
import { NestFactory } from '@nestjs/core';
import { FastifyAdapter, NestFastifyApplication } from '@nestjs/platform-fastify';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create<NestFastifyApplication>(
    AppModule,
    new FastifyAdapter(),
  );

  await app.listen(3000, '0.0.0.0');
}
bootstrap();
```

**Beneficios:**
- 2x más rápido que Express
- Mejor serialización JSON
- Menor huella de memoria
- Validación basada en schemas

### Build Multi-Etapa de Docker (Buenas Prácticas 2025)

```dockerfile
# Etapa 1: Build
FROM node:20-alpine AS builder

WORKDIR /app
COPY package*.json pnpm-lock.yaml ./
RUN npm install -g pnpm
RUN pnpm install --frozen-lockfile
COPY . .
RUN pnpm run build

# Etapa 2: Producción
FROM node:20-alpine

WORKDIR /app
COPY package*.json pnpm-lock.yaml ./
RUN npm install -g pnpm
RUN pnpm install --frozen-lockfile --prod
COPY --from=builder /app/dist ./dist

EXPOSE 3000
USER node

CMD ["node", "dist/main"]
```

### Versionado de la API

```typescript
// main.ts
import { VersioningType } from '@nestjs/common';

app.enableVersioning({
  type: VersioningType.URI,
  defaultVersion: '1',
});

// controller.ts
@Controller({ path: 'users', version: '1' })
export class UsersV1Controller {}

@Controller({ path: 'users', version: '2' })
export class UsersV2Controller {}
```

### Plataformas de Despliegue (Actualizado 2025)

**Plataformas Recomendadas:**

1. **Railway** - La más fácil para principiantes (auto-deploy, nivel gratuito)
2. **Fly.io** - Despliegue global en el edge
3. **Render** - HTTPS simple, PostgreSQL integrado
4. **AWS ECS/Fargate** - Producción empresarial
5. **Vercel** - NestJS serverless (solo APIs ligeras)

### Health Checks

```bash
npm install @nestjs/terminus
```

```typescript
// health.controller.ts
import { Controller, Get } from '@nestjs/common';
import { HealthCheck, HealthCheckService, PrismaHealthIndicator } from '@nestjs/terminus';

@Controller('health')
export class HealthController {
  constructor(
    private health: HealthCheckService,
    private db: PrismaHealthIndicator,
  ) {}

  @Get()
  @HealthCheck()
  check() {
    return this.health.check([
      () => this.db.pingCheck('database', this.prisma),
    ]);
  }
}
```

### Logging con Pino

```bash
npm install nestjs-pino pino-http
```

```typescript
// app.module.ts
import { LoggerModule } from 'nestjs-pino';

@Module({
  imports: [
    LoggerModule.forRoot({
      pinoHttp: {
        transport: {
          target: 'pino-pretty',
          options: { singleLine: true },
        },
      },
    }),
  ],
})
export class AppModule {}
```

---

## 📊 Notas del Documento

**Temas cubiertos:**
- Fundamentos de NestJS (módulos, controladores, servicios, DTOs, pipes, guards)
- Buenas prácticas modernas (Prisma como ORM preferido, pnpm, Fastify)
- Prácticas de seguridad (Helmet, rate limiting, CORS, config/secretos)
- Despliegue (builds multi-etapa de Docker, Railway, Fly.io, Render)
- Versionado de API, health checks, monitoreo y logging estructurado con Pino

---

**Última Actualización:** 2026-08-31
