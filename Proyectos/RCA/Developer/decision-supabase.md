---
type: Concepto
title: "Decisión: Arquitectura Supabase en RCA"
description: "Estructura de la base de datos, Storage y Realtime en el proyecto RCA. Políticas RLS y decisiones de esquema."
tags: [rca, supabase, postgresql, realtime, rls, storage, decision]
related: [decisiones-arquitectura, dead-ends]
timestamp: "2026-07-06"
---

# Decisión: Arquitectura Supabase en RCA

---

## Tablas principales

| Tabla | Para qué | RLS |
|-------|----------|-----|
| `products` | Catálogo de joyas | Lectura pública |
| `product_images` | Imágenes por producto | Lectura pública |
| `stock_items` | Stock disponible por producto | Lectura pública, escritura solo webhook |
| `categories` | Categorías (pendientes, colgantes...) | Lectura pública |
| `collections` | Colecciones temáticas | Lectura pública |

**No hay tabla de usuarios.** Los clientes no tienen cuenta. El checkout es anónimo — solo email y datos de envío para la confirmación.

---

## Storage buckets

- `product-images` — imágenes de productos. URLs públicas. Subida solo desde el panel de Supabase (no desde la app).

---

## Realtime en `stock_items`

Sustabase Realtime está activado en la tabla `stock_items`. Cuando el webhook de Stripe actualiza el stock después de un pago, todos los usuarios conectados ven el cambio instantáneamente sin recargar la página.

**Importante:** el `StockService` solo se suscribe al canal de Realtime en el browser. En SSR no hay WebSocket. Ver [[decision-ssr-zoneless]].

---

## RLS — Reglas importantes

**Nunca desactivar RLS** en ninguna tabla, aunque parezca que simplifica el desarrollo local. Si RLS está desactivado, cualquier usuario puede escribir en cualquier tabla.

Las políticas actuales:
- `products`, `product_images`, `categories`, `collections`: `SELECT` pública para todos.
- `stock_items`: `SELECT` pública, `UPDATE` solo para el rol de service_role (usado por el webhook de Stripe vía Edge Function).

---

## Seed data de desarrollo

Las tablas tienen datos de desarrollo con imágenes de `picsum.photos`. Antes de lanzar a producción hay que reemplazarlos con fotos reales y precios definitivos. Ver RCA-43 y RCA-44.

---

## Edge Functions usadas

| Función | Para qué |
|---------|----------|
| `create-checkout-session` | Crea una Stripe Checkout Session con los items del carrito (RCA-36) |
| `stripe-webhook` | Recibe eventos de Stripe y actualiza el stock en Supabase (RCA-37) |

Ambas funciones viven en Supabase Edge Functions (Deno). Las claves de Stripe están en las variables de entorno de Supabase, no en el frontend.
