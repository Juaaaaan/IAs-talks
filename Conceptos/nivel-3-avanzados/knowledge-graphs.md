---
type: Concepto
title: "Knowledge Graphs + LLMs — GraphRAG"
description: "Combinación de grafos de conocimiento con LLMs para mejorar la búsqueda y el razonamiento. El grafo aporta estructura y relaciones que el LLM solo no descubriría."
tags: [knowledge-graph, graphrag, grafo, relaciones, rag, semantica]
related: [rag, graphify, embeddings, wiki-llm, okf]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Knowledge Graphs + LLMs — GraphRAG

> _"RAG te encuentra el documento correcto. GraphRAG te encuentra el documento correcto Y todos los que están conectados a él."_

---

## Qué es

**Knowledge Graphs + LLMs** combina la capacidad de los grafos de conocimiento (relaciones entre entidades) con la generación de texto de los LLMs.

**GraphRAG** es la variante más práctica: en lugar de buscar documentos solo por similitud semántica (RAG clásico), también sigue las relaciones entre documentos para encontrar contexto conectado.

---

## RAG clásico vs GraphRAG

| RAG clásico | GraphRAG |
|---|---|
| Busca por similitud semántica | Busca por similitud + relaciones |
| Documentos aislados | Documentos conectados |
| "¿Qué documento habla de esto?" | "¿Qué documentos están relacionados con esto?" |
| Encuentra 1 documento | Encuentra el grafo completo de documentos relevantes |

---

## Ejemplo con este vault

**Pregunta:** "¿Cómo afecta la decisión de no usar NgRx al estado del sprint?"

**RAG clásico:** Encuentra `decision-no-ngrx.md` (por similitud)

**GraphRAG:** Encuentra `decision-no-ngrx.md` → sigue `related:` → encuentra `contexto-proyecto.md` → sigue relaciones → encuentra `estado-sprint-actual.md`. Responde con el contexto completo.

---

## El vault OKF como grafo

El campo `related:` del frontmatter OKF **es** un grafo de conocimiento:

```
arnes-completo
├── related: [sdd, skills, mcp]
│   ├── sdd.related: [arnes-completo, charla-07]
│   ├── skills.related: [arnes-completo, mcp]
│   └── mcp.related: [function-calling, arnes-completo]
└── ...
```

Un agente que navega estos `related:` está haciendo GraphRAG manualmente.

---

## Componentes

1. **Entidades:** Los conceptos, ficheros, decisiones (nodos del grafo)
2. **Relaciones:** Los `related:`, `[[wikilinks]]` (aristas del grafo)
3. **Propiedades:** Los campos del frontmatter (`type`, `tags`, `estado`)
4. **LLM:** Genera respuestas combinando la información del grafo

---

## Relación con otras piezas

- **[[rag]]** — GraphRAG extiende RAG con relaciones entre documentos
- **[[graphify]]** — Graphify mapea el grafo del código, GraphRAG el del conocimiento
- **[[embeddings]]** — Los embeddings se combinan con el grafo para búsqueda híbrida
- **[[wiki-llm]]** — El Wiki LLM con OKF es una implementación ligera de knowledge graph
- **[[okf]]** — El campo `related:` de OKF define las aristas del grafo

---

## Referencias

- [GraphRAG — Microsoft Research](https://microsoft.github.io/graphrag/)
- [Knowledge Graphs + LLMs survey](https://arxiv.org/abs/2306.08302)
