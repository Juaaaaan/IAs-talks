---
type: Concepto
title: "Mixture of Experts — No todo el modelo trabaja a la vez"
description: "Arquitectura en la que partes del modelo se dividen en varios bloques llamados expertos y un mecanismo de enrutado activa solo algunos para cada token, reduciendo el cálculo."
tags: [moe, mixture-of-experts, arquitectura, eficiencia, modelos]
related: [transformer-atencion, llm, model-routing, cuantizacion]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Mixture of Experts (MoE)

> _"Un modelo muy grande que, para cada token, enciende solo una parte."_

---

## Qué es

En un modelo **MoE**, ciertas capas contienen varios sub-bloques (**expertos**) y un **enrutador** decide cuáles se usan para cada token.

---

## Dos malentendidos

| Se suele pensar | En realidad |
|---|---|
| "Hay un experto en derecho y otro en cocina" | La especialización se aprende al entrenar y no tiene por qué corresponder a temas humanos |
| "Es lo mismo que elegir entre varios modelos" | El enrutado MoE ocurre **dentro** de un modelo. [[model-routing]] elige **entre** modelos |

---

## Parámetros totales y activos

- **Totales:** todos los del modelo
- **Activos:** los que intervienen en el cálculo de cada token

Un MoE puede tener muchos parámetros totales y usar una fracción en cada paso. Eso ahorra **cálculo**, pero no implica que necesite poca **memoria**: los expertos tienen que estar disponibles.

---

## Para qué te sirve saberlo

Al comparar modelos, una cifra de parámetros por sí sola dice poco: conviene saber si son totales o activos y, sobre todo, probar el rendimiento en tus tareas.

---

## Relación con otras piezas

- **[[transformer-atencion]]** — La arquitectura con la que suele combinarse
- **[[llm]]** — Donde se aplica
- **[[model-routing]]** — Enrutado entre modelos distintos
- **[[cuantizacion]]** — Otra vía para reducir recursos

---

## Referencias

- [Outrageously Large Neural Networks (Shazeer et al., 2017)](https://arxiv.org/abs/1701.06538)
