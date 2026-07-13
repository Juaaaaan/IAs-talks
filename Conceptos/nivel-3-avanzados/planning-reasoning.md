---
type: Concepto
title: "Planning & Reasoning — Planificación y razonamiento"
description: "Capacidad de los LLMs de descomponer problemas complejos en pasos, razonar sobre ellos y elegir estrategias. Fundamental para tareas que no se resuelven en un solo paso."
tags: [planning, reasoning, razonamiento, descomposicion, agentes, estrategia]
related: [chain-of-thought, agentic-workflows, orchestration-patterns]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Planning & Reasoning — Planificación y razonamiento

> _"La diferencia entre un agente útil y uno peligroso es su capacidad de planificar antes de actuar."_

---

## Qué es

**Planning** es la capacidad de un agente de descomponer una tarea compleja en subtareas ejecutables antes de empezar a actuar.

**Reasoning** es la capacidad de evaluar opciones, considerar consecuencias y elegir la mejor estrategia.

Juntos, permiten que un agente no solo ejecute instrucciones literales, sino que entienda el problema y diseñe un plan.

---

## Sin planning vs con planning

| Sin planning | Con planning |
|---|---|
| "Implementa todo de golpe" | "Primero leo el spec, luego diseño, luego implemento" |
| Se pierde en tareas complejas | Descompone y avanza paso a paso |
| No prioriza | Identifica dependencias y orden |
| Si falla, no sabe por qué | Si falla, sabe en qué paso y reintenta |

---

## Estrategias de planning

### ReAct (Reasoning + Acting)
```
Pensamiento: Necesito implementar el navbar. Primero leo el spec.
Acción: Leer spec.md
Observación: El spec dice usar el componente HeaderComponent...
Pensamiento: Ahora necesito ver el sistema de diseño...
Acción: Leer design-system.md
...
```

### Plan-and-Execute
```
Plan:
1. Leer especificación
2. Crear componente base
3. Añadir estilos del design system
4. Escribir tests
5. Verificar

Ejecución: Paso 1... ✅ Paso 2... ✅ ...
```

### Tree of Thought
Explorar múltiples caminos de razonamiento en paralelo y elegir el mejor.

---

## Limitaciones actuales

- Los LLMs pueden generar planes que suenan bien pero son inviables
- La planificación consume tokens (y tiempo)
- Los planes largos (10+ pasos) pierden coherencia
- Todavía necesitan supervisión humana en decisiones críticas

---

## Relación con otras piezas

- **[[chain-of-thought]]** — CoT es la base del reasoning paso a paso
- **[[agentic-workflows]]** — Los workflows requieren planning para funcionar
- **[[orchestration-patterns]]** — El planning decide qué patrón de orquestación usar

---

## Referencias

- [ReAct: Synergizing Reasoning and Acting — Yao et al. 2023](https://arxiv.org/abs/2210.03629)
- [Tree of Thoughts — Yao et al. 2023](https://arxiv.org/abs/2305.10601)
