# Agentes múltiples — Patrón developer/reviewer

> _"Un agente construye. Otro verifica. Ninguno de los dos trabaja sin contexto. Eso es un equipo de IA."_

---

## El problema con un solo agente

Un agente que implementa y verifica al mismo tiempo tiende a aprobar su propio trabajo. Es el mismo problema que ocurre cuando un desarrollador revisa su propio código — la objetividad se pierde.

---

## La solución: agentes especializados

El patrón de agentes múltiples divide el trabajo entre agentes con responsabilidades distintas y acceso a herramientas distintas:

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

El `description` le dice al sistema cuándo invocar este agente automáticamente o cómo describirlo para invocación manual. El `tools` define exactamente a qué herramientas tiene acceso — no puede hacer más de lo que le permitimos.

---

## El agente developer

**Responsabilidad:** Implementar la tarea descrita en el `task.md`.

**Acceso:** Lectura, escritura, ejecución de comandos, búsqueda en ficheros.

**Flujo:**
1. Leer el `task.md` completo
2. Analizar la arquitectura del proyecto
3. Identificar componentes reutilizables
4. Implementar siguiendo las convenciones
5. Pasar tests, lint y build
6. Hacer commit y crear Pull Request

---

## El agente reviewer

**Responsabilidad:** Verificar que la implementación cumple los criterios de aceptación.

**Acceso:** Solo lectura. No puede modificar ningún fichero.

**Flujo:**
1. Leer el `task.md` y los criterios de aceptación
2. Revisar el código implementado
3. Verificar convenciones, tests, cobertura y build
4. Generar informe de revisión

**Resultado posible:**
- ✅ Aprobado → se crea la Pull Request
- ❌ Requiere cambios → el developer corrige y el reviewer vuelve a revisar

---

## Por qué funciona

- **Separación de responsabilidades** — cada agente tiene un único objetivo
- **Control de acceso** — el reviewer no puede modificar código aunque quisiera
- **Objetividad** — el reviewer aplica los criterios del `task.md` sin sesgo
- **Trazabilidad** — el informe del reviewer documenta qué se verificó y cómo

---

## Relación con otras piezas

- **[[copilot-instructions]]** — Los agentes heredan el contexto del proyecto definido en copilot-instructions
- **[[frontmatter]]** — El frontmatter define las herramientas y descripción de cada agente
- **[[sdd]]** — El `task.md` es la fuente de verdad que ambos agentes leen

---

## Dónde aparece en la serie

| Charla | Rol |
|---|---|
| 8 | Acto 5 de la demo — patrón developer/reviewer |
