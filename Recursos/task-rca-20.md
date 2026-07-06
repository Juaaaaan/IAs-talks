---
type: Recurso
title: "task-rca-20.md — app-navbar y app-footer definitivos"
description: "Task del issue RCA-20 del proyecto Resin Craft Art. Navbar y footer con SSR e i18n. Usado en el bonus de Charla 8."
tags: [recurso, task, rca, angular, navbar, footer, ssr, i18n]
related: [sdd, charla-08-copilot-instrucciones, agentes-multiples]
charla: "Charla 8"
estado: "✅ Publicado"
timestamp: "2026-07-02"
---

# task-rca-20.md — app-navbar y app-footer definitivos

**Issue Jira:** RCA-20
**Épica:** RCA-3 — Páginas y Componentes
**Rama:** `feature/rca-20-navbar-footer-ssr-i18n`

---

## Objetivo

Implementar el `app-navbar` y el `app-footer` definitivos del proyecto Resin Craft Art, con soporte completo de SSR e i18n mediante Transloco.

---

## Funcionalidad esperada

### app-navbar

- Logo alineado a la izquierda
- Navegación: Home, Colecciones, Stock, Personaliza, Cuidados, Contacto
- Sticky con `bg-surface/80 backdrop-blur-[10px]`
- Textos traducibles con Transloco
- Compatible con SSR

### app-footer

- Logo o nombre de la marca
- Copyright con año dinámico
- Compatible con SSR

---

## Criterios de aceptación

- [ ] Navbar renderiza correctamente en SSR
- [ ] Footer renderiza correctamente en SSR
- [ ] Textos traducidos en todos los idiomas
- [ ] Navbar sticky en todas las páginas
- [ ] Cobertura de tests ≥ 80%
- [ ] Sin errores de lint
- [ ] Build de producción sin errores

---

## Convenciones

- Standalone, OnPush, `inject()`, Signals, control flow nativo
- Tokens Artisanal Ether — no colores hardcodeados
- `NgOptimizedImage` para el logo
- No acceder a `window` ni `document` — usar `isPlatformBrowser`
