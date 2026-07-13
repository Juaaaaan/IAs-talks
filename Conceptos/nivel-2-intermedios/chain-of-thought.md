---
type: Concepto
title: "Chain of Thought (CoT) — Razonamiento paso a paso"
description: "Técnica que hace que el LLM razone explícitamente paso a paso antes de dar una respuesta final. Mejora drásticamente la precisión en tareas complejas."
tags: [chain-of-thought, cot, razonamiento, prompting, precision]
related: [context-engineering, system-prompt, structured-output]
estado: "✅ Publicado"
timestamp: "2026-07-09"
---

# Chain of Thought (CoT) — Razonamiento paso a paso

> _"Cuando le pides a la IA que piense paso a paso, sus respuestas mejoran dramáticamente."_

---

## Qué es

**Chain of Thought** es una técnica de prompting que hace que el LLM explicite su razonamiento intermedio antes de llegar a una conclusión.

En lugar de saltar directamente a la respuesta, el modelo muestra los pasos de su "pensamiento", lo que reduce errores y mejora la precisión en tareas complejas.

---

## Ejemplo

**Sin CoT:**
> P: ¿Cuántos ficheros del vault tienen type: Concepto y están relacionados con MCP?
> R: 3 ficheros.

**Con CoT:**
> P: Piensa paso a paso. ¿Cuántos ficheros del vault tienen type: Concepto y están relacionados con MCP?
> R: Voy a revisar cada fichero:
> 1. mcp.md → type: Concepto, related incluye arnes-completo ✓ (es el propio)
> 2. skills.md → type: Concepto, related incluye mcp ✓
> 3. arnes-completo.md → type: Concepto, related incluye mcp ✓
> 4. function-calling.md → type: Concepto, related incluye mcp ✓
> Total: 4 ficheros (incluyendo el propio mcp.md)

---

## Por qué funciona

Los LLMs generan tokens de izquierda a derecha. Si la respuesta correcta depende de razonamiento intermedio, forzar al modelo a generar ese razonamiento antes de la conclusión le da "espacio de pensamiento".

Es como pedirle a un humano que muestre su trabajo en un examen de matemáticas — los errores se reducen.

---

## Variantes

| Variante | Cómo se usa |
|---|---|
| **Zero-shot CoT** | Añadir "Piensa paso a paso" al prompt |
| **Few-shot CoT** | Dar ejemplos con razonamiento incluido |
| **Self-consistency** | Generar múltiples cadenas y elegir la respuesta más frecuente |
| **Tree of Thought** | Explorar múltiples ramas de razonamiento |

---

## Cuándo usar CoT

✅ **Útil para:**
- Tareas de lógica o matemáticas
- Análisis de código (encontrar bugs)
- Decisiones con múltiples factores
- Clasificaciones complejas

❌ **No necesario para:**
- Tareas simples de generación
- Resúmenes directos
- Traducciones
- Tareas donde la velocidad importa más que la precisión

---

## Reasoning Models

Los modelos de reasoning (como o1, o3, Claude con "thinking") implementan CoT de forma nativa — no necesitas pedirlo, el modelo razona internamente por defecto.

---

## Relación con otras piezas

- **[[context-engineering]]** — CoT es una técnica de diseño de prompts dentro del context engineering
- **[[system-prompt]]** — Se puede forzar CoT desde el system prompt
- **[[structured-output]]** — CoT se combina bien con outputs estructurados (razona → formatea)

---

## Referencias

- [Chain-of-Thought Prompting — Wei et al. 2022](https://arxiv.org/abs/2201.11903)
