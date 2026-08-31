# Kubernetes - De Novato a Pro

## 📌 Metadatos del Documento

**Última Actualización:** 2026-08-31
**Versiones de Kubernetes Cubiertas:** 1.29 - 1.31
**Versiones de API Usadas:** apps/v1, v1, networking.k8s.io/v1
**Requisitos Previos:**
- Comprensión básica de Docker y la contenerización
- Familiaridad con la sintaxis YAML
- Experiencia básica en línea de comandos
- Comprensión de conceptos básicos de red

**Nivel de Habilidad:** Principiante hasta Listo para la Certificación CKA/CKAD

---

## 🎯 Cuándo Usar Este Conocimiento

**Usa esta guía cuando necesites:**
- Desplegar aplicaciones contenerizadas en clústeres de Kubernetes de producción
- Gestionar aplicaciones multi-nivel en varios servidores/nodos
- Implementar infraestructura con auto-escalado y auto-recuperación
- Configurar el descubrimiento de servicios y el balanceo de carga
- Configurar almacenamiento persistente para aplicaciones con estado
- Implementar despliegues sin tiempo de inactividad con rolling updates
- Solucionar fallos de pods y problemas de red
- Prepararte para las certificaciones CKA (Certified Kubernetes Administrator) o CKAD (Certified Kubernetes Application Developer)

**Esta guía está alineada con los manifiestos en:**
- `/Users/sysadmin/Workspace/Kubernetes/` - Manifiestos listos para producción
- Estructura de dos niveles: Tipo de Recurso → Proyecto/Entorno
- Ejemplos del mundo real de los namespaces `devsonic-cl`, `applications` y `databases`

**Aplicaciones de Producción Actuales Referenciadas:**
- `api-devsonic-cl` - API NestJS (Deployment apps/v1)
- `devsonic-cl` - Frontend React (Deployment apps/v1)
- `petsecure-devsonic-cl` - Frontend Angular (Deployment apps/v1)
- StatefulSet de PostgreSQL con almacenamiento persistente
- Nginx Ingress Controller con terminación TLS

---

## 📋 Tabla de Contenidos

1. [Introducción a Kubernetes](#1-introducción-a-kubernetes)
2. [¿Qué es Kubernetes?](#2-qué-es-kubernetes)
3. [Kubernetes vs Docker](#3-kubernetes-vs-docker)
4. [Arquitectura de Kubernetes](#4-arquitectura-de-kubernetes)
5. [Instalación y Configuración](#5-instalación-y-configuración)
6. [kubectl - La CLI de Kubernetes](#6-kubectl---la-cli-de-kubernetes)
7. [Namespaces](#7-namespaces)
8. [Pods - La Unidad Básica](#8-pods---la-unidad-básica)
9. [Deployments](#9-deployments)
10. [DaemonSets](#10-daemonsets)
11. [StatefulSets](#11-statefulsets)
12. [Services - ClusterIP](#12-services---clusterip)
13. [Services - NodePort](#13-services---nodeport)
14. [Services - LoadBalancer](#14-services---loadbalancer)
15. [Ingress](#15-ingress)
16. [Redes en Kubernetes](#16-redes-en-kubernetes)
17. [ConfigMaps](#17-configmaps)
18. [Secrets](#18-secrets)
19. [Volúmenes Persistentes](#19-volúmenes-persistentes)
20. [Kustomize](#20-kustomize)
21. [Gestor de Paquetes Helm](#21-gestor-de-paquetes-helm)
22. [Herramientas de Kubernetes](#22-herramientas-de-kubernetes)
23. [Buenas Prácticas](#23-buenas-prácticas)
24. [Operaciones Avanzadas de kubectl](#24-operaciones-avanzadas-de-kubectl)
25. [Almacenamiento en Profundidad](#25-almacenamiento-en-profundidad)
26. [Network Policies Explicadas](#26-network-policies-explicadas)
27. [Entendiendo Kube Proxy y las Redes](#27-entendiendo-kube-proxy-y-las-redes)
28. [Gestión de Logs y Solución de Problemas](#28-gestión-de-logs-y-solución-de-problemas)
29. [Gestión de Recursos y Probes](#29-gestión-de-recursos-y-probes)
30. [Configuración de Kubernetes en la Nube](#30-configuración-de-kubernetes-en-la-nube)

---

## Descripción General

Kubernetes es una plataforma de orquestación de contenedores de código abierto que automatiza el despliegue, escalado y gestión de aplicaciones contenerizadas. Creada por Google y ahora mantenida por la Cloud Native Computing Foundation (CNCF), Kubernetes se ha convertido en el estándar de la industria para la orquestación de contenedores.

### ¿Qué es Kubernetes?

- **Orquestador de contenedores** para gestionar aplicaciones contenerizadas
- Desarrollado por Google basándose en su sistema interno Borg
- Liberado como código abierto en 2014, ahora mantenido por la CNCF
- Configuración declarativa usando manifiestos YAML
- Escalado automático, auto-recuperación y balanceo de carga
- Agnóstico a la nube (se ejecuta en AWS, GCP, Azure, on-premises)

### Características Principales

- ✅ Gestión declarativa de la infraestructura
- ✅ Colocación y programación automática de contenedores
- ✅ Auto-recuperación (reinicia contenedores fallidos automáticamente)
- ✅ Escalado horizontal
- ✅ Descubrimiento de servicios y balanceo de carga
- ✅ Rollouts y rollbacks automatizados
- ✅ Gestión de secretos y configuración
- ✅ Orquestación de almacenamiento

### Conceptos Fundamentales

**La Filosofía de Ganado vs Mascotas (Cattle vs Pets):**
- **Mascotas (Pets)** (enfoque tradicional): Cada servidor tiene un nombre, te importa si muere
- **Ganado (Cattle)** (enfoque de Kubernetes): Los servidores son desechables, fácilmente reemplazables
- Kubernetes trata las instancias como ganado - si una muere, crea otra

**Infraestructura como Datos:**
- Configuración almacenada en archivos YAML declarativos
- Estado almacenado en etcd (base de datos clave-valor)
- No es infraestructura como código, sino infraestructura como datos

---

## 1. Introducción a Kubernetes

### Desde la Perspectiva Profesional

**Nota Importante:** Ser un "profesional" en Kubernetes no significa ser un "experto". Un profesional puede:
- Usar Kubernetes de forma efectiva en un entorno de trabajo
- Desplegar aplicaciones en clústeres de producción
- Solucionar problemas comunes
- Cobrar por trabajar con Kubernetes

**No necesitas 5 años de experiencia** para trabajar con Kubernetes profesionalmente. Necesitas:
- Comprensión de los conceptos fundamentales
- Experiencia práctica
- Capacidad de aplicar el conocimiento en escenarios del mundo real

### ¿Por Qué Kubernetes?

**Docker es genial para:**
- Ejecutar contenedores en un solo servidor
- Entornos de desarrollo
- Aplicaciones simples

**Docker se vuelve problemático cuando:**
- Necesitas ejecutar en varios servidores
- Quieres failover automático
- Necesitas auto-escalado
- Requieres despliegues sin tiempo de inactividad

**Kubernetes resuelve estos problemas al:**
- Orquestar contenedores en varios nodos
- Proporcionar failover automático
- Habilitar el auto-escalado
- Gestionar rolling updates
- Tratar la infraestructura como desechable

### Lectura Recomendada

**Site Reliability Engineering** de Google
- Gratis para leer en línea: [landing.google.com/sre/book](https://landing.google.com/sre/book)
- Explica la filosofía detrás de Kubernetes
- Muestra cómo Google gestionó la infraestructura a escala
- Cubre las prácticas y la cultura SRE

---

## 2. ¿Qué es Kubernetes?

### Orquestación de Contenedores

Kubernetes orquesta contenedores, lo que significa que:
- Decide dónde se ejecutan los contenedores
- Monitorea la salud de los contenedores
- Reinicia los contenedores fallidos
- Balancea la carga entre los contenedores
- Escala los contenedores hacia arriba o hacia abajo

### Declarativo vs Imperativo

**Declarativo (enfoque de Kubernetes):**
```yaml
# Declaras lo que quieres
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx
spec:
  replicas: 3
```

**Kubernetes intenta mantener este estado deseado:**
- Si un pod muere → Crea uno nuevo
- Si un nodo falla → Mueve los pods a otro nodo
- Siempre trabajando para igualar el estado declarado

### Beneficios Clave

**1. Auto-Recuperación Automática:**
- Kubernetes monitorea constantemente tus aplicaciones
- Reinicia automáticamente los contenedores fallidos
- Reemplaza los pods no saludables
- ¡Trabaja mientras duermes!

**2. Programación Inteligente (Scheduling):**
- Distribuye los pods entre los nodos
- Considera los requisitos de recursos
- Evita los puntos únicos de fallo
- Optimiza la utilización de recursos

**3. Integración con la Nube:**
- Se conecta a las APIs de los proveedores de nube (AWS, GCP, Azure, DigitalOcean)
- Crea automáticamente balanceadores de carga
- Aprovisiona volúmenes persistentes
- Crea y destruye instancias
- ¡Todo a través de manifiestos de Kubernetes!

---

## 3. Kubernetes vs Docker

### Limitaciones de Docker

**Docker Run:**
```bash
docker run -d \
  -p 80:80 \
  -v /data:/app/data \
  --name my-app \
  nginx:alpine
```

**Problemas:**
- El comando se vuelve complejo rápidamente
- Difícil de gestionar varios servidores
- Sin failover automático
- Escalado manual

**Docker Compose:**
```yaml
version: '3'
services:
  nginx:
    image: nginx:alpine
    ports:
      - "80:80"
```

**Mejor, pero:**
- Aún limitado a un solo servidor (en su mayoría)
- Sin escalado automático
- Sin auto-recuperación entre servidores
- Difícil de gestionar más de 10 servidores

### Ventajas de Kubernetes

**Gestiona cientos/miles de contenedores:**
- En varios servidores
- Con failover automático
- Con balanceo de carga
- Con auto-escalado

**Ejemplo:**
```yaml
# Un solo manifiesto gestiona 3 réplicas en el clúster
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx
spec:
  replicas: 3
  template:
    spec:
      containers:
      - name: nginx
        image: nginx:alpine
```

Kubernetes se encarga de:
- Dónde ejecutar cada pod
- El balanceo de carga entre ellos
- Reiniciarlos si fallan
- Escalar hacia arriba o hacia abajo
- Los rolling updates

---

## 4. Arquitectura de Kubernetes

### Componentes del Clúster

**Control Plane (Nodos Master):**
- **API Server** - Punto de entrada para todas las operaciones
- **Scheduler** - Decide dónde ejecutar los pods
- **Controller Manager** - Mantiene el estado deseado
- **Cloud Controller Manager** - Se integra con los proveedores de nube
- **etcd** - Base de datos clave-valor que almacena el estado del clúster

**Nodos Worker:**
- **kubelet** - Agente que se ejecuta en cada nodo
- **kube-proxy** - Proxy de red para los servicios
- **Container Runtime** - Docker, containerd, CRI-O

### Cómo Funciona

```
┌─────────────────────────────────────────────┐
│          Control Plane                      │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  │
│  │ API      │  │Scheduler │  │  etcd    │  │
│  │ Server   │  │          │  │          │  │
│  └──────────┘  └──────────┘  └──────────┘  │
└─────────────────────────────────────────────┘
           │
           ├─────────────────────┬─────────────┐
           │                     │             │
    ┌──────▼──────┐      ┌──────▼──────┐  ┌──▼───────┐
    │   Worker 1  │      │   Worker 2  │  │ Worker 3 │
    │  ┌────────┐ │      │  ┌────────┐ │  │┌────────┐│
    │  │kubelet │ │      │  │kubelet │ │  ││kubelet ││
    │  └────────┘ │      │  └────────┘ │  │└────────┘│
    │  ┌────────┐ │      │  ┌────────┐ │  │┌────────┐│
    │  │ Pods   │ │      │  │ Pods   │ │  ││ Pods   ││
    │  └────────┘ │      │  └────────┘ │  │└────────┘│
    └─────────────┘      └─────────────┘  └──────────┘
```

### Flujo de Comunicación

1. **Envías un manifiesto** al API Server
2. **El API Server valida** y lo almacena en etcd
3. **El Scheduler asigna los pods** a los nodos
4. **El kubelet en cada nodo** recibe instrucciones
5. **El kubelet inicia los contenedores** usando el container runtime
6. **El Controller Manager monitorea** y mantiene el estado
7. **Si un pod muere**, el controller crea uno nuevo

---

## 5. Instalación y Configuración

### Instalación de kubectl

**kubectl** es el cliente de línea de comandos de Kubernetes.

**Linux:**
```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/
```

**macOS:**
```bash
brew install kubectl
```

**Windows:**
```powershell
choco install kubernetes-cli
```

**Verificar la instalación:**
```bash
kubectl version --client=true
# Salida: Client Version: v1.29.0 (o v1.30.x, v1.31.x)
```

### Opciones de Kubernetes Local

**1. Docker Desktop (Mac/Windows):**
- La opción más fácil para usuarios de Mac/Windows
- Soporte integrado de Kubernetes
- Habilitar en: Preferences → Kubernetes → Enable Kubernetes

**2. Minikube (Todas las plataformas):**
```bash
# Instalar minikube
brew install minikube  # macOS
# o descargar desde minikube.sigs.k8s.io

# Iniciar el clúster (usa la última versión estable de Kubernetes)
minikube start

# Iniciar con una versión específica de Kubernetes
minikube start --kubernetes-version=v1.29.0

# Comprobar el estado
minikube status
```

**Características:**
- Se ejecuta en una VM o contenedor
- Incluye add-ons (dashboard, metrics, ingress)
- Fácil de usar
- Genial para aprender
- Soporta clústeres multi-nodo

**3. kind (Kubernetes in Docker):**
```bash
# Instalar kind
brew install kind  # macOS

# Crear un clúster
kind create cluster

# Clúster de varios nodos
kind create cluster --config kind-config.yaml
```

**Mejor para:**
- Usuarios de Linux
- Entornos de CI/CD
- Probar configuraciones multi-nodo

### Kubernetes en la Nube

**Proveedores populares:**
- **DigitalOcean Kubernetes** (DOKS)
- **Amazon EKS** (Elastic Kubernetes Service)
- **Google GKE** (Google Kubernetes Engine)
- **Azure AKS** (Azure Kubernetes Service)

**Ejemplo de DigitalOcean:**
1. Ve al dashboard de DigitalOcean
2. Haz clic en "Create" → "Kubernetes"
3. Elige la región y el tamaño de nodo
4. Selecciona el número de nodos
5. Haz clic en "Create Cluster"
6. Descarga el archivo kubeconfig

### Configuración de kubeconfig

**kubeconfig** contiene la información de conexión al clúster y las credenciales.

**Establecer kubeconfig:**
```bash
# Exportar la variable de entorno
export KUBECONFIG=/path/to/your/kubeconfig.yaml

# O copiar a la ubicación por defecto
mkdir -p ~/.kube
cp /path/to/kubeconfig.yaml ~/.kube/config
```

**Verificar la conexión:**
```bash
kubectl get nodes

# Salida:
# NAME                   STATUS   ROLES    AGE   VERSION
# worker-1               Ready    <none>   5m    v1.29.0
# worker-2               Ready    <none>   5m    v1.29.0
# worker-3               Ready    <none>   5m    v1.29.0
```

---

## 6. kubectl - La CLI de Kubernetes

### Comandos Esenciales

**Obtener Recursos:**
```bash
# Obtener pods
kubectl get pods

# Obtener todos los recursos
kubectl get all

# Obtener pods con más información
kubectl get pods -o wide

# Obtener pods en todos los namespaces
kubectl get pods --all-namespaces
# o
kubectl get pods -A
```

**Describir Recursos:**
```bash
# Información detallada sobre un pod
kubectl describe pod <pod-name>

# Describir un nodo
kubectl describe node <node-name>

# Describir un servicio
kubectl describe service <service-name>
```

**Crear/Aplicar Recursos:**
```bash
# Crear desde un archivo
kubectl apply -f manifest.yaml

# Crear desde un directorio
kubectl apply -f ./manifests/

# Crear desde una URL
kubectl apply -f https://example.com/manifest.yaml
```

**Eliminar Recursos:**
```bash
# Eliminar un pod
kubectl delete pod <pod-name>

# Eliminar desde un archivo
kubectl delete -f manifest.yaml

# Eliminar todos los pods con una etiqueta
kubectl delete pods -l app=nginx
```

**Editar Recursos:**
```bash
# Editar un pod (abre el editor)
kubectl edit pod <pod-name>

# Editar un deployment
kubectl edit deployment <deployment-name>
```

### Comandos Avanzados

**Exec en contenedores:**
```bash
# Ejecutar un comando en un pod
kubectl exec <pod-name> -- ls /app

# Shell interactiva
kubectl exec -it <pod-name> -- /bin/bash

# Exec en un contenedor específico (pod multi-contenedor)
kubectl exec -it <pod-name> -c <container-name> -- /bin/bash
```

**Ver logs:**
```bash
# Ver los logs de un pod
kubectl logs <pod-name>

# Seguir los logs (como tail -f)
kubectl logs -f <pod-name>

# Últimas 100 líneas
kubectl logs --tail=100 <pod-name>

# Logs de un contenedor específico
kubectl logs <pod-name> -c <container-name>
```

**Port forwarding:**
```bash
# Reenviar un puerto local al puerto de un pod
kubectl port-forward <pod-name> 8080:80

# Reenviar a un servicio
kubectl port-forward service/<service-name> 8080:80
```

**Copiar archivos:**
```bash
# Copiar de un pod a local
kubectl cp <pod-name>:/path/to/file ./local-file

# Copiar de local a un pod
kubectl cp ./local-file <pod-name>:/path/to/file
```

### Gestión de Nodos

**Drain (sacar pods de un nodo):**
```bash
# Vaciar un nodo (mover los pods a otros nodos)
kubectl drain <node-name> --ignore-daemonsets

# Ejemplo de uso: antes del mantenimiento de un nodo
```

**Cordon (marcar un nodo como no programable):**
```bash
# Evitar que se programen nuevos pods
kubectl cordon <node-name>

# Permitir la programación de nuevo
kubectl uncordon <node-name>
```

### Gestión de Contextos

**Los contextos combinan:**
- URL del clúster
- Credenciales del usuario
- Namespace (opcional)

**Ver los contextos:**
```bash
# Listar todos los contextos
kubectl config get-contexts

# Mostrar el contexto actual
kubectl config current-context
```

**Cambiar de contexto:**
```bash
# Usar un contexto distinto
kubectl config use-context <context-name>
```

---

## 7. Namespaces

### ¿Qué son los Namespaces?

Los namespaces proporcionan una separación lógica dentro de un clúster. Son como clústeres virtuales dentro de un clúster físico.

### Namespaces por Defecto

```bash
kubectl get namespaces

# Salida:
# NAME              STATUS   AGE
# default           Active   10m
# kube-system       Active   10m
# kube-public       Active   10m
# kube-node-lease   Active   10m
```

**Propósitos de los namespaces:**
- `default` - Namespace por defecto para los recursos
- `kube-system` - Componentes del sistema de Kubernetes
- `kube-public` - Datos accesibles públicamente
- `kube-node-lease` - Datos de heartbeat de los nodos

### Creando Namespaces

**Manifiesto YAML:**
```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: development
```

**Comando:**
```bash
# Crear desde un archivo
kubectl apply -f namespace.yaml

# Crear directamente
kubectl create namespace development
```

### Usando Namespaces

**Especificar el namespace en los comandos:**
```bash
# Obtener pods de un namespace específico
kubectl get pods -n development

# Obtener todos los pods en kube-system
kubectl get pods -n kube-system

# Crear un recurso en un namespace
kubectl apply -f deployment.yaml -n development
```

**Establecer el namespace por defecto:**
```bash
# Establecer el namespace para el contexto actual
kubectl config set-context --current --namespace=development

# Ahora todos los comandos usan el namespace development
kubectl get pods  # Obtiene los pods de development
```

### Casos de Uso de Namespaces

**1. Separación de Entornos:**
```bash
# Distintos entornos
kubectl create namespace dev
kubectl create namespace staging
kubectl create namespace production
```

**2. Separación de Equipos:**
```bash
# Distintos equipos
kubectl create namespace team-a
kubectl create namespace team-b
```

**3. Aislamiento de Recursos:**
- Aplicar cuotas de recursos por namespace
- Establecer network policies por namespace
- Separar cargas de trabajo sensibles

---

## 8. Pods - La Unidad Básica

### ¿Qué es un Pod?

Un **Pod** es la unidad desplegable más pequeña en Kubernetes. Es un conjunto de uno o más contenedores que comparten:
- Namespace de red (misma IP)
- Volúmenes de almacenamiento
- Ciclo de vida

### Pod de un Solo Contenedor

**Manifiesto mínimo de pod:**
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:alpine
```

**Crear el pod:**
```bash
kubectl apply -f pod.yaml

# Comprobar el estado del pod
kubectl get pods

# Salida:
# NAME    READY   STATUS    RESTARTS   AGE
# nginx   1/1     Running   0          10s
```

### Pod con Más Opciones

**Ejemplo completo:**
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:alpine

    # Variables de entorno
    env:
    - name: MY_VARIABLE
      value: "hello"
    - name: MY_OTHER_VAR
      value: "world"

    # Obtener el valor de la downward API
    - name: DD_AGENT_HOST
      valueFrom:
        fieldRef:
          fieldPath: status.hostIP

    # Requests y limits de recursos
    resources:
      requests:
        memory: "64Mi"
        cpu: "200m"
      limits:
        memory: "128Mi"
        cpu: "500m"

    # Health checks
    readinessProbe:
      httpGet:
        path: /
        port: 80
      initialDelaySeconds: 5
      periodSeconds: 10

    livenessProbe:
      tcpSocket:
        port: 80
      initialDelaySeconds: 15
      periodSeconds: 20

    # Puertos expuestos
    ports:
    - containerPort: 80
```

### Requests y Limits de Recursos

**Requests (garantizados):**
- Recursos mínimos garantizados al pod
- El scheduler usa esto para colocar los pods
- El pod no se programará si el nodo no tiene los recursos

**Ejemplo:**
```yaml
resources:
  requests:
    memory: "64Mi"    # 64MB de RAM garantizados
    cpu: "200m"       # 200 millicores garantizados (0.2 CPU)
```

**Limits (máximo):**
- Recursos máximos que el pod puede usar
- El contenedor se mata si excede el límite de memoria
- La CPU se limita (throttled) si excede el límite de CPU

**Ejemplo:**
```yaml
resources:
  limits:
    memory: "128Mi"   # Máx 128MB de RAM (se mata si se excede)
    cpu: "500m"       # Máx 500 millicores (throttled si se excede)
```

**Notas importantes:**
- **Memoria:** El pod se mata (OOMKilled) si excede el límite
- **CPU:** El pod se limita (throttled) pero no se mata
- **1000 millicores = 1 núcleo de CPU**
- Los pods del sistema también usan recursos

### Health Checks

**Liveness Probe:**
- Comprueba si el contenedor está vivo
- Reinicia el contenedor si el probe falla
- Usar para detectar procesos colgados

```yaml
livenessProbe:
  tcpSocket:
    port: 80
  initialDelaySeconds: 15
  periodSeconds: 20
```

**Readiness Probe:**
- Comprueba si el contenedor está listo para el tráfico
- Elimina el pod del servicio si no está listo
- Usar para periodos de calentamiento

```yaml
readinessProbe:
  httpGet:
    path: /
    port: 80
  initialDelaySeconds: 5
  periodSeconds: 10
```

**¿Por qué ambos?**
- **Liveness**: "¿Mi app está congelada/muerta?" → Reiniciarla
- **Readiness**: "¿Mi app está lista para el tráfico?" → Esperar antes de enviar tráfico

---

## 9. Deployments

### ¿Por Qué Deployments?

**Problema con los pods sueltos:**
- Si el pod muere, desaparece para siempre
- Sin recreación automática
- Escalado manual
- Sin rolling updates

**Los Deployments resuelven esto:**
- Recreación automática de pods
- Escalado declarativo
- Rolling updates
- Capacidad de rollback

### Deployment Básico

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:alpine
        ports:
        - containerPort: 80
```

**Secciones clave:**
- `replicas: 3` - Número deseado de pods
- `selector` - Cómo encontrar los pods a gestionar
- `template` - Plantilla del pod (igual que la spec del pod)

### Aplicar el Deployment

```bash
# Crear el deployment
kubectl apply -f deployment.yaml

# Comprobar el deployment
kubectl get deployments

# Salida:
# NAME               READY   UP-TO-DATE   AVAILABLE   AGE
# nginx-deployment   3/3     3            3           1m

# Comprobar los pods
kubectl get pods

# Salida:
# NAME                                READY   STATUS    RESTARTS   AGE
# nginx-deployment-5d59d67564-7x4gh   1/1     Running   0          1m
# nginx-deployment-5d59d67564-klm9p   1/1     Running   0          1m
# nginx-deployment-5d59d67564-tn82w   1/1     Running   0          1m
```

**Observa:**
- Los pods tienen nombres generados con un hash
- Siempre 3 pods en ejecución (replicas: 3)

### Auto-Recuperación en Acción

**Eliminar un pod:**
```bash
# Eliminar un pod
kubectl delete pod nginx-deployment-5d59d67564-7x4gh

# Comprobar los pods inmediatamente
kubectl get pods

# Salida:
# NAME                                READY   STATUS              RESTARTS   AGE
# nginx-deployment-5d59d67564-klm9p   1/1     Running             0          2m
# nginx-deployment-5d59d67564-tn82w   1/1     Running             0          2m
# nginx-deployment-5d59d67564-x9k2l   0/1     ContainerCreating   0          2s

# ¡Nuevo pod creado automáticamente!
```

Kubernetes creó automáticamente un nuevo pod para mantener `replicas: 3`.

### Escalando Deployments

**Escalar hacia arriba:**
```bash
# Escalado imperativo
kubectl scale deployment nginx-deployment --replicas=5

# Comprobar los pods
kubectl get pods
# Ahora muestra 5 pods
```

**Escalado declarativo (recomendado):**
```yaml
# Editar deployment.yaml
spec:
  replicas: 5  # Cambiado de 3 a 5
```

```bash
# Aplicar los cambios
kubectl apply -f deployment.yaml

# Kubernetes crea 2 pods más
```

**Escalar hacia abajo:**
```bash
# Escalar a 2 réplicas
kubectl scale deployment nginx-deployment --replicas=2

# Kubernetes termina 3 pods
```

### Rolling Updates

**Actualizar la imagen:**
```yaml
# deployment.yaml
spec:
  template:
    spec:
      containers:
      - name: nginx
        image: nginx:1.27  # Actualizado desde nginx:alpine
```

```bash
# Aplicar la actualización
kubectl apply -f deployment.yaml

# Observar el rollout
kubectl rollout status deployment nginx-deployment

# Salida:
# Waiting for deployment "nginx-deployment" rollout to finish: 1 out of 3 new replicas have been updated...
# Waiting for deployment "nginx-deployment" rollout to finish: 2 out of 3 new replicas have been updated...
# deployment "nginx-deployment" successfully rolled out
```

**Rollback:**
```bash
# Ver el historial de rollout
kubectl rollout history deployment nginx-deployment

# Rollback a la versión anterior
kubectl rollout undo deployment nginx-deployment

# Rollback a una revisión específica
kubectl rollout undo deployment nginx-deployment --to-revision=2
```

---

## 10. DaemonSets

### ¿Qué es un DaemonSet?

Un **DaemonSet** garantiza que una copia de un pod se ejecute en **todos (o algunos) los nodos**.

**Casos de uso:**
- Agentes de monitoreo (monitoreo de nodos)
- Recolectores de logs (recopilar logs de cada nodo)
- Plugins de red (CNI)
- Daemons de almacenamiento

### Ejemplo de DaemonSet

```yaml
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: nginx-daemonset
spec:
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:alpine
        ports:
        - containerPort: 80
```

**Diferencias clave con el Deployment:**
- Sin campo `replicas` (automáticamente uno por nodo)
- `kind: DaemonSet` en lugar de `kind: Deployment`

### Aplicar el DaemonSet

```bash
# Crear el DaemonSet
kubectl apply -f daemonset.yaml

# Comprobar el DaemonSet
kubectl get daemonsets

# Salida:
# NAME              DESIRED   CURRENT   READY   UP-TO-DATE   AVAILABLE
# nginx-daemonset   3         3         3       3            3

# Comprobar los pods
kubectl get pods -o wide

# Salida:
# NAME                    READY   STATUS    NODE
# nginx-daemonset-abc12   1/1     Running   worker-1
# nginx-daemonset-def34   1/1     Running   worker-2
# nginx-daemonset-ghi56   1/1     Running   worker-3
```

**Observa:**
- Un pod por nodo
- Si añades un nodo, el DaemonSet crea un pod en él
- Si eliminas un pod, el DaemonSet lo recrea en el mismo nodo

### Comportamiento del DaemonSet

**Añadir un nodo:**
```bash
# Añadir un nuevo nodo al clúster
# El DaemonSet crea automáticamente un pod en el nuevo nodo

kubectl get pods -o wide
# Muestra el nuevo pod en el nuevo nodo
```

**Eliminar un pod:**
```bash
# Eliminar un pod
kubectl delete pod nginx-daemonset-abc12

# Comprobar los pods
kubectl get pods -o wide

# La salida muestra un nuevo pod creado en el mismo nodo (worker-1)
```

---

## 11. StatefulSets

### ¿Qué es un StatefulSet?

Un **StatefulSet** gestiona aplicaciones con estado. A diferencia de los Deployments, los StatefulSets proporcionan:
- Identificadores de red estables y únicos
- Almacenamiento estable y persistente
- Despliegue y escalado ordenado y grácil
- Rolling updates ordenados y automatizados

**Casos de uso:**
- Bases de datos (MySQL, PostgreSQL, MongoDB)
- Colas de mensajes (Kafka, RabbitMQ)
- Sistemas distribuidos que requieren identidad de red estable

### Ejemplo de StatefulSet

```yaml
apiVersion: apps/v1
kind: StatefulSet
metadata:
  name: mysql
spec:
  serviceName: "mysql"
  replicas: 1
  selector:
    matchLabels:
      app: mysql
  template:
    metadata:
      labels:
        app: mysql
    spec:
      containers:
      - name: mysql
        image: busybox
        args:
        - sleep
        - infinity
        volumeMounts:
        - name: site-pvc
          mountPath: /data

  # Plantilla de Persistent Volume Claim
  volumeClaimTemplates:
  - metadata:
      name: site-pvc
    spec:
      accessModes: [ "ReadWriteOnce" ]
      storageClassName: "do-block-storage"
      resources:
        requests:
          storage: 5Gi
```

### Características Clave

**1. Persistent Volume Claims:**
```yaml
volumeClaimTemplates:
  - metadata:
      name: site-pvc
    spec:
      accessModes: [ "ReadWriteOnce" ]
      storageClassName: "do-block-storage"
      resources:
        requests:
          storage: 5Gi
```

**Qué pasa:**
1. Kubernetes se conecta a la API del proveedor de nube (DigitalOcean)
2. Crea un volumen de block storage de 5GB
3. Adjunta el volumen al nodo donde se ejecuta el pod
4. Monta el volumen en el pod en `/data`
5. ¡Todo automático!

**2. Nombres de Pod Estables:**
```bash
# Los pods de StatefulSet tienen nombres predecibles
mysql-0
mysql-1
mysql-2
# vs los pods de Deployment
mysql-deployment-abc123
mysql-deployment-def456
```

### Aplicar el StatefulSet

```bash
# Crear el StatefulSet
kubectl apply -f statefulset.yaml

# Comprobar el StatefulSet
kubectl get statefulsets

# Salida:
# NAME    READY   AGE
# mysql   1/1     1m

# Comprobar los pods
kubectl get pods

# Salida:
# NAME      READY   STATUS    RESTARTS   AGE
# mysql-0   1/1     Running   0          1m

# Comprobar los PVCs
kubectl get pvc

# Salida:
# NAME             STATUS   VOLUME                 CAPACITY   STORAGECLASS
# site-pvc-mysql-0 Bound    pvc-abc123             5Gi        do-block-storage
```

### Describir los Eventos del StatefulSet

```bash
kubectl describe statefulset mysql

# Los eventos muestran la creación del volumen:
# Normal  SuccessfulCreate  Created pod: mysql-0
# Normal  ProvisioningSucceeded  Successfully provisioned volume pvc-abc123
```

**Línea de tiempo:**
1. StatefulSet creado
2. PVC creado (solicita un volumen de 5GB)
3. El proveedor de nube aprovisiona el volumen (~2 segundos)
4. Volumen adjuntado al nodo
5. El pod arranca con el volumen montado

### La Magia de la Integración con la Nube

**En el dashboard de DigitalOcean:**
- La sección Volumes muestra el nuevo volumen de 5GB
- Creado automáticamente por Kubernetes
- Adjuntado al nodo correcto
- ¡Todo gestionado a través de Kubernetes!

**Eliminar el StatefulSet:**
```bash
# Eliminar el StatefulSet
kubectl delete statefulset mysql

# El PVC sigue existiendo (no se elimina automáticamente)
kubectl get pvc
# La salida muestra que el PVC sigue ahí

# Eliminar el PVC
kubectl delete pvc site-pvc-mysql-0

# Volumen eliminado del proveedor de nube
```

---

## 12. Services - ClusterIP

### ¿Qué es un Service?

Un **Service** es una abstracción que define un conjunto lógico de pods y una política para acceder a ellos.

**¿Por qué servicios?**
- Los pods tienen IPs dinámicas (cambian al recrearse)
- Se necesita una forma estable de acceder a los pods
- Balanceo de carga entre varios pods

### Service ClusterIP

**ClusterIP** crea una IP interna accesible solo dentro del clúster.

**Ejemplo:**
```yaml
# deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello
spec:
  replicas: 3
  selector:
    matchLabels:
      role: hello
  template:
    metadata:
      labels:
        role: hello
    spec:
      containers:
      - name: hello
        image: gcr.io/google-samples/hello-app:1.0
        ports:
        - containerPort: 8080

---
# service.yaml
apiVersion: v1
kind: Service
metadata:
  name: hello
spec:
  type: ClusterIP  # Tipo por defecto
  selector:
    role: hello  # Coincide con los pods con la etiqueta role: hello
  ports:
  - port: 8080
    targetPort: 8080
```

### Aplicar el Service

```bash
# Aplicar deployment y service
kubectl apply -f deployment.yaml

# Comprobar el deployment
kubectl get deployments

# Salida:
# NAME    READY   UP-TO-DATE   AVAILABLE   AGE
# hello   3/3     3            3           1m

# Comprobar el service
kubectl get services

# Salida:
# NAME    TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE
# hello   ClusterIP   10.245.227.157  <none>        8080/TCP   1m

# Comprobar los pods
kubectl get pods -o wide

# Salida:
# NAME                     READY   STATUS    RESTARTS   AGE   IP
# hello-5d59d67564-7x4gh   1/1     Running   0          1m    10.244.0.205
# hello-5d59d67564-klm9p   1/1     Running   0          1m    10.244.0.33
# hello-5d59d67564-tn82w   1/1     Running   0          1m    10.244.0.12
```

### Cómo Funcionan los Services

**El selector coincide con los pods:**
```yaml
# Selector del service
selector:
  role: hello

# Etiquetas del pod
metadata:
  labels:
    role: hello
```

**El service actúa como balanceador de carga:**
```bash
# Describir el service para ver los endpoints
kubectl describe service hello

# Salida:
# Endpoints: 10.244.0.205:8080,10.244.0.33:8080,10.244.0.12:8080
```

El service automáticamente:
- Encuentra los pods que coinciden con el selector
- Crea la lista de endpoints
- Balancea el tráfico entre ellos

### Probar el Service desde un Pod

**Crear un pod de prueba:**
```bash
# Aplicar el pod de prueba (ubuntu con sleep)
kubectl apply -f random-pod.yaml

# Exec en el pod
kubectl exec -it ubuntu -- /bin/bash
```

**Dentro del pod:**
```bash
# Ping al service (resolución DNS)
ping hello.default.svc.cluster.local

# Devuelve: 10.245.227.157 (ClusterIP)

# Hacer una petición HTTP
curl http://hello:8080

# Salida:
# Hello, world!
# Version: 1.0.0
# Hostname: hello-5d59d67564-7x4gh

# Hacer otra petición
curl http://hello:8080

# Salida:
# Hello, world!
# Version: 1.0.0
# Hostname: hello-5d59d67564-klm9p  # ¡Pod distinto!
```

**El service balancea la carga** entre todos los pods que coinciden.

### DNS del Service

**Formato:**
```
<service-name>.<namespace>.svc.cluster.local
```

**Ejemplos:**
```bash
# Mismo namespace
curl http://hello:8080

# Nombre DNS completo
curl http://hello.default.svc.cluster.local:8080

# Namespace distinto
curl http://hello.production.svc.cluster.local:8080
```

### Actualizaciones del Service

**Eliminar un pod:**
```bash
# Eliminar un pod
kubectl delete pod hello-5d59d67564-7x4gh

# Se crea un nuevo pod con una IP distinta
kubectl get pods -o wide

# Describir el service de nuevo
kubectl describe service hello

# ¡Los endpoints se actualizan automáticamente a la IP del nuevo pod!
```

---

## 13. Services - NodePort

### ¿Qué es NodePort?

**NodePort** expone un servicio en un puerto estático en la IP de cada nodo.

**Casos de uso:**
- Acceso externo rápido sin balanceador de carga
- Desarrollo/pruebas
- Cuando conoces las IPs de los nodos

### Service NodePort

```yaml
apiVersion: v1
kind: Service
metadata:
  name: hello
spec:
  type: NodePort
  selector:
    role: hello
  ports:
  - port: 8080
    targetPort: 8080
    nodePort: 30000  # Puerto en cada nodo (30000-32767)
```

### Aplicar el Service NodePort

```bash
# Aplicar el service
kubectl apply -f nodeport-service.yaml

# Comprobar el service
kubectl get services

# Salida:
# NAME    TYPE       CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
# hello   NodePort   10.245.227.157  <none>        8080:30000/TCP   1m

# Obtener las IPs de los nodos
kubectl get nodes -o wide

# Salida:
# NAME       STATUS   ROLES    EXTERNAL-IP
# worker-1   Ready    <none>   192.168.1.10
# worker-2   Ready    <none>   192.168.1.11
# worker-3   Ready    <none>   192.168.1.12
```

### Acceder al Service

**Desde fuera del clúster:**
```bash
# Acceder a cualquier IP de nodo en el puerto 30000
curl http://192.168.1.10:30000
curl http://192.168.1.11:30000
curl http://192.168.1.12:30000

# Todos enrutan al service, balanceado a los pods
```

**Cómo funciona:**
1. El tráfico llega a cualquier nodo en el puerto 30000
2. `kube-proxy` intercepta el tráfico
3. Enruta al pod correcto (puede estar en un nodo distinto)
4. Balancea la carga entre todos los pods que coinciden

### Limitaciones de NodePort

**Problemas:**
- Necesitas conocer las IPs de los nodos
- La IP del nodo puede cambiar
- No es ideal para producción
- Rango de puertos limitado (30000-32767)

**Mejores alternativas:**
- Service LoadBalancer (nube)
- Ingress controller

---

## 14. Services - LoadBalancer

### ¿Qué es LoadBalancer?

**LoadBalancer** crea un balanceador de carga externo en tu proveedor de nube.

**Características:**
- Una sola IP externa
- Integración automática con la nube
- El proveedor de nube gestiona el balanceador de carga
- Listo para producción

### Service LoadBalancer

```yaml
apiVersion: v1
kind: Service
metadata:
  name: hello
spec:
  type: LoadBalancer
  selector:
    role: hello
  ports:
  - port: 8080
    targetPort: 8080
```

### Aplicar el Service LoadBalancer

```bash
# Aplicar el service
kubectl apply -f loadbalancer-service.yaml

# Comprobar el service (puede mostrar <pending>)
kubectl get services

# Salida:
# NAME    TYPE           CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
# hello   LoadBalancer   10.245.227.157  <pending>     8080:30123/TCP   10s

# Espera un momento, comprueba de nuevo
kubectl get services

# Salida:
# NAME    TYPE           CLUSTER-IP      EXTERNAL-IP      PORT(S)          AGE
# hello   LoadBalancer   10.245.227.157  134.209.123.45   8080:30123/TCP   2m
```

### ¿Qué Pasó?

**Tras bambalinas:**
1. Kubernetes contactó la API del proveedor de nube (DigitalOcean)
2. Creó un recurso de balanceador de carga
3. Configuró el balanceador para enrutar a los nodos
4. Asignó una IP externa
5. ¡Todo automático!

**En el dashboard del proveedor de nube:**
- Aparece un nuevo balanceador de carga
- Configurado con las IPs de los nodos como backends
- Health checks configurados
- ¡Todo gestionado por Kubernetes!

### Acceder al Service

**Desde cualquier lugar:**
```bash
# Acceder vía la IP externa
curl http://134.209.123.45:8080

# Salida:
# Hello, world!
# Version: 1.0.0
# Hostname: hello-5d59d67564-7x4gh

# Hacer varias peticiones
curl http://134.209.123.45:8080
curl http://134.209.123.45:8080
curl http://134.209.123.45:8080

# Balanceado entre todos los pods
```

### Beneficios de LoadBalancer

**Ventajas:**
- Una sola IP estable
- Gestionado por el proveedor de nube
- Alta disponibilidad
- Health checks automáticos
- Listo para producción

**Usar para:**
- Aplicaciones de producción
- Servicios de cara al público
- Cuando necesitas acceso externo

**Apuntar un dominio a la IP:**
```bash
# Añadir un registro DNS A
myapp.example.com → 134.209.123.45

# Ahora accesible vía dominio
curl http://myapp.example.com:8080
```

---

## 15. Ingress

### ¿Qué es Ingress?

**Ingress** proporciona enrutamiento HTTP/HTTPS a los servicios basándose en hostnames y rutas.

**¿Por qué Ingress?**
- Un solo balanceador de carga para muchos servicios
- Enrutamiento basado en rutas (`/api`, `/frontend`)
- Enrutamiento basado en host (`api.example.com`, `www.example.com`)
- Terminación TLS/SSL
- Más rentable que varios LoadBalancers

### Ingress Controller

**Requerido:** El ingress controller debe instalarse primero.

**Controllers populares:**
- nginx-ingress
- traefik
- kong
- HAProxy

**Instalar nginx-ingress (DigitalOcean):**
1. Ve al dashboard del clúster
2. Haz clic en "Add-ons" o "Applications"
3. Selecciona "nginx-ingress-controller"
4. Haz clic en "Install"

**O con Helm:**
```bash
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm install nginx-ingress ingress-nginx/ingress-nginx
```

### Ejemplo de Configuración

**Dos deployments, dos services:**
```yaml
# deployment hello-v1
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-v1
spec:
  replicas: 3
  selector:
    matchLabels:
      app: hello
      version: v1
  template:
    metadata:
      labels:
        app: hello
        version: v1
    spec:
      containers:
      - name: hello
        image: gcr.io/google-samples/hello-app:1.0
        ports:
        - containerPort: 8080

---
# service hello-v1
apiVersion: v1
kind: Service
metadata:
  name: hello-v1
spec:
  selector:
    app: hello
    version: v1
  ports:
  - port: 8080
    targetPort: 8080

---
# deployment hello-v2
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-v2
spec:
  replicas: 3
  selector:
    matchLabels:
      app: hello
      version: v2
  template:
    metadata:
      labels:
        app: hello
        version: v2
    spec:
      containers:
      - name: hello
        image: gcr.io/google-samples/hello-app:2.0
        ports:
        - containerPort: 8080

---
# service hello-v2
apiVersion: v1
kind: Service
metadata:
  name: hello-v2
spec:
  selector:
    app: hello
    version: v2
  ports:
  - port: 8080
    targetPort: 8080
```

### Recurso Ingress

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: hello-app
spec:
  rules:
  - http:
      paths:
      - path: /v1
        pathType: Prefix
        backend:
          service:
            name: hello-v1
            port:
              number: 8080
      - path: /v2
        pathType: Prefix
        backend:
          service:
            name: hello-v2
            port:
              number: 8080
```

### Aplicar el Ingress

```bash
# Aplicar deployments y services
kubectl apply -f deployments-services.yaml

# Aplicar el ingress
kubectl apply -f ingress.yaml

# Comprobar el ingress
kubectl get ingress

# Salida:
# NAME        CLASS   HOSTS   ADDRESS          PORTS   AGE
# hello-app   nginx   *       134.209.123.45   80      1m
```

### Cómo Funciona

**El ingress controller:**
- Ejecuta un pod nginx en el clúster
- Tiene un service LoadBalancer (obtiene una IP externa)
- Observa los recursos Ingress
- Configura nginx automáticamente
- Enruta el tráfico según las reglas

```bash
# Comprobar el namespace ingress-nginx
kubectl get pods -n ingress-nginx

# Salida:
# NAME                                        READY   STATUS
# nginx-ingress-controller-abc123             1/1     Running

kubectl get svc -n ingress-nginx

# Salida:
# NAME                    TYPE           EXTERNAL-IP      PORT(S)
# nginx-ingress-controller LoadBalancer  134.209.123.45   80:30080/TCP
```

### Probar el Ingress

```bash
# Obtener la IP del ingress
INGRESS_IP=$(kubectl get ingress hello-app -o jsonpath='{.status.loadBalancer.ingress[0].ip}')

# Probar la ruta /v1
curl http://$INGRESS_IP/v1

# Salida:
# Hello, world!
# Version: 1.0.0
# Hostname: hello-v1-abc123

# Probar la ruta /v2
curl http://$INGRESS_IP/v2

# Salida:
# Hello, world!
# Version: 2.0.0
# Hostname: hello-v2-def456

# Probar la ruta raíz (sin regla)
curl http://$INGRESS_IP/

# Salida: 404 Not Found
```

### Funciones Avanzadas de Ingress

**Enrutamiento basado en host:**
```yaml
spec:
  rules:
  - host: api.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: api-service
            port:
              number: 8080
  - host: www.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: frontend-service
            port:
              number: 80
```

**TLS/SSL:**
```yaml
spec:
  tls:
  - hosts:
    - example.com
    secretName: example-tls
  rules:
  - host: example.com
    http:
      paths:
      - path: /
        backend:
          service:
            name: web
            port:
              number: 80
```

---

## 16. Redes en Kubernetes

### Redes de Pods

**Cada pod obtiene su propia dirección IP.**

```bash
kubectl get pods -o wide

# Salida:
# NAME              READY   STATUS    IP
# pod-1             1/1     Running   10.244.0.10
# pod-2             1/1     Running   10.244.0.11
# pod-3             1/1     Running   10.244.1.10  # Nodo distinto
```

**Características de la IP del pod:**
- Única dentro del clúster
- Accesible desde cualquier pod
- Cambia cuando el pod se recrea
- No accesible directamente desde fuera del clúster

### Container Network Interface (CNI)

**Los plugins CNI** crean la red de pods:
- Calico (el más común)
- Flannel
- Weave
- Cilium

**Qué hace CNI:**
- Asigna una IP a cada pod
- Crea rutas entre los nodos
- Habilita la comunicación pod-a-pod
- Funciona entre distintos nodos

### Cómo se Comunican los Pods

**Clúster de ejemplo:**
```
Worker 1 (IP: 192.168.1.10)
├─ Pod A (IP: 10.244.0.10)
└─ Pod B (IP: 10.244.0.11)

Worker 2 (IP: 192.168.1.11)
└─ Pod C (IP: 10.244.1.10)
```

**Pod A → Pod C:**
1. El Pod A envía un paquete a 10.244.1.10
2. CNI enruta el paquete al Worker 2
3. El Worker 2 lo entrega al Pod C
4. ¡Todo automático vía rutas IP!

### IP del Contenedor vs del Pod

**Importante:** Los contenedores en el mismo pod comparten la IP.

**Pod de un solo contenedor:**
```yaml
spec:
  containers:
  - name: nginx
    image: nginx
    # El pod obtiene una IP: 10.244.0.10
```

**Pod multi-contenedor:**
```yaml
spec:
  containers:
  - name: nginx
    image: nginx
    ports:
    - containerPort: 80
  - name: sidecar
    image: busybox
    ports:
    - containerPort: 8080
    # Ambos comparten la misma IP: 10.244.0.10
    # ¡No pueden usar ambos el puerto 80!
```

### kube-proxy

**kube-proxy** se ejecuta en cada nodo y gestiona las redes de los servicios.

**Qué hace:**
- Implementa la abstracción del service
- Crea reglas de iptables/IPVS
- Enruta el tráfico del servicio a los pods
- Habilita NodePort y LoadBalancer

**Ejemplo:**
```bash
# El service tiene ClusterIP: 10.245.227.157
# Los pods tienen IPs: 10.244.0.10, 10.244.0.11, 10.244.0.12

# kube-proxy crea reglas de iptables:
# Tráfico a 10.245.227.157:8080
#   → Balancear a:
#     - 10.244.0.10:8080
#     - 10.244.0.11:8080
#     - 10.244.0.12:8080
```

### etcd Almacena el Estado de la Red

**etcd** es la fuente de la verdad:
- IPs de los pods
- IPs de los services
- Listas de endpoints
- Network policies

**Los plugins CNI leen de etcd** para configurar la red.

---

## 17. ConfigMaps

### ¿Qué es un ConfigMap?

**ConfigMap** almacena datos de configuración como pares clave-valor.

**Casos de uso:**
- Archivos de configuración de aplicaciones
- Variables de entorno
- Argumentos de línea de comandos
- Configuración no sensible

### Crear un ConfigMap

**Desde un manifiesto:**
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: game-demo
data:
  # Clave-valor simple
  player_initial_lives: "3"
  ui_properties_file_name: "user-interface.properties"

  # Claves tipo archivo
  game.properties: |
    enemy.types=aliens,monsters
    player.maximum-lives=5

  user-interface.properties: |
    color.good=purple
    color.bad=yellow
    allow.textmode=true
```

**Desde la línea de comandos:**
```bash
# Desde valores literales
kubectl create configmap my-config \
  --from-literal=key1=value1 \
  --from-literal=key2=value2

# Desde un archivo
kubectl create configmap app-config \
  --from-file=config.properties

# Desde un directorio
kubectl create configmap configs \
  --from-file=./config-dir/
```

### Usar un ConfigMap como Variables de Entorno

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:alpine

    # Variables de entorno desde el ConfigMap
    env:
    - name: PLAYER_INITIAL_LIVES
      valueFrom:
        configMapKeyRef:
          name: game-demo
          key: player_initial_lives

    - name: UI_PROPERTIES_FILE_NAME
      valueFrom:
        configMapKeyRef:
          name: game-demo
          key: ui_properties_file_name
```

**Verificar:**
```bash
# Aplicar el ConfigMap y el Pod
kubectl apply -f configmap.yaml
kubectl apply -f pod.yaml

# Comprobar las variables de entorno
kubectl exec nginx -- env | grep PLAYER

# Salida:
# PLAYER_INITIAL_LIVES=3
```

### Usar un ConfigMap como Archivos

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:alpine

    # Montar el ConfigMap como volumen
    volumeMounts:
    - name: config
      mountPath: /config
      readOnly: true

  volumes:
  - name: config
    configMap:
      name: game-demo
      items:
      - key: game.properties
        path: game.properties
      - key: user-interface.properties
        path: user-interface.properties
```

**Verificar:**
```bash
# Exec en el pod
kubectl exec -it nginx -- /bin/sh

# Comprobar los archivos
ls /config
# Salida: game.properties  user-interface.properties

cat /config/game.properties
# Salida:
# enemy.types=aliens,monsters
# player.maximum-lives=5
```

### Casos de Uso de ConfigMap

**1. Distintas configuraciones por entorno:**
```bash
# Desarrollo
kubectl create configmap app-config \
  --from-literal=db.host=dev-db.example.com \
  -n development

# Producción
kubectl create configmap app-config \
  --from-literal=db.host=prod-db.example.com \
  -n production
```

**2. Archivos de configuración de aplicaciones:**
```yaml
# nginx.conf como ConfigMap
apiVersion: v1
kind: ConfigMap
metadata:
  name: nginx-config
data:
  nginx.conf: |
    server {
      listen 80;
      location / {
        proxy_pass http://backend:8080;
      }
    }
```

---

## 18. Secrets

### ¿Qué es un Secret?

**Secret** almacena datos sensibles codificados en base64.

**Importante:** ¡Base64 **no es cifrado**!
- Fácil de decodificar
- No es seguro por sí mismo
- Mejor que texto plano en Git
- Deberías usar gestión externa de secretos en producción

### Crear un Secret

**Desde un manifiesto:**
```yaml
apiVersion: v1
kind: Secret
metadata:
  name: db-credentials
type: Opaque
data:
  username: YWRtaW4=        # admin (base64)
  password: c3VwZXJwYXNzd29yZA==  # superpassword (base64)
```

**Codificar valores:**
```bash
echo -n 'admin' | base64
# Salida: YWRtaW4=

echo -n 'superpassword' | base64
# Salida: c3VwZXJwYXNzd29yZA==
```

**Desde la línea de comandos:**
```bash
# Crear un secret desde valores literales
kubectl create secret generic db-credentials \
  --from-literal=username=admin \
  --from-literal=password=superpassword

# Codificado automáticamente en base64
```

### Usar un Secret como Variables de Entorno

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:alpine

    # Variables de entorno desde el Secret
    env:
    - name: MYSQL_USER
      valueFrom:
        secretKeyRef:
          name: db-credentials
          key: username

    - name: MYSQL_PASSWORD
      valueFrom:
        secretKeyRef:
          name: db-credentials
          key: password
```

**Verificar:**
```bash
# Aplicar el secret y el pod
kubectl apply -f secret.yaml
kubectl apply -f pod.yaml

# Comprobar las variables de entorno
kubectl exec nginx -- env | grep MYSQL

# Salida:
# MYSQL_USER=admin
# MYSQL_PASSWORD=superpassword
# (Decodificado automáticamente de base64)
```

### Usar un Secret como Archivos

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:alpine
    volumeMounts:
    - name: secrets
      mountPath: /etc/secrets
      readOnly: true

  volumes:
  - name: secrets
    secret:
      secretName: db-credentials
```

**Verificar:**
```bash
# Comprobar los archivos
kubectl exec nginx -- ls /etc/secrets
# Salida: username  password

kubectl exec nginx -- cat /etc/secrets/username
# Salida: admin
```

### Buenas Prácticas de Secrets

**❌ No hagas:**
- Almacenar secretos en Git (ni siquiera en base64)
- Usar secretos para datos muy sensibles sin cifrado
- Compartir valores de secretos en chat/correo

**✅ Haz:**
- Usar gestión externa de secretos (Sealed Secrets, Vault)
- Rotar los secretos regularmente
- Limitar el acceso con RBAC
- Usar distintos secretos por entorno

**Mejores alternativas:**
- **Sealed Secrets** (cifra los secretos)
- **External Secrets Operator** (sincroniza desde Vault/AWS Secrets Manager)
- **SOPS** (cifra los archivos de secretos)

---

## 19. Volúmenes Persistentes

### Almacenamiento en Kubernetes

**Almacenamiento efímero (por defecto):**
- Los datos viven con el contenedor
- Se pierden cuando el pod se elimina
- Bien para apps sin estado

**Almacenamiento persistente:**
- Los datos sobreviven a la eliminación del pod
- Requerido para bases de datos
- Gestionado a través de PV y PVC

### Conceptos de Almacenamiento

**1. StorageClass:**
- Define el tipo de almacenamiento
- Se mapea al almacenamiento del proveedor de nube
- Habilita el aprovisionamiento dinámico

**2. PersistentVolume (PV):**
- Recurso de almacenamiento real
- Creado manual o dinámicamente
- Ciclo de vida independiente de los pods

**3. PersistentVolumeClaim (PVC):**
- Solicitud de almacenamiento
- Se enlaza a un PV
- Usado por los pods

### StatefulSet con PVC

```yaml
apiVersion: apps/v1
kind: StatefulSet
metadata:
  name: mysql
spec:
  serviceName: "mysql"
  replicas: 1
  selector:
    matchLabels:
      app: mysql
  template:
    metadata:
      labels:
        app: mysql
    spec:
      containers:
      - name: mysql
        image: busybox
        args:
        - sleep
        - infinity
        volumeMounts:
        - name: site-pvc
          mountPath: /data

  # Plantilla de PVC
  volumeClaimTemplates:
  - metadata:
      name: site-pvc
    spec:
      accessModes: [ "ReadWriteOnce" ]
      storageClassName: "do-block-storage"  # Almacenamiento de DigitalOcean
      resources:
        requests:
          storage: 5Gi
```

### Cómo Funciona

**1. Aplicar el StatefulSet:**
```bash
kubectl apply -f statefulset.yaml

# Observar la creación del pod
kubectl get pods -w

# Salida:
# NAME      READY   STATUS              RESTARTS   AGE
# mysql-0   0/1     Pending             0          5s
# mysql-0   0/1     ContainerCreating   0          35s
# mysql-0   1/1     Running             0          37s
```

**2. Comprobar los eventos:**
```bash
kubectl describe pod mysql-0

# Events:
# Normal  Scheduled  Successfully assigned default/mysql-0 to worker-1
# Normal  ProvisioningSucceeded  Successfully provisioned volume pvc-abc123
# Normal  Pulled  Container image "busybox" already present
# Normal  Created  Created container mysql
# Normal  Started  Started container mysql
```

**Línea de tiempo:**
- 0s: Pod creado, sin PVC → Pending
- 2s: PVC creado, solicitando volumen
- El proveedor de nube crea un volumen de 5GB
- 35s: Volumen listo, adjuntado al nodo
- 37s: El pod arranca con el volumen montado

**3. Verificar el PVC:**
```bash
kubectl get pvc

# Salida:
# NAME             STATUS   VOLUME       CAPACITY   STORAGECLASS
# site-pvc-mysql-0 Bound    pvc-abc123   5Gi        do-block-storage
```

**4. Describir el PVC:**
```bash
kubectl describe pvc site-pvc-mysql-0

# Events:
# Normal  Provisioning  External provisioner is provisioning volume
# Normal  ProvisioningSucceeded  Successfully provisioned volume pvc-abc123
```

### Integración con la Nube

**En el dashboard del proveedor de nube (DigitalOcean):**
1. Navega a "Volumes"
2. Verás el nuevo volumen de 5GB
3. Muestra la conexión al nodo
4. ¡Creado y gestionado por Kubernetes!

**Eliminar el StatefulSet:**
```bash
# Eliminar el StatefulSet
kubectl delete statefulset mysql

# ¡El PVC sigue existiendo!
kubectl get pvc
# Salida: site-pvc-mysql-0 sigue ahí

# Los datos persisten aunque el StatefulSet desaparezca
```

**Eliminar el PVC:**
```bash
# Eliminar el PVC
kubectl delete pvc site-pvc-mysql-0

# Esto también elimina el volumen de la nube
# (Comprueba el dashboard del proveedor de nube - el volumen desapareció)
```

### Modos de Acceso

**ReadWriteOnce (RWO):**
- Montado por un solo nodo
- Lectura y escritura
- El más común

**ReadOnlyMany (ROX):**
- Montado por varios nodos
- Solo lectura

**ReadWriteMany (RWX):**
- Montado por varios nodos
- Lectura y escritura
- No soportado por todas las storage classes

---

## 20. Kustomize

### ¿Qué es Kustomize?

**Kustomize** personaliza manifiestos de Kubernetes sin modificar los originales.

**Características:**
- Integrado en kubectl
- Sin plantillas (YAML puro)
- Overlays para distintos entornos
- Genera ConfigMaps y Secrets
- Parchea recursos existentes

### Kustomization Básica

**Estructura de directorios:**
```
.
├── kustomization.yaml
├── deployment.yaml
└── service.yaml
```

**kustomization.yaml:**
```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

# Recursos a incluir
resources:
- deployment.yaml
- service.yaml

# Añadir etiquetas a todos los recursos
commonLabels:
  app: example

# Generar un secret
secretGenerator:
- name: db-credentials
  literals:
  - username=admin
  - password=superpassword

# Cambiar la imagen
images:
- name: nginx
  newTag: latest
```

### Construir y Aplicar

**Construir (previsualizar):**
```bash
kubectl kustomize .

# Salida: YAML completo con las transformaciones aplicadas
```

**Aplicar:**
```bash
kubectl apply -k .

# Igual que:
# kubectl kustomize . | kubectl apply -f -
```

### Secret Generado

**Antes de kustomize:**
```yaml
# Crearías manualmente:
apiVersion: v1
kind: Secret
metadata:
  name: db-credentials
data:
  username: YWRtaW4=
  password: c3VwZXJwYXNzd29yZA==
```

**Con kustomize:**
```yaml
# kustomization.yaml
secretGenerator:
- name: db-credentials
  literals:
  - username=admin
  - password=superpassword
```

**El secret generado tiene un hash:**
```bash
kubectl get secrets

# Salida:
# NAME                        TYPE     DATA   AGE
# db-credentials-6gt2m9k8hf   Opaque   2      1m
```

**¿Por qué el hash?**
- Nuevo secret en cada cambio
- Fuerza la recreación del pod
- Garantiza que los pods usen la última configuración

### Cambiar el Secret

**Modificar la contraseña:**
```yaml
secretGenerator:
- name: db-credentials
  literals:
  - username=admin
  - password=newpassword  # ¡Cambiado!
```

**Aplicar:**
```bash
kubectl apply -k .

# Nuevo secret creado: db-credentials-8h4k2n9f5d
# El pod referencia el nuevo secret
# El pod se recrea automáticamente
```

### Transformación de Imagen

**Deployment original:**
```yaml
spec:
  containers:
  - name: nginx
    image: nginx:alpine
```

**kustomization.yaml:**
```yaml
images:
- name: nginx
  newTag: latest  # Cambiar el tag a latest
```

**Construir:**
```bash
kubectl kustomize .

# La salida muestra:
spec:
  containers:
  - name: nginx
    image: nginx:latest  # ¡Tag cambiado!
```

### Overlays (Entornos)

**Estructura de directorios:**
```
.
├── base/
│   ├── kustomization.yaml
│   ├── deployment.yaml
│   └── service.yaml
├── overlays/
│   ├── dev/
│   │   └── kustomization.yaml
│   └── prod/
│       └── kustomization.yaml
```

**base/kustomization.yaml:**
```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

resources:
- deployment.yaml
- service.yaml
```

**overlays/dev/kustomization.yaml:**
```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

bases:
- ../../base

namePrefix: dev-
replicas:
- name: nginx
  count: 1
```

**overlays/prod/kustomization.yaml:**
```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

bases:
- ../../base

namePrefix: prod-
replicas:
- name: nginx
  count: 5
```

**Aplicar:**
```bash
# Desarrollo
kubectl apply -k overlays/dev

# Producción
kubectl apply -k overlays/prod
```

---

## 21. Gestor de Paquetes Helm

### ¿Qué es Helm?

**Helm** es un gestor de paquetes para Kubernetes (como apt, yum, brew).

**Características:**
- Empaqueta aplicaciones como "charts"
- Comparte charts vía repositorios
- Plantillas de manifiestos con valores
- Versiona y hace rollback de releases
- Gestiona dependencias

### ¿Por Qué Helm?

**Sin Helm:**
- Copiar/pegar manifiestos
- Modificar manualmente para cada entorno
- Difícil compartir aplicaciones
- Apps complejas con múltiples recursos

**Con Helm:**
- Un comando para instalar
- Personalizar con valores
- Upgrades y rollbacks fáciles
- Charts de la comunidad disponibles

### Instalar Helm

```bash
# macOS
brew install helm

# Linux
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash

# Verificar
helm version
```

### Usando Charts de Helm

**Añadir un repositorio:**
```bash
# Añadir el repositorio de charts stable
helm repo add stable https://charts.helm.sh/stable

# Añadir los charts de bitnami
helm repo add bitnami https://charts.bitnami.com/bitnami

# Actualizar los repos
helm repo update
```

**Buscar charts:**
```bash
# Buscar nginx
helm search repo nginx

# Salida:
# NAME                    CHART VERSION   APP VERSION     DESCRIPTION
# bitnami/nginx           9.5.0           1.21.1          Chart for NGINX...
```

**Instalar un chart:**
```bash
# Instalar nginx
helm install my-nginx bitnami/nginx

# Instalar con valores personalizados
helm install my-nginx bitnami/nginx \
  --set service.type=LoadBalancer \
  --set replicaCount=3
```

**Listar releases:**
```bash
helm list

# Salida:
# NAME      NAMESPACE  REVISION  STATUS    CHART         APP VERSION
# my-nginx  default    1         deployed  nginx-9.5.0   1.21.1
```

**Actualizar un release:**
```bash
helm upgrade my-nginx bitnami/nginx \
  --set replicaCount=5
```

**Rollback:**
```bash
# Rollback a la versión anterior
helm rollback my-nginx

# Rollback a una revisión específica
helm rollback my-nginx 1
```

**Desinstalar:**
```bash
helm uninstall my-nginx
```

### Creando Charts

**Crear un nuevo chart:**
```bash
helm create my-app

# Crea la estructura de directorios:
# my-app/
# ├── Chart.yaml
# ├── values.yaml
# ├── templates/
# │   ├── deployment.yaml
# │   ├── service.yaml
# │   └── ...
```

**Chart.yaml:**
```yaml
apiVersion: v2
name: my-app
description: My application
version: 0.1.0
appVersion: "1.0"
```

**values.yaml:**
```yaml
replicaCount: 3

image:
  repository: nginx
  tag: alpine
  pullPolicy: IfNotPresent

service:
  type: ClusterIP
  port: 80
```

**templates/deployment.yaml:**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: {{ .Release.Name }}
spec:
  replicas: {{ .Values.replicaCount }}
  template:
    spec:
      containers:
      - name: {{ .Chart.Name }}
        image: "{{ .Values.image.repository }}:{{ .Values.image.tag }}"
```

---

## 22. Herramientas de Kubernetes

### Lens - IDE de Kubernetes

**¿Qué es Lens?**
- IDE de escritorio para Kubernetes
- Gestión visual del clúster
- Soporte multi-clúster
- Terminal integrada
- Monitoreo de recursos

**Características:**
- Explorar todos los recursos
- Ver logs en tiempo real
- Editar manifiestos visualmente
- GUI de port forwarding
- Métricas y gráficos

**Instalación:**
- Descargar desde [k8slens.dev](https://k8slens.dev)
- Añadir el clúster desde kubeconfig
- Explorar los recursos visualmente

**¿Por qué usar Lens?**
- Más fácil que kubectl para explorar
- Genial para aprender
- Retroalimentación visual
- Gestión multi-clúster

### stern - Logs de Múltiples Pods

**¿Qué es stern?**
- Seguimiento mejorado de logs para Kubernetes
- Seguir los logs de varios pods
- Salida con codificación por colores
- Selección de pods por regex

**Instalación:**
```bash
# macOS
brew install stern

# Linux
wget https://github.com/stern/stern/releases/download/v1.21.0/stern_1.21.0_linux_amd64.tar.gz
tar -xvf stern_*.tar.gz
sudo mv stern /usr/local/bin/
```

**Uso:**
```bash
# Seguir los logs de todos los pods que coinciden con un patrón
stern hello

# Salida:
# hello-v1-abc123 Hello from v1!
# hello-v1-def456 Hello from v1!
# hello-v2-ghi789 Hello from v2!

# Con codificación por colores por pod
```

**¿Por qué stern vs kubectl logs?**
```bash
# kubectl - un solo pod
kubectl logs -f hello-v1-abc123

# stern - todos los pods que coinciden
stern hello-v1
# Muestra los logs de TODOS los pods hello-v1-*
```

### plugins de kubectl

**krew - Gestor de plugins:**
```bash
# Instalar krew
kubectl krew install krew

# Buscar plugins
kubectl krew search

# Instalar plugins
kubectl krew install ctx
kubectl krew install ns
kubectl krew install tree
```

**Plugins útiles:**

**ctx (cambio de contexto):**
```bash
# Listar contextos
kubectl ctx

# Cambiar de contexto
kubectl ctx my-cluster
```

**ns (cambio de namespace):**
```bash
# Listar namespaces
kubectl ns

# Cambiar de namespace
kubectl ns development
```

**tree (relaciones de recursos):**
```bash
# Mostrar el árbol de recursos
kubectl tree deployment nginx
```

### kubectx y kubens

**kubectx - Cambio de contexto:**
```bash
# Instalar
brew install kubectx

# Listar contextos
kubectx

# Cambiar de contexto
kubectx staging

# Cambiar al anterior
kubectx -
```

**kubens - Cambio de namespace:**
```bash
# Listar namespaces
kubens

# Cambiar de namespace
kubens development

# Cambiar al anterior
kubens -
```

---

## 23. Buenas Prácticas

### Gestión de Recursos

**Siempre establece requests y limits:**
```yaml
resources:
  requests:
    memory: "64Mi"
    cpu: "100m"
  limits:
    memory: "128Mi"
    cpu: "500m"
```

**Por qué:**
- Previene la escasez de recursos
- Habilita una programación adecuada
- Protege la estabilidad del clúster

### Health Checks

**Siempre define probes:**
```yaml
livenessProbe:
  httpGet:
    path: /health
    port: 8080
  initialDelaySeconds: 30
  periodSeconds: 10

readinessProbe:
  httpGet:
    path: /ready
    port: 8080
  initialDelaySeconds: 5
  periodSeconds: 5
```

**Por qué:**
- Recuperación automática de fallos
- Despliegues sin tiempo de inactividad
- Mejor balanceo de carga

### Usa Deployments, No Pods

**❌ No hagas:**
```yaml
apiVersion: v1
kind: Pod
# Los pods sueltos no se reinician automáticamente
```

**✅ Haz:**
```yaml
apiVersion: apps/v1
kind: Deployment
# Auto-recuperación, escalado, actualizaciones
```

### Organización de Namespaces

**Estructura:**
```bash
# Por entorno
kubectl create namespace dev
kubectl create namespace staging
kubectl create namespace prod

# O por equipo
kubectl create namespace team-a
kubectl create namespace team-b
```

### Etiquetas y Selectores

**Usa etiquetas significativas:**
```yaml
metadata:
  labels:
    app: nginx
    version: v1
    environment: production
    tier: frontend
```

**Beneficios:**
- Filtrado fácil
- Selectores de servicio
- Agrupación de recursos

### ConfigMaps y Secrets

**Externaliza la configuración:**
```yaml
# ❌ No pongas valores fijos
env:
- name: DB_HOST
  value: "mysql.example.com"

# ✅ Usa un ConfigMap
env:
- name: DB_HOST
  valueFrom:
    configMapKeyRef:
      name: app-config
      key: db.host
```

### Buenas Prácticas de Seguridad

**1. Usa contenedores no-root:**
```yaml
securityContext:
  runAsNonRoot: true
  runAsUser: 1000
```

**2. Sistema de archivos de solo lectura:**
```yaml
securityContext:
  readOnlyRootFilesystem: true
```

**3. Elimina capacidades:**
```yaml
securityContext:
  capabilities:
    drop:
    - ALL
```

### Control de Versiones

**Almacena los manifiestos en Git:**
```bash
git/
├── base/
│   └── deployment.yaml
├── overlays/
│   ├── dev/
│   └── prod/
└── README.md
```

**Beneficios:**
- Rastrear cambios
- Revisión de código
- Capacidad de rollback
- Infraestructura como código

### Monitoreo y Logging

**Instalar monitoreo:**
```bash
# Metrics server
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

# Comprobar las métricas
kubectl top nodes
kubectl top pods
```

**Logging centralizado:**
- Usa stern para desarrollo
- Stack ELK/EFK para producción
- Logging del proveedor de nube

### Buenas Prácticas y Actualizaciones 2025

**Versiones de API Actuales (a partir de Kubernetes 1.29-1.31):**
```yaml
# Usa estas versiones de API estables
apps/v1                    # Deployments, StatefulSets, DaemonSets, ReplicaSets
v1                         # Pods, Services, ConfigMaps, Secrets, PersistentVolumes
networking.k8s.io/v1       # Ingress, NetworkPolicy
batch/v1                   # Jobs, CronJobs
storage.k8s.io/v1          # StorageClass
rbac.authorization.k8s.io/v1  # Roles, RoleBindings, ClusterRoles
```

**APIs Obsoletas a Evitar:**
- `extensions/v1beta1` - Eliminada en Kubernetes 1.22+
- `networking.k8s.io/v1beta1` (Ingress) - Usa `networking.k8s.io/v1`
- `batch/v1beta1` (CronJob) - Usa `batch/v1`

**Buenas Prácticas de Seguridad 2025:**
```yaml
# Siempre establece el security context
securityContext:
  runAsNonRoot: true
  runAsUser: 1000
  allowPrivilegeEscalation: false
  capabilities:
    drop:
      - ALL
  readOnlyRootFilesystem: true
  seccompProfile:
    type: RuntimeDefault
```

**Optimización de Recursos:**
```yaml
# Usa las recomendaciones del Vertical Pod Autoscaler (VPA)
# Establece las clases QoS apropiadas
resources:
  requests:
    memory: "256Mi"
    cpu: "250m"
  limits:
    memory: "512Mi"
    cpu: "500m"
# Esto crea la clase QoS "Burstable" (recomendada para la mayoría de apps)
```

**Buenas Prácticas de Ingress:**
```yaml
# Siempre especifica ingressClassName (requerido en networking.k8s.io/v1)
spec:
  ingressClassName: nginx  # o traefik, etc.
  rules:
    - host: api.example.com
      http:
        paths:
          - path: /
            pathType: Prefix  # Requerido: Exact, Prefix o ImplementationSpecific
            backend:
              service:
                name: api-service
                port:
                  number: 80
```

**Almacenamiento Persistente de StatefulSet:**
```yaml
# Usa volumeClaimTemplates para el aprovisionamiento dinámico
volumeClaimTemplates:
  - metadata:
      name: data
    spec:
      accessModes: ["ReadWriteOnce"]
      storageClassName: "fast-ssd"  # Usa la storage class apropiada
      resources:
        requests:
          storage: 10Gi
```

**Herramientas Recomendadas para 2025:**
- **kubectl 1.29+** - Mantén la versión de kubectl dentro de una versión menor del clúster
- **k9s** - UI de terminal para la gestión de Kubernetes
- **stern** - Seguimiento de logs de múltiples pods
- **kubectx/kubens** - Cambio rápido de contexto/namespace
- **Helm 3.x** - Gestión de paquetes (Helm 2 está obsoleto)
- **Kustomize** - Integrado en kubectl, no se necesita instalación separada

**Flujo de Trabajo GitOps:**
```bash
# Almacena todos los manifiestos en Git
/kubernetes
├── base/              # Configuraciones base
├── overlays/
│   ├── dev/          # Overrides de desarrollo
│   ├── staging/      # Overrides de staging
│   └── production/   # Overrides de producción
└── README.md

# Usa herramientas como ArgoCD o Flux para el despliegue automatizado
```

**Pod Disruption Budgets (PDB):**
```yaml
# Garantiza alta disponibilidad durante el mantenimiento de nodos
apiVersion: policy/v1
kind: PodDisruptionBudget
metadata:
  name: api-pdb
spec:
  minAvailable: 2  # o maxUnavailable: 1
  selector:
    matchLabels:
      app: api
```

**Network Policies:**
```yaml
# Denegar todo el tráfico por defecto, luego permitir explícitamente
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: default-deny-all
spec:
  podSelector: {}
  policyTypes:
    - Ingress
    - Egress
```

---

## 24. Operaciones Avanzadas de kubectl

### Port Forwarding

**El port forwarding** te permite acceder a los pods desde tu máquina local sin exponer los servicios externamente.

**Port forward básico:**
```bash
# Reenviar el puerto local 8080 al puerto 80 del pod
kubectl port-forward pod/nginx 8080:80

# Acceder al pod
curl http://localhost:8080
```

**Reenviar a un service:**
```bash
# Reenviar a un service en lugar de un pod
kubectl port-forward service/nginx 8080:80

# Útil cuando los pods cambian
```

**Múltiples puertos:**
```bash
# Reenviar varios puertos
kubectl port-forward pod/nginx 8080:80 8443:443
```

**Ejemplo práctico:**
```bash
# Crear un pod nginx
kubectl run demo-pod --image=nginx --port=80

# Port forward (ocupará la terminal)
kubectl port-forward demo-pod 2224:80

# En una nueva terminal
curl localhost:2224
# Salida: Welcome to nginx!

# Presiona Ctrl+C para detener el reenvío
```

**Para el examen CKA/CKAD:**
- tmux está instalado en las máquinas del examen
- Divide la pantalla para mantener el port-forward en ejecución
- Prueba servicios sin crear un LoadBalancer

### Exec en Contenedores

**Shell interactiva:**
```bash
# Abrir una shell bash en el pod
kubectl exec -it <pod-name> -- /bin/bash

# Si bash no está disponible
kubectl exec -it <pod-name> -- /bin/sh
```

**Ejecutar un solo comando:**
```bash
# Ejecutar un comando sin shell interactiva
kubectl exec <pod-name> -- ls /app

# Comprobar las variables de entorno
kubectl exec <pod-name> -- env

# Comprobar los procesos
kubectl exec <pod-name> -- ps aux
```

**Pods multi-contenedor:**
```bash
# Especificar el contenedor
kubectl exec -it <pod-name> -c <container-name> -- /bin/bash

# Ejemplo con sidecar
kubectl exec -it myapp-pod -c sidecar -- /bin/sh
```

**Ejemplo práctico - modificar un contenedor:**
```bash
# Exec en nginx
kubectl exec -it demo-pod -- /bin/bash

# Dentro del contenedor
cd /var/www
mkdir html
echo "Hello from Kubernetes!" > html/index.html

# Salir
exit

# ¡Pero los cambios se pierden cuando el pod muere!
# Esto demuestra la naturaleza efímera de los contenedores
```

**Limitaciones:**
- Las herramientas disponibles dependen de la imagen del contenedor
- Vim, nano podrían no estar instalados
- Usa imágenes mínimas para producción (seguridad)
- Los cambios no persisten cuando el contenedor muere

### Copiar Archivos

**Copiar de un pod a local:**
```bash
# Copiar un archivo desde el pod
kubectl cp <pod-name>:/path/to/file ./local-file

# Ejemplo
kubectl cp nginx:/etc/nginx/nginx.conf ./nginx.conf
```

**Copiar de local a un pod:**
```bash
# Copiar un archivo al pod
kubectl cp ./local-file <pod-name>:/path/to/file

# Ejemplo - copiar una config personalizada
kubectl cp ./nginx.conf demo-pod:/etc/nginx/nginx.conf

# Recargar nginx para aplicar los cambios
kubectl exec demo-pod -- nginx -s reload
```

**Copiar a un contenedor específico:**
```bash
# Pod multi-contenedor
kubectl cp ./file <pod-name>:/path -c <container-name>
```

**Ejemplo práctico:**
```bash
# Crear una config de nginx personalizada localmente
cat > nginx.conf << EOF
server {
    listen 80;
    root /var/www/html;
    index index.html;
}
EOF

# Copiar al pod
kubectl cp ./nginx.conf demo-pod:/etc/nginx/nginx.conf

# Copiar una página index personalizada
echo "Custom page!" > index.html
kubectl cp ./index.html demo-pod:/var/www/html/index.html

# Probar
kubectl port-forward demo-pod 8080:80
curl localhost:8080
# Salida: Custom page!
```

---

## 25. Almacenamiento en Profundidad

### Flujo de Trabajo del Almacenamiento

**Flujo completo del almacenamiento:**
```
Storage Class (define el tipo de almacenamiento)
    ↓
Persistent Volume (almacenamiento real)
    ↓
Persistent Volume Claim (acceso al almacenamiento)
    ↓
Pod Volume Mount (montar al pod)
    ↓
Container Mount (montar al contenedor)
```

### Storage Class

**¿Qué es una Storage Class?**
- Le enseña al clúster cómo aprovisionar almacenamiento
- Específica del proveedor (AWS, GCP, Azure, etc.)
- Habilita el aprovisionamiento dinámico
- Creada una vez, usada por muchos PVs

**Storage class manual (ejemplo simple):**
```yaml
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: manual
provisioner: kubernetes.io/no-provisioner
volumeBindingMode: WaitForFirstConsumer
```

**Storage class de nube (automática):**
```yaml
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: fast-ssd
provisioner: kubernetes.io/aws-ebs
parameters:
  type: gp3
  fsType: ext4
```

### Persistent Volume (Manual)

**Crear un PV con almacenamiento local:**
```yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: my-pv
spec:
  storageClassName: manual
  capacity:
    storage: 3Gi
  accessModes:
    - ReadWriteOnce
  hostPath:
    path: "/mnt/data"
```

**Modos de acceso explicados:**
- **ReadWriteOnce (RWO)** - Montado por un solo nodo (lectura/escritura)
- **ReadOnlyMany (ROX)** - Montado por varios nodos (solo lectura)
- **ReadWriteMany (RWX)** - Montado por varios nodos (lectura/escritura)

### Persistent Volume Claim

**Solicitar almacenamiento:**
```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: my-pvc
spec:
  storageClassName: manual
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi  # Solicita 1Gi, obtiene 3Gi del PV
```

**Enlace (Binding):**
- El PVC se enlaza a un PV con la storage class coincidente
- El PVC es monógamo (un PVC → un PV)
- Varios pods pueden usar el mismo PVC

### Ejemplo Completo

**Manifiesto todo-en-uno:**
```yaml
# Persistent Volume
apiVersion: v1
kind: PersistentVolume
metadata:
  name: nginx-pv
spec:
  storageClassName: manual
  capacity:
    storage: 3Gi
  accessModes:
    - ReadWriteOnce
  hostPath:
    path: "/mnt/data"

---
# Persistent Volume Claim
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: nginx-pvc
spec:
  storageClassName: manual
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi

---
# Pod usando el PVC
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  # Node selector (forzar el pod a un nodo específico)
  nodeSelector:
    kubernetes.io/hostname: node-1

  containers:
  - name: nginx
    image: nginx:alpine
    volumeMounts:
    - name: storage
      mountPath: /data

  # Montar el PVC como volumen
  volumes:
  - name: storage
    persistentVolumeClaim:
      claimName: nginx-pvc
```

**Aplicar y probar:**
```bash
# Aplicar todos los recursos
kubectl apply -f storage.yaml

# Comprobar el PV
kubectl get pv
# Salida: nginx-pv   3Gi    RWO    Bound

# Comprobar el PVC
kubectl get pvc
# Salida: nginx-pvc  Bound  nginx-pv  3Gi

# Exec en el pod
kubectl exec -it nginx -- /bin/sh

# Crear un archivo en /data
echo "Hello persistent storage!" > /data/test.txt

# Salir
exit

# Eliminar el pod
kubectl delete pod nginx

# Recrear el pod
kubectl apply -f storage.yaml

# Comprobar que el archivo aún existe
kubectl exec nginx -- cat /data/test.txt
# Salida: Hello persistent storage!
```

**Verificar en el nodo:**
```bash
# SSH al node-1
ssh node-1

# Comprobar la ruta del host
cat /mnt/data/test.txt
# Salida: Hello persistent storage!

# ¡El archivo está físicamente almacenado en el nodo!
```

### Aprovisionamiento Dinámico en la Nube

**StatefulSet con volúmenes automáticos:**
```yaml
apiVersion: apps/v1
kind: StatefulSet
metadata:
  name: mysql
spec:
  serviceName: mysql
  replicas: 1
  selector:
    matchLabels:
      app: mysql
  template:
    metadata:
      labels:
        app: mysql
    spec:
      containers:
      - name: mysql
        image: mysql:8.0
        env:
        - name: MYSQL_ROOT_PASSWORD
          value: "password"
        volumeMounts:
        - name: mysql-data
          mountPath: /var/lib/mysql

  # Creación automática de volumen
  volumeClaimTemplates:
  - metadata:
      name: mysql-data
    spec:
      accessModes: [ "ReadWriteOnce" ]
      storageClassName: "do-block-storage"  # DigitalOcean
      resources:
        requests:
          storage: 10Gi
```

**Qué pasa (ejemplo de DigitalOcean):**
1. StatefulSet creado
2. Kubernetes llama a la API de DigitalOcean
3. DigitalOcean crea un volumen de block storage de 10GB
4. Volumen adjuntado al nodo worker
5. Montado en el pod en `/var/lib/mysql`
6. ¡Todo automático!

**Verificar en la nube:**
- Comprueba el dashboard del proveedor de nube
- Aparece el nuevo volumen
- Adjuntado al nodo correcto
- Todo gestionado por Kubernetes

**Comportamiento al eliminar:**
```bash
# Eliminar el StatefulSet
kubectl delete statefulset mysql

# ¡El PVC sigue existiendo!
kubectl get pvc
# Salida: mysql-data-mysql-0  Bound

# El volumen sigue existiendo en la nube
# Datos preservados

# Eliminar el PVC para quitar el volumen
kubectl delete pvc mysql-data-mysql-0

# Ahora el volumen se elimina de la nube
```

---

## 26. Network Policies Explicadas

### Comportamiento por Defecto

**Por defecto, todos los pods pueden comunicarse:**
```bash
# Cualquier pod puede acceder a cualquier otro pod
# Sin restricciones
# ¡Una pesadilla de seguridad!
```

**Probar el acceso sin restricciones:**
```bash
# Crear un deployment
kubectl create deployment nginx --image=nginx

# Crear un pod de prueba
kubectl run client --image=busybox --command -- sleep infinity

# Exec en el client
kubectl exec -it client -- /bin/sh

# Acceder a nginx (¡funciona!)
wget -qO- http://nginx
# Salida: Welcome to nginx!
```

### Fundamentos de Network Policy

**Network policy = Reglas de firewall para pods**

**Conceptos clave:**
- **podSelector** - A qué pods aplicar la política
- **policyTypes** - Ingress, Egress o ambos
- **ingress** - Reglas para el tráfico entrante
- **egress** - Reglas para el tráfico saliente

### Política de Denegación por Defecto

**Bloquear todo el tráfico:**
```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: default-deny
  namespace: default
spec:
  podSelector: {}  # Seleccionar todos los pods
  policyTypes:
  - Ingress
  - Egress
  # Sin reglas = denegar todo
```

**Aplicar y probar:**
```bash
# Aplicar la política
kubectl apply -f default-deny.yaml

# Intentar acceder a nginx
kubectl exec client -- wget -qO- http://nginx --timeout=5
# ¡Timeout! Conexión bloqueada
```

### Permitir Tráfico Específico

**Permitir tráfico de pods específicos:**
```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-from-client
spec:
  podSelector:
    matchLabels:
      app: nginx  # Aplicar a los pods nginx
  policyTypes:
  - Ingress
  ingress:
  - from:
    - podSelector:
        matchLabels:
          run: client  # Permitir desde el pod client
    ports:
    - protocol: TCP
      port: 80
```

### Ejemplo Completo de Network Policy

**Política exhaustiva con todas las opciones:**
```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: db-policy
  namespace: default
spec:
  # Aplicar a los pods con role=db
  podSelector:
    matchLabels:
      role: db

  policyTypes:
  - Ingress
  - Egress

  # Reglas de ingress (tráfico entrante)
  ingress:
  - from:
    # Permitir desde un rango de IP
    - ipBlock:
        cidr: 172.17.0.0/16
        except:
        - 172.17.1.0/24

    # O desde un namespace con etiqueta
    - namespaceSelector:
        matchLabels:
          project: myproject

    # O desde pods con etiqueta
    - podSelector:
        matchLabels:
          role: frontend

    # Solo en el puerto 6379
    ports:
    - protocol: TCP
      port: 6379

  # Reglas de egress (tráfico saliente)
  egress:
  - to:
    # Permitir a un rango de IP
    - ipBlock:
        cidr: 10.0.0.0/24

    # Solo en el puerto 5978
    ports:
    - protocol: TCP
      port: 5978
```

**Interpretación de las reglas:**
- **Ingress**: "Los pods con la etiqueta role=db pueden recibir tráfico de:"
  - Pods en el rango de IP 172.17.0.0/16 (excepto 172.17.1.0/24)
  - O desde un namespace con la etiqueta project=myproject
  - O desde pods con la etiqueta role=frontend
  - Solo en el puerto 6379
- **Egress**: "Los pods con la etiqueta role=db pueden enviar tráfico a:"
  - El rango de IP 10.0.0.0/24
  - Solo en el puerto 5978

### Notas Importantes

**OR vs AND:**
```yaml
ingress:
- from:
  - podSelector: {...}  # Opción 1
  - namespaceSelector: {...}  # O la Opción 2
  - ipBlock: {...}  # O la Opción 3
```

Todas las opciones en la misma lista = OR (cualquier coincidencia permite el tráfico)

**Reglas combinadas:**
```yaml
ingress:
- from:
  - podSelector: {...}
    namespaceSelector: {...}  # AND (ambas deben coincidir)
```

Mismo nivel = AND (ambas deben coincidir)

### Ejemplo Práctico - Microservicios

**Configuración:**
- Pods de Frontend (etiqueta: tier=frontend)
- Pods de API Backend (etiqueta: tier=backend)
- Pods de Base de datos (etiqueta: tier=database)

**Política: La base de datos solo accesible desde el backend:**
```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: db-policy
spec:
  podSelector:
    matchLabels:
      tier: database
  policyTypes:
  - Ingress
  ingress:
  - from:
    - podSelector:
        matchLabels:
          tier: backend
    ports:
    - protocol: TCP
      port: 3306
```

**Resultado:**
- ✅ Backend → Base de datos (permitido en el puerto 3306)
- ❌ Frontend → Base de datos (bloqueado)
- ❌ Externo → Base de datos (bloqueado)

---

## 27. Entendiendo Kube Proxy y las Redes

### Fundamentos de las Redes de Pods

**Cada pod obtiene una IP única:**
```bash
kubectl get pods -o wide

# Salida:
# NAME       IP            NODE
# pod-1      10.244.0.10   node-1
# pod-2      10.244.0.11   node-1
# pod-3      10.244.1.10   node-2
```

**Características de la IP del pod:**
- Única dentro del clúster
- Enrutable desde cualquier pod
- Cambia cuando el pod se recrea
- No accesible directamente desde el exterior

### Container Network Interface (CNI)

**Los plugins CNI crean la red de pods:**
- Asignan una IP a cada pod
- Crean rutas entre los nodos
- Habilitan la comunicación pod-a-pod

**Plugins CNI comunes:**
- **Calico** - El más popular, network policies
- **Flannel** - Red overlay simple
- **Weave** - Red en malla
- **Cilium** - Basado en eBPF

**Cómo funciona CNI:**
```
Nodo 1 (192.168.1.10)
├─ Pod A (10.244.0.10)
└─ Pod B (10.244.0.11)

Nodo 2 (192.168.1.11)
└─ Pod C (10.244.1.10)
```

Pod A → Pod C:
1. Paquete enviado a 10.244.1.10
2. CNI enruta al Nodo 2
3. El Nodo 2 lo entrega al Pod C

### Kube Proxy en Profundidad

**Kube proxy se ejecuta en cada nodo:**
```bash
# Comprobar kube-proxy
kubectl get pods -n kube-system | grep proxy

# Salida:
# kube-proxy-abc123  1/1  Running  node-1
# kube-proxy-def456  1/1  Running  node-2
# kube-proxy-ghi789  1/1  Running  node-3
```

**Qué hace kube-proxy:**
1. Observa el API server en busca de services/endpoints
2. Crea reglas de iptables/IPVS
3. Enruta el tráfico del servicio a los pods
4. Implementa el balanceo de carga

### Enrutamiento de Service a Pod

**Escenario de ejemplo:**
```yaml
# Service
apiVersion: v1
kind: Service
metadata:
  name: nginx
spec:
  selector:
    app: nginx
  ports:
  - port: 80
    targetPort: 80
```

**Tras bambalinas:**
```bash
# El service obtiene un ClusterIP
kubectl get svc nginx
# NAME    TYPE        CLUSTER-IP      PORT(S)
# nginx   ClusterIP   10.96.100.50    80/TCP

# Los pods tienen IPs distintas
kubectl get pods -o wide -l app=nginx
# NAME         IP
# nginx-1      10.244.0.10
# nginx-2      10.244.0.11
# nginx-3      10.244.1.10
```

**Kube proxy crea reglas de iptables:**
```bash
# En cada nodo, kube-proxy crea:
# Regla: Tráfico a 10.96.100.50:80 → Balancear a:
#   - 10.244.0.10:80
#   - 10.244.0.11:80
#   - 10.244.1.10:80
```

### Cómo Fluye el Tráfico

**Pod → Service → Pod:**
```
1. La app en pod-1 llama a http://nginx:80
2. DNS resuelve nginx → 10.96.100.50 (ClusterIP)
3. Paquete enviado a 10.96.100.50:80
4. Kube proxy intercepta (iptables)
5. Elige un pod (round-robin): 10.244.0.11:80
6. Enruta el paquete a pod-2
7. La respuesta vuelve por la misma ruta
```

**Flujo visual:**
```
Pod-1 (10.244.0.5)
   ↓ curl http://nginx:80
DNS: nginx → 10.96.100.50
   ↓
Kube Proxy (Node-1)
   ↓ iptables: 10.96.100.50 → pod aleatorio
Pod-2 (10.244.0.11) [elegido]
   ↓
Respuesta de vuelta a Pod-1
```

### Tipos de Service y Kube Proxy

**ClusterIP (interno):**
```yaml
type: ClusterIP
# Kube proxy: Enruta el tráfico interno del clúster
```

**NodePort (externo vía nodo):**
```yaml
type: NodePort
# Kube proxy: Escucha en todas las IPs de los nodos
# Enruta: NodeIP:NodePort → Service → Pods
```

**LoadBalancer (nube):**
```yaml
type: LoadBalancer
# Kube proxy: Igual que NodePort
# Además: La nube crea un LB externo apuntando a los nodos
```

### IPTables vs IPVS

**Modos de kube proxy:**

**IPTables (por defecto):**
- Usa reglas de iptables
- Comprobación secuencial de reglas
- Funciona hasta ~1000 services
- Degradación lineal del rendimiento

**IPVS (mejor para escala):**
- Usa IP Virtual Server
- Búsquedas en tabla hash
- Escala a más de 10,000 services
- Rendimiento constante

**Comprobar el modo:**
```bash
kubectl logs -n kube-system kube-proxy-abc123 | grep "mode"
# Salida: Using iptables Proxier
```

**Cambiar a IPVS:**
```yaml
# ConfigMap de kube-proxy
apiVersion: v1
kind: ConfigMap
metadata:
  name: kube-proxy
  namespace: kube-system
data:
  config.conf: |
    mode: "ipvs"
```

### Algoritmos de Balanceo de Carga

**Round-robin (por defecto):**
```
Petición 1 → Pod-1
Petición 2 → Pod-2
Petición 3 → Pod-3
Petición 4 → Pod-1 (vuelve al primero)
```

**Afinidad de sesión:**
```yaml
spec:
  sessionAffinity: ClientIP
  sessionAffinityConfig:
    clientIP:
      timeoutSeconds: 10800
```

La misma IP de cliente siempre enruta al mismo pod.

---

## 28. Gestión de Logs y Solución de Problemas

### Logs de Contenedores

**Ver los logs de un pod:**
```bash
# Logs actuales
kubectl logs <pod-name>

# Seguir los logs (tail -f)
kubectl logs -f <pod-name>

# Últimas 100 líneas
kubectl logs --tail=100 <pod-name>

# Desde hace 10 segundos
kubectl logs --since=10s <pod-name>

# Desde hace 1 hora
kubectl logs --since=1h <pod-name>
```

### Logs de Pods Multi-Contenedor

**Ejemplo de pod con dos contenedores:**
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: counter
spec:
  containers:
  - name: count
    image: busybox
    args:
    - /bin/sh
    - -c
    - >
      i=0;
      while true;
      do
        echo "$i: $(date)";
        i=$((i+1));
        sleep 1;
      done

  - name: count-by-three
    image: busybox
    args:
    - /bin/sh
    - -c
    - >
      i=0;
      while true;
      do
        echo "$i: $(date)";
        i=$((i+3));
        sleep 3;
      done
```

**Ver los logs de un contenedor específico:**
```bash
# Primer contenedor (por defecto)
kubectl logs counter

# Salida: Defaulted container "count"...

# Contenedor específico
kubectl logs counter -c count-by-three

# Ambos contenedores
kubectl logs counter --all-containers=true

# Seguir ambos
kubectl logs -f counter --all-containers=true
```

### Marcas de Tiempo en los Logs

**Incluir marcas de tiempo:**
```bash
kubectl logs <pod-name> --timestamps=true

# Salida:
# 2026-02-11T10:15:30.123456789Z Application started
# 2026-02-11T10:15:31.234567890Z Listening on port 8080
```

### Logs del Contenedor Anterior

**Ver los logs de un contenedor que se cayó:**
```bash
# Contenedor actual
kubectl logs <pod-name>

# Contenedor anterior (tras un crash/reinicio)
kubectl logs <pod-name> --previous

# Útil cuando el pod está en CrashLoopBackOff
```

### Dónde se Almacenan los Logs

**Ubicación de los logs en los nodos:**
```bash
# SSH al nodo
ssh node-1

# Los logs se almacenan en
/var/log/pods/<namespace>_<pod-name>_<pod-uid>/<container-name>/

# Ejemplo
ls /var/log/pods/default_counter_abc-123-def/count/
# Salida: 0.log

# Ver el archivo de log
cat /var/log/pods/default_counter_abc-123-def/count/0.log
```

**Impermanencia de los logs:**
```bash
# Los logs se eliminan cuando el pod se elimina
kubectl delete pod counter

# Espera ~60 segundos (limpieza del kubelet)
# Comprueba el nodo de nuevo
ls /var/log/pods/default_counter_abc-123-def/
# Salida: No such file or directory

# ¡Los logs DESAPARECIERON!
```

**Por qué esto importa:**
- Los logs se pierden cuando el pod se elimina
- Necesitas una solución de logging externa
- Elasticsearch, Fluentd, Kibana (stack EFK)
- O el logging del proveedor de nube

### Solución de Problemas con Logs

**Problemas comunes:**

**1. CrashLoopBackOff:**
```bash
# Comprobar por qué el pod sigue cayéndose
kubectl logs <pod-name> --previous

# A menudo muestra:
# - Variables de entorno faltantes
# - Errores en el archivo de config
# - Health checks fallidos
```

**2. ImagePullBackOff:**
```bash
# Describir el pod (los logs no ayudarán)
kubectl describe pod <pod-name>

# Los eventos muestran:
# Failed to pull image "nginx:wrongtag"
# ErrImagePull
```

**3. Errores de aplicación:**
```bash
# Seguir los logs en tiempo real
kubectl logs -f <pod-name>

# Filtrar por errores
kubectl logs <pod-name> | grep ERROR

# Contar las ocurrencias de error
kubectl logs <pod-name> | grep ERROR | wc -l
```

### Visualización Avanzada de Logs

**Múltiples pods:**
```bash
# Ver los logs de todos los pods con una etiqueta
for pod in $(kubectl get pods -l app=nginx -o name); do
  echo "=== $pod ==="
  kubectl logs $pod
done

# O usar stern (mejor opción)
stern nginx
```

**Logs con contexto:**
```bash
# Mostrar 5 líneas antes del error
kubectl logs <pod-name> | grep -B 5 ERROR

# Mostrar 5 líneas después del error
kubectl logs <pod-name> | grep -A 5 ERROR

# Mostrar 5 líneas antes y después
kubectl logs <pod-name> | grep -C 5 ERROR
```

---

## 29. Gestión de Recursos y Probes

### Requests y Limits de Recursos

**Por qué importa la gestión de recursos:**
- Previene la escasez de recursos
- Habilita una programación adecuada de pods
- Protege la estabilidad del clúster
- Garantiza un reparto justo de recursos

**Requests vs Limits:**
```yaml
resources:
  requests:      # Mínimo garantizado
    memory: "64Mi"
    cpu: "200m"
  limits:        # Máximo permitido
    memory: "128Mi"
    cpu: "500m"
```

### Recursos de CPU

**Unidades de CPU:**
- `1000m` = 1 núcleo de CPU
- `500m` = 0.5 núcleo de CPU
- `100m` = 0.1 núcleo de CPU
- `m` = millicores

**Ejemplo:**
```yaml
resources:
  requests:
    cpu: "100m"  # Necesita al menos 0.1 CPU
  limits:
    cpu: "500m"  # Puede usar hasta 0.5 CPU
```

**Qué pasa:**
- **Request**: El scheduler asegura que el nodo tenga 0.1 CPU libre
- **Limit**: El contenedor se limita (throttled) si excede 0.5 CPU
- **Sin límite**: Puede usar toda la CPU disponible (¡malo!)

### Recursos de Memoria

**Unidades de memoria:**
- `Ki` = Kibibyte (1024 bytes)
- `Mi` = Mebibyte (1024 Ki)
- `Gi` = Gibibyte (1024 Mi)
- `K`, `M`, `G` = Decimal (base 1000)

**Ejemplo:**
```yaml
resources:
  requests:
    memory: "64Mi"   # Necesita al menos 64 MB
  limits:
    memory: "128Mi"  # Puede usar hasta 128 MB
```

**Qué pasa:**
- **Request**: El scheduler asegura que el nodo tenga 64Mi libres
- **Limit**: El contenedor se mata (OOMKilled) si excede 128Mi
- **Sin límite**: Puede usar toda la memoria hasta que el nodo se agote (¡muy malo!)

### Diferencias de Comportamiento de los Recursos

**CPU (recurso comprimible):**
```yaml
limits:
  cpu: "500m"
```
- El contenedor se limita (throttled) si excede
- No mata el contenedor
- El rendimiento se degrada
- El contenedor sigue en ejecución

**Memoria (recurso no comprimible):**
```yaml
limits:
  memory: "128Mi"
```
- El contenedor se mata si excede (OOMKilled)
- El pod muestra el estado OOMKilled
- El kubelet reinicia el contenedor
- Datos perdidos si no se guardan

### Liveness Probes

**Propósito:** Detectar cuándo el contenedor está muerto/colgado

**Tipos de probes:**

**1. HTTP GET:**
```yaml
livenessProbe:
  httpGet:
    path: /health
    port: 8080
  initialDelaySeconds: 30
  periodSeconds: 10
  timeoutSeconds: 5
  failureThreshold: 3
```

**2. TCP Socket:**
```yaml
livenessProbe:
  tcpSocket:
    port: 8080
  initialDelaySeconds: 15
  periodSeconds: 20
```

**3. Comando Exec:**
```yaml
livenessProbe:
  exec:
    command:
    - cat
    - /tmp/healthy
  initialDelaySeconds: 5
  periodSeconds: 5
```

**Parámetros explicados:**
- `initialDelaySeconds`: Esperar antes del primer probe
- `periodSeconds`: Con qué frecuencia hacer el probe
- `timeoutSeconds`: Timeout del probe
- `failureThreshold`: Fallos antes de reiniciar

### Readiness Probes

**Propósito:** Detectar cuándo el contenedor está listo para el tráfico

**Ejemplo:**
```yaml
readinessProbe:
  httpGet:
    path: /ready
    port: 8080
  initialDelaySeconds: 5
  periodSeconds: 5
  successThreshold: 1
  failureThreshold: 3
```

**Qué pasa:**
- **El probe falla**: El pod se elimina de los endpoints del servicio
- **El probe tiene éxito**: El pod se vuelve a añadir a los endpoints
- **El contenedor no se mata**: Solo se marca como no listo

### Liveness vs Readiness

**Liveness probe:**
- "¿Mi app está muerta/congelada?"
- Reinicia el contenedor si falla
- Usar para: Deadlocks, bucles infinitos, procesos colgados

**Readiness probe:**
- "¿Mi app está lista para el tráfico?"
- Elimina del servicio si falla
- Usar para: Retrasos de arranque, comprobaciones de dependencias, calentamiento

**Ambos juntos:**
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: webapp
spec:
  containers:
  - name: webapp
    image: myapp:v1

    # Reiniciar si está muerto
    livenessProbe:
      httpGet:
        path: /health
        port: 8080
      initialDelaySeconds: 30  # La app tarda en arrancar
      periodSeconds: 10

    # Eliminar del servicio si no está listo
    readinessProbe:
      httpGet:
        path: /ready
        port: 8080
      initialDelaySeconds: 5   # Comprobar pronto
      periodSeconds: 5
```

**Línea de tiempo:**
```
0s:    El contenedor arranca
5s:    Empieza la comprobación de readiness
7s:    Readiness tiene éxito → Añadido al servicio
30s:   Empieza la comprobación de liveness
40s:   Liveness tiene éxito → Contenedor saludable
...
120s:  Readiness falla → Eliminado del servicio
       (La app sigue en ejecución)
125s:  Readiness tiene éxito → Añadido de nuevo al servicio
...
200s:  Liveness falla 3 veces → Contenedor reiniciado
```

### Startup Probes

**Propósito:** Dar más tiempo a los contenedores de arranque lento

**Problema:**
```yaml
livenessProbe:
  httpGet:
    path: /health
    port: 8080
  initialDelaySeconds: 30
  periodSeconds: 10
# Si la app tarda 2 minutos en arrancar, ¡liveness la mata!
```

**Solución:**
```yaml
# Deshabilitar liveness/readiness hasta que el arranque tenga éxito
startupProbe:
  httpGet:
    path: /startup
    port: 8080
  failureThreshold: 30  # 30 intentos
  periodSeconds: 10     # Cada 10s = 300s máx (5 min)

# Estos esperan hasta que el arranque tenga éxito
livenessProbe:
  httpGet:
    path: /health
    port: 8080
  periodSeconds: 10

readinessProbe:
  httpGet:
    path: /ready
    port: 8080
  periodSeconds: 5
```

---

## 30. Configuración de Kubernetes en la Nube

### ¿Por Qué Kubernetes en la Nube?

**Beneficios del Kubernetes gestionado:**
- ✅ Control plane gestionado (nodos master)
- ✅ Actualizaciones automáticas
- ✅ Integrado con los servicios de la nube
- ✅ Creación fácil de clústeres
- ✅ Solo pagas por los nodos worker

**Proveedores populares:**
- **DigitalOcean Kubernetes (DOKS)** - Simple, asequible
- **Amazon EKS** - Integración con AWS
- **Google GKE** - Integración con Google Cloud
- **Azure AKS** - Integración con Azure
- **Linode Kubernetes Engine (LKE)** - Rentable

### Configuración de Kubernetes en Linode

**Paso 1: Crear una cuenta**
- Regístrate en [linode.com](https://www.linode.com)
- Obtén $100 de crédito (60 días)

**Paso 2: Crear un clúster**
```bash
# En Linode Cloud Manager
1. Haz clic en "Kubernetes" en el menú izquierdo
2. Haz clic en "Create Cluster"
3. Da un nombre al clúster: "my-k8s-cluster"
4. Elige la región: Dallas (la más cercana a ti)
5. Selecciona la versión de Kubernetes: Latest (1.29+, 1.30 o 1.31 recomendadas)
6. Elige el node pool:
   - Shared CPU: 2GB RAM ($10/mes)
   - Número de nodos: 3
7. Haz clic en "Create Cluster"
```

**Paso 3: Descargar el kubeconfig**
```bash
# En el dashboard de Linode
1. Haz clic en el nombre de tu clúster
2. Haz clic en "Download kubeconfig"
3. Guardar como: my-cluster-kubeconfig.yaml
```

**Paso 4: Configurar kubectl**
```bash
# Establecer la variable de entorno kubeconfig
export KUBECONFIG=/path/to/my-cluster-kubeconfig.yaml

# Verificar la conexión
kubectl get nodes

# Salida:
# NAME                           STATUS   ROLES    AGE   VERSION
# lke-123-456-worker-1           Ready    <none>   5m    v1.29.0
# lke-123-456-worker-2           Ready    <none>   5m    v1.29.0
# lke-123-456-worker-3           Ready    <none>   5m    v1.29.0
```

### Configuración de Kubernetes en DigitalOcean

**Paso 1: Crear un clúster**
```bash
# En el dashboard de DigitalOcean
1. Haz clic en "Create" → "Kubernetes"
2. Elige la región
3. Selecciona la versión de Kubernetes (1.29+, 1.30 o 1.31 recomendadas)
4. Elige el tamaño de nodo: Basic (2 vCPU, 4GB RAM)
5. Número de nodos: 3
6. Nombre: my-cluster
7. Haz clic en "Create Cluster"
```

**Paso 2: Conectar al clúster**
```bash
# Descargar el archivo de configuración
doctl kubernetes cluster kubeconfig save <cluster-id>

# O descargar desde el dashboard y:
export KUBECONFIG=/path/to/kubeconfig.yaml

# Probar la conexión
kubectl cluster-info
```

### Desplegar una Aplicación en la Nube

**Ejemplo completo:**

**1. Crear el deployment:**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: coffee-app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: coffee
  template:
    metadata:
      labels:
        app: coffee
    spec:
      containers:
      - name: coffee
        image: your-registry/coffee-app:v1
        ports:
        - containerPort: 80
```

**2. Crear el service LoadBalancer:**
```yaml
apiVersion: v1
kind: Service
metadata:
  name: coffee-service
spec:
  type: LoadBalancer  # ¡Crea un balanceador de carga en la nube!
  selector:
    app: coffee
  ports:
  - port: 80
    targetPort: 80
```

**3. Aplicar:**
```bash
# Aplicar ambos
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

# Observar cómo el service obtiene una IP externa
kubectl get service coffee-service -w

# Salida:
# NAME              TYPE           CLUSTER-IP      EXTERNAL-IP   PORT(S)
# coffee-service    LoadBalancer   10.245.100.50   <pending>     80:30123/TCP
# ...esperar...
# coffee-service    LoadBalancer   10.245.100.50   134.209.1.100 80:30123/TCP
```

**4. Acceder a la aplicación:**
```bash
# Obtener la IP externa
EXTERNAL_IP=$(kubectl get service coffee-service -o jsonpath='{.status.loadBalancer.ingress[0].ip}')

# Acceder a la app
curl http://$EXTERNAL_IP

# Salida: ¡Tu sitio web de café!
```

**5. Comprobar el dashboard de la nube:**
- Navega a la sección Load Balancers
- Verás el balanceador de carga recién creado
- El backend muestra tus 3 nodos
- Health checks configurados
- ¡Todo automático vía Kubernetes!

### Escalado en la Nube

**Escalar el deployment:**
```bash
# Escalar a 10 réplicas
kubectl scale deployment coffee-app --replicas=10

# Comprobar los pods
kubectl get pods
# Muestra 10 pods

# Comprobar los endpoints del service
kubectl describe service coffee-service
# Muestra 10 endpoints

# ¡El balanceador de carga se actualiza automáticamente!
```

**Actualizar la aplicación:**
```bash
# Actualizar la imagen
kubectl set image deployment/coffee-app \
  coffee=your-registry/coffee-app:v2

# Observar el rollout
kubectl rollout status deployment/coffee-app

# ¡Actualización sin tiempo de inactividad!
```

### Beneficios de la Integración con la Nube

**Balanceador de carga automático:**
- Sin configuración manual
- Alta disponibilidad
- Health checks
- Terminación SSL (con Ingress)

**Almacenamiento automático:**
- El PVC crea un volumen en la nube
- Adjuntado al nodo correcto
- Sobrevive a la eliminación del pod
- Gestionado a través de Kubernetes

**Auto-escalado (avanzado):**
```bash
# Instalar el metrics server
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

# Crear un horizontal pod autoscaler
kubectl autoscale deployment coffee-app \
  --cpu-percent=75 \
  --min=3 \
  --max=20

# ¡Los pods escalan automáticamente según la CPU!
```

### Gestión de Costos

**Monitorear el gasto:**
```bash
# Comprobar los recursos
kubectl get nodes
kubectl get services -A

# ¡Cada LoadBalancer cuesta dinero!
# Eliminar los servicios sin usar
kubectl delete service <unused-service>
```

**Limpiar al terminar:**
```bash
# Eliminar el clúster desde el dashboard de la nube
# Todos los recursos eliminados
# Detiene la facturación
```

---

## Resumen

Esta guía proporciona un camino completo desde principiante hasta estar listo para la certificación CKA/CKAD.

### Puntos Clave

**1. Conceptos Fundamentales:**
- **Pods** - Unidad básica de despliegue, contenedores efímeros
- **Deployments** - Gestionan réplicas de pods, auto-recuperación, rolling updates
- **Services** - Endpoint de red estable para las IPs dinámicas de los pods
- **Ingress** - Enrutamiento HTTP/HTTPS con reglas basadas en rutas/host

**2. Almacenamiento:**
- **ConfigMaps** - Datos de configuración (variables de entorno, archivos)
- **Secrets** - Datos sensibles (¡codificados en base64, no cifrados!)
- **Storage Classes** - Definen los tipos de almacenamiento (específicos del proveedor)
- **Persistent Volumes** - Recursos de almacenamiento reales
- **PVCs** - Reclaman almacenamiento para los pods
- **Volume mounts** - Adjuntan almacenamiento a los contenedores (subPath para directorios existentes)

**3. Tipos de Carga de Trabajo:**
- **Deployment** - Apps sin estado (el más común)
- **StatefulSet** - Apps con estado (bases de datos, identidad de red estable)
- **DaemonSet** - Un pod por nodo (agentes de monitoreo, logging)
- **ReplicaSet** - Creado por los deployments (no usar directamente)

**4. Redes:**
- **IPs de Pod** - Cada pod obtiene una IP única (cambia al recrearse)
- **CNI** - Plugins de red (Calico, Flannel, Weave)
- **Kube Proxy** - Implementación de servicios vía iptables/IPVS
- **ClusterIP** - Servicio interno (tipo por defecto)
- **NodePort** - Externo vía puertos de nodo (30000-32767)
- **LoadBalancer** - Balanceador de carga en la nube (¡cuesta dinero!)
- **Ingress** - Enrutamiento HTTP (basado en ruta/host, terminación TLS)
- **Network Policies** - Reglas de firewall de pods (¡por defecto permite todo!)

**5. Integración con la Nube:**
- Creación automática de balanceadores de carga (AWS ELB, DigitalOcean, Linode)
- Aprovisionamiento dinámico de volúmenes (block storage en la nube)
- Auto-escalado con HPA (Horizontal Pod Autoscaler)
- Monitoreo y logging integrados
- ¡Todo vía manifiestos de Kubernetes (Infraestructura como Datos!)

**6. Operaciones:**
- **kubectl** - Herramienta CLI principal, memoriza los comandos comunes
- **Port forwarding** - Acceso local sin exposición externa
- **Exec** - Shell interactiva o ejecución de comandos
- **Logs** - Ver, seguir, filtrar los logs de los contenedores (¡los logs son efímeros!)
- **Describe** - Información detallada de recursos y eventos
- **Copiar archivos** - Transferir archivos hacia/desde los pods

**7. Buenas Prácticas:**
- Usa Deployments, no pods sueltos (¡auto-recuperación!)
- Establece siempre requests/limits de recursos (previene la escasez)
- Define liveness y readiness probes (recuperación automática)
- Externaliza la configuración (ConfigMaps, Secrets)
- Versiona los manifiestos (GitOps)
- Usa namespaces para el aislamiento (dev, staging, prod)
- Etiqueta todo (filtrado fácil y selectores de servicio)
- Nunca commitees secretos a Git (usa Sealed Secrets, Vault)
- Prueba en dev antes de desplegar a producción

**8. Enfoque de Certificación (CKA/CKAD):**
- Conoce los atajos de kubectl y los flags de línea de comandos
- Practica la creación de manifiestos YAML (¡la velocidad importa!)
- Entiende el flujo de trabajo de solución de problemas (describe → logs → events)
- Siéntete cómodo con vim/nano para editar manifiestos
- Sabe cómo usar kubectl explain para la documentación de campos
- tmux está disponible en el examen (¡pantallas divididas!)
- La documentación de Kubernetes.io está permitida durante el examen

### ¿Qué Te Convierte en un Profesional?

**Eres un profesional de Kubernetes cuando puedes:**
- Desplegar aplicaciones multi-nivel en clústeres
- Solucionar fallos de pods usando logs y eventos
- Configurar servicios ClusterIP, NodePort y LoadBalancer
- Configurar Ingress para el enrutamiento HTTP
- Gestionar almacenamiento persistente para apps con estado
- Usar kubectl de forma efectiva y eficiente
- Entender los requests/limits de recursos y los probes
- Trabajar en equipo usando Kubernetes
- Desplegar en proveedores de nube (AWS, GCP, Azure, DO, Linode)

**No necesitas:**
- Conocer cada funcionalidad obscura de Kubernetes
- Tener 5 años de experiencia
- Ser administrador de clúster o SRE
- Entender cada detalle interno del kubelet/API server
- Escribir Kubernetes desde cero

**Recuerda:** Profesional ≠ Experto. Un profesional puede trabajar con Kubernetes de forma productiva y cobrar por ello. ¡Te conviertes en profesional haciendo, no leyendo!

### Siguientes Pasos

**Practica (Principiante):**
1. Configura un clúster local:
   - **Docker Desktop** (Mac/Windows) - El más fácil
   - **Minikube** - Multiplataforma, rico en funciones
   - **kind** (Kubernetes in Docker) - Rápido, capaz de multi-nodo
2. Despliega aplicaciones de ejemplo (usa los ejemplos de esta guía)
3. Experimenta con distintos tipos de servicio
4. Prueba a escalar deployments
5. Rompe cosas y arréglalas (¡la mejor forma de aprender!)

**Practica (Intermedio):**
1. Despliega una aplicación multi-nivel (frontend, backend, base de datos)
2. Configura Ingress con enrutamiento basado en rutas
3. Configura ConfigMaps y Secrets
4. Implementa network policies
5. Usa volúmenes persistentes para cargas de trabajo con estado

**Practica (Avanzado):**
1. Despliega en un proveedor de nube (la mayoría ofrece créditos gratis para cuentas nuevas)
   - Linode / Akamai Kubernetes Engine
   - DigitalOcean Kubernetes
   - GCP GKE
   - AWS EKS (nivel gratuito)
2. Configura monitoreo (metrics-server, Prometheus)
3. Implementa un pipeline de CI/CD con Kubernetes
4. Practica escenarios del examen CKA/CKAD
5. Contribuye a proyectos de código abierto de Kubernetes

**Camino de Certificación:**
1. **CKAD** (Certified Kubernetes Application Developer)
   - Enfoque: Desplegar y gestionar aplicaciones
   - Dificultad: Intermedia
   - Primera certificación recomendada

2. **CKA** (Certified Kubernetes Administrator)
   - Enfoque: Administración y operaciones de clústeres
   - Dificultad: Avanzada
   - Hazla tras dominar los temas de CKAD

**Recursos de estudio para la certificación:**
- Documentación de Kubernetes.io - Referencia oficial (¡permitida durante el examen!)
- [KillerCoda](https://killercoda.com/kubernetes) / Killer.sh - Escenarios de práctica CKA/CKAD
- Practica, practica, practica - La velocidad importa en los exámenes

**Aprende Más:**
- [SRE Book](https://sre.google/books/) - Gratis, explica la filosofía de Kubernetes
- Explora los Helm charts - [Artifact Hub](https://artifacthub.io/)
- Prueba Lens IDE o k9s - Gestión de clústeres
- Construye proyectos reales - Despliega tus propias apps en Kubernetes

**Comunidad:**
- [CNCF Slack](https://slack.cncf.io/) - Únete a #kubernetes-users
- [Kubernetes Reddit](https://reddit.com/r/kubernetes)
- [Stack Overflow](https://stackoverflow.com/questions/tagged/kubernetes)
- Meetups locales de Kubernetes/Cloud Native

---

## Recursos

### Documentación Oficial
- [Kubernetes Docs](https://kubernetes.io/docs/) - **¡Esencial para el examen!**
- [kubectl Reference](https://kubernetes.io/docs/reference/kubectl/)
- [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [API Reference](https://kubernetes.io/docs/reference/)

### Libros
- [Site Reliability Engineering (Google)](https://landing.google.com/sre/book) - **Gratis**, filosofía fundacional
- [Kubernetes Patterns](https://k8spatterns.io/) - Patrones de diseño y buenas prácticas
- [Kubernetes in Action](https://www.manning.com/books/kubernetes-in-action) - En profundidad
- [The Kubernetes Book](https://www.amazon.com/Kubernetes-Book-Nigel-Poulton/dp/1916585000) - Nigel Poulton

### Herramientas
- [kubectl](https://kubernetes.io/docs/tasks/tools/) - **CLI Esencial**
- [Lens IDE](https://k8slens.dev/) - Gestión visual de clústeres
- [k9s](https://k9scli.io/) - UI de terminal para Kubernetes
- [Helm](https://helm.sh/) - Gestor de paquetes
- [stern](https://github.com/stern/stern) - Seguimiento de logs de múltiples pods
- [kubectx/kubens](https://github.com/ahmetb/kubectx) - Cambio rápido de contexto/namespace
- [kustomize](https://kustomize.io/) - Personalización de YAML sin plantillas

### Aprendizaje Interactivo
- [Kubernetes Playground](https://labs.play-with-k8s.com/) - Clúster en línea gratuito
- [KillerCoda](https://killercoda.com/kubernetes) - Escenarios interactivos para CKA/CKAD (sucesor de Katacoda)

### Kubernetes Gestionado (Proveedores de Nube)
- [Linode / Akamai Kubernetes Engine](https://www.linode.com/products/kubernetes/)
- [DigitalOcean Kubernetes](https://www.digitalocean.com/products/kubernetes/)
- [Google GKE](https://cloud.google.com/kubernetes-engine)
- [Amazon EKS](https://aws.amazon.com/eks/)
- [Azure AKS](https://azure.microsoft.com/en-us/services/kubernetes-service/)

### Recursos de Certificación
- [CNCF Certification Overview](https://www.cncf.io/certification/)
- [CKA Exam](https://www.cncf.io/certification/cka/) - Certificación de administrador
- [CKAD Exam](https://www.cncf.io/certification/ckad/) - Certificación de desarrollador
- [CKS Exam](https://www.cncf.io/certification/cks/) - Certificación de seguridad (requiere CKA)

### Comunidad y Soporte
- [CNCF Slack](https://slack.cncf.io/) - Slack oficial de Kubernetes
- [Kubernetes Reddit](https://reddit.com/r/kubernetes)
- [Stack Overflow - Kubernetes](https://stackoverflow.com/questions/tagged/kubernetes)
- [Kubernetes Forums](https://discuss.kubernetes.io/)
- [CNCF Webinars](https://www.cncf.io/webinars/)
- [Kubernetes Podcast](https://kubernetespodcast.com/)

### Repositorios de Código
- [Kubernetes Examples](https://github.com/kubernetes/examples)
- [Awesome Kubernetes](https://github.com/ramitsurana/awesome-kubernetes)

---

**Recuerda el principio clave:** No necesitas ser un experto para ser un profesional. ¡Empieza a usar Kubernetes en proyectos reales, sigue experimentando, y estarás trabajando con él profesionalmente más rápido de lo que crees!

¡Feliz orquestación! ☸️ 🚀

---

**Actualizaciones del Documento**: Última actualización 2026-08-31 para reflejar:
- Versiones actuales de Kubernetes (1.29-1.31)
- Versiones de API actualizadas (apps/v1, networking.k8s.io/v1, batch/v1)
- Advertencias y migraciones de APIs obsoletas
- Buenas prácticas de seguridad actuales
- Recomendaciones de herramientas actuales
- Alineación con los manifiestos de producción en `/Users/sysadmin/Workspace/Kubernetes/`

Para la documentación de Kubernetes más actual, consulta siempre [kubernetes.io/docs](https://kubernetes.io/docs/).
