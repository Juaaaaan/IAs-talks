---
type: Concepto
title: "Decisión: Sin NgRx — Signals-first en RCA"
description: "Por qué no usamos NgRx en el proyecto RCA y cómo gestionamos el estado con Angular Signals."
tags: [rca, angular, signals, ngrx, estado, decision]
related: [decisiones-arquitectura, contexto-proyecto]
timestamp: "2026-07-06"
---

# Decisión: Sin NgRx — Signals-first en RCA

---

## La decisión

**No usamos NgRx en el proyecto RCA.** El estado se gestiona con Angular Signals nativos.

---

## Por qué

**El estado es local a cada feature.** El carrito vive en `CartService`, el stock en `StockService`, los productos en `ProductService`. No hay estado compartido complejo que justifique un store global.

**NgRx añade complejidad innecesaria.** Actions, reducers, selectors, effects — todo eso tiene sentido en aplicaciones con múltiples equipos trabajando en paralelo sobre el mismo estado. Para una tienda de una artesana con un desarrollador, es sobreingenieria.

**Signals cubre el caso de uso.** `signal()` para estado local, `computed()` para estado derivado, `effect()` para side effects. El CartService con Signals es suficientemente reactivo y más fácil de entender.

---

## Cómo lo hacemos

```typescript
// CartService — estado con Signals
@Injectable({ providedIn: 'root' })
export class CartService {
  private readonly items = signal<CartItem[]>([]);
  
  readonly total = computed(() => 
    this.items().reduce((sum, item) => sum + item.price * item.quantity, 0)
  );
  
  readonly itemCount = computed(() => 
    this.items().reduce((sum, item) => sum + item.quantity, 0)
  );
  
  addItem(product: Product): void {
    this.items.update(items => {
      const existing = items.find(i => i.id === product.id);
      if (existing) {
        return items.map(i => i.id === product.id 
          ? { ...i, quantity: i.quantity + 1 } 
          : i
        );
      }
      return [...items, { ...product, quantity: 1 }];
    });
  }
}
```

---

## Lo que NO se debe hacer

- No instalar NgRx aunque parezca que simplifica algo.
- No usar `BehaviorSubject` para estado local en componentes — usar `signal()` en su lugar.
- No usar `mutate()` en signals — está deprecado. Usar `update()` o `set()`.

---

## Cuándo reconsiderar

Si el proyecto creciera con múltiples desarrolladores y features con estado compartido complejo (ej. un backoffice de gestión de pedidos, panel de admin con tiempo real), NgRx o Akita podrían justificarse. En el estado actual del proyecto: no.
