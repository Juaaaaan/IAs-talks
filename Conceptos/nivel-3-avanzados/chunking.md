---
type: Concepto
title: "Chunking — Trocear documentos sin romper su sentido"
description: "División de documentos en fragmentos para indexarlos y recuperar solo lo relevante. Cómo se corta influye directamente en lo que el sistema puede encontrar y entender."
tags: [chunking, fragmentacion, rag, indexacion, retrieval]
related: [rag, embeddings, busqueda-semantica, base-de-datos-vectorial, reranking, context-window-management]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Chunking

> _"Si cortas la frase por la mitad, el buscador solo encontrará media respuesta."_

---

## Qué es

**Chunking** es dividir un documento en **fragmentos** (*chunks*) que se indexan por separado. En un sistema [[rag]], lo que se recupera suelen ser esos fragmentos, no el documento entero.

---

## Estrategias

| Estrategia | Cómo corta | A tener en cuenta |
|---|---|---|
| **Tamaño fijo** | Cada cierta cantidad de texto | Sencillo, puede romper ideas |
| **Con solapamiento** | Repite un margen entre fragmentos | Conserva continuidad, duplica contenido |
| **Por estructura** | Títulos, apartados, párrafos | Respeta el documento si está bien estructurado |
| **Por significado** | Agrupa texto del mismo tema | Más complejo y costoso de preparar |

---

## El dilema del tamaño

- **Muy pequeños:** precisos, pero sin contexto
- **Muy grandes:** con contexto, pero con ruido y más tokens

No hay un tamaño ideal universal: se **prueba con preguntas reales**.

---

## Ejemplo práctico

En un condicionado, separar una cobertura de sus **exclusiones** puede llevar a responder "está cubierto" sin ver la excepción. Conservar el título y la referencia del apartado en cada fragmento ayuda.

---

## Relación con otras piezas

- **[[context-window-management]]** — La nota general que menciona el chunking como estrategia
- **[[embeddings]]** — Cada fragmento suele tener su vector
- **[[base-de-datos-vectorial]]** — Donde se almacenan
- **[[busqueda-semantica]]** y **[[reranking]]** — Cómo se recuperan y ordenan
