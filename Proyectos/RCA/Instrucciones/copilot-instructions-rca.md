---
type: Recurso
title: "copilot-instructions.md — Proyecto RCA"
description: "Fichero de referencia del proyecto Resin Craft Art usado en la demo de Charla 8. Vive en .github/copilot-instructions.md del proyecto."
tags: [recurso, copilot, rca, angular, instrucciones, artisanal-ether]
related: [copilot-instructions, charla-08-copilot-instrucciones]
charla: "Charla 8"
estado: "✅ Publicado"
timestamp: "2026-07-02"
---

# copilot-instructions.md — Proyecto RCA

> Fichero de referencia usado en la demo de la Charla 8.
> Vive en `.github/copilot-instructions.md` del proyecto Resin Craft Art.

---

# Resin Craft Art — Copilot Instructions

## Project overview

Resin Craft Art (RCA) is an Angular 21 SSR e-commerce application for handmade resin jewelry.
It uses zoneless change detection, Signals-first state management, Supabase as the backend,
Transloco for i18n, and Tailwind v4 with a custom design system called Artisanal Ether.

## Stack

- **Framework:** Angular 21 with SSR (`@angular/ssr`) and Express
- **Change detection:** Zoneless (`provideZonelessChangeDetection()`). No Zone.js.
- **State:** Signals and `computed()`. No NgRx, no BehaviorSubject for local state.
- **Database:** Supabase (PostgreSQL + Storage + Realtime + RLS)
- **Styling:** Tailwind v4 with custom tokens defined in `src/tailwind.css`
- **i18n:** Transloco with separate browser/SSR loaders
- **Testing:** Karma/Jasmine for unit tests, minimum 80% coverage per file
- **Linting:** ESLint with `angular-eslint` covering `.ts` and `.html`
- **Commits:** Conventional Commits (`feat(rca-XX): description`)
- **Pre-commit hook:** Husky runs `npm test` automatically

## TypeScript conventions

- Strict type checking enabled
- Never use `any`. Use `unknown` when type is uncertain.

## Angular conventions

- Always use standalone components. Never use NgModules.
- Never set `standalone: true` inside decorators — it is the default.
- Use `input()` and `output()` functions instead of `@Input` and `@Output` decorators.
- Use `inject()` instead of constructor injection.
- Use `computed()` for derived state.
- Set `changeDetection: ChangeDetectionStrategy.OnPush` in every `@Component`.
- Use native control flow: `@if`, `@for`, `@switch`. Never use `*ngIf`, `*ngFor`, `*ngSwitch`.
- Never use `@HostBinding` or `@HostListener`. Use the `host` object in the decorator instead.
- Never use `ngClass`. Use `class` bindings.
- Never use `ngStyle`. Use `style` bindings.
- Never use `mutate` on signals. Use `update` or `set`.
- Use `NgOptimizedImage` for all static images.
- Use `providedIn: 'root'` for singleton services.

## Design system — Artisanal Ether

| Role | Token |
|------|-------|
| Page canvas | `bg-surface` (#fff8f4) |
| Card / highlight | `bg-surface-container-lowest` (white) |
| Borders | `border-outline-variant` (#d0c4bc) |
| Body text | `text-on-surface` (#1f1b18) |
| CTA | `bg-primary` (#685c52) |
| Accent | `bg-primary-container` (#f5e4d7) |
