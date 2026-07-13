---
type: Concepto
title: "Model Routing — Elegir el modelo correcto para cada tarea"
description: "Estrategia de dirigir cada petición al modelo más adecuado según la complejidad, coste y requisitos. No todas las tareas necesitan el modelo más potente ni el más barato."
tags: [model-routing, seleccion, modelos, coste, eficiencia, estrategia]
related: [temperature, context-engineering, eval-benchmarking, caching-cost]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Model Routing — Elegir el modelo correcto para cada tarea

> _"Usar GPT-5 para autocompletar un import es como usar un Ferrari para ir al buzón."_

---

## Qué es

**Model routing** (o model selection) es la estrategia de dirigir cada petición al modelo más adecuado según:
- La complejidad de la tarea
- El coste aceptable
- La latencia requerida
- Los requisitos de calidad

---

## El problema

| Modelo | Calidad | Coste | Velocidad |
|---|---|---|---|
| GPT-5 / Claude Opus | ⭐⭐⭐⭐⭐ | $$$$ | Lento |
| GPT-4o / Claude Sonnet | ⭐⭐⭐⭐ | $$ | Medio |
| GPT-4o-mini / Claude Haiku | ⭐⭐⭐ | $ | Rápido |
| Modelos locales | ⭐⭐ | Gratis | Variable |

Usar siempre el mejor modelo es caro. Usar siempre el barato sacrifica calidad. La solución es **enrutar**.

---

## Estrategias de routing

### 1. Por tipo de tarea
```
Autocomplete de código → modelo rápido/barato
Revisión de código → modelo potente
Generación de spec → modelo potente
Formateo de texto → modelo barato
```

### 2. Por complejidad estimada
Un clasificador rápido evalúa la complejidad y elige:
- Simple → modelo pequeño
- Complejo → modelo grande

### 3. Cascading (escalado)
```
1. Intenta con modelo barato
2. Si el resultado no es bueno → reintenta con modelo potente
```

### 4. Ensemble
Varios modelos responden y se elige la mejor respuesta (o se combinan).

---

## En la práctica

Copilot ya hace routing interno:
- **Tab completion** → modelo rápido optimizado para velocidad
- **Chat** → modelo medio (Sonnet)
- **Agente / Workspace** → modelo potente (Opus/GPT-5)

---

## Por qué importa

- **Coste:** Puedes reducir costes 10x enrutando bien
- **Velocidad:** Tareas simples se resuelven al instante
- **Calidad:** Las tareas complejas reciben la potencia que necesitan
- **Escalabilidad:** Soportar más usuarios sin multiplicar costes

---

## Relación con otras piezas

- **[[temperature]]** — Junto con el modelo, la temperature define el comportamiento
- **[[context-engineering]]** — El contexto puede determinar qué modelo necesitas
- **[[eval-benchmarking]]** — Necesitas eval para saber qué modelo funciona mejor en cada tarea
- **[[caching-cost]]** — Caching y routing son estrategias complementarias de optimización

---

## Referencias

- [Martian — Model Router](https://withmartian.com/)
- [OpenRouter — Multi-model API](https://openrouter.ai/)
