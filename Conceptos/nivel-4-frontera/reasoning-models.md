---
type: Concepto
title: "Reasoning Models — Modelos que piensan antes de responder"
description: "Nueva generación de modelos (o1, o3, Claude thinking) que dedican tokens a razonar internamente antes de generar la respuesta. Mayor precisión en tareas complejas a cambio de más latencia y coste."
tags: [reasoning, modelos, o1, o3, thinking, razonamiento, precision]
related: [chain-of-thought, planning-reasoning, model-routing, eval-benchmarking]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Reasoning Models — Modelos que piensan antes de responder

> _"Los modelos normales responden. Los reasoning models piensan, y después responden."_

---

## Qué es

Los **reasoning models** son una nueva generación de LLMs que dedican tiempo y tokens a razonar internamente (chain of thought nativo) antes de producir una respuesta.

A diferencia de un LLM estándar que genera la respuesta directamente, estos modelos:
1. Reciben la pregunta
2. Generan una cadena de razonamiento (visible o no)
3. Producen la respuesta final basada en ese razonamiento

---

## Modelos actuales (2026)

| Modelo | Proveedor | Razonamiento |
|---|---|---|
| o1 / o3 | OpenAI | Thinking tokens (ocultos o visibles) |
| Claude con Extended Thinking | Anthropic | Thinking block visible |
| Gemini 2.5 Pro Thinking | Google | Razonamiento interno |
| DeepSeek R1 | DeepSeek | Razonamiento abierto (open-source) |

---

## Cuándo usar reasoning vs estándar

| Tarea | Modelo recomendado |
|---|---|
| Autocompletar código simple | Estándar (rápido, barato) |
| Debuggear un error complejo | Reasoning (necesita analizar) |
| Escribir un email | Estándar |
| Diseñar una arquitectura | Reasoning |
| Generar JSON desde plantilla | Estándar |
| Resolver un puzzle lógico | Reasoning |

---

## Tradeoffs

| Ventaja | Desventaja |
|---|---|
| Mucho más preciso en lógica y matemáticas | 3-10x más lento |
| Mejor en problemas multi-paso | 3-10x más caro |
| Menos alucinaciones en razonamiento | Puede "sobre-pensar" tareas simples |
| Mejor planificación | Los thinking tokens consumen ventana de contexto |

---

## Effort levels

Muchos reasoning models permiten ajustar cuánto "piensan":

```
Low effort    → razonamiento mínimo → rápido, barato
Medium effort → razonamiento moderado → equilibrado
High effort   → razonamiento profundo → lento, preciso
```

Elegir el effort level correcto es una forma de [[model-routing]].

---

## Relación con otras piezas

- **[[chain-of-thought]]** — Los reasoning models implementan CoT de forma nativa
- **[[planning-reasoning]]** — Son los mejores modelos para tareas de planificación
- **[[model-routing]]** — Saber cuándo usar reasoning vs estándar es clave
- **[[eval-benchmarking]]** — Los benchmarks muestran grandes diferencias en tareas de lógica

---

## Referencias

- [OpenAI o1 blog](https://openai.com/index/learning-to-reason-with-llms/)
- [Anthropic Extended Thinking](https://docs.anthropic.com/en/docs/build-with-claude/extended-thinking)
- [DeepSeek R1](https://github.com/deepseek-ai/DeepSeek-R1)
