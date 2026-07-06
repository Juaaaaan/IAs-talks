---
type: Charla
title: "Charla 8 — Instruyendo a la IA: .github/ y .claude/"
description: "Instrucciones persistentes para Copilot y Claude Code. Demo de agentes developer/reviewer con anécdota real de Superpowers interceptando prompts."
tags: [charla, copilot, instrucciones, agentes, github, claude, developer, reviewer, superpowers]
related: [copilot-instructions, agentes-multiples, frontmatter, arnes-completo, demo-copilot-instrucciones-charla-8]
charla: "Charla 8"
fecha: "2026-07-02"
estado: "✅ Impartida"
timestamp: "2026-07-02"
---

# Charla 8 — Instruyendo a la IA: `.github/` y `.claude/`

**Fecha:** Por determinar **Asistentes:** ~60–90 (developers junior/senior, RRHH, directivos, comerciales) **Estado:** ✅ Impartida

---

## Idea central

> _"El onboarding que le harías a un desarrollador nuevo, escríbselo a la IA en un fichero. Solo una vez."_

---

## Estructura

| Bloque | Contenido | Tiempo |
|--------|-----------|--------|
| Apertura | Puente desde Charla 7 + aclaración anticipada | 2 min |
| Bloque 1 | El problema: la IA sin contexto | 3 min |
| Bloque 2 | La solución: ficheros de instrucciones | 5 min |
| Bloque 3 | `.github/` para Copilot — estructura completa | 5 min |
| Demo Acto 1 | Tour por el `.github/` completo | 8 min |
| Demo Acto 2 | Prompts en vivo: modificaciones reales | 7 min |
| Demo Acto 3 | AGENTS.md en acción: developer y reviewer | 10 min |
| Demo Acto 4 | ¿Cómo confiar en el resultado? | 5 min |
| Bonus | `.claude/` + hook Graphify | opcional |
| Cierre | 3 ideas + dónde empezar | 3 min |

---

## Narrativa por bloques

### Apertura — Aclaración anticipada

Responde a la pregunta que llegó de la audiencia tras la Charla 7: **¿quién crea esos ficheros?**

> _"La respuesta es: los dos juntos. Vosotros tenéis el conocimiento. La IA lo organiza."_

### Bloque 1 — El problema

Cada sesión con la IA empieza desde cero. No sabe las convenciones del equipo, no conoce el stack. Es como un desarrollador nuevo sin onboarding.

### Bloque 2 — La solución

Tabla comparativa de ecosistemas:

| | GitHub Copilot | Claude Code |
|---|---|---|
| Instrucciones globales | `.github/copilot-instructions.md` | `CLAUDE.md` |
| Instrucciones por ruta | `.github/instructions/*.instructions.md` | `.claude/rules/*.md` |
| Agentes | `AGENTS.md` | `.claude/agents/*.md` |

### Demo — Cuatro actos

**Acto 1** — Tour por el `.github/` completo. Anécdota de Superpowers: extensión de terceros que interceptaba prompts y generaba su propia estructura de carpetas.

**Acto 2** — Prompts pequeños en vivo (cambiar texto, añadir botón). Respeta tokens de diseño Artisanal Ether y convenciones Angular.

**Acto 3** — `@developer` implementa, `@reviewer` revisa. **El reviewer encontró un fallo real de tests en vivo.** Momento de mayor impacto.

**Acto 4** — Cómo medir la confianza: tests, lint, build, reviewer, PR humana.

### Cierre

Gancho para Charla 11:
> _"Hoy le hemos dado a la IA el manual de cómo trabajamos. La semana que viene le damos el manual de por qué lo hacemos así."_

**Frase final:**
> _"La IA nunca se olvida de leerlo."_

---

## Lecciones aprendidas

- Desactivar extensiones de terceros antes de la demo — Superpowers interceptaba prompts
- Para demos en vivo, prompts pequeños son más seguros que crear componentes completos
- El reviewer pillando un fallo real es el momento de mayor impacto de la charla
- El Copilot CLI puede ser lento con tareas complejas

---

## Próxima charla

[[charla-11-wiki-llm-obsidian]] — Wiki LLM con Obsidian, GitHub y el estándar OKF.
