---
type: Concepto
title: "Nivel del equipo — Resumen y recomendaciones"
description: "Visión agregada del assessment de madurez IA del equipo. Quién está preparado para qué, brechas prioritarias y plan de acción."
tags: [equipo, assessment, nivel, resumen, recomendaciones, ia]
related: [assessment-framework, perfil-alejandro-m, perfil-sara-l, perfil-miguel-r, perfil-laura-g, perfil-jose-p, perfil-francisco-t, perfil-anabel-m, perfil-yuki-l]
timestamp: "2026-07-08"
---

# Nivel del equipo — Resumen y recomendaciones

*Assessment realizado en julio de 2026. 8 participantes (equipo multidisciplinar: desarrollo + operaciones + análisis funcional).*

---

## Scores medios por dimensión

| Dimensión | Media Personas | Nivel |
|-----------|:---:|-------|
| 1. Ideación, Planning y Diseño | 1.7 | Inicial/Repetible |
| 2. Desarrollo y Generación de Código | 1.8 | Inicial/Repetible |
| 3. Testing, Calidad y Seguridad | 1.7 | Inicial/Repetible |
| 4. Validación de Código IA | 1.5 | Inicial/Repetible |
| 5. Configuración y Assets de IA | 1.6 | Inicial/Repetible |
| 6. Automatización y Agentes | 1.4 | Inicial |
| 7. Gobierno, Riesgo y Compliance | 2.1 | Repetible |
| 8. Cultura, Skills y Adopción | 2.2 | Repetible |
| **Media global** | **1.8** | **Inicial/Repetible** |

---

## Brecha principal: Dimensiones técnicas con nuevas incorporaciones

La incorporación de Anabel M. (developer middle) y Yuki L. (analista funcional) amplía el equipo pero reduce las medias técnicas. Ambas tienen scores bajos en dimensiones de desarrollo con IA (D2-D6), lo que refleja que están en fase de onboarding.

**Fortalezas del equipo ampliado:**
- Francisco T. y Alejandro M. siguen siendo los champions técnicos.
- Yuki L. aporta conocimiento conceptual de MCPs/Skills/Agentes y experiencia en gestión de equipos — perfil puente con cliente.
- Anabel M. tiene alto potencial de crecimiento rápido (perfil autodidacta con seniority técnica).

**Consecuencia práctica:** La media global baja de 2.1 a 1.8. Esto no indica retroceso real sino que el equipo crece más rápido que la formación. El plan de acción debe priorizar el onboarding de las nuevas incorporaciones sin frenar a los perfiles avanzados.

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
| Anabel M. | ❌ No | ❌ No | Onboarding IA en IDE (D2, D3, D4, D5) |
| Yuki L. | ❌ N/A (no dev) | ⚠️ Puente cliente | Gobierno (D7) + IA aplicada a rol funcional |

---

## Plan de acción recomendado

**Inmediato (esta semana):**
- Alejandro M. crea el `copilot-instructions.md` del proyecto — ya lo tiene en proyectos personales.
- Miguel R. completa formación de gobernanza — bloquea su uso en modo agentic.

**Corto plazo (1 mes):**
- Sara L.: onboarding completo de context engineering con Alejandro como mentor.
- Laura G.: definir `testing.instructions.md` del equipo basado en su práctica actual.
- Anabel M.: onboarding de Copilot en IDE (autocompletado + chat + archivos de contexto). Mentor: Alejandro M.
- Yuki L.: formación en uso de IA generativa para documentación funcional, requisitos e historias de usuario. Explorar Adobe AI para su flujo de trabajo.

**Corto plazo — José P. (1 mes):**
- Taller de Copilot básico (autocompletado + chat) con mentor asignado (Alejandro M.).
- Sesión sobre archivos de contexto y `copilot-instructions.md`.
- Práctica guiada: generar tests con IA para su código backend.

**Medio plazo (3 meses):**
- Elevar Dimensión 6 del equipo a nivel 2: todos probando agentes supervisados.
- José P. debe alcanzar score ≥ 2 en Dimensiones 2, 3 y 5.
- Anabel M. debe alcanzar score ≥ 2 en Dimensiones 2, 4 y 5.
- Yuki L.: consolidar rol de puente entre equipo técnico y cliente en adopción de IA.
- Objetivo: onboarding de IA < 1 día para nuevas incorporaciones.

---

## Visión de equipo multidisciplinar

El equipo ya no es solo de desarrollo y operaciones. Con la incorporación de Yuki L. (analista funcional) se establece un **equipo verdaderamente multidisciplinar** que cubre desde el análisis funcional y la relación con cliente hasta la operación segura de agentes autónomos. La IA no es solo para quien escribe código — también transforma cómo se analizan requisitos, se documentan decisiones y se comunica con stakeholders.

---

## Pregunta clave respondida

> *"¿Quién del equipo está preparado para liderar la adopción de Copilot en el próximo proyecto?"*

**Alejandro M.** (desarrollo) y **Francisco T.** (operaciones/seguridad) — ambos con score ≥ 3 en Dimensiones 2, 5 y 8. Francisco cubre además la brecha de seguridad y automatización que el equipo tenía. Pendiente: Alejandro necesita formación en gobernanza (D7); Francisco en ideación/diseño (D1).
