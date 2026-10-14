---
type: Charla
title: "Charla 16 — SDD con herramientas: spec manual vs OpenSpec"
description: "Del vibe coding al Spec-Driven Development con herramientas. Anatomía de un spec manual, el ecosistema SDD 2026 (OpenSpec, Spec Kit, Kiro) y demo en directo: ciclo completo Jira → OpenSpec → Claude Code → código sobre RCA (Cart Drawer, RCA-21)."
tags: [charla, sdd, openspec, spec-kit, kiro, claude-code, rca, delta-spec]
related: [MATERIAL-CHARLA-16-SDD-HERRAMIENTAS, guion-charla-16, demo-openspec-charla-16, sdd, sdd-variations, agente-ia]
charla: "Charla 16"
fecha: "2026-08-12"
estado: "✅ Impartida"
timestamp: "2026-08-12"
---

# Charla 16 — SDD con herramientas: spec manual vs OpenSpec

**Estado:** ✅ Impartida

---

## Idea central

> _"El 90% de los desarrolladores ya usa IA en su trabajo. Pero solo el 13% la usa en todo el ciclo de desarrollo."_ (encuesta JetBrains, enero 2026)

Vibe coding (prompt vago, se espera que salga algo razonable) se desmorona con la complejidad. Spec-Driven Development invierte el orden: la especificación, no el código, es la fuente de verdad.

## Hilo narrativo

Primera charla técnica con demo en pantalla desde el bloque de herramientas SDD. Retoma SDD —introducido conceptualmente en la Charla 7— y lo lleva a herramientas concretas y a un flujo reproducible sobre el proyecto demo RCA.

## Estructura

| Bloque | Contenido |
|---|---|
| Apertura | Vibe coding vs SDD; el salto 90%→13% |
| Anatomía de un spec manual | Las 5 partes de un buen spec; ventajas y límites |
| Ecosistema SDD 2026 | Tres arquetipos: OpenSpec (ligero), Spec Kit (estándar de comunidad), Kiro (integrado, AWS) |
| Demo | Ciclo completo con Claude Code: ticket Jira RCA-21 (Cart Drawer) → `/opsx-propose` → revisión → `/opsx-apply` → `/opsx-archive` → PR |
| Delta specs | El concepto central de OpenSpec: ADDED/MODIFIED/REMOVED en vez de reescribir todo el spec |
| Cierre | Criterio práctico: cuándo usar spec manual, OpenSpec, Spec Kit o Kiro — y cuándo no usar nada |

## Conceptos que introduce

- [[sdd]] — ampliado con las herramientas 2026 y la anatomía de un spec manual
- [[sdd-variations]] — Spec Kit y Kiro como variantes del mismo patrón, junto a Design Docs/RFC/ADR

## Demo asociada

- [[demo-openspec-charla-16]] — flujo completo Jira RCA-21 → OpenSpec → Claude Code → código

## Material asociado

- [[MATERIAL-CHARLA-16-SDD-HERRAMIENTAS]] — instalación de OpenSpec, referencia completa de comandos, el mismo flujo repetido con GitHub Copilot, y consideraciones de seguridad corporativa

## Frases clave

> _"No le das a un contratista 'hazme una casa, ya te apañas'. Le das planos. El SDD son los planos para agentes de IA."_

> _"El spec no es un impuesto que pagas siempre — es un seguro que contratas cuando la tarea es lo bastante grande como para que valga la pena."_

---

## Retrospectiva

_(pendiente de completar)_
