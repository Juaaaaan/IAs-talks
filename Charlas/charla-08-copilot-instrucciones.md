# Charla 8 — Instruyendo a la IA: `.github/` y `.claude/`

**Fecha:** Por determinar **Asistentes:** ~60–90 (developers junior/senior, RRHH, directivos, comerciales) **Estado:** 🔜 En preparación

---

## Idea central

Si la Charla 7 mostró cómo conectar la IA con herramientas externas, esta charla muestra cómo darle a la IA el contexto de cómo trabaja el equipo — de forma persistente, sin tener que explicarlo cada vez.

> _"El onboarding que le harías a un desarrollador nuevo, escríbeselo a la IA en un fichero. Solo una vez."_

---

## Estructura

| Bloque | Contenido | Tiempo |
|--------|-----------|--------|
| Apertura | Puente desde Charla 7 + aclaración anticipada | 2 min |
| Bloque 1 | El problema: la IA sin contexto | 3 min |
| Bloque 2 | La solución: ficheros de instrucciones | 5 min |
| Bloque 3 | `.github/` para Copilot — estructura completa | 5 min |
| Demo Acto 1 | El antes: Copilot sin instrucciones | 5 min |
| Demo Acto 2 | Crear instrucciones en vivo | 5 min |
| Demo Acto 3 | El después: Copilot con instrucciones | 5 min |
| Demo Acto 4 | AGENTS.md, frontmatter e instructions/ | 5 min |
| Demo Acto 5 | Múltiples agentes: developer y reviewer | 8 min |
| Bonus | `.claude/` + hook Graphify + RCA-20 | opcional |
| Cierre | 3 ideas + dónde empezar | 3 min |

---

## Narrativa por bloques

### Apertura — Aclaración anticipada

Responde a la pregunta que llegó de la audiencia tras la Charla 7: **¿quién crea esos ficheros?**

> _"La respuesta es: los dos juntos. Vosotros tenéis el conocimiento. La IA lo organiza."_

Conecta con el prompt que quedó sin enviar la semana anterior: la RCA-20.

### Bloque 1 — El problema

Cada sesión con la IA empieza desde cero. No sabe las convenciones del equipo, no conoce el stack, no ha leído el código. Es como un desarrollador nuevo sin onboarding.

**Frase de anclaje:**
> _"El onboarding que le harías a un desarrollador nuevo, escríbeselo a la IA en un fichero. Solo una vez."_

### Bloque 2 — La solución

Tanto Copilot como Claude tienen ficheros de instrucciones persistentes. El concepto es idéntico, solo cambia el nombre y la ubicación.

Tabla comparativa de ecosistemas presentada en la charla:

| | GitHub Copilot | Claude Code |
|---|---|---|
| Instrucciones globales | `.github/copilot-instructions.md` | `CLAUDE.md` |
| Instrucciones por ruta | `.github/instructions/*.instructions.md` | `.claude/rules/*.md` |
| Agentes | `AGENTS.md` | `.claude/agents/*.md` |
| Hooks y permisos | `.github/hooks/` | `.claude/settings.json` |

### Bloque 3 — `.github/` para Copilot

Tres ficheros clave:
- `copilot-instructions.md` — instrucciones globales, se leen siempre
- `instructions/*.instructions.md` — instrucciones por ruta con frontmatter `applyTo:`
- `AGENTS.md` — instrucciones para el agente autónomo

**Frase de anclaje:**
> _"Tres ficheros de texto. Eso es todo lo que separa a Copilot de conocer vuestro proyecto de verdad."_

### Demo — Cinco actos

**Acto 1** — Copilot sin instrucciones genera código genérico.
**Acto 2** — Se crea `copilot-instructions.md` en vivo. Se explica el origen del fichero (generado con IA, revisado por humano).
**Acto 3** — Mismo prompt, resultado completamente distinto.
**Acto 4** — `AGENTS.md` para comportamiento autónomo. Explicación de **frontmatter** (`---`) y `applyTo:` para instrucciones por contexto.
**Acto 5** — Patrón de múltiples agentes: `developer.agent.md` implementa, `reviewer.agent.md` verifica. Equivalentes en `.claude/agents/`.

**Frase de anclaje del Acto 5:**
> _"Un agente construye. Otro verifica. Ninguno de los dos trabaja sin contexto. Eso es un equipo de IA."_

### Cierre

Tres ideas + GitHub Desktop como recurso para perfiles no técnicos.

Gancho para la Charla 9:
> _"Hoy le hemos dado a la IA el manual de cómo trabajamos. La semana que viene le damos el manual de por qué lo hacemos así."_

**Frase final:**
> _"La IA nunca se olvida de leerlo."_

---

## Recursos de la charla

- [[demo-copilot-instrucciones-charla-8]] — Flujo completo de la demo
- [[copilot-instructions]] — Concepto copilot-instructions.md
- [[frontmatter]] — Qué es el frontmatter
- [[agentes-multiples]] — Patrón developer/reviewer con agentes
- [[github-actions]] — Teaser para charla futura

### Ficheros de referencia (proyecto RCA)
- `Recursos/copilot-instructions-rca.md` — El `copilot-instructions.md` usado en la demo
- `Recursos/agents-md-rca.md` — El `AGENTS.md` del proyecto RCA
- `Recursos/testing-instructions-rca.md` — Instrucciones para tests
- `Recursos/components-instructions-rca.md` — Instrucciones para componentes
- `Recursos/developer-agent-github-rca.md` — Agente developer para Copilot
- `Recursos/reviewer-agent-github-rca.md` — Agente reviewer para Copilot
- `Recursos/developer-agent-claude-rca.md` — Agente developer para Claude
- `Recursos/reviewer-agent-claude-rca.md` — Agente reviewer para Claude
- `Recursos/task-rca-20.md` — Task de la RCA-20 usada en el bonus

---

## Próxima charla

[[charla-09-wiki-llm-obsidian]] — Wiki LLM con Obsidian y GitHub como repositorio de conocimiento documental.
