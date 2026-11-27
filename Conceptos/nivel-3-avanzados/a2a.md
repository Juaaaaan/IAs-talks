---
type: Concepto
title: "A2A — El protocolo para que agentes distintos se entiendan"
description: "Agent2Agent es un estándar abierto para que agentes independientes, incluso de proveedores distintos, se descubran, se comuniquen y se coordinen. Complementa a MCP."
tags: [a2a, agent2agent, protocolo, interoperabilidad, agentes, estandar]
related: [mcp, agentes-multiples, orchestration-patterns, subagentes, mcp-ecosystem]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# A2A — Agent2Agent

> _"MCP conecta al agente con sus herramientas. A2A lo conecta con otros agentes."_

---

## Qué es

**A2A** (*Agent2Agent*) es un **protocolo abierto** para la comunicación y colaboración entre agentes que pueden estar hechos con tecnologías distintas.

---

## Un poco de historia

| Fecha | Hito |
|---|---|
| Abril 2025 | Google lo presenta |
| Junio 2025 | Pasa a la Linux Foundation |
| Marzo 2026 | Versión 1.0, primera especificación estable |
| Agosto 2026 | Pasa a ser proyecto de la Agentic AI Foundation |

---

## A2A y MCP

| | [[mcp]] | A2A |
|---|---|---|
| **Conecta** | Aplicaciones de IA con herramientas y datos | Agentes independientes entre sí |
| **Analogía** | Darle instrumentos a un profesional | Que dos profesionales de empresas distintas colaboren |

No compiten: resuelven conexiones diferentes.

---

## Ejemplo ilustrativo

Un agente de una empresa que gestiona un viaje pide disponibilidad al agente de un proveedor, sin necesidad de conocer cómo está construido por dentro.

---

## Ojo

Que un protocolo permita comunicarse **no significa que haya que confiar** en el otro agente. Siguen haciendo falta identidad, permisos, trazabilidad y tratar sus respuestas como contenido externo.

---

## Relación con otras piezas

- **[[mcp]]** y **[[mcp-ecosystem]]** — La conexión con herramientas
- **[[agentes-multiples]]** y **[[orchestration-patterns]]** — Coordinación entre agentes
- **[[subagentes]]** — Delegación, habitualmente dentro de un mismo sistema

---

## Referencias

- [Agentic AI Foundation — A2A joins AAIF](https://aaif.io/blog/a2a-joins-aaif)
- [Especificación A2A](https://a2a-protocol.org/latest/)
