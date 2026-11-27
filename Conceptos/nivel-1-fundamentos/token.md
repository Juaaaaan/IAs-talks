---
type: Concepto
title: "Token — La unidad en la que la IA lee, escribe y cobra"
description: "Un token es el fragmento de texto con el que trabaja un modelo: una palabra, parte de ella o un signo. Los límites de longitud y el coste de uso de los modelos se miden en tokens."
tags: [token, tokenizacion, coste, limites, fundamentos]
related: [llm, prediccion-siguiente-token, context-window-management, caching-cost]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Token — La unidad en la que la IA lee, escribe y cobra

> _"Tú cuentas palabras. El modelo cuenta tokens."_

---

## Qué es

Un **token** es el trozo de texto con el que trabaja un modelo. Puede ser una palabra entera, un fragmento de palabra, un signo de puntuación o un espacio. El proceso de partir el texto se llama **tokenización**, y cada familia de modelos puede partirlo de forma distinta.

No hay una equivalencia fija entre palabras y tokens: depende del modelo y del idioma.

---

## Por qué importa

| Dónde aparece | Qué implica |
|---|---|
| **Límite de longitud** | La ventana de contexto se mide en tokens |
| **Coste** | En el uso por API se suele pagar por tokens de entrada y de salida |
| **Velocidad** | Cuantos más tokens genera, más tarda |
| **Conversaciones largas** | El historial que se reenvía también ocupa y consume tokens |

---

## Ejemplo práctico

Pegar un documento de 80 páginas para preguntar por una sola cláusula obliga al modelo a procesar las 80 páginas. Dar solo la parte relevante consume menos y suele facilitar una respuesta más centrada.

---

## En qué se diferencia de la predicción del siguiente token

Esta nota explica **la unidad**. [[prediccion-siguiente-token]] explica **el mecanismo**: cómo el modelo elige qué token viene después.

---

## Relación con otras piezas

- **[[llm]]** — El modelo que lee y genera tokens
- **[[prediccion-siguiente-token]]** — Cómo se genera la respuesta token a token
- **[[context-window-management]]** — Cómo repartir un espacio limitado de tokens
- **[[caching-cost]]** — Cómo reducir coste y latencia
