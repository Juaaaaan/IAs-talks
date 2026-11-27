---
type: Concepto
title: "Machine learning y redes neuronales — Aprender de ejemplos"
description: "El machine learning construye sistemas que aprenden patrones a partir de datos en lugar de seguir reglas escritas una a una. Las redes neuronales son una de sus técnicas y la base del deep learning."
tags: [machine-learning, redes-neuronales, deep-learning, fundamentos]
related: [ia-generativa, entrenamiento-vs-inferencia, transformer-atencion, llm, synthetic-data]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Machine learning y redes neuronales

> _"No le escribes la regla: le das ejemplos y la encuentra."_

---

## El mapa en una línea

```
Inteligencia artificial
└── Machine learning (aprende de datos)
    └── Deep learning (redes neuronales con muchas capas)
        └── Buena parte de la IA generativa actual, incluidos los LLM
```

---

## Qué es

- **Machine learning:** el sistema ajusta un modelo a partir de datos para hacer predicciones o decisiones
- **Red neuronal:** un modelo formado por muchas operaciones matemáticas conectadas, con valores ajustables llamados **parámetros** o pesos. Se inspira vagamente en el cerebro, pero no funciona como él
- **Deep learning:** redes neuronales con muchas capas

---

## Reglas escritas vs aprendizaje

| Programación con reglas | Machine learning |
|---|---|
| Una persona define cada regla | El modelo aprende patrones de ejemplos |
| Fácil de explicar | Puede ser difícil de explicar |
| Falla ante casos no previstos | Puede generalizar, y también equivocarse |
| Ideal si la regla es clara | Útil si la regla es difícil de escribir |

---

## Ejemplo práctico

Detectar correo no deseado: en vez de mantener una lista infinita de palabras prohibidas, se entrena un modelo con correos ya etiquetados como *spam* o *no spam*.

**Criterio:** si una regla sencilla resuelve el problema, no hace falta machine learning.

---

## Relación con otras piezas

- **[[entrenamiento-vs-inferencia]]** — Las dos fases de la vida de un modelo
- **[[ia-generativa]]** — Modelos que además crean contenido
- **[[transformer-atencion]]** — Una arquitectura de red neuronal muy influyente
- **[[synthetic-data]]** — Datos artificiales para entrenar
