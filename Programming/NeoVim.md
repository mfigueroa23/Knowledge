# Flujo de Trabajo y Atajos de NeoVim

Tecla líder (leader): `Space`

---

## Tabla de Contenidos

- [Navegación](#navegación)
  - [Splits / Paneles](#splits--paneles)
  - [Explorador de Archivos](#explorador-de-archivos)
  - [Navegación de Buffers](#navegación-de-buffers)
  - [Búsqueda de Archivos](#búsqueda-de-archivos)
  - [Editor](#editor)
- [Edición](#edición)
  - [Yank / Copiar](#yank--copiar)
  - [Eliminar / Cortar](#eliminar--cortar)
  - [Pegar](#pegar)
  - [Cambiar / Reemplazar](#cambiar--reemplazar)
  - [Deshacer / Rehacer](#deshacer--rehacer)
  - [Modo Visual](#modo-visual)
  - [Mover Líneas](#mover-líneas)
  - [Marcas y Saltos](#marcas-y-saltos)
  - [Buscar y Reemplazar](#buscar-y-reemplazar)
- [Programación (LSP)](#programación-lsp)
  - [Atajos de LSP](#atajos-de-lsp)
  - [Autocompletado](#autocompletado-nvim-cmp)
  - [Copilot](#copilot)
  - [Claude Code](#claude-code-claudecodenvim)
  - [Formateo y Linting](#formateo-y-linting-none-ls)
- [Git](#git)
  - [Gitsigns](#gitsigns)
  - [Fugitive](#fugitive-modo-comando)
- [GitHub (Octo)](#github-octo)
  - [Pull Requests](#pull-requests)
  - [Issues](#issues)
- [Testing](#testing-vim-test--herdr)
- [API / Swagger](#api--swagger)
- [Salud y Gestión de Plugins](#salud-de-neovim-y-gestión-de-plugins)

---

## Navegación

### Splits / Paneles
Navegación fluida entre splits de NeoVim y paneles de herdr (herdr-nvim-nav).

| Tecla | Acción |
|---|---|
| `<C-h>` / `<C-Left>` | Ir al split / panel de herdr izquierdo |
| `<C-j>` / `<C-Down>` | Ir al split / panel de herdr inferior |
| `<C-k>` / `<C-Up>` | Ir al split / panel de herdr superior |
| `<C-l>` / `<C-Right>` | Ir al split / panel de herdr derecho |

### Explorador de Archivos
| Tecla | Acción |
|---|---|
| `<C-n>` | Alternar Neo-tree (barra lateral izquierda) |
| `-` | Abrir el explorador de archivos Oil (flotante, editable) |

### Navegación de Buffers
| Tecla / Comando | Acción |
|---|---|
| `<leader>bf` | Lista de buffers de Neo-tree (selector flotante) |
| `<C-^>` o `<C-6>` | Alternar entre el buffer actual y el alternativo (lo más rápido) |
| `:bn` / `:bp` | Buffer siguiente / anterior |
| `:b#` | Saltar al buffer alternativo (último) |
| `:b <num>` | Saltar a un buffer por número |
| `:bd` | Eliminar (cerrar) el buffer actual |
| `:ls` | Listar todos los buffers abiertos con sus números |

> `<C-^>` es la forma más rápida de alternar entre dos archivos sin salir del modo normal.

### Búsqueda de Archivos
| Tecla | Acción |
|---|---|
| `<C-p>` | Búsqueda difusa de archivos (Telescope) |
| `<leader><leader>` | Archivos recientes (Telescope) |
| `<leader>fg` | Live grep en todo el proyecto (Telescope) |

### Editor
| Tecla | Acción |
|---|---|
| `<leader>h` | Limpiar el resaltado de búsqueda |

---

## Edición

### Yank / Copiar
| Tecla | Acción |
|---|---|
| `yy` o `Y` | Copiar (yank) la línea actual |
| `yw` | Copiar palabra |
| `y$` | Copiar hasta el final de la línea |
| `yi"` / `ya"` | Copiar dentro de / alrededor de las comillas |

### Eliminar / Cortar
| Tecla | Acción |
|---|---|
| `dd` | Eliminar (cortar) la línea actual |
| `dw` | Eliminar palabra |
| `d$` o `D` | Eliminar hasta el final de la línea |
| `x` | Eliminar el carácter bajo el cursor |

### Pegar
| Tecla | Acción |
|---|---|
| `p` | Pegar después del cursor |
| `P` | Pegar antes del cursor |
| `"0p` | Pegar desde el registro de yank (ignora el texto eliminado) |

### Cambiar / Reemplazar
| Tecla | Acción |
|---|---|
| `cc` o `S` | Cambiar la línea completa |
| `cw` | Cambiar palabra |
| `c$` o `C` | Cambiar hasta el final de la línea |
| `r<char>` | Reemplazar el carácter bajo el cursor |
| `R` | Entrar en modo reemplazo |
| `s` | Sustituir carácter (eliminar + insertar) |

### Deshacer / Rehacer
| Tecla | Acción |
|---|---|
| `u` | Deshacer |
| `<C-r>` | Rehacer |

### Modo Visual
| Tecla | Acción |
|---|---|
| `v` | Modo visual por caracteres |
| `V` | Modo visual por líneas |
| `<C-v>` | Modo visual por bloques |
| `gv` | Volver a seleccionar la última selección visual |
| `>` / `<` | Indentar / desindentar la selección |

### Mover Líneas
| Tecla | Acción |
|---|---|
| `>>` / `<<` | Indentar / desindentar la línea actual |
| `:m .+1` / `:m .-2` | Mover la línea hacia abajo / arriba |
| (visual) `:m '>+1` / `:m '<-2` | Mover las líneas seleccionadas hacia abajo / arriba |

### Marcas y Saltos
| Tecla | Acción |
|---|---|
| `m<letra>` | Establecer marca |
| `'<letra>` | Saltar a la marca |
| `<C-o>` / `<C-i>` | Saltar hacia atrás / adelante en la lista de saltos |

### Buscar y Reemplazar
| Comando | Acción |
|---|---|
| `:%s/old/new/g` | Reemplazar todas las ocurrencias en el archivo |
| `:%s/old/new/gc` | Reemplazar todas con confirmación |
| `:s/old/new/g` | Reemplazar solo en la línea actual |

---

## Programación (LSP)

Los servidores LSP arrancan automáticamente según el tipo de archivo. Gestionados por Mason (`:Mason` para abrir la interfaz).

| Lenguaje | LSP |
|---|---|
| TypeScript / JavaScript | `ts_ls` |
| Python | `pyright` |
| Go | `gopls` |
| Java | `jdtls` (vía nvim-jdtls) |
| C# / .NET | `omnisharp` |
| Bash | `bashls` |
| HTML | `html` |
| CSS | `cssls` |
| Tailwind CSS | `tailwindcss` |
| YAML (Docker / K8s) | `yamlls` |
| Lua | `lua_ls` |
| Angular | `angularls` |
| Dockerfile | `dockerls` |
| Docker Compose | `docker_compose_language_service` |
| Markdown | `marksman` |

### Atajos de LSP
| Tecla | Acción |
|---|---|
| `K` | Documentación al pasar el cursor (hover) |
| `<leader>gd` | Ir a la definición |
| `<leader>gr` | Buscar referencias |
| `<leader>ca` | Acción de código (code action) |
| `<leader>gf` | Formatear el buffer |

### Autocompletado (nvim-cmp)
| Tecla | Acción |
|---|---|
| `<C-Space>` | Activar el autocompletado |
| `<CR>` | Confirmar la selección |
| `<C-e>` | Abortar / cerrar el menú |
| `<C-b>` | Desplazar la documentación hacia arriba |
| `<C-f>` | Desplazar la documentación hacia abajo |

### Copilot
| Tecla | Modo | Acción |
|---|---|---|
| `<C-S-y>` | Insertar | Aceptar la sugerencia de Copilot |
| `<C-S-n>` | Insertar | Descartar la sugerencia de Copilot |

> El mapeo por defecto de `Tab` está deshabilitado para que no choque con nvim-cmp.

### Claude Code (claudecode.nvim)
Conecta la CLI `claude` con los buffers de NeoVim: abre Claude Code en una terminal integrada, envía selecciones/buffers como contexto y muestra los cambios propuestos como diffs revisables. Usa el login/suscripción de `claude` que ya esté activo en el `PATH`, sin configuración adicional.

| Tecla | Modo | Acción |
|---|---|---|
| `<leader>cc` | Normal | Alternar la terminal de Claude Code |
| `<leader>cf` | Normal | Enfocar la terminal de Claude Code |
| `<leader>cr` | Normal | Reanudar Claude (`--resume`) |
| `<leader>cC` | Normal | Continuar Claude (`--continue`) |
| `<leader>cm` | Normal | Seleccionar modelo |
| `<leader>cb` | Normal | Añadir el buffer actual al contexto |
| `<leader>cs` | Visual | Enviar la selección a Claude |
| `<leader>cy` | Normal | Aceptar el diff |
| `<leader>cn` | Normal | Rechazar el diff |

> `<leader>ca` queda reservado para Code Action de LSP (ver [Atajos de LSP](#atajos-de-lsp)) — aceptar/rechazar diffs usa `y`/`n` para evitar el conflicto.

### Formateo y Linting (none-ls)
Se ejecuta automáticamente con `<leader>gf`.

| Herramienta | Lenguaje |
|---|---|
| `prettier` | JS, TS, HTML, CSS, YAML, Markdown |
| `stylua` | Lua |
| `black` | Python |
| `markdownlint` | Markdown (linter) |

---

## Git

Impulsado por **vim-fugitive** (comandos completos de git) + **gitsigns** (navegación de hunks y blame).

### Gitsigns
| Tecla | Acción |
|---|---|
| `<leader>gp` | Previsualizar hunk (diff en línea) |
| `<leader>gt` | Alternar blame por línea |

### Fugitive (modo comando)
| Comando | Acción |
|---|---|
| `:Git` | Git status interactivo |
| `:Git add %` | Añadir el archivo actual al stage |
| `:Git commit` | Hacer commit |
| `:Git push` | Hacer push |
| `:Git pull` | Hacer pull |
| `:Git diff` | Ver diff |
| `:Git log` | Ver log |
| `:Git blame` | Blame (archivo completo) |

---

## GitHub (Octo)

Requiere la CLI `gh` autenticada (`gh auth login`).

### Pull Requests
| Tecla | Acción |
|---|---|
| `<leader>opl` | Listar PRs |
| `<leader>opc` | Crear PR |
| `<leader>opm` | Mergear PR |
| `<leader>opr` | Revisar PR (comentarios en línea) |
| `<leader>opd` | Diff del PR |

### Issues
| Tecla | Acción |
|---|---|
| `<leader>oil` | Listar issues |
| `<leader>oic` | Crear issue |

> Dentro de cualquier buffer de Octo, ejecuta `:help octo-mappings` para ver la lista completa de atajos locales al buffer (asignados, etiquetas, reacciones, etc).

---

## Testing (vim-test + herdr)

Los tests se ejecutan en un panel de herdr dividido debajo del editor, reutilizado entre ejecuciones (estrategia `herdr` personalizada para vim-test). Fuera de una sesión de herdr, recurre a `:terminal`.

| Tecla | Acción |
|---|---|
| `<leader>t` | Ejecutar el test más cercano |
| `<leader>T` | Ejecutar todos los tests del archivo |
| `<leader>a` | Ejecutar la suite de tests completa |
| `<leader>l` | Volver a ejecutar el último test |
| `<leader>g` | Ir al archivo de test (TestVisit) |

---

## API / Swagger

| Tecla | Acción |
|---|---|
| `<leader>sw` | Abrir la vista previa de Swagger UI en el navegador |

Abre una Swagger UI con recarga en vivo a partir del archivo `openapi.yaml` / `openapi.json` actual.

---

## Salud de NeoVim y Gestión de Plugins

| Comando | Acción |
|---|---|
| `:Lazy` | Abrir la interfaz del gestor de plugins |
| `:Lazy sync` | Actualizar todos los plugins |
| `:Mason` | Abrir la interfaz de instalación de LSP/herramientas |
| `:TSUpdate` | Actualizar los parsers de Treesitter |
| `:checkhealth` | Ejecutar las comprobaciones de salud de NeoVim |
| `:source %` | Recargar el archivo de configuración actual |
