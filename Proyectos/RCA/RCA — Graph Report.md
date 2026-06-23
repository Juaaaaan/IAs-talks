# RCA — Graph Report

> Análisis interpretado del reporte de Graphify. No es el reporte en bruto — es lo que significa para el proyecto.
> Actualizar después de cada `graphify update .`

---

## Cómo actualizar

```bash
graphify update .
# Compara el commit del reporte con HEAD:
git rev-parse HEAD
```

---

## Reporte: 2026-06-22 (commit `2454ba2d`)

**Corpus:** 117 archivos · ~91.119 palabras  
**Grafo:** 450 nodos · 556 edges · 33 comunidades  
**Import cycles:** ✅ Ninguno

---

## God Nodes — lo que hay que proteger

Los nodos más conectados son los que más duelen si cambian sin cuidado.

| Nodo | Edges | Interpretación |
|------|-------|---------------|
| `SPEC.md` | 17 | Documento raíz — todo referencia a él |
| `Product` | 11 | Abstracción central del dominio |
| `CLAUDE.md` | 11 | Muy integrado — las reglas de Claude Code están bien conectadas |
| `ProductsService` | 8 | Servicio ya existente y bien conectado |
| `ButtonComponent` | 7 | El primitivo más reutilizado |

**Acción:** Cualquier cambio a `Product` (el modelo) o `ProductsService` tiene impacto cascada. Revisar con cuidado antes de modificar su interface.

---

## Comunidades — arquitectura emergente

Las comunidades muestran cómo el código se ha agrupado naturalmente.

### Las que están bien
- **Community 4** — Colecciones coherente: `InfoCards`, `HeroCollections`, `CardsCollections`, `HealthCards`, `HealthCare`
- **Community 5** — Home coherente: `BrandStory`, `Hero`, `CategoryTabs`, `ButtonComponent`
- **Community 10** — Layout limpio: `Navbar`, `Footer`, `Layout`, `StubComponent`
- **Community 16** — Modelo de datos Supabase bien agrupado: tablas, modelos TypeScript, Storage

### Las que merecen atención
- **Community 0** (cohesión 0.04) — 47 nodos mezclando pagos, i18n, variables de entorno, convenciones de código. Es básicamente "todo lo que todavía no tiene un home en el código real". Se disolverá sola a medida que avancen las Fases 4-5.
- **Community 1** (cohesión 0.06) — Angular CLI config. Normal que tenga baja cohesión, es configuración.

### Interesante
- **Community 19** incluye `graphify` como nodo — detectó su propia presencia en el proyecto (probablemente desde el `.claude/` o algún script).

---

## Knowledge Gaps — 213 nodos aislados

213 nodos con ≤1 conexión. La mayoría son archivos de configuración (`$schema`, `allow`, `deny`, `ANGULAR_CLI_ANALYTICS`) que no necesitan documentación.

Los que sí merecen revisar: los 208 restantes incluyen probablemente componentes nuevos de Fase 3 que aún no tienen conexiones suficientes porque están recién creados. Volver a revisar este número después de que la Fase 3 esté completa — debería bajar significativamente.

---

## Conexiones sorprendentes detectadas

Graphify marcó estas como "surprising" — en realidad tienen sentido pero vale la pena registrarlas:

- `InfoCards` → `Cards` (model) — el componente de colecciones referencia el modelo de cards. Correcto.
- `ButtonComponent` → `ButtonSize` y `ButtonVariant` (consts) — el componente referencia sus propias constantes de configuración. Correcto y bien organizado.
- `StockItem` → `StockStatus` (const) — el modelo referencia el enum de estados. Correcto.

Ninguna de estas es problemática. Graphify las marca como sorprendentes porque son referencias cruzadas entre archivos que no están en la misma carpeta.

---

## Preguntas que el grafo sugiere explorar

Del reporte original, las que tienen más valor para RCA:

1. **¿Debería dividirse Community 0?** — No ahora. Se resolverá sola en Fases 4-5 cuando los servicios de pago y el módulo de i18n tengan más código real.
2. **¿Qué conecta los 213 nodos aislados al resto?** — Revisar después de Fase 3 completa.
3. **¿Por qué `devDependencies` tiene alta betweenness centrality?** — Es un nodo puente entre comunidades de config. Normal en proyectos Angular donde `package.json` referencia muchas cosas.

---

## Historial de reportes

| Fecha | Commit | Archivos | Nodos | Edges | Cycles |
|-------|--------|----------|-------|-------|--------|
| 2026-06-22 | `2454ba2d` | 117 | 450 | 556 | 0 |
