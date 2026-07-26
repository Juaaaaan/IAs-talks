---
type: Concepto
title: "RAG (Retrieval-Augmented Generation)"
description: "Técnica por la que un modelo de IA busca primero en una base de documentos específica antes de responder, en lugar de depender solo de su conocimiento general"
tags: [rag, embeddings, conocimiento, copilot-studio, busqueda-semantica]
related: [embeddings, copilot-studio, agente-ia]
charla: "Charla 13"
estado: "✅ Publicado"
timestamp: "2026-07-22"
---

# RAG — Retrieval-Augmented Generation

---

## Qué es

RAG es la técnica por la que un modelo de IA, antes de responder, busca en una base de documentos específica en lugar de apoyarse únicamente en su conocimiento general entrenado. El modelo "recupera" (retrieval) los fragmentos relevantes y luego "genera" (generation) la respuesta a partir de ellos.

Es lo que ocurre por debajo cuando un [[agente-ia|agente]] de [[copilot-studio|Copilot Studio]] responde citando el handbook corporativo en lugar de inventar o quedarse callado.

---

## Por qué hace falta

Un LLM genérico responde con lo que aprendió durante su entrenamiento — conocimiento general del mundo, no de vuestra empresa. Preguntas como "¿cuál es la política de teletrabajo aquí?" no tienen respuesta en ese conocimiento general porque nunca estuvo en ningún documento público.

RAG resuelve esto conectando el modelo a una fuente de conocimiento concreta y actualizable: el handbook, la wiki interna, la documentación del proyecto. El modelo no necesita "reentrenarse" para saber algo nuevo — basta con añadir el documento a la base que consulta.

---

## Cómo funciona, en fases

1. El documento se descompone en fragmentos (párrafos o secciones)
2. Cada fragmento se convierte en **[[embeddings]]** — una representación matemática de su significado
3. Cuando llega una pregunta, esa pregunta también se convierte en embedding y se compara con los fragmentos almacenados
4. Se recuperan los fragmentos más relevantes semánticamente (no por coincidencia exacta de palabras)
5. El modelo genera la respuesta usando esos fragmentos como contexto

---

## Relación con otras piezas

- **[[embeddings]]** — El mecanismo matemático que hace posible la búsqueda semántica dentro de RAG
- **[[copilot-studio]]** — Aplica RAG automáticamente al conectar documentos vía SharePoint
- **[[agente-ia]]** — Un agente con RAG bien configurado es lo que le permite decir "no lo sé" en vez de inventar, cuando el documento relevante no está conectado

---

## Dónde aparece en la serie

| Charla | Rol del concepto |
| ------ | --------------- |
| 12 | Introducción teórica de RAG y embeddings en el mapa de madurez de IA |
| 13 | Aplicación práctica: es el mecanismo detrás de la conexión del handbook en Copilot Studio |
