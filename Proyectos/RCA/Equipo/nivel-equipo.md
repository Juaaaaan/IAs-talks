---
type: Concepto
title: "Nivel del equipo — Resumen y recomendaciones"
description: "Visión agregada del assessment de madurez IA del equipo. Quién está preparado para qué, brechas prioritarias y plan de acción."
tags: [equipo, assessment, nivel, resumen, recomendaciones, ia]
related: [assessment-framework, perfil-alejandro-m, perfil-sara-l, perfil-miguel-r, perfil-laura-g, perfil-jose-p, perfil-francisco-t]
timestamp: "2026-07-07"
---

# Nivel del equipo — Resumen y recomendaciones

*Assessment realizado en julio de 2026. 6 participantes (equipo multidisciplinar: desarrollo + operaciones).*

---

## Scores medios por dimensión

| Dimensión | Media Personas | Nivel |
|-----------|:---:|-------|
| 1. Ideación, Planning y Diseño | 1.8 | Inicial/Repetible |
| 2. Desarrollo y Generación de Código | 2.2 | Repetible |
| 3. Testing, Calidad y Seguridad | 2.3 | Repetible |
| 4. Validación de Código IA | 2.0 | Repetible |
| 5. Configuración y Assets de IA | 1.8 | Inicial/Repetible |
| 6. Automatización y Agentes | 1.7 | Inicial/Repetible |
| 7. Gobierno, Riesgo y Compliance | 2.3 | Repetible |
| 8. Cultura, Skills y Adopción | 2.3 | Repetible |
| **Media global** | **2.1** | **Repetible** |

---

## Brecha principal: Dimensión 5 y 6 (en mejora)

La incorporación de Francisco T. (AI Ops Senior) reduce significativamente la brecha en Dimensiones 5 y 6. El equipo pasa de no tener referente en automatización y agentes a contar con un especialista (score 4/4 en ambas dimensiones).

**Situación actual:** el equipo sigue teniendo uso heterogéneo, pero ahora cuenta con **dos champions complementarios**: Alejandro M. (desarrollo) y Francisco T. (operaciones/seguridad). La brecha de José P. sigue existiendo pero hay más capacidad de mentoría.

**Consecuencia práctica:** Francisco T. aporta experiencia en montaje de sistemas agénticos (Hermes), seguridad IA (red team, prompt injection) y context engineering operativo (AGENTS.md, skills, MCPs). El equipo ya no depende de un solo perfil para adopción avanzada.

---

## ¿Quién está preparado para qué?

| Persona | Modo agentic | Champion | Prioridad formación |
|---------|:---:|:---:|---------------------|
| Alejandro M. | ✅ Sí | ✅ Sí (Dev) | Gobernanza (D7) |
| Francisco T. | ✅ Sí | ✅ Sí (Ops/Seguridad) | Ideación y diseño (D1) |
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

## Visión de equipo multidisciplinar

El equipo ya no es solo de desarrollo. Con la incorporación de Francisco T. se establece un **equipo multidisciplinar** donde operaciones e IA convergen. El objetivo es cubrir todo el ciclo: desde la generación de código hasta la operación segura de agentes autónomos.

---

## Pregunta clave respondida

> *"¿Quién del equipo está preparado para liderar la adopción de Copilot en el próximo proyecto?"*

**Alejandro M.** (desarrollo) y **Francisco T.** (operaciones/seguridad) — ambos con score ≥ 3 en Dimensiones 2, 5 y 8. Francisco cubre además la brecha de seguridad y automatización que el equipo tenía. Pendiente: Alejandro necesita formación en gobernanza (D7); Francisco en ideación/diseño (D1).
