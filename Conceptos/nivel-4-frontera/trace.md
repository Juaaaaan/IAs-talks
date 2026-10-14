---
type: Concepto
title: "Trace — El registro estructurado de auditoría"
description: "Registro estructurado emitido por cada estación para dejar trazabilidad y auditoría sobre entradas, decisiones, resultados y checkpoints del flujo."
tags: [ai-sdlc-foundation, trace, auditoria, trazabilidad, station, workflow]
related: [ai-sdlc-foundation, station, gate, workflow, ai-governance]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Trace — El registro estructurado de auditoría

> _"Si un workflow toma decisiones importantes, luego tiene que poder explicar qué ocurrió y en qué orden."_

---

## Qué es

En AI SDLC Foundation, **Trace** es el registro estructurado que deja cada [[station]] para hacer posible la trazabilidad y la auditoría del flujo. Su función es conservar evidencia suficiente sobre qué agente intervino, qué entradas relevantes recibió, qué resultado produjo y qué checkpoints afectaron al recorrido. No pretende ser memoria creativa del agente, sino huella operativa del proceso.

---

## Papel en AI SDLC Foundation

Trace conecta la ejecución con la gobernanza. Hace visible cómo avanzó un [[workflow]], qué gates se evaluaron y por qué un resultado quedó aprobado, advertido o bloqueado. Foundation lo necesita para revisión posterior, análisis de incidentes y explicabilidad mínima del sistema, especialmente cuando la conversación sobre control y responsabilidad se amplía hacia [[ai-governance]].

---

## Cómo funciona

Cada estación emite un registro con la información relevante de su paso y ese rastro se acumula a lo largo del workflow. El objetivo es que después pueda reconstruirse el recorrido sin depender solo de logs libres o del recuerdo de un agente. La frontera clave es no convertir esta nota conceptual en un contrato de datos inventado: Trace implica estructura y consistencia, pero aquí no hace falta afirmar un esquema concreto que la implementación real no haya definido.

---

## Ejemplos prácticos

### Ejemplo 1 — Registrar agente, entradas y resultado

Una estación deja constancia de qué agente realizó el trabajo, qué material recibió como entrada y qué salida produjo. Esa información permite revisar después si la responsabilidad y los insumos fueron los adecuados para el resultado obtenido.

### Ejemplo 2 — Registrar gates y timestamps

Otra parte del trace recoge cuándo terminó una estación y qué gate quedó en pass, warn o block. Con ese rastro resulta más fácil entender por qué el flujo siguió adelante o en qué punto se detuvo.

---

## Matices y confusiones habituales

- **Cuidado:** Trace no es solo un log libre. Necesita suficiente estructura para que el recorrido del workflow pueda revisarse y compararse con criterio.
- **Cuidado:** Trace tampoco es la memoria interna del agente. Registra el proceso observable, no todo el razonamiento privado o contextual que el agente haya tenido.
- **Importante:** No conviene afirmar formatos, campos obligatorios exhaustivos o mecanismos concretos si la implementación real aún no los ha fijado.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Sitúa el trace como parte de la disciplina operativa del sistema.
- **[[station]]** — Es la unidad que emite los registros parciales del recorrido.
- **[[gate]]** — Aporta decisiones de control cuya huella conviene conservar en el rastro auditable.
- **[[workflow]]** — Acumula los traces de sus estaciones para explicar el proceso completo.
- **[[ai-governance]]** — Amplía la dimensión de auditoría, control y responsabilidad sobre sistemas de IA.
