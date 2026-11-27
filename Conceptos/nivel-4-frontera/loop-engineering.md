---
type: Concepto
title: "Loop engineering — Diseñar el ciclo, no cada petición"
description: "Práctica de diseñar sistemas que invocan a agentes de forma repetida, según un horario o un evento, con criterios de verificación y parada. El término se popularizó en junio de 2026."
tags: [loop-engineering, bucles, agentes, automatizacion, frontera]
related: [bucle-agentico, ai-harness-engineering, context-engineering, gate, eval-benchmarking, human-in-the-loop]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Loop engineering

> _"En vez de pedirle cada paso al agente, diseñas quién se lo pide, cuándo y hasta cuándo."_

---

## Qué es

El **loop engineering** consiste en diseñar **estructuras automáticas** que lanzan agentes repetidamente. Los agentes en bucle existían antes; el nombre se acuñó a principios de **junio de 2026**. Es un término reciente: su definición todavía puede cambiar.

---

## Dónde se sitúa

| Disciplina | Se ocupa de |
|---|---|
| Prompt engineering | Qué le dices al modelo |
| [[context-engineering]] | Qué información ve |
| [[ai-harness-engineering]] | El entorno, límites y herramientas que lo rodean |
| **Loop engineering** | El ciclo que lo mantiene trabajando hacia un objetivo |

Se complementan: una capa no elimina las anteriores.

---

## Preguntas de diseño

1. **¿Qué lo dispara?** Un horario o un evento
2. **¿Cómo sabe que ha terminado?** Un criterio verificable
3. **¿Quién comprueba?** Mejor algo independiente de quien hace el trabajo
4. **¿Cuándo se detiene?** Límites de intentos, tiempo y coste
5. **¿Cuándo avisa a una persona?**
6. **¿Qué estado guarda** entre vueltas?

---

## Ejemplo práctico

Cuando falla una integración, se lanza un agente que propone una corrección, se ejecutan las comprobaciones y una persona revisa antes de integrar.

**Riesgo:** un bucle mal definido puede gastar mucho y repetir errores sin que nadie mire.

---

## Relación con otras piezas

- **[[bucle-agentico]]** — El ciclo interno de un agente
- **[[ai-harness-engineering]]** — La capa sobre la que se apoya
- **[[gate]]** — Decidir si el resultado avanza
- **[[eval-benchmarking]]** — Medir si el bucle funciona
- **[[human-in-the-loop]]** — Cuándo interviene una persona

---

## Referencias

- [Loop Engineering: Building Blocks, Adoption, and Impact](https://arxiv.org/pdf/2608.21884)
