---
type: Concepto
title: "Gate — El punto de control de calidad"
description: "Checkpoint al final de una estación que interpreta la evidencia disponible y decide si el flujo queda en pass, warn o block dentro de AI SDLC Foundation."
tags: [ai-sdlc-foundation, gate, calidad, checkpoint, control, workflow]
related: [ai-sdlc-foundation, station, hook, trace, workflow, hooks-approval-gates]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Gate — El punto de control de calidad

> _"No basta con ejecutar un paso: en algún momento alguien tiene que decidir si el resultado deja pasar, avisa o bloquea."_

---

## Qué es

En AI SDLC Foundation, **Gate** es el checkpoint de calidad que se evalúa al final de una [[station]] para decidir si el flujo puede seguir, si conviene continuar con señal de cautela o si debe detenerse. Sus salidas conceptuales son **pass**, **warn** o **block**. No es la comprobación en sí, sino el punto donde esa evidencia se interpreta como decisión operativa.

---

## Papel en AI SDLC Foundation

Gate introduce control explícito dentro del [[workflow]]. Ayuda a que cada estación no solo produzca una salida, sino también una evaluación comprensible sobre su calidad o riesgo. Foundation lo necesita para evitar que todo avance por inercia aunque una validación crítica haya fallado y para dejar rastro en [[trace]] de por qué un flujo siguió o se detuvo.

---

## Cómo funciona

Al cerrar una estación, el sistema reúne la evidencia relevante de tests, revisión, validaciones automáticas u otras comprobaciones y la convierte en un veredicto. **Pass** permite avanzar sin reservas; **warn** deja continuar, pero conserva una señal explícita de que existe una desviación o riesgo; **block** corta el flujo hasta que alguien resuelva el problema. La frontera importante es que el gate decide sobre calidad y continuación, aunque la evidencia la hayan producido otras piezas.

---

## Ejemplos prácticos

### Ejemplo 1 — Gate de tests

Una estación de implementación termina y se revisa si la evidencia de tests permite promover el cambio. Si todo está en orden, el gate queda en pass; si hay un aviso menor documentado, puede quedar en warn; si falla una validación crítica, pasa a block.

### Ejemplo 2 — Gate de revisión de seguridad

En un flujo sensible, una estación de revisión de seguridad emite hallazgos y el gate traduce ese resultado a una decisión operativa. Un riesgo severo puede bloquear el workflow, mientras que una observación no crítica puede dejar una advertencia explícita sin detener todo el proceso.

---

## Matices y confusiones habituales

- **Cuidado:** Un gate no ejecuta la comprobación. Evalúa la calidad de la salida y decide pass, warn o block a partir de la evidencia disponible.
- **Cuidado:** Un warn no equivale a "todo bien". Permite continuar, pero dejando señal de que hay algo que conviene revisar o aceptar conscientemente.
- **Importante:** No conviene confundir gate con [[hook]]. El hook ejecuta una comprobación antes o después de la estación; el gate interpreta el resultado al final del paso.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Da contexto al gate como mecanismo de control dentro del sistema.
- **[[station]]** — Define el lugar del flujo donde el checkpoint se evalúa.
- **[[hook]]** — Puede producir parte de la evidencia que el gate usará para decidir.
- **[[trace]]** — Registra el veredicto y su efecto sobre la trazabilidad del proceso.
- **[[workflow]]** — Encadena estaciones cuyos gates determinan cómo avanza o se detiene el pipeline.
- **[[hooks-approval-gates]]** — Nota general del vault sobre checkpoints de aprobación; Gate aterriza esa idea al vocabulario de Foundation.
