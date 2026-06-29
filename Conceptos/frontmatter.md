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

```markdown
---
applyTo: "src/app/**/*.component.ts"
---
```
Solo se carga cuando trabaja con componentes Angular.

---

## Propiedades disponibles en agentes de Copilot

En ficheros `.agent.md` dentro de `.github/agents/`:

```markdown
---
description: Implementa tareas siguiendo las convenciones del proyecto
tools: read_file, write_file, run_command, search_files
---
```

| Propiedad | Para qué sirve |
|---|---|
| `description` | Cuándo debe invocarse este agente |
| `tools` | Herramientas a las que tiene acceso |

---

## Propiedades disponibles en agentes de Claude Code

En ficheros `.md` dentro de `.claude/agents/`:

```markdown
---
name: developer
description: Implementa tareas del proyecto RCA
tools: Read, Write, Edit, Bash, Glob, Grep
---
```

---

## Equivalente en Claude Code

En `.claude/rules/*.md` se usa el frontmatter `paths:` en lugar de `applyTo:`:

```markdown
---
paths:
  - "**/*.spec.ts"
  - "**/*.test.ts"
---
```

El concepto es idéntico — instrucciones que se cargan solo cuando el contexto lo requiere.

---

## Relación con otras piezas

- **[[copilot-instructions]]** — El fichero principal que usa frontmatter en las instrucciones por ruta
- **[[agentes-multiples]]** — Los agentes usan frontmatter para definir herramientas y descripción

---

## Dónde aparece en la serie

| Charla | Rol |
|---|---|
| 8 | Concepto explicado en el Acto 4 de la demo |
