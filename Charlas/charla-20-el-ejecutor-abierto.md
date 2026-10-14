---
type: Charla
title: "Charla 20 — La otra correa del arnés: el ejecutor abierto (OpenCode)"
description: "Especificar (qué construir, correa de la Charla 16) y ejecutar (quién lo hace) son dos cosas distintas. Claude Code es un ejecutor potente pero cerrado y de un solo proveedor; OpenCode es el mismo trabajo con el motor, los datos y la gobernanza en manos de la empresa. Demo: el menú de OpenCode."
tags: [charla, opencode, ejecutor, arnes, gobernanza, open-source, claude-code]
related: [MATERIAL-CHARLA-20-EL-EJECUTOR-ABIERTO, guion-charla-20, demo-opencode-charla-20, opencode, arnes-completo, mcp-ecosystem]
charla: "Charla 20"
fecha: "2026-09-16"
estado: "✅ Impartida"
timestamp: "2026-09-16"
---

# Charla 20 — La otra correa del arnés: el ejecutor abierto (OpenCode)

**Estado:** ✅ Impartida

---

## Idea central

> _"¿Quién controla la IA que usa mi empresa, y dónde viven mis datos?"_

## Hilo narrativo

Retoma la distinción especificar/ejecutar de la Charla 16 (donde se usó Claude Code como ejecutor) y la separa en dos preguntas: QUÉ construir y QUIÉN lo ejecuta. Dirección definida como sesión de teoría/modelo mental (sin demo de construcción desde cero), con callback directo al "Analista de RFP" de la Charla 19 reinterpretado como ejemplo de multiagente dentro de una caja cerrada.

## Estructura

| Bloque | Contenido |
|---|---|
| Especificar vs ejecutar | El QUÉ (Charla 16) y el QUIÉN — dos decisiones que se mezclan sin darse cuenta |
| El ejecutor cerrado | Claude Code / GitHub Copilot: potentes, pero de un proveedor y con el código saliendo a un servidor de terceros — una decisión que toma el proveedor, no tú |
| El ejecutor abierto | OpenCode: licencia MIT, agnóstico de proveedor (75+ proveedores, incluidos modelos locales), los datos no salen de casa |
| Demo | El menú de OpenCode — elegir el motor, no asumir que hay uno solo |
| Gobernanza en empresa | `baseURL` a un gateway interno, config remota de organización, ajustes gestionados (MDM), permisos por agente como checkpoint |
| Cierre | Las tres preguntas para decidir: qué gobernar, cuántas manos, qué datos |

## Conceptos que introduce

- [[modelos-abiertos-vs-cerrados]] — aplicado ahora al ejecutor de código, no solo al modelo
- [[mcp-ecosystem]] — MCP del lado del ejecutor abierto

## Demo asociada

- [[demo-opencode-charla-20]] — el menú de OpenCode: elegir proveedor/modelo, modos Plan/Build

## Material asociado

- [[MATERIAL-CHARLA-20-EL-EJECUTOR-ABIERTO]] — guía de referencia completa de OpenCode: instalación, configuración y precedencia, agentes, permisos, skills, MCP, plugins, SDK, servidor headless, y un flujo de trabajo de principio a fin

## Frases clave

> _"Elegir el motor dentro de la caja no es lo mismo que controlar la caja."_

> _"El mismo trabajo. Pero el motor lo eliges tú, y tus datos se quedan en casa."_

---

## Retrospectiva

_(pendiente de completar)_
