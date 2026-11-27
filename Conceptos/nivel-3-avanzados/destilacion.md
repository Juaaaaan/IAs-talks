---
type: Concepto
title: "Destilación — Un modelo aprende de otro"
description: "Técnica en la que un modelo alumno, normalmente más pequeño, se entrena usando las salidas de un modelo maestro para conservar parte de su capacidad con menos recursos."
tags: [destilacion, distillation, entrenamiento, eficiencia, modelos]
related: [modelos-pequenos-slm, fine-tuning, cuantizacion, synthetic-data]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Destilación

> _"El alumno no copia el cerebro del maestro: aprende de cómo responde."_

---

## Qué es

En la **destilación de conocimiento**, un modelo **maestro** sirve para entrenar a un modelo **alumno**. El alumno aprende de las salidas del maestro (en la forma clásica, de las probabilidades que asigna a cada opción; en otras variantes, de ejemplos que genera).

---

## Destilación vs cuantización

| | Destilación | [[cuantizacion]] |
|---|---|---|
| **Qué hace** | Entrena un modelo alumno | Reduce la precisión numérica |
| **¿Cambia la arquitectura?** | Puede ser distinta y más pequeña | Normalmente se mantiene |
| **Necesita entrenar** | Sí | No siempre |

Se pueden combinar.

---

## Límites

- El alumno **no hereda todo** lo que sabe el maestro
- Puede heredar **errores y sesgos**
- Hay que evaluarlo en las tareas donde se va a usar
- Usar las salidas de un modelo de terceros para entrenar otro puede estar **limitado por sus condiciones de uso**

---

## Ejemplo práctico

Con un modelo grande se generan respuestas para una tarea concreta, se revisan y con ellas se entrena un modelo pequeño que la haga a menor coste.

---

## Relación con otras piezas

- **[[modelos-pequenos-slm]]** — Un resultado habitual
- **[[fine-tuning]]** — Puede usarse en el proceso
- **[[cuantizacion]]** — Otra técnica de eficiencia
- **[[synthetic-data]]** — Los ejemplos generados son datos sintéticos

---

## Referencias

- [Distilling the Knowledge in a Neural Network (Hinton et al., 2015)](https://arxiv.org/abs/1503.02531)
