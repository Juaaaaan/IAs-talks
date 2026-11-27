---
type: Concepto
title: "Reranking — Segunda vuelta para ordenar resultados"
description: "Paso que reordena los resultados de una primera búsqueda con un criterio de relevancia más preciso, para pasar al modelo solo los mejores."
tags: [reranking, reordenacion, retrieval, rag, relevancia]
related: [rag, busqueda-semantica, chunking, base-de-datos-vectorial, eval-benchmarking]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Reranking

> _"Primero una criba amplia. Después, una lectura atenta de los finalistas."_

---

## Qué es

El **reranking** es una **segunda ordenación**. Una búsqueda rápida recupera un conjunto amplio de candidatos y después un método más preciso (a menudo un modelo especializado) los reordena según su relevancia para la pregunta.

---

## Las dos fases

| Fase | Objetivo | Característica |
|---|---|---|
| **1. Recuperar** | Que no se escape lo importante | Rápida, sobre mucho contenido |
| **2. Reordenar** | Poner lo mejor arriba | Más precisa y costosa, sobre pocos candidatos |

---

## Ejemplo práctico

Es como una selección: primero se filtran muchas candidaturas con criterios generales y después se estudian con detalle las finalistas.

---

## Cuándo plantearlo

- La respuesta correcta **aparece** entre los resultados, pero **no arriba**
- Hay muchos fragmentos parecidos
- Se quiere pasar **menos contexto** y de más calidad

## Cuándo no ayuda

Si el fragmento correcto **no se recuperó** en la primera fase, el reranking no puede inventarlo: hay que revisar [[chunking]], la búsqueda o los documentos.

---

## Relación con otras piezas

- **[[busqueda-semantica]]** — Una forma de hacer la primera recuperación
- **[[base-de-datos-vectorial]]** — Origen habitual de los candidatos
- **[[rag]]** — El patrón que se beneficia
- **[[eval-benchmarking]]** — Medir si el paso extra compensa su coste y latencia
