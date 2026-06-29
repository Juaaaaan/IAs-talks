# task-rca-20.md — app-navbar y app-footer definitivos

> Fichero de referencia usado en la demo de la Charla 8.
> En el proyecto RCA vive en `docs/tasks/task-rca-20.md`.

---

**Issue Jira:** RCA-20
**Épica:** RCA-3 — Páginas y Componentes
**Estado:** 🟡 En curso
**Rama:** `feature/rca-20-navbar-footer-ssr-i18n`

---

## Objetivo

Implementar el `app-navbar` y el `app-footer` definitivos del proyecto Resin Craft Art,
con soporte completo de SSR e i18n mediante Transloco.

---

## Funcionalidad esperada

### app-navbar

- Logo de la marca alineado a la izquierda
- Navegación: Home, Colecciones, Stock, Personaliza, Cuidados, Contacto
- Comportamiento sticky
- Fondo semitransparente: `bg-surface/80 backdrop-blur-[10px]`
- Textos traducibles con Transloco
- Compatible con SSR

### app-footer

- Logo o nombre de la marca
- Links secundarios: política de privacidad, términos, contacto
- Copyright con año dinámico
- Textos traducibles con Transloco
- Compatible con SSR

---

## Criterios de aceptación

- [ ] Navbar renderiza correctamente en SSR (sin errores de hidratación)
- [ ] Footer renderiza correctamente en SSR
- [ ] Textos traducidos en todos los idiomas configurados
- [ ] Navbar sticky en todas las páginas
- [ ] Año del copyright dinámico
- [ ] Cobertura de tests ≥ 80% en ambos componentes
- [ ] Sin errores de lint
- [ ] Build de producción sin errores

---

## Convenciones

- Standalone, OnPush, `inject()`, Signals, control flow nativo
- Tokens Artisanal Ether — no colores hardcodeados
- `NgOptimizedImage` para el logo
- No acceder a `window` ni `document` directamente — usar `isPlatformBrowser`

---

## Comandos de verificación

```bash
npm test
npm run test:coverage
npm run lint
npm run build
npm run serve:ssr:Resin-Craft-Art
```
