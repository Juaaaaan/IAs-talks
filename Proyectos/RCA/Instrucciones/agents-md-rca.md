---
type: Recurso
title: "AGENTS.md — Proyecto RCA"
description: "Fichero de referencia del proyecto RCA. Define el comportamiento autónomo del agente: qué leer antes de tocar código, qué verificar antes de terminar, qué nunca hacer."
tags: [recurso, agents, rca, copilot, claude, autonomo]
related: [agentes-multiples, copilot-instructions, charla-08-copilot-instrucciones]
charla: "Charla 8"
estado: "✅ Publicado"
timestamp: "2026-07-02"
---

# AGENTS.md — Proyecto RCA

> Fichero de referencia usado en la demo de la Charla 8.
> Vive en la raíz del proyecto Resin Craft Art.

---

# AGENTS.md — Resin Craft Art

Este fichero define cómo debe comportarse el agente cuando trabaja de forma autónoma en el proyecto RCA.
Léelo completo antes de iniciar cualquier tarea.

## Antes de tocar cualquier fichero

1. Leer el `task.md` de la tarea asignada. Si no existe, preguntar antes de continuar.
2. Analizar la estructura del proyecto — carpetas, componentes existentes, servicios, rutas.
3. Comprobar si existe `graphify-out/graph.json`. Si existe, usarlo para entender la arquitectura.
4. Leer los ficheros de contexto relevantes: `CLAUDE.md`, `copilot-instructions.md`, `AGENTS.md`.
5. Identificar componentes reutilizables antes de crear nuevos.

Si hay dudas sobre lógica de negocio, **preguntar antes de implementar**.

## Antes de dar una tarea por terminada

1. `npm run test:coverage` — cobertura mínima 80% por fichero
2. `npm run lint` — sin errores de lint
3. `npm run build` — build de producción sin errores
4. Comprobar si existe `playwright.config.*`. Si existe, ejecutar E2E relevantes.
5. Partir desde `develop`. Rama: `feature/rca-XX-descripcion` o `fix/rca-XX-descripcion`.
6. Commit: `feat(rca-XX): descripción` siguiendo Conventional Commits.
7. Pull Request hacia `develop`.

## Lo que el agente nunca debe hacer

- ❌ Modificar `CLAUDE.md`, `AGENTS.md`, `copilot-instructions.md`
- ❌ Modificar `src/styles.scss` o `src/tailwind.css`
- ❌ Modificar el `.gitignore`
- ❌ Actualizar dependencias sin confirmación explícita
- ❌ Borrar ficheros sin confirmar
- ❌ Commit directo a `main` o `develop`
