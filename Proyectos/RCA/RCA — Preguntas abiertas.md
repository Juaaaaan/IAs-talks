# RCA — Preguntas abiertas

> Inbox de dudas sin resolver. Todo lo que está pendiente de decisión — con la clienta, técnico, o de diseño. Mover a [[RCA — Decisiones de arquitectura]] cuando se resuelvan.

---

## Pendientes con la clienta

- [ ] **Umbral de envío gratuito** — ¿A partir de qué importe el envío es gratis? En el código está marcado como `FREE_SHIPPING_THRESHOLD = 50` pero pendiente de confirmar. Impacta directamente al `ShippingService`.

- [ ] **Fotografías reales de producto** — Hasta que las entregue, las imágenes son placeholders de `picsum.photos`. El flujo acordado es: artesana sube fotos → Supabase Storage → `getPublicUrl()`. ¿Cuándo las tendrá?

- [ ] **Datos reales de productos y colecciones** — Los CSV de seed data son de prueba. ¿Cuándo tendremos los nombres, descripciones y precios reales de las piezas?

- [ ] **IBAN para transferencia bancaria** — Necesario para el flujo de pago por transferencia. No incluir en el código — va en variable de entorno o en el dashboard de Supabase.

- [ ] **Colores disponibles para personalización** — La paleta de `/personaliza` tiene Cotton Candy, Golden Hour, Sage Mist, Blush Pink, Midnight Onyx. ¿Son los definitivos?

---

## Pendientes técnicos

- [ ] **Stripe en modo live** — Actualmente en modo test. Antes de producción: activar cuenta Stripe para España, habilitar Bizum, configurar webhook en producción.

- [ ] **Dominio en Vercel** — ¿Cuál es el dominio final del proyecto? Necesario para configurar `APP_URL` en las Edge Functions y los redirects de Stripe Checkout.

- [ ] **Variables de entorno en Vercel** — `SUPABASE_URL`, `SUPABASE_ANON_KEY`, `STRIPE_SECRET_KEY`, `STRIPE_WEBHOOK_SECRET`, `RESEND_API_KEY`, `APP_URL`. Están en `.env` local pero hay que configurarlas en el panel de Vercel antes del deploy de producción.

- [ ] **RLS en tablas de orders** — La tabla `orders` necesita RLS configurado. Actualmente solo `stock_items` y `products` tienen RLS. Revisar antes de Fase 5.

- [ ] **Email de la artesana para notificaciones Resend** — Necesario para configurar el destinatario de las notificaciones de nuevo encargo.

---

## Pendientes de diseño / UX

- [ ] **Estado "reservado" en stock** — El modelo tiene `status: 'available' | 'reserved' | 'sold'`. ¿Qué ve el usuario cuando una pieza está `reserved`? ¿Aparece como no disponible? ¿Se oculta del grid?

- [ ] **Página de error personalizada** — No hay diseño en Figma para 404 ni para errores de pago. Definir comportamiento mínimo antes de producción.

- [ ] **Confirmación de pedido por transferencia** — El flujo está definido (IBAN en pantalla + email), pero ¿qué ve exactamente el usuario en pantalla? No hay mockup para ese estado.

---

## Resueltas (referencia)

- ~~¿ngx-translate o Transloco?~~ → Transloco. SSR con readFileSync loader. Ver [[RCA — Decisiones de arquitectura#ADR-003]]
- ~~¿Google Drive para imágenes?~~ → No. Supabase Storage. Ver [[RCA — Decisiones de arquitectura#ADR-006]]
- ~~¿Panel de admin?~~ → No. Dashboard de Supabase es suficiente.
- ~~¿Área privada de usuarios?~~ → No. Decisión explícita de la clienta.
- ~~¿Prefijo de selector rca- o app-?~~ → `app-`. `rca-` genera warnings de lint con Angular CLI.
