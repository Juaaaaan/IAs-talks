# testing.instructions.md — Proyecto RCA

> Fichero de referencia usado en la demo de la Charla 8.
> Vive en `.github/instructions/testing.instructions.md` del proyecto Resin Craft Art.

---

```markdown
---
applyTo: "**/*.spec.ts"
---

# Testing conventions — Resin Craft Art

## General rules

- Use Karma and Jasmine. No Jest.
- Minimum coverage per file: 80%.
- Test files live next to the source file: foo.component.ts → foo.component.spec.ts
- Each describe block corresponds to one class or function.
- Each it block tests one specific behavior.

## Naming convention

describe('ComponentName', () => {
  it('should [expected behavior] when [condition]', () => { ... });
});

## Component testing

- Use TestBed.configureTestingModule with imports: [ComponentName] for standalone components.
- Never import NgModules in tests — components are standalone.
- Use fixture.detectChanges() after setting inputs.
- For OnPush components, call fixture.detectChanges() explicitly after every state change.

## Mocking

- Mock external dependencies and services. Never mock internal modules.
- Use jasmine.createSpyObj for service mocks.
- Clean up side effects in afterEach.

## Transloco

- Provide TranslocoTestingModule with the test translations in TestBed.
- Never test raw translation keys — always test the translated output.
```
