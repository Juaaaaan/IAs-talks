---
type: Concepto
title: "Context Window Management — Gestión de la ventana de contexto"
description: "Estrategias para manejar el límite de tokens que un LLM puede procesar a la vez. Decidir qué entra, qué se resume y qué se descarta es clave para obtener buenos resultados."
tags: [context-window, tokens, gestion, limites, estrategias, truncamiento]
related: [context-engineering, rag, embeddings, wiki-llm]
estado: "✅ Publicado"
timestamp: "2026-07-09"
---

# Context Window Management — Gestión de la ventana de contexto

> _"El modelo no puede leer todo. Tu trabajo es decidir qué merece estar en su atención."_

---

## Qué es

La **ventana de contexto** es la cantidad máxima de texto que un LLM puede procesar en una sola llamada (medida en tokens). Gestionar esta ventana significa decidir estratégicamente qué información incluir y cuál dejar fuera.

---

## Tamaños actuales (2026)

| Modelo | Ventana | Equivalente aproximado |
|---|---|---|
| GPT-4o | 128K tokens | ~300 páginas |
| Claude Sonnet/Opus | 200K tokens | ~500 páginas |
| Gemini 2.5 | 1M tokens | ~2500 páginas |
| Modelos pequeños | 8-32K tokens | ~20-80 páginas |

---

## El problema

Aunque las ventanas crecen, siempre hay un límite. Y más importante: **más contexto ≠ mejor resultado**.

| Problema | Consecuencia |
|---|---|
| Contexto demasiado largo | El modelo "pierde" información del medio ("lost in the middle") |
| Contexto irrelevante | Distrae al modelo y empeora la respuesta |
| Sin contexto | Alucinaciones y respuestas genéricas |
| Contexto desorganizado | El modelo no encuentra lo relevante |

---

## Estrategias de gestión

### 1. Selección inteligente (RAG)
No meter todo — buscar solo lo relevante para la pregunta.

### 2. Resumen progresivo
Resumir conversaciones largas manteniendo los puntos clave.

### 3. Priorización por posición
- **Inicio del contexto:** Instrucciones (system prompt)
- **Final del contexto:** La pregunta actual
- **Medio:** Documentos de soporte (menos atención del modelo)

### 4. Chunking
Dividir documentos grandes en fragmentos manejables y pasar solo los relevantes.

### 5. Metadata-first (OKF)
Pasar primero los frontmatter/metadatos para que el modelo decida qué documentos necesita leer completos.

---

## Ejemplo práctico con el vault

```
❌ Malo: Pasar los 50+ ficheros del vault completos al modelo
✅ Bueno: 
  1. Pasar el index.md (mapa del vault)
  2. El modelo identifica qué ficheros necesita
  3. Pasar solo esos ficheros
```

Esto es exactamente lo que hace la navegación por `related:` en OKF.

---

## Por qué importa para esta serie

El **arnés completo** es en parte una solución al problema de context window:
- **copilot-instructions** → contexto persistente que siempre está presente
- **Wiki LLM + OKF** → contexto on-demand que el agente navega
- **RAG** → selección automática del contexto relevante

---

## Relación con otras piezas

- **[[context-engineering]]** — La gestión de ventana es una habilidad core del context engineering
- **[[rag]]** — RAG es la estrategia principal para no saturar la ventana
- **[[embeddings]]** — Permiten buscar qué meter en la ventana
- **[[wiki-llm]]** — El formato OKF optimiza la navegación sin saturar el contexto

---

## Referencias

- [Lost in the Middle — Liu et al. 2023](https://arxiv.org/abs/2307.03172)
- Concepto en glosario: [[glosario-ia-nivel-1]] §9
