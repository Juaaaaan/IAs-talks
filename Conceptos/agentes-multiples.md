---
type: Concepto
title: "Agentes múltiples — Patrón developer/reviewer"
description: "Patrón de agentes especializados donde un agente implementa y otro verifica. Aplica la separación de responsabilidades al trabajo autónomo de la IA."
tags: [agentes, copilot, claude, developer, reviewer, calidad, patron]
related: [copilot-instructions, frontmatter, sdd, arnes-completo]
charla: "Charla 8"
estado: "✅ Publicado"
timestamp: "2026-07-02"
---

# Agentes múltiples — Patrón developer/reviewer

> _"Un agente construye. Otro verifica. Ninguno de los dos trabaja sin contexto. Eso es un equipo de IA."_

---

## El problema con un solo agente

Un agente que implementa y verifica al mismo tiempo tiende a aprobar su propio trabajo. Es el mismo problema que ocurre cuando un desarrollador revisa su propio código — la objetividad se pierde.

---

## La solución: agentes especializados

**Developer** → implementa la tarea
**Reviewer** → verifica que la implementación es correcta

Cada agente tiene su propio fichero de instrucciones, su propio contexto y sus propias herramientas permitidas.

---

## Dónde viven

### GitHub Copilot

```
.github/
└── agents/
    ├── developer.agent.md
    └── reviewer.agent.md
```

### Claude Code

```
.claude/
└── agents/
    ├── developer.md
    └── reviewer.md
```

---

## Estructura de un agente

```markdown
---
description: Cuándo invocarlo y para qué
tools: herramientas permitidas
---

# Nombre del agente

Instrucciones de comportamiento...
```

El [[frontmatter]] `tools:` define exactamente a qué herramientas tiene acceso — no puede hacer más de lo que le permitimos.

---

## El agente developer

**Responsabilidad:** Implementar la tarea descrita en el `task.md`.
**Acceso:** Lectura, escritura, ejecución de comandos.
**Flujo:** Leer task.md → analizar arquitectura → implementar → tests + lint + build → commit + PR.

## El agente reviewer

**Responsabilidad:** Verificar que la implementación cumple los criterios de aceptación.
**Acceso:** Solo lectura. No puede modificar ningún fichero.
**Resultado:** Informe con ✅/❌ por criterio + veredicto (Aprobado / Requiere cambios).

---

## Por qué funciona

- Separación de responsabilidades
- El reviewer no puede modificar código aunque quisiera
- Aplica los criterios del `task.md` sin sesgo
- Documenta qué se verificó y cómo

---

## Relación con otras piezas

- **[[copilot-instructions]]** — Los agentes heredan el contexto del proyecto
- **[[frontmatter]]** — Define las herramientas y descripción de cada agente
- **[[sdd]]** — El `task.md` es la fuente de verdad que ambos agentes leen

---

## Dónde aparece en la serie

| Charla | Rol |
|---|---|
| 8 | Acto 3 de la demo — patrón developer/reviewer en vivo |
