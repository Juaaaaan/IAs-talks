---
type: Concepto
title: "Estado del sprint actual — Proyecto RCA"
description: "Estado actual del proyecto RCA a julio 2026: qué está hecho, qué está en curso y qué está pendiente. Extraido de Jira."
tags: [rca, sprint, estado, jira, tareas]
related: [contexto-proyecto, decisiones-arquitectura]
timestamp: "2026-07-06"
---

# Estado del sprint actual — Proyecto RCA

*Última actualización: julio 2026 — extraído de Jira `da-ju-ia-talks.atlassian.net`*

---

## Resumen ejecutivo

| Fase | Épica Jira | Estado | Issues |
|------|-----------|--------|--------|
| Fase 1 — Setup y Fundamentos | RCA-1 | ⚠️ En revisión | RCA-7 a RCA-13 |
| Fase 2 — Componentes Primitivos | RCA-2 | ⚠️ En revisión | RCA-14 a RCA-19 |
| Fase 3 — Páginas y Componentes | RCA-3 | 🟡 En curso | RCA-20 a RCA-28 |
| Fase 4 — Estado y Servicios | RCA-4 | 🔵 Por hacer | RCA-29 a RCA-34 |
| Fase 5 — Pagos y Notificaciones | RCA-5 | 🔵 Por hacer | RCA-35 a RCA-40 |
| Fase 6 — Producción y Despliegue | RCA-6 | 🔵 Por hacer | RCA-41 a RCA-47 |

> ⚠️ Fases 1 y 2 están "En revisión" porque todas sus tareas están completadas pero las épicas no se han cerrado formalmente en Jira. Hay que cerrarlas manualmente.

---

## Fase 3 en detalle — Lo que está en curso ahora

| Issue | Tarea | Estado |
|-------|-------|--------|
| RCA-20 | app-navbar y app-footer definitivos (SSR + i18n) | ✅ Listo |
| RCA-21 | app-cart-drawer: sidebar de carrito con Signals | 🔵 Por hacer |
| RCA-22 | app-product-card: componente de dominio SSR-safe | 🔵 Por hacer |
| RCA-23 | Página Home (/): hero, categorías, featured, proceso | 🔵 Por hacer |
| RCA-24 | Página Colecciones (/colecciones): bento grid | 🔵 Por hacer |
| RCA-25 | Página Stock (/stock): catálogo grid 4 columnas | 🔵 Por hacer |
| RCA-26 | Página Personaliza (/personaliza): formulario 6 pasos | 🔵 Por hacer |
| RCA-27 | Página Cuidados (/cuidados): tiempos y care instructions | 🔵 Por hacer |
| RCA-28 | Página Contacto (/contacto): formulario + links directos | 🔵 Por hacer |

**Prioridad recomendada esta semana:**
1. **RCA-22** (app-product-card) — bloqueante para Home, Stock y Colecciones
2. **RCA-21** (app-cart-drawer) — necesario para que el navbar tenga funcionalidad de carrito
3. **RCA-23** (Home) — primera página visible, valida la arquitectura end-to-end

---

## Lo que NO se debe iniciar todavía

- **Fase 4** (CartService, StockService, ShippingService) no debe iniciarse hasta tener al menos RCA-22 y RCA-23 listos. Los servicios necesitan componentes donde conectarse para poder probarlos.
- **Fase 5** (Pagos) bloqueada por Fase 4.
- **Fase 6** (Producción) al final. RCA-47 (confirmar datos con la cliente) puede hacerse en paralelo.

---

## Datos pendientes de confirmar con la cliente (RCA-47)

Estos datos son necesarios antes de la Fase 6 pero no bloquean el desarrollo:

- ✅ IBAN para transferencia bancaria
- ✅ Número de WhatsApp para enlace directo en /contacto
- ✅ Email para notificaciones de encargos
- ✅ Umbral de envío gratuito (pendiente decidir: ¿a partir de cuántos euros?)
- ✅ Fotografías reales de productos (ahora hay placeholders de picsum.photos)
