---
type: Concepto
title: "Assessment de Madurez de IA Generativa — Framework"
description: "Cómo medimos el nivel de madurez en el uso de IA generativa en el equipo. 8 dimensiones, escala 0-4. Base para asignar recursos y planificar formación."
tags: [equipo, assessment, madurez, ia, formacion, copilot, adopcion]
related: [nivel-equipo]
timestamp: "2026-07-06"
---

# Assessment de Madurez de IA Generativa

Este framework evalúa el nivel de uso de IA generativa de cada persona del equipo en 8 dimensiones. Permite al jefe de proyecto saber quién está preparado para qué y cómo asignar recursos en proyectos que usan IA.

---

## Escala de madurez (0–4)

| Score | Nivel | Descripción |
|-------|-------|-------------|
| 0 | Inexistente / Shadow AI | No hay uso oficial. Uso oculto sin control. |
| 1 | Inicial (Ad-hoc) | Uso individual y esporádico. Sin guías ni consistencia. |
| 2 | Repetible (Equipo) | Acuerdos de trabajo. Prompts básicos compartidos. Consciencia de riesgos. |
| 3 | Gestionado (Estandarizado) | Integración formal en el SDLC. Plantillas, repos de contexto, métricas. |
| 4 | Optimizado (Agentic / Autónomo) | Automatización profunda. IA en CI/CD, agentes autónomos. Mejora continua. |

---

## Las 8 dimensiones evaluadas

| # | Dimensión | Qué mide |
|---|-----------|----------|
| 1 | Ideación, Planning y Diseño | Uso de IA en ceremonias Agile, ADRs, estimaciones, wireframes |
| 2 | Desarrollo y Generación de Código | Autocompletado, pair programming, modo agentic, archivos de contexto |
| 3 | Testing, Calidad y Seguridad | Generación de tests, debugging, SAST/DAST, quality gates |
| 4 | Validación de Código Generado por IA | Checklists de revisión, trazabilidad, confianza |
| 5 | Configuración y Assets de IA | AGENTS.md, rules, skills, MCPs, hooks, onboarding |
| 6 | Automatización y Agentes Autónomos | Bots en CI/CD, agentes que implementan features, orquestación |
| 7 | Gobierno, Riesgo y Compliance | Políticas, DLP, licencias, Shadow AI, regulación |
| 8 | Cultura, Skills y Adopción | Formación, champions, compartición de conocimiento, métricas |

---

## Cómo interpretar los resultados

**Score ≤ 1 en Dimensión 7 (Gobierno):** riesgo inmediato. La persona puede estar usando IA sin conocer las restricciones del cliente. Formación urgente en políticas.

**Score ≥ 3 en Dimensiones 2 y 5:** lista para trabajar con Copilot en modo agentic de forma autónoma en el proyecto.

**Score ≥ 3 en Dimensión 8:** candidata a champion o mentora de otros miembros del equipo.

**Score ≤ 1 en todas las dimensiones:** perfil que necesita onboarding completo antes de integrarse en un proyecto con flujo de IA.

---

## Pregunta clave para asignación de recursos

> *"¿Quién del equipo está preparado para liderar la adopción de Copilot en el próximo proyecto?"*

Criterios: score ≥ 3 en Dimensiones 2, 5 y 8, y score ≥ 2 en Dimensión 7.
