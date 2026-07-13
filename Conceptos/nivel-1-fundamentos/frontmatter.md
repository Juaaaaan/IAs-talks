---
type: Concepto
title: "Frontmatter"
description: "Bloque de metadatos YAML al inicio de ficheros Markdown que controla cuándo y cómo los carga la IA. Base del estándar OKF."
tags: [frontmatter, yaml, metadatos, copilot, claude, okf, instrucciones]
related: [copilot-instructions, agentes-multiples, okf]
charla: "Charla 8"
estado: "✅ Publicado"
timestamp: "2026-07-02"
---

# Frontmatter

> _"Son metadatos sobre el fichero en sí, no contenido. Le dicen a la IA cuándo tiene que leer este fichero y cuándo no."_

---

## Qué es

El frontmatter es un bloque de metadatos que aparece al inicio de un fichero Markdown, delimitado por tres guiones (`---`). No es contenido del fichero — es información sobre el fichero.

```markdown
---
applyTo: "**/*.spec.ts"
description: Convenciones de testing para el proyecto
---

# Testing conventions
...
```

---

## Por qué importa en IA

En el contexto de ficheros de instrucciones para Copilot y Claude, el frontmatter controla **cuándo** se carga cada instrucción. Esto permite tener instrucciones específicas para contextos concretos sin sobrecargar a la IA con información irrelevante.

---

## Propiedades disponibles en Copilot

| Propiedad | Para qué sirve |
|---|---|
| `applyTo` | Glob de ficheros que activan la instrucción automáticamente |
| `description` | Descripción del fichero para que Copilot entienda su propósito |
| `excludeAgent` | Excluir un agente específico de leer este fichero |

**Ejemplo con `applyTo:`**

```markdown
---
applyTo: "**/*.spec.ts"
---
```
Solo se carga cuando Copilot trabaja con ficheros `.spec.ts`.

---

## Propiedades en agentes

En ficheros `.agent.md` dentro de `.github/agents/`:

```markdown
---
description: Implementa tareas siguiendo las convenciones del proyecto
tools: read_file, write_file, run_command, search_files
---
```

---

## Relación con OKF

El frontmatter es también el mecanismo que implementa el estándar [[okf]] en este vault. El campo `type:` es el único obligatorio en OKF.

---

## Relación con otras piezas

- **[[copilot-instructions]]** — El fichero principal que usa frontmatter en las instrucciones por ruta
- **[[agentes-multiples]]** — Los agentes usan frontmatter para definir herramientas y descripción
- **[[okf]]** — OKF formaliza el frontmatter como estándar de conocimiento para agentes

---

## Dónde aparece en la serie

| Charla | Rol |
|---|---|
| 8 | Explicado en el Acto 1 de la demo |
| 11 | Base del estándar OKF para el Wiki LLM |
