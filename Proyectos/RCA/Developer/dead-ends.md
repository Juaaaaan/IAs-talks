---
type: Concepto
title: "Dead ends — Cosas que se intentaron y no funcionaron en RCA"
description: "Registro de problemas, callejones sin salida y soluciones descartadas en el proyecto RCA. Evita que el equipo repita los mismos errores."
tags: [rca, dead-ends, problemas, ssr, tailwind, supabase]
related: [decision-ssr-zoneless, decision-supabase, contexto-proyecto]
timestamp: "2026-07-06"
---

# Dead ends — Cosas que se intentaron y no funcionaron

> Este fichero es el más valioso del vault. Evita que el equipo gaste horas en caminos que ya se exploraron.

---

## SSR: Transloco SSR loader silencioso

**Problema:** En producción, algunos textos aparecían como claves de traducción en lugar del texto traducido (`home.hero.title` en vez de "Joyas hechas a mano").

**Causa:** El loader de SSR usa `readFileSync` para leer los ficheros de i18n. El path era relativo al directorio de ejecución del servidor, que en Vercel es diferente al path del build.

**Solución:** Usar `path.join(process.cwd(), 'dist/browser/i18n', lang + '.json')` en lugar de un path relativo. Los ficheros de i18n tienen que estar en `public/i18n/` y Angular los copia al build automáticamente.

---

## Tailwind v4: clases de opacidad con tokens personalizados

**Problema:** La clase `bg-surface/80` (fondo semitransparente para el navbar) no generaba la clase CSS correcta.

**Causa:** En Tailwind v4, la opacidad con tokens definidos via `@theme` requiere que el token sea un color en formato compatible (RGBA o HSL). Los tokens del proyecto estaban en HEX.

**Solución:** Definir los colores clave en formato HSL en `tailwind.css` para los que necesiten opacidad: `--color-surface: 24 100% 98%` en lugar de `#fff8f4`.

---

## Angular Signals: `mutate()` deprecado

**Problema:** El código generado por Claude Code usaba `signal.mutate()` que lanzaba warnings de deprecación en la consola.

**Causa:** `mutate()` fue deprecado en Angular 17. Tanto Claude Code como GitHub Copilot lo siguen generando a veces porque está en su training data.

**Solución:** Sustituir siempre `mutate()` por `update()` o `set()`. Está en las reglas de `copilot-instructions.md` pero conviene comprobarlo en code review.

---

## Supabase Realtime en SSR

**Problema:** Error en el servidor al intentar suscribirse al canal de Realtime de Supabase.

**Causa:** Supabase Realtime usa WebSockets. El servidor de SSR no tiene WebSocket disponible.

**Solución:** Envolver la suscripción en `isPlatformBrowser`:
```typescript
if (isPlatformBrowser(this.platformId)) {
  this.supabase.channel('stock_items').on('postgres_changes', ...).subscribe();
}
```

---

## CDK FocusTrap: hidratación con errores

**Problema:** El componente `app-modal` con `cdkTrapFocus` generaba errores de hidratación en SSR (`Hydration error: DOM tree mismatch`).

**Causa:** `CdkTrapFocus` modifica el DOM en el cliente al agregar elementos de foco. El DOM renderizado en el servidor no tiene esos elementos, y la hidratación falla al comparar.

**Solución:** El modal solo se renderiza en el cliente. Usar `@defer` con `on interaction` o un guard `isPlatformBrowser` en el componente que lo abre.

---

## `@cosmix/jira-mcp` en npm

**Problema:** Intento de conectar Claude Desktop a Jira usando el paquete `@cosmix/jira-mcp`.

**Causa:** El paquete devuelve 404 en npm — no existe.

**Solución:** Usar el MCP oficial de Atlassian: `npx mcp-remote https://mcp.atlassian.com/v1/mcp`. Ver configuración en el vault de IAs-talks.
