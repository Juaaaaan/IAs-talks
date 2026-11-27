---
type: Concepto
title: "Fine-tuning — Ajustar un modelo con ejemplos propios"
description: "Entrenamiento adicional de un modelo ya entrenado para especializar su comportamiento. Suele ser más adecuado para fijar forma y tareas que para mantener conocimiento que cambia."
tags: [fine-tuning, ajuste, entrenamiento, lora, modelos]
related: [modelo-fundacional, entrenamiento-vs-inferencia, rag, few-shot, destilacion, rlhf]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Fine-tuning

> _"RAG le pasa los apuntes en el examen. El fine-tuning le hace practicar antes."_

---

## Qué es

El **fine-tuning** es seguir entrenando un modelo ya existente con ejemplos específicos. A diferencia de dar instrucciones, **modifica el modelo** (o añade parámetros adaptados a él). Una técnica extendida es **LoRA**, que entrena un conjunto pequeño de parámetros adicionales.

---

## Cuándo usar qué

| Necesidad | Primera opción a probar |
|---|---|
| Un formato o tono puntual | Instrucciones y [[few-shot]] |
| Responder con documentos que cambian | [[rag]] |
| Un comportamiento muy repetitivo que lo anterior no consigue de forma consistente | Fine-tuning |

---

## Antes de decidirlo

- Hacen falta **ejemplos buenos y representativos**
- Hay que **evaluar** antes y después
- Hay que **mantenerlo** cuando cambie el modelo base
- Si se entrena con datos sensibles, el modelo puede **memorizar y revelar** parte de ellos
- No es una forma fiable de "meter la documentación de la empresa"

---

## Ejemplo práctico

Clasificar miles de comunicaciones en categorías propias y muy específicas, después de comprobar que con instrucciones y ejemplos no se alcanza la calidad necesaria.

---

## Relación con otras piezas

- **[[modelo-fundacional]]** — El punto de partida
- **[[entrenamiento-vs-inferencia]]** — El fine-tuning es entrenamiento
- **[[rag]]** — Aportar conocimiento sin modificar el modelo
- **[[destilacion]]** y **[[rlhf]]** — Otras formas de entrenar o adaptar modelos

---

## Referencias

- [LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685)
