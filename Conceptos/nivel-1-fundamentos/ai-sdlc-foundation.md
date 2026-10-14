---
type: Concepto
title: "AI SDLC Foundation — Sistema operativo para el ciclo de desarrollo con IA"
description: "Dominio modular de agentes, conocimiento, workflows y controles que se define una vez en formato canonical y se proyecta a distintos providers."
tags: [ai-sdlc-foundation, agentes, workflows, gobernanza, proveedores]
related: [agent, apm, canonical, hub-orchestrator, workflow, arnes-completo]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# AI SDLC Foundation — Sistema operativo para el ciclo de desarrollo con IA

> _"Definir una vez, proyectar a cada plataforma y ejecutar con controles visibles."_

---

## Qué es

**AI SDLC Foundation** organiza los activos y flujos que necesita un equipo para aplicar IA al ciclo de desarrollo de forma consistente. Separa la fuente de verdad agnóstica del proveedor, los ficheros que cada plataforma ejecuta y la orquestación que convierte una petición en un resultado auditable.

No sustituye al modelo ni al provider. Es el arnés operativo que conecta conocimiento, comportamiento, herramientas, procesos y controles.

---

## Del conocimiento al runtime

```text
Knowledge / Templates / Skills / Instructions
                    |
              Canonical (.apm/)
                    |
                Projection
                    |
                 Runtime
                    |
                 Provider
```

1. **[[knowledge|Knowledge]]**, **[[template|Templates]]**, **[[skill-foundation|Skills]]** e **[[instruction|Instructions]]** definen qué sabe y cómo trabaja el sistema.
2. **[[canonical|Canonical]]** conserva esos activos como fuente de verdad independiente de la plataforma.
3. **[[projection|Projection]]** los transforma al formato que entiende cada **[[provider|Provider]]**.
4. El **[[runtime|Runtime]]** generado es lo que el provider descubre y ejecuta.
5. **[[apm|APM]]** distribuye estos activos en **[[pack|Packs]]** instalables.

---

## De la intención al resultado

```text
Prompt -> Hub Orchestrator -> Workflow -> Station -> Station
                                      |          |
                                   Hooks      Agent
                                      |          |
                                    Gates   Skills + MCP
                                      |
                                    Traces
```

1. Un **[[prompt|Prompt]]** inicia una tarea o expresa una intención.
2. El **[[hub-orchestrator|Hub Orchestrator]]** clasifica esa intención y elige un **[[workflow|Workflow]]**.
3. El workflow avanza por **[[station|Stations]]**, cada una delegada a un **[[agent|Agent]]** especializado.
4. Los **[[hook|Hooks]]** automatizan comprobaciones pre y post; los **[[gate|Gates]]** deciden `pass`, `warn` o `block`.
5. Cada estación emite un **[[trace|Trace]]** para hacer el proceso auditable.
6. La **[[model-policy|Model Policy]]** asigna un **[[tier|Tier]]** abstracto adecuado a cada tarea.

## Glosario

| Link | Description |
|---|---|
| [[agent|Agent]] | Rol autónomo con responsabilidad, skills y herramientas. |
| [[apm|APM]] | Sistema de distribución de bundles de Foundation. |
| [[canonical|Canonical]] | Fuente de verdad agnóstica en `.apm/`. |
| [[context|Context]] | Catálogo YAML de capacidades disponibles en runtime. |
| [[gate|Gate]] | Checkpoint de calidad: pass, warn o block. |
| [[hook|Hook]] | Comprobación automática pre o post estación. |
| [[hub-orchestrator|Hub Orchestrator]] | Agente central de triaje y despacho. |
| [[instruction|Instruction]] | Regla automática aplicada por patrones de ruta. |
| [[knowledge|Knowledge]] | Biblioteca de principios, políticas y playbooks. |
| [[mcp-foundation|MCP]] | Estándar de conexión con herramientas externas. |
| [[model-policy|Model Policy]] | Reglas que asignan tiers a tipos de tarea. |
| [[pack|Pack]] | Subconjunto modular e instalable de capacidades. |
| [[projection|Projection]] | Transformación de canonical a formatos de provider. |
| [[prompt|Prompt]] | Slash command que inicia un workflow o tarea. |
| [[provider|Provider]] | Plataforma que ejecuta agentes y workflows. |
| [[runtime|Runtime]] | Ficheros generados que descubre el provider. |
| [[script|Script]] | Tooling interno de construcción, validación y distribución. |
| [[skill-foundation|Skill]] | Paquete reutilizable de conocimiento experto. |
| [[station|Station]] | Paso especializado dentro de un workflow. |
| [[template|Template]] | Esqueleto preformateado de un entregable. |
| [[tier|Tier]] | Nivel abstracto de capacidad del modelo. |
| [[trace|Trace]] | Registro estructurado para auditoría. |
| [[workflow|Workflow]] | Pipeline multiestación que entrega un resultado. |

---

## Relación con el arnés completo

- **[[arnes-completo]]** — Foundation operacionaliza el arnés como activos distribuibles y workflows ejecutables.
- **[[sdd]]** — Las especificaciones aportan el objetivo documental que consumen agentes y workflows.
- **[[skills]]** — Las skills aportan comportamiento y conocimiento reutilizable.
- **[[mcp]]** — MCP conecta los agentes con herramientas y servicios reales.
- **[[copilot-instructions]]** — Las instrucciones persistentes son uno de los formatos que puede producir una proyección.
- **[[agentic-workflows]]** — Los workflows de Foundation concretan el patrón agentic en estaciones, hooks, gates y traces.
