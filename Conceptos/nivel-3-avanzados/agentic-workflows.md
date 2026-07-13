---
type: Concepto
title: "Agentic Workflows — Flujos de trabajo con agentes"
description: "Patrones donde los agentes de IA no solo responden preguntas sino que ejecutan flujos completos de trabajo: planifican, actúan, verifican y corrigen de forma autónoma."
tags: [agentic, workflows, agentes, autonomia, orquestacion]
related: [function-calling, mcp, agentes-multiples, orchestration-patterns, planning-reasoning]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Agentic Workflows — Flujos de trabajo con agentes

> _"Un chatbot contesta. Un agente trabaja. Un agentic workflow es el trabajo completo."_

---

## Qué es

Un **agentic workflow** es un flujo donde un agente de IA ejecuta una tarea completa de forma autónoma o semi-autónoma, siguiendo un ciclo de:

1. **Planificar** — descomponer la tarea en pasos
2. **Actuar** — ejecutar cada paso usando herramientas
3. **Observar** — evaluar el resultado
4. **Corregir** — ajustar si algo salió mal

---

## Diferencia con un prompt simple

| Prompt simple | Agentic Workflow |
|---|---|
| Una pregunta → una respuesta | Una tarea → un proceso completo |
| Sin herramientas | Usa herramientas reales (APIs, ficheros, CLI) |
| Sin verificación | Verifica su propio trabajo |
| Interacción puntual | Flujo multi-paso autónomo |

---

## Ejemplo real

```
Tarea: "Implementa la RCA-20"

Agentic workflow:
1. Lee el spec.md para entender qué construir
2. Lee copilot-instructions.md para saber las convenciones
3. Genera los componentes Angular
4. Ejecuta los tests
5. Si fallan → lee el error → corrige → vuelve a ejecutar
6. Cuando pasan → crea el commit
```

---

## Niveles de autonomía

```
Nivel 0: Chatbot         → solo responde texto
Nivel 1: Tool use        → responde + usa 1 herramienta
Nivel 2: Agent           → planifica + usa N herramientas
Nivel 3: Agentic workflow → ejecuta flujo completo con verificación
Nivel 4: Multi-agent     → varios agentes coordinados
```

---

## Riesgos

- **Sin supervisión:** El agente puede tomar decisiones erróneas en cadena
- **Loops infinitos:** Si la corrección no converge, puede ejecutarse indefinidamente
- **Costes:** Cada paso consume tokens — flujos largos pueden ser costosos
- **Human in the loop:** La mayoría de flujos necesitan aprobación en puntos clave

---

## Relación con otras piezas

- **[[function-calling]]** — La base técnica que permite a los agentes actuar
- **[[mcp]]** — El protocolo que conecta agentes con herramientas
- **[[agentes-multiples]]** — Patrón developer/reviewer es un agentic workflow
- **[[orchestration-patterns]]** — Cómo se coordinan los agentes dentro del flujo
- **[[planning-reasoning]]** — La capacidad de planificar es clave para workflows complejos

---

## Referencias

- [Andrew Ng — Agentic Design Patterns](https://www.deeplearning.ai/the-batch/how-agents-can-improve-llm-performance/)
- [LangChain — Agent architectures](https://python.langchain.com/docs/concepts/agents/)
