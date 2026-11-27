---
type: Concepto
title: "AGENTS.md — Un sitio común para instruir a los agentes"
description: "Convención abierta: un fichero Markdown en el repositorio con las indicaciones que un agente de código necesita sobre el proyecto, como comandos, convenciones y límites."
tags: [agents-md, instrucciones, agentes, repositorio, estandar]
related: [copilot-instructions, instruction, context-engineering, skills, intent-md]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# AGENTS.md

> _"El README es para las personas. AGENTS.md, para los agentes."_

---

## Qué es

**AGENTS.md** es una convención abierta para poner en un lugar predecible las **indicaciones para agentes** que trabajan en un repositorio. OpenAI aportó esta convención a la **Agentic AI Foundation**, creada bajo la Linux Foundation en diciembre de 2025.

El soporte y la forma de leerlo dependen de cada herramienta: compruébalo en su documentación.

---

## Qué suele incluir

- Cómo instalar, probar y compilar
- Convenciones del proyecto
- Qué zonas no se deben tocar
- Cómo comprobar que un cambio está bien

---

## Relación con copilot-instructions

| | AGENTS.md | [[copilot-instructions]] |
|---|---|---|
| **Enfoque** | Convención compartida entre herramientas | Mecanismo propio de GitHub Copilot |
| **Ubicación habitual** | Raíz del repositorio (y a veces subcarpetas) | Carpeta \`.github/\` |

---

## Buenas prácticas

- **Corto y concreto:** ocupa contexto
- **Actualizado:** una instrucción obsoleta confunde
- **Sin secretos**
- Revisar sus cambios como código: **influye en lo que hace el agente**
- No sustituye a los permisos: es una indicación, no una barrera

---

## Relación con otras piezas

- **[[instruction]]** — Reglas por ruta en AI SDLC Foundation
- **[[context-engineering]]** — Parte del contexto persistente
- **[[skills]]** — Conocimiento de comportamiento reutilizable
- **[[intent-md]]** — Otro fichero, centrado en la intención de un cambio

---

## Referencias

- [AGENTS.md](https://agents.md/)
