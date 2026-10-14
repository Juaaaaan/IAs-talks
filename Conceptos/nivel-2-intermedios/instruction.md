---
type: Concepto
title: "Instruction — Reglas automáticas por ruta"
description: "Regla de comportamiento que se aplica automáticamente según patrones de ruta de ficheros dentro de un runtime. Automatiza convenciones por ámbito, pero no sustituye una petición puntual del usuario."
tags: [ai-sdlc-foundation, instruction, rutas, runtime, reglas, provider]
related: [ai-sdlc-foundation, canonical, runtime, provider, copilot-instructions]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Instruction — Reglas automáticas por ruta

> _"No hace falta repetir la norma cada vez si el sistema ya sabe dónde debe aplicarla."_

---

## Qué es

En AI SDLC Foundation, **Instruction** es una regla de comportamiento que se activa automáticamente cuando un fichero o tarea cae dentro de un patrón de ruta definido. Sirve para acotar convenciones de forma contextual, por ejemplo según carpeta, extensión o tipo de entregable. No es un mensaje manual del usuario, sino una automatización ligada al ámbito correcto.

---

## Papel en AI SDLC Foundation

Instruction permite que las normas viajen con la estructura del proyecto en lugar de depender de recordatorios humanos. Desde la capa [[canonical]] se pueden definir estas reglas y proyectarlas al [[runtime]] del [[provider]] correspondiente. Así, el agente recibe instrucciones precisas justo cuando trabaja en el área afectada.

---

## Cómo funciona

La regla declara un patrón de rutas y el comportamiento asociado a ese patrón. Cuando el runtime detecta que la tarea afecta a un fichero coincidente, carga la instrucción y la incorpora al contexto operativo del agente. El límite clave es el alcance: si el patrón es demasiado amplio, la regla termina condicionando zonas para las que nunca fue diseñada.

---

## Ejemplos prácticos

### Ejemplo 1 — Reglas por ruta para `src/**/*.ts`

Una instruction se aplica solo a ficheros TypeScript que coinciden con `src/**/*.ts` y recuerda las convenciones que el equipo definió para ese ámbito del proyecto. El agente la recibe automáticamente cuando toca ese árbol y no cuando edita documentación o scripts auxiliares.

### Ejemplo 2 — Convenciones de documentación para `docs/**/*.md`

Otra instruction obliga a respetar un tono, una estructura de encabezados y ciertas comprobaciones de enlaces cuando se modifican ficheros de `docs/`. El agente no necesita que el usuario repita esas reglas en cada petición.

---

## Matices y confusiones habituales

- **Cuidado:** Una instruction no es una petición puntual del usuario. Define comportamiento automático condicionado por el ámbito de ruta.
- **Cuidado:** Un patrón demasiado amplio puede aplicar reglas fuera de su contexto y degradar la calidad de la respuesta.
- **Importante:** Si dos instructions solapan sus rutas, hace falta una política clara de prioridad para evitar mensajes contradictorios.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Muestra dónde encajan las instructions dentro del dominio.
- **[[canonical]]** — Es el origen neutral desde el que se definen y versionan estas reglas.
- **[[runtime]]** — Evalúa las rutas afectadas y activa la instruction correspondiente.
- **[[provider]]** — Recibe la adaptación concreta del formato de reglas.
- **[[copilot-instructions]]** — Ayuda a conectar esta idea con el mecanismo equivalente en GitHub Copilot.
