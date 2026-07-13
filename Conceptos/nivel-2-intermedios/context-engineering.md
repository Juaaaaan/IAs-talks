---
type: Concepto
title: "Context Engineering — Diseño del contexto para IA"
description: "Disciplina de diseñar todo lo que la IA necesita para trabajar bien: instrucciones, documentos, ejemplos, memoria, herramientas y formato de salida. La evolución natural del prompting."
tags: [context-engineering, contexto, prompting, instrucciones, agentes]
related: [copilot-instructions, arnes-completo, rag, wiki-llm, system-prompt]
estado: "✅ Publicado"
timestamp: "2026-07-09"
---

# Context Engineering — Diseño del contexto para IA

> _"No es solo escribir un buen prompt — es preparar todo lo que la IA necesita para hacer bien su trabajo."_

---

## Qué es

**Context Engineering** es la disciplina de diseñar el contexto completo que un agente de IA necesita para producir resultados útiles. Va mucho más allá de escribir un prompt:

- Qué instrucciones recibe (system prompt, rules)
- Qué documentos puede consultar (RAG, wiki)
- Qué ejemplos tiene disponibles (few-shot)
- Qué herramientas puede usar (MCPs, function calling)
- Qué memoria retiene entre sesiones
- Qué formato debe devolver

---

## Prompting vs Context Engineering

| Prompting | Context Engineering |
|---|---|
| Un prompt bien escrito | Todo el entorno del agente |
| Esfuerzo puntual | Diseño sistemático |
| "Dame una buena respuesta" | "Aquí tienes todo para trabajar bien" |
| Una sola interacción | Arquitectura de múltiples capas |

---

## Las capas del contexto

```
┌─────────────────────────────────────────┐
│  System Prompt (identidad, reglas)  │
├─────────────────────────────────────────┤
│  Instrucciones persistentes         │
│  (copilot-instructions, CLAUDE.md)  │
├─────────────────────────────────────────┤
│  Documentos relevantes (RAG/Wiki)   │
├─────────────────────────────────────────┤
│  Ejemplos (few-shot)                │
├─────────────────────────────────────────┤
│  Herramientas disponibles (MCPs)    │
├─────────────────────────────────────────┤
│  Memoria (historial, estado)        │
├─────────────────────────────────────────┤
│  Prompt del usuario                 │
└─────────────────────────────────────────┘
```

---

## Ejemplo práctico

El **arnés completo** de esta serie es un ejercicio de context engineering:

- **SDD** → documenta qué construir (contexto de especificación)
- **Skills** → define cómo comportarse (contexto de comportamiento)
- **MCPs** → conecta con herramientas (contexto de acción)
- **copilot-instructions** → instrucciones persistentes (contexto de identidad)

---

## Por qué importa

La calidad de la salida de un LLM depende directamente de la calidad de su contexto. Un modelo mediocre con excelente context engineering supera a un modelo excelente con contexto pobre.

---

## Relación con otras piezas

- **[[copilot-instructions]]** — Una capa del context engineering: instrucciones persistentes
- **[[arnes-completo]]** — El arnés es context engineering aplicado a desarrollo
- **[[rag]]** — RAG es una técnica de context engineering para inyectar documentos
- **[[wiki-llm]]** — El Wiki LLM es la fuente de contexto persistente
- **[[system-prompt]]** — El system prompt es la capa más fundamental del contexto

---

## Referencias

- Concepto en glosario: [[glosario-ia-nivel-1]] §29
- [Simon Willison — Context Engineering](https://simonwillison.net/)
