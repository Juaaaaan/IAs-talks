---
type: Concepto
title: "Base de datos vectorial — El almacén de los embeddings"
description: "Sistema preparado para guardar vectores y encontrar los más parecidos a uno dado. Es una pieza frecuente en la búsqueda semántica y el RAG, aunque no siempre imprescindible."
tags: [base-de-datos-vectorial, vector-database, embeddings, rag, infraestructura]
related: [embeddings, busqueda-semantica, chunking, rag, reranking]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Base de datos vectorial

> _"En lugar de preguntar '¿cuál es igual?', pregunta '¿cuáles se parecen más?'."_

---

## Qué es

Una **base de datos vectorial** guarda [[embeddings]] (listas de números) y permite recuperar **los más cercanos** a una consulta. Puede ser un producto dedicado o una capacidad añadida a una base de datos que ya usas.

---

## Cómo encaja

```
Documentos → fragmentos → embeddings → se guardan con sus metadatos
Pregunta   → embedding  → se buscan los más cercanos → fragmentos
```

---

## Qué guardar además del vector

| Dato | Para qué |
|---|---|
| **Texto o referencia** | Poder mostrar la fuente |
| **Fecha y versión** | No responder con documentos obsoletos |
| **Permisos** | Filtrar según quién pregunta |
| **Tipo o área** | Acotar la búsqueda |

---

## Puntos de atención

- Para ir rápido a gran escala suelen usarse búsquedas **aproximadas**, que pueden dejar fuera algún resultado
- Si cambias de modelo de embeddings, normalmente hay que **volver a generar** los vectores
- Si se borra o cambia un documento, el **índice** también debe actualizarse
- Con pocos documentos puede haber soluciones más simples

---

## Relación con otras piezas

- **[[embeddings]]** — Lo que se almacena
- **[[chunking]]** — Cómo se preparan los fragmentos
- **[[busqueda-semantica]]** — El uso principal
- **[[reranking]]** — Refinar los resultados
- **[[rag]]** — El patrón que suele consumirlos
