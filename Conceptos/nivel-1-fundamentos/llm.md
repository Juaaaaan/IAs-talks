---
type: Concepto
title: "LLM — Modelo de lenguaje grande"
description: "Un Large Language Model es un modelo entrenado con enormes cantidades de texto para predecir cómo continúa una secuencia. Es el motor que hay debajo de los asistentes de IA, pero no es lo mismo que la aplicación que usas."
tags: [llm, modelos, lenguaje, fundamentos]
related: [ia-generativa, token, prediccion-siguiente-token, transformer-atencion, entrenamiento-vs-inferencia, modelos-pequenos-slm]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# LLM — Modelo de lenguaje grande

> _"El asistente es el coche. El LLM es el motor."_

---

## Qué es

Un **LLM** (*Large Language Model*) es un modelo entrenado con una cantidad enorme de texto para **predecir cómo continúa una secuencia**. Con ese mecanismo, repetido muchas veces, redacta, resume, traduce, programa o responde preguntas.

---

## Modelo no es lo mismo que aplicación

| Pieza | Qué es |
|---|---|
| **Modelo (LLM)** | El "cerebro" que genera el texto |
| **Aplicación** | El chat o asistente donde escribes |
| **Alrededor del modelo** | Instrucciones, documentos, búsqueda, memoria y herramientas |

Dos aplicaciones pueden usar el mismo modelo y comportarse de forma muy distinta, porque lo que cambia es todo lo que lo rodea.

---

## Por qué importa

- Un LLM, por sí solo, **no consulta una base de datos de verdades**
- **No conoce tu empresa** salvo que le des esa información (ver [[rag]])
- **No aprende de cada conversación** en el momento: su entrenamiento ya ocurrió (ver [[entrenamiento-vs-inferencia]]). Las funciones de memoria guardan información aparte y se la vuelven a dar
- Qué se hace con tus datos depende del **producto y del contrato**, no del concepto de LLM

---

## Ejemplo práctico

Cuando pides "resume este contrato", la aplicación junta tu petición, el documento y sus propias instrucciones, y se lo entrega todo al LLM. El modelo genera el resumen trozo a trozo.

---

## Relación con otras piezas

- **[[token]]** — La unidad en la que un LLM lee y escribe
- **[[prediccion-siguiente-token]]** — El mecanismo básico de funcionamiento
- **[[transformer-atencion]]** — La arquitectura en la que se basan los LLM actuales más conocidos
- **[[entrenamiento-vs-inferencia]]** — Cuándo aprende y cuándo solo responde
- **[[modelos-pequenos-slm]]** — La versión compacta de la misma idea
