---
type: Concepto
title: "Nivel del equipo — Resumen y recomendaciones"
description: "Visión agregada del assessment de madurez IA del equipo. Quién está preparado para qué, brechas prioritarias y plan de acción."
tags: [equipo, assessment, nivel, resumen, recomendaciones, ia]
related: [assessment-framework, perfil-alejandro-m, perfil-sara-l, perfil-miguel-r, perfil-laura-g, perfil-jose-p]
timestamp: "2026-07-07"
---

# Nivel del equipo — Resumen y recomendaciones

*Assessment realizado en julio de 2026. 5 participantes.*

---

## Scores medios por dimensión

| Dimensión | Media Personas | Nivel |
|-----------|:---:|-------|
| 1. Ideación, Planning y Diseño | 1.8 | Inicial/Repetible |
| 2. Desarrollo y Generación de Código | 2.0 | Repetible |
| 3. Testing, Calidad y Seguridad | 2.0 | Repetible |
| 4. Validación de Código IA | 1.8 | Inicial/Repetible |
| 5. Configuración y Assets de IA | 1.4 | Inicial |
| 6. Automatización y Agentes | 1.2 | Inicial |
| 7. Gobierno, Riesgo y Compliance | 2.2 | Repetible |
| 8. Cultura, Skills y Adopción | 2.0 | Repetible |
| **Media global** | **1.8** | **Inicial/Repetible** |

---

## Brecha principal: Dimensión 5 y 6

El equipo tiene uso individual heterogéneo (media 1.8) y **no ha estandarizado el context engineering** (Dimensión 5: 1.4) ni ha adoptado flujos agentic (Dimensión 6: 1.2). La incorporación de José P. (score 0.6) evidencia que los perfiles junior entran sin base de IA, lo que amplía la brecha.

**Consecuencia práctica:** cuando entra una persona nueva al proyecto, no hay onboarding de IA estructurado. Cada developer tiene sus propios prompts y configuraciones que no benefician al resto. José P. es un caso claro: motivación alta pero formación cero.

---

## ¿Quién está preparado para qué?

| Persona | Modo agentic | Champion | Prioridad formación |
|---------|:---:|:---:|---------------------|
| Alejandro M. | ✅ Sí | ✅ Sí | Gobernanza (D7) |
| Sara L. | ❌ No | ❌ No | Context engineering (D5) + Validación (D4) |
| Miguel R. | ⚠️ Con supervisión | ⚠️ Parcial | Modo agentic (D6) + Assets (D5) |
| Laura G. | ⚠️ En testing | ❌ No | Context engineering (D5) |
| José P. | ❌ No | ❌ No | Onboarding completo (D2, D3, D5) |

---

## Plan de acción recomendado

**Inmediato (esta semana):**
- Alejandro M. crea el `copilot-instructions.md` del proyecto — ya lo tiene en proyectos personales.
- Miguel R. completa formación de gobernanza — bloquea su uso en modo agentic.

**Corto plazo (1 mes):**
- Sara L.: onboarding completo de context engineering con Alejandro como mentor.
- Laura G.: definir `testing.instructions.md` del equipo basado en su práctica actual.

**Corto plazo — José P. (1 mes):**
- Taller de Copilot básico (autocompletado + chat) con mentor asignado (Alejandro M.).
- Sesión sobre archivos de contexto y `copilot-instructions.md`.
- Práctica guiada: generar tests con IA para su código backend.

**Medio plazo (3 meses):**
- Elevar Dimensión 6 del equipo a nivel 2: todos probando agentes supervisados.
- José P. debe alcanzar score ≥ 2 en Dimensiones 2, 3 y 5.
- Objetivo: onboarding de IA < 1 día para nuevas incorporaciones.

---

## Pregunta clave respondida

> *"¿Quién del equipo está preparado para liderar la adopción de Copilot en el próximo proyecto?"*

**Alejandro M.** — único con score ≥ 3 en Dimensiones 2, 5 y 8. Pendiente de formación en gobernanza (D7) antes de proyectos con restricciones de cliente.
