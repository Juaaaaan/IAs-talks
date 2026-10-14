---
type: Concepto
title: "Station — Un paso especializado del workflow"
description: "Paso único del workflow que delega una responsabilidad concreta a un agente con skills específicas, entradas definidas y una salida clara."
tags: [ai-sdlc-foundation, station, workflow, especializacion, delegacion, gate]
related: [ai-sdlc-foundation, workflow, agent, skill-foundation, gate]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Station — Un paso especializado del workflow

> _"Un workflow útil no es una masa continua: se entiende mejor cuando cada tramo tiene oficio y frontera propios."_

---

## Qué es

En AI SDLC Foundation, **Station** es un paso especializado dentro de un [[workflow]] que delega una responsabilidad concreta a un [[agent]] con las [[skill-foundation|skills]] que correspondan. Su valor está en tener una misión clara, una entrada reconocible y una salida que otras piezas puedan consumir. Así el flujo se vuelve componible y cada parte puede evaluarse con más precisión.

---

## Papel en AI SDLC Foundation

Station es la unidad de trabajo intermedia entre el agente individual y el workflow completo. Foundation la usa para descomponer un pipeline en pasos entendibles: implementación, revisión, clasificación, documentación o cualquier otra función especializada. Esta separación facilita que cada estación tenga su propio control de calidad mediante un [[gate]] y que el sistema no mezcle responsabilidades incompatibles en un único bloque opaco.

---

## Cómo funciona

Cada estación recibe una entrada, delega el trabajo a un agente o conjunto acotado de capacidades y produce una salida concreta para el siguiente paso o para el cierre del flujo. Puede tener hooks alrededor y un gate al final, pero su identidad sigue siendo la del trabajo especializado que realiza. El límite esencial es no confundirla con el workflow entero: una estación resuelve un tramo del proceso, no la misión completa de principio a fin.

---

## Ejemplos prácticos

### Ejemplo 1 — Estación de implementación

En un workflow de entrega de cambios, una estación de implementación toma una tarea definida y la delega a un agente que sabe producir el artefacto esperado. Su salida puede ser una propuesta de cambio lista para pasar por validaciones posteriores.

### Ejemplo 2 — Estación de revisión

Otra estación posterior recibe ese resultado y lo somete a revisión técnica o documental. Aquí la responsabilidad cambia: ya no se trata de construir, sino de verificar con criterios y evidencias distintas.

---

## Matices y confusiones habituales

- **Cuidado:** Una estación debe tener responsabilidad y salida claras. Si el paso intenta hacer demasiadas cosas a la vez, el workflow pierde legibilidad y control.
- **Cuidado:** Una station no es el workflow completo. Es solo un tramo especializado dentro de una cadena mayor.
- **Importante:** Que una estación use un agente no significa que ambos conceptos sean equivalentes; el agente es el actor y la estación es el lugar funcional que organiza esa responsabilidad dentro del flujo.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Sitúa la station dentro de la arquitectura general del vocabulario.
- **[[workflow]]** — Es la cadena de estaciones que da orden al proceso completo.
- **[[agent]]** — Ejecuta la responsabilidad concreta que la estación delega.
- **[[skill-foundation]]** — Aporta el conocimiento especializado que la estación puede requerir para funcionar bien.
- **[[gate]]** — Evalúa la salida de la estación antes de dejar pasar el flujo.
