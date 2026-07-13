---
type: Concepto
title: "Caching & Cost Optimization — Optimización de costes en IA"
description: "Técnicas para reducir el coste y la latencia de usar LLMs: prompt caching, batching, model routing, y gestión eficiente de tokens. Fundamental para uso empresarial sostenible."
tags: [caching, costes, optimizacion, tokens, latencia, prompt-caching, batching]
related: [model-routing, context-window-management, temperature, eval-benchmarking]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Caching & Cost Optimization — Optimización de costes en IA

> _"La llamada más barata a un LLM es la que no necesitas hacer."_

---

## Qué es

Estrategias para reducir el coste económico y la latencia de usar LLMs en producción, sin sacrificar calidad de forma significativa.

---

## Los costes de un LLM

| Componente | Coste |
|---|---|
| **Input tokens** | Lo que envías al modelo (contexto + pregunta) |
| **Output tokens** | Lo que genera el modelo (generalmente más caro) |
| **Reasoning tokens** | Tokens de "pensamiento" en modelos de reasoning |
| **Latencia** | Tiempo de espera = productividad perdida |

---

## Técnicas de optimización

### 1. Prompt Caching
Cachear el prefijo del prompt (system prompt + instrucciones) para no reprocesarlo en cada llamada.

- **Anthropic:** Cache automática de prefijos frecuentes (90% de descuento)
- **OpenAI:** Prompt caching en la API (50% de descuento)
- **Impacto:** System prompts largos (como copilot-instructions) se cachean

### 2. Respuesta cacheada
Si la misma pregunta se repite, devolver la respuesta anterior sin llamar al modelo.

### 3. Model Routing
Usar modelos más baratos para tareas simples (ver [[model-routing]]).

### 4. Batching
Agrupar varias peticiones en una sola llamada cuando es posible.

### 5. Reducción de tokens
- Prompts más concisos (sin sacrificar claridad)
- Resumir documentos antes de inyectarlos
- Limitar la salida con `max_tokens`

### 6. Streaming
No reduce el coste pero mejora la percepción de velocidad — el usuario ve la respuesta mientras se genera.

---

## Ejemplo de impacto

```
Sin optimizar:
  200K tokens/día × $10/M tokens = $2/día = $60/mes

Con prompt caching + routing:
  Caching: -50% en input = $1/día
  Routing: 70% de peticiones a modelo barato = $0.40/día
  Total: $12/mes (80% de ahorro)
```

---

## Para este vault

El diseño OKF del vault ya optimiza costes:
- Los agentes navegan por `related:` en vez de leer todos los ficheros
- El `description` del frontmatter permite decidir si leer el fichero completo
- El `type` filtra qué ficheros son relevantes para cada tarea

---

## Relación con otras piezas

- **[[model-routing]]** — Routing es la optimización de coste más impactante
- **[[context-window-management]]** — Menos contexto = menos tokens = menos coste
- **[[temperature]]** — Temperature 0 permite cachear respuestas deterministas
- **[[eval-benchmarking]]** — Necesitas eval para saber si la optimización mantiene la calidad

---

## Referencias

- [Anthropic Prompt Caching](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching)
- [OpenAI Pricing](https://openai.com/pricing)
