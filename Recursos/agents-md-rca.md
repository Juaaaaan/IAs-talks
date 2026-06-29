# AGENTS.md — Proyecto RCA

> Fichero de referencia usado en la demo de la Charla 8.
> Vive en la raíz del proyecto Resin Craft Art.

---

# AGENTS.md — Resin Craft Art

Este fichero define cómo debe comportarse el agente cuando trabaja de forma autónoma en el proyecto RCA.
Léelo completo antes de iniciar cualquier tarea.

---

## Antes de tocar cualquier fichero

1. **Leer el `task.md`** de la tarea asignada. Si no existe, preguntar antes de continuar.
2. **Analizar la estructura del proyecto** — carpetas, componentes existentes, servicios, rutas.
3. **Comprobar si existe `graphify-out/graph.json`**. Si existe, ejecutar:
   - `graphify query "<pregunta>"` para preguntas sobre el codebase
   - `graphify path "<A>" "<B>"` para entender relaciones entre ficheros
   - `graphify explain "<concepto>"` para conceptos concretos
4. **Leer los ficheros de contexto** relevantes: `CLAUDE.md`, `copilot-instructions.md`, `AGENTS.md`.
5. **Identificar componentes reutilizables** antes de crear nuevos.

Si hay dudas sobre lógica de negocio entre componentes, **preguntar antes de implementar**.

---

## Antes de dar una tarea por terminada

1. `npm run test:coverage` — cobertura mínima 80% por fichero
2. `npm run lint` — sin errores de lint
3. `npm run build` — build de producción sin errores
4. Comprobar si existe `playwright.config.*`. Si existe, ejecutar E2E relevantes.
5. Partir desde `develop`. Rama: `feature/rca-XX-descripcion` o `fix/rca-XX-descripcion`.
6. Commit siguiendo Conventional Commits: `feat(rca-XX): descripción`
7. Pull Request hacia `develop` con descripción completa.

---

## Lo que el agente nunca debe hacer

- ❌ Modificar ficheros de contexto: `CLAUDE.md`, `AGENTS.md`, `copilot-instructions.md`
- ❌ Modificar `src/styles.scss` o `src/tailwind.css`
- ❌ Modificar el `.gitignore`
- ❌ Actualizar dependencias sin confirmación explícita
- ❌ Borrar ficheros sin confirmar
- ❌ Modificar `angular.json`, `tsconfig*.json`, `eslint.config.*`
- ❌ Hacer commit directamente a `main` o `develop`
- ❌ Tomar decisiones de lógica de negocio sin preguntar
