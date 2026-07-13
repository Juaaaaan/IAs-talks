---
type: Concepto
title: "Orchestration Patterns — Patrones de orquestación de agentes"
description: "Arquitecturas para coordinar múltiples agentes o pasos: pipeline, fan-out, supervisor, swarm. Cada patrón resuelve un tipo diferente de problema."
tags: [orquestacion, patrones, pipeline, fan-out, supervisor, swarm, multi-agente]
related: [agentic-workflows, agentes-multiples, planning-reasoning, function-calling]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Orchestration Patterns — Patrones de orquestación de agentes

> _"Un agente solo puede mucho. Varios agentes coordinados pueden con todo."_

---

## Qué es

Los **orchestration patterns** son arquitecturas que definen cómo se coordinan múltiples agentes (o pasos de un flujo) para completar una tarea compleja.

No hay un patrón universal — cada problema pide una coordinación diferente.

---

## Patrones principales

### 1. Pipeline (secuencial)
```
Agente A → Agente B → Agente C → Resultado
```
Cada agente procesa la salida del anterior. Simple, predecible.

**Ejemplo:** `spec.md → task.md → código → tests → review`

### 2. Fan-out / Fan-in (paralelo)
```
         ┌→ Agente B ─┐
Agente A ├→ Agente C ─┤→ Agente E (combina)
         └→ Agente D ─┘
```
Un agente distribuye subtareas a varios agentes en paralelo y otro combina los resultados.

**Ejemplo:** Analizar 10 ficheros de código en paralelo y combinar los hallazgos.

### 3. Supervisor
```
         Supervisor
        ┌────┼────┐
     Worker Worker Worker
```
Un agente supervisor decide qué worker ejecutar, evalúa resultados y redirige si es necesario.

**Ejemplo:** Un agente coordinador que decide si la tarea la hace el developer o el reviewer.

### 4. Swarm (enjambre)
```
Agente A ↔ Agente B
    ↕            ↕
Agente C ↔ Agente D
```
Los agentes se comunican entre sí sin un coordinador central. Cada uno tiene capacidades diferentes y transfiere la tarea al más adecuado.

**Ejemplo:** OpenAI Swarm — agentes que se pasan el control según su especialización.

### 5. Debate / Crítica
```
Agente A genera → Agente B critica → Agente A mejora → ...
```
Dos agentes iteran: uno genera y otro evalúa, mejorando el resultado en cada ciclo.

**Ejemplo:** El patrón developer/reviewer de esta serie.

---

## Qué patrón elegir

| Situación | Patrón |
|---|---|
| Tarea con pasos claros y ordenados | Pipeline |
| Tarea descomponible en subtareas independientes | Fan-out |
| Tarea compleja que necesita supervisión | Supervisor |
| Múltiples especialistas con handoff | Swarm |
| Calidad crítica | Debate/Crítica |

---

## Relación con otras piezas

- **[[agentic-workflows]]** — Los workflows implementan uno o más de estos patrones
- **[[agentes-multiples]]** — El patrón developer/reviewer es un pipeline + debate
- **[[planning-reasoning]]** — El planning decide qué patrón usar
- **[[function-calling]]** — Cada agente usa function calling para ejecutar acciones

---

## Referencias

- [LangGraph — Multi-agent patterns](https://langchain-ai.github.io/langgraph/)
- [OpenAI Swarm](https://github.com/openai/swarm)
- [Andrew Ng — Agentic Design Patterns](https://www.deeplearning.ai/the-batch/)
