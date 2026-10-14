---
type: Concepto
title: "Prompt — La entrada ejecutable por slash command"
description: "Punto de entrada ejecutable, normalmente en forma de slash command, que inicia un workflow o una tarea independiente. Define cómo arranca el flujo, no todo lo que ocurrirá después."
tags: [ai-sdlc-foundation, prompt, slash-command, workflow, runtime, entrada]
related: [ai-sdlc-foundation, workflow, hub-orchestrator, runtime, system-prompt]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Prompt — La entrada ejecutable por slash command

> _"Aquí prompt no es cualquier frase: es el gatillo que pone a trabajar al sistema."_

---

## Qué es

En AI SDLC Foundation, **Prompt** es un punto de entrada ejecutable que suele expresarse como slash command y sirve para arrancar un workflow o una tarea aislada. Su papel no es describir todo el sistema, sino ofrecer una invocación clara y repetible. Por eso este término es más cercano a un comando de arranque que al prompting general de un chat.

---

## Papel en AI SDLC Foundation

Prompt simplifica la activación del sistema para el usuario final o para otro agente. En lugar de reconstruir manualmente un flujo completo, basta con invocar una entrada conocida y dejar que el [[workflow]] o el [[hub-orchestrator]] continúen el trabajo dentro del [[runtime]]. Es la pieza que convierte una capacidad disponible en una acción iniciable.

---

## Cómo funciona

El runtime registra prompts ejecutables y los asocia a una lógica posterior: qué workflow se lanza, qué plantilla se prepara o qué skill se carga primero. Cuando alguien invoca el slash command, el sistema resuelve ese punto de entrada y encadena los pasos que correspondan. El límite clave es que el prompt inicia el flujo, pero no sustituye la definición detallada de todo el proceso interno.

---

## Ejemplos prácticos

### Ejemplo 1 — `/review-pr`

Un equipo expone `/review-pr` como prompt de entrada para disparar un workflow de revisión. El usuario invoca el comando y el runtime ya sabe qué estaciones, skills y validaciones deben seguir.

### Ejemplo 2 — `/create-adr`

Otro prompt activa la creación de una ADR con su plantilla y su circuito de aprobación. El comando abre la puerta, pero el contenido final dependerá del workflow y del conocimiento disponible.

---

## Matices y confusiones habituales

- **Cuidado:** Este prompt no equivale a cualquier mensaje libre del usuario. Está pensado como entrada ejecutable y nominal.
- **Cuidado:** Iniciar un flujo no define todos sus pasos. La orquestación detallada pertenece al workflow o al hub que toma el relevo.
- **Importante:** Un nombre de slash command puede ser memorable y aun así confuso si no deja claro qué tarea autónoma dispara.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Da contexto al papel de los prompts dentro del dominio completo.
- **[[workflow]]** — Suele ser el destino inmediato que el prompt pone en marcha.
- **[[hub-orchestrator]]** — Puede enrutar o decidir qué flujo ejecutar a partir de la entrada recibida.
- **[[runtime]]** — Registra y resuelve el prompt ejecutable en tiempo de uso.
- **[[system-prompt]]** — Ayuda a diferenciar esta noción Foundation del prompting general y del contexto base del modelo.
