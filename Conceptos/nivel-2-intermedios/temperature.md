---
type: Concepto
title: "Temperature y Top-P — Control de creatividad del modelo"
description: "Parámetros que controlan cuánta variabilidad y creatividad tiene la salida de un LLM. Temperature alta = más creativo. Temperature baja = más determinista y predecible."
tags: [temperature, top-p, parametros, creatividad, determinismo, configuracion]
related: [context-engineering, structured-output, system-prompt]
estado: "✅ Publicado"
timestamp: "2026-07-09"
---

# Temperature y Top-P — Control de creatividad del modelo

> _"Temperature baja para código. Temperature alta para brainstorming. No al revés."_

---

## Qué es

**Temperature** y **Top-P** son parámetros que controlan cuánta aleatoriedad tiene la salida del modelo:

- **Temperature = 0:** El modelo siempre elige la palabra más probable → respuestas deterministas, repetibles
- **Temperature = 1:** El modelo considera muchas opciones → respuestas variadas, creativas
- **Temperature > 1:** Más caótico → puede generar incoherencias

---

## La analogía

Imagina que el modelo tiene un dado para elegir cada palabra:

| Temperature | Comportamiento |
|---|---|
| 0 | Siempre elige la cara más pesada (la misma respuesta siempre) |
| 0.3 | Casi siempre la más pesada, pero a veces sorprende |
| 0.7 | Equilibrado — variedad con coherencia |
| 1.0 | Todas las caras tienen peso similar — muy creativo |
| 1.5+ | Caótico — puede decir cosas sin sentido |

---

## Temperature vs Top-P

| Parámetro | Qué controla |
|---|---|
| **Temperature** | Cuánto "suaviza" la distribución de probabilidades |
| **Top-P** (nucleus sampling) | Qué porcentaje de opciones considera (ej: solo el top 90%) |

En la práctica se suele ajustar uno u otro, no ambos a la vez.

---

## Guía práctica

| Tarea | Temperature recomendada |
|---|---|
| Generación de código | 0 – 0.2 |
| Análisis técnico | 0.1 – 0.3 |
| Resúmenes | 0.3 – 0.5 |
| Escritura general | 0.5 – 0.7 |
| Brainstorming / ideas | 0.7 – 1.0 |
| Escritura creativa | 0.8 – 1.2 |

---

## Ejemplo real

El mismo prompt con diferentes temperatures:

**Temperature 0:**
> "El patrón recomendado para estado en Angular es signals con servicios inyectables."

**Temperature 1:**
> "Podrías explorar signals combinados con un store ligero tipo mini-rx, o incluso un patrón pub-sub reactivo con observables compartidos."

---

## Cuándo importa

- **Copilot / agentes de código:** Temperature baja (quieres consistencia y corrección)
- **Chat creativo:** Temperature media-alta (quieres variedad)
- **Tests deterministas:** Temperature 0 (misma entrada = misma salida)

---

## Relación con otras piezas

- **[[context-engineering]]** — Temperature es un parámetro del diseño de contexto
- **[[structured-output]]** — Para outputs estructurados, temperature baja es esencial
- **[[system-prompt]]** — Algunos system prompts incluyen instrucciones de temperature

---

## Referencias

- [OpenAI Temperature parameter](https://platform.openai.com/docs/api-reference/chat/create#chat-create-temperature)
