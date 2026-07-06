---
type: Concepto
title: "Contexto del proyecto RCA — Qué nunca debes tocar"
description: "Información de contexto del proyecto Resin Craft Art: cliente, objetivo, restricciones y cosas que nunca deben modificarse sin consultar."
tags: [rca, contexto, cliente, restricciones, reglas]
related: [decisiones-arquitectura, dead-ends, estado-sprint-actual]
timestamp: "2026-07-06"
---

# Contexto del proyecto RCA

---

## El proyecto en una frase

Resin Craft Art es la tienda online de una artesana española que vende joyas hechas a mano con resina UV, resina epoxi y acero inoxidable. Las piezas son principalmente por encargo; hay stock limitado de algunas piezas ya fabricadas.

---

## La cliente

- Artesana autodidacta, aprendiz solitaria. La web le permite vender sin intermediarios.
- No tiene conocimientos técnicos. La app tiene que funcionar sola, sin intervención técnica suya.
- La paleta de la marca: tonos pastel salmón y blanco. Color de acento: `#f5e4d7`. Nombre del sistema de diseño: **Artisanal Ether**.
- **Política de pedidos:** ningún pedido se confirma ni se fabrica hasta que hay conversación directa con la cliente (por email o WhatsApp) y el pago está confirmado.

---

## Restricciones de negocio importantes

**El pedido nunca se inicia automáticamente.** El formulario de /personaliza y el de /contacto envían una notificación a la artesana, pero el encargo no comienza hasta la conversación directa. Esto es una decisión de negocio deliberada, no un bug.

**Sin sistema de usuarios.** Los clientes no tienen cuenta. El checkout es anónimo. No hay login, no hay historial de pedidos visible al cliente. Todo se gestiona por email.

**Fotos placeholder hasta la Fase 6.** Las imágenes actuales son de `picsum.photos`. Son temporales. No enviar la web a clientes reales hasta sustituirlas (RCA-43).

---

## Lo que nunca se debe modificar sin consultar

- **`src/tailwind.css`** — los design tokens de Artisanal Ether. Cambiar un color afecta a toda la app.
- **`public/i18n/es.json` y `en.json`** — las traducciones. Añadir keys está bien; borrar o renombrar existentes rompe SSR silenciosamente.
- **Las políticas RLS de Supabase** — nunca desactivar RLS en producción.
- **La lógica de no-auto-confirmación de pedidos** — el flujo de /personaliza envía una notificación pero no crea un pedido. Es intencional.
- **El IBAN y datos de contacto** — cuando se añadan, son datos reales de la artesana. No publicar en logs, comentarios de código ni en el repositorio público.

---

## Stack completo

| Tecnología | Versión | Para qué |
|-----------|---------|----------|
| Angular | 21 | Framework frontend |
| @angular/ssr | 21 | Server-Side Rendering |
| Tailwind CSS | v4 | Estilos con design tokens |
| Supabase | Latest | PostgreSQL + Storage + Realtime |
| Transloco | Latest | i18n browser + SSR |
| Stripe | Latest | Pagos (tarjeta + Bizum + transferencia) |
| Resend | Latest | Emails transaccionales |
| Vercel | N/A | Despliegue SSR |
| Husky | Latest | Pre-commit hooks |
| ESLint + angular-eslint | Latest | Linting |
| Karma + Jasmine | Latest | Tests unitarios |

---

## Comandos habituales

```bash
npm start                           # Dev server http://localhost:4200
npm run build                       # Build de producción
npm test                            # Tests unitarios
npm run test:coverage               # Cobertura (mínimo 80%)
npm run lint                        # ESLint
npm run serve:ssr:Resin-Craft-Art   # SSR local http://localhost:4000
```
