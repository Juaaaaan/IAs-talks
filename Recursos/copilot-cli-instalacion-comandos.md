---
type: recurso
title: "GitHub Copilot CLI — instalación, comandos y primeras tareas"
description: "Dossier técnico de GitHub Copilot CLI: instalación en todas las plataformas, autenticación, comandos de terminal, comandos dentro de sesión (slash commands), atajos de teclado y ejemplos de primeras tareas aplicados a RCA. Material complementario de la Charla 23 — Copilot CLI es, en la práctica, el mismo ODD que se contó allí como protocolo abstracto."
tags: [recurso, copilot, copilot-cli, cli, agentes, herramientas, charla-23]
related:
  - "[[guion-charla-23]]"
  - "[[MATERIAL-CHARLA-23-COMPROBAR-ANTES-DE-CONSTRUIR]]"
  - "[[guion-charla-8]]"
  - "[[ai-harness-engineering]]"
  - "[[odd]]"
  - "[[bdd]]"
timestamp: "2026-10-16"
fuente: "https://docs.github.com/en/copilot/how-tos/copilot-cli/set-up-copilot-cli/install-copilot-cli"
---

# GitHub Copilot CLI — instalación, comandos y primeras tareas

> Dossier técnico de referencia. Nace como material de apoyo a la Charla 23 (Comprobar antes de construir): lo que allí se explicó como ODD en abstracto es, literalmente, lo que Copilot CLI hace por debajo cuando clasifica un cambio como pequeño o sustancial. Recurso para consultar o reutilizar en futuras charlas sobre agentes de terminal.

---

## 1. Qué es

GitHub Copilot CLI es la versión de terminal de Copilot: un agente que vive en la línea de comandos, explora el proyecto en el que estás, y puede leer, escribir y ejecutar cosas en tu nombre (con permiso) en lugar de limitarse a autocompletar código en el editor. Es el mismo Copilot que ya usamos en `.github/` (Charla 8), pero como agente interactivo en vez de como asistente dentro del IDE.

## 2. Instalación

Requiere una suscripción activa de Copilot. Si viene de una organización, el admin tiene que tener habilitada la política de Copilot CLI.

| Método | Comando | Plataforma |
|---|---|---|
| npm | `npm install -g @github/copilot` | Todas (requiere Node.js 22+) |
| WinGet | `winget install GitHub.Copilot` | Windows |
| Homebrew | `brew install --cask copilot-cli` | macOS y Linux |
| Script de instalación | `curl -fsSL https://gh.io/copilot-install \| bash` | macOS y Linux |
| Descarga directa | Binario desde la página de releases de `copilot-cli` en GitHub | Todas |

En Windows hace falta PowerShell v6 o superior. Si el `.npmrc` tiene `ignore-scripts=true`, hay que instalar con `npm_config_ignore_scripts=false npm install -g @github/copilot`.

**Para una demo:** basta con mostrar el comando npm — es el más universal y el que ya usamos para otras herramientas. El resto queda de referencia por si alguien pregunta por Mac/Windows nativo.

## 3. Primer arranque y autenticación

1. Escribir `copilot` en la terminal para lanzar la interfaz interactiva.
2. Si no has iniciado sesión, te pide ejecutar `/login` (autenticación vía OAuth con tu cuenta de GitHub).
3. Alternativa sin interacción: crear un token de acceso personal de grano fino en GitHub, activar el permiso **Copilot Requests** en la pestaña "Account", y exportarlo como variable de entorno `COPILOT_GITHUB_TOKEN` (o `GH_TOKEN` / `GITHUB_TOKEN`).
4. La primera vez que abres un proyecto, Copilot pide permiso para explorar y modificar ficheros de esa carpeta — puedes darlo solo para la sesión o guardarlo para no repetir el permiso cada vez.

**Frase útil:** _"Se autentica una vez, con tu cuenta de GitHub de siempre. Nada nuevo que recordar."_

## 4. Comandos de terminal (fuera de una sesión)

Estos se escriben directamente en la terminal, antes de entrar al modo interactivo:

| Comando | Para qué sirve |
|---|---|
| `copilot` | Abre la interfaz interactiva |
| `copilot app` | Abre la app de Copilot en la carpeta actual, nueva sesión |
| `copilot init` | Genera las instrucciones personalizadas de Copilot para el repositorio (el equivalente a lo que vimos en la Charla 8 con `.github/copilot-instructions.md`) |
| `copilot login [opción]` | Autenticación vía OAuth (`--host`, `--web-flow`, `--device-code`, `--with-token`) |
| `copilot mcp` | Gestiona la configuración de servidores MCP |
| `copilot plugin` | Lista, instala, activa o desactiva plugins |
| `copilot skill` | Lista, añade, activa o desactiva skills del agente |
| `copilot config [clave] [valor]` | Lee o cambia ajustes fuera de una sesión |
| `copilot update` | Descarga e instala la última versión |
| `copilot version` | Muestra la versión instalada |
| `copilot workflow run NOMBRE-WORKFLOW` | Ejecuta un workflow predefinido sin pedir nada por chat |
| `copilot help [tema]` | Ayuda sobre un tema concreto (billing, config, permissions, sandbox…) |

**Para una demo:** de esta lista, solo `copilot`, `copilot init` y quizás `copilot mcp` (porque ya conectamos MCPs en charlas anteriores) merecen pantalla. El resto es referencia de "por si lo necesitáis".

## 5. Comandos dentro de una sesión (slash commands)

Una vez dentro de la interfaz interactiva, se escriben con `/`:

| Comando | Para qué sirve |
|---|---|
| `/login`, `/logout` | Entrar o salir de la cuenta de Copilot |
| `/model [modelo]` | Ver el menú de modelos disponibles, o fijar uno directamente |
| `/agent` | Cambia a un agente personalizado |
| `/mcp [show\|add\|edit\|delete\|disable\|enable]` | Gestiona los servidores MCP conectados |
| `/add-dir <carpeta>` | Da acceso a Copilot a otra carpeta además de la actual |
| `/list-dirs` | Lista las carpetas a las que Copilot tiene acceso |
| `/cwd [carpeta]` | Muestra o cambia la carpeta de trabajo actual |
| `/clear` | Reinicia la conversación — borra el contexto previo |
| `/reset-allowed-tools` | Olvida los permisos de herramientas ya aprobados |
| `/delegate <tarea>` | Copilot hace los cambios y abre un pull request en remoto, en segundo plano |
| `/share [file\|gist] [ruta]` | Exporta la sesión como markdown o como Gist de GitHub |
| `/session`, `/usage` | Muestra métricas de uso de la sesión actual |
| `/theme` | Cambia el tema de color de la terminal |
| `/user [show\|list\|switch]` | Ver, listar o cambiar la cuenta de GitHub en uso |
| `/help` | Lista todos los comandos y atajos disponibles |
| `/feedback` | Envía feedback o un bug a GitHub |
| `/exit`, `/quit` | Cierra la sesión |

**Los tres que de verdad importan para una demo:** `/model` (para que la audiencia vea que no es un único modelo fijo), `/mcp` (callback directo a charlas anteriores), y `/delegate` (es el más espectacular: Copilot abre un PR solo, en remoto, sin que tengas la terminal abierta esperando).

## 6. Atajos de teclado dentro de una sesión

- `!` ejecuta un comando de shell local sin salir de Copilot. `$` solo te pasa a una shell completa.
- `@nombre-fichero` añade el contenido de un fichero al contexto. `#número` añade una issue o PR.
- `Shift+Tab` cambia entre los modos estándar, plan y autopilot.
- `Esc` dos veces interrumpe lo que está haciendo. `Ctrl+C` dos veces cierra Copilot del todo.
- `Ctrl+L` limpia la pantalla. `Ctrl+Enter` o `Ctrl+Q` encola un mensaje mientras el agente sigue trabajando.
- `Ctrl+X` luego `b` manda la tarea actual a segundo plano. `Ctrl+X` luego `x` cierra la sesión.

**Para una demo:** probablemente solo `!` (ejecutar shell sin salir) y el cambio de modo con `Shift+Tab` tienen valor visual para una audiencia no técnica — el resto es más para quien ya lo usa a diario.

## 7. Cómo empezar una tarea — ejemplos reales

Según la documentación oficial, una primera sesión típica es:

1. **Visión general del proyecto** — escribir literalmente _"Give me an overview of this project"_ (o en español, "dame un resumen de este proyecto"). Copilot explora el repo, abre los ficheros importantes y te cuenta qué encontró. Es el mejor primer ejemplo para una demo: no modifica nada, solo demuestra que "entiende" el proyecto.

2. **Pedir código nuevo** — por ejemplo, "añade un endpoint que devuelva todas las categorías". Copilot revisa la documentación y los ejemplos existentes, sigue el patrón del proyecto, y pide tu permiso antes de crear el fichero. Este es el ejemplo que conecta con ODD (Charla 23): explora, clasifica, y antes de tocar nada pide confirmación si el cambio lo merece.

3. **Delegar una tarea completa** — `/delegate` seguido de una tarea bien definida (por ejemplo, el número de una issue). El agente en la nube de Copilot crea una rama, abre un pull request en borrador, y hace los cambios en segundo plano, sin que tengas que esperar con la terminal abierta. Luego te avisa para que lo revises.

## 8. Ejemplos aplicados a RCA (para una demo)

Usando el mismo proyecto de siempre (Resin Craft Art):

| Prompt | Qué demuestra |
|---|---|
| "Dame un resumen de este proyecto" | Exploración — Copilot entiende Angular, Supabase, Tailwind v4 sin que se le explique nada |
| "Cambia el color del botón de 'Añadir al carrito' a un tono más cálido" | Cambio pequeño — callback directo al ejemplo de ODD de la Charla 23 |
| "Añade un endpoint que devuelva las piezas con stock bajo" | Cambio sustancial — sigue los patrones existentes (Signals, `inject()`, Supabase) |
| `/delegate` + número de issue real de RCA | El más espectacular: PR en remoto, sin supervisión directa, para verlo "trabajar solo" |

**Nota:** este recurso conecta directamente con la Charla 23 — ODD ya no es solo un protocolo abstracto, es literalmente lo que hace Copilot CLI por debajo cuando se clasifica un cambio como pequeño o sustancial.

## 9. Lo que no suele aportar en una demo ante audiencia no técnica

Por la profundidad de la lista de comandos, hay mucho material que un desarrollador necesita pero que no aporta a una audiencia mayoritariamente no técnica:
- `copilot config`, `copilot workflow run`, `copilot sandbox ca`, `copilot lsp list` — demasiado operativo.
- La lista completa de atajos de teclado — mostrar 2 o 3, no las quince.
- La autenticación con token de grano fino — mencionar que existe, sin entrar en el detalle del scope "Copilot Requests".

## Fuentes

- [Installing GitHub Copilot CLI — GitHub Docs](https://docs.github.com/en/copilot/how-tos/copilot-cli/set-up-copilot-cli/install-copilot-cli)
- [Command-line commands — GitHub Docs](https://docs.github.com/en/copilot/reference/copilot-cli-reference/cli-command-reference)
- [A cheat sheet to slash commands in GitHub Copilot CLI — The GitHub Blog](https://github.blog/developer-skills/github/a-cheat-sheet-to-slash-commands-in-github-copilot-cli)
- [GitHub Copilot CLI for Beginners: Getting started — The GitHub Blog](https://github.blog/ai-and-ml/github-copilot/github-copilot-cli-for-beginners-getting-started-with-github-copilot-cli/)
