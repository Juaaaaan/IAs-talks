---
type: Concepto
title: "OKF — Open Knowledge Format"
description: "Estándar abierto de Google basado en el concepto Wiki LLM de Karpathy. Ficheros markdown con frontmatter YAML estructurado para que los agentes de IA naveguen el conocimiento de forma semántica."
tags: [okf, wiki-llm, karpathy, google, frontmatter, markdown, conocimiento, agentes]
related: [frontmatter, graphify, wiki-llm]
charla: "Charla 11"
estado: "📋 Planificado"
timestamp: "2026-07-06"
---

# OKF — Open Knowledge Format

> _"El conocimiento que no está estructurado no es conocimiento para la IA — es ruido."_

---

## Origen: de Karpathy a Google

El concepto nace de **Andrej Karpathy** (cofundador de OpenAI) con su idea de **Wiki LLM**: en lugar de darle a la IA los mismos documentos una y otra vez, construir una wiki en markdown que crece con el tiempo y que la IA puede leer, actualizar y mantener.

Karpathy observó que los LLMs no se aburren, no se olvidan de actualizar referencias cruzadas, y pueden tocar 15 ficheros en un solo paso. El trabajo de mantenimiento que hace que los humanos abandonen sus wikis personales es exactamente lo que los LLMs hacen bien.

**Google formalizó este patrón** en junio de 2026 con el **Open Knowledge Format (OKF)**: un estándar portátil, interoperable, legible por humanos y por agentes, basado en ficheros markdown con frontmatter YAML.

---

## Qué es OKF

OKF no es una extensión de fichero. Los ficheros siguen siendo `.md`. Es un **estándar de metadatos** que estructura el conocimiento para que sea navegable por agentes de IA.

La especificación es mínima:
- **Un campo obligatorio:** `type` — define de qué tipo es el fichero
- **Todo lo demás es opcional:** `title`, `description`, `tags`, `related`, `timestamp`, etc.

OKF define la superficie de interoperabilidad, no el modelo de contenido. Tú decides qué tipos usas y qué campos añades.

### Ejemplo de fichero OKF

```markdown
---
type: Concepto
title: "MCP — Model Context Protocol"
description: "Protocolo estándar que conecta la IA con herramientas externas"
tags: [ia, integracion, protocolo]
related: [arnes-completo, sdd, skills]
timestamp: "2026-06-17"
---

# Qué es

...
```

---

## Por qué importa para un Wiki LLM

Sin OKF, un vault de Obsidian es una colección de ficheros. Con OKF, es un **grafo de conocimiento navegable**:

| Sin OKF | Con OKF |
|---|---|
| La IA lee ficheros sueltos | La IA navega el grafo semánticamente |
| No hay relaciones explícitas | `related:` define las conexiones |
| Cada fichero es opaco | `type:` y `description:` orientan al agente |
| El vault es estático | El agente puede mantenerlo activo |

---

## Los tipos usados en este vault

| Tipo | Carpeta | Descripción |
|---|---|---|
| `Concepto` | `Conceptos/` | Explicación de un concepto técnico concreto |
| `Charla` | `Charlas/` | Resumen narrativo de una charla impartida |
| `Demo` | `Demos/` | Paso a paso de una demo realizada en vivo |
| `Recurso` | `Recursos/` | Fichero de referencia, configuración o ejemplo |
| `Guion` | Raíz | Guión completo de una charla (para el ponente) |
| `Indice` | Raíz | Fichero de navegación del vault |

---

## OKF en la práctica: este vault

Todos los ficheros de `Juaaaaan/IAs-talks` siguen el estándar OKF desde julio de 2026. El campo `related:` conecta los conceptos entre sí, formando un grafo que cualquier agente puede navegar sin necesidad de leer todos los ficheros.

Ejemplo de cadena de navegación:
- `charla-07` → enlaza a `mcp`, `skills`, `sdd`, `arnes-completo`
- `arnes-completo` → enlaza a `sdd`, `skills`, `mcp`, `copilot-instructions`
- `copilot-instructions` → enlaza a `agentes-multiples`, `frontmatter`
- `frontmatter` → enlaza a `okf`

---

## Relación con otras piezas

- **[[frontmatter]]** — El frontmatter YAML es el mecanismo técnico que implementa OKF
- **[[graphify]]** — Graphify y OKF son complementarios: Graphify mapea la estructura del código, OKF estructura el conocimiento documental
- **[[wiki-llm]]** — OKF es la formalización del concepto Wiki LLM de Karpathy

---

## Referencias

- Google Cloud Blog: [How the Open Knowledge Format can improve data sharing](https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing)
- Concepto original Wiki LLM: Andrej Karpathy

---

## Dónde aparece en la serie

| Charla | Rol |
|---|---|
| 11 | Concepto central — Wiki LLM y OKF como estándar del vault |
