# Mapa del WorkSpace en Notion

**Workspace:** `WorkSpace` · **Esquema verificado:** 2026-08-30 · **11 bases de datos**

Este documento es el mapa del sistema: **qué recurso sirve para qué, con qué propiedades y
con qué se conecta**. Sirve para dos lectores:

- **Una persona** que necesita entender dónde va cada cosa y por qué.
- **Un agente de IA** que va a crear registros y debe respetar la estructura, las plantillas
  y las reglas de conexión.

> Describe la **forma** del sistema, no su contenido: no lleva nombres de áreas, objetivos,
> proyectos, tareas, notas ni referencias reales. El flujo de ejemplo (§4) reproduce la forma
> de un caso real con nombres genéricos.
>
> Los nombres de **bases, propiedades y opciones** sí van textuales: son identificadores.
> Escritos distinto, las fórmulas, los rollups y las llamadas por API fallan.

---

## Contenido

1. [Vista rápida: qué sirve para qué](#1-vista-rápida-qué-sirve-para-qué)
2. [Mapa de conexiones](#2-mapa-de-conexiones)
3. [Ficha de cada recurso](#3-ficha-de-cada-recurso)
4. [Flujo de ejemplo, de punta a punta](#4-flujo-de-ejemplo-de-punta-a-punta)
5. [Reglas para crear](#5-reglas-para-crear)

---

## 1. Vista rápida: qué sirve para qué

| Recurso | Responde a | Se conecta con |
|---|---|---|
| `Areas` | ¿A qué pilar permanente de mi vida pertenece? | **Todas** menos Key Results y Destacados |
| `Temas` | ¿De qué asunto trata, dentro del área? | Areas, Notas, Referencias, Destacados |
| `Objetivos` | ¿Qué resultado quiero y para cuándo? | Areas, Key Results, Proyectos, Tareas, Notas, Referencias |
| `Key Results` | ¿Con qué número sé que lo logré? | Objetivos |
| `Proyectos` | ¿Qué iniciativa multipaso hace falta? | Areas, Objetivos, Tareas, Eventos, Notas, Referencias, sí misma |
| `Tareas` | ¿Cuál es la próxima acción ejecutable? | Areas, Objetivos, Proyectos, Eventos, Notas, sí misma |
| `Eventos` | ¿Cuándo ocurre y con quién? | Areas, Proyectos, Tareas |
| `Notas` | ¿Qué aprendí, pensé o resumí? | Areas, Temas, Objetivos, Proyectos, Tareas, Referencias, Bloques, Destacados, sí misma |
| `Bloques de notas` | ¿En qué cuaderno agrupo estas notas? | Areas, Notas |
| `Destacados` | ¿Cuál es el fragmento textual que vale? | Referencias, Notas, Temas |
| `Referencias` | ¿De dónde salió esto? | Areas, Temas, Objetivos, Proyectos, Notas, Destacados, sí misma |

**Dos ejes, no uno.** El sistema tiene una cadena **ejecutable** (Objetivo → Proyecto → Tarea:
cosas que se cierran) y una cadena **acumulativa** (Tema → Referencia → Destacado → Nota:
cosas que se guardan para siempre). `Areas` sostiene ambas por arriba y `Notas` es el único
recurso que las cruza por abajo.

---

## 2. Mapa de conexiones

Nodos = recursos. Flechas = relaciones, etiquetadas con lo que significan.

```
                    ┌──────────────────────────────┐
                    │            AREAS             │
                    │Empresa · Personal · Académico│
                    └───────────────┬──────────────┘
                                    │
                      todo se ancla aquí, en directo
                                    │
          ┌─────────────────────────┴─────────────────────────┐
          │ se persigue con                                   │ se estudia en
          ▼                                                   ▼
   ┌──────────────┐                                    ┌──────────────┐
   │  OBJETIVOS   │                                    │    TEMAS     │
   │ Deadline     │                                    │ asunto       │
   └──┬────────┬──┘                                    └──────┬───────┘
      │        │ se mide con                                  │ reúne
      │        ▼                                              ▼
      │ ┌──────────────┐                             ┌──────────────┐
      │ │ KEY RESULTS  │                             │ REFERENCIAS  │
      │ │ Start→Target │                             │ Tipo·Platafor│
      │ └──────────────┘                             └──────┬───────┘
      │ se descompone en                                    │ se cita en
      ▼                                                     ▼
   ┌──────────────┐                                  ┌──────────────┐
   │  PROYECTOS   │                                  │  DESTACADOS  │
   │ Progreso %   │                                  │ cita textual │
   └──┬────────┬──┘                                  └──────┬───────┘
      │        │ se reúne en                                │
      │        ▼                                            │
      │ ┌──────────────┐                                    │
      │ │   EVENTOS    │                                    │
      │ └──────┬───────┘                                    │
      │        │ genera                                     │
      ▼        ▼                                            │
   ┌──────────────┐                                         │
   │    TAREAS    │                                         │
   │ Contexto·Ene.│                                         │
   └──────┬───────┘                                         │
          │ documenta                    se interpreta en   │
          │                                                 │
          └────────────────►┌──────────────┐◄───────────────┘
                            │    NOTAS     │
                            │ Tipo         │
                            └──────┬───────┘
                                   │ se agrupa en
                                   ▼
                          ┌──────────────────┐
                          │ BLOQUES DE NOTAS │
                          └──────────────────┘
```

**Rama izquierda: ejecutable.** Cosas que se cierran. El objetivo se descompone en
proyectos, los proyectos en tareas, y los eventos inyectan tareas nuevas. Es la única
rama con porcentaje de avance.

**Rama derecha: acumulativo.** Cosas que se guardan para siempre. El tema reúne
referencias, de las referencias se rescatan destacados, y los destacados se interpretan
en notas.

**`Notas` es donde las dos ramas se juntan:** recibe de `Tareas` lo ejecutable y de
`Destacados` lo acumulativo. Es el único recurso que toca ambos mundos.

### Tres cosas que el diagrama no muestra

**1. `Areas` se conecta directo con todo, no solo con la capa de abajo.**
Ocho de las otras diez bases tienen su propia relación a `Areas`. Solo `Key Results` y
`Destacados` no la tienen: cuelgan de su padre (`Objetivos` y `Referencias`). En la práctica
esto permite abrir un área y ver *todo* lo suyo sin recorrer la jerarquía — y obliga a llenar
`Area` siempre (ver [regla 5.2](#52-doble-anclaje-siempre-llenar-area)).

**2. Hay cinco auto-relaciones y no significan lo mismo.**

| Recurso | Propiedades | Qué significa |
|---|---|---|
| `Proyectos` | `Parent Project` / `Sub-Projects` | jerarquía real padre–hijo |
| `Proyectos` | `Proyectos relacionados` | asociación lateral, **sin** jerarquía |
| `Tareas` | `Parent Task` / `Sub-Task` | descomposición de una acción |
| `Notas` | `Notas relacionadas` | red de conocimiento, sin jerarquía |
| `Referencias` | `References relacionadas` | fuentes que se citan entre sí |

**3. `Notas` es el segundo nodo central.** Ocho conexiones, igual que `Areas`. Es el único
lugar donde lo ejecutable y lo acumulativo se tocan.

---

## 3. Ficha de cada recurso

Convenciones: **rel →** relación bidireccional · **(máx. 1)** admite un solo valor ·
🔒 se calcula solo, no se escribe · **●** conviene llenarlo al crear.

---

### `Areas` — pilar permanente

**Sirve para** agrupar todo lo que pertenece a una responsabilidad de largo plazo. No se
completa ni se termina: existe. Es el ancla de búsqueda de todo el sistema.

| Propiedad | Tipo | Valores / Destino |
|---|---|---|
| ● `Name` | title | |
| ● `Type` | select | `Empresa` · `Personal` · `Académico` |
| `Archive` | checkbox | |
| `Temas` | rel → | `Temas` |
| `Objetivos` | rel → | `Objetivos` |
| `Proyectos` | rel → | `Proyectos` |
| `Tareas` | rel → | `Tareas` |
| `Eventos` | rel → | `Eventos` |
| `Notas` | rel → | `Notas` |
| `Bloques de notas` | rel → | `Bloques de notas` |
| `Referencias` | rel → | `Referencias` |

**Al crear:** nombre + `Type`. Las relaciones no se llenan desde aquí — se llenan desde el
otro lado, cuando se crea el objetivo, el proyecto o la nota.

No tiene fechas ni campos de auditoría, a propósito: un área no ocurre.

---

### `Temas` — asunto dentro de un área

**Sirve para** agrupar conocimiento por materia, independiente de si hay un objetivo vigente.
Un tema acumula notas, referencias y destacados durante años. Es el índice temático del
sistema.

| Propiedad | Tipo | Valores / Destino |
|---|---|---|
| ● `Name` | title | |
| ● `Area` | rel → | `Areas` |
| `Notas` | rel → | `Notas` |
| `Referencias` | rel → | `Referencias` |
| `Destacados` | rel → | `Destacados` |
| `Area Type` | 🔒 rollup | `Area` → `Type` |
| `Counter` | 🔒 formula | material acumulado |
| `Archive` | checkbox | |
| `Created Time` / `Edited` | 🔒 auditoría | |

**Al crear:** nombre + `Area`. Nada más es obligatorio.

**Tema ≠ Proyecto.** El tema es *sobre qué*; el proyecto es *qué hay que hacer*. Un mismo tema
puede sobrevivir a varios objetivos.

---

### `Objetivos` — resultado con fecha

**Sirve para** declarar un resultado concreto y su plazo. Es la bisagra: por arriba se ancla a
un área, por abajo se descompone en proyectos y se mide con key results.

| Propiedad | Tipo | Valores / Destino |
|---|---|---|
| ● `Name` | title | |
| ● `Status` | status | `No empezado` → `En progreso` → `Completado` |
| ● `Deadline` | date | formato `ll` |
| ● `Area` | rel → | `Areas` |
| `Milestones` | rel → | `Key Results` |
| `Proyectos` | rel → | `Proyectos` |
| `Tareas` | rel → | `Tareas` |
| `Notas` | rel → | `Notas` |
| `Referencias` | rel → | `Referencias` |
| `Countdown` | 🔒 formula | días hasta `Deadline` |
| `Quarter` | 🔒 formula | trimestre del `Deadline` |
| `Archive` | checkbox | |
| `Created` / `Edited` | 🔒 auditoría | |

**Al crear:** nombre + `Area` + `Deadline` + `Status`. **Sin `Deadline` no hay `Countdown` ni
`Quarter`**, y el objetivo desaparece de cualquier vista ordenada por urgencia.

---

### `Key Results` — la métrica del objetivo

**Sirve para** poner un número al objetivo cuando el estado binario no alcanza. Es el único
recurso que mide con cifras.

| Propiedad | Tipo | Valores / Destino |
|---|---|---|
| ● `Name` | title | |
| ● `Goal` | rel → **(máx. 1)** | `Objetivos` |
| ● `Start` | number | valor de partida |
| ● `Current` | number | valor actual |
| ● `Target` | number | meta |
| `Progress` | 🔒 formula | avance entre los tres números |
| `Status` | status | `Open` → `Closed` |
| `Created` / `Edited` | 🔒 auditoría | |

**Al crear:** los tres números **y** el objetivo. Si falta uno, `Progress` no calcula.

Recurso satélite: solo se relaciona con `Objetivos`, ni siquiera con `Areas`.

---

### `Proyectos` — iniciativa multipaso

**Sirve para** agrupar las tareas que hacen falta para avanzar un objetivo. Tiene principio,
fin y porcentaje de avance calculado.

| Propiedad | Tipo | Valores / Destino |
|---|---|---|
| ● `Name` | title | |
| ● `Status` | status | `Inbox` · `Not Started` → `In Progress` · `On Hold` → `Completed` |
| ● `Prioridad` | select | `Urgent` · `High` · `Medium` · `Low` |
| ● `Area` | rel → **(máx. 1)** | `Areas` |
| ● `Objetivo` | rel → | `Objetivos` |
| ● `Línea tiempo` | date | rango inicio–fin, alimenta la vista timeline |
| `Start Date` | date | fecha de inicio |
| `Tareas` | rel → | `Tareas` |
| `Notas` | rel → | `Notas` |
| `` Referencias`` | rel → | `Referencias` — ⚠ **el nombre lleva un espacio inicial** |
| `Meetings` | rel → | `Eventos` |
| `Parent Project` | rel → **(máx. 1)** | `Proyectos` |
| `Sub-Projects` | rel → | `Proyectos` |
| `Proyectos relacionados` | rel → | `Proyectos` |
| `Progreso` | 🔒 rollup | % de `Tareas` en el grupo `Complete` |
| `Goal Area` | 🔒 rollup | `Objetivo` → `Area` |
| `Fecha` | 🔒 formula | fecha efectiva |
| `Archivo` | checkbox | ⚠ aquí se llama `Archivo`, no `Archive` |
| `Creado` / `Editado` | 🔒 auditoría | |

**Al crear:** nombre + `Area` + `Objetivo` + `Status` + `Prioridad` + `Línea tiempo`.

**`Area` admite un solo valor** aquí, a diferencia del resto del sistema.

---

### `Tareas` — la próxima acción

**Sirve para** registrar algo ejecutable en una sesión. Es lo único que mueve el `Progreso` de
un proyecto.

| Propiedad | Tipo | Valores / Destino |
|---|---|---|
| ● `Nombre` | title | ⚠ **el título se llama `Nombre`**, no `Name` |
| ● `Status` | status | `Inbox` · `Sin fecha` → `En proceso` · `Esperando` → `Completed` |
| ● `Prioridad` | select | `Baja` · `Media` · `Alta` · `Urgente` |
| ● `Contexto` | multi_select | `Programa` · `Sistemas` · `Computador` · `Llamada` · `Home` · `Reunion` |
| ● `Energía` | select | `Low` · `Medium` · `High` · `Extreme` |
| ● `Fecha` | date | |
| ● `Area` | rel → | `Areas` |
| ● `Proyecto` | rel → | `Proyectos` |
| `Objetivo` | rel → | `Objetivos` |
| `Evento` | rel → | `Eventos` |
| `Notas` | rel → | `Notas` |
| `Descripción` | text | |
| `URL` | url | |
| `Propietario` | person | |
| `Parent Task` | rel → | `Tareas` |
| `Sub-Task` | rel → | `Tareas` |
| `Goal Area` | 🔒 rollup | `Objetivo` → `Area` |
| `Project Area` | 🔒 rollup | `Proyecto` → `Area` |
| `Objetivo proyecto` | 🔒 rollup | `Proyecto` → `Objetivo` |
| `Parent Date` | 🔒 rollup | fecha vía `Sub-Task` |
| `Creado` / `Editado` | 🔒 auditoría | |

**Al crear:** nombre + `Area` + `Proyecto` + `Status` + `Prioridad` + `Fecha`.

**`Contexto` y `Energía` son la parte útil.** Permiten filtrar por *dónde estoy* y *cuánta
cabeza tengo*, no solo por urgencia. Una lista larga de tareas sin estos dos campos es
inservible.

**No tiene checkbox de archivado.** El cierre es `Status = Completed` y nada más.

---

### `Eventos` — reunión o hito en el calendario

**Sirve para** que una reunión deje rastro accionable: se cuelga de un proyecto y genera
tareas, en vez de quedar solo en la agenda.

| Propiedad | Tipo | Valores / Destino |
|---|---|---|
| ● `Name` | title | |
| ● `Date` | date | |
| ● `Type` | select | `Zoom` · `Google Meet` · `Teams` · `Presencial` |
| ● `Area` | rel → | `Areas` |
| `Projects` | rel → | `Proyectos` |
| `Tasks` | rel → | `Tareas` |
| `Attendees` | person | |
| `Meeting Link` | url | |
| `Description` | text | |
| `Project Area` | 🔒 rollup | `Projects` → `Area` |

**Al crear:** nombre + `Date` + `Type` + `Area`. Si sale de una reunión de proyecto, enlazar
`Projects` y crear las tareas desde ahí.

---

### `Notas` — conocimiento propio

**Sirve para** guardar lo que aprendiste, resumiste o pensaste. Es el cruce entre lo
ejecutable y lo acumulativo: la única base que se conecta con ambos lados.

| Propiedad | Tipo | Valores / Destino |
|---|---|---|
| ● `Name` | title | |
| ● `Tipo` | select | `Nota Reunion` · `Nota Resumen` · `Nota Libro` · `Nota Rapida` |
| ● `Area` | rel → | `Areas` |
| ● `Temas` | rel → | `Temas` |
| `Objetivos` | rel → | `Objetivos` |
| `Proyectos` | rel → | `Proyectos` |
| `Tareas` | rel → | `Tareas` |
| `References` | rel → | `Referencias` — ⚠ en inglés, aquí |
| `Bloques de notas` | rel → | `Bloques de notas` |
| `Destacados` | rel → | `Destacados` |
| `Notas relacionadas` | rel → | `Notas` |
| `Favorito` | checkbox | |
| `Archivo` | checkbox | ⚠ aquí se llama `Archivo` |
| `URL` | url | |
| `Goal Area` · `Topics Area` · `Project Area` · `Notebook Area` | 🔒 rollup | área heredada por cada camino |
| `Creado` / `Editado` | 🔒 auditoría | |

**Al crear:** nombre + `Tipo` + `Area` + `Temas`, **más al menos un enlace a la cadena
ejecutable o a la fuente** (`Proyectos`, `Tareas`, `References`). Una nota sin ningún enlace
queda huérfana y no aparece en ningún contexto.

**Cómo elegir `Tipo`:** `Nota Reunion` si sale de un evento · `Nota Libro` si resume una
referencia larga · `Nota Resumen` si sintetiza varias fuentes · `Nota Rapida` para captura al
vuelo pendiente de procesar.

---

### `Bloques de notas` — cuaderno

**Sirve para** agrupar notas que se leen juntas, como un cuaderno temático. Capa opcional
entre el área y la nota.

| Propiedad | Tipo | Valores / Destino |
|---|---|---|
| ● `Name` | title | |
| ● `Area` | rel → | `Areas` |
| `Descripción` | text | |
| `Notas` | rel → | `Notas` |
| `Counter` | 🔒 formula | cantidad de notas |
| `Archive` | checkbox | |
| `Createado` / `Editado` | 🔒 auditoría | ⚠ `Createado`, con errata |

---

### `Destacados` — el fragmento textual

**Sirve para** rescatar la cita exacta de una fuente, separada de tu interpretación. Es el
eslabón entre la referencia (completa) y la nota (tuya).

⚠ El nombre de la base lleva **un espacio inicial**: `` Destacados``.

| Propiedad | Tipo | Valores / Destino |
|---|---|---|
| ● `Highlight` | title | ⚠ **el título ES la cita** |
| ● `Referencias` | rel → | `Referencias` |
| `Author` | text | |
| `Notas` | rel → | `Notas` |
| `Temas` | rel → | `Temas` |
| `Favourite` | checkbox | ⚠ grafía británica |
| `Media Type` | 🔒 rollup | `Referencias` → `Tipo` |
| `Created` / `Edited` | 🔒 auditoría | |

**Al crear:** la cita va en el título, no en el cuerpo. Siempre enlazar la `Referencias` de
donde salió — sin eso pierde trazabilidad y `Media Type` queda vacío.

---

### `Referencias` — la fuente externa

**Sirve para** registrar todo lo que consumes de afuera: documentos, videos, libros, guías,
presentaciones. Es el punto de entrada del conocimiento al sistema.

| Propiedad | Tipo | Valores / Destino |
|---|---|---|
| ● `Name` | title | |
| ● `Tipo` | select | `Informe` · `Documento Oficial` · `Manual` · `Guia` · `Video` · `Post` · `Libro` · `Presentación` |
| ● `Plataforma` | multi_select | `Educativo` · `Cloud` · `Libreria` · `Gobierno` · `Redes Sociales` · `Website` · `Physical Copy` · `Notion` |
| ● `Status` | status | `Inbox` · `Backlog` · `Up Next` → `In Progress` → `Completed` |
| ● `Areas` | rel → | `Areas` — ⚠ en plural, aquí |
| ● `Temas` | rel → | `Temas` |
| `Objetivos` | rel → | `Objetivos` |
| `Proyectos` | rel → | `Proyectos` |
| `Notas` | rel → | `Notas` |
| `Destacados` | rel → | `Destacados` |
| `References relacionadas` | rel → | `Referencias` |
| `Rating` | select | `★` · `★★` · `★★★` · `★★★★` · `★★★★★` |
| `Fuente` | text | |
| `Descripción` | text | |
| `URL` | url | |
| `Publication Date` | date | |
| `Completed Date` | date | formato `DD/MM/YYYY` |
| `Favorite` | checkbox | |
| `Archive` | checkbox | |
| `Topics Area` | 🔒 rollup | `Temas` → `Area` |
| `Created` / `Edited` | 🔒 auditoría | |

**Al crear:** nombre + `Tipo` + `Plataforma` + `Status` + `Areas` + `Temas`.

**`Tipo` y `Plataforma` son ejes independientes.** `Tipo` es *qué formato tiene*; `Plataforma`
es *de dónde salió*. Una guía de un portal educativo es `Guia` + `Educativo`.

---

## 4. Flujo de ejemplo, de punta a punta

Caso: una asignatura con una entrega en tres etapas. Nombres genéricos; la **forma** es la de
un caso real del workspace.

### Paso 1 — El área ya existe

```
Areas › "[Asignatura]"
  Type: Académico
```

Permanente. No se crea una por entrega ni por semestre.

### Paso 2 — Tema, para acumular material

```
Temas › "[Actividad]"
  Area: [Asignatura]
```

Aquí van a colgar las referencias y las notas. Sobrevive al objetivo.

### Paso 3 — El objetivo, con plazo

```
Objetivos › "[Actividad]"
  Area:     [Asignatura]
  Deadline: 2026-11-20
  Status:   En progreso
```

`Countdown` y `Quarter` empiezan a calcular solos. La plantilla abre el cuerpo con las vistas
de Key Results, Projects, Tasks, Notes y References ya filtradas.

### Paso 4 — Los proyectos, en secuencia

Tres entregas parciales, cada una un proyecto del mismo objetivo:

```
Proyectos › "[Entrega 1]"          Proyectos › "[Entrega 2]"     › "[Entrega 3]"
  Area:         [Asignatura]         Area:      [Asignatura]        …
  Objetivo:     [Actividad]          Objetivo:  [Actividad]
  Status:       In Progress          Status:    Not Started
  Prioridad:    High                 Prioridad: High
  Línea tiempo: 2026-08-25 → 09-14   Línea tiempo: 09-15 → 10-12
```

Las tres cuelgan del **mismo** objetivo. Cada una lleva `Area` propia aunque el objetivo ya la
tenga — es el doble anclaje.

### Paso 5 — Las tareas

```
Tareas › "[Acción concreta]"
  Area:      [Asignatura]
  Proyecto:  [Entrega 1]
  Status:    Inbox        → En proceso → Completed
  Prioridad: Alta
  Contexto:  Computador
  Energía:   High
  Fecha:     2026-08-25
```

Al pasar una tarea a `Completed`, el `Progreso` de `[Entrega 1]` sube solo. **Una tarea colgada
solo del objetivo, sin proyecto, no entra en ningún porcentaje.**

### Paso 6 — El material de apoyo

```
Referencias › "[Enunciado de la actividad]"   Referencias › "[Material de apoyo]"
  Tipo:       Guia                              Tipo:       Presentación
  Plataforma: Educativo                         Plataforma: Educativo
  Status:     Completed                         Status:     Completed
  Areas:      [Asignatura]                      Areas:      [Asignatura]
  Temas:      [Actividad]                       Temas:      [Actividad]
```

Ambas se enlazan también al proyecto, desde `` Referencias`` del proyecto.

### Paso 7 — La nota que cruza todo

```
Notas › "[Hallazgos de la investigación]"
  Tipo:       Nota Rapida
  Area:       [Asignatura]
  Temas:      [Actividad]
  Proyectos:  [Entrega 1]
  References: [Enunciado de la actividad]
```

Esta nota queda visible desde el área, desde el tema, desde el proyecto y desde la referencia.
Es lo que hace que el material siga siendo encontrable cuando el objetivo ya se cerró.

### El resultado

```
[Asignatura] ─┬─ Tema [Actividad] ──┬── Referencias ×2
              │                     └── Nota
              └─ Objetivo [Actividad]  (deadline, countdown)
                    ├── [Entrega 1]  In Progress · Progreso ▓▓▓░░
                    │      ├── Tareas ×4
                    │      ├── Referencias ×2
                    │      └── Nota
                    ├── [Entrega 2]  Not Started
                    └── [Entrega 3]  Not Started
```

---

## 5. Reglas para crear

Aplican igual a una persona y a un agente. Un registro que las incumple *parece* correcto pero
queda fuera de las vistas, los filtros y los cálculos.

### 5.1 Usar siempre la plantilla del recurso

**Las 11 bases tienen plantilla por defecto.** No es decoración: el cuerpo trae las vistas
embebidas ya filtradas al registro, y es lo que invita a conectar el resto.

```
Objetivos  →  Key Results · Projects · Tasks · Notes · References
Proyectos  →  Tasks · Meetings · Notes · References
```

- **Desde la interfaz:** crear con el botón `New` de la base, que aplica la plantilla. No usar
  "página en blanco".
- **Desde la API o MCP:** la plantilla por defecto no siempre se aplica sola. Después de crear,
  verificar que el cuerpo tenga las vistas; si no las tiene, duplicar la plantilla del recurso
  en vez de dejar la página vacía.

### 5.2 Doble anclaje: siempre llenar `Area`

Cada registro se ancla al área **por dos caminos**: la propiedad `Area` directa, y el rollup
`*Area` que la hereda por la cadena.

- Solo el padre, sin `Area` → el registro desaparece de las vistas por área.
- Solo `Area`, sin padre → queda fuera de todo cálculo de progreso.
- Si el `Area` directa y la heredada no coinciden → hay algo mal clasificado. Es un chequeo de
  integridad gratis.

**Regla:** al crear cualquier cosa, llenar `Area` *además* de la relación con su padre.

### 5.3 Orden de creación

```
Area → Tema → Objetivo → Proyecto → Tarea
```

Referencias y Notas entran en cualquier momento; Key Results y Eventos, después del objetivo y
del proyecto respectivamente. Crear de abajo hacia arriba deja huérfanos.

### 5.4 Estados: qué significan y qué mueven

| Recurso | Estados | Nota |
|---|---|---|
| `Objetivos` | `No empezado` / `En progreso` / `Completado` | |
| `Proyectos` | `Inbox` / `Not Started` / `In Progress` / `On Hold` / `Completed` | |
| `Tareas` | `Inbox` / `Sin fecha` / `En proceso` / `Esperando` / `Completed` | **mueve el `Progreso`** |
| `Referencias` | `Inbox` / `Backlog` / `Up Next` / `In Progress` / `Completed` | |
| `Key Results` | `Open` / `Closed` | |

Los vocabularios no coinciden entre bases — hay que usar el literal exacto de cada una.

**`Inbox` es un estado real, no un error.** Es para capturar sin decidir. Sacar algo del Inbox
significa: llenar `Area`, enlazar al padre y poner fecha.

**El `Progreso` del proyecto depende del *grupo* del estado, no de la etiqueta.** Cuenta las
tareas cuyo `Status` cae en el grupo `Complete`. Renombrar una etiqueta es seguro; mover una
opción de grupo altera en silencio el porcentaje de todos los proyectos.

### 5.5 Archivar, nunca borrar

Marcar el checkbox de archivado: el registro sale de las vistas activas por filtro y conserva
sus relaciones. Borrar se lleva por delante los rollups de todo lo que lo referenciaba.

| Recurso | Propiedad |
|---|---|
| `Areas` · `Temas` · `Objetivos` · `Bloques de notas` · `Referencias` | `Archive` |
| `Proyectos` · `Notas` | `Archivo` |
| `Tareas` · `Eventos` · `Key Results` · `Destacados` | ninguna — solo `Status` |

### 5.6 Trampas de nomenclatura al escribir por API

Los nombres no son uniformes. Copiarlos exactos:

| Trampa | Correcto |
|---|---|
| Título de `Tareas` | `Nombre`, no `Name` |
| Título de `Destacados` | `Highlight`, no `Name` |
| Relación a referencias en `Proyectos` | `` Referencias`` **con espacio inicial** |
| Nombre de la base de destacados | `` Destacados`` **con espacio inicial** |
| Relación a referencias en `Notas` | `References`, en inglés |
| Relación a áreas en `Referencias` | `Areas`, en plural |
| Checkbox de archivado | `Archive` o `Archivo` según la base |
| Favorito | `Favorito` (Notas) · `Favorite` (Referencias) · `Favourite` (Destacados) |
| Creación en `Bloques de notas` | `Createado`, con errata |

Además: `Energía` reusa las etiquetas `Low`/`Medium`/`High` que `Proyectos.Prioridad` usa con
otro significado — no confundirlas.

### 5.7 Qué no tocar

| Acción | Consecuencia |
|---|---|
| Borrar una base bajo `Bases de datos` | Destruye todas sus relaciones. Irrecuperable en la práctica |
| Mover una opción de `Tareas.Status` a otro grupo | Altera el `Progreso` de todos los proyectos, sin aviso |
| Renombrar una propiedad de relación | Rompe fórmulas, rollups y llamadas por API |
| Cambiar el destino de una relación | Vacía los valores existentes |
| Borrar en vez de archivar | Se lleva los rollups de todo lo que apuntaba al registro |

**Seguro de cambiar:** contenido, vistas, filtros, iconos, portadas, y renombrar *etiquetas* de
estado mientras no cambien de grupo.
