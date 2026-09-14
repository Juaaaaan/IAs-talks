---
type: recurso
title: "OpenCode — dossier técnico (ejecutor abierto)"
description: "Nota de empape sobre OpenCode: qué es, por qué es abierto (MIT), sus capas (modelos, agentes, skills, references, SDK), el ecosistema y la arquitectura para montar un frontal propio con OpenCode de motor."
tags: [opencode, ejecutor, herramienta, open-source, sdk, agentes, recurso]
related:
  - "[[guion-charla-20]]"
  - "[[guion-charla-16]]"
  - "[[claude-code]]"
  - "[[el-arnes]]"
timestamp: 2026-09-14
fuente: "https://opencode.ai/docs"
---

# OpenCode — dossier técnico

> Nota para mi empape (Charla 20 + proyecto del frontal). Aquí sí entro en profundidad técnica; en la charla esto NO va (es para 98% no técnico). Fuente: docs oficiales opencode.ai, sep 2026.

## Qué es (y la duda resuelta)

Agente de código open source, de la empresa **Anomaly** (repo `anomalyco/opencode`). Hace el mismo trabajo que Claude Code / GitHub Copilot / Cursor: lee tu proyecto, razona y hace cambios, con modos plan/build, subagentes, permisos, MCP y skills.

**¿Es de verdad abierto? Sí, sin matices:**
- Licencia **MIT** (de las más permisivas): auditar, contribuir, hacer fork, ejecutar en tu infraestructura, sin vendor lock-in.
- Código entero público. ~200.000 estrellas, 900+ contribuidores, 27.000 forks. TypeScript.
- Arquitectura **cliente-servidor**. Interfaces: terminal (TUI), app de escritorio, extensión de IDE/VS Code y web.

La similitud con Claude Code es real y esperable (mismo trabajo). La diferencia no es la experiencia de uso, es la **propiedad**: abierto + agnóstico de proveedor + construible por encima. Ese es el eje de la charla.

> Matiz honesto por si preguntan: existe **OpenCode Zen** (servicio propio de modelos validados, de pago, con sus términos aparte). El *software* OpenCode sigue siendo MIT; Zen es opcional.

## Las capas / conceptos clave

### Modelos (`/models`)
- **75+ proveedores** vía AI SDK + Models.dev. Incluye **modelos locales** (Ollama, LM Studio). Este es el corazón del "elige tu motor".
- Selección con `/models`; por defecto en config `"model": "provider/model"` (p. ej. `anthropic/claude-sonnet-4-5`, `lmstudio/...`).
- Recomendados que van bien (no exhaustivo): GPT 5.2, GPT 5.1 Codex, Claude Opus 4.5, Claude Sonnet 4.5, Minimax M2.1, Gemini 3 Pro.
- Variants: presupuestos de "thinking" / esfuerzo de razonamiento por modelo.

### Agentes
- Dos tipos: **primary** (los que manejas tú: Build con todo habilitado, Plan restringido a solo análisis) y **subagents** (General, Explore de solo lectura, Scout para docs/dependencias), más agentes ocultos de sistema (compaction, title, summary).
- Se configuran por **JSON** (`opencode.json`) o por **Markdown** (`.opencode/agents/*.md` o global `~/.config/opencode/agents/`). El nombre del fichero = nombre del agente.
- Opciones por agente: `description` (obligatoria), `model`, `prompt`, `permission`, `mode`, `temperature`, `steps` (tope de iteraciones = control de coste), `color`, etc.
- **Multiagente**: un primary invoca subagents vía la herramienta Task, con permisos por patrón (`permission.task`). Esto conecta con la Charla 19 (orquestador + hijos), pero aquí abierto y bajo tu control.
- `opencode agent create` → asistente interactivo que genera el `.md`.

### Skills (habilidades del agente)
- `SKILL.md` reutilizables, cargados **bajo demanda** por la herramienta nativa `skill`.
- Ubicaciones: `.opencode/skills/`, global, y **compatibles con `.claude/skills/` y `.agents/skills/`** → OpenCode lee el mismo estándar de skills que Claude. Interoperabilidad real.
- Frontmatter: `name`, `description` (obligatorios), `license`, `compatibility`, `metadata`. Permisos por skill (allow/deny/ask, con comodines).

### References
- Dan al agente acceso a **directorios o repos externos** como contexto (docs, librerías compartidas, otro repo), por alias en `opencode.json`.
- Local (`path`) o Git (`repository: "owner/repo"` + `branch`; se clona a caché local). Se usan con `@alias` en el TUI.

### SDK (`@opencode-ai/sdk`)
- Cliente **JS/TS con tipos** para hablar con el servidor. `createOpencode()` (levanta server + client) o `createOpencodeClient({ baseUrl })` (conecta a uno ya en marcha).
- API cubre: **sesiones** (create/list/prompt/command/shell/abort/share/messages/revert), `app.agents()` (listar agentes), `config.providers()`, búsqueda/lectura de ficheros, control del TUI, `auth.set`, y **`event.subscribe()` = stream de eventos en tiempo real (SSE)**.
- Soporta **salida estructurada** (json_schema).

### Servidor / red / empresa
- `opencode serve` = servidor headless con API (OpenAPI). Es la pieza sobre la que se construye todo.
- Hay páginas de **Enterprise**, **Network** y **Policies** (gobernanza corporativa) que aún no he leído a fondo — pendiente si quiero el ángulo de despliegue en empresa.

## Arquitectura para el frontal (el proyecto de "la semana que viene")

La idea que tuve encaja exactamente con cómo está pensado OpenCode:

```
[ Frontal propio ]  Vite + React + Tailwind + Zustand
        │  (SDK @opencode-ai/sdk, cliente tipado)
        ▼
[ Servidor OpenCode ]  opencode serve  (motor headless, API OpenAPI)
        │
        ▼
[ Modelo ]  el que elijas: cloud o local (Ollama/LM Studio)
```

Piezas mínimas del frontal:
- **Crear/lanzar**: `session.create` + `session.prompt` para mandar tareas.
- **Agentes**: `app.agents()` para listar; agentes definidos por config/markdown para crearlos.
- **Salida en vivo**: `event.subscribe()` → pintar el streaming en la UI.
- **Estado**: Zustand (sesiones, agente activo, stream). **Tailwind** para la cara bonita.
- **Motor por debajo**: OpenCode. La app es la cara; el ejecutor es OpenCode. Ahí está la gracia — y por qué con Claude Code/Copilot esto no se puede.

**Referencias del ecosistema para copiar ideas** (frontales ya hechos con el SDK):
- OpenChamber — app web/escritorio + extensión VS Code.
- CodeNomad — escritorio, web, móvil y cliente remoto.
- portal — UI web móvil vía Tailscale/VPN.
- octto — UI de navegador para brainstorming con formularios.
- OpenWork — alternativa open source a Claude Cowork, sobre OpenCode.
- kimaki — bot de Discord que controla sesiones, sobre el SDK.
- Agregadores: `awesome-opencode`, `opencode.cafe`.

## Enlaces
- Docs: https://opencode.ai/docs
- Repo: https://github.com/anomalyco/opencode
- SDK: https://opencode.ai/docs/sdk/ · Server: https://opencode.ai/docs/server/
- Agentes: https://opencode.ai/docs/agents/ · Skills: https://opencode.ai/docs/skills/
- Modelos: https://opencode.ai/docs/models/ · References: https://opencode.ai/docs/references/
- Ecosistema: https://opencode.ai/docs/ecosystem/
