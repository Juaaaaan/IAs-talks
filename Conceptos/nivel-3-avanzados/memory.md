---
type: Concepto
title: "Memory — Memoria de los agentes de IA"
description: "Mecanismos para que los agentes recuerden información entre sesiones. Memoria a corto plazo (conversación) y a largo plazo (persistente). Sin memoria, cada interacción empieza desde cero."
tags: [memoria, agentes, short-term, long-term, persistencia, contexto]
related: [context-window-management, wiki-llm, rag, context-engineering]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Memory — Memoria de los agentes de IA

> _"Sin memoria, la IA es brillante pero amnésica. Cada conversación empieza desde cero."_

---

## Qué es

**Memory** en IA se refiere a los mecanismos que permiten a un agente retener y recuperar información más allá de una sola interacción.

Los LLMs por defecto no tienen memoria — cada conversación es independiente. La memoria se añade como capa externa.

---

## Tipos de memoria

| Tipo | Duración | Ejemplo |
|---|---|---|
| **Short-term** | Una conversación | El historial del chat actual |
| **Working memory** | Una tarea | Los ficheros abiertos mientras programa |
| **Long-term** | Persistente | El Wiki LLM, preferencias del usuario |
| **Episodic** | Eventos pasados | "La última vez que hicimos deploy falló por X" |
| **Semantic** | Conocimiento | "NgRx no se usa en este proyecto porque..." |

---

## El problema sin memoria

```
Conversación 1: "No uses NgRx, usa signals"
                 → OK, perfecto

Conversación 2: "Implementa el estado del carrito"
                 → Genera con NgRx (¡no recuerda!)
```

---

## Soluciones actuales

### 1. Instrucciones persistentes
- `copilot-instructions.md`, `CLAUDE.md`
- Siempre presentes → memoria "hardcoded"

### 2. Wiki LLM
- Vault de ficheros que el agente consulta
- Memoria semántica navegable

### 3. RAG
- Busca información relevante bajo demanda
- Memoria on-demand

### 4. Memory stores
- Bases de datos donde el agente guarda y recupera hechos
- Claude memory, ChatGPT memory, Mem0

### 5. Resumen de conversaciones
- Resumir chats largos y mantener el resumen como contexto

---

## Wiki LLM como memoria

El vault de este proyecto es un ejemplo de **memoria a largo plazo**:
- Las decisiones de arquitectura persisten entre sesiones
- Los perfiles del equipo están siempre disponibles
- El conocimiento crece con cada interacción

---

## Relación con otras piezas

- **[[context-window-management]]** — La memoria compite por espacio en la ventana de contexto
- **[[wiki-llm]]** — Un Wiki LLM es memoria a largo plazo estructurada
- **[[rag]]** — RAG es el mecanismo para recuperar memorias relevantes
- **[[context-engineering]]** — Diseñar la memoria es parte del context engineering

---

## Referencias

- [MemGPT — Virtual context management](https://arxiv.org/abs/2310.08560)
- [Mem0 — Memory layer for AI](https://mem0.ai/)
