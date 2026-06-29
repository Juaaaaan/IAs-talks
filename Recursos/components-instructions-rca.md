# components.instructions.md — Proyecto RCA

> Fichero de referencia usado en la demo de la Charla 8.
> Vive en `.github/instructions/components.instructions.md` del proyecto Resin Craft Art.

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
