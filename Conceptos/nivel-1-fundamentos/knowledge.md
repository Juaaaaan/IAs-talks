---
type: Concepto
title: "Knowledge — La biblioteca de referencia"
description: "Biblioteca fundacional de principios, políticas, playbooks y guías de marca que informa el trabajo del agente. Aporta criterio reusable, pero no ejecuta acciones por sí sola."
tags: [ai-sdlc-foundation, knowledge, biblioteca, politicas, playbooks, template]
related: [ai-sdlc-foundation, skill-foundation, context, template, wiki-llm]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Knowledge — La biblioteca de referencia

> _"Antes de actuar, el agente necesita saber qué principios del equipo debe respetar."_

---

## Qué es

En AI SDLC Foundation, **Knowledge** es la biblioteca reusable que recoge principios, políticas, playbooks, guías de marca y demás referencia estable. No está pensada para iniciar tareas por sí misma, sino para informar cómo se deben resolver. Es la capa donde el equipo encapsula criterio que conviene reutilizar más allá de una sesión concreta.

---

## Papel en AI SDLC Foundation

Knowledge aporta sustancia a otras piezas del sistema. Una [[skill-foundation]] puede apoyarse en esta biblioteca para decidir cómo revisar seguridad, y una [[template]] puede reflejar su estructura recomendada en la salida final. Foundation la necesita para que los agentes no improvisen políticas, tono o estándares cada vez desde cero.

---

## Cómo funciona

El runtime expone documentos o fragmentos de referencia que el agente puede consultar cuando una tarea lo requiere. Esa información puede alimentar una skill, una plantilla o una validación, pero sigue siendo conocimiento declarativo, no un motor de ejecución. Su frontera más importante es temporal: conviene diferenciar los hechos vigentes que el equipo debe seguir de los ejemplos históricos que solo sirven para aprender.

---

## Ejemplos prácticos

### Ejemplo 1 — Política de seguridad

Un documento de Knowledge define requisitos mínimos sobre gestión de secretos, revisión de permisos y tratamiento de datos sensibles. Cuando una skill de seguridad se activa, usa esa política como referencia para evaluar la tarea con criterios del equipo.

### Ejemplo 2 — Guía de voz de marca

Otra pieza de Knowledge recoge tono, vocabulario permitido y ejemplos de copy para entregables externos. Un agente que redacta una propuesta o una ADR pública consulta esa guía para no mezclar estilos inconsistentes.

---

## Matices y confusiones habituales

- **Cuidado:** Knowledge informa decisiones, pero no ejecuta acciones. Necesita combinarse con agentes, skills o workflows para producir trabajo.
- **Cuidado:** Los ejemplos dentro de la biblioteca no siempre son norma vigente. Hay que separar claramente referencia actual de material ilustrativo.
- **Importante:** Si la biblioteca no se mantiene al día, el agente puede obedecer políticas ya superadas con total coherencia y aun así equivocarse.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Coloca Knowledge dentro del mapa general del sistema.
- **[[skill-foundation]]** — Reutiliza esta biblioteca como conocimiento experto empaquetado.
- **[[context]]** — Puede catalogar qué referencias están disponibles en cada runtime.
- **[[template]]** — Se apoya en Knowledge para estructurar entregables coherentes.
- **[[wiki-llm]]** — Conecta esta biblioteca con la idea de una base de conocimiento navegable por agentes.
