---
type: Concepto
title: "SLM — Modelos pequeños para tareas concretas"
description: "Small Language Models: modelos de lenguaje bastante más compactos que los grandes. Cuestan menos de ejecutar y pueden rendir muy bien en tareas acotadas, con menos capacidad general."
tags: [slm, modelos-pequenos, eficiencia, coste, local, modelos]
related: [llm, ia-local, cuantizacion, destilacion, model-routing]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# SLM — Small Language Models

> _"No necesitas un camión para llevar una carta."_

---

## Qué es

Un **SLM** es un modelo de lenguaje **compacto**. No hay una frontera oficial de tamaño que separe un SLM de un LLM, y lo que hoy se considera pequeño cambia con el tiempo.

---

## Comparativa orientativa

| | Modelo grande | Modelo pequeño |
|---|---|---|
| **Capacidad general** | Mayor | Más limitada |
| **Recursos y coste** | Más altos | Más bajos |
| **Latencia** | Suele ser mayor en igualdad de condiciones | Suele ser menor |
| **Ejecución en local** | Exige hardware potente | Más asequible |

---

## Cuándo tiene sentido

- Tarea **acotada y repetitiva**: clasificar, extraer campos, resumir textos cortos
- Mucho volumen, donde el coste importa
- Hardware limitado o necesidad de trabajar sin conexión

---

## Cómo decidir

Prueba con **tus propios casos** y compara calidad, coste y tiempo. Un enrutado puede mandar lo sencillo al modelo pequeño y lo difícil a uno mayor (ver [[model-routing]]).

---

## Relación con otras piezas

- **[[llm]]** — La misma idea a mayor escala
- **[[ia-local]]** — Ejecutarlo en tus equipos
- **[[cuantizacion]]** — Reducir los recursos que necesita un modelo
- **[[destilacion]]** — Una vía para obtener modelos más compactos
- **[[model-routing]]** — Elegir modelo según la tarea
