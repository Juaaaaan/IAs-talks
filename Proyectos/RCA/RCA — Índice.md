# RCA — Resin Craft Art

> Mapa de contenido del proyecto. Punto de entrada para todo lo relacionado con RCA en este vault.
> Última actualización: 2026-06-23

---

## Estado actual

| Fase | Descripción | Estado |
|------|-------------|--------|
| Fase 1 | Setup y fundamentos | ✅ Completada |
| Fase 2 | Componentes primitivos | ✅ Completada |
| Fase 3 | Páginas y componentes | 🚧 En curso |
| Fase 4 | Estado y servicios | ⏳ Pendiente |
| Fase 5 | Pagos y notificaciones | ⏳ Pendiente |
| Fase 6 | Producción y despliegue | ⏳ Pendiente |

---

## Notas del proyecto

- [[RCA — Decisiones de arquitectura]]
- [[RCA — Aprendizajes Angular 21]]
- [[RCA — Graph Report]]
- [[RCA — Preguntas abiertas]]

---

## Enlaces externos

| Recurso | URL |
|---------|-----|
| Repositorio GitHub | https://github.com/Juaaaaan/Resin-Craft.git |
| Jira (RCA) | https://da-ju-ia-talks.atlassian.net/jira/software/projects/RCA |
| Figma | https://www.figma.com/design/kAEGwQ9NFWaPwyGqI0s8MT/Resin-Craft-Art |
| Supabase | https://rrrgvoxenaabqymhtpqd.supabase.co |
| Vercel | https://vercel.com |

---

## Stack de un vistazo

```
Angular 21 · SSR · Zoneless · Signals
Tailwind v4 (CSS-first) · SCSS
Supabase (PostgreSQL + Storage + Realtime)
Transloco · Stripe + Bizum · Resend · Vercel
```

---

## Contexto del proyecto

Tienda online para una artesana que fabrica joyería con resina UV, resina epoxi y acero inoxidable. Dos flujos de venta: stock inmediato (Stripe) y encargos personalizados (formulario → conversación directa → pago). Sin panel admin, sin autenticación, sin área privada. Stock gestionado directamente desde el Dashboard de Supabase.
