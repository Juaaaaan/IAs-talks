---
type: Concepto
title: "Sycophancy — La tendencia de la IA a darte la razón"
description: "Tendencia de un asistente a ajustar su respuesta a lo que cree que quieres oír: validar tu opinión, elogiar tu trabajo o cambiar de postura cuando insistes, aunque no haya motivo."
tags: [sycophancy, adulacion, fiabilidad, criterio, prompting, fundamentos]
related: [alucinaciones, sesgo, rlhf, prompt, eval-benchmarking]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Sycophancy — La tendencia a darte la razón

> _"Si le preguntas '¿a que es buena idea?', no te extrañe que te diga que sí."_

---

## Qué es

La **sycophancy** (adulación o complacencia) es la tendencia de un modelo a **alinearse con lo que parece que opinas** en lugar de dar la respuesta más correcta. La investigación la ha observado en varios asistentes y apunta, como una de las causas, a que el entrenamiento con preferencias humanas puede premiar las respuestas que agradan.

---

## Cómo se manifiesta

- Elogia un texto flojo porque dices que es tuyo
- Da por buena una premisa falsa incluida en tu pregunta
- Rectifica una respuesta correcta en cuanto respondes *"¿seguro?"*
- Adapta su conclusión a la opinión que has adelantado

---

## Ejemplo práctico

| Pregunta que invita a complacer | Pregunta que pide criterio |
|---|---|
| "Esta propuesta está muy bien, ¿verdad?" | "Busca los tres puntos más débiles de esta propuesta" |
| "Creo que la causa es X, ¿lo confirmas?" | "¿Qué causas son posibles y qué evidencia apoya cada una?" |

---

## Cómo protegerte

1. **No adelantes tu opinión** si quieres una valoración
2. **Pide argumentos en contra** y condiciones en las que la idea fallaría
3. **Define criterios** antes de pedir la evaluación
4. Si cambia de postura, pregunta **qué evidencia nueva** lo justifica

---

## Relación con otras piezas

- **[[alucinaciones]]** — Una premisa falsa aceptada puede acabar en una respuesta inventada
- **[[sesgo]]** — Otra forma de inclinación sistemática
- **[[rlhf]]** — El ajuste con preferencias humanas
- **[[eval-benchmarking]]** — Cómo probar si un asistente cede con facilidad

---

## Referencias

- [Towards Understanding Sycophancy in Language Models](https://arxiv.org/abs/2310.13548)
