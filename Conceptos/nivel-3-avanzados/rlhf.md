---
type: Concepto
title: "RLHF — Aprender de las preferencias humanas"
description: "Reinforcement Learning from Human Feedback: personas comparan respuestas del modelo y esas preferencias se usan para ajustarlo. Mejora el seguimiento de instrucciones, pero no garantiza la verdad."
tags: [rlhf, alineamiento, entrenamiento, preferencias, feedback]
related: [constitutional-ai, fine-tuning, sycophancy, entrenamiento-vs-inferencia, sesgo]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# RLHF

> _"El modelo aprende qué respuestas se prefieren, y preferida no siempre significa correcta."_

---

## Qué es

El **RLHF** es una técnica de ajuste basada en **preferencias humanas**. En su esquema clásico:

1. El modelo genera varias respuestas
2. Personas las **comparan u ordenan**
3. Se entrena un **modelo de recompensa** que intenta predecir esas preferencias
4. El modelo se ajusta con aprendizaje por refuerzo para obtener mejor recompensa

> [[constitutional-ai]] ya compara RLHF con Constitutional AI. Esta nota da a RLHF **una entrada propia** y no repite la comparativa.

---

## Qué aporta y qué limita

| Aporta | Limita |
|---|---|
| Respuestas más ajustadas a lo que se pide | Las personas evaluadoras no siempre coinciden |
| Captura criterios difíciles de escribir como regla | Se heredan sus preferencias y sesgos |
| Ayuda a moderar comportamientos no deseados | Puede premiar lo que **suena** bien o agrada |

Hoy conviven varias técnicas de ajuste, y cada proveedor combina las suyas.

---

## Matiz importante

Valorar una respuesta con un pulgar en una aplicación **no reentrena el modelo al instante**. Que ese dato se use o no depende de las condiciones del producto.

---

## Relación con otras piezas

- **[[constitutional-ai]]** — Alineamiento guiado por principios escritos
- **[[fine-tuning]]** — El ajuste de modelos en general
- **[[sycophancy]]** — Un efecto que las preferencias humanas pueden favorecer
- **[[sesgo]]** — Las inclinaciones que se pueden transmitir

---

## Referencias

- [Training language models to follow instructions with human feedback](https://arxiv.org/abs/2203.02155)
