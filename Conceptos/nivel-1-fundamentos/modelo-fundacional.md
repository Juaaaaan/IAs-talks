---
type: Concepto
title: "Modelo fundacional — La base sobre la que se construye"
description: "Modelo entrenado a gran escala con datos amplios que sirve de base para muchas tareas y productos distintos, directamente o tras adaptarlo."
tags: [modelo-fundacional, foundation-model, modelos, fundamentos]
related: [ia-generativa, llm, fine-tuning, modelos-abiertos-vs-cerrados, provider]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Modelo fundacional

> _"Un mismo cimiento, muchos edificios."_

---

## Qué es

Un **modelo fundacional** (*foundation model*) se entrena a gran escala con datos muy amplios y luego **sirve de base para muchas tareas**. En lugar de construir un modelo desde cero para cada problema, se parte de uno general y se orienta o adapta.

> No confundir con las notas marcadas como *Foundation* en este vault, que pertenecen al vocabulario de [[ai-sdlc-foundation]]. Es otra cosa.

---

## Modelo fundacional, LLM y asistente

| Término | Alcance |
|---|---|
| **Modelo fundacional** | Categoría amplia: texto, imagen, audio u otros datos |
| **LLM** | Modelo grande centrado en lenguaje |
| **Asistente** | El producto que usas, construido encima de uno o varios modelos |

---

## Formas de adaptarlo

1. **Instrucciones y ejemplos** en cada petición (ver [[few-shot]])
2. **Darle documentos** en el momento de responder (ver [[rag]])
3. **Ajustarlo con entrenamiento adicional** (ver [[fine-tuning]])

Suele tener sentido probar las dos primeras antes de plantearse la tercera.

---

## Por qué importa

Muchos productos dependen de un modelo de un tercero. Conviene saber **cuál** hay debajo, quién lo ofrece y qué pasa si cambia o se retira.

---

## Relación con otras piezas

- **[[llm]]** — El tipo más conocido
- **[[fine-tuning]]** — Adaptarlo con datos propios
- **[[modelos-abiertos-vs-cerrados]]** — Dos formas de acceder a estos modelos
- **[[provider]]** — La plataforma que los pone a disposición dentro de AI SDLC Foundation
