# Docker - Plataforma de Contenerización

**Metadatos:**
- **Última Actualización:** 2026-08-31
- **Versión de Docker Cubierta:** 25.x+
- **Docker Compose:** v2 (integrado con la CLI de Docker)
- **Requisitos Previos:** Conocimientos básicos de línea de comandos, comprensión de conceptos de desarrollo de software
- **Nivel de Habilidad:** Principiante a Avanzado

---

## 🎯 Cuándo Usar Este Conocimiento

**Consulta esta guía cuando necesites:**

1. **Iniciar un Nuevo Proyecto:**
   - Configurar entornos de desarrollo contenerizados
   - Crear Dockerfiles para tu stack de aplicaciones
   - Configurar aplicaciones multi-contenedor con Docker Compose

2. **Solucionar Problemas:**
   - Problemas de red de contenedores (resolución DNS, conectividad)
   - Retos de montaje de volúmenes y persistencia de datos
   - Fallos de build u optimización de imágenes
   - Conflictos de puertos o problemas de exposición

3. **Despliegue en Producción:**
   - Escribir Dockerfiles listos para producción con buenas prácticas de seguridad
   - Implementar builds multi-etapa para reducir el tamaño de la imagen
   - Configurar la red correctamente (bridge, host, macvlan, ipvlan)
   - Configurar health checks y límites de recursos

4. **Colaboración en Equipo:**
   - Estandarizar entornos de desarrollo entre equipos
   - Crear procesos de build y despliegue reproducibles
   - Documentar la infraestructura como código

5. **Progresión del Camino de Aprendizaje:**
   - **Principiantes:** Empieza con las Secciones 1-9 (fundamentos, imágenes, contenedores, Dockerfile)
   - **Intermedio:** Continúa con las Secciones 10-13 (red, volúmenes, Compose)
   - **Avanzado:** Domina las Secciones 14-16 (apps multi-contenedor, buenas prácticas, producción)

**Navegación Rápida:**
- ¿Necesitas resolver problemas de red? → [Sección 10](#10-red-de-docker) y [Sección 11](#11-tipos-de-red)
- ¿Builds de imágenes lentos? → [Sección 9](#9-construcción-de-imágenes) y [Sección 16](#16-buenas-prácticas)
- ¿Configuración multi-contenedor? → [Sección 13](#13-docker-compose) y [Sección 14](#14-aplicaciones-multi-contenedor)
- ¿Preocupaciones de seguridad? → [Sección 16 - Buenas Prácticas de Seguridad](#16-buenas-prácticas)

---

## 📋 Tabla de Contenidos

1. [Introducción](#1-introducción)
2. [Instalación](#2-instalación)
3. [Conceptos Fundamentales](#3-conceptos-fundamentales)
4. [Imágenes](#4-imágenes)
5. [Contenedores](#5-contenedores)
6. [Mapeo de Puertos](#6-mapeo-de-puertos)
7. [Variables de Entorno](#7-variables-de-entorno)
8. [Dockerfile](#8-dockerfile)
9. [Construcción de Imágenes](#9-construcción-de-imágenes)
10. [Red de Docker](#10-red-de-docker)
11. [Tipos de Red](#11-tipos-de-red)
12. [Volúmenes y Persistencia de Datos](#12-volúmenes-y-persistencia-de-datos)
13. [Docker Compose](#13-docker-compose)
14. [Aplicaciones Multi-Contenedor](#14-aplicaciones-multi-contenedor)
15. [Entornos de Desarrollo](#15-entornos-de-desarrollo)
16. [Buenas Prácticas](#16-buenas-prácticas)
17. [Referencia de Comandos Comunes](#17-referencia-de-comandos-comunes)
18. [Resumen](#18-resumen)
19. [Recursos](#19-recursos)

---

## Descripción General

Docker es una plataforma de contenerización que permite a los desarrolladores empaquetar aplicaciones con todas sus dependencias en unidades estandarizadas llamadas contenedores. Estos contenedores pueden ejecutarse de forma consistente en distintos entornos, resolviendo el clásico problema de "funciona en mi máquina".

### ¿Qué es Docker?

- Plataforma de **código abierto** para desarrollar, distribuir y ejecutar aplicaciones
- **Tecnología de contenerización** que aísla las aplicaciones en contenedores ligeros
- **Entornos consistentes** desde el desarrollo hasta la producción
- **Uso eficiente de recursos** comparado con las máquinas virtuales tradicionales
- **Despliegue rápido** y escalabilidad

### Características Principales

- ✅ Aislamiento de aplicaciones en contenedores
- ✅ Ligero en comparación con las VMs (comparte el kernel del SO anfitrión)
- ✅ Portable entre distintos entornos
- ✅ Control de versiones para la infraestructura (Dockerfile)
- ✅ Tiempos de arranque rápidos (segundos vs minutos de las VMs)
- ✅ Escalado y orquestación sencillos
- ✅ Gran ecosistema con Docker Hub

### Docker vs Máquinas Virtuales

| Característica | Contenedores Docker | Máquinas Virtuales |
|---------|------------------|------------------|
| **SO** | Comparte el kernel del anfitrión | SO completo por VM |
| **Tamaño** | MBs | GBs |
| **Arranque** | Segundos | Minutos |
| **Rendimiento** | Nativo | Sobrecarga del hipervisor |
| **Aislamiento** | A nivel de proceso | A nivel de hardware |
| **Portabilidad** | Alta | Media |

---

## 1. Introducción

### ¿Por Qué Docker?

**Antes de Docker:**
- Síndrome de "funciona en mi máquina"
- Configuración compleja para nuevos miembros del equipo
- Entornos distintos (dev, staging, producción)
- Infierno de dependencias y conflictos de versiones
- Difícil replicar problemas de producción localmente

**Con Docker:**
- Entornos consistentes en todas partes
- Un comando para configurar el entorno de desarrollo
- Aislamiento de aplicaciones y dependencias
- Fácil de compartir y distribuir aplicaciones
- Pipelines de CI/CD simplificados

### Casos de Uso Clave

1. **Arquitectura de Microservicios** - Aislar cada servicio en su propio contenedor
2. **Entornos de Desarrollo** - Levantar rápidamente bases de datos, servicios, herramientas
3. **Pipelines de CI/CD** - Entornos de build y test consistentes
4. **Empaquetado de Aplicaciones** - Agrupar la app con todas sus dependencias
5. **Soporte de Aplicaciones Legadas** - Ejecutar apps antiguas en contenedores aislados

---

## 2. Instalación

### Instalando Docker

La instalación de Docker varía según el sistema operativo. El componente principal es **Docker Engine**.

#### Linux (Ubuntu/Debian)

```bash
# Actualizar el índice de paquetes
sudo apt-get update

# Instalar requisitos previos
sudo apt-get install ca-certificates curl gnupg lsb-release

# Añadir la clave GPG de Docker
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# Configurar el repositorio
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Instalar Docker Engine
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

# Verificar la instalación
sudo docker run hello-world
```

#### macOS

```bash
# Descargar Docker Desktop desde docker.com
# O usar Homebrew
brew install --cask docker

# Iniciar Docker Desktop
open -a Docker

# Verificar la instalación
docker --version
docker-compose --version
```

#### Windows

1. Descarga **Docker Desktop for Windows** desde docker.com
2. Instala y reinicia
3. Habilita el backend de WSL 2 (recomendado)
4. Verifica en PowerShell:

```powershell
docker --version
docker-compose --version
```

### Post-Instalación (Linux)

```bash
# Añadir el usuario al grupo docker (evitar usar sudo)
sudo usermod -aG docker $USER

# Cierra sesión y vuelve a entrar, luego verifica
docker run hello-world
```

### Verificando la Instalación

```bash
# Comprobar la versión de Docker
docker --version
# Esperado: Docker version 25.x.x (o superior)

# Comprobar la información de Docker
docker info

# Verificar que BuildKit está disponible
docker buildx version

# Comprobar Compose v2
docker compose version
# Esperado: Docker Compose version v2.x.x

# Ejecutar un contenedor de prueba
docker run hello-world
```

---

## 2.1 Alternativas a Docker Desktop

Para usuarios que buscan alternativas a Docker Desktop (por licencias, uso de recursos o preferencia):

### Rancher Desktop

**Alternativa gratuita y de código abierto a Docker Desktop con Kubernetes incluido.**

```bash
# Instalación en macOS
brew install --cask rancher

# Características:
# - Gratis para todos los usos (licencia Apache 2.0)
# - Kubernetes integrado (k3s)
# - Runtime dockerd o containerd
# - Funciona con la CLI de docker
# - Disponible en macOS, Windows, Linux
```

**Configuración:**
- UI para alternar entre dockerd y containerd
- Interruptor para habilitar/deshabilitar Kubernetes
- Controles de asignación de recursos

### Podman Desktop

**Motor de contenedores compatible con Docker, sin demonio (daemonless).**

```bash
# Instalación en macOS
brew install podman podman-desktop

# Iniciar la máquina de Podman (VM en macOS/Windows)
podman machine init
podman machine start

# Usar como Docker (CLI compatible)
podman run -d -p 8080:80 nginx
podman ps
podman images

# Crear un alias para compatibilidad con Docker
alias docker=podman
alias docker-compose=podman-compose

# Características:
# - Sin demonio (rootless por defecto)
# - CLI compatible con Docker
# - Soporte de pods (similar a Kubernetes)
# - Gratis para todos los usos
```

### Colima (macOS/Linux)

**Alternativa mínima a Docker Desktop usando Lima VM.**

```bash
# Instalación en macOS
brew install colima docker docker-compose

# Iniciar Colima
colima start

# Iniciar con recursos personalizados
colima start --cpu 4 --memory 8 --disk 100

# Usar los comandos estándar de docker
docker run hello-world
docker compose up

# Características:
# - Muy ligero
# - Arranque rápido
# - Soporte de Docker + containerd
# - Kubernetes opcional
# - Gratis y de código abierto
```

### OrbStack (macOS)

**Reemplazo rápido y ligero de Docker Desktop para macOS.**

```bash
# Instalación
brew install orbstack

# Características:
# - 2x más rápido que Docker Desktop
# - Integración nativa con macOS
# - Uso mínimo de recursos
# - Arranque instantáneo
# - VM de Linux incluida
# - Nivel gratuito disponible, Pro para funciones avanzadas
```

**Tabla Comparativa:**

| Característica | Docker Desktop | Rancher Desktop | Podman Desktop | Colima | OrbStack |
|---------|----------------|-----------------|----------------|---------|----------|
| **Licencia** | De pago (empresas) | Gratis (Apache 2.0) | Gratis (Apache 2.0) | Gratis (MIT) | Freemium |
| **Kubernetes** | Sí | Sí (k3s) | Sí | Opcional | Sí |
| **GUI** | Sí | Sí | Sí | No | Sí |
| **Uso de Recursos** | Alto | Medio | Bajo-Medio | Bajo | Muy Bajo |
| **Velocidad de Arranque** | Lento | Medio | Medio | Rápido | Muy Rápido |
| **Plataformas** | macOS, Win, Linux | macOS, Win, Linux | macOS, Win, Linux | macOS, Linux | Solo macOS |
| **Compatibilidad Docker** | Nativa | Total | Total | Total | Total |

---

## 3. Conceptos Fundamentales

### Imágenes

Las **Imágenes de Docker** son plantillas de solo lectura usadas para crear contenedores. Piénsalas como planos o instantáneas.

- **Sistema de archivos por capas** - Cada instrucción del Dockerfile crea una capa
- **Inmutables** - Una vez creadas, las imágenes no cambian
- **Almacenadas en registries** - Docker Hub, registries privados
- **Etiquetadas para el versionado** - `nginx:latest`, `node:22`, `postgres:17`

### Contenedores

Los **Contenedores de Docker** son instancias en ejecución de las imágenes. Son ligeros, portables y aislados.

- **Instancia en tiempo de ejecución** de una imagen
- **Entorno aislado** con su propio sistema de archivos, red y procesos
- **Efímeros por defecto** - Los datos se pierden cuando se elimina el contenedor
- **Se pueden iniciar, detener, eliminar**

### Dockerfile

Un **Dockerfile** es un archivo de texto con instrucciones para construir una imagen de Docker.

```dockerfile
FROM node:22
WORKDIR /app
COPY . .
RUN npm install
EXPOSE 3000
CMD ["node", "index.js"]
```

### Docker Registry

Un **Docker Registry** es un sistema de almacenamiento y distribución de imágenes de Docker.

- **Docker Hub** - Registry público (hub.docker.com)
- **Registries privados** - Autoalojados o en la nube
- **Push/Pull** - Subir y descargar imágenes

### Docker Compose

**Docker Compose** es una herramienta para definir y ejecutar aplicaciones multi-contenedor.

```yaml
services:
  app:
    image: node:22
    ports:
      - "3000:3000"
  db:
    image: postgres:17
    environment:
      POSTGRES_PASSWORD: secret
```

---

## 4. Imágenes

### Listando Imágenes

```bash
# Listar todas las imágenes
docker images

# Listar imágenes con información detallada
docker images -a

# Mostrar los tamaños de las imágenes
docker images --format "table {{.Repository}}\t{{.Tag}}\t{{.Size}}"
```

### Descargando Imágenes desde Docker Hub

```bash
# Descargar la última versión
docker pull nginx

# Descargar una versión específica
docker pull nginx:1.25

# Descargar desde un registry específico
docker pull mongo:7

# Revisa primero la imagen en Docker Hub
# https://hub.docker.com/_/nginx
```

### Buscando Imágenes

```bash
# Buscar en Docker Hub
docker search nginx

# Buscar con filtros
docker search --filter stars=100 nginx
```

### Eliminando Imágenes

```bash
# Eliminar una imagen específica
docker rmi nginx:latest

# Eliminar una imagen por ID
docker rmi abc123def456

# Forzar la eliminación (aunque exista un contenedor)
docker rmi -f nginx

# Eliminar todas las imágenes sin usar
docker image prune

# Eliminar todas las imágenes
docker image prune -a
```

### Capas de Imágenes y Caché

Las imágenes de Docker se construyen en capas:

```dockerfile
FROM node:22           # Capa 1
WORKDIR /app           # Capa 2
COPY package*.json ./  # Capa 3 (en caché si package.json no cambia)
RUN npm install        # Capa 4 (en caché si la Capa 3 no cambia)
COPY . .              # Capa 5 (los cambios de tu código)
CMD ["node", "app.js"] # Capa 6
```

**Puntos Clave:**
- Las capas se cachean para builds más rápidos
- El orden importa - pon las instrucciones que cambian con frecuencia al final
- Cada `RUN`, `COPY`, `ADD` crea una nueva capa

---

## 5. Contenedores

### Ciclo de Vida del Contenedor

```
┌─────────┐
│ Created │
└────┬────┘
     │ docker start
     ↓
┌─────────┐
│ Running │
└────┬────┘
     │ docker stop
     ↓
┌─────────┐
│ Stopped │
└────┬────┘
     │ docker rm
     ↓
┌─────────┐
│ Deleted │
└─────────┘
```

### Creando Contenedores

```bash
# Crear un contenedor (no lo inicia)
docker create nginx

# Crear con nombre
docker create --name my-nginx nginx

# Crear con mapeo de puertos
docker create -p 8080:80 nginx

# Crear con variables de entorno
docker create -e MYSQL_ROOT_PASSWORD=secret mysql
```

### Ejecutando Contenedores

```bash
# Ejecutar un contenedor (crear + iniciar)
docker run nginx

# Ejecutar en segundo plano (modo detached)
docker run -d nginx

# Ejecutar con nombre
docker run -d --name my-nginx nginx

# Ejecutar con mapeo de puertos
docker run -d -p 8080:80 nginx

# Ejecutar con terminal interactiva
docker run -it ubuntu bash

# Ejecutar y eliminar tras salir
docker run --rm nginx
```

### Iniciando y Deteniendo Contenedores

```bash
# Iniciar un contenedor detenido
docker start my-nginx

# Detener un contenedor en ejecución (graceful, espera 10s)
docker stop my-nginx

# Matar el contenedor inmediatamente
docker kill my-nginx

# Reiniciar un contenedor
docker restart my-nginx
```

### Listando Contenedores

```bash
# Listar contenedores en ejecución
docker ps

# Listar todos los contenedores (incluyendo detenidos)
docker ps -a

# Listar con un formato específico
docker ps --format "table {{.Names}}\t{{.Status}}\t{{.Ports}}"

# Listar solo los IDs de contenedor
docker ps -q
```

### Eliminando Contenedores

```bash
# Eliminar un contenedor detenido
docker rm my-nginx

# Forzar la eliminación de un contenedor en ejecución
docker rm -f my-nginx

# Eliminar todos los contenedores detenidos
docker container prune

# Eliminar contenedores específicos
docker rm container1 container2
```

### Inspeccionando Contenedores

```bash
# Ver los detalles del contenedor
docker inspect my-nginx

# Ver los logs
docker logs my-nginx

# Seguir los logs (en vivo)
docker logs -f my-nginx

# Mostrar las últimas 100 líneas
docker logs --tail 100 my-nginx

# Ver el uso de recursos
docker stats my-nginx

# Ver los procesos en ejecución
docker top my-nginx
```

### Ejecutando Comandos en Contenedores

```bash
# Ejecutar un comando en un contenedor en ejecución
docker exec my-nginx ls /usr/share/nginx/html

# Sesión interactiva de bash
docker exec -it my-nginx bash

# Ejecutar como un usuario específico
docker exec -u root my-nginx whoami

# Ejecutar con una variable de entorno
docker exec -e VAR=value my-nginx env
```

---

## 6. Mapeo de Puertos

### Entendiendo el Mapeo de Puertos

Los contenedores de Docker tienen su propio espacio de nombres de red. Para acceder a los servicios dentro de los contenedores, debes mapear los puertos del contenedor a los puertos del anfitrión.

```
Máquina Anfitriona (tu computadora)
├── Puerto 8080 ──────► Puerto 80 del Contenedor (nginx)
├── Puerto 3000 ──────► Puerto 3000 del Contenedor (app node)
└── Puerto 5432 ──────► Puerto 5432 del Contenedor (postgres)
```

### Sintaxis del Mapeo de Puertos

```bash
# Formato: -p PUERTO_ANFITRION:PUERTO_CONTENEDOR

# Mapear el puerto 8080 del anfitrión al puerto 80 del contenedor
docker run -d -p 8080:80 nginx
# Acceso: http://localhost:8080

# Mapear el puerto 3000 del anfitrión al puerto 3000 del contenedor
docker run -d -p 3000:3000 node-app

# Mapear todas las interfaces del anfitrión
docker run -d -p 0.0.0.0:8080:80 nginx

# Mapear a una IP específica del anfitrión
docker run -d -p 127.0.0.1:8080:80 nginx

# Dejar que Docker asigne un puerto aleatorio en el anfitrión
docker run -d -P nginx
# Usa 'docker ps' para ver el puerto asignado
```

### Mapeos de Puertos Múltiples

```bash
# Mapear varios puertos
docker run -d \
  -p 80:80 \
  -p 443:443 \
  nginx

# Ejemplo con una aplicación
docker run -d \
  -p 3000:3000 \
  -p 9229:9229 \
  --name my-app \
  node-app
```

### Viendo los Mapeos de Puertos

```bash
# Ver los mapeos de puertos en la salida de ps
docker ps

# Inspeccionar un contenedor específico
docker port my-nginx

# Inspección detallada
docker inspect my-nginx | grep -A 10 PortBindings
```

### Mapeos de Puertos Comunes por Servicio

| Servicio | Puerto del Contenedor | Puerto Común del Anfitrión |
|---------|----------------|------------------|
| **HTTP** | 80 | 8080, 80 |
| **HTTPS** | 443 | 8443, 443 |
| **Node.js** | 3000 | 3000 |
| **React Dev** | 3000 | 3000 |
| **Angular Dev** | 4200 | 4200 |
| **PostgreSQL** | 5432 | 5432 |
| **MySQL** | 3306 | 3306 |
| **MongoDB** | 27017 | 27017 |
| **Redis** | 6379 | 6379 |
| **Elasticsearch** | 9200 | 9200 |

---

## 7. Variables de Entorno

### Pasando Variables de Entorno

Las variables de entorno configuran las aplicaciones contenerizadas sin cambiar el código.

```bash
# Una sola variable
docker run -d -e MYSQL_ROOT_PASSWORD=secret mysql

# Varias variables
docker run -d \
  -e MYSQL_ROOT_PASSWORD=secret \
  -e MYSQL_DATABASE=mydb \
  -e MYSQL_USER=user \
  -e MYSQL_PASSWORD=pass \
  mysql

# Desde un archivo .env
docker run -d --env-file .env mysql
```

### Ejemplo de Archivo .env

```bash
# .env
MYSQL_ROOT_PASSWORD=secret
MYSQL_DATABASE=myapp
MYSQL_USER=appuser
MYSQL_PASSWORD=apppass
```

### Casos de Uso Comunes

#### Configuración de Base de Datos

```bash
# PostgreSQL
docker run -d \
  -e POSTGRES_PASSWORD=secret \
  -e POSTGRES_USER=admin \
  -e POSTGRES_DB=mydb \
  postgres:17

# MongoDB
docker run -d \
  -e MONGO_INITDB_ROOT_USERNAME=admin \
  -e MONGO_INITDB_ROOT_PASSWORD=secret \
  -e MONGO_INITDB_DATABASE=mydb \
  mongo:7
```

#### Configuración de la Aplicación

```bash
# App Node.js
docker run -d \
  -e NODE_ENV=production \
  -e DATABASE_URL=postgres://db:5432/mydb \
  -e API_KEY=secret123 \
  -e PORT=3000 \
  my-node-app
```

### Viendo las Variables de Entorno

```bash
# Ver todas las variables de entorno del contenedor
docker exec my-container env

# Ver una variable específica
docker exec my-container printenv DATABASE_URL

# Inspeccionar la configuración del contenedor
docker inspect my-container | grep -A 20 Env
```

---

## 8. Dockerfile

### Docker Init (Inicio Rápido para 2025)

**Docker Init** es un comando nuevo (Docker Desktop 4.18+) que genera automáticamente Dockerfiles y archivos de Compose para tu proyecto:

```bash
# Inicializar Docker para tu proyecto (interactivo)
docker init

# La herramienta:
# 1. Detecta el tipo de tu aplicación (Node.js, Python, Go, etc.)
# 2. Genera un Dockerfile optimizado
# 3. Genera un docker-compose.yml
# 4. Genera un .dockerignore
# 5. Añade un README con instrucciones de uso

# Ejemplo de salida:
# ? What application platform does your project use? Node
# ? What version of Node do you want to use? 20
# ? Which package manager do you want to use? npm
# ? Do you want to run "npm run build" to build your app? Yes
# ? What port does your server listen on? 3000

# Archivos creados:
# - Dockerfile (build multi-etapa optimizado)
# - compose.yaml
# - .dockerignore
# - README.Docker.md
```

**Ejemplo de Dockerfile Generado (Node.js):**
```dockerfile
# syntax=docker/dockerfile:1

# Build multi-etapa creado automáticamente
FROM node:20-alpine AS base
WORKDIR /usr/src/app

FROM base AS deps
COPY package*.json ./
RUN npm ci --only=production

FROM base AS build
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM base AS final
COPY --from=deps /usr/src/app/node_modules ./node_modules
COPY --from=build /usr/src/app/dist ./dist
EXPOSE 3000
CMD ["node", "dist/main.js"]
```

**Beneficios de Docker Init:**
- ✅ Buenas prácticas por defecto
- ✅ Builds multi-etapa incluidos
- ✅ Caché de capas optimizado
- ✅ .dockerignore adecuado
- ✅ Configuración lista para producción
- ✅ Ahorra horas de configuración manual

---

### Fundamentos del Dockerfile

Un **Dockerfile** es un script con instrucciones para construir una imagen de Docker.

### Instrucciones Comunes

| Instrucción | Descripción | Ejemplo |
|-------------|-------------|---------|
| **FROM** | Imagen base | `FROM node:22` |
| **WORKDIR** | Establecer el directorio de trabajo | `WORKDIR /app` |
| **COPY** | Copiar archivos del anfitrión al contenedor | `COPY . .` |
| **ADD** | Copiar y extraer archivos comprimidos | `ADD file.tar.gz /app` |
| **RUN** | Ejecutar comandos durante el build | `RUN npm install` |
| **ENV** | Establecer variables de entorno | `ENV NODE_ENV=production` |
| **EXPOSE** | Documentar el uso de puertos | `EXPOSE 3000` |
| **CMD** | Comando por defecto al iniciar el contenedor | `CMD ["node", "app.js"]` |
| **ENTRYPOINT** | Configurar el contenedor como ejecutable | `ENTRYPOINT ["npm", "start"]` |

### Ejemplo de Dockerfile Simple

```dockerfile
# Usar la imagen oficial de Node.js 18
FROM node:22

# Crear el directorio de la app
WORKDIR /app

# Copiar los archivos de paquetes
COPY package*.json ./

# Instalar dependencias
RUN npm install

# Copiar el código de la aplicación
COPY . .

# Exponer el puerto
EXPOSE 3000

# Iniciar la aplicación
CMD ["node", "index.js"]
```

### Ejemplo de Build Multi-Etapa

```dockerfile
# Etapa 1: Build
FROM node:22 AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Etapa 2: Producción
FROM node:22-alpine
WORKDIR /app
COPY --from=builder /app/dist ./dist
COPY --from=builder /app/node_modules ./node_modules
EXPOSE 3000
CMD ["node", "dist/main.js"]
```

### Dockerfile para Distintos Lenguajes

#### Aplicación Python

```dockerfile
FROM python:3.13-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
EXPOSE 8000
CMD ["python", "app.py"]
```

#### Aplicación Go

```dockerfile
FROM golang:1.23 AS builder
WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN CGO_ENABLED=0 GOOS=linux go build -o main .

FROM alpine:3.21
RUN apk --no-cache add ca-certificates
RUN addgroup -S app && adduser -S app -G app
WORKDIR /home/app
COPY --from=builder /app/main .
USER app
EXPOSE 8080
CMD ["./main"]
```

#### Java Spring Boot

```dockerfile
FROM maven:3.9-eclipse-temurin-17 AS builder
WORKDIR /app
COPY pom.xml .
RUN mvn dependency:go-offline
COPY src ./src
RUN mvn package -DskipTests

FROM eclipse-temurin:17-jre
WORKDIR /app
COPY --from=builder /app/target/*.jar app.jar
EXPOSE 8080
CMD ["java", "-jar", "app.jar"]
```

### Buenas Prácticas para el Dockerfile

1. **Usa tags de imagen específicos** (no `latest`) — y prefiere digests para inmutabilidad
```dockerfile
FROM node:22.11.0-alpine          # ✅ Bien (versión fijada)
FROM node:22-alpine@sha256:...    # ✅ Mejor (fijada por digest)
FROM node:latest                  # ❌ Evitar (no reproducible)
```

2. **Minimiza las capas** (combina los comandos RUN)
```dockerfile
RUN apt-get update && \
    apt-get install -y curl && \
    apt-get clean
```

3. **Aprovecha la caché del build** (el orden importa)
```dockerfile
# Copiar package.json primero (cambia con menos frecuencia)
COPY package*.json ./
RUN npm install

# Copiar el código fuente al final (cambia con frecuencia)
COPY . .
```

4. **Usa .dockerignore**
```
node_modules
.git
.env
*.log
dist
```

5. **No ejecutes como root**
```dockerfile
FROM node:22-alpine
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser
WORKDIR /app
COPY --chown=appuser:appgroup . .
CMD ["node", "app.js"]
```

---

## 9. Construcción de Imágenes

### Construyendo desde un Dockerfile

**BuildKit (Por Defecto en Docker 23.0+):**

Docker ahora usa BuildKit por defecto, que proporciona builds más rápidos, mejor caché y funciones avanzadas. BuildKit se habilita automáticamente en Docker Desktop y Docker Engine 23.0+.

```bash
# BuildKit es ahora el builder por defecto - ¡no se necesitan flags especiales!
docker build -t my-app:1.0 .

# Build con tag
docker build -t my-app:1.0 .

# Build con nombre y tag latest
docker build -t my-app:latest .
docker build -t my-app .  # Implica :latest

# Build con varios tags
docker build -t my-app:1.0 -t my-app:latest .

# Build desde un Dockerfile específico
docker build -f Dockerfile.dev -t my-app:dev .

# Build con argumentos de build
docker build --build-arg NODE_VERSION=18 -t my-app .

# Habilitar BuildKit explícitamente (versiones antiguas de Docker)
DOCKER_BUILDKIT=1 docker build -t my-app .
```

**Funciones Avanzadas de BuildKit:**

```bash
# Mostrar la salida detallada del build
docker build --progress=plain -t my-app .

# Usar caché inline para builds de CI/CD más rápidos
docker build --cache-from my-app:latest -t my-app:latest .

# Build con secretos (seguro, no incrustado en la imagen)
docker build --secret id=github_token,src=$HOME/.github/token -t my-app .

# Reenvío del agente SSH (para repos privados)
docker build --ssh default -t my-app .

# Builds multi-plataforma (ARM64 + AMD64)
docker buildx build --platform linux/amd64,linux/arm64 -t my-app:latest .
```

**Docker Buildx (Builds Multi-Plataforma):**

Buildx extiende el build de Docker con todas las capacidades de BuildKit, especialmente el soporte multi-plataforma:

```bash
# Crear una nueva instancia de builder (configuración única)
docker buildx create --name multiplatform --use
docker buildx inspect --bootstrap

# Build para varias arquitecturas
docker buildx build \
  --platform linux/amd64,linux/arm64,linux/arm/v7 \
  -t username/my-app:latest \
  --push \
  .

# Build y cargar en el Docker local (solo una plataforma)
docker buildx build --platform linux/amd64 -t my-app:latest --load .

# Ver las plataformas disponibles
docker buildx ls
```

### Usando Argumentos de Build

**Dockerfile:**
```dockerfile
ARG NODE_VERSION=18
FROM node:${NODE_VERSION}

ARG APP_PORT=3000
ENV PORT=${APP_PORT}

WORKDIR /app
COPY . .
EXPOSE ${APP_PORT}
CMD ["node", "app.js"]
```

**Comando de build:**
```bash
docker build \
  --build-arg NODE_VERSION=20 \
  --build-arg APP_PORT=8080 \
  -t my-app .
```

### Contexto de Build

El contexto de build es el conjunto de archivos que se envían al demonio de Docker.

```bash
# Directorio actual como contexto
docker build -t my-app .

# Directorio específico
docker build -t my-app /path/to/app

# Repositorio Git remoto
docker build -t my-app github.com/user/repo

# Tarball
docker build -t my-app http://example.com/app.tar.gz
```

### Archivo .dockerignore

Excluir archivos del contexto de build:

```
# .dockerignore
node_modules
npm-debug.log
.git
.gitignore
README.md
.env
.env.local
dist
build
coverage
.DS_Store
*.log
```

### Viendo el Historial del Build

```bash
# Ver las capas de la imagen
docker history my-app:latest

# Vista detallada
docker history --no-trunc my-app:latest
```

### Etiquetando Imágenes

```bash
# Etiquetar una imagen existente
docker tag my-app:latest my-app:1.0.0

# Etiquetar para un registry
docker tag my-app:latest username/my-app:latest

# Etiquetar para un registry privado
docker tag my-app:latest registry.example.com/my-app:latest
```

### Enviando (Push) al Registry

```bash
# Iniciar sesión en Docker Hub
docker login

# Enviar la imagen
docker push username/my-app:latest

# Enviar un tag específico
docker push username/my-app:1.0.0

# Enviar a un registry privado
docker push registry.example.com/my-app:latest
```

---

## 10. Red de Docker

### Fundamentos de Red

Los contenedores de Docker pueden comunicarse entre sí a través de redes. Por defecto, los contenedores están aislados.

**Conceptos Clave:**
- Los contenedores en la misma red pueden comunicarse
- Los contenedores pueden resolverse entre sí por nombre de contenedor (DNS)
- Múltiples redes proporcionan aislamiento
- Las redes se pueden crear, conectar y desconectar dinámicamente

### Red Bridge por Defecto

Cuando ejecutas un contenedor sin especificar una red, se conecta a la red `bridge` por defecto.

```bash
# Ejecutar un contenedor en el bridge por defecto
docker run -d --name nginx1 nginx

# Los contenedores en el bridge por defecto NO pueden usar nombres de contenedor
# Deben usar direcciones IP para comunicarse
```

#### Cómo Funciona el Bridge por Defecto Internamente

Cuando se instala Docker, este crea una interfaz de bridge virtual llamada `docker0`:

```bash
# Ver la interfaz docker0 (creada automáticamente al instalar Docker)
ip addr show docker0
# Muestra: docker0 con IP 172.17.0.1/16 (gateway por defecto de los contenedores)

# Ver las conexiones del bridge
bridge link
```

**Pares de Ethernet Virtual (veth):**
- Cada despliegue de contenedor crea un par de interfaces de ethernet virtual (par veth)
- Un extremo se conecta a la interfaz `eth0` del contenedor
- El otro extremo se conecta al bridge `docker0` en el anfitrión
- Actúa como un cable de red virtual entre el contenedor y el switch bridge
- El bridge `docker0` actúa como un switch virtual que conecta todos los contenedores por defecto

```bash
# Ver los pares veth en el anfitrión tras desplegar contenedores
ip link show | grep veth

# Ver qué interfaces veth están conectadas a docker0
bridge link
```

**Cómo Obtienen IP los Contenedores (DHCP Integrado):**
- Docker ejecuta su propio servicio DHCP interno
- Asigna automáticamente IPs de la subred del bridge (por defecto: `172.17.0.0/16`)
- `docker0` obtiene `172.17.0.1` (actúa como gateway)
- El primer contenedor normalmente obtiene `172.17.0.2`, luego `.3`, `.4`, etc.

**NAT para Acceso a Internet:**
- El bridge `docker0` actúa como gateway NAT para el tráfico saliente
- La ruta por defecto de los contenedores apunta a `docker0` (172.17.0.1)
- El tráfico saliente se traduce para aparecer con la dirección IP del anfitrión
- Usa reglas NAT de iptables por detrás

**Resolución DNS:**
- Docker copia el `/etc/resolv.conf` del anfitrión en cada contenedor
- Los contenedores usan los mismos servidores DNS que el anfitrión
- El DNS por nombre de contenedor NO funciona en el bridge por defecto (solo comunicación por IP)

**Requisito de Exposición de Puertos:**
- Los puertos del contenedor están aislados por defecto — el acceso externo requiere el flag `-p`
- `-p 8080:80` mapea el puerto 8080 del anfitrión al puerto 80 del contenedor vía reglas de iptables
- Sin `-p`, los servicios dentro de los contenedores no pueden alcanzarse desde fuera

**Limitaciones:**
- ❌ No hay resolución DNS automática por nombre de contenedor (hay que usar IPs)
- ❌ Hay que usar las direcciones IP del contenedor para comunicarse entre contenedores
- ❌ Todos los contenedores en el bridge por defecto pueden verse entre sí (sin aislamiento de apps)
- ✅ Puede acceder a la red externa vía NAT
- ✅ Asignación automática de IP desde el DHCP interno de Docker

### Comandos de Red

```bash
# Listar redes
docker network ls

# Inspeccionar una red
docker network inspect bridge

# Crear una red
docker network create my-network

# Eliminar una red
docker network rm my-network

# Eliminar redes sin usar
docker network prune

# Conectar un contenedor a una red
docker network connect my-network my-container

# Desconectar un contenedor de una red
docker network disconnect my-network my-container
```

### Creando Redes Personalizadas

```bash
# Crear una red bridge definida por el usuario
docker network create my-app-network

# Crear con subred
docker network create --subnet=172.20.0.0/16 my-network

# Crear con gateway
docker network create \
  --subnet=172.20.0.0/16 \
  --gateway=172.20.0.1 \
  my-network

# Crear con driver
docker network create --driver bridge my-network
```

### Conectando Contenedores

```bash
# Ejecutar contenedores en la misma red
docker run -d --name db --network my-app-network postgres
docker run -d --name api --network my-app-network my-api

# Dentro del contenedor 'api', se puede conectar a 'db' usando:
# postgresql://db:5432/mydb
# El hostname 'db' resuelve a la IP del contenedor
```

### Ejemplo de Red: Node.js + MongoDB

```bash
# 1. Crear la red
docker network create my-network

# 2. Ejecutar MongoDB
docker run -d \
  --name mongodb \
  --network my-network \
  -e MONGO_INITDB_ROOT_USERNAME=admin \
  -e MONGO_INITDB_ROOT_PASSWORD=secret \
  mongo:7

# 3. Ejecutar la app Node.js
docker run -d \
  --name node-app \
  --network my-network \
  -p 3000:3000 \
  -e MONGO_URL=mongodb://admin:secret@mongodb:27017 \
  my-node-app

# Dentro de node-app, MongoDB es accesible en 'mongodb:27017'
```

### Alias de Red

```bash
# Ejecutar un contenedor con alias de red
docker run -d \
  --name db1 \
  --network my-network \
  --network-alias database \
  postgres

# Otros contenedores pueden alcanzarlo vía el hostname 'database'
```

### Inspeccionando las Redes de un Contenedor

```bash
# Ver la configuración de red del contenedor
docker inspect my-container | grep -A 20 Networks

# Obtener la dirección IP del contenedor
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' my-container

# Ver todos los contenedores de una red
docker network inspect my-network
```

---

## 11. Tipos de Red

Docker soporta 7 tipos de driver de red, cada uno con casos de uso específicos.

### 1. Red Bridge (Por Defecto)

**Red por defecto** para los contenedores. Proporciona aislamiento y resolución DNS.

```bash
# Crear una red bridge
docker network create --driver bridge my-bridge

# Ejecutar contenedores
docker run -d --name c1 --network my-bridge nginx
docker run -d --name c2 --network my-bridge nginx

# c1 puede hacer ping a c2 por nombre
docker exec c1 ping c2
```

**Casos de Uso:**
- ✅ Varios contenedores en un solo anfitrión
- ✅ Comunicación contenedor a contenedor
- ✅ Entornos de desarrollo

**Características:**
- Aislado de la red del anfitrión
- Resolución DNS automática entre contenedores
- NAT para acceder a redes externas

### 2. Red Bridge Definida por el Usuario

**Redes bridge personalizadas** con mejor aislamiento y funciones. Docker recomienda oficialmente usar bridges definidos por el usuario en lugar del bridge por defecto para todas las cargas de trabajo de producción.

```bash
# Crear un bridge personalizado
docker network create --driver bridge app-network

# Desplegar contenedores en la red personalizada
docker run -d --name db --network app-network postgres:17
docker run -d --name api --network app-network my-api

# Los contenedores pueden alcanzarse entre sí por nombre
docker exec api ping db  # ✅ ¡Funciona! DNS resuelve 'db' automáticamente
```

**Cómo Funciona el DNS en los Bridges Definidos por el Usuario:**
- Docker ejecuta un servidor DNS integrado (`127.0.0.11`) dentro de cada contenedor
- Los nombres de contenedor se registran automáticamente como entradas DNS
- Ejemplo: un contenedor llamado `db` puede alcanzarse en `db:5432` desde cualquier contenedor de la misma red
- Esto es crítico porque las direcciones IP de los contenedores cambian al redesplegar

**Aislamiento de Red Entre Bridges:**
- Los contenedores en distintos bridges definidos por el usuario NO pueden comunicarse
- El bridge por defecto y los bridges personalizados están totalmente aislados entre sí
- Esto proporciona aislamiento de seguridad entre distintas aplicaciones/stacks

**Ventajas sobre el Bridge por Defecto:**
- ✅ Resolución DNS automática por nombre de contenedor (servidor DNS integrado)
- ✅ Mejor aislamiento entre aplicaciones (los bridges no se ven entre sí)
- ✅ Configurable (subred, gateway, rango de IP)
- ✅ Se pueden conectar/desconectar contenedores sin reiniciar
- ✅ El DNS por nombre de contenedor sobrevive a los redespliegues (las IPs pueden cambiar, los nombres no)

### 3. Red Host

**Elimina el aislamiento de red** - el contenedor usa la red del anfitrión directamente. El contenedor esencialmente se ejecuta como una aplicación nativa en el anfitrión.

```bash
# Ejecutar un contenedor con red host
docker run -d --network host nginx

# No se necesita mapeo de puertos (-p se ignora)
# El contenedor se enlaza directamente a los puertos del anfitrión
# Acceso directo en http://<host-ip>:80
```

**Cómo Funciona:**
- El contenedor comparte todo el espacio de nombres de red del anfitrión
- No hay bridge `docker0` involucrado, no se crean pares veth
- El contenedor ve todas las interfaces de red del anfitrión (`ip addr show` dentro del contenedor coincide con el anfitrión)
- Se enlaza directamente a los puertos del anfitrión (sin mapeo de puertos, sin NAT)
- El contenedor es esencialmente un proceso normal en el anfitrión desde el punto de vista de la red

**Casos de Uso:**
- ✅ Máximo rendimiento de red (sin sobrecarga de NAT)
- ✅ Contenedores que necesitan manejar muchos puertos dinámicamente
- ✅ Herramientas de monitoreo de red (necesitan acceso a todas las interfaces)
- ✅ **Contenedores VPN (p. ej. WireGuard)** — necesitan crear interfaces de red y acceder a la tabla de rutas del anfitrión
- ✅ Aplicaciones que necesitan acceso a raw sockets

```bash
# Ejemplo: VPN WireGuard con red host
docker run -d \
  --name wireguard \
  --network host \
  --cap-add NET_ADMIN \
  --cap-add SYS_MODULE \
  wireguard-image
```

**Limitaciones:**
- ❌ Sin aislamiento de red (el contenedor comparte por completo la red del anfitrión)
- ❌ Conflictos de puertos con los servicios del anfitrión (mismo espacio de puertos)
- ❌ Menos portable (fuertemente acoplado al anfitrión)
- ❌ Solo funciona en Linux (no en Docker Desktop de macOS/Windows)

### 4. Red None

**Sin red** - contenedor completamente aislado. La opción de red más segura.

```bash
# Ejecutar un contenedor sin red
docker run -d --network none alpine sleep 1000

# El contenedor SOLO tiene loopback — sin eth0, sin acceso externo
docker exec <container> ip addr show
# Solo se muestra lo (127.0.0.1) — nada más
```

**Casos de Uso:**
- ✅ Máximo aislamiento para cargas de trabajo sensibles a la seguridad
- ✅ Trabajos de procesamiento por lotes que no necesitan red
- ✅ Contenedores de procesamiento de datos que solo usan volúmenes para E/S
- ✅ Probar el comportamiento de un contenedor sin dependencias de red

### 5. Red Macvlan

**Asigna una dirección MAC única** a cada contenedor - aparece como un dispositivo físico en la red. Los contenedores se conectan directamente a la red física, evitando por completo la red de Docker.

#### Modo Bridge (Por Defecto)

```bash
# Crear una red macvlan (modo bridge)
docker network create -d macvlan \
  --subnet=192.168.1.0/24 \
  --gateway=192.168.1.1 \
  -o parent=eth0 \
  my-macvlan

# Ejecutar un contenedor con IP específica (recomendado)
docker run -d \
  --network my-macvlan \
  --ip=192.168.1.100 \
  --name web \
  nginx

# ¡El contenedor está ahora directamente en tu red física!
# Acceso en http://192.168.1.100 — no se necesita exposición de puertos
```

#### Requisito del Modo Promiscuo

Cada contenedor obtiene su propia dirección MAC, pero las interfaces de red normalmente solo aceptan tráfico para su propia MAC. El modo promiscuo permite que la NIC acepte tráfico para múltiples MACs.

```bash
# Habilitar el modo promiscuo en la NIC del anfitrión
sudo ip link set eth0 promisc on

# Verificar que el modo promiscuo está habilitado
ip link show eth0 | grep PROMISC
```

**Dónde debe habilitarse el modo promiscuo:**
- Interfaz de red del anfitrión (comando de Linux de arriba)
- Hipervisor de máquina virtual (VirtualBox: Settings > Network > Advanced > Allow All)
- Switch de red físico (la seguridad del puerto debe permitir múltiples MACs)
- Algunos proveedores de nube (AWS, Azure) lo bloquean por completo

#### Gestión de Direcciones IP

**Docker NO usa el DHCP de tu router para los contenedores macvlan.** Esto es un problema crítico a tener en cuenta:

- Si no especificas `--ip`, Docker asigna desde su propio DHCP interno (p. ej. `.2`, `.3`)
- Esto puede entrar en conflicto con las asignaciones DHCP de tu router
- **Buena práctica:** Especifica siempre `--ip` manualmente, o usa `--ip-range` para reservar un bloque

```bash
# Reservar un rango de IP para Docker (evita conflictos con el DHCP)
docker network create -d macvlan \
  --subnet=192.168.1.0/24 \
  --gateway=192.168.1.1 \
  --ip-range=192.168.1.192/27 \
  -o parent=eth0 \
  my-macvlan
```

#### Modo Trunk 802.1Q (Etiquetado VLAN)

Macvlan soporta el etiquetado VLAN vía sub-interfaces, permitiendo colocar los contenedores en distintas VLANs:

```bash
# Crear macvlan en la VLAN 20 (Docker crea automáticamente la sub-interfaz eth0.20)
docker network create -d macvlan \
  --subnet=192.168.20.0/24 \
  --gateway=192.168.20.1 \
  -o parent=eth0.20 \
  macvlan-vlan20

# Crear macvlan en la VLAN 30
docker network create -d macvlan \
  --subnet=192.168.30.0/24 \
  --gateway=192.168.30.1 \
  -o parent=eth0.30 \
  macvlan-vlan30

# Los contenedores en distintas VLANs están aislados en la Capa 2
# Requiere configuración de puerto trunk en el switch físico
```

**Casos de Uso:**
- ✅ Aplicaciones legadas que esperan acceso directo a la red
- ✅ Aplicaciones de monitoreo de red (necesitan direcciones MAC reales)
- ✅ Contenedores que necesitan aparecer como dispositivos físicos en la red
- ✅ Entornos multi-tenant con aislamiento VLAN (modo 802.1Q)
- ✅ No se necesita exposición de puertos — los contenedores tienen su propia IP en la red física

**Limitaciones:**
- ❌ Requiere modo promiscuo (bloqueado en muchos entornos de nube)
- ❌ Sin DHCP del router (hay que gestionar las IPs manualmente)
- ❌ El anfitrión NO puede comunicarse directamente con sus propios contenedores macvlan
- ❌ Límites de la tabla de direcciones MAC en los switches (puede agotar la tabla CAM)
- ❌ Configuración compleja comparada con las redes bridge

### 6. Red IPvlan L2

**Modo Capa 2** - similar a macvlan pero todos los contenedores **comparten la dirección MAC del anfitrión**. Esto resuelve el mayor problema de macvlan: el modo promiscuo.

**Diferencia Clave con Macvlan:**
- Macvlan: cada contenedor obtiene una dirección MAC única (requiere modo promiscuo)
- IPvlan L2: todos los contenedores comparten la dirección MAC del anfitrión (no se necesita modo promiscuo)
- Cada contenedor sigue obteniendo su propia dirección IP única en la red física

```bash
# Crear una red ipvlan L2 (L2 es el modo por defecto)
docker network create -d ipvlan \
  --subnet=192.168.1.0/24 \
  --gateway=192.168.1.1 \
  -o parent=eth0 \
  -o ipvlan_mode=l2 \
  my-ipvlan-l2

# Ejecutar un contenedor (igual que el uso de macvlan)
docker run -d \
  --network my-ipvlan-l2 \
  --ip=192.168.1.100 \
  --name web \
  nginx

# Verificar: la MAC del contenedor coincide con la MAC del anfitrión
# En el anfitrión: ip link show eth0
# En el contenedor: ip link show eth0
# Ambos muestran la misma dirección MAC
```

**Ventajas sobre Macvlan:**
- ✅ No requiere modo promiscuo (una sola dirección MAC)
- ✅ Funciona en entornos con filtrado MAC estricto
- ✅ Mejor para entornos de nube (AWS, Azure, GCP)
- ✅ Reduce el uso de la tabla MAC/CAM del switch
- ✅ Los mismos beneficios de conectividad que macvlan

**Casos de Uso:**
- ✅ Cuando macvlan no está soportado (límites de direcciones MAC en los switches)
- ✅ Los mismos casos de uso que macvlan pero con restricciones de MAC
- ✅ Mejor para entornos con filtrado MAC estricto o seguridad de puertos

**Aún Requiere:**
- ❌ Gestión manual de IP (sin DHCP del router, el mismo problema que macvlan)
- ❌ El anfitrión no puede alcanzar los contenedores directamente

### 7. Red IPvlan L3

**Modo Capa 3** - el anfitrión actúa como **router** para las redes de contenedores. Enrutamiento IP puro sin tráfico ARP ni broadcast. Esto es el sueño de un fanático de las redes.

**Cómo se Diferencia IPvlan L3:**
- Solo Capa 3: sin ARP, sin broadcast, sin multicast
- El anfitrión funciona como router entre las subredes de contenedores
- Múltiples subredes pueden compartir una sola interfaz padre
- El gateway del contenedor es automáticamente la interfaz padre (no se necesita `--gateway`)
- Los contenedores en distintas subredes sobre el mismo padre SÍ pueden comunicarse (el anfitrión enruta entre ellos)

#### Subred Única (Básico)

```bash
# Crear una red ipvlan L3 (no se necesita --gateway, el anfitrión es el gateway)
docker network create -d ipvlan \
  --subnet=192.168.94.0/24 \
  -o parent=eth0 \
  -o ipvlan_mode=l3 \
  my-ipvlan-l3

docker run -d --network my-ipvlan-l3 --ip=192.168.94.7 --name app1 busybox
docker run -d --network my-ipvlan-l3 --ip=192.168.94.8 --name app2 busybox

# Los contenedores pueden alcanzarse vía enrutamiento L3
docker exec app1 ping app2  # ✅ Funciona
```

#### Subredes Múltiples (Avanzado)

Puedes definir varias subredes en una sola creación de red — comparten la misma interfaz padre:

```bash
# Crear una red con DOS subredes en el mismo padre
docker network create -d ipvlan \
  --subnet=192.168.94.0/24 \
  --subnet=192.168.95.0/24 \
  -o parent=eth0 \
  -o ipvlan_mode=l3 \
  multi-l3-network

# Contenedor en la subred 94
docker run -d --network multi-l3-network --ip=192.168.94.7 --name thor busybox

# Contenedor en la subred 95
docker run -d --network multi-l3-network --ip=192.168.95.7 --name loki busybox

# ¡La comunicación entre subredes funciona! El anfitrión enruta entre ellas
docker exec thor ping 192.168.95.7  # ✅ Funciona
```

#### El Acceso Externo Requiere Rutas Estáticas

Por defecto, los contenedores en redes IPvlan L3 **no pueden alcanzar internet ni ser alcanzados desde dispositivos externos**. Las subredes de contenedores son totalmente nuevas — tu red no sabe cómo enrutar hacia ellas.

**Para habilitar el acceso externo, añade rutas estáticas en tu router/gateway:**

```bash
# En el router de tu red, añade rutas apuntando a la IP del anfitrión de Docker:
# Ruta a 192.168.94.0/24 vía <docker-host-ip>
# Ruta a 192.168.95.0/24 vía <docker-host-ip>

# Ejemplo (varía según el router):
ip route add 192.168.94.0/24 via 10.7.1.50   # IP del anfitrión de Docker
ip route add 192.168.95.0/24 via 10.7.1.50

# Tras añadir las rutas: los contenedores pueden alcanzar internet Y
# los dispositivos externos pueden alcanzar los contenedores
```

**Casos de Uso:**
- ✅ Escenarios multi-subred (redes separadas por servicio/equipo)
- ✅ Requisitos de enrutamiento avanzado (topologías de red complejas)
- ✅ Redes de alto rendimiento (sin sobrecarga de broadcast/ARP)
- ✅ Verdadero aislamiento de red en la Capa 3 (fronteras de seguridad)
- ✅ Buena práctica para aislar distintas aplicaciones vía enrutamiento

**Ventajas:**
- ✅ Sin tráfico ARP/broadcast (red más limpia y eficiente)
- ✅ Múltiples subredes en una sola interfaz padre
- ✅ El anfitrión actúa como router (control L3 completo)
- ✅ Funciona bien con protocolos de enrutamiento y políticas de red

**Limitaciones:**
- ❌ Requiere configuración del router para el acceso externo (rutas estáticas)
- ❌ Sin DHCP (asignación manual de IP)
- ❌ Configuración más compleja que las redes bridge
- ❌ Distintas subredes que comparten el mismo padre SÍ pueden alcanzarse (para aislarlas, usa distintas interfaces padre)

### 8. Red Overlay (Docker Swarm)

**Para la comunicación de contenedores multi-anfitrión** - se usa con la orquestación de Docker Swarm cuando los contenedores están repartidos entre varios anfitriones físicos.

```bash
# Inicializar Swarm (en el nodo manager)
docker swarm init

# Crear una red overlay
docker network create -d overlay my-overlay

# Desplegar un servicio en varios anfitriones
docker service create \
  --name web \
  --network my-overlay \
  --replicas 3 \
  nginx
```

**Cómo Funciona:**
- Abstrae la complejidad de la red multi-anfitrión
- Crea una red virtual que abarca todos los nodos de Swarm
- Los contenedores en distintos anfitriones pueden comunicarse como si estuvieran en la misma LAN
- Cifrado por defecto (tunelización IPSec)
- Descubrimiento de servicios y balanceo de carga automáticos

**Casos de Uso:**
- ✅ Despliegues de Docker Swarm multi-anfitrión
- ✅ Aplicaciones distribuidas en varios servidores

**Nota:** Para la orquestación de contenedores multi-anfitrión en producción, considera Kubernetes en lugar de Docker Swarm. Kubernetes usa su propio modelo de red (plugins CNI como Calico, Flannel, Cilium).

### Comparación de Tipos de Red

| Tipo de Red | Aislamiento | Rendimiento | Exposición de Puertos | Dirección MAC | Caso de Uso |
|--------------|-----------|-------------|---------------|-------------|----------|
| **Bridge** | Bueno | Bueno | Requerida (-p) | Asignada por Docker | Por defecto, la mayoría de apps |
| **Bridge Definido por Usuario** | Mejor | Bueno | Requerida (-p) | Asignada por Docker | Apps multi-contenedor |
| **Host** | Ninguno | Excelente | No necesaria | MAC del anfitrión | VPN, alto rendimiento |
| **None** | Completo | N/A | N/A | Ninguna | Trabajos por lotes aislados |
| **Macvlan** | Bueno | Excelente | No necesaria | Única por contenedor | Acceso directo a la red |
| **IPvlan L2** | Bueno | Excelente | No necesaria | Compartida (MAC del anfitrión) | Entornos con restricción de MAC |
| **IPvlan L3** | Bueno | Excelente | No necesaria | Compartida (MAC del anfitrión) | Enrutamiento L3 avanzado |
| **Overlay** | Bueno | Bueno | No necesaria | Virtual | Multi-anfitrión (Swarm) |

### Guía de Selección del Driver de Red

```
┌─────────────────────────────────────────┐
│ ¿Necesitas comunicación entre           │
│  contenedores?                           │
└────────────┬────────────────────────────┘
             │
    ┌────────┴────────┐
    │ SÍ              │ NO
    ↓                 ↓
┌─────────────┐   ┌──────────┐
│ Bridge      │   │ None     │
└─────────────┘   └──────────┘
    │
    ↓
┌──────────────────────────────────────────┐
│ ¿Necesitas contenedores en la red física?│
└────────┬─────────────────────────────────┘
         │
    ┌────┴────┐
    │ SÍ      │ NO
    ↓         ↓
┌──────────────────┐  ┌──────────────────────────────┐
│ ¿Modo promiscuo  │  │ ¿Necesitas máximo rendimiento?│
│ disponible?      │  └────────┬─────────────────────┘
└────────┬─────────┘           │
    ┌────┴────┐           ┌────┴────┐
    │ SÍ      │ NO        │ SÍ      │ NO
    ↓         ↓           ↓         ↓
┌────────┐ ┌──────────┐ ┌──────┐ ┌────────────────────┐
│ Macvlan│ │ IPvlan L2│ │ Host │ │ Bridge def. usuario│
└────────┘ └──────────┘ └──────┘ └────────────────────┘
```

### Solución de Problemas de Red

#### Problemas Comunes y Soluciones

**Problema 1: Los contenedores no pueden resolverse entre sí por nombre**
```bash
# Causa: Usar el bridge por defecto (sin resolución DNS)
# Solución: Usar un bridge definido por el usuario
docker network create my-network
docker run -d --name db --network my-network postgres
docker run -d --name app --network my-network myapp
# Ahora 'app' puede alcanzar 'db' por nombre
```

**Problema 2: Los contenedores macvlan no son alcanzables desde la red**
```bash
# Comprobar que el modo promiscuo está habilitado
ip link show eth0 | grep PROMISC

# Habilitar si falta
sudo ip link set eth0 promisc on

# Comprobar también la configuración del hipervisor (VirtualBox, Proxmox, etc.)
# Comprobar también la seguridad de puerto del switch físico
```

**Problema 3: El anfitrión no puede alcanzar sus propios contenedores macvlan/ipvlan**
```bash
# Este es el comportamiento esperado — el tráfico debe enrutarse por la red física
# Solución alternativa: Crear una interfaz macvlan separada en el anfitrión
sudo ip link add macvlan-shim link eth0 type macvlan mode bridge
sudo ip addr add 192.168.1.99/32 dev macvlan-shim
sudo ip link set macvlan-shim up
sudo ip route add 192.168.1.100/32 dev macvlan-shim
```

**Problema 4: Los dispositivos externos no pueden alcanzar los contenedores IPvlan L3**
```bash
# Causa: Tu router no sabe cómo enrutar hacia la subred del contenedor
# Solución: Añadir rutas estáticas en tu router
ip route add 192.168.94.0/24 via <docker-host-ip>
```

**Problema 5: Conflictos de IP del DHCP con macvlan/ipvlan**
```bash
# Causa: El DHCP interno de Docker asigna IPs que entran en conflicto con el DHCP del router
# Solución: Especifica siempre --ip o usa --ip-range al crear la red
docker run --network my-macvlan --ip=192.168.1.100 nginx
```

#### Comandos de Diagnóstico

```bash
# Ver todas las redes de Docker
docker network ls

# Inspeccionar los detalles de la red (muestra contenedores, IPs, config)
docker network inspect <network-name>

# Ver la configuración de red del contenedor
docker inspect <container> | grep -A 30 NetworkSettings

# Comprobar la conectividad desde dentro del contenedor
docker exec <container> ping <target>
docker exec <container> nslookup <hostname>
docker exec <container> ip addr show
docker exec <container> ip route

# Ver las interfaces bridge del anfitrión y los pares veth
ip addr show | grep docker
bridge link

# Ver las reglas NAT (cómo Docker enruta el tráfico)
sudo iptables -t nat -L -n -v
```

---

## 12. Volúmenes y Persistencia de Datos

### Entendiendo el Almacenamiento de Contenedores

**Por defecto, los datos del contenedor son efímeros:**
- Los datos existen solo mientras el contenedor se ejecuta
- Se eliminan cuando se elimina el contenedor
- No se pueden compartir entre contenedores

**Los volúmenes resuelven esto:**
- ✅ Persisten los datos más allá del ciclo de vida del contenedor
- ✅ Comparten datos entre contenedores
- ✅ Hacen backup y restauran datos
- ✅ Mejor rendimiento que los bind mounts

### Tres Tipos de Montajes

```
1. Volumen (Gestionado por Docker)
   Anfitrión: /var/lib/docker/volumes/my-vol
   Contenedor: /data

2. Bind Mount (Directorio del anfitrión)
   Anfitrión: /home/user/app
   Contenedor: /app

3. Montaje tmpfs (Solo memoria, Linux)
   RAM → Contenedor: /tmp
```

### 1. Volúmenes (Recomendado)

**Almacenamiento gestionado por Docker** - lo mejor para producción.

```bash
# Crear un volumen
docker volume create my-data

# Listar volúmenes
docker volume ls

# Inspeccionar un volumen
docker volume inspect my-data

# Eliminar un volumen
docker volume rm my-data

# Eliminar volúmenes sin usar
docker volume prune

# Eliminar todos los volúmenes
docker volume prune -a
```

#### Usando Volúmenes con Contenedores

```bash
# Ejecutar un contenedor con volumen
docker run -d \
  --name db \
  -v my-data:/var/lib/mysql \
  mysql:8

# Volumen anónimo (Docker asigna el nombre)
docker run -d -v /var/lib/mysql mysql:8

# Volumen con nombre (tú eliges el nombre)
docker run -d -v mysql-data:/var/lib/mysql mysql:8
```

#### Ejemplo: PostgreSQL Persistente

```bash
# Crear un volumen
docker volume create postgres-data

# Ejecutar PostgreSQL con volumen
docker run -d \
  --name postgres \
  -e POSTGRES_PASSWORD=secret \
  -v postgres-data:/var/lib/postgresql/data \
  postgres:17

# Los datos persisten aunque se elimine el contenedor
docker rm -f postgres

# Iniciar un nuevo contenedor con los mismos datos
docker run -d \
  --name postgres-new \
  -e POSTGRES_PASSWORD=secret \
  -v postgres-data:/var/lib/postgresql/data \
  postgres:17
```

### 2. Bind Mounts (Desarrollo)

**Montar un directorio del anfitrión** en el contenedor - excelente para desarrollo.

```bash
# Sintaxis: -v RUTA_ANFITRION:RUTA_CONTENEDOR

# Montar el directorio actual
docker run -d \
  -v $(pwd):/app \
  -p 3000:3000 \
  node:22

# Ruta absoluta
docker run -d \
  -v /home/user/app:/app \
  node:22

# Montaje de solo lectura
docker run -d \
  -v $(pwd):/app:ro \
  nginx
```

#### Ejemplo de Flujo de Trabajo de Desarrollo

```bash
# Estructura del proyecto
my-app/
├── index.js
├── package.json
└── node_modules/

# Ejecutar con bind mount para edición en vivo
docker run -d \
  --name dev \
  -v $(pwd):/app \
  -v /app/node_modules \
  -p 3000:3000 \
  my-app:dev

# Los cambios en index.js en el anfitrión se reflejan inmediatamente en el contenedor
```

### 3. Montaje tmpfs (Solo Linux)

**Sistema de archivos temporal en memoria** - los datos se pierden cuando el contenedor se detiene.

```bash
# Crear un montaje tmpfs
docker run -d \
  --tmpfs /tmp \
  nginx

# Con límite de tamaño
docker run -d \
  --tmpfs /tmp:size=100m \
  nginx
```

**Casos de Uso:**
- Datos sensibles (contraseñas, claves)
- Datos de procesamiento temporal
- Almacenamiento temporal de alto rendimiento

### Ubicaciones de Volúmenes por Base de Datos

```bash
# PostgreSQL
/var/lib/postgresql/data

# MySQL
/var/lib/mysql

# MongoDB
/data/db

# Redis
/data

# Elasticsearch
/usr/share/elasticsearch/data
```

### Compartiendo Volúmenes Entre Contenedores

```bash
# El Contenedor 1 crea el volumen
docker run -d \
  --name writer \
  -v shared-data:/data \
  alpine sh -c "echo 'Hello' > /data/message.txt"

# El Contenedor 2 lee del mismo volumen
docker run \
  --name reader \
  -v shared-data:/data \
  alpine cat /data/message.txt

# Salida: Hello
```

### Haciendo Backup de Volúmenes

```bash
# Backup del volumen a un archivo tar
docker run --rm \
  -v my-data:/data \
  -v $(pwd):/backup \
  alpine tar czf /backup/backup.tar.gz -C /data .

# Restaurar el volumen desde el backup
docker run --rm \
  -v my-data:/data \
  -v $(pwd):/backup \
  alpine tar xzf /backup/backup.tar.gz -C /data
```

### Buenas Prácticas de Volúmenes

1. **Usa volúmenes con nombre para las bases de datos**
```bash
docker run -v postgres-data:/var/lib/postgresql/data postgres
```

2. **Usa bind mounts para el desarrollo**
```bash
docker run -v $(pwd):/app my-dev-image
```

3. **Excluye node_modules con un volumen anónimo**
```bash
docker run \
  -v $(pwd):/app \
  -v /app/node_modules \
  my-app
```

4. **Backups regulares**
```bash
docker run --rm -v my-data:/data -v $(pwd):/backup alpine \
  tar czf /backup/$(date +%Y%m%d)-backup.tar.gz -C /data .
```

---

## 13. Docker Compose

### ¿Qué es Docker Compose?

**Docker Compose** es una herramienta para definir y ejecutar aplicaciones multi-contenedor usando un archivo YAML.

**Beneficios:**
- ✅ Definir todos los servicios en un solo archivo
- ✅ Iniciar/detener todos los contenedores con un solo comando
- ✅ Creación automática de red
- ✅ Configuración del entorno
- ✅ Fácil de versionar
- ✅ Entornos reproducibles

### Docker Compose v2 (CLI Integrada)

**Importante:** Desde Docker Desktop 4.0+ y Docker Engine 20.10+, Docker Compose v2 está integrado directamente en la CLI de Docker como un plugin. El `docker-compose` (v1) independiente está obsoleto.

**Diferencias Clave:**
- ✅ **v2 (actual)**: `docker compose` (espacio, sin guion)
- ❌ **v1 (obsoleto)**: `docker-compose` (con guion)

```bash
# Comprobar Docker Compose v2 (viene con Docker Desktop y Docker Engine moderno)
docker compose version

# Salida esperada: Docker Compose version v2.x.x

# Verificar que está integrado (debería mostrar compose como subcomando)
docker --help | grep compose

# Si usas Docker Desktop: Compose v2 se incluye automáticamente
# ¡No se necesita instalación por separado!
```

**Instalación Manual en Linux (si es necesario):**

```bash
# En la mayoría de distros de Linux, instala el plugin vía el gestor de paquetes:
sudo apt-get install docker-compose-plugin        # Debian/Ubuntu
sudo dnf install docker-compose-plugin            # Fedora/RHEL

# Instalación manual (fija una versión explícita en lugar de 'latest'):
mkdir -p ~/.docker/cli-plugins/
COMPOSE_VERSION=v2.32.4
curl -SL "https://github.com/docker/compose/releases/download/${COMPOSE_VERSION}/docker-compose-$(uname -s)-$(uname -m)" \
  -o ~/.docker/cli-plugins/docker-compose
chmod +x ~/.docker/cli-plugins/docker-compose

# Verificar la instalación
docker compose version
```

**Migrando de v1 a v2:**

```bash
# La mayoría de los comandos son idénticos, solo cambia el formato del comando:

# v1 (antiguo): docker-compose up
# v2 (nuevo): docker compose up

# v1 (antiguo): docker-compose down
# v2 (nuevo): docker compose down

# Crear un alias para compatibilidad hacia atrás (opcional)
echo 'alias docker-compose="docker compose"' >> ~/.bashrc
source ~/.bashrc
```

### Estructura Básica de docker-compose.yml

**Archivo de Compose Moderno:**

```yaml
# Nota: el campo 'version' de nivel superior es obsoleto en Compose v2.
# La Compose Specification no tiene versión — omítelo. Incluirlo ahora
# solo emite una advertencia de obsolescencia y por lo demás se ignora.

services:
  service-name:
    image: image:tag
    # o
    build: ./path
    ports:
      - "HOST:CONTAINER"
    environment:
      - KEY=value
    volumes:
      - volume-name:/path
    networks:
      - network-name
    depends_on:
      - other-service

volumes:
  volume-name:

networks:
  network-name:
```

> **Obsoleto:** la clave `version:` de nivel superior (p. ej. `version: '3.9'`). Compose v2 la ignora y avisa. Simplemente omítela — los ejemplos siguientes lo hacen.

### Ejemplo Simple: Servidor Web

```yaml
services:
  web:
    image: nginx:1.27
    ports:
      - "8080:80"
    volumes:
      - ./html:/usr/share/nginx/html
```

```bash
# Iniciar
docker compose up

# Iniciar en segundo plano
docker compose up -d

# Detener
docker compose down
```

### Ejemplo Completo: Node.js + MongoDB

```yaml
services:
  # Base de datos MongoDB
  mongodb:
    image: mongo:7
    container_name: mongodb
    environment:
      MONGO_INITDB_ROOT_USERNAME: admin
      MONGO_INITDB_ROOT_PASSWORD: secret
      MONGO_INITDB_DATABASE: myapp
    ports:
      - "27017:27017"
    volumes:
      - mongo-data:/data/db
    networks:
      - app-network

  # Aplicación Node.js
  app:
    build: .
    container_name: node-app
    ports:
      - "3000:3000"
    environment:
      NODE_ENV: production
      MONGODB_URI: mongodb://admin:secret@mongodb:27017/myapp
    depends_on:
      - mongodb
    volumes:
      - ./:/app
      - /app/node_modules
    networks:
      - app-network

volumes:
  mongo-data:

networks:
  app-network:
    driver: bridge
```

### Comandos de Docker Compose

```bash
# Iniciar servicios
docker compose up

# Iniciar en modo detached
docker compose up -d

# Construir imágenes antes de iniciar
docker compose up --build

# Iniciar un servicio específico
docker compose up web

# Detener servicios (mantiene los contenedores)
docker compose stop

# Detener y eliminar contenedores, redes
docker compose down

# Eliminar también los volúmenes
docker compose down -v

# Ver los servicios en ejecución
docker compose ps

# Ver los logs
docker compose logs

# Seguir los logs
docker compose logs -f

# Logs de un servicio específico
docker compose logs -f app

# Ejecutar un comando en un servicio
docker compose exec app sh

# Reiniciar servicios
docker compose restart

# Ver la configuración de los servicios
docker compose config
```

### Variables de Entorno en Compose

#### Usando un archivo .env

```bash
# .env
MYSQL_ROOT_PASSWORD=secret
MYSQL_DATABASE=myapp
APP_PORT=3000
```

```yaml
# docker-compose.yml
services:
  db:
    image: mysql:8
    environment:
      MYSQL_ROOT_PASSWORD: ${MYSQL_ROOT_PASSWORD}
      MYSQL_DATABASE: ${MYSQL_DATABASE}

  app:
    build: .
    ports:
      - "${APP_PORT}:3000"
```

#### Variables de Entorno en Línea

```yaml
services:
  app:
    image: node:22
    environment:
      NODE_ENV: production
      DATABASE_URL: postgres://db:5432/mydb
      API_KEY: secret123
```

#### environment vs env_file

```yaml
services:
  app:
    # Opción 1: En línea
    environment:
      KEY1: value1
      KEY2: value2

    # Opción 2: Desde un archivo
    env_file:
      - .env
      - .env.local
```

### Volúmenes en Compose

```yaml
services:
  db:
    image: postgres:17
    volumes:
      # Volumen con nombre
      - postgres-data:/var/lib/postgresql/data

      # Bind mount
      - ./init.sql:/docker-entrypoint-initdb.d/init.sql

      # Volumen anónimo
      - /var/lib/postgresql/logs

volumes:
  postgres-data:
    driver: local
```

### Redes en Compose

```yaml
services:
  frontend:
    image: nginx
    networks:
      - frontend-network

  backend:
    image: node:22
    networks:
      - frontend-network
      - backend-network

  database:
    image: postgres
    networks:
      - backend-network

networks:
  frontend-network:
  backend-network:
```

### Dependencias de Servicios

```yaml
services:
  db:
    image: postgres:17

  backend:
    build: ./backend
    depends_on:
      - db

  frontend:
    build: ./frontend
    depends_on:
      - backend
```

**Nota:** `depends_on` solo espera a que el contenedor arranque, no a que el servicio esté listo.

### Health Checks

```yaml
services:
  db:
    image: postgres:17
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U postgres"]
      interval: 10s
      timeout: 5s
      retries: 5

  app:
    build: .
    depends_on:
      db:
        condition: service_healthy
```

---

## 14. Aplicaciones Multi-Contenedor

### Ejemplo: Aplicación Full Stack

**Estructura del Proyecto:**
```
fullstack-app/
├── docker-compose.yml
├── frontend/
│   ├── Dockerfile
│   └── (React app)
├── backend/
│   ├── Dockerfile
│   └── (Node.js API)
└── database/
    └── init.sql
```

**docker-compose.yml:**
```yaml
services:
  # Base de datos PostgreSQL
  db:
    image: postgres:17
    container_name: postgres-db
    environment:
      POSTGRES_USER: admin
      POSTGRES_PASSWORD: secret
      POSTGRES_DB: appdb
    volumes:
      - postgres-data:/var/lib/postgresql/data
      - ./database/init.sql:/docker-entrypoint-initdb.d/init.sql
    networks:
      - backend-network
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U admin"]
      interval: 10s
      timeout: 5s
      retries: 5

  # API Backend (Node.js + Express)
  backend:
    build: ./backend
    container_name: api-server
    environment:
      NODE_ENV: production
      DATABASE_URL: postgres://admin:secret@db:5432/appdb
      PORT: 5000
    ports:
      - "5000:5000"
    depends_on:
      db:
        condition: service_healthy
    networks:
      - backend-network
      - frontend-network
    volumes:
      - ./backend:/app
      - /app/node_modules

  # Frontend (React)
  frontend:
    build: ./frontend
    container_name: react-app
    environment:
      REACT_APP_API_URL: http://localhost:5000
    ports:
      - "3000:3000"
    depends_on:
      - backend
    networks:
      - frontend-network
    volumes:
      - ./frontend:/app
      - /app/node_modules

  # Proxy Inverso Nginx
  nginx:
    image: nginx:alpine
    container_name: nginx-proxy
    ports:
      - "80:80"
    volumes:
      - ./nginx/nginx.conf:/etc/nginx/nginx.conf
    depends_on:
      - frontend
      - backend
    networks:
      - frontend-network

volumes:
  postgres-data:

networks:
  backend-network:
  frontend-network:
```

### Ejemplo: Arquitectura de Microservicios

```yaml
services:
  # API Gateway
  api-gateway:
    build: ./gateway
    ports:
      - "80:80"
    networks:
      - microservices
    depends_on:
      - user-service
      - product-service
      - order-service

  # Servicio de Usuarios
  user-service:
    build: ./services/users
    environment:
      DB_HOST: users-db
    networks:
      - microservices
    depends_on:
      - users-db

  # Servicio de Productos
  product-service:
    build: ./services/products
    environment:
      DB_HOST: products-db
    networks:
      - microservices
    depends_on:
      - products-db

  # Servicio de Pedidos
  order-service:
    build: ./services/orders
    environment:
      DB_HOST: orders-db
      USER_SERVICE: user-service:3000
      PRODUCT_SERVICE: product-service:3000
    networks:
      - microservices
    depends_on:
      - orders-db

  # Bases de datos
  users-db:
    image: postgres:17
    environment:
      POSTGRES_DB: users
    volumes:
      - users-data:/var/lib/postgresql/data
    networks:
      - microservices

  products-db:
    image: postgres:17
    environment:
      POSTGRES_DB: products
    volumes:
      - products-data:/var/lib/postgresql/data
    networks:
      - microservices

  orders-db:
    image: postgres:17
    environment:
      POSTGRES_DB: orders
    volumes:
      - orders-data:/var/lib/postgresql/data
    networks:
      - microservices

  # Caché Redis
  redis:
    image: redis:alpine
    networks:
      - microservices

volumes:
  users-data:
  products-data:
  orders-data:

networks:
  microservices:
    driver: bridge
```

### Ejemplo: Stack de WordPress

```yaml
services:
  wordpress:
    image: wordpress:latest
    container_name: wordpress
    restart: always
    ports:
      - "8080:80"
    environment:
      WORDPRESS_DB_HOST: db:3306
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: secret
      WORDPRESS_DB_NAME: wordpress
    volumes:
      - wordpress-data:/var/www/html
    networks:
      - wordpress-network
    depends_on:
      - db

  db:
    image: mysql:8
    container_name: wordpress-mysql
    restart: always
    environment:
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wordpress
      MYSQL_PASSWORD: secret
      MYSQL_ROOT_PASSWORD: rootsecret
    volumes:
      - mysql-data:/var/lib/mysql
    networks:
      - wordpress-network

  phpmyadmin:
    image: phpmyadmin:latest
    container_name: phpmyadmin
    restart: always
    ports:
      - "8081:80"
    environment:
      PMA_HOST: db
      MYSQL_ROOT_PASSWORD: rootsecret
    networks:
      - wordpress-network
    depends_on:
      - db

volumes:
  wordpress-data:
  mysql-data:

networks:
  wordpress-network:
```

---

## 15. Entornos de Desarrollo

### Desarrollo vs Producción

**Necesidades distintas:**
- Desarrollo: Recarga en vivo, depuración, source maps
- Producción: Optimizado, tamaño mínimo, seguridad

### Dockerfile.dev vs Dockerfile

**Dockerfile (Producción):**
```dockerfile
FROM node:22-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
RUN npm run build
EXPOSE 3000
CMD ["node", "dist/main.js"]
```

**Dockerfile.dev (Desarrollo):**
```dockerfile
FROM node:22
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "run", "dev"]
```

### docker-compose.yml vs docker-compose.dev.yml

**docker-compose.dev.yml:**
```yaml
services:
  app:
    build:
      context: .
      dockerfile: Dockerfile.dev
    ports:
      - "3000:3000"
      - "9229:9229"  # Puerto de depuración de Node.js
    environment:
      NODE_ENV: development
    volumes:
      # Bind mount para recarga en vivo
      - ./src:/app/src
      - /app/node_modules
    command: npm run dev

  db:
    image: postgres:17
    environment:
      POSTGRES_PASSWORD: dev-password
    ports:
      - "5432:5432"  # Exponer para herramientas locales
```

**Ejecutando el compose de desarrollo:**
```bash
# Usar un archivo compose específico
docker compose -f docker-compose.dev.yml up

# Sobrescribir el archivo por defecto
docker compose -f docker-compose.yml -f docker-compose.dev.yml up
```

### Hot Reload con Nodemon

**Dockerfile.dev:**
```dockerfile
FROM node:22
WORKDIR /app

# Instalar nodemon globalmente
RUN npm install -g nodemon

COPY package*.json ./
RUN npm install
COPY . .

EXPOSE 3000
CMD ["nodemon", "index.js"]
```

**docker-compose.dev.yml:**
```yaml
services:
  app:
    build:
      context: .
      dockerfile: Dockerfile.dev
    volumes:
      - .:/app
      - /app/node_modules
    environment:
      NODE_ENV: development
```

### Depuración en Docker

**Node.js con depuración:**
```yaml
services:
  app:
    build: .
    ports:
      - "3000:3000"
      - "9229:9229"
    command: node --inspect=0.0.0.0:9229 app.js
```

**launch.json de VS Code:**
```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Docker: Attach to Node",
      "type": "node",
      "request": "attach",
      "port": 9229,
      "address": "localhost",
      "localRoot": "${workspaceFolder}",
      "remoteRoot": "/app",
      "protocol": "inspector"
    }
  ]
}
```

### Configuración Específica del Entorno

**.env.development:**
```bash
NODE_ENV=development
DATABASE_URL=postgres://localhost:5432/dev
API_KEY=dev-key-123
DEBUG=true
```

**.env.production:**
```bash
NODE_ENV=production
DATABASE_URL=postgres://prod-db:5432/prod
API_KEY=${PROD_API_KEY}
DEBUG=false
```

**docker-compose.dev.yml:**
```yaml
services:
  app:
    env_file:
      - .env.development
```

---

## 16. Buenas Prácticas

### Buenas Prácticas del Dockerfile

#### 1. Usa Tags de Imagen Base Específicos

```dockerfile
# ✅ Bien - versión específica
FROM node:22.11.0-alpine

# ❌ Mal - actualizaciones impredecibles
FROM node:latest
```

#### 2. Usa .dockerignore

```
node_modules
.git
.env
*.log
dist
build
coverage
.vscode
.idea
```

#### 3. Minimiza las Capas

```dockerfile
# ✅ Bien - una sola capa
RUN apt-get update && \
    apt-get install -y curl vim && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# ❌ Mal - varias capas
RUN apt-get update
RUN apt-get install -y curl
RUN apt-get install -y vim
```

#### 4. Aprovecha la Caché del Build

```dockerfile
# ✅ Bien - dependencias cacheadas por separado
COPY package*.json ./
RUN npm install
COPY . .

# ❌ Mal - caché invalidada ante cualquier cambio de código
COPY . .
RUN npm install
```

#### 5. Usa Builds Multi-Etapa (Sintaxis Moderna de BuildKit)

**Builds multi-etapa modernos con mejoras de BuildKit:**

```dockerfile
# syntax=docker/dockerfile:1.4

# Etapa de build
FROM node:20-alpine AS builder
WORKDIR /app

# Aprovechar el caché de capas para las dependencias
COPY package*.json ./
RUN --mount=type=cache,target=/root/.npm \
    npm ci --only=production

COPY . .
RUN npm run build

# Etapa de producción con base distroless
FROM gcr.io/distroless/nodejs20-debian12
WORKDIR /app

# Copiar solo los artefactos de producción
COPY --from=builder /app/dist ./dist
COPY --from=builder /app/node_modules ./node_modules

CMD ["dist/main.js"]
```

**Multi-Etapa Avanzado con Múltiples Arquitecturas:**

```dockerfile
# syntax=docker/dockerfile:1.4

# Etapa de build (consciente de la plataforma)
FROM --platform=$BUILDPLATFORM node:20-alpine AS builder
ARG TARGETPLATFORM
ARG BUILDPLATFORM

WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
RUN npm run build

# Etapa de producción
FROM node:20-alpine
WORKDIR /app
COPY --from=builder /app/dist ./dist
COPY --from=builder /app/node_modules ./node_modules
CMD ["node", "dist/main.js"]
```

**Cache Mounts de BuildKit (Builds Más Rápidos):**

```dockerfile
# syntax=docker/dockerfile:1.4

FROM golang:1.23 AS builder

WORKDIR /app
COPY go.mod go.sum ./

# Usar cache mount de BuildKit para los módulos de Go (persiste entre builds)
RUN --mount=type=cache,target=/go/pkg/mod \
    go mod download

COPY . .

# Usar caché para los artefactos de build
RUN --mount=type=cache,target=/go/pkg/mod \
    --mount=type=cache,target=/root/.cache/go-build \
    CGO_ENABLED=0 go build -o main .

# Imagen de producción mínima
FROM gcr.io/distroless/static-debian12
COPY --from=builder /app/main /
CMD ["/main"]
```

#### 6. No Ejecutes como Root

```dockerfile
FROM node:22-alpine

# Crear usuario
RUN addgroup -S appgroup && adduser -S appuser -G appgroup

WORKDIR /app
COPY --chown=appuser:appgroup . .

USER appuser
CMD ["node", "app.js"]
```

#### 7. Usa COPY en Lugar de ADD

```dockerfile
# ✅ Bien - explícito
COPY package.json .

# ❌ Mal - demasiada magia (extracción automática, soporte de URL)
ADD package.json .
```

### Buenas Prácticas de Seguridad

#### 1. Escanea las Imágenes en Busca de Vulnerabilidades

**Docker Scout (Integrado, Recomendado para 2025):**

Docker Scout está ahora integrado en Docker Desktop y proporciona escaneo de vulnerabilidades en tiempo real:

```bash
# Escanear una imagen con Docker Scout (integrado desde Docker Desktop 4.17+)
docker scout cves my-image:latest

# Obtener recomendaciones para actualizar la imagen base
docker scout recommendations my-image:latest

# Comparar con las vulnerabilidades de la imagen base
docker scout compare --to my-image:latest my-image:dev

# Ver el SBOM (Software Bill of Materials)
docker scout sbom my-image:latest

# Resumen rápido
docker scout quickview my-image:latest

# Evaluación de políticas (requiere suscripción a Docker Scout)
docker scout policy my-image:latest
```

**Escáneres Alternativos:**

```bash
# Trivy (código abierto, completo)
trivy image my-image:latest

# Trivy con filtrado por severidad
trivy image --severity HIGH,CRITICAL my-image:latest

# Grype (de Anchore)
grype my-image:latest

# Snyk
snyk container test my-image:latest
```

#### 2. Usa Imágenes Base Oficiales y Verificadas

```dockerfile
# ✅ Lo mejor - imagen oficial de Docker Official Images
FROM node:20-alpine

# ✅ Bien - Docker Verified Publisher (DVP)
FROM bitnami/node:20

# ⚠️ Precaución - imagen de la comunidad (comprueba su reputación)
FROM some-user/node

# ❌ Mal - fuente no confiable
FROM random-user/node
```

**Comprobar la Procedencia de la Imagen (función de 2025):**
```bash
# Verificar la fuente de la imagen y la atestación del build
docker buildx imagetools inspect my-image:latest --format "{{json .}}"
```

#### 3. Mantén las Imágenes Actualizadas

```bash
# Rebuild regular con los últimos parches
docker build --no-cache -t my-app:latest .

# Actualizaciones automáticas de dependencias con Dependabot (GitHub)
# Añade .github/dependabot.yml:
# version: 2
# updates:
#   - package-ecosystem: "docker"
#     directory: "/"
#     schedule:
#       interval: "weekly"
```

#### 4. No Almacenes Secretos en las Imágenes

**❌ Malas Prácticas:**
```dockerfile
# ❌ Secretos en ENV (incrustados en la imagen)
ENV API_KEY=secret123

# ❌ Secretos en build args (visibles en el historial)
ARG SECRET_TOKEN=abc123
ENV SECRET_TOKEN=${SECRET_TOKEN}

# ❌ Copiar archivos de secretos
COPY .env /app/.env
```

**✅ Gestión Moderna de Secretos:**

```bash
# 1. Variables de entorno en tiempo de ejecución
docker run -e API_KEY=secret123 my-app

# 2. Archivo de entorno (no commiteado a git)
docker run --env-file .env.production my-app

# 3. Docker secrets (modo Swarm)
echo "my_secret_value" | docker secret create db_password -
docker service create --secret db_password my-app

# 4. Secret mounts de BuildKit (en tiempo de build, no en la imagen)
docker build --secret id=npm_token,src=$HOME/.npmrc -t my-app .
```

**Dockerfile con Secretos de BuildKit:**
```dockerfile
# syntax=docker/dockerfile:1.4
FROM node:20-alpine

WORKDIR /app
COPY package*.json ./

# Montar el secreto en tiempo de build (NO se almacena en la imagen)
RUN --mount=type=secret,id=npm_token \
    echo "//registry.npmjs.org/:_authToken=$(cat /run/secrets/npm_token)" > .npmrc && \
    npm install && \
    rm .npmrc

COPY . .
CMD ["node", "app.js"]
```

#### 5. Usa Imágenes Base Distroless o Mínimas (Recomendación de 2025)

**Las imágenes distroless contienen solo tu aplicación y sus dependencias de runtime:**

```dockerfile
# Build multi-etapa con distroless
FROM node:20-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
RUN npm run build

# Imagen final distroless (sin shell, superficie de ataque mínima)
FROM gcr.io/distroless/nodejs20-debian12
COPY --from=builder /app/dist /app/dist
COPY --from=builder /app/node_modules /app/node_modules
WORKDIR /app
CMD ["dist/main.js"]
```

**Beneficios de Distroless:**
- ✅ Sin shell ni gestor de paquetes (superficie de ataque reducida)
- ✅ Tamaño de imagen menor
- ✅ Menos CVEs (menos software instalado)
- ✅ Más difícil para los atacantes persistir si son comprometidos

#### 6. Firma y Verifica las Imágenes (Docker Content Trust)

**Habilita Docker Content Trust para la firma de imágenes:**

```bash
# Habilitar DCT (Docker Content Trust)
export DOCKER_CONTENT_TRUST=1

# Enviar una imagen firmada
docker push username/my-app:latest

# Descargar solo imágenes firmadas
docker pull username/my-app:latest
```

#### 7. Escaneo de Seguridad en CI/CD

**Ejemplo de GitHub Actions:**
```yaml
name: Security Scan
on: [push, pull_request]

jobs:
  scan:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Build image
        run: docker build -t my-app:${{ github.sha }} .

      - name: Run Trivy vulnerability scanner
        uses: aquasecurity/trivy-action@master
        with:
          image-ref: my-app:${{ github.sha }}
          severity: 'CRITICAL,HIGH'
          exit-code: '1'  # Fallar el build ante vulnerabilidades

      - name: Docker Scout CVEs
        uses: docker/scout-action@v1
        with:
          command: cves
          image: my-app:${{ github.sha }}
```

### Buenas Prácticas de Rendimiento

#### 1. Usa Imágenes Alpine

```dockerfile
# Tamaño de imagen menor
FROM node:22-alpine  # ~170MB
# vs
FROM node:22         # ~900MB
```

#### 2. Limpia en la Misma Capa

```dockerfile
RUN apt-get update && \
    apt-get install -y package && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
```

#### 3. Usa .dockerignore de Forma Agresiva

```
**/.git
**/node_modules
**/.env*
**/dist
**/build
**/*.log
```

### Buenas Prácticas de Compose

#### 1. Usa Control de Versiones

```bash
# Commitear docker-compose.yml
git add docker-compose.yml
git commit -m "Add Docker Compose configuration"
```

#### 2. Archivos Específicos del Entorno

```
docker-compose.yml          # Base
docker-compose.dev.yml      # Overrides de desarrollo
docker-compose.prod.yml     # Overrides de producción
```

```bash
# Desarrollo
docker compose -f docker-compose.yml -f docker-compose.dev.yml up

# Producción
docker compose -f docker-compose.yml -f docker-compose.prod.yml up
```

#### 3. Health Checks

```yaml
services:
  db:
    image: postgres:17
    healthcheck:
      test: ["CMD-SHELL", "pg_isready"]
      interval: 10s
      timeout: 5s
      retries: 5
```

#### 4. Límites de Recursos

```yaml
services:
  app:
    image: my-app
    deploy:
      resources:
        limits:
          cpus: '0.5'
          memory: 512M
        reservations:
          cpus: '0.25'
          memory: 256M
```

### Buenas Prácticas de Mantenimiento

#### 1. Limpieza Regular

```bash
# Eliminar contenedores sin usar
docker container prune

# Eliminar imágenes sin usar
docker image prune

# Eliminar volúmenes sin usar
docker volume prune

# Eliminar todo lo que no se usa
docker system prune -a
```

#### 2. Monitorea el Uso de Recursos

```bash
# Ver estadísticas
docker stats

# Ver el uso de disco
docker system df
```

#### 3. Estrategia de Logging

```yaml
services:
  app:
    image: my-app
    logging:
      driver: "json-file"
      options:
        max-size: "10m"
        max-file: "3"
```

---

## 17. Referencia de Comandos Comunes

### Gestión de Contenedores

```bash
# Ejecutar un contenedor
docker run -d --name my-app -p 8080:80 nginx

# Iniciar/Detener
docker start my-app
docker stop my-app
docker restart my-app

# Eliminar
docker rm my-app
docker rm -f my-app  # Forzar la eliminación de un contenedor en ejecución

# Listar
docker ps          # En ejecución
docker ps -a       # Todos
docker ps -q       # Solo IDs

# Logs
docker logs my-app
docker logs -f my-app  # Seguir
docker logs --tail 100 my-app

# Ejecutar un comando
docker exec my-app ls /app
docker exec -it my-app bash

# Inspeccionar
docker inspect my-app
docker stats my-app
```

### Gestión de Imágenes

```bash
# Descargar
docker pull nginx:latest

# Construir
docker build -t my-app:1.0 .
docker build -f Dockerfile.dev -t my-app:dev .

# Listar
docker images

# Eliminar
docker rmi my-app:1.0
docker rmi -f my-app:1.0

# Etiquetar
docker tag my-app:latest my-app:1.0

# Enviar (push)
docker push username/my-app:latest

# Historial
docker history my-app:latest
```

### Gestión de Red

```bash
# Crear
docker network create my-network

# Listar
docker network ls

# Inspeccionar
docker network inspect my-network

# Conectar un contenedor
docker network connect my-network my-app

# Desconectar
docker network disconnect my-network my-app

# Eliminar
docker network rm my-network
```

### Gestión de Volúmenes

```bash
# Crear
docker volume create my-data

# Listar
docker volume ls

# Inspeccionar
docker volume inspect my-data

# Eliminar
docker volume rm my-data

# Podar los que no se usan
docker volume prune
```

### Docker Compose

```bash
# Iniciar
docker compose up
docker compose up -d
docker compose up --build

# Detener
docker compose stop
docker compose down
docker compose down -v  # Eliminar volúmenes

# Logs
docker compose logs
docker compose logs -f
docker compose logs -f app

# Listar
docker compose ps

# Ejecutar
docker compose exec app sh

# Reiniciar
docker compose restart

# Construir
docker compose build
docker compose build --no-cache
```

### Comandos de Limpieza

```bash
# Eliminar contenedores detenidos
docker container prune

# Eliminar imágenes sin usar
docker image prune
docker image prune -a

# Eliminar volúmenes sin usar
docker volume prune

# Eliminar redes sin usar
docker network prune

# Limpiar todo
docker system prune
docker system prune -a --volumes

# Ver el uso de disco
docker system df
```

### Combinaciones Útiles

```bash
# Detener todos los contenedores en ejecución
docker stop $(docker ps -q)

# Eliminar todos los contenedores
docker rm $(docker ps -aq)

# Eliminar todas las imágenes
docker rmi $(docker images -q)

# Eliminar imágenes colgantes (dangling)
docker rmi $(docker images -f "dangling=true" -q)

# Ver los logs de todos los contenedores
docker ps -q | xargs -L 1 docker logs

# Entrar en la shell de un contenedor alpine
docker exec -it my-app sh

# Entrar en bash de un contenedor debian/ubuntu
docker exec -it my-app bash
```

---

## 18. Resumen

### Visión General

Esta guía cubre Docker desde los fundamentos hasta conceptos avanzados:

**Conceptos Fundamentales:**
- ✅ Entender contenedores vs máquinas virtuales
- ✅ Imágenes como planos, contenedores como instancias en ejecución
- ✅ Arquitectura y flujo de trabajo de Docker

**Habilidades Esenciales:**
- ✅ Instalar Docker en múltiples plataformas
- ✅ Trabajar con imágenes (pull, build, push, tag)
- ✅ Gestionar contenedores (crear, iniciar, detener, eliminar)
- ✅ Mapeo de puertos para el acceso a la red
- ✅ Variables de entorno para la configuración

**Temas Avanzados:**
- ✅ Escribir Dockerfiles eficientes con buenas prácticas
- ✅ Builds multi-etapa para imágenes más pequeñas
- ✅ Siete tipos de red y cuándo usar cada uno
- ✅ Comunicación de contenedores vía redes personalizadas
- ✅ Persistencia de datos con volúmenes (con nombre, bind, tmpfs)
- ✅ Docker Compose para aplicaciones multi-contenedor
- ✅ Entornos de desarrollo vs producción
- ✅ Buenas prácticas de seguridad, rendimiento y mantenimiento

### Puntos Clave

**Docker Simplifica el Desarrollo:**
- "Funciona en mi máquina" se convierte en "funciona en todas partes"
- Configuración con un comando para nuevos desarrolladores
- Entornos consistentes de dev a producción
- Gestión de dependencias sencilla

**Las Buenas Prácticas Importan:**
- Usa tags de imagen específicos, no `latest`
- Aprovecha la caché del build ordenando las instrucciones del Dockerfile
- No ejecutes contenedores como root
- Usa .dockerignore para reducir el contexto de build
- Builds multi-etapa para imágenes de producción más pequeñas
- Escaneos de seguridad y actualizaciones regulares

**Compose es Tu Aliado:**
- Define todo el stack en un solo archivo YAML
- Inicia todo con `docker compose up`
- Configuraciones específicas del entorno fáciles
- Creación automática de red y resolución DNS
- Versiona tu infraestructura

### Flujos de Trabajo Comunes

**Desarrollo:**
```bash
# Iniciar el entorno de desarrollo
docker compose -f docker-compose.dev.yml up

# Hacer cambios en el código (auto-recarga con volúmenes)

# Ver los logs
docker compose logs -f app

# Ejecutar comandos
docker compose exec app npm test
```

**Producción:**
```bash
# Construir imágenes de producción
docker build -t my-app:1.0 .

# Etiquetar para el registry
docker tag my-app:1.0 registry.com/my-app:1.0

# Enviar al registry
docker push registry.com/my-app:1.0

# Desplegar con compose
docker compose -f docker-compose.prod.yml up -d
```

### Siguientes Pasos

**Continúa Aprendiendo:**
1. **Orquestación de Contenedores** - Kubernetes, Docker Swarm
2. **Integración de CI/CD** - GitHub Actions, GitLab CI, Jenkins
3. **Monitoreo** - Prometheus, Grafana, ELK Stack
4. **Seguridad** - Escaneo de imágenes, gestión de secretos, protección en runtime
5. **Redes Avanzadas** - Service mesh, redes overlay
6. **Despliegue en Producción** - Plataformas de nube (AWS ECS, GKE, AKS)

**Proyectos de Práctica:**
- App full-stack (React + Node.js + PostgreSQL)
- Arquitectura de microservicios con varios servicios
- Sitio WordPress con MySQL y phpMyAdmin
- Stack de monitoreo (Prometheus + Grafana)
- Pipeline de CI/CD con builds de Docker

**Recursos para Explorar:**
- Documentación Oficial de Docker
- Docker Hub para imágenes oficiales
- Ejemplos de Docker Compose en GitHub
- Servicios de contenedores de los proveedores de nube
- Kubernetes para la orquestación

---

## 19. Recursos

### Documentación Oficial

- **Docker Docs** - https://docs.docker.com
- **Docker Hub** - https://hub.docker.com
- **Docker Compose** - https://docs.docker.com/compose
- **Referencia del Dockerfile** - https://docs.docker.com/engine/reference/builder
- **Docker CLI** - https://docs.docker.com/engine/reference/commandline/cli

### Aprendizaje Interactivo

- **Play with Docker** - https://labs.play-with-docker.com
  - Playground de Docker en línea gratuito
  - No requiere instalación

- **Docker Curriculum** - https://docker-curriculum.com
  - Tutorial práctico para principiantes

- **Katacoda Docker Scenarios** - Tutoriales interactivos de Docker

### Guías de Buenas Prácticas

- **Docker Best Practices** - https://docs.docker.com/develop/dev-best-practices
- **Dockerfile Best Practices** - https://docs.docker.com/develop/develop-images/dockerfile_best-practices
- **Security Best Practices** - https://docs.docker.com/engine/security

### Herramientas

**Seguridad de Contenedores:**
- **Trivy** - https://github.com/aquasecurity/trivy
- **Docker Scout** - Integrado en Docker Desktop
- **Snyk** - https://snyk.io/product/container-vulnerability-management

**Optimización de Imágenes:**
- **Dive** - https://github.com/wagoodman/dive (analizar capas)
- **Docker Slim** - https://github.com/docker-slim/docker-slim

**Alternativas a Compose:**
- **Podman Compose** - https://github.com/containers/podman-compose
- **Docker Swarm** - Integrado en Docker

### Comunidad

- **Docker Community Forums** - https://forums.docker.com
- **Docker Slack** - https://dockercommunity.slack.com
- **Stack Overflow** - Tags: `docker`, `dockerfile`, `docker-compose`
- **Reddit** - r/docker

### Tecnologías Relacionadas

- **Kubernetes** - https://kubernetes.io (orquestación de contenedores)
- **Podman** - https://podman.io (alternativa a Docker)
- **containerd** - https://containerd.io (runtime de contenedores)
- **BuildKit** - https://github.com/moby/buildkit (builds avanzados)

### Hojas de Referencia (Cheat Sheets)

- **Docker Cheat Sheet** - https://dockerlabs.collabnix.com/docker/cheatsheet
- **Dockerfile Cheat Sheet** - https://kapeli.com/cheat_sheets/Dockerfile.docset/Contents/Resources/Documents/index
- **Docker Compose Cheat Sheet** - https://devhints.io/docker-compose

---

## Información del Documento

**Última Actualización:** 2026-08-31
**Versión de Docker Cubierta:** 25.x+
**Versión de Compose:** v2 (integrada con la CLI de Docker)
**BuildKit:** Habilitado por defecto (Docker 23.0+)

**Temas Clave Cubiertos:**
- ✅ Docker Compose v2 (CLI integrada)
- ✅ BuildKit como motor de build por defecto
- ✅ Buildx para builds multi-plataforma
- ✅ Escaneo de vulnerabilidades con Docker Scout
- ✅ Imágenes base distroless y mínimas
- ✅ Cache mounts y secretos de BuildKit
- ✅ Alternativas a Docker Desktop (Rancher, Podman, Colima, OrbStack)
- ✅ Buenas prácticas de seguridad modernas
- ✅ Content Trust y firma de imágenes
- ✅ Explicaciones avanzadas de red (modos macvlan, ipvlan)

**Requisitos Previos:**
- Conocimientos básicos de línea de comandos
- Comprensión de conceptos de desarrollo de software
- Familiaridad con los sistemas de archivos de Linux (útil pero no obligatorio)

**Progresión del Nivel de Habilidad:**
1. **Principiante** (Secciones 1-7): Fundamentos, imágenes, contenedores, puertos
2. **Intermedio** (Secciones 8-13): Dockerfile, construcción, redes, volúmenes, Compose
3. **Avanzado** (Secciones 14-16): Apps multi-contenedor, despliegues en producción, buenas prácticas

**Cambios recientes de Docker a tener en cuenta:**
- BuildKit es el builder por defecto (más rápido, mejor caché)
- Compose v2 integrado en la CLI de Docker (`docker compose`, no `docker-compose`)
- Escaneo de vulnerabilidades integrado con Docker Scout
- Soporte multi-plataforma mejorado con Buildx
- Mejor gestión de secretos con los mounts de BuildKit
- Licencia de Docker Desktop (de pago para empresas; hay alternativas disponibles: Colima, Podman, OrbStack, Rancher Desktop)

**Siguientes Pasos Tras Esta Guía:**
1. Practicar la construcción de Dockerfiles multi-etapa
2. Configurar CI/CD con builds automatizados y escaneo de imágenes
3. Explorar Kubernetes para la orquestación
4. Implementar imágenes firmadas y procedencia (cadena de suministro zero-trust)
5. Optimizar imágenes con los cache mounts de BuildKit
