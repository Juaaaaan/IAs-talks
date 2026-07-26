---
type: Concepto
title: "Embeddings"
description: "Representación matemática del significado de un texto, usada para buscar de forma semántica qué fragmentos de un documento son relevantes ante una pregunta"
tags: [embeddings, rag, busqueda-semantica, vectores]
related: [rag, copilot-studio]
charla: "Charla 13"
estado: "✅ Publicado"
timestamp: "2026-07-22"
---

# Embeddings

---

## Qué es

Un embedding es una representación matemática (un vector de números) del significado de un texto. Dos fragmentos de texto con significados parecidos generan embeddings numéricamente cercanos entre sí, aunque usen palabras distintas.

Esto es lo que permite que un sistema de [[rag|RAG]] encuentre el fragmento relevante de un documento aunque la pregunta del usuario no use exactamente las mismas palabras que el texto original.

---

## Por qué no es una simple búsqueda de palabras clave

Una búsqueda tradicional por palabras clave falla si la pregunta usa sinónimos o una redacción distinta a la del documento. Los embeddings comparan **significado**, no texto literal — por eso la pregunta "¿cuántos empleados hay?" puede encontrar un párrafo del handbook que dice "la plantilla actual asciende a...", sin que compartan ni una palabra.

---

## Cómo se usan en la práctica (ejemplo Copilot Studio)

1. [[copilot-studio|Copilot Studio]] lee el documento conectado (p. ej. vía SharePoint)
2. Extrae el significado semántico de cada párrafo y lo convierte en embeddings
3. Los almacena de forma que puedan consultarse eficientemente
4. Cuando alguien pregunta algo, la pregunta se convierte también en embedding y se compara contra los almacenados para encontrar los fragmentos más relevantes

Todo esto ocurre de forma automática y transparente para quien construye el agente — no requiere configuración manual.

---

## Relación con otras piezas

- **[[rag]]** — Los embeddings son el mecanismo que hace posible la fase de "retrieval" en RAG
- **[[copilot-studio]]** — Genera y gestiona embeddings automáticamente al conectar documentos de conocimiento

---

## Dónde aparece en la serie

| Charla | Rol del concepto |
| ------ | --------------- |
| 12 | Introducción teórica junto con RAG en el mapa de madurez |
| 13 | Explicación de por qué Copilot Studio encuentra el dato correcto en el handbook al conectar un documento |
