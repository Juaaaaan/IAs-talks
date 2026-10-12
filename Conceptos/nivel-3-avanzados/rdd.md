---
type: Concepto
title: "RDD — Receipt-Driven Development"
description: "Modelo de profundidad para la revisión de código con IA: tres niveles (pasivo, medio, alto/4R — Risk, Resilience, Readability, Reliability)"
tags: [rdd, code-review, revision, gentle-ai, calidad]
related: [ai-code-review, odd, bdd]
charla: "Pendiente — charla futura de ai-code-review"
estado: "borrador"
timestamp: "2026-10-14"
---

# RDD — Receipt-Driven Development

> _"Verifying beats generating."_ — Alan Buscaglia, Gentleman Programming

---

## Qué es

RDD es un modelo de profundidad para la revisión de código asistida por IA, del framework [gentle-ai](https://github.com/Gentleman-Programming/gentle-ai). Define **cuánto** se revisa, no solo si se revisa, con tres niveles crecientes:

| Nivel | Qué cubre |
|---|---|
| **Pasivo** | Lectura superficial — ¿compila, pasa lint, pasa tests? |
| **Medio** | Revisión funcional — ¿hace lo que el ticket pedía? |
| **Alto ("4R")** | Las cuatro dimensiones completas: **Risk** (riesgo de lo que cambia), **Resilience** (qué pasa si falla), **Readability** (¿lo entendería otra persona dentro de seis meses?), **Reliability** (¿es fiable bajo carga, datos raros, condiciones límite?) |

---

## Por qué importa

No toda PR necesita el nivel alto. RDD da un vocabulario para decidir **a propósito** cuánta revisión merece cada cambio, en vez de aplicar siempre el mismo nivel por costumbre o por prisa.

---

## Relación con el resto del arnés

- **[[ai-code-review]]** — RDD es un modelo de profundidad *dentro* de esa etapa de revisión; no sustituye la capa de checks deterministas ni el review humano reservado a lo crítico, define cuánto deben profundizar
- **[[odd]]** — ODD nunca activa RDD por sí solo; son interruptores separados. Clasificar un cambio como "sustancial" en ODD no implica automáticamente una revisión de nivel 4R
- **[[bdd]]** — un escenario Gherkin es el criterio que una revisión de nivel medio/alto puede usar para comprobar el resultado

---

## Estado en la serie

Deliberadamente **no** se introdujo en la Charla 23 — se reservó junto con la demo de ai-code-review para una charla futura dedicada, para que llegue con tiempo propio en vez de como cierre apresurado.

## Dónde aparecerá en la serie

| Charla | Rol previsto |
|---|---|
| Futura (ai-code-review) | Framework de profundidad para estructurar esa charla y su demo |

---

## Referencias

- [gentle-ai — docs](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/usage.md)
