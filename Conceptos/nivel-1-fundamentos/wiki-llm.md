---
type: Concepto
title: "Wiki LLM — Base de conocimiento para agentes"
description: "Patrón de Andrej Karpathy: una wiki en markdown que los LLMs pueden leer, actualizar y mantener. La memoria persistente que convierte ficheros sueltos en un grafo de conocimiento navegable."
tags: [wiki-llm, karpathy, conocimiento, obsidian, markdown, agentes, memoria]
related: [okf, frontmatter, graphify, arnes-completo]
charla: "Charla 11"
estado: "✅ Publicado"
timestamp: "2026-07-08"
---

# Wiki LLM — Base de conocimiento para agentes

> _"Los LLMs no se aburren de mantener una wiki. No se olvidan de actualizar una referencia cruzada. Pueden tocar quince ficheros en un solo paso."_ — Andrej Karpathy

---

## Qué es

Un **Wiki LLM** es una base de conocimiento en ficheros markdown diseñada para que los agentes de IA la lean, actualicen y mantengan de forma autónoma.

No es una wiki tradicional pensada solo para humanos. Es un **artefacto vivo** donde:
- Los humanos aportan el conocimiento (decisiones, contexto, experiencia)
- La IA lo estructura, lo conecta y lo mantiene actualizado

---

## Origen

El concepto fue articulado por **Andrej Karpathy** (cofundador de OpenAI) en su [LLM Wiki gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

Su observación clave: el trabajo de mantenimiento que hace que los humanos abandonen sus wikis personales (actualizar referencias, mantener consistencia, reorganizar) es exactamente lo que los LLMs hacen bien.

---

## Por qué funciona

| Problema humano | Solución LLM |
|---|---|
| Olvidamos actualizar referencias cruzadas | El LLM las actualiza en cada paso |
| Abandonamos wikis por el esfuerzo de mantenimiento | El LLM no se aburre ni se cansa |
| El conocimiento queda en las cabezas | El LLM lo extrae y lo estructura |
| Cada fichero es una isla | El LLM conecta todo en un grafo |

---

## Componentes de un Wiki LLM

1. **Ficheros markdown** — legibles por humanos y máquinas
2. **Frontmatter YAML** — metadatos estructurados ([[frontmatter]])
3. **Estándar OKF** — convenciones de interoperabilidad ([[okf]])
4. **Enlaces internos** — grafo de conocimiento navegable
5. **Repositorio git** — versionado, colaborativo, auditable

---

## Diferencia con una wiki normal

| Wiki tradicional | Wiki LLM |
|---|---|
| Solo la leen humanos | La leen humanos y agentes |
| Se abandona cuando crece | La IA la mantiene viva |
| Estructura libre | Estructura formalizada (OKF) |
| Conocimiento estático | Conocimiento que se actualiza solo |
| Buscar = leer todo | Navegar = seguir el grafo |

---

## Relación con otras piezas

- **[[okf]]** — OKF es la formalización del patrón Wiki LLM en un estándar portable
- **[[frontmatter]]** — El mecanismo técnico que hace los ficheros navegables por agentes
- **[[graphify]]** — Complementario: Graphify mapea código, Wiki LLM mapea conocimiento
- **[[arnes-completo]]** — El Wiki LLM es donde vive el contexto que alimenta al arnés

---

## Dónde aparece en la serie

| Charla | Rol |
|---|---|
| 11 | Concepto central — se presenta el patrón y se demuestra con este vault |

---

## Referencias

- [LLM Wiki — Andrej Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- [Open Knowledge Format — Google Cloud](https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing)
