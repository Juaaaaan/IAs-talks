---
type: Concepto
title: "Workflow — El flujo de trabajo multiestación"
description: "Flujo de trabajo de varias estaciones que coordina agentes, orden, entradas, salidas y checkpoints para entregar un resultado completo dentro de AI SDLC Foundation."
tags: [ai-sdlc-foundation, workflow, pipeline, orquestacion, station, gate]
related: [ai-sdlc-foundation, station, hub-orchestrator, gate, agentic-workflows]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Workflow — El flujo de trabajo multiestación

> _"La capacidad real no vive en un paso aislado, sino en el recorrido entero que coordina quién hace qué y en qué orden."_

---

## Qué es

En AI SDLC Foundation, **Workflow** es un flujo de trabajo de varias [[station]]es que coordina agentes y checkpoints para entregar un resultado completo. Define cómo se encadenan los pasos, qué entrada necesita cada tramo y qué salida debe producir antes de pasar al siguiente. No es una sola acción ni un único agente, sino la coreografía del trabajo de principio a fin.

---

## Papel en AI SDLC Foundation

Workflow es la pieza que convierte capacidades sueltas en un proceso operativo repetible. Permite que agentes, skills, hooks y gates cooperen bajo un orden común en lugar de aparecer como recursos aislados. En Foundation también sirve como destino natural de un [[hub-orchestrator]] o de un [[prompt]], y conversa con la noción más amplia de [[agentic-workflows]] sin perder el foco en este vocabulario específico.

---

## Cómo funciona

Un workflow define estaciones, secuencia, entradas esperadas, salidas intermedias y checkpoints de control. A medida que avanza, delega responsabilidades a agentes especializados y registra el recorrido relevante para poder revisarlo después. Su límite principal es semántico: si el flujo no deja claro el orden, las transiciones y los puntos de control, deja de ser un workflow entendible y se convierte en una colección confusa de acciones.

---

## Ejemplos prácticos

### Ejemplo 1 — Workflow de feature desde spec hasta review

Un flujo de trabajo puede arrancar en una estación que interpreta una spec, continuar con implementación y cerrar con revisión y gates de calidad. El valor no está en un paso individual, sino en la coordinación completa que lleva de intención a resultado validado.

### Ejemplo 2 — Workflow de análisis de incidente

Otro flujo recibe una incidencia, la clasifica, recopila evidencia, propone explicación y deja una salida revisable para el equipo. Cada estación cumple una función distinta, pero juntas forman un proceso repetible para responder mejor ante incidentes.

---

## Matices y confusiones habituales

- **Cuidado:** Un workflow no es una sola acción. Si todo cabe en un único acto sin coordinación entre pasos, probablemente no estamos ante este concepto.
- **Cuidado:** Workflow tampoco es sinónimo de agente. El agente ejecuta responsabilidades concretas; el workflow organiza varias responsabilidades dentro de una secuencia coherente.
- **Importante:** Un flujo útil debe definir orden, entradas, salidas y checkpoints. Sin esos elementos, la orquestación queda implícita y se vuelve difícil de auditar o reutilizar.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Coloca el workflow como eje de coordinación del sistema.
- **[[station]]** — Son los pasos especializados que componen el pipeline.
- **[[hub-orchestrator]]** — Puede clasificar la intención inicial y despachar la petición a este flujo.
- **[[gate]]** — Introduce los checkpoints que determinan cómo progresa o se detiene el proceso.
- **[[agentic-workflows]]** — Aporta el contexto general sobre flujos de trabajo con agentes más allá de Foundation.
