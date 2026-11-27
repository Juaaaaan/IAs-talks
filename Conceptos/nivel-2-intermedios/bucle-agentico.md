---
type: Concepto
title: "Bucle agéntico — Actuar, observar y volver a decidir"
description: "Ciclo por el que un agente decide un paso, usa una herramienta, observa el resultado y elige el siguiente, hasta cumplir el objetivo o alcanzar un límite."
tags: [bucle-agentico, agent-loop, agentes, herramientas, autonomia]
related: [agente-ia, function-calling, planning-reasoning, loop-engineering, agentic-workflows, human-in-the-loop]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Bucle agéntico

> _"Un chat contesta. Un agente prueba, mira qué ha pasado y sigue."_

---

## Qué es

El **bucle agéntico** es el ciclo que permite a un agente avanzar por pasos:

```
Objetivo
  ↓
Decidir el siguiente paso → Usar una herramienta → Observar el resultado
  ↑                                                       │
  └────────────── ¿Terminado? No ←────────────────────────┘
                       Sí → Entregar
```

---

## Piezas que lo hacen funcionar

| Pieza | Función |
|---|---|
| **Modelo** | Decide el siguiente paso |
| **Herramientas** | Permiten buscar, leer, ejecutar o escribir |
| **Observación** | El resultado real vuelve al contexto |
| **Condición de parada** | Cuándo se da por terminado |
| **Límites** | Máximo de pasos, tiempo, coste y permisos |

---

## Ejemplo práctico

*"Corrige el test que falla"*: el agente lee el error, abre el fichero, hace un cambio, ejecuta el test y, si sigue fallando, prueba otra vez con la nueva información.

---

## Qué puede salir mal

- Repetir el mismo intento sin avanzar
- Darse por terminado sin haberlo comprobado
- Cumplir la comprobación **haciendo trampas**, por ejemplo modificando el test

Por eso importan los **criterios de éxito verificables** y los límites.

---

## Relación con otras piezas

- **[[function-calling]]** — Cómo el modelo pide usar una herramienta
- **[[planning-reasoning]]** — Cómo organiza los pasos
- **[[loop-engineering]]** — Diseñar bucles que se repiten y se disparan solos
- **[[human-in-the-loop]]** — Puntos de aprobación dentro del ciclo

---

## Referencias

- [ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629)
