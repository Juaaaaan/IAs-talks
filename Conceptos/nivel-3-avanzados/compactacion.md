---
type: Concepto
title: "Compactación — Resumir el contexto para poder seguir"
description: "Sustituir parte del historial de una sesión por una versión condensada para liberar espacio y reducir ruido. Siempre existe el riesgo de perder un detalle importante."
tags: [compactacion, compaction, contexto, resumen, agentes]
related: [context-window-management, context-rot, memory, subagentes, token]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Compactación

> _"Es tomar notas y recoger la mesa, sabiendo que lo que no apuntes quizá se pierda."_

---

## Qué es

La **compactación** sustituye historial antiguo por un **resumen** para continuar una tarea larga sin arrastrarlo todo. Algunas herramientas la hacen automáticamente y otras permiten pedirla.

> [[context-window-management]] cubre **todas las estrategias** para gestionar la ventana. Esta nota profundiza en **una**.

---

## Qué conviene conservar

| Conservar | Normalmente prescindible |
|---|---|
| Objetivo y criterios de éxito | Salidas largas ya analizadas |
| Decisiones y sus motivos | Intentos intermedios sin información útil |
| Restricciones e instrucciones | Texto repetido |
| Estado actual y pendientes | Conversación lateral |
| Lo que **no funcionó** | |

---

## El riesgo

Un resumen **pierde información**. Una excepción, una cifra exacta o una prohibición pueden desaparecer o deformarse, y el agente seguirá como si nada.

---

## Buenas prácticas

1. Guarda lo crítico **fuera del chat**, en un fichero que se pueda releer
2. Compacta al **cerrar una fase**, si puedes elegir el momento
3. **Revisa el resumen** si la herramienta lo muestra
4. Ante la duda, vuelve a la **fuente original**

---

## Relación con otras piezas

- **[[context-rot]]** — Uno de los problemas que intenta mitigar
- **[[memory]]** — Información que persiste más allá del contexto actual
- **[[subagentes]]** — Otra forma de proteger el contexto principal
- **[[token]]** — La unidad que se ahorra
