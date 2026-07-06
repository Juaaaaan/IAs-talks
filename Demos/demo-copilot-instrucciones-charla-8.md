---
type: Demo
title: "Demo — Copilot con instrucciones (Charla 8)"
description: "Paso a paso de la demo de Charla 8: tour por .github/, prompts en vivo sobre proyecto RCA, agentes developer y reviewer trabajando con anécdota de Superpowers"
tags: [demo, copilot, instrucciones, agentes, developer, reviewer, superpowers, rca]
related: [charla-08-copilot-instrucciones, copilot-instructions, agentes-multiples, frontmatter]
charla: "Charla 8"
estado: "✅ Ejecutada"
timestamp: "2026-07-02"
---

# Demo — Copilot con instrucciones (Charla 8)

**Charla:** [[charla-08-copilot-instrucciones]]
**Herramienta:** GitHub Copilot CLI en VS Code
**Proyecto:** Resin Craft Art (RCA) — Angular 21
**Duración:** 20-25 min

---

## Preparación previa

- `.github/` completo con todos los ficheros
- Extensión Superpowers desactivada en VS Code
- Copilot CLI funcionando en el portátil corporativo
- Prompts preparados y listos para copiar

---

## Acto 1 — Tour por el `.github/` completo (8 min)

Mostrar la carpeta `.github/` ya configurada:

```
.github/
├── copilot-instructions.md
├── AGENTS.md
├── instructions/
│   ├── testing.instructions.md
│   └── components.instructions.md
└── agents/
    ├── developer.agent.md
    └── reviewer.agent.md
```

- `copilot-instructions.md` — instrucciones globales generadas con Claude a partir del contexto del proyecto
- `instructions/` — frontmatter `applyTo:` para instrucciones por contexto
- `AGENTS.md` — comportamiento autónomo

**Anécdota Superpowers:** extensión de terceros que interceptaba prompts y generaba su propia estructura de carpetas sin saberlo.

---

## Acto 2 — Prompts en vivo: modificaciones reales (7 min)

```
Cambia el texto del botón principal del footer a "Contáctanos"
```

```
Añade un botón secundario en el header que ponga "Suscríbete" y no haga nada
```

Resultados: tokens de diseño Artisanal Ether respetados, convenciones Angular seguidas.

---

## Acto 3 — Developer y reviewer en acción (10 min)

```
@developer Añade un badge que muestre el número de items en el carrito
```

```
@reviewer Revisa la implementación del badge
```

**Momento clave:** el reviewer encontró un fallo real — test de regresión fallido. Mostrado en vivo.

Brevemente mostrados los equivalentes en `.claude/agents/`.

---

## Acto 4 — ¿Cómo confiar en el resultado? (5 min)

Señales automatizables: tests, lint, build, reviewer agent.
Señales humanas: lógica de negocio, PR aprobada por persona.

> _"La confianza se construye en capas."_

---

## Lecciones aprendidas

- Desactivar extensiones de terceros antes de la demo (Superpowers interceptaba prompts)
- Para demos en vivo usar prompts pequeños y concretos, no creación de componentes completos
- El reviewer pillando un fallo real es el momento de mayor impacto
- El Copilot CLI puede ser lento con tareas complejas — mejor modificaciones pequeñas
