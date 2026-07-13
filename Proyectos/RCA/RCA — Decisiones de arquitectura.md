# RCA — Decisiones de arquitectura

> Registro personal de las decisiones técnicas tomadas en el proyecto y el razonamiento detrás de cada una. No es el GUIDE.md (que documenta el *qué*), sino el *por qué* real.

---

## ADR-001 — Angular 21 con SSR y zoneless

**Decisión:** Angular 21 standalone, `provideZonelessChangeDetection()`, `@angular/ssr`.

**Por qué:** El proyecto sirve como campo de práctica real mientras se construye un producto de producción. Zoneless + Signals es la dirección clara de Angular hacia adelante. SSR es necesario para SEO — una tienda de producto artesanal necesita que Google indexe bien las páginas de colecciones y stock.

**Consecuencia más importante:** Cualquier acceso a APIs de browser (`localStorage`, `window`, `document`) tiene que ir detrás de un guard `isBrowser` o dentro de `afterNextRender()`. Esto no es opcional, rompe el servidor si se ignora.

---

## ADR-002 — Tailwind v4 con configuración CSS-first

**Decisión:** Tailwind v4, configuración en `tailwind.css` con `@theme {}`. Sin `tailwind.config.js`.

**Por qué:** Tailwind v4 es CSS-first por diseño — los tokens viven en el mismo lugar que los estilos. Para un sistema de diseño tan definido como "Artisanal Ether", tener los tokens en `@theme {}` junto al resto de CSS es más coherente que un archivo JS de configuración separado.

**Consecuencia:** Los tokens del sistema de diseño (`--color-primary`, `--font-serif`, etc.) se definen una sola vez en `tailwind.css` y se usan en las clases de Tailwind directamente. No hay duplicación entre config y código.

---

## ADR-003 — Transloco en lugar de ngx-translate

**Decisión:** `@jsverse/transloco` para i18n.

**Por qué:** El problema con ngx-translate en SSR es que el HTTP loader intenta hacer una petición de red durante el render del servidor, lo que causa problemas de timing y en algunos setups falla silenciosamente. Transloco permite un loader diferenciado: HTTP en browser, `readFileSync` en servidor. Cada entorno usa el mecanismo que tiene disponible.

**Consecuencia:** Hay dos configs: `app.config.ts` (browser) y `app.config.server.ts` (SSR). El loader del servidor lee directamente del sistema de archivos con `readFileSync`. Más boilerplate inicial, pero sin sorpresas en producción.

---

## ADR-004 — Supabase sin Auth

**Decisión:** Supabase solo para base de datos, storage y realtime. Sin usuarios ni sesiones.

**Por qué:** La clienta tomó dos decisiones explícitas: no quiere que los compradores tengan área privada, y no quiere panel de administración. Sin ninguna de las dos, Auth no aporta nada — solo añade complejidad y superficie de ataque. El stock se gestiona directamente desde el Dashboard de Supabase, que es suficiente para el volumen esperado.

**Consecuencia:** RLS configurado para lectura pública de productos y stock. Escritura solo desde Edge Functions con la service key. Sin tokens JWT en el cliente.

---

## ADR-005 — Sin librerías de componentes UI

**Decisión:** Componentes 100% propios. Solo `@angular/cdk` para accesibilidad (FocusTrap en modales).

**Por qué:** El sistema de diseño "Artisanal Ether" está completamente definido — paleta, tipografía, espaciado, componentes. Cualquier librería externa introduciría capas de sobreescritura de estilos para llegar al diseño final. El esfuerzo de override supera al de construir desde cero cuando el diseño ya está tan especificado.

**Consecuencia:** Más trabajo inicial en Fase 2. A cambio, control total sobre el output visual y cero conflictos de estilos en el futuro.

---

## ADR-006 — Google Drive descartado para imágenes

**Decisión:** Supabase Storage para todas las imágenes de producto.

**Por qué:** Las URLs de compartición de Google Drive no son URLs directas de imagen. Cuando Angular SSR intenta resolver una imagen durante el render del servidor, la redirección de Drive causa errores CORS. No hay workaround limpio — el único que funciona es un guard `isBrowser` que deja la imagen vacía durante el SSR, lo que arruina el SEO de producto.

**Consecuencia:** Las imágenes actuales usan placeholders de `picsum.photos` hasta que la clienta entregue fotografías reales. El flujo final es: artesana sube fotos → van a Supabase Storage → `getPublicUrl()` devuelve una URL directa que funciona en SSR sin guards.

---

## ADR-007 — Stripe con Bizum activado

**Decisión:** Stripe como pasarela principal con Bizum habilitado para España.

**Por qué:** Bizum tiene una penetración altísima en España para compras online pequeñas. Para el perfil de cliente de una tienda de joyería artesanal española, no ofrecer Bizum es una fricción real. Stripe lo soporta nativamente en su Checkout para cuentas españolas, así que el coste de añadirlo es prácticamente cero.

**Consecuencia:** El tipo de pago `bizum` se añade a `payment_method_types` en la Edge Function de Stripe. Solo disponible para clientes con número de teléfono español vinculado a Bizum.

---

## ADR-008 — Responsive desktop-first

**Decisión:** Implementar diseño responsive con estrategia desktop-first. Breakpoints estándar: tablet 768px, mobile 375px.

**Por qué:** El sistema de diseño Artisanal Ether solo define versión desktop, pero el cliente requiere visualización en tablet y mobile. La estrategia desktop-first es coherente porque ya tenemos el diseño desktop implementado — adaptamos hacia abajo.

**Consecuencia:** Las adaptaciones responsive son decisiones de desarrollo (no hay maquetas de referencia para mobile/tablet). Se documentan en [[decision-responsive]]. Si el equipo de diseño publica maquetas responsive en el futuro, se revisan las adaptaciones.

---

## ADR-009 — Graphify para análisis de arquitectura

**Decisión:** `graphify` (pip install graphify) integrado en el flujo de desarrollo.

**Por qué:** Con 117 archivos y 91k palabras de corpus, el grafo de conocimiento añade valor real. Permite detectar import cycles, identificar god nodes que hay que proteger de cambios, y ver qué comunidades de código han emergido de forma natural. El reporte del 2026-06-22 confirma arquitectura limpia: 0 import cycles, comunidades bien definidas por feature.

**Consecuencia:** Ejecutar `graphify update .` después de cambios significativos de estructura. El graph report se analiza en [[RCA — Graph Report]].
