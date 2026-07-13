---
type: Concepto
title: "Embeddings — Representación semántica del texto"
description: "Vectores numéricos que capturan el significado del texto. Permiten buscar por similaridad semántica en lugar de por palabras exactas. Base técnica de RAG y búsqueda inteligente."
tags: [embeddings, vectores, semantica, busqueda, rag, similitud]
related: [rag, wiki-llm, context-engineering]
estado: "✅ Publicado"
timestamp: "2026-07-09"
---

# Embeddings — Representación semántica del texto

> _"Permiten buscar por significado, no solo por palabras exactas."_

---

## Qué es

Un **embedding** es una representación numérica (un vector) del significado de un texto. Convierte palabras, frases o documentos enteros en listas de números que capturan su semántica.

Dos textos con significado similar tendrán embeddings cercanos en el espacio vectorial, aunque usen palabras completamente diferentes.

---

## Por qué importa

| Búsqueda tradicional | Búsqueda con embeddings |
|---|---|
| Busca palabras exactas | Busca significado |
| "autenticación" no encuentra "login" | "autenticación" SÍ encuentra "login" |
| Requiere que uses los mismos términos | Entiende sinónimos y conceptos relacionados |
| Keyword matching | Semantic matching |

---

## Cómo funciona (simplificado)

```
Texto: "El usuario no puede iniciar sesión"
          ↓ Modelo de embeddings
Vector: [0.23, -0.45, 0.12, ..., 0.67]  (1536 dimensiones)

Texto: "Login fails for the customer"
          ↓ Modelo de embeddings  
Vector: [0.21, -0.43, 0.14, ..., 0.65]  (muy cercano al anterior)
```

La **distancia** entre vectores indica similitud semántica.

---

## Uso en RAG

Los embeddings son el mecanismo que hace posible RAG:

1. **Indexación:** Cada documento del vault se convierte en embeddings
2. **Búsqueda:** La pregunta del usuario se convierte en embedding
3. **Matching:** Se encuentran los documentos más cercanos semánticamente
4. **Inyección:** Esos documentos se pasan al LLM como contexto

---

## Ejemplo práctico

Un developer pregunta: _"¿Hay alguna restricción con el estado global?"_

El sistema de embeddings busca en el vault y encuentra `decision-no-ngrx.md` porque su contenido es semánticamente cercano a "estado global", aunque el fichero no contenga exactamente esas palabras.

---

## Modelos de embeddings comunes

| Modelo | Proveedor | Dimensiones |
|---|---|---|
| text-embedding-3-small | OpenAI | 1536 |
| text-embedding-3-large | OpenAI | 3072 |
| Gecko | Google | 768 |
| Voyage | Anthropic | 1024 |

---

## Relación con otras piezas

- **[[rag]]** — Los embeddings son el motor de búsqueda de RAG
- **[[wiki-llm]]** — Un Wiki LLM se puede indexar con embeddings para búsqueda semántica
- **[[context-engineering]]** — Los embeddings permiten inyectar el contexto correcto automáticamente

---

## Referencias

- Concepto en glosario: [[glosario-ia-nivel-1]] §14
