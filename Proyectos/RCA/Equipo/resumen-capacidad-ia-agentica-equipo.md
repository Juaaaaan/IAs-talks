---
type: Recurso
title: "Resumen de capacidad en IA Agéntica — Equipo RCA"
description: "Documento para reunión con dirección. Clasifica al equipo según su preparación para usar IA agéntica e identifica necesidades de formación."
tags: [equipo, agentic, formacion, direccion, resumen]
related: [assessment-framework, nivel-equipo]
timestamp: "2026-07-08"
---

# Resumen de Capacidad en IA Agéntica — Equipo RCA

**Fecha:** 8 de julio de 2026
**Objetivo:** Identificar qué perfiles están capacitados para trabajar con IA agéntica y cuáles necesitan formación de refuerzo.
**Contexto:** Reunión con dirección — 9 de julio de 2026.

---

## Criterios de evaluación

Un perfil se considera **capacitado para IA agéntica** cuando cumple:

- Score ≥ 3 en **Dimensión 2** (Desarrollo y Generación de Código)
- Score ≥ 3 en **Dimensión 5** (Configuración y Assets de IA)
- Score ≥ 2 en **Dimensión 6** (Automatización y Agentes)

Fuente: [[assessment-framework]] — Assessment de Madurez de IA Generativa (8 dimensiones, escala 0–4).

---

## Resumen ejecutivo

| Estado | Personas | % Equipo |
|--------|:--------:|:--------:|
| ✅ Capacitados | 2 | 29% |
| ⚠️ Parcialmente (con supervisión) | 2 | 29% |
| ❌ No capacitados (requieren formación) | 3 | 43% |

---

## ✅ Capacitados para IA agéntica

| Persona | Rol | Score medio | D2 | D5 | D6 | Observaciones |
|---------|-----|:---:|:---:|:---:|:---:|---------------|
| **Alejandro M.** | Developer Senior Frontend | 3.1 | 4 | 4 | 3 | Champion de desarrollo. Usa modo agentic en producción. |
| **Francisco T.** | AI Ops Senior | 3.4 | 3 | 4 | 4 | Champion de operaciones/seguridad. Opera agentes autónomos. |

**Pueden:** trabajar de forma autónoma con agentes, configurar flujos agentic, mentorizar al equipo.

---

## ⚠️ Parcialmente capacitados (requieren supervisión)

| Persona | Rol | Score medio | D2 | D5 | D6 | Brecha principal |
|---------|-----|:---:|:---:|:---:|:---:|------------------|
| **Miguel R.** | Tech Lead / Backend Senior | 2.1 | 2 | 1 | 1 | Context engineering (D5) y resistencia al modo agentic (D6) |
| **Laura G.** | QA Engineer | 1.9 | 1 | 1 | 2 | Context engineering (D5); fuerte en testing con IA (D3=3) |

**Pueden:** usar IA en tareas supervisadas (chat, autocompletado, testing). **No pueden:** operar agentes de forma autónoma sin apoyo.

---

## ❌ No capacitados (requieren formación prioritaria)

| Persona | Rol | Score medio | D2 | D5 | D6 | Situación |
|---------|-----|:---:|:---:|:---:|:---:|-----------|
| **Sara L.** | Developer Junior Fullstack | 1.4 | 2 | 1 | 0 | Usa Copilot básico. No conoce modo agentic. |
| **José P.** | Developer Junior Backend | 0.6 | 1 | 0 | 0 | Uso mínimo (solo ChatGPT puntual). Onboarding completo necesario. |
| **Anabel M.** | Developer Middle Fullstack | 0.8 | 1 | 0 | 0 | Uso puntual de ChatGPT/Gemini. Conoce agentes en teoría pero sin práctica. |

**No pueden:** usar IA agéntica en ningún contexto. Necesitan onboarding antes de integrarse en flujos con agentes.

---

## Plan de formación recomendado

### Prioridad alta (antes de asignar a proyectos con agentes)

| Persona | Formación necesaria | Mentor sugerido | Plazo |
|---------|--------------------:|:---------------:|:-----:|
| José P. | Onboarding completo: Copilot básico → archivos de contexto → testing con IA → agentes | Alejandro M. | 3 meses |
| Anabel M. | Onboarding herramientas IA en IDE → context engineering → workshop práctico agentes/MCPs | Alejandro M. / Francisco T. | 2 meses |
| Sara L. | Context engineering + validación de código IA + introducción a modo agentic | Alejandro M. | 1–2 meses |

### Prioridad media (para habilitar modo agentic con supervisión)

| Persona | Formación necesaria | Mentor sugerido | Plazo |
|---------|--------------------:|:---------------:|:-----:|
| Miguel R. | Context engineering (D5) + demos de modo agentic supervisado para vencer resistencia | Francisco T. | 1 mes |
| Laura G. | Context engineering para testing + quality gates con IA en CI/CD | Alejandro M. | 1 mes |

### Prioridad baja (refuerzo puntual)

| Persona | Formación necesaria | Plazo |
|---------|--------------------:|:-----:|
| Alejandro M. | Gobernanza y compliance (D7) | 2 semanas |
| Francisco T. | Ideación y diseño de producto (D1) | 1 mes |

---

## Conclusiones para dirección

1. **El 29% del equipo (2/7) está preparado hoy** para trabajar con IA agéntica de forma autónoma.
2. **El 43% (3/7) necesita formación** antes de poder integrarse en proyectos que usen agentes.
3. **El equipo tiene dos champions complementarios** (desarrollo + operaciones) que pueden actuar como mentores internos.
4. **Riesgo principal:** si se asignan perfiles no preparados a proyectos con flujo agentic, la productividad caerá y aumentará el riesgo de código no validado.
5. **Inversión estimada:** con el plan de formación propuesto, en 3 meses el 71% del equipo (5/7) podría operar con agentes bajo supervisión.

---

## Visualización rápida

```
Escala de madurez agéntica (Dimensión 6):

Francisco T.  ████████████████████ 4/4  ✅ Autónomo
Alejandro M.  ███████████████      3/4  ✅ Autónomo
Laura G.      ██████████      2/4  ⚠️ Supervisado
Miguel R.     █████      1/4  ⚠️ Necesita formación
Sara L.       ·····      0/4  ❌ Sin capacidad
José P.       ·····      0/4  ❌ Sin capacidad
Anabel M.     ·····      0/4  ❌ Sin capacidad
```
