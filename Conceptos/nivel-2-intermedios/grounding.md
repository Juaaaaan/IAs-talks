---
type: Concepto
title: "Grounding — Respuestas apoyadas en fuentes"
description: "Anclar la respuesta de un modelo a información concreta y verificable que se le aporta, como documentos o resultados de búsqueda. Reduce las invenciones, pero no las elimina."
tags: [grounding, fuentes, citas, fiabilidad, rag]
related: [rag, alucinaciones, deep-research, busqueda-semantica, fecha-de-corte]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Grounding

> _"No me digas lo que recuerdas. Dime lo que pone aquí, y dónde."_

---

## Qué es

**Grounding** es hacer que la respuesta **se apoye en una fuente concreta** que el modelo tiene delante: un documento, una base de datos o un resultado de búsqueda.

---

## Grounding y RAG

| | Grounding | RAG |
|---|---|---|
| **Qué es** | El objetivo: respuestas ancladas a fuentes | Una técnica para conseguirlo buscando información antes de responder |
| **Ejemplo sin búsqueda** | Pegas el documento y pides que se ciña a él | No aplica: no hay paso de recuperación |

---

## Lo que no garantiza

- La fuente puede estar **desactualizada o equivocada**
- El sistema puede recuperar el **fragmento que no era**
- El modelo puede **interpretar mal** el texto o mezclarlo con lo que ya sabía
- Una **cita presente** no asegura que respalde la afirmación

---

## Cómo pedirlo

```
Responde solo con la información del documento adjunto.
Para cada afirmación, indica el apartado y copia la frase que la respalda.
Si el documento no lo dice, responde "No aparece en el documento".
```

Después, **comprueba las citas** de lo que importe.

---

## Relación con otras piezas

- **[[rag]]** — La técnica más conocida de recuperación y respuesta
- **[[alucinaciones]]** — El problema que ayuda a reducir
- **[[busqueda-semantica]]** — Una forma de encontrar la fuente relevante
- **[[deep-research]]** — Investigación con múltiples fuentes
- **[[fecha-de-corte]]** — Por qué hace falta aportar información reciente
