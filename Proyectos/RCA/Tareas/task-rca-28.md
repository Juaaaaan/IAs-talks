---
type: Recurso
title: "task-rca-28.md — Página Contacto (/contacto)"
description: "Task del issue RCA-28 del proyecto Resin Craft Art. Página de contacto con formulario reactivo, split 60/40, i18n y estados de envío con Signals. Ejemplo avanzado de task.md con spec.md como fuente de verdad."
tags: [recurso, task, rca, angular, contacto, formulario, i18n, signals]
related: [sdd, task-rca-20, agentes-multiples, copilot-instructions]
charla: "Charla 11"
estado: "✅ Publicado"
timestamp: "2026-07-06"
---

# TASK — RCA-28: Página Contacto (`/contacto`)

**Jira:** https://da-ju-ia-talks.atlassian.net/browse/RCA-28
**Especificación completa:** `spec.md` (mismo directorio) — léela entera antes de tocar código, es la fuente de verdad para contenido, validaciones, i18n y criterios de aceptación.
**Diseño visual:** MCP de Stitch, ya conectado en este entorno. Frame de referencia en Figma: `2:470` ("Contacto", 2560×1159px), archivo `Resin Craft Art`.

## Antes de empezar

1. Lee `spec.md` completo.
2. Consulta el diseño vía Stitch MCP para el frame de `/contacto`.
3. Revisa `.claude/CLAUDE.md` (reglas de Angular/TypeScript del proyecto) y `DESIGN.md` (tokens).
4. Mira `src/app/features/customize/customize.component.*` como ejemplo de formulario ya maquetado.
5. Confirma en `app.routes.ts` que la ruta `contacto` ya apunta a `./features/contact/contact.component`.

## Qué construir

Componente `ContactComponent` (`src/app/features/contact/contact.component.ts`) con:

- Header de página (H1 + subtítulo) centrado, full width.
- Split 60/40: formulario (Full Name, Email, Subject, Message, aviso legal, botón submit) + aside.
- Formulario reactivo (`FormGroup`/`FormControl`) con validaciones de `spec.md` §8.
- Estados de envío con Signals (`isSubmitting`, `submitStatus`) — sin integración real de backend.
- Reutilización estricta de `app-input`, `app-select`, `app-textarea`, `app-button`, `app-navbar`, `app-footer`.
- i18n: añade las keys de `spec.md` §9 a `public/i18n/es.json` y `public/i18n/en.json`.
- Placeholders de contacto claramente marcados como pendientes de confirmación.
- Tests unitarios cubriendo los 4 casos de `spec.md` §12.

## Al terminar, ejecuta y confirma que pasan

```bash
npm run lint
npm run test:coverage
npm run build
```

## Explícitamente fuera de alcance

- Integración real de envío de email.
- Tabla nueva en Supabase para mensajes de contacto.
- Inventar datos de contacto reales.

---

> 📌 **Nota de contexto:** este archivo muestra el formato de `task.md` que acompaña a un `spec.md` exhaustivo para delegar una tarea a un agente developer. Ver también [[task-rca-20]] como otro ejemplo previo.
