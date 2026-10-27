---
type: Concepto
title: "RDD — Receipt-Driven Development"
description: "Modelo para revisar código generado con IA: vincula evidencia a un candidato congelado, propone la profundidad de revisión (baja/media/alta, con las lentes 4R — Risk, Resilience, Readability, Reliability) y devuelve la decisión de entrega a la persona."
tags: [rdd, code-review, revision, receipt, candidato-congelado, gentle-ai, calidad]
related: [ai-code-review, odd, bdd]
charla: "Charla 24 — Comprobar después de construir (28 oct 2026)"
estado: "borrador"
timestamp: "2026-10-27"
---

# RDD — Receipt-Driven Development

> _"Verifying beats generating."_ — Alan Buscaglia, Gentleman Programming

---

## Qué es

RDD es un enfoque para revisar código asistido por IA, del framework [gentle-ai](https://github.com/Gentleman-Programming/gentle-ai). La palabra clave no es *review*, es **receipt** (recibo): una revisión útil no termina en "el agente dice que está bien". Debe dejar constancia de qué candidato exacto se revisó, qué comprobaciones se hicieron, qué evidencia se obtuvo, qué hallazgos quedaron abiertos y quién conserva la autoridad de entrega.

RDD no decide solo "cuánto" revisar — decide **sobre qué versión concreta** se sostiene esa evidencia, y organiza quién propone, quién limita y quién decide.

---

## Candidato congelado

La evidencia debe estar vinculada a una versión concreta del cambio (una PR, una rama o un commit identificable). Si el contenido cambia después de revisarlo, el receipt anterior deja de demostrar nada sobre la nueva versión — hay que revisar el candidato nuevo.

```text
Candidato terminado
        ↓
Congelar la versión que se va a revisar
        ↓
Checks + lentes de revisión
        ↓
Evidencia y hallazgos
        ↓
Receipt ligado al candidato
        ↓
Decisión humana de aceptar, corregir o rechazar
```

> **Un receipt no certifica "el proyecto". Registra la evidencia obtenida sobre un candidato concreto.**

---

## El receipt

Registro trazable de la revisión. Como mínimo contiene:

- el candidato revisado (PR / commit / rama);
- el riesgo percibido;
- la evidencia obtenida, capa por capa;
- los hallazgos que quedaron abiertos (si los hay);
- el resultado propuesto;
- quién conserva la autoridad de entrega — nunca el propio agente revisor.

Un receipt no es una garantía universal. Registra qué se comprobó y con qué resultado; su valor es hacer explícito el alcance real de la evidencia, para no confundir un "verde" genérico con una garantía de que todo está bien.

---

## Profundidad proporcional al riesgo

RDD simplifica la profundidad de revisión en tres niveles, pensados como explicación pedagógica — lo que importa no es la etiqueta, sino que la intensidad la decidan señales de riesgo, no la intuición ni el volumen del diff:

| Nivel | Cuándo encaja | Tratamiento |
|---|---|---|
| **Baja** | Cambio pasivo o visual acotado, sin señales críticas | Checks y evidencia directa del cambio |
| **Media** | Cambio ordinario de código con impacto localizado | Checks más una lente focalizada y contraste con el ticket |
| **Alta** | Seguridad, permisos, pagos, exposición o pérdida de datos, concurrencia u otra consecuencia difícil de revertir | Revisión profunda con las lentes 4R pertinentes y entrada humana explícita |

No todo cambio de alto riesgo necesita las cuatro lentes al mismo nivel de profundidad — la política del repositorio puede exigir el conjunto completo para lo crítico, y bastar con una lente focalizada para el resto. Lo que debe quedar siempre es que la elección sea justificable y quede registrada en el receipt.

**Quién decide el nivel:**

> **El modelo propone. La política limita. La persona decide.**

El agente detecta señales y propone una profundidad; la política del proyecto fija mínimos obligatorios; la persona responsable puede escalar la revisión cuando el contexto lo exige. El nivel nunca depende solo de una clasificación libre del LLM.

---

## Las lentes 4R (nivel alto)

Cuatro preguntas distintas, cada una exige evidencia distinta — no son sellos decorativos:

| Lente | Pregunta |
|---|---|
| **Risk** | ¿Qué daño puede causar este cambio si se equivoca? |
| **Resilience** | ¿Se comporta correctamente en límites, fallos y condiciones adversas? |
| **Readability** | ¿Otra persona puede comprender la regla, su ubicación y sus límites sin reconstruir toda la intención? |
| **Reliability** | ¿Qué evidencia reproducible detectaría una regresión? |

Reliability, en concreto, es donde conecta con [[bdd]]: un escenario Gherkin escrito antes de construir es la evidencia reproducible que esta lente busca después.

---

## Lo que RDD no sustituye

- los checks deterministas de la capa 1;
- BDD ni los criterios de aceptación escritos antes de construir;
- la política de ramas y protección del repositorio;
- la revisión humana de cambios críticos;
- pruebas especializadas de seguridad, carga, accesibilidad o concurrencia cuando sean necesarias.

RDD organiza la revisión y vincula evidencia al candidato — no se apropia de la decisión de entrega.

---

## Relación con el resto del arnés

- **[[ai-code-review]]** — RDD es el modelo de profundidad y trazabilidad *dentro* de esa etapa de revisión; no sustituye la capa de checks deterministas ni el review humano reservado a lo crítico, define cuánto deben profundizar y qué constancia dejar
- **[[odd]]** — ODD nunca activa RDD por sí solo; son interruptores separados. Clasificar un cambio como "sustancial" en ODD no implica automáticamente una revisión de nivel alto en RDD, y viceversa — cada uno responde a una pregunta distinta (cómo se aborda el trabajo vs. cómo se revisa el candidato terminado)
- **[[bdd]]** — un escenario Gherkin es el criterio que la lente Reliability usa para comprobar el resultado; además, una revisión profunda puede descubrir riesgos que el escenario original no cubría (ver Charla 24, caso de concurrencia) y que deberían convertirse en un nuevo escenario, no quedar como observación verbal

---

## Estado en la serie

Deliberadamente **no** se introdujo en la Charla 23 — se reservó junto con la demo de ai-code-review para una charla futura dedicada, para que llegara con tiempo propio en vez de como cierre apresurado. Esa charla es la **Charla 24** (28 de octubre de 2026): guion revisado, demo de contraste con dos PR abiertas (sin fusionar) sobre RCA, cada una con su receipt.

## Dónde aparece en la serie

| Charla | Rol |
|---|---|
| Charla 24 (28 oct 2026) | Introduce RDD con nombre: candidato congelado, receipt, niveles de profundidad y lentes 4R, demostrados mediante dos PR de contraste |

## Implementación sobre RCA

El reviewer agent de la Charla 8 no clasificaba riesgo ni producía receipt. [[rdd-reviewer-rca]] contiene el contenido preparado para extenderlo — checks deterministas, clasificación de riesgo, disparo de las 4R y plantilla de receipt — más el bloque de protocolo para las instrucciones persistentes de RCA, junto al de ODD y BDD.

---

## Referencias

- [gentle-ai — docs](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/usage.md)
- [Organic RDD: atomic review architecture](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/architecture/organic-rdd.md)
- [Receipt-Driven Development and Review Lifecycle](https://deepwiki.com/Gentleman-Programming/gentle-ai/8-receipt-driven-development-and-review-lifecycle)
- [Gates, Risk and Receipts](https://deepwiki.com/Gentleman-Programming/gentle-ai/8.3-gates-risk-and-receipts)
