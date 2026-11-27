---
type: Concepto
title: "RAG agéntico y GraphRAG — Cuando buscar una vez no basta"
description: "Dos evoluciones del RAG: en el agéntico, un agente decide qué buscar, dónde y si necesita volver a hacerlo; GraphRAG aprovecha las relaciones entre entidades. Pueden combinarse."
tags: [rag-agentico, agentic-rag, graphrag, rag, agentes, retrieval]
related: [rag, knowledge-graphs, bucle-agentico, deep-research, reranking]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# RAG agéntico y GraphRAG

> _"Un RAG básico busca y responde. Uno agéntico se pregunta si lo encontrado es suficiente."_

---

## Qué son

- **RAG agéntico:** un agente **dirige la recuperación**: reformula la consulta, elige la fuente, evalúa lo obtenido y vuelve a buscar si hace falta
- **GraphRAG:** usa un **grafo** de entidades y relaciones para recuperar información conectada. La explicación detallada está en [[knowledge-graphs]]

Son ideas distintas: una trata de **quién decide cómo buscar** y la otra de **cómo está organizado** lo que se busca. Se pueden combinar.

---

## Comparativa

| | RAG básico | RAG agéntico | GraphRAG |
|---|---|---|---|
| **Recuperación** | Habitualmente un paso | Varios, según resultados | Apoyada en relaciones |
| **Útil para** | Preguntas directas | Preguntas por partes o con varias fuentes | Preguntas que conectan entidades |
| **Coste** | Menor | Más llamadas y latencia | Construir y mantener el grafo |

---

## Ejemplo práctico

*"¿Ha cambiado la cobertura de agua entre el condicionado del año pasado y el actual?"* Un RAG agéntico puede buscar **cada versión por separado**, comprobar que tiene las dos y después compararlas.

---

## Criterio

Empieza por lo simple. Añade autonomía o un grafo cuando las pruebas muestren que el RAG básico **no llega**.

---

## Relación con otras piezas

- **[[rag]]** — El punto de partida
- **[[knowledge-graphs]]** — GraphRAG en detalle
- **[[bucle-agentico]]** — El ciclo que permite volver a buscar
- **[[deep-research]]** — Investigación iterativa aplicada a un informe
- **[[reranking]]** — Mejorar la ordenación en cualquiera de los casos

---

## Referencias

- [GraphRAG — Microsoft Research](https://microsoft.github.io/graphrag/)
