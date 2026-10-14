---
type: Concepto
title: "Template — El esqueleto de un entregable"
description: "Documento preformateado que el agente completa al producir un resultado dentro de AI SDLC Foundation. Ordena la salida, pero no decide por sí solo el contenido ni sustituye una instrucción."
tags: [ai-sdlc-foundation, template, entregables, structured-output, workflow, station]
related: [ai-sdlc-foundation, workflow, station, knowledge, structured-output]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Template — El esqueleto de un entregable

> _"La plantilla no piensa por el agente, pero evita que el resultado salga desordenado."_

---

## Qué es

En AI SDLC Foundation, **Template** es un documento preformateado que define la estructura esperada de un entregable. Marca secciones, campos o bloques que el agente debe completar cuando produce una salida. Su función es dar forma consistente al resultado, no decidir automáticamente qué contenido debe ir en cada apartado.

---

## Papel en AI SDLC Foundation

Template convierte la intención de un [[workflow]] o de una [[station]] en un formato reutilizable y repetible. Ayuda a que distintos agentes entreguen resultados comparables, auditables y más fáciles de revisar. Además, puede apoyarse en [[knowledge]] para reflejar el estilo o los requisitos que el equipo considera válidos.

---

## Cómo funciona

Cuando un flujo necesita generar una ADR, un informe o un checklist, el runtime asocia la tarea con una plantilla concreta. El agente recibe esa estructura y la completa con contenido obtenido del contexto, de las herramientas y del razonamiento del flujo. La frontera clave es que la plantilla organiza la salida, pero no reemplaza la instrucción que explica por qué se genera ni el criterio que decide qué poner dentro.

---

## Ejemplos prácticos

### Ejemplo 1 — Plantilla de ADR

Una template puede ofrecer un esqueleto de ADR con encabezados y espacios reservados para documentar una decisión técnica de forma consistente. El agente lo completa según el caso concreto, pero la plantilla solo aporta la forma inicial del entregable.

### Ejemplo 2 — Plantilla de informe de revisión

Otra template puede preparar un informe de revisión con bloques ya separados para que distintas revisiones mantengan una presentación homogénea. El contenido exacto de cada bloque depende del análisis realizado, no de un esquema cerrado impuesto por la plantilla.

---

## Matices y confusiones habituales

- **Cuidado:** La plantilla estructura la salida, pero no decide el contenido. El agente sigue necesitando criterio y contexto para completarla bien.
- **Cuidado:** Una template no sustituye una instruction. Una organiza el entregable; la otra condiciona comportamiento.
- **Importante:** Una plantilla excesivamente rígida puede forzar resultados artificiales si el tipo de tarea no encaja con su estructura.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Integra Template en el vocabulario base del sistema.
- **[[workflow]]** — Suele decidir qué plantilla corresponde a cada flujo.
- **[[station]]** — Puede producir un entregable parcial o final usando una template concreta.
- **[[knowledge]]** — Aporta políticas y criterios que enriquecen el contenido de la salida.
- **[[structured-output]]** — Conecta la plantilla con la idea de respuestas estructuradas y parseables.
