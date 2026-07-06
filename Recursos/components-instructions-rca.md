---
type: Recurso
title: "components.instructions.md — Proyecto RCA"
description: "Instrucciones de componentes para GitHub Copilot en el proyecto RCA. Se activa solo con ficheros *.component.ts mediante frontmatter applyTo."
tags: [recurso, componentes, copilot, rca, angular, signals, instrucciones]
related: [copilot-instructions, frontmatter, charla-08-copilot-instrucciones]
charla: "Charla 8"
estado: "✅ Publicado"
timestamp: "2026-07-02"
---

# components.instructions.md — Proyecto RCA

> Fichero de referencia usado en la demo de la Charla 8.
> Vive en `.github/instructions/components.instructions.md` del proyecto Resin Craft Art.
> Se activa solo cuando Copilot trabaja con ficheros `*.component.ts`.

---

```markdown
---
applyTo: "**/*.component.ts"
---

# Component conventions — Resin Craft Art

## Required

- ChangeDetectionStrategy.OnPush en todos los componentes
- Nunca set standalone: true — es el default en Angular 21
- input() y output() en lugar de @Input/@Output
- inject() en lugar de constructor injection
- computed() para estado derivado
- Control flow nativo: @if, @for, @switch — nunca *ngIf, *ngFor, *ngSwitch
- Nunca ngClass — usar class bindings
- Nunca ngStyle — usar style bindings
- NgOptimizedImage para imágenes estáticas
- Tokens de diseño Artisanal Ether — nunca colores hardcodeados
- providedIn: 'root' para servicios singleton

## Host bindings

Usar el objeto host en el decorator:

@Component({
  host: {
    '[class.active]': 'isActive()',
    '(click)': 'onClick()'
  }
})

Nunca @HostBinding ni @HostListener.
```
