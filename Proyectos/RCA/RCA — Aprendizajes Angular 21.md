# RCA — Aprendizajes Angular 21

> Diario técnico de lo que voy descubriendo en la práctica. No es documentación oficial, es lo que me ha sorprendido, lo que me ha costado entender o lo que quiero recordar.

---

## Zoneless + OnPush — cómo conviven

Con `provideZonelessChangeDetection()`, Angular ya no usa Zone.js para detectar cambios. Esto significa que `OnPush` no es solo una optimización: es el único modo que tiene sentido. Sin Zone.js, si un componente no es `OnPush`, nunca detectaría cambios de forma automática.

La combinación concreta que usamos:
- `ChangeDetectionStrategy.OnPush` en todos los componentes
- Signals para estado reactivo — la actualización de un signal notifica al scheduler de Angular directamente, sin Zone.js de por medio
- `computed()` para estado derivado — solo recalcula cuando cambian sus dependencias

Lo que me sorprendió: con Signals, `OnPush` ya no requiere que marques manualmente con `markForCheck()`. El signal hace eso internamente al cambiar.

---

## SSR — los tres patrones para browser APIs

Hay tres formas de proteger código que solo puede correr en browser:

```typescript
// 1. Guard clásico — para lógica en métodos
private platformId = inject(PLATFORM_ID);
protected isBrowser = isPlatformBrowser(this.platformId);

ngOnInit() {
  if (this.isBrowser) {
    // localStorage, window, animaciones...
  }
}

// 2. afterNextRender — más moderno, para efectos post-render
constructor() {
  afterNextRender(() => {
    // siempre corre solo en browser, después del primer render
  });
}

// 3. afterRenderEffect — para efectos reactivos post-render
constructor() {
  afterRenderEffect(() => {
    const value = miSignal(); // se re-ejecuta cuando cambia el signal
    // lógica de browser aquí
  });
}
```

En este proyecto usamos principalmente el patrón 1 (`isBrowser`) para casos simples y `afterNextRender` para inicializaciones que dependen del DOM.

---

## Signals — diferencias entre signal, computed y effect

```typescript
// signal — estado mutable
const count = signal(0);
count.set(1);       // reemplaza
count.update(n => n + 1); // transforma

// computed — estado derivado, solo lectura, lazy
const doubled = computed(() => count() * 2);
// Solo recalcula si count() cambia

// effect — efecto secundario, corre cuando cambian sus dependencias
effect(() => {
  console.log('count cambió:', count());
  // no devuelve nada — es para side effects
});
```

Lo importante: `computed` es **lazy** — no recalcula hasta que alguien lo lee. `effect` es **eager** — corre automáticamente cuando cambia cualquier signal que lea dentro de él.

---

## input.required vs input con default

```typescript
// Obligatorio — el componente padre DEBE pasarlo
product = input.required<Product>();

// Opcional con valor por defecto
variant = input<'primary' | 'secondary'>('primary');

// Opcional sin default — puede ser undefined
label = input<string>();
```

`input.required()` lanza un error en tiempo de compilación si el padre no pasa el valor. Mucho mejor que el `@Input() product!: Product` con non-null assertion que era fácil de olvidar.

---

## Control flow moderno — @if y @for

Nunca más `*ngIf` ni `*ngFor`. El control flow nuevo es sintaxis del template, no directivas:

```html
@if (products().length > 0) {
  @for (product of products(); track product.id) {
    <app-product-card [product]="product" />
  } @empty {
    <p>Sin productos disponibles</p>
  }
} @else {
  <p>Cargando...</p>
}
```

Lo que me gustó: `@empty` dentro de `@for` es un bloque nativo, no necesitas un `@if` anidado para el caso vacío. Y `track` es obligatorio — te obliga a pensar en la clave de identidad desde el principio.

---

## Transloco en SSR — el doble loader

El problema: en SSR, el HttpClient no tiene contexto de browser para hacer peticiones HTTP durante el render. El loader HTTP de Transloco fallaba silenciosamente.

La solución: dos configuraciones separadas.

`app.config.ts` (browser):
```typescript
provideTransloco({
  config: { availableLangs: ['es', 'en'], defaultLang: 'es' },
  loader: TranslocoHttpLoader
})
```

`app.config.server.ts` (SSR):
```typescript
{
  provide: TRANSLOCO_LOADER,
  useFactory: () => ({
    getTranslation: (lang: string) => {
      const path = join(process.cwd(), `src/i18n/${lang}.json`);
      return of(JSON.parse(readFileSync(path, 'utf8')));
    }
  })
}
```

El servidor lee directamente del sistema de archivos. Sin peticiones HTTP, sin timing issues.

---

## Supabase Realtime en Angular

El patrón que usamos para stock en tiempo real:

```typescript
@Injectable({ providedIn: 'root' })
export class StockService {
  private supabase = inject(SupabaseService);
  private _items = signal<StockItem[]>([]);
  items = this._items.asReadonly();

  constructor() {
    // Solo suscribirse en browser
    afterNextRender(() => {
      this.loadStock();
      this.subscribeToChanges();
    });
  }

  private subscribeToChanges() {
    this.supabase.client
      .channel('stock-realtime')
      .on('postgres_changes', {
        event: '*',
        schema: 'public',
        table: 'stock_items'
      }, () => this.loadStock())
      .subscribe();
  }
}
```

`afterNextRender` asegura que la suscripción Realtime solo ocurre en browser. En SSR, el componente renderiza con los datos iniciales del fetch y el cliente se suscribe después.

---

## Lazy loading con loadComponent

```typescript
{
  path: 'stock',
  loadComponent: () =>
    import('./features/stock/stock.component')
      .then(m => m.StockComponent)
}
```

Con standalone components, `loadComponent` reemplaza a `loadChildren` para rutas simples. No hace falta un módulo de routing por feature — la ruta importa el componente directamente. El chunk de JS se genera automáticamente por cada `import()` dinámico.
