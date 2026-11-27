---
type: Concepto
title: "Cuantización — El mismo modelo ocupando menos"
description: "Representar los números de un modelo con menor precisión para reducir la memoria que necesita y, según el caso, acelerar su ejecución. Puede afectar a la calidad."
tags: [cuantizacion, quantization, eficiencia, memoria, local, modelos]
related: [ia-local, modelos-pequenos-slm, destilacion, eval-benchmarking]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Cuantización

> _"Como guardar una foto con más compresión: ocupa menos y puede perder detalle."_

---

## Qué es

Un modelo está formado por muchísimos números. La **cuantización** los representa con **menos bits**, por ejemplo pasando de 16 a 8 o a 4. La comparación con la foto es solo una intuición.

---

## Cuenta orientativa

Para **7.000 millones de parámetros**, contando solo los pesos:

| Precisión | Bytes por parámetro | Memoria aproximada |
|---|---|---|
| 16 bits | 2 | 14 GB |
| 8 bits | 1 | 7 GB |
| 4 bits | 0,5 | 3,5 GB |

En la práctica se necesita **más memoria** para el contexto y la ejecución, y algunos formatos no cuantizan todas las partes igual.

---

## El compromiso

- **Se gana:** menos memoria y la posibilidad de usar hardware más modesto
- **Se puede perder:** calidad, de forma distinta según la tarea y el método
- **La velocidad** depende también del hardware y del software

Dos versiones del mismo modelo no tienen por qué comportarse igual: **evalúa la que vayas a usar**.

---

## Relación con otras piezas

- **[[ia-local]]** — Donde más se nota
- **[[modelos-pequenos-slm]]** — Otra forma de reducir recursos
- **[[destilacion]]** — Entrenar un modelo más pequeño, un enfoque diferente
- **[[eval-benchmarking]]** — Medir la pérdida de calidad
