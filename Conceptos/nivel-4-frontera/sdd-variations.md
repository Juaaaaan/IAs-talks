---
type: Concepto
title: "SDD Variations — Variantes de Specification-Driven Development"
description: "Evoluciones y variantes del patrón SDD: Design Docs, RFC-as-code, ADRs, Spec files. Diferentes formas de especificar antes de implementar con IA."
tags: [sdd, variantes, design-docs, rfc, adr, especificacion, desarrollo]
related: [sdd, code-generation-patterns, copilot-instructions, arnes-completo]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# SDD Variations — Variantes de Specification-Driven Development

> _"SDD es una filosofía, no un formato. Hay muchas formas de especificar antes de implementar."_

---

## Qué es

**SDD (Specification-Driven Development)** establece que debes especificar QUÉ construir antes de pedirle a la IA que lo implemente. Pero el formato concreto de esa especificación puede variar.

Estas son las variantes más utilizadas.

---

## Variantes

### 1. spec.md + task.md (SDD clásico)
```
spec.md  → QUÉ construir (requisitos, criterios)
task.md  → CÓMO implementarlo (pasos, ficheros)
```
El patrón original de esta serie. Ideal para features bien definidas.

### 2. Design Docs (Google-style)
```
Contexto → Problema → Solución propuesta → Alternativas → Plan
```
Documentos más extensos que cubren el razonamiento completo. Usados en Google internamente.

### 3. RFC (Request for Comments)
```
RFC-0042: Migrar autenticación a OAuth2
Estado: Aprobado
Autor: Juan R.
Fecha: 2026-07-13
...
```
Formato formal para propuestas técnicas que requieren discusión del equipo.

### 4. ADR (Architecture Decision Records)
```
# ADR-003: No usar NgRx
Estado: Aceptado
Contexto: ...
Decisión: ...
Consecuencias: ...
```
Decisiones de arquitectura documentadas. Más ligeros que RFCs.

### 5. Issue-as-spec
```
GitHub Issue con:
- Descripción del problema
- Criterios de aceptación
- Contexto técnico
```
La issue ES la especificación. El agente la lee y la implementa.

### 6. Prompt Engineering Documents
```
Documento que define:
- El system prompt exacto
- Los ejemplos (few-shot)
- Los guardrails
- Las métricas de éxito
```
Para tareas que no son código sino configuración de comportamiento IA.

---

## Cuándo usar cada variante

| Situación | Variante |
|---|---|
| Feature nueva con requisitos claros | spec.md + task.md |
| Decisión de arquitectura | ADR |
| Cambio que afecta a múltiples equipos | RFC |
| Proyecto grande en fase de diseño | Design Doc |
| Bugfix o tarea pequeña | Issue-as-spec |
| Configurar comportamiento IA | Prompt Engineering Doc |

---

## Lo que tienen en común

Todas las variantes comparten los mismos principios:
1. **Escribe primero, implementa después**
2. **El humano especifica, la IA ejecuta**
3. **El documento es el contrato**
4. **La revisión ocurre sobre la spec, no sobre el código**

---

## ADRs en este vault

La carpeta `Proyectos/RCA/Developer/` contiene ADRs reales:
- `decision-no-ngrx.md`
- `decision-ssr-zoneless.md`
- `decision-supabase.md`
- `decision-responsive.md`
- `decision-no-dark-mode.md`

Estos son ejemplos vivos de SDD variations.

---

## Relación con otras piezas

- **[[sdd]]** — El concepto base del que derivan todas las variantes
- **[[code-generation-patterns]]** — SDD es el patrón de generación más estructurado
- **[[copilot-instructions]]** — Las instrucciones complementan la spec
- **[[arnes-completo]]** — SDD es el arnés documental del arnés completo

---

## Referencias

- [Google Design Docs](https://www.industrialempathy.com/posts/design-docs-at-google/)
- [ADR — Architecture Decision Records](https://adr.github.io/)
- [Thoughtworks RFC process](https://www.thoughtworks.com/insights/blog/architecture/rfcs-lightweight-architectural-decision-records)
