---
type: Indice
title: "RCA Wiki LLM — Índice"
description: "Mapa de navegación del vault de conocimiento del proyecto Resin Craft Art. Memoria técnica y de equipo en formato OKF."
tags: [indice, rca, wiki-llm, angular, e-commerce]
timestamp: "2026-07-06"
---

# RCA Wiki LLM — Índice

Este vault contiene la **memoria del proyecto Resin Craft Art** — todo el conocimiento que no está en el código pero que es igual de importante.

---

## Estructura

```
Proyectos/RCA/
├── index.md                    ← estás aquí
├── Developer/
│   ├── decisiones-arquitectura.md
│   ├── decision-no-ngrx.md
│   ├── decision-ssr-zoneless.md
│   ├── decision-supabase.md
│   ├── dead-ends.md
│   ├── estado-sprint-actual.md
│   └── contexto-proyecto.md
└── Equipo/
    ├── (pendiente — perfiles del equipo)
```

---

## Proyecto en una frase

Resin Craft Art es una tienda online Angular 21 SSR para una artesana que vende joyas de resina UV, resina epoxi y acero inoxidable. Piezas por encargo + stock limitado. Pagos con Stripe (tarjeta + Bizum + transferencia).

## Estado actual (julio 2026)

| Fase | Épica | Estado |
|------|-------|--------|
| Fase 1 | Setup y Fundamentos | ✅ En revisión |
| Fase 2 | Componentes Primitivos | ✅ En revisión |
| Fase 3 | Páginas y Componentes | 🟡 En curso |
| Fase 4 | Estado y Servicios | 🔵 Por hacer |
| Fase 5 | Pagos y Notificaciones | 🔵 Por hacer |
| Fase 6 | Producción y Despliegue | 🔵 Por hacer |

## Entradas rápidas para agentes

- ¿Por qué Angular y no Next.js? → [[decisiones-arquitectura]]
- ¿Por qué no usamos NgRx? → [[decision-no-ngrx]]
- ¿Qué se intentó y no funcionó? → [[dead-ends]]
- ¿Qué está en curso ahora? → [[estado-sprint-actual]]
- ¿Qué nunca se debe tocar? → [[contexto-proyecto]]
