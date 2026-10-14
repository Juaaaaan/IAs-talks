---
type: Concepto
title: "Model Policy — Reglas para asignar capacidad de modelo"
description: "Conjunto de reglas que asigna tiers abstractos de capacidad según el tipo de tarea dentro de AI SDLC Foundation, equilibrando coste, riesgo y profundidad de razonamiento sin fijar marcas concretas."
tags: [ai-sdlc-foundation, model-policy, tier, routing, coste, capacidad]
related: [ai-sdlc-foundation, tier, station, hub-orchestrator, model-routing]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Model Policy — Reglas para asignar capacidad de modelo

> _"No todas las tareas merecen el mismo músculo: la política decide cuánta capacidad conviene gastar en cada una."_

---

## Qué es

En AI SDLC Foundation, **Model Policy** es el conjunto de reglas que decide qué [[tier]] abstracto de capacidad usar según la naturaleza de la tarea. Sirve para gobernar cuándo basta una opción económica y cuándo conviene reservar una capacidad frontier para problemas de mayor ambigüedad o impacto. La política define niveles y criterios, no una marca o versión concreta de modelo.

---

## Papel en AI SDLC Foundation

Model Policy da coherencia a la orquestación cuando distintas [[station]] o un [[hub-orchestrator]] deben enrutar trabajo a capacidades desiguales. Evita que cada workflow decida de forma improvisada qué potencia usar y documenta el criterio operativo para tareas de clasificación, síntesis, revisión o arquitectura. Como mapa general del routing entre modelos, la referencia conceptual amplia sigue siendo [[model-routing]].

---

## Cómo funciona

La política clasifica tipos de tarea o niveles de riesgo y los traduce a tiers abstractos, por ejemplo desde un nivel barato para formato y extracción hasta uno frontier para razonamiento profundo. El runtime o el orquestador aplican esa regla cuando resuelven cada estación del flujo. Su frontera principal es que el coste importa, pero no es el único criterio: también pesan la calidad requerida, la latencia tolerable y el daño potencial de una mala decisión.

---

## Ejemplos prácticos

### Ejemplo 1 — Tier barato para clasificación

Una estación que solo etiqueta tickets, resume campos estructurados o normaliza formato puede seguir una policy que le asigne un tier económico. El objetivo es reservar capacidad cara para tareas donde realmente aporte valor.

### Ejemplo 2 — Tier frontier para arquitectura compleja

Cuando el workflow entra en una decisión arquitectónica con múltiples trade-offs y dependencias, la policy puede exigir un tier frontier. La regla no nombra un modelo exacto, pero sí deja claro que esa clase de trabajo merece máxima profundidad.

---

## Matices y confusiones habituales

- **Cuidado:** Model Policy elige niveles abstractos de capacidad; no debería fijar marcas ni nombres concretos salvo en una capa posterior de mapping.
- **Cuidado:** Optimizar solo por coste puede romper el sistema si abarata tareas donde el error sale mucho más caro que la inferencia.
- **Importante:** Una policy útil necesita criterios estables y observables; si las categorías de tarea son vagas, el routing se vuelve arbitrario.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Ubica la policy dentro de la gobernanza del sistema.
- **[[tier]]** — Es la abstracción que la policy selecciona para cada clase de trabajo.
- **[[station]]** — Ejecuta tareas concretas cuyo nivel de capacidad puede venir determinado por la policy.
- **[[hub-orchestrator]]** — Suele aplicar estas reglas al distribuir trabajo entre etapas o agentes.
- **[[model-routing]]** — Aporta el contexto general sobre estrategias de routing más allá del vocabulario específico de Foundation.
