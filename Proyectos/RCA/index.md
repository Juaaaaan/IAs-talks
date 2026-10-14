---
type: Indice
title: "RCA Wiki LLM — Índice"
description: "Mapa de navegación del vault de conocimiento del proyecto Resin Craft Art. Memoria técnica y de equipo en formato OKF."
tags: [indice, rca, wiki-llm, angular, e-commerce]
timestamp: "2026-10-14"
---

# RCA Wiki LLM — Índice

Este vault contiene la **memoria del proyecto Resin Craft Art** — todo el conocimiento que no está en el código pero que es igual de importante.

> **Fusión 2026-10-14:** esta nota fusiona el contenido de la antigua `RCA — Índice.md` (2026-06-23, ahora retirada) con este `index.md` (originalmente 2026-07-06). Se conservan los enlaces externos, el stack y el contexto de negocio que solo estaban en la nota antigua; se descartan sus wikilinks a notas (`RCA — Decisiones de arquitectura`, `RCA — Aprendizajes Angular 21`, `RCA — Graph Report`, `RCA — Preguntas abiertas`) que no existen en el repositorio — probablemente quedaron huérfanos tras una reorganización de nombres de fichero.

---

## Estructura

```
Proyectos/RCA/
├── index.md                    ← estás aquí
├── Developer/
│   ├── decisiones-arquitectura.md
│   ├── decision-no-ngrx.md
│   ├── decision-no-dark-mode.md
│   ├── decision-responsive.md
│   ├── decision-ssr-zoneless.md
│   ├── decision-supabase.md
│   ├── dead-ends.md
│   ├── estado-sprint-actual.md
│   ├── contexto-proyecto.md
│   ├── developer-agent-claude-rca.md      ← movido desde Recursos/
│   ├── developer-agent-github-rca.md      ← movido desde Recursos/
│   ├── reviewer-agent-claude-rca.md       ← movido desde Recursos/
│   └── reviewer-agent-github-rca.md       ← movido desde Recursos/
├── Instrucciones/                          ← carpeta nueva (2026-10-14)
│   ├── agents-md-rca.md
│   ├── components-instructions-rca.md
│   ├── copilot-instructions-rca.md
│   └── testing-instructions-rca.md
├── Tareas/                                 ← carpeta nueva (2026-10-14)
│   ├── task-rca-20.md
│   └── task-rca-28.md
└── Equipo/
    ├── nivel-equipo.md
    ├── assessment-framework.md
    ├── okr-capacidad-ia-equipo.md
    ├── resumen-capacidad-ia-agentica-equipo.md
    └── perfil-*.md (8 perfiles individuales del equipo)
```

> `Instrucciones/` y `Tareas/` agrupan ficheros que antes vivían sueltos en `Recursos/` (configuración de agentes y de IDE del propio proyecto RCA, no referencias técnicas generales). `Developer/` ya existía y ahora también recoge los 4 ficheros de agentes developer/reviewer que antes estaban en `Recursos/`.

---

## Proyecto en una frase

Resin Craft Art es una tienda online Angular 21 SSR para una artesana que vende joyas de resina UV, resina epoxi y acero inoxidable. Piezas por encargo + stock limitado. Pagos con Stripe (tarjeta + Bizum + transferencia).

## Contexto del proyecto

Tienda online para una artesana que fabrica joyería con resina UV, resina epoxi y acero inoxidable. Dos flujos de venta: stock inmediato (Stripe) y encargos personalizados (formulario → conversación directa → pago). Sin panel admin, sin autenticación, sin área privada. Stock gestionado directamente desde el Dashboard de Supabase.

## Stack de un vistazo

```
Angular 21 · SSR · Zoneless · Signals
Tailwind v4 (CSS-first) · SCSS
Supabase (PostgreSQL + Storage + Realtime)
Transloco · Stripe + Bizum · Resend · Vercel
```

## Enlaces externos

| Recurso | URL |
|---------|-----|
| Repositorio GitHub | https://github.com/Juaaaaan/Resin-Craft.git |
| Jira (RCA) | https://da-ju-ia-talks.atlassian.net/jira/software/projects/RCA |
| Figma | https://www.figma.com/design/kAEGwQ9NFWaPwyGqI0s8MT/Resin-Craft-Art |
| Supabase | https://rrrgvoxenaabqymhtpqd.supabase.co |
| Vercel | https://vercel.com |

## Estado actual

> ⚠️ Última confirmación: julio 2026. Con charlas hasta la 23 (octubre 2026) usando RCA como vehículo de demo, es probable que algunas fases hayan avanzado — pendiente de confirmar con Juan antes de dar esta tabla por buena.

| Fase | Épica | Estado (jul 2026) |
|------|-------|--------|
| Fase 1 | Setup y Fundamentos | ✅ Completada |
| Fase 2 | Componentes Primitivos | ✅ Completada |
| Fase 3 | Páginas y Componentes | 🟡 En curso |
| Fase 4 | Estado y Servicios | 🔵 Por hacer |
| Fase 5 | Pagos y Notificaciones | 🔵 Por hacer |
| Fase 6 | Producción y Despliegue | 🔵 Por hacer |

## Entradas rápidas para agentes

- ¿Por qué Angular y no Next.js? → [[decisiones-arquitectura]]
- ¿Por qué no usamos NgRx? → [[decision-no-ngrx]]
- ¿Por qué no hay dark mode? → [[decision-no-dark-mode]]
- ¿Cómo se gestiona el responsive? → [[decision-responsive]]
- ¿Por qué SSR zoneless? → [[decision-ssr-zoneless]]
- ¿Por qué Supabase? → [[decision-supabase]]
- ¿Qué se intentó y no funcionó? → [[dead-ends]]
- ¿Qué está en curso ahora? → [[estado-sprint-actual]]
- ¿Qué nunca se debe tocar? → [[contexto-proyecto]]
- ¿Cómo se configuran los agentes developer/reviewer? → `Developer/developer-agent-claude-rca.md`, `Developer/developer-agent-github-rca.md`, `Developer/reviewer-agent-claude-rca.md`, `Developer/reviewer-agent-github-rca.md`
- ¿Qué instrucciones sigue Copilot en este proyecto? → `Instrucciones/copilot-instructions-rca.md`, `Instrucciones/components-instructions-rca.md`, `Instrucciones/testing-instructions-rca.md`, `Instrucciones/agents-md-rca.md`
- ¿Cómo es un task.md real de este proyecto? → `Tareas/task-rca-20.md`, `Tareas/task-rca-28.md`

## Equipo

`Equipo/` ya no está pendiente — contiene el framework de assessment, el nivel del equipo, el OKR de capacidad IA agéntica, un resumen de capacidad y 8 perfiles individuales de miembros del equipo.
