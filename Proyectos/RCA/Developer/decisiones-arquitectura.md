---
type: Concepto
title: "Decisiones de arquitectura — Proyecto RCA"
description: "Resumen de las principales decisiones técnicas del proyecto Resin Craft Art y el razonamiento detrás de cada una."
tags: [rca, arquitectura, angular, decisiones, tecnologia]
related: [decision-no-ngrx, decision-ssr-zoneless, decision-supabase, dead-ends]
timestamp: "2026-07-06"
---

# Decisiones de arquitectura — Proyecto RCA

---

## Por qué Angular y no Next.js o Nuxt

**Decisión:** Angular 21 con SSR.

**Razón:** El desarrollador tiene expertise en Angular. Cambiar a React/Vue solo para este proyecto suponía un coste de aprendizaje alto sin un beneficio claro para una tienda de este tamaño. Angular 21 con `@angular/ssr` cubre los requisitos de SEO sin necesidad de cambiar el stack.

**Compromiso asumido:** Angular genera más boilerplate que Next.js. Se mitiga con standalone components y el CLI.

---

## Por qué Tailwind v4 y no CSS modules o SCSS puro

**Decisión:** Tailwind CSS v4 con design tokens personalizados en `src/tailwind.css` via `@theme`.

**Razón:** El sistema de diseño Artisanal Ether requiere tokens consistentes (colores, tipografía, espaciados) que se usen en toda la app. Tailwind v4 con `@theme` permite definirlos una vez y usarlos en todos los componentes sin clases arbitrarias.

**Lo que NO se debe hacer:** usar valores de color o spacing hardcodeados (ej. `#fff8f4` o `px-4`). Siempre usar los tokens: `bg-surface`, `px-sm`, `text-on-surface`.

---

## Por qué Supabase y no Firebase o un backend propio

**Decisión:** Supabase (PostgreSQL + Storage + Realtime + RLS).

**Razón:** La artesana necesita stock en tiempo real (cuando alguien compra, el stock se actualiza instantáneamente para todos los usuarios). Supabase Realtime cubre esto sin infraestructura adicional. PostgreSQL es más predecible que Firestore para queries relacionales (productos con imágenes, stock por producto).

**Lo que NO se debe hacer:** desactivar RLS en ninguna tabla. Las políticas están configuradas para lectura pública en productos e imágenes, escritura solo autenticada.

Ver [[decision-supabase]] para más detalle.

---

## Por qué Transloco y no Angular i18n nativo

**Decisión:** Transloco con loaders diferenciados browser/SSR.

**Razón:** Angular i18n nativo requiere builds separados por idioma, lo cual complica el despliegue en Vercel. Transloco carga las traducciones en runtime y tiene loaders específicos para SSR (filesystem) y browser (HTTP), lo que permite un único build con múltiples idiomas.

**Precaución:** El loader de SSR usa `readFileSync` desde el filesystem. Los ficheros de traducciones deben estar en `public/i18n/`. Si se mueven, SSR rompe silenciosamente.

---

## Por qué Vercel y no Netlify o servidor propio

**Decisión:** Vercel para despliegue SSR.

**Razón:** Vercel tiene soporte nativo para Angular SSR desde la configuración del proyecto. El CI/CD es automático desde GitHub. La artesana no tiene conocimientos técnicos y necesita algo que funcione sin intervención.

---

## Por qué Stripe y no PayPal o Redsys

**Decisión:** Stripe con Bizum activado para España + opción de transferencia bancaria.

**Razón:** Bizum es el método de pago más usado en España para compras pequeñas. Stripe lo soporta nativamente. PayPal tiene comisiones más altas y Redsys requiere contrato bancario. La transferencia bancaria se incluye porque algunos clientes mayores lo prefieren.

**Pendiente confirmar con la cliente:** IBAN, número de WhatsApp, email de contacto y umbral de envío gratuito. Ver RCA-47.
