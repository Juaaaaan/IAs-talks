---
type: Concepto
title: "Decisión: SSR + Zoneless en Angular 21"
description: "Por qué usamos SSR y zoneless change detection en el proyecto RCA, y qué implica para el desarrollo."
tags: [rca, angular, ssr, zoneless, rendimiento, decision]
related: [decisiones-arquitectura, dead-ends, contexto-proyecto]
timestamp: "2026-07-06"
---

# Decisión: SSR + Zoneless en Angular 21

---

## SSR — Por qué

**Motivo principal: SEO.** Una tienda de e-commerce necesita que los buscadores indexen los productos. Sin SSR, el HTML inicial está vacío y Google no ve el contenido.

**Motivo secundario: rendimiento percibido.** El First Contentful Paint es más rápido porque el servidor ya renderiza el HTML. El cliente hace hydration en segundo plano.

**Cómo está configurado:**
- `@angular/ssr` con Express server en `src/server.ts`
- `RenderMode.Prerender` para todas las rutas en `app.routes.server.ts`
- Hydration activada con `withEventReplay()`

---

## Zoneless — Por qué

**Motivo: rendimiento y preparación para el futuro.** Zone.js intercepta todos los eventos async para disparar change detection. Con Signals, ya no necesitamos que Zone.js haga ese trabajo — los signals notifican los cambios directamente.

**Lo que cambia:** la change detection ya no es automática. Solo se ejecuta cuando un signal cambia. Esto es mejor en rendimiento pero requiere disciplina.

**Configurado en `app.config.ts`:**
```typescript
providers: [
  provideZonelessChangeDetection(), // No Zone.js
  provideClientHydration(withEventReplay())
]
```

---

## Lo que implica para el desarrollo

### Regla 1: Nunca acceder a APIs de browser directamente

En SSR, no existe `window`, `document`, `localStorage`. Si accedes a ellos directamente, el servidor rompe.

```typescript
// ❌ MAL — rompe en SSR
const stored = localStorage.getItem('cart');

// ✅ BIEN — SSR-safe
if (isPlatformBrowser(this.platformId)) {
  const stored = localStorage.getItem('cart');
}
```

### Regla 2: `OnPush` en todos los componentes

Sin Zone.js, la change detection no se dispara automáticamente. `OnPush` + Signals es la combinación correcta.

### Regla 3: `NgOptimizedImage` para imágenes

SSR requiere dimensiones conocidas de las imágenes. `NgOptimizedImage` las gestiona correctamente y evita errores de hidratación.

---

## Problemas conocidos con SSR en este proyecto

**Transloco SSR loader:** el loader del servidor usa `readFileSync`. Si los ficheros de traducción no están en `public/i18n/` en el momento del build, SSR falla silenciosamente (devuelve las keys sin traducir).

**Supabase Realtime en SSR:** Supabase Realtime usa WebSockets. En el servidor, no hay WebSocket. El `StockService` tiene que comprobar `isPlatformBrowser` antes de suscribirse al canal de Realtime.

Ver [[dead-ends]] para más problemas encontrados.
