---
type: recurso
title: "Gentleman Programming / gentle-ai — dossier"
description: "Comunidad y framework de Alan Buscaglia: el origen de ODD, RDD (candidato congelado, receipt, lentes 4R) y el término 'AI harness engineering' usado en la Charla 23 y desarrollado en la 24"
tags: [gentleman-programming, gentle-ai, alan-buscaglia, odd, rdd, receipt, candidato-congelado, harness, recurso]
related:
  - "[[odd]]"
  - "[[rdd]]"
  - "[[ai-harness-engineering]]"
  - "[[guion-charla-23]]"
  - "[[guion-charla-24]]"
timestamp: 2026-10-27
fuente: "https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/usage.md"
---

# Gentleman Programming / gentle-ai — dossier

> Nota de referencia. Gentleman Programming (Alan Buscaglia) es la fuente de ODD, RDD y de la frase "verifying beats generating", usadas en la Charla 23 y desarrolladas en profundidad en la Charla 24.

## Qué es

**Gentleman Programming** es la comunidad hispanohablante de Alan Buscaglia centrada en desarrollo asistido por IA. **gentle-ai** es el framework/CLI que construye sobre Claude Code / Copilot CLI, inyectando disciplina de "AI harness engineering" encima del modelo base.

No hace falta instalar gentle-ai para usar sus ideas: la mayoría son instrucciones persistentes que se pueden escribir a mano en `CLAUDE.md` o `copilot-instructions.md`.

## Lo que aporta a esta serie

- **[[odd|ODD — Organic Driven Development]]** — el comportamiento por defecto del agente (autorizar → explorar → clasificar → documentar si es sustancial). Introducido con nombre en la Charla 23.
- **[[rdd|RDD — Receipt-Driven Development]]** — modelo de profundidad y trazabilidad para revisión de código, desarrollado con nombre en la Charla 24:
  - **candidato congelado** — la evidencia se vincula a una versión concreta del cambio; si el candidato cambia, el receipt anterior deja de ser válido;
  - **receipt** — el registro trazable de la revisión (candidato, checks, lentes, evidencia, hallazgos, resultado, autoridad de entrega);
  - **profundidad proporcional** — tres niveles pedagógicos (baja/media/alta), con el reparto "el modelo propone, la política limita, la persona decide";
  - **lentes 4R** — Risk, Resilience, Readability, Reliability, para la revisión de nivel alto.
- El término **[[ai-harness-engineering|AI harness engineering]]** y la frase *"verifying beats generating"*, usados como cierre de la Charla 23.

## Relación con el resto del arnés

ODD y RDD no sustituyen nada de lo ya construido en la serie ([[sdd|SDD]], [[bdd|BDD]], Skills, MCPs) — son el nombre formal para disciplinas que ya se venían aplicando, más el protocolo concreto para lo que no tenía nombre todavía: qué hacer cuando no hay spec ni escenario (ODD), y qué evidencia exigir a un candidato ya construido antes de aceptarlo (RDD).

## Enlaces

- Docs generales: https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/usage.md
- Sección ODD: https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/usage.md#organic-driven-development-odd
- Organic RDD — arquitectura de revisión atómica: https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/architecture/organic-rdd.md
- Receipt-Driven Development y ciclo de vida de la revisión: https://deepwiki.com/Gentleman-Programming/gentle-ai/8-receipt-driven-development-and-review-lifecycle
- Gates, Risk and Receipts: https://deepwiki.com/Gentleman-Programming/gentle-ai/8.3-gates-risk-and-receipts
