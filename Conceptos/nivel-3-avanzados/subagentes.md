---
type: Concepto
title: "Subagentes — Delegar subtareas con contexto propio"
description: "Agentes a los que otro agente encarga una parte del trabajo. Suelen trabajar con su propio contexto y devolver un resultado, lo que permite aislar ruido y a veces trabajar en paralelo."
tags: [subagentes, delegacion, agentes, contexto, orquestacion]
related: [agentes-multiples, orchestration-patterns, context-rot, hub-orchestrator, a2a]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Subagentes

> _"Encargas la búsqueda y recibes la conclusión, no las cien páginas leídas."_

---

## Qué es

Un **subagente** recibe de un agente principal un **encargo acotado**. Normalmente trabaja en un contexto separado y devuelve un resultado. Los detalles cambian según la herramienta.

---

## Para qué sirve

| Ventaja | Ejemplo |
|---|---|
| **Proteger el contexto principal** | Explorar muchos ficheros y devolver solo lo relevante |
| **Paralelizar** | Revisar varias partes independientes a la vez |
| **Especializar** | Uno con instrucciones de seguridad, otro de tests |
| **Segunda mirada** | Revisar sin heredar todo el razonamiento del autor |

---

## Lo que cuesta

- Más consumo de tokens
- El subagente **no sabe lo que no le cuentes**
- Su resumen puede omitir o afirmar cosas: hay que **verificar** lo importante
- Si varios modifican lo mismo, pueden pisarse

---

## Un buen encargo

Objetivo, contexto necesario, límites, formato de la respuesta y cómo distinguir lo comprobado de lo supuesto.

---

## Relación con otras piezas

- **[[agentes-multiples]]** — El patrón developer/reviewer
- **[[orchestration-patterns]]** — Formas de coordinar varios agentes
- **[[hub-orchestrator]]** — El despachador en AI SDLC Foundation
- **[[context-rot]]** — El ruido que se intenta aislar
- **[[a2a]]** — Protocolo para comunicar agentes independientes
