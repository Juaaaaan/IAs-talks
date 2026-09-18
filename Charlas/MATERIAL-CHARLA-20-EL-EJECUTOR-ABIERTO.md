---
type: material
title: "Charla 20 — La otra correa del arnés: el ejecutor abierto (guía completa de OpenCode)"
description: "Material extendido de la Charla 20: el hilo de la charla (especificar vs ejecutar, cerrado vs abierto, gobernanza) más una guía de referencia completa de OpenCode — instalación, autenticación y proveedores, configuración y precedencia (incluida la config gestionada por la organización), agentes, permisos, skills, reglas, references, MCP, comandos y herramientas personalizadas, plugins, TUI (temas y keybinds), el servidor headless, el SDK, cómo montar un frontal propio, un flujo de trabajo de principio a fin, gobernanza en empresa y ecosistema."
tags: [material, charla-20, opencode, ejecutor, arnes, gobernanza, open-source, guia, instalacion, sdk, configuracion, agentes, plugins]
related:
  - "[[guion-charla-20]]"
  - "[[guion-charla-16]]"
  - "[[guion-charla-19]]"
  - "[[opencode]]"
  - "[[claude-code]]"
  - "[[el-arnes]]"
charla: 20
estado: borrador
timestamp: 2026-09-15
fuente: "https://opencode.ai/docs"
---

# La otra correa del arnés: el ejecutor abierto — guía completa de OpenCode

*Material extendido de la Charla 20. La **Parte 1** es el hilo de la charla, para leer con calma. La **Parte 2** es una guía de referencia de OpenCode: instalación, uso, configuración, extensión y despliegue. Los comandos y opciones están verificados contra la documentación oficial (`opencode.ai/docs`), pero OpenCode se mueve muy rápido: el esquema en `opencode.ai/config.json` es la fuente de verdad, y ante cualquier duda conviene contrastar la doc y el changelog.*

---

# Parte 1 — El hilo de la charla

## Dos cosas que solemos mezclar: especificar y ejecutar

Llevamos toda la serie montando un *arnés* para la IA: riendas para que el caballo no se desboque. En la [[guion-charla-16|Charla 16]] miramos la correa de **especificar** —decir bien QUÉ queremos antes de que la IA toque nada— y para ejecutar ese trabajo usamos Claude Code. Hoy tocaba la otra correa. Cuando decimos "la IA programa" juntamos dos cosas distintas:

- **Especificar**: decidir y describir qué queremos. La correa del QUÉ.
- **Ejecutar**: el agente que lee el código, lo entiende y hace los cambios. La correa del QUIÉN lo hace.

Lo interesante del ejecutor no es tanto *qué hace*, sino *de quién depende*.

## El ejecutor cerrado: potente, pero de otro

Un ejecutor como **Claude Code** es una maravilla: le das una tarea, mira el proyecto entero, razona y hace los cambios él solo. Pero tiene tres características (sin juzgarlas): funciona con un único proveedor, es cerrado (no ves cómo está hecho) y, para trabajar, tu código sale a un servidor de un tercero. No es malo — es un *trade-off*. Lo importante es ver que ahí hay **una decisión tomada, y la ha tomado el proveedor, no tú**. Lo mismo vale para el **Copilot de Office** que muchos usáis a diario, y para su primo **GitHub Copilot** (que hasta te deja elegir el modelo, pero sigue siendo una caja cerrada y alojada fuera).

> **Elegir el motor dentro de la caja no es lo mismo que controlar la caja.**

## El ejecutor abierto: OpenCode

La misma herramienta, construida al revés en tres cosas:

1. **Es abierto de verdad.** Licencia MIT, código público, cientos de contribuidores. Puedes verlo, cambiarlo y montarlo en tu casa.
2. **No te casa con ningún proveedor.** Le enchufas el motor que quieras, incluido uno local o interno.
3. **Los datos no salen de casa.** Si el motor es interno o local, tu código nunca viaja a un tercero. Funciona hasta sin internet.

Se parece a Claude Code o Copilot en el uso — normal, hacen el mismo trabajo. **La diferencia no está en cómo se usa, sino en de quién es.** Misma cara, dueño distinto.

> **El mismo trabajo. Pero el motor lo eliges tú, y tus datos se quedan en casa.**

## ¿Y a mí qué?

Porque esta decisión —abierto o cerrado— se está tomando en empresas como la nuestra ahora mismo. Una empresa elige lo abierto para **no quedar atrapada** (ni a un proveedor ni a su precio), para **gobernar sus datos** (RGPD, información sensible: con un motor interno, no salen de casa) y para **correr contra lo suyo** (sus propios modelos o acuerdos). Y hay un paso más: **porque es abierto, se construye encima** — la gente monta sus propias apps con OpenCode de motor por debajo.

> **La factura y los datos dejan de ser rehenes.**

## Las tres preguntas y lo que te llevas

Ni abierto es siempre bueno ni cerrado siempre malo. Para decidir: **¿qué necesito gobernar?**, **¿cuántas manos tengo?**, **¿qué datos toca?**. Y la idea que se lleva todo el mundo, aunque nunca abra una terminal:

> **¿Quién controla la IA que usa mi empresa, y dónde viven mis datos?**

---

# Parte 2 — Guía completa de OpenCode

## 1. Qué es, y cómo está montado

OpenCode es un **agente de código open source (MIT)** de la empresa Anomaly (repo `anomalyco/opencode`). Dos ideas de arquitectura importan:

- **Es cliente-servidor.** Hay un servidor que hace el trabajo (habla con el modelo, lee y edita ficheros, ejecuta comandos) y un cliente que lo maneja. Esto permite usarlo desde distintas "caras" y, sobre todo, **construir las tuyas propias por encima**.
- **Es agnóstico de proveedor.** Funciona con **75+ proveedores** de modelos, incluidos **modelos locales**.

Superficies: **terminal (TUI)**, **app de escritorio** e **integración con el editor**.

## 2. Requisitos previos

- Un **terminal moderno**: WezTerm, Alacritty, Ghostty o Kitty van especialmente finos.
- **Claves de API** de los proveedores que quieras usar — o **OpenCode Zen**, una lista curada de modelos ya verificados, si empiezas de cero.

## 3. Instalación

```bash
# La vía más sencilla
curl -fsSL https://opencode.ai/install | bash

# Node.js (también bun, pnpm, yarn)
npm install -g opencode-ai

# Homebrew (macOS y Linux) — el tap recomendado va más al día
brew install anomalyco/tap/opencode

# Arch Linux
sudo pacman -S opencode        # estable
paru -S opencode-bin           # última desde AUR
```

En **Windows** se recomienda **WSL** para compatibilidad total; también `scoop install opencode` y `choco install opencode`. Para **actualizar**, con `"autoupdate": true` se actualiza solo. Para **servidor** hay imágenes **Docker** versionadas (`ghcr.io/anomalyco/opencode:2.0.0`).

## 4. Conectar un proveedor de modelo (autenticación)

Tres caminos según de dónde venga el "motor":

1. **Con asistente:**
   ```bash
   opencode auth login
   ```
   (o `/connect` dentro de la interfaz). Si empiezas de cero, se recomienda **Zen**; con tu suscripción, Claude Pro/Max suele salir más económico.

2. **Con tu propia clave**, sin dejarla escrita, usando interpolación de entorno:
   ```json
   { "provider": { "anthropic": { "options": { "apiKey": "{env:ANTHROPIC_API_KEY}" } } } }
   ```

3. **Contra un endpoint propio o interno** (gateway de empresa, modelo local, proveedor compatible con OpenAI) con `baseURL` — el patrón que hace que **los datos no salgan de casa**:
   ```json
   { "provider": { "anthropic": { "options": { "baseURL": "https://gateway-interno.miempresa.com/v1" } } } }
   ```
   Para local se usan **Ollama** o **LM Studio**; también existe **OpenRouter** integrado (una clave, muchos modelos).

## 5. Primeros pasos

```bash
cd ruta/a/tu/proyecto
opencode
```

Dentro, inicializa el proyecto con `/init`: OpenCode lo analiza y crea un **`AGENTS.md`** en la raíz. **Commitéalo a Git** — es el "contexto persistente" del proyecto (estructura, convenciones, patrones). A partir de ahí, pídele en lenguaje natural. Trucos: `@` (buscador difuso de ficheros), `/help` (ayuda), `/share` (enlace para compartir la sesión). Recomendación: pídele **primero un plan**, luego que lo ejecute.

## 6. Modos Plan y Build

- **Plan** — razona y propone, pero **no toca nada** (edición y comandos deshabilitados).
- **Build** — ejecuta los cambios.

El "piensa antes de actuar" metido en la herramienta.

## 7. Elegir y configurar el modelo

- `/models` abre el selector en la interfaz.
- En config: `"model": "proveedor/modelo"` (p. ej. `anthropic/claude-sonnet-4-5`, o con Zen `opencode/gpt-5.1-codex`).
- `small_model` aparte para tareas ligeras (resúmenes, títulos), para no gastar el grande en todo.
- **75+ proveedores**, **locales** (Ollama, LM Studio) y **OpenRouter**.

*Ese selector es, literalmente, el tema de la Charla 20: aquí eliges tú el motor.*

## 8. Configuración (`opencode.json`) y precedencia

Fichero **JSON o JSONC** (admite comentarios y comas finales). Añade el `$schema` para validación y autocompletado:

```jsonc
{
  "$schema": "https://opencode.ai/config.json",
  "model": "anthropic/claude-sonnet-4-5",
  "autoupdate": true
}
```

Los ficheros se **fusionan**, no se reemplazan: las claves en conflicto las gana la fuente de mayor prioridad; el resto se conserva. **Orden de precedencia** (de menor a mayor; la última gana):

1. **Config remota** (`.well-known/opencode`) — valores por defecto de la organización, que se descargan al autenticarte.
2. **Global** (`~/.config/opencode/opencode.json`) — tus preferencias.
3. **Config personalizada** (variable `OPENCODE_CONFIG`).
4. **Proyecto** (`opencode.json` en el proyecto, o en `.opencode/`).
5. **Directorios `.opencode`** — agentes, comandos, plugins.
6. **Config en línea** (variable `OPENCODE_CONFIG_CONTENT`) — override en tiempo de ejecución.
7. **Ficheros gestionados** (directorios del sistema, controlados por admin).
8. **Preferencias gestionadas de macOS** (`.mobileconfig` por MDM) — máxima prioridad, no anulable por el usuario.

En monorepos, OpenCode busca desde el directorio actual hacia la raíz y fusiona de lo más lejano a lo más cercano (cada paquete afina lo suyo). Otras secciones útiles: `tui`, `server`, `tools` (activar/desactivar `bash`/`edit`/`write`/`read`), `provider`, `agent`, `mcp`, `plugin`. Interpolación `{env:VAR}` y `{file:./ruta}` en todo el config.

## 9. Agentes

Dos tipos: **primarios** (los que manejas tú: **Build** con todo, **Plan** restringido) y **subagentes** (General, Explore de solo lectura, Scout, o los tuyos). Se definen por **JSON** en `opencode.json` o por **Markdown** (un fichero por agente en `.opencode/agents/*.md`; el nombre del fichero es el nombre del agente).

```json
{
  "$schema": "https://opencode.ai/config.json",
  "agent": {
    "build": {
      "mode": "primary",
      "model": "anthropic/claude-sonnet-4-5",
      "prompt": "{file:./prompts/build.txt}",
      "permission": { "edit": "allow", "bash": "allow" }
    },
    "plan": {
      "mode": "primary",
      "model": "anthropic/claude-haiku-4",
      "permission": { "edit": "deny", "bash": "deny" }
    },
    "code-reviewer": {
      "description": "Revisa el código: seguridad, rendimiento y mantenibilidad",
      "mode": "subagent",
      "model": "anthropic/claude-sonnet-4-5",
      "prompt": "Eres un revisor de código. Céntrate en seguridad, rendimiento y mantenibilidad.",
      "permission": { "edit": "deny" }
    }
  }
}
```

Opciones: `description` (**obligatoria** en subagentes: le dice al orquestador cuándo usarlo), `model`, `prompt`, `permission`, `mode`, `temperature` (0 por defecto; 0.55 en Qwen), tope de **iteraciones** (acota coste) y `tools`. Con asistente: `opencode agent create`. **Multiagente:** un primario invoca subagentes con permisos — la idea del "Analista de RFP" de la [[guion-charla-19|Charla 19]], pero abierto y bajo tu control.

## 10. Permisos

Cada herramienta peligrosa (editar, `bash`, escribir…) se controla con `permission`: `allow`, `deny` o `ask` (pregunta antes de actuar), por agente. Es el mecanismo que evita el "agente suelto" — el equivalente al **checkpoint humano** de la Charla 19.

## 11. Skills

Habilidades reutilizables en `SKILL.md`, cargadas **bajo demanda**. Van en `.opencode/skills/` (o global) y son **compatibles con el estándar de Claude** (`.claude/skills/`) y `.agents/skills/`: OpenCode lee las mismas skills. Frontmatter con `name` y `description` (obligatorios); permisos por skill.

## 12. Reglas y `AGENTS.md`

`AGENTS.md` (el que crea `/init`) es el fichero de **reglas y contexto del proyecto**: estructura, convenciones, cómo se construye y se prueba. El agente lo lee siempre — es contexto persistente, no instrucciones de una sola vez.

## 13. References (contexto externo)

Acceso a **directorios o repos de fuera** del proyecto como contexto (docs, librerías compartidas, otro repo). Se declaran por alias en `opencode.json` (ruta local, o repo Git `owner/repo` + rama, que se clona a caché) y se invocan con `@alias`.

## 14. MCP (conectar herramientas externas)

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "context7": { "type": "local", "command": ["npx", "-y", "@upstash/context7-mcp"] }
  }
}
```

Locales (un comando) o remotos (una URL). La misma idea de MCP de la serie, aquí del lado del ejecutor.

## 15. Comandos personalizados

Convierten un **prompt con nombre en un comando reutilizable** (slash command). Son ficheros `.md` en `commands/`: `~/.config/opencode/commands/` (global) o `.opencode/commands/` (proyecto). Se pueden anidar: `.opencode/commands/team/review.md` define `/team/review`.

```markdown
---
description: Revisa el código en busca de fallos y tests que falten
agent: plan
model: anthropic/claude-sonnet-4-5#high
---

Revisa $ARGUMENTS. Primero los bugs, luego los tests que faltan.
```

El cuerpo es la plantilla; `$ARGUMENTS` es lo que le pasas al invocarlo. Las definiciones de proyecto ganan a las globales, y una posterior puede sobrescribir una anterior o una integrada.

## 16. Herramientas personalizadas

Funciones que **el LLM puede llamar** durante la conversación, junto a las integradas (`read`, `write`, `bash`). Se definen en TS/JS en `.opencode/tools/` (proyecto) o `~/.config/opencode/tools/` (global); **el nombre del fichero es el nombre de la herramienta**. La definición usa el helper `tool()` (tipado y validación) pero puede invocar por dentro un script en cualquier lenguaje.

```ts
// .opencode/tools/database.ts
import { tool } from "@opencode-ai/plugin"

export default tool({
  description: "Consulta la base de datos del proyecto",
  args: { query: tool.schema.string().describe("Consulta SQL a ejecutar") },
  async execute(args) {
    // tu lógica aquí
    return resultado
  },
})
```

## 17. Plugins

Módulos **JS/TS** que enganchan a eventos y personalizan el comportamiento: añadir herramientas, proveedores de autenticación, o interceptar acciones. Se cargan de dos formas: ficheros locales en `.opencode/plugins/` (o `~/.config/opencode/plugins/`), auto-cargados al arranque; o desde **npm** declarándolos en el config:

```json
{ "plugin": ["opencode-wakatime", "@mi-org/plugin-interno"] }
```

Un plugin recibe un contexto (`{ project, client, $, directory, worktree }`) y devuelve *hooks*. Algunos hooks útiles: `tool.execute.before` / `tool.execute.after` (interceptar herramientas — por ejemplo, sanear un comando `bash` antes de ejecutarlo), `permission.ask` (decidir permisos), `chat.message`, `chat.params` (ajustar temperatura, etc.), `event`, `config`, `auth`. Para dependencias, añade un `.opencode/package.json` y OpenCode ejecuta `bun install` al arrancar. Para logs, `client.app.log()` (niveles debug/info/warn/error).

```ts
// .opencode/plugins/sanea-bash.ts
import { escape } from "shescape"
export const SaneaBash = async (ctx) => ({
  "tool.execute.before": async (input, output) => {
    if (input.tool === "bash") output.args.command = escape(output.args.command)
  },
})
```

## 18. TUI: temas y keybinds

Los ajustes de la interfaz de terminal van en la clave `tui` de `opencode.json` o en un fichero dedicado `tui.json` (`$schema: https://opencode.ai/tui.json`), apuntable con `OPENCODE_TUI_CONFIG`:

```json
{
  "$schema": "https://opencode.ai/tui.json",
  "scroll_speed": 3,
  "scroll_acceleration": { "enabled": true },
  "diff_style": "auto"
}
```

- `diff_style`: `"auto"` (se adapta al ancho del terminal) o `"stacked"` (siempre una columna).
- **Tema**: se fija con `"theme"` (por ejemplo `"opencode"`); hay temas integrados y puedes definir el tuyo.
- **Keybinds**: las combinaciones de teclas son personalizables. Nota: las claves antiguas `theme`, `keybinds` y `tui` dentro de `opencode.json` están **deprecadas** y OpenCode las migra automáticamente al nuevo formato.

## 19. El servidor headless

```bash
opencode serve         # servidor headless (por defecto, puerto 4096)
opencode web           # interfaz web sobre ese servidor
```

Configurable en la sección `server`:

```json
{ "server": { "port": 4096, "hostname": "0.0.0.0", "mdns": true, "cors": ["http://localhost:5173"] } }
```

`cors` es importante si le vas a hablar desde un frontal web en otro puerto (p. ej. el 5173 de Vite). Para scripting rápido sin código:

```bash
opencode run --attach http://localhost:4096 "Resume la estructura del repo y sus puntos de entrada"
```

## 20. El SDK — el mando a distancia del motor

`@opencode-ai/sdk` es un **cliente tipado en JS/TS** para controlar el servidor desde tu código:

```ts
import { createOpencodeClient } from "@opencode-ai/sdk"

const client = createOpencodeClient({ baseUrl: "http://localhost:4096" })

const session = await client.session.create()
await client.session.prompt({
  sessionID: session.id,
  parts: [{ type: "text", text: "Añade validación al formulario de contacto" }],
})

for await (const event of client.event.subscribe()) {
  // event → mensajes, cambios de estado, tokens… para ir pintando la salida
}
```

(`createOpencode()` levanta el servidor **y** te da el cliente en una sola llamada.) La API cubre: **sesiones** (`create`, `prompt`, `command`, `shell`, `abort`, `share`, `messages`, `revert`), **agentes** (`app.agents()`), **proveedores/config**, **ficheros** (buscar/leer), control del **TUI**, **autenticación** (`auth.set`) y el **stream de eventos** (`event.subscribe()`, SSE). Soporta **salida estructurada** (JSON con esquema).

En cristiano: **el SDK es el mando a distancia**. Tú construyes lo que quieras alrededor; OpenCode ejecuta.

## 21. Montar un frontal propio

```
[ Frontal propio ]   Vite + React + Tailwind + Zustand
        |   (@opencode-ai/sdk, cliente tipado)
        v
[ Servidor OpenCode ]   opencode serve   (motor headless, puerto 4096)
        |
        v
[ Modelo ]   el que elijas: en la nube o local (Ollama / LM Studio)
```

Piezas mínimas: **crear/lanzar** (`session.create` + `session.prompt`), **agentes** (`app.agents()`), **salida en vivo** (`event.subscribe()`), **estado** (Zustand), **diseño** (Tailwind), **CORS** (añade tu origen, p. ej. `http://localhost:5173`, en `server.cors`), y **el motor por debajo** (OpenCode). Referencias del ecosistema para copiar ideas: **OpenChamber**, **CodeNomad**, **portal**, **OpenWork**.

## 22. Un flujo de trabajo de principio a fin

Para verlo entero, así sería añadir una funcionalidad a un proyecto:

1. **Instalar y conectar:** `curl -fsSL https://opencode.ai/install | bash`, luego `opencode auth login`.
2. **Situarse:** `cd mi-proyecto && opencode`, y `/init` para generar `AGENTS.md` (commitearlo).
3. **Elegir motor:** `/models` — el que mejor encaje (o uno local si los datos no pueden salir).
4. **Planificar (modo Plan):** *"Añade un endpoint para exportar pedidos a CSV, con tests"*. OpenCode propone un plan **sin tocar nada**. Lo lees y ajustas.
5. **Ejecutar (modo Build):** dejas que lo implemente. Revisas el **diff** que va generando; con `permission: ask` te pide visto bueno en lo irreversible.
6. **Cerrar:** revisas, ejecutas los tests, y commiteas. Si quieres enseñar cómo lo hizo, `/share` genera un enlace de la sesión.

Todo el rato, tú mantienes la última palabra — el arnés en acción.

## 23. Gobernanza en empresa

Las piezas que hacen a OpenCode encajar en soluciones internas:

- **Modelo/endpoint bajo control:** `baseURL` a un gateway o modelo interno → los datos no salen; funciona incluso **air-gapped**.
- **Config impuesta por la organización, en dos niveles:** la **config remota** (`.well-known/opencode`) fija valores por defecto que se descargan al autenticarse (por ejemplo, qué servidores MCP hay); y los **ajustes gestionados** (directorios del sistema / MDM en macOS) imponen configuración que el usuario **no puede** sobrescribir.
- **Permisos y checkpoint:** `permission: ask/deny` por agente para que nada irreversible pase sin visto bueno.
- **Auditable:** al ser MIT, el código se revisa; no es una caja negra.

Es la traducción práctica del mensaje de la charla: **el control se queda del lado de la empresa.**

## 24. Ecosistema

Al ser abierto, alrededor han crecido **plugins** (autenticación con suscripciones existentes, orquestación multiagente, memoria…) y **aplicaciones** construidas con el SDK. Agregadores: `awesome-opencode` y `opencode.cafe`.

---

# Parte 3 — Cierre

En la [[guion-charla-19|Charla 19]] montamos un equipo de agentes… dentro de una caja cerrada. Para probar, perfecto. Pero cuando esto va en serio —con tus permisos, tus datos y tus reglas— la forma de construir y ejecutar se mueve hacia herramientas donde el motor y los datos son tuyos. El siguiente paso práctico es ese frontal con OpenCode por debajo: dejar de hablar y montar algo de verdad.

> **Hoy no te llevas una herramienta. Te llevas el criterio para entender la que viene.**

## Enlaces

- Documentación oficial: https://opencode.ai/docs
- Repositorio: https://github.com/anomalyco/opencode
- Descargas: https://opencode.ai/download
- Configuración (esquema, fuente de verdad): https://opencode.ai/config.json
- Config · Agentes · Modelos · Skills: https://opencode.ai/docs/config/ · https://opencode.ai/docs/agents/ · https://opencode.ai/docs/models/ · https://opencode.ai/docs/skills/
- Comandos · Herramientas · Plugins: https://opencode.ai/docs/commands/ · https://opencode.ai/docs/custom-tools/ · https://opencode.ai/docs/plugins/
- SDK · Servidor: https://opencode.ai/docs/sdk/ · https://opencode.ai/docs/server/
- Ecosistema (apps construidas encima): https://opencode.ai/docs/ecosystem/
- Nota de recursos (resumen técnico): [[opencode]]

---

*Material de la serie IAs-talks. Charla 20.*
