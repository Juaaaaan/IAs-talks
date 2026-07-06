---
type: Concepto
title: "Nivel del equipo — Resumen y recomendaciones"
description: "Visión agregada del assessment de madurez IA del equipo. Quién está preparado para qué, brechas prioritarias y plan de acción."
tags: [equipo, assessment, nivel, resumen, recomendaciones, ia]
related: [assessment-framework, perfil-alejandro-m, perfil-sara-l, perfil-miguel-r, perfil-laura-g]
timestamp: "2026-07-06"
---

# Nivel del equipo — Resumen y recomendaciones

*Assessment realizado en julio de 2026. 4 participantes.*

---

## Scores medios por dimensión

| Dimensión | Media Personas | Nivel |
|-----------|:---:|-------|
| 1. Ideación, Planning y Diseño | 2.0 | Repetible |
| 2. Desarrollo y Generación de Código | 2.3 | Repetible |
| 3. Testing, Calidad y Seguridad | 2.5 | Repetible/Gestionado |
| 4. Validación de Código IA | 2.3 | Repetible |
| 5. Configuración y Assets de IA | 1.8 | Inicial/Repetible |
| 6. Automatización y Agentes | 1.5 | Inicial |
| 7. Gobierno, Riesgo y Compliance | 2.3 | Repetible |
| 8. Cultura, Skills y Adopción | 2.3 | Repetible |
| **Media global** | **2.1** | **Repetible** |

---

## Brecha principal: Dimensión 5 y 6

El equipo tiene uso individual razonablemente maduro (media 2.1) pero **no ha estandarizado el context engineering** (Dimensión 5: 1.8) ni ha adoptado flujos agentic (Dimensión 6: 1.5). Esto significa que cada persona trabaja con IA de forma diferente y el conocimiento no se comparte.

**Consecuencia práctica:** cuando entra una persona nueva al proyecto, no hay onboarding de IA estructurado. Cada developer tiene sus propios prompts y configuraciones que no benefician al resto.

---

## ¿Quién está preparado para qué?

| Persona | Modo agentic | Champion | Prioridad formación |
|---------|:---:|:---:|---------------------|
| Alejandro M. | ✅ Sí | ✅ Sí | Gobernanza (D7) |
| Sara L. | ❌ No | ❌ No | Context engineering (D5) + Validación (D4) |
| Miguel R. | ⚠️ Con supervisión | ⚠️ Parcial | Modo agentic (D6) + Assets (D5) |
| Laura G. | ⚠️ En testing | ❌ No | Context engineering (D5) |

---

## Plan de acción recomendado

**Inmediato (esta semana):**
- Alejandro M. crea el `copilot-instructions.md` del proyecto — ya lo tiene en proyectos personales.
- Miguel R. completa formación de gobernanza — bloquea su uso en modo agentic.

**Corto plazo (1 mes):**
- Sara L.: onboarding completo de context engineering con Alejandro como mentor.
- Laura G.: definir `testing.instructions.md` del equipo basado en su práctica actual.

**Medio plazo (3 meses):**
- Elevar Dimensión 6 del equipo a nivel 2: todos probando agentes supervisados.
- Objetivo: onboarding de IA < 1 día para nuevas incorporaciones.

---

## Pregunta clave respondida

> *"¿Quién del equipo está preparado para liderar la adopción de Copilot en el próximo proyecto?"*

**Alejandro M.** — único con score ≥ 3 en Dimensiones 2, 5 y 8. Pendiente de formación en gobernanza (D7) antes de proyectos con restricciones de cliente.
