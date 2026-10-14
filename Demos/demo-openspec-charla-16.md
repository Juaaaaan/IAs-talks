---
type: Demo
title: "Demo — OpenSpec + Claude Code sobre RCA (Charla 16)"
description: "Paso a paso de la demo de Charla 16: ciclo completo de Spec-Driven Development con OpenSpec, desde un ticket de Jira (RCA-21, Cart Drawer) hasta código implementado con Claude Code, sobre el proyecto Resin Craft Art."
tags: [demo, openspec, sdd, claude-code, rca, jira, delta-spec]
related: [charla-16-sdd-herramientas, sdd, agente-ia]
charla: "Charla 16"
estado: "✅ Ejecutada"
timestamp: "2026-08-12"
---

# Demo — OpenSpec + Claude Code sobre RCA (Charla 16)

**Charla:** [[charla-16-sdd-herramientas]]
**Herramienta:** OpenSpec (CLI) + Claude Code
**Proyecto:** Resin Craft Art (RCA) — Angular
**Jira:** `da-ju-ia-talks.atlassian.net` — ticket **RCA-21** (Cart Drawer)
**Duración:** 15-20 min

---

## Objetivo de la demo

Mostrar el ciclo completo de SDD con herramientas, no a mano: de un ticket de Jira de dos frases a código real implementado, pasando por una propuesta estructurada que se revisa *antes* de tocar código.

---

## Preparación previa

- `openspec init` ya ejecutado sobre el repo de RCA, con `claude-code` seleccionado
- Ticket RCA-21 (Cart Drawer) preparado en Jira, visible en pantalla secundaria
- Terminal y editor abiertos, tamaño de fuente verificado para proyección

---

## Paso a paso

### Paso 1 — Proponer el cambio desde el ticket (4 min)

En el chat de Claude Code:

```
Usa OpenSpec para proponer un cambio. Lee las instrucciones de openspec/AGENTS.md.

Contexto del ticket Jira RCA-21:
Título: Cart Drawer
Descripción: Implementar un panel lateral (drawer) que muestre el contenido
del carrito de compra. Se abre al hacer clic en el icono del carrito
en la barra de navegación y permite ver los productos añadidos,
modificar cantidades y proceder al checkout.

Nombre del cambio: cart-drawer
```

**Resultado esperado:** se genera `openspec/changes/cart-drawer/` con cuatro documentos: `proposal.md`, `specs/` (delta spec), `design.md` y `tasks.md`.

### Paso 2 — Revisar la propuesta en pantalla (5 min)

Abrir y comentar en voz alta cada fichero generado antes de implementar — este es el momento pedagógico central: mostrar que el spec se lee y se corrige *antes* de que exista una línea de código.

- `proposal.md` — ¿ha entendido la intención?
- `design.md` — ¿usa las convenciones de Angular de RCA?
- `specs/` — delta spec con escenarios GIVEN/WHEN/THEN
- `tasks.md` — desglose atómico y ordenado

**Resultado esperado:** la audiencia ve que corregir un párrafo de Markdown es mucho más barato que deshacer código ya escrito.

### Paso 3 — Implementar (5 min)

```
Aplica el cambio de OpenSpec cart-drawer. Sigue las instrucciones
de openspec/AGENTS.md para el flujo de apply.
```

**Resultado esperado:** Claude Code ejecuta `tasks.md` tarea a tarea, marcando cada checkbox.

### Paso 4 — Archivar y cerrar el ciclo (3 min)

```
Archiva el cambio cart-drawer de OpenSpec siguiendo las instrucciones
de openspec/AGENTS.md.
```

Mostrar cómo la delta spec se fusiona en el spec principal (`openspec/specs/`), y cerrar con el Git manual (`git checkout -b feat/cart-drawer`, commit, push) — remarcando que aquí es donde OpenSpec se para y el flujo normal de equipo toma el relevo.

---

## Prompts de referencia

```
Usa OpenSpec para proponer un cambio. Lee las instrucciones de openspec/AGENTS.md.
[contexto del ticket]
```

```
Aplica el cambio de OpenSpec [nombre]. Sigue las instrucciones de openspec/AGENTS.md para el flujo de apply.
```

```
Archiva el cambio [nombre] de OpenSpec siguiendo las instrucciones de openspec/AGENTS.md.
```

---

## Plan B

Si `/opsx-apply` falla o se atasca en una tarea: mostrar el `tasks.md` ya marcado de un ensayo previo y narrar el resto en vez de re-ejecutar en directo.

---

## Checklist pre-demo

- [ ] `openspec init` ya ejecutado y verificado sobre RCA
- [ ] Ticket RCA-21 visible y legible en pantalla secundaria
- [ ] Ensayo completo realizado al menos una vez
- [ ] Conexión a internet verificada
