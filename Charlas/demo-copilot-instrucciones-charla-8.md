# Demo — Copilot con instrucciones (Charla 8)

**Charla:** [[charla-08-copilot-instrucciones]]
**Herramienta:** GitHub Copilot en VS Code
**Proyecto:** Resin Craft Art (RCA) — Angular 21
**Duración:** 20-25 min + bonus opcional

---

## Preparación previa

- `.github/` vacío para el Acto 1
- `copilot-instructions.md` listo para pegar en el Acto 2
- `AGENTS.md` listo para mostrar en el Acto 4
- `instructions/` con `testing.instructions.md` y `components.instructions.md`
- `.github/agents/` con `developer.agent.md` y `reviewer.agent.md`
- `.claude/agents/` con `developer.md` y `reviewer.md`
- `task.md` de RCA-20 copiado por si se lanza el bonus

---

## Acto 1 — El antes: Copilot sin instrucciones (5 min)

**Objetivo:** Mostrar qué genera Copilot sin contexto del proyecto.

Con `.github/` vacío, abrir Copilot Chat en VS Code y escribir:

```
Crea el componente app-navbar para el proyecto
```

Copilot genera Angular estándar: sin Signals, sin OnPush, sin tokens de diseño, probablemente con NgModules o constructor injection.

> _"¿Veis lo que ha generado? Angular estándar. No sabe que usamos standalone components, no sabe que usamos Signals, no conoce nuestro sistema de diseño. Tendríamos que corregirlo todo."_

---

## Acto 2 — Crear las instrucciones en vivo (5 min)

**Objetivo:** Mostrar qué contiene el fichero y cómo se origina.

Crear `.github/copilot-instructions.md` pegando el contenido preparado:

> _"Este fichero no lo escribí desde cero. Le di el contexto a Claude y me lo generó. Lo revisé y lo ajusté. Ese es el flujo."_

Guardar.

---

## Acto 3 — El después: Copilot con instrucciones (5 min)

**Objetivo:** Mostrar la diferencia en el resultado.

Mismo prompt:

```
Crea el componente app-navbar para el proyecto
```

Ahora Copilot genera: standalone component, OnPush, `inject()`, Signals, tokens de diseño Artisanal Ether (`bg-surface`, `text-on-surface`, `border-outline-variant`), control flow nativo.

> _"Mismo prompt. Fichero de instrucciones mediante. Resultado completamente distinto."_

---

## Acto 4 — AGENTS.md e instructions/ (5 min)

**Objetivo:** Mostrar instrucciones para el agente y el concepto de frontmatter.

Abrir `AGENTS.md` — explicar que define el comportamiento autónomo: qué leer antes de tocar código, cómo verificar antes de terminar, qué nunca hacer.

Abrir `instructions/testing.instructions.md` — señalar el bloque `---`:

> _"Esto se llama frontmatter: son metadatos sobre el fichero en sí. El `applyTo: '**/*.spec.ts'` le dice a Copilot que solo cargue estas instrucciones cuando trabaja con ficheros de test."_

---

## Acto 5 — Múltiples agentes: developer y reviewer (8 min)

**Objetivo:** Mostrar el patrón de agentes especializados.

Abrir `.github/agents/`:

**`developer.agent.md`:**
> _"Lee el `task.md`, analiza la arquitectura, implementa, pasa tests y hace commit. Fijaos en el frontmatter — `tools:` define exactamente a qué herramientas tiene acceso."_

**`reviewer.agent.md`:**
> _"Solo tiene acceso de lectura. No puede modificar nada. Verifica criterios de aceptación, convenciones, cobertura de tests y genera un informe."_

> _"Si el reviewer dice que algo no está bien, el developer vuelve a trabajar. Si aprueba, se crea la Pull Request."_

Mostrar brevemente `.claude/agents/`:

> _"Los mismos agentes existen para Claude Code — mismo concepto, diferente herramienta."_

**Momento clave:**
> _"Un agente construye. Otro verifica. Ninguno de los dos trabaja sin contexto. Eso es un equipo de IA."_

---

## Bonus — `.claude/` y el hook de Graphify

Mostrar `CLAUDE.md` del RCA brevemente y el hook de Graphify en `settings.json`.

> _"Este hook hace que antes de cada sesión Claude lea el grafo de conocimiento del proyecto. No solo sabe cómo escribir código, sino que entiende la arquitectura completa."_

---

## Bonus opcional — Lanzar la RCA-20

```
Implementa la RCA-20: app-navbar y app-footer definitivos con SSR e i18n
```

⚠️ Solo lanzar si el tiempo acompaña y la demo ha ido fluida.

---

## Ficheros de referencia

- `Recursos/copilot-instructions-rca.md` — copilot-instructions.md del RCA
- `Recursos/agents-md-rca.md` — AGENTS.md del RCA
- `Recursos/testing-instructions-rca.md` — testing.instructions.md
- `Recursos/components-instructions-rca.md` — components.instructions.md
- `Recursos/developer-agent-github-rca.md` — developer.agent.md para Copilot
- `Recursos/reviewer-agent-github-rca.md` — reviewer.agent.md para Copilot
- `Recursos/developer-agent-claude-rca.md` — developer.md para Claude
- `Recursos/reviewer-agent-claude-rca.md` — reviewer.md para Claude
- `Recursos/task-rca-20.md` — task de la RCA-20
