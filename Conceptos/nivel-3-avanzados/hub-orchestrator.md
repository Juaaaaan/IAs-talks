---
type: Concepto
title: "Hub Orchestrator — El agente central de triaje"
description: "Agente central que clasifica la intención recibida y despacha la petición al workflow adecuado sin asumir que ejecutará personalmente todas las estaciones."
tags: [ai-sdlc-foundation, hub-orchestrator, triaje, routing, workflow, model-policy]
related: [ai-sdlc-foundation, prompt, workflow, model-policy, orchestration-patterns]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Hub Orchestrator — El agente central de triaje

> _"Cuando llegan muchas intenciones posibles, alguien tiene que decidir a qué circuito mandar cada una."_

---

## Qué es

En AI SDLC Foundation, **Hub Orchestrator** es el agente central que recibe una intención, la clasifica y la despacha al [[workflow]] más adecuado. Su papel se parece al de una capa de triaje: entender qué tipo de petición ha llegado y derivarla hacia el circuito correcto. No se define por ejecutar cada paso, sino por enrutar con criterio.

---

## Papel en AI SDLC Foundation

Hub Orchestrator evita que cada punto de entrada tenga que conocer todos los flujos disponibles. Un [[prompt]] puede invocarlo como puerta única y dejar que él determine si la petición corresponde a revisión, documentación, análisis o cualquier otra capacidad instalada. En Foundation esta pieza coordina el enrutamiento y puede apoyarse en [[model-policy]] para decidir con qué capacidad conviene clasificar o qué ruta merece más profundidad.

---

## Cómo funciona

El orquestador recibe una entrada, interpreta la intención y la compara con los workflows que el sistema tiene disponibles. Si detecta una petición de revisión, la envía al flujo de review; si identifica una necesidad documental, la deriva al circuito correspondiente. Su límite es importante: puede arrancar, delegar y supervisar, pero no hace falta que ejecute personalmente todas las estaciones de cada ruta. Una mala clasificación no rompe solo el inicio; puede dirigir toda la petición al flujo equivocado.

---

## Ejemplos prácticos

### Ejemplo 1 — Enrutar una petición de PR review

Un usuario invoca una entrada genérica y describe que quiere revisar un pull request. El hub interpreta la intención y manda la solicitud al workflow preparado para revisión técnica, en lugar de tratarla como generación de documentación o soporte general.

### Ejemplo 2 — Enviar una petición de ADR al workflow documental

Otra petición pide formalizar una decisión arquitectónica. El orquestador reconoce que no corresponde a un circuito de implementación, sino a uno documental, y la deriva al workflow que trabaja con plantillas y criterios editoriales de ADR.

---

## Matices y confusiones habituales

- **Cuidado:** Un hub-orchestrator no es simplemente "otro agente que hace de todo". Su responsabilidad central es clasificar y delegar, no absorber necesariamente todas las estaciones.
- **Cuidado:** El enrutamiento correcto depende de la calidad del triaje. Si clasifica mal la intención, el sistema puede trabajar de forma impecable... en el flujo equivocado.
- **Importante:** No conviene inventar aquí mecanismos cerrados de clasificación o un patrón único de coordinación. El concepto es el rol central de enrutamiento, no una implementación concreta.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Coloca el orquestador dentro del mapa operativo completo.
- **[[prompt]]** — Suele ser la entrada que entrega al hub una intención inicial para clasificar.
- **[[workflow]]** — Es el destino que el hub selecciona y pone en marcha.
- **[[model-policy]]** — Puede aportar criterio sobre qué nivel de capacidad usar en clasificación o delegación.
- **[[orchestration-patterns]]** — Amplía la conversación sobre supervisor, pipeline y otros patrones de coordinación.
