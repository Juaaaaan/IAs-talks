---
type: Concepto
title: "copilot-instructions.md — Instrucciones persistentes para Copilot"
description: "Fichero en .github/ que da contexto persistente a GitHub Copilot: stack, convenciones, sistema de diseño. El manual de bienvenida de la IA."
tags: [copilot, instrucciones, github, contexto, arnes, onboarding]
related: [agentes-multiples, frontmatter, arnes-completo, sdd, skills, system-prompt]
charla: "Charla 8"
nivel: 2
estado: "✅ Publicado"
timestamp: "2026-07-02"
---

# copilot-instructions.md — Instrucciones persistentes para Copilot

> _"El onboarding que le harías a un desarrollador nuevo, escríbselo a la IA en un fichero. Solo una vez."_

---

## Qué es

El fichero `.github/copilot-instructions.md` es el mecanismo principal para dar contexto persistente a GitHub Copilot. Lo lee automáticamente en cada sesión, en cualquier IDE compatible (VS Code, JetBrains, Visual Studio).

No es un prompt que escribes cada vez. Es el manual de bienvenida de tu proyecto para la IA.

---

## Qué contiene

Un buen `copilot-instructions.md` recoge:

- **Stack tecnológico** — qué framework, versión, librerías principales
- **Convenciones de código** — patrones, estilos, reglas que el equipo sigue
- **Estructura del proyecto** — dónde vive cada cosa
- **Comandos habituales** — build, test, lint, serve
- **Reglas de negocio** — restricciones importantes que la IA debe respetar

---

## Cómo se crea

No se escribe desde cero. El flujo correcto es:

1. Recopilar el contexto que ya existe — decisiones técnicas, convenciones del equipo, documentación
2. Dárselo a la IA como contexto
3. Pedirle que genere el fichero de instrucciones
4. Revisar, ajustar y commitear al repositorio

> _"La IA no inventa el conocimiento. Lo organiza. Tú sigues siendo el que sabe."_

---

## La diferencia con el prompt

| Sin instrucciones | Con instrucciones |
|---|---|
| Cada sesión empieza desde cero | Cada sesión arranca con el contexto cargado |
| Copilot usa convenciones genéricas | Copilot usa las convenciones del equipo |
| Resultados inconsistentes | Resultados consistentes |

---

## Instrucciones por ruta — `instructions/`

```markdown
---
applyTo: "**/*.spec.ts"
---
```

El [[frontmatter]] `applyTo:` define el glob de ficheros que activan la instrucción. Ver [[frontmatter]] para más detalle.

---

## Equivalente en Claude Code

| GitHub Copilot | Claude Code |
|---|---|
| `.github/copilot-instructions.md` | `CLAUDE.md` en la raíz del proyecto |
| `.github/instructions/*.instructions.md` | `.claude/rules/*.md` |

---

## Relación con otras piezas

- **[[system-prompt]]** — copilot-instructions es una implementación práctica del system prompt
- **[[agentes-multiples]]** — Los agentes tienen su propio mecanismo (`AGENTS.md` y `.github/agents/`)
- **[[frontmatter]]** — El sistema de metadatos que controla cuándo se cargan las instrucciones
- **[[sdd]]** — Las instrucciones del proyecto complementan los documentos SDD
- **[[arnes-completo]]** — La cuarta pieza del arnés

---

## Dónde aparece en la serie

| Charla | Rol |
|---|---|
| 8 | Concepto central — introducción y demo |
