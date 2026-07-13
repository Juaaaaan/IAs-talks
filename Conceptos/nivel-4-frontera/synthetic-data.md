---
type: Concepto
title: "Synthetic Data & Self-Play — Datos sintéticos y auto-entrenamiento"
description: "Técnicas donde los modelos de IA generan sus propios datos de entrenamiento. Desde data augmentation hasta modelos que mejoran jugando contra sí mismos."
tags: [synthetic-data, self-play, entrenamiento, datos, augmentation, generacion]
related: [eval-benchmarking, reasoning-models, constitutional-ai]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Synthetic Data & Self-Play — Datos sintéticos y auto-entrenamiento

> _"Cuando se acaban los datos del mundo, la IA aprende generando los suyos."_

---

## Qué es

**Datos sintéticos** son datos generados artificialmente (por la propia IA o por programas) en lugar de recolectados del mundo real.

**Self-play** es una técnica donde el modelo juega contra sí mismo (o una versión anterior) para mejorar su rendimiento.

---

## Por qué importa

### El problema de los datos
- Los datos humanos de internet se están agotando
- Los datos de calidad son escasos y caros
- Datos reales tienen problemas de privacidad y sesgo
- No hay suficientes datos para dominios especializados

### La solución
- Generar datos de entrenamiento con IA
- Crear escenarios sintéticos para evaluar modelos
- Self-play para mejorar razonamiento

---

## Tipos de datos sintéticos

| Tipo | Descripción | Ejemplo |
|---|---|---|
| **Augmentation** | Variaciones de datos existentes | Parafrasear preguntas |
| **Generation** | Datos creados desde cero | Generar conversaciones de soporte |
| **Distillation** | Un modelo grande genera datos para entrenar uno pequeño | GPT-5 genera datos para entrenar Haiku |
| **Self-play** | El modelo genera problemas y los resuelve | AlphaGo, modelos de reasoning |
| **Simulation** | Datos de entornos simulados | Conducción autónoma en simulador |

---

## Self-play en detalle

```
Iteración 1: Modelo genera un problema de código
Iteración 2: Modelo intenta resolverlo
Iteración 3: Verificador comprueba si la solución es correcta
Iteración 4: Modelo aprende de los errores
Iteración 5: Repite con problemas más difíciles
```

Así es como se entrenan modelos de reasoning como DeepSeek R1.

---

## Riesgos

- **Model collapse:** Si el modelo se entrena solo con datos generados por IA, pierde diversidad
- **Amplificación de sesgos:** Los datos sintéticos heredan los sesgos del modelo generador
- **Calidad variable:** No todos los datos generados son correctos o útiles
- **Contaminación:** Datos sintéticos en internet contaminan futuros entrenamientos

---

## Relación con otras piezas

- **[[eval-benchmarking]]** — Los datos sintéticos se usan para crear benchmarks
- **[[reasoning-models]]** — Los reasoning models se mejoran con self-play
- **[[constitutional-ai]]** — Constitutional AI usa generación sintética para alineamiento

---

## Referencias

- [Synthetic Data — Stanford HAI](https://hai.stanford.edu/news/synthetic-data-ai)
- [DeepSeek R1 — Self-play training](https://arxiv.org/abs/2401.02954)
