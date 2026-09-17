---
type: Concepto
title: "Hooks como gates de aprobación — Gobernanza que se ejecuta"
description: "Gobernanza técnica: hooks deterministas que aprueban o bloquean acciones del agente mientras actúa. El puente entre la política de gobernanza y la ejecución real."
tags: [hooks, gates, aprobacion, gobernanza, control, seguridad, human-in-the-loop]
related: [ai-governance, prompt-injection, autonomous-coding-agents, ai-native-sdlc]
estado: "✅ Publicado"
timestamp: "2026-09-17"
---

# Hooks como gates de aprobación — Gobernanza que se ejecuta

> _"Una política que nadie ejecuta es un PDF. Un hook es esa política convertida en código que se dispara sola."_

---

## Qué es

Un **hook** es un punto de enganche determinista que se ejecuta automáticamente en un momento del ciclo del agente (antes de una acción, después de generar código, antes de un commit...) y puede **permitir, bloquear o pedir aprobación humana**.

Usados como **gates de aprobación**, los hooks hacen que la gobernanza ocurra *mientras el agente actúa*, no en una revisión posterior. Son deterministas: no dependen del criterio del modelo, se cumplen siempre.

---

## Normativa vs. técnica

Es el complemento ejecutable de **[[ai-governance]]**:

| | Gobernanza normativa | Hooks (gobernanza técnica) |
|---|---|---|
| Qué es | Políticas, EU AI Act, ISO 42001 | Código que se dispara en la ejecución |
| Dónde vive | Documentos, procesos | El repo y el runtime del agente |
| Cuándo actúa | Auditoría, revisión | En el momento exacto de la acción |
| Ejemplo | "Hay que revisar el output crítico" | Hook que bloquea el merge si no hay aprobación |

La política dice *qué* debe cumplirse; el hook *lo hace cumplir*.

---

## Ejemplos

- **Pre-commit**: bloquear el commit si detecta secretos o PII.
- **Antes de tocar producción**: exigir firma humana explícita (gate).
- **Post-generación**: correr los tests y no dejar avanzar si fallan.
- **Acción destructiva**: parar y pedir confirmación antes de borrar o migrar datos.

---

## Por qué importa (y más en seguros)

En un entorno regulado, "el agente no debería haber hecho eso" no vale: hay que **impedir** que lo haga y **dejar traza** de quién aprobó qué. Los hooks convierten el *human-in-the-loop* de buena intención en un control que no se puede saltar. Es exactamente lo que hace vendible una plataforma agéntica a un cliente regulado.

---

## Relación con otras piezas

- **[[ai-governance]]** — Los hooks ejecutan lo que la gobernanza exige
- **[[prompt-injection]]** — Un hook puede ser una capa de defensa ante acciones inducidas
- **[[autonomous-coding-agents]]** — Cuanto más autónomo el agente, más necesarios los gates
- **[[ai-native-sdlc]]** — Los gates viven sobre todo en las etapas Build y Deploy

---

## Referencias

- [Hooks as approval gates — Claude Academy](https://academy.claude.com/courses/ai-native-sdlc-playbook/hooks-as-approval-gates)
