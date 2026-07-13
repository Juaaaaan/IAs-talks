---
type: Concepto
title: "RAG — Retrieval-Augmented Generation"
description: "Técnica que combina búsqueda en documentos con generación de texto. La IA busca primero la información relevante y después responde usándola como base."
tags: [rag, retrieval, generacion, contexto, embeddings, grounding]
related: [wiki-llm, embeddings, context-engineering, okf]
estado: "✅ Publicado"
timestamp: "2026-07-09"
---

# RAG — Retrieval-Augmented Generation

> _"No entrenas al modelo con tu información — se la das en el momento de responder."_

---

## Qué es

**RAG** es una técnica donde la IA primero busca información relevante en una base de conocimiento y después genera la respuesta usando esa información como contexto.

En lugar de esperar que el modelo "sepa" algo (porque lo vio durante el entrenamiento), le proporcionas los documentos correctos justo antes de que responda.

---

## Por qué importa

| Sin RAG | Con RAG |
|---|---|
| La IA responde con lo que "recuerda" del entrenamiento | La IA responde con datos actuales y verificables |
| Alucinaciones frecuentes sobre datos internos | Respuestas ancladas a documentos reales |
| Necesitas re-entrenar para actualizar conocimiento | Actualizas los documentos y listo |
| No sabe nada de tu empresa | Puede consultar tu wiki, tu código, tus docs |

---

## Cómo funciona (simplificado)

```
1. Usuario hace pregunta
2. Sistema busca documentos relevantes (via embeddings)
3. Documentos encontrados se inyectan en el prompt
4. LLM genera respuesta basada en esos documentos
5. Usuario recibe respuesta con contexto real
```

---

## Ejemplo práctico

Un developer pregunta: _"¿Por qué no usamos NgRx en el proyecto RCA?"_

- **Sin RAG:** La IA inventa una razón genérica
- **Con RAG:** El sistema busca en el vault, encuentra `decision-no-ngrx.md`, lo inyecta en el contexto, y la IA responde con la razón real documentada

---

## RAG vs Wiki LLM

Un **Wiki LLM** con OKF es una forma de organizar el conocimiento para que un sistema RAG (o un agente) pueda encontrarlo eficientemente. Son complementarios:

- **RAG** = el mecanismo de búsqueda + inyección
- **Wiki LLM** = la fuente de conocimiento estructurada

---

## Relación con otras piezas

- **[[wiki-llm]]** — El Wiki LLM es la fuente ideal para un sistema RAG
- **[[embeddings]]** — Los embeddings son el mecanismo de búsqueda que usa RAG
- **[[context-engineering]]** — RAG es una técnica dentro del context engineering
- **[[okf]]** — OKF estructura los documentos para que RAG los encuentre mejor

---

## Referencias

- [RAG paper original — Lewis et al. 2020](https://arxiv.org/abs/2005.11401)
- Concepto en glosario: [[glosario-ia-nivel-1]] §12
