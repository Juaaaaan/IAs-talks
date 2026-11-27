---
type: Concepto
title: "Human-in-the-loop — Una persona decide en los puntos que importan"
description: "Diseño en el que una persona revisa, aprueba o corrige lo que hace la IA antes de que tenga efecto. Solo funciona si quien revisa tiene información, tiempo y capacidad real para decir que no."
tags: [human-in-the-loop, supervision, aprobacion, control, gobernanza]
related: [hooks-approval-gates, gate, guardrails, ai-governance, ai-slop]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Human-in-the-loop

> _"Poner un botón de 'Aprobar' no es supervisar."_

---

## Qué es

**Human-in-the-loop** (HITL) significa que hay una **persona dentro del proceso**, con capacidad de revisar, corregir, aprobar o detener lo que propone la IA antes de que produzca efecto.

---

## Cómo se diferencia de las notas cercanas

| Nota | Qué cubre |
|---|---|
| **Human-in-the-loop** | El principio general: dónde y cómo interviene una persona |
| [[hooks-approval-gates]] | Una forma técnica de forzar la aprobación dentro del flujo |
| [[gate]] | El checkpoint de calidad en el vocabulario de AI SDLC Foundation, que no siempre es humano |

---

## Para que sea real

- La persona ve **qué se va a hacer** y con qué información
- Tiene **tiempo y conocimiento** para juzgarlo
- Puede **rechazarlo** sin que eso sea un problema
- La revisión se concentra **donde el error cuesta más**

---

## El riesgo del "sí" automático

Cuando casi todo sale bien y hay muchas aprobaciones, es fácil acabar aprobando sin leer. Pedir confirmación para todo puede ser tan inútil como no pedirla.

---

## Ejemplo práctico

La IA redacta la respuesta a una reclamación. Antes de enviarla, la persona responsable ve el borrador **junto con la documentación** en la que se basa, y decide si lo envía, lo corrige o lo descarta.

---

## Relación con otras piezas

- **[[hooks-approval-gates]]** — Puertas de aprobación ejecutables
- **[[gate]]** — Checkpoints de calidad de un flujo
- **[[guardrails]]** — Controles automáticos que complementan la revisión
- **[[ai-governance]]** — Define qué decisiones necesitan supervisión
- **[[ai-slop]]** — Lo que se cuela cuando nadie revisa de verdad
