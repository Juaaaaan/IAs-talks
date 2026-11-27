---
type: Concepto
title: "Guardrails — Los quitamiedos de un sistema de IA"
description: "Controles que limitan lo que un sistema de IA puede recibir, responder o hacer. Los hay basados en instrucciones, en filtros y en permisos; no todos ofrecen la misma garantía."
tags: [guardrails, seguridad, controles, filtros, permisos]
related: [system-prompt, prompt-injection, jailbreak, sandbox, hooks-approval-gates, human-in-the-loop]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Guardrails

> _"Una instrucción pide. Un permiso impide."_

---

## Qué son

Los **guardrails** son los controles que ponen límites a un sistema de IA: qué entradas acepta, qué respuestas puede entregar y qué acciones puede ejecutar.

---

## No todos protegen igual

| Tipo | Ejemplo | Garantía |
|---|---|---|
| **Instrucción** | "No des asesoramiento legal" en el system prompt | Orienta, pero se puede incumplir |
| **Filtro de entrada o salida** | Detectar datos personales antes de enviar la respuesta | Ayuda, con falsos positivos y negativos |
| **Validación determinista** | Rechazar una salida que no cumple el formato | Fiable para lo que comprueba |
| **Permisos y aislamiento** | El agente no tiene acceso a borrar registros | Lo impide el sistema, no el criterio del modelo |

---

## Criterio de diseño

Cuanto más grave sea el daño posible, menos conviene depender solo de una instrucción. Combina **varias capas**.

---

## Ejemplo práctico

Un asistente de atención al cliente puede tener la instrucción de no prometer indemnizaciones, un filtro que revise la respuesta y **ninguna herramienta** capaz de aprobar un pago.

---

## Relación con otras piezas

- **[[system-prompt]]** — Donde viven los guardrails basados en instrucciones
- **[[prompt-injection]]** y **[[jailbreak]]** — Ataques que intentan saltárselos
- **[[sandbox]]** — Aislar el entorno donde actúa el agente
- **[[hooks-approval-gates]]** — Controles ejecutables en puntos concretos
- **[[human-in-the-loop]]** — La capa humana
