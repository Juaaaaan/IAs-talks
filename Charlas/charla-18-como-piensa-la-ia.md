---
type: Charla
title: "Charla 18 — Abriendo la caja: cómo piensa la IA por dentro"
description: "Cuatro mecanismos internos de un LLM, demostrados en directo sobre un Excel de proyecto real: predicción del siguiente token, embeddings (búsqueda por significado), alucinación (y cómo se ha movido el riesgo en 2026), y la ventana de contexto. Cierra mostrando que los cuatro son el mismo motor."
tags: [charla, mecanismos-internos, embeddings, alucinaciones, ventana-de-contexto, rag]
related: [MATERIAL-CHARLA-18-COMO-PIENSA-LA-IA, guion-charla-18, prediccion-siguiente-token, embeddings, alucinaciones, context-window-management, rag]
charla: "Charla 18"
fecha: "2026-08-26"
estado: "✅ Impartida"
timestamp: "2026-08-26"
---

# Charla 18 — Abriendo la caja: cómo piensa la IA por dentro

**Estado:** ✅ Impartida

---

## Idea central

> _"Por dentro, la IA hace una sola cosa —predecir lo que viene después— y los otros tres comportamientos son consecuencias de esa única cosa."_

## Hilo narrativo

Primera charla que abre la caja negra para audiencia no técnica, usando como hilo un Excel de proyecto real sobre el que se hacen las cuatro preguntas en directo. El hallazgo de este ensayo —que con un buen modelo y una fuente delante el riesgo de alucinación se ha desplazado— pasa a formar parte del canon de la serie y se vuelve a citar en la 19 y la 22.

## Estructura

| Mecanismo | La pregunta | Lo que se vio |
|---|---|---|
| 1. Predicción del siguiente token | ¿Cómo "entiende" la hoja? | No entiende: predice el patrón más probable, palabra a palabra |
| 2. Embeddings | ¿Cómo agrupa cosas parecidas? | Por significado, no por palabras — geometría: lo parecido queda cerca en un mapa de coordenadas; ejemplo rey−hombre+mujer≈reina; de ahí sale el RAG |
| 3. Alucinaciones | ¿Cuándo se lo inventa (y cuándo ya no)? | El ensayo en directo no consiguió que alucinara con la fuente delante — el riesgo se ha desplazado a sin-fuente, modelos flojos y premisas falsas |
| 4. Ventana de contexto | ¿Por qué "se le olvida" en chats largos? | Una mesa de tamaño fijo; lo que no cabe se empuja fuera y puede rellenarse inventando |

Demo en directo sobre un Excel de proyecto real (sin datos sensibles).

## Conceptos que introduce

- [[prediccion-siguiente-token]]
- [[embeddings]] — con el desarrollo más extenso que ha tenido en la serie: hipótesis distribucional, dos generaciones (vectores de palabra vs embeddings modernos), y cómo alimentan el RAG
- [[alucinaciones]] — actualizado con el desplazamiento del riesgo en 2026 (canon de la serie, ver [[learnings]])
- [[context-window-management]]

## Material asociado

- [[MATERIAL-CHARLA-18-COMO-PIENSA-LA-IA]] — guía larga, con el "kit del lunes" completo y el cierre que cose los cuatro mecanismos en uno

## Frases clave

> _"La distinción que lo cambia todo: predecir el patrón ≠ saber la verdad."_

> _"Entender esto es lo que separa a quien usa la IA a ciegas de quien la dirige. No hace falta programar. Hace falta el modelo mental."_

---

## Retrospectiva

_(pendiente de completar)_
