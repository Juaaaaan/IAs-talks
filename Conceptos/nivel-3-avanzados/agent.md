---
type: Concepto
title: "Agent — Un rol autónomo con responsabilidad concreta"
description: "Rol autónomo de IA con responsabilidad específica, skills y acceso controlado a herramientas dentro de AI SDLC Foundation."
tags: [ai-sdlc-foundation, agent, autonomia, responsabilidad, skills, herramientas]
related: [ai-sdlc-foundation, skill-foundation, mcp-foundation, station, agentes-multiples]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Agent — Un rol autónomo con responsabilidad concreta

> _"El agente no es solo inteligencia disponible: es una responsabilidad delimitada con permisos y criterio para actuar."_

---

## Qué es

En AI SDLC Foundation, **Agent** es un rol autónomo de IA al que se le asigna una responsabilidad específica dentro de un sistema mayor. Ese rol combina objetivo, instrucciones, [[skill-foundation|skills]], contexto operativo y acceso controlado a herramientas o integraciones como [[mcp-foundation]]. La idea central no es "tener un modelo", sino definir una unidad de trabajo capaz de hacerse cargo de una función concreta.

---

## Papel en AI SDLC Foundation

Agent es la pieza que ejecuta o sostiene el trabajo especializado de una [[station]]. Foundation lo necesita para separar responsabilidades, limitar permisos y hacer que un mismo [[workflow]] no dependa de una inteligencia amorfa que intenta hacerlo todo a la vez. En esta familia conceptual, el referente más amplio sobre colaboración entre agentes sigue siendo [[agentes-multiples]], pero aquí el término se usa de forma más acotada y operativa.

---

## Cómo funciona

Un agente recibe una responsabilidad definida, un conjunto de skills relevantes y acceso solo a las herramientas o integraciones que realmente necesita. A partir de ahí actúa con cierta autonomía dentro de sus límites: puede leer, producir entregables, verificar evidencias o consultar sistemas externos si el entorno lo permite. Su frontera es clave: la autonomía sirve para ejecutar una función con menos intervención manual, no para borrar los límites de acceso, gobernanza o alcance.

---

## Ejemplos prácticos

### Ejemplo 1 — Agente reviewer

Una estación de revisión delega en un agente reviewer la tarea de comprobar si una implementación cumple criterios técnicos y de calidad. Ese agente necesita skills de revisión, contexto del cambio y acceso de lectura a los artefactos relevantes, pero no tiene por qué compartir exactamente los mismos permisos que un agente implementador.

### Ejemplo 2 — Agente de documentación

Otro workflow usa un agente de documentación para convertir decisiones dispersas en una ADR o en una guía técnica consistente. Su valor no está en "escribir texto" sin más, sino en asumir una responsabilidad editorial concreta apoyada por conocimiento reusable y plantillas adecuadas.

---

## Matices y confusiones habituales

- **Cuidado:** Un agente no es solo un modelo. El modelo aporta capacidad de inferencia, pero el agente añade responsabilidad, instrucciones, contexto y límites de actuación.
- **Cuidado:** Un agente tampoco es solo un prompt. El prompt puede iniciarlo o enmarcarlo, pero el rol autónomo incluye permisos, herramientas y comportamiento sostenido dentro del flujo.
- **Importante:** Autonomía no significa acceso sin límites. Un agente bien definido sabe qué puede hacer y qué no debe tocar.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Sitúa al agente dentro del vocabulario operativo completo.
- **[[skill-foundation]]** — Aporta conocimiento reusable para que el agente actúe con mejor criterio.
- **[[mcp-foundation]]** — Puede abrir el acceso mediado a herramientas y servicios externos que el agente necesite.
- **[[station]]** — Es el paso especializado donde el agente suele ejercer su responsabilidad concreta.
- **[[agentes-multiples]]** — Amplía el patrón de colaboración y separación de roles entre agentes.
