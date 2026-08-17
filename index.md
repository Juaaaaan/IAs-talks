---
type: Indice
title: "IAs-talks — Índice del vault"
description: "Mapa de navegación del vault de conocimiento de la serie de charlas de IA. Punto de entrada para agentes y colaboradores."
tags: [indice, navegacion, vault, wiki-llm]
timestamp: "2026-08-17"
---

# IAs-talks — Índice del vault

Este fichero es el punto de entrada del vault. Un agente que empiece aquí puede navegar todo el conocimiento de la serie siguiendo los enlaces.

---

## Estructura

```
IAs-talks/
├── index.md              ← estás aquí
├── README.md             ← descripción del proyecto
├── CLAUDE.md              ← instrucciones para agentes que trabajan en el vault
├── Charlas/              ← resumen narrativo de cada charla
│   └── guiones/          ← scripts completos para el ponente
├── Conceptos/            ← 46 conceptos, uno por fichero, clasificados por nivel
│   ├── nivel-1-fundamentos/  ← conceptos de la serie de charlas (8)
│   ├── nivel-2-intermedios/  ← conceptos técnicos intermedios (14)
│   ├── nivel-3-avanzados/    ← patrones y arquitecturas (14)
│   └── nivel-4-frontera/     ← tecnologías emergentes 2026-2027 (10)
├── Demos/                ← paso a paso de demos en vivo
├── Recursos/             ← ficheros de referencia y configuración
├── Proyectos/            ← proyectos demo de la serie (RCA)
└── Plantillas/           ← plantillas OKF para nuevos ficheros
```

---

## Charlas

| Fichero                                   | Charla                                                | Estado      |
| ------------------------------------------ | ------------------------------------------------------ | ----------- |
| [[charla-07-skills-mcps]]                 | Charla 7 — Skills, MCPs y el Arnés Completo            | ✅ Impartida |
| [[charla-08-copilot-instrucciones]]       | Charla 8 — Instruyendo a la IA                          | ✅ Impartida |
| [[guion-charla-08]]                       | Charla 8 — Guión charla 8                               | ✅ Impartida |
| [[guion-charla-11]]                       | Charla 11 — Guión Wiki LLM                              | ✅ Impartida |
| [[charla-12-mapa-ia]]                     | Charla 12 — El mapa de la IA                            | ✅ Impartida |
| [[guion-charla-12]]                       | Charla 12 — Guión con frases de J.C. Jover              | ✅ Impartida |
| [[charla-13-copilot-studio-metricas]]     | Charla 13 — Copilot Studio, agentes y métricas          | ✅ Impartida |
| [[guion-charla-13]]                       | Charla 13 — Guión, demo handbook corporativo + Teams    | ✅ Impartida |
| [[material-charla-14-gobernanza]]         | Charla 14 — Gobernanza de la IA (EU AI Act, ISO 42001)  | ✅ Impartida |
| [[guion-charla-14]]                       | Charla 14 — Guión gobernanza                            | ✅ Impartida |
| [[MATERIAL-CHARLA-15-SEGURIDAD]]          | Charla 15 — Seguridad en sistemas con IA                | ✅ Impartida |
| [[guion-charla-15]]                       | Charla 15 — Guión seguridad                             | ✅ Impartida |
| [[MATERIAL-CHARLA-16-SDD-HERRAMIENTAS]]   | Charla 16 — SDD con herramientas: spec manual vs OpenSpec | ✅ Impartida |
| [[guion-charla-16]]                       | Charla 16 — Guión, demo OpenSpec + Claude Code          | ✅ Impartida |
| [[guion-charla-17]]                       | Charla 17 — Elegir bien la IA: herramienta, modelo y modo de trabajo | 📝 Guión listo (pdte. impartir) |

Serie en curso (7–16 impartidas; 17 con guión listo). El arco narrativo del **arnés completo** se cerró en la Charla 13; a partir de la 14 la serie continúa con bloques temáticos (gobernanza, seguridad, herramientas SDD, elección de IA). **Próxima: Charla 17 (guión listo, pendiente de impartir).**

---

## Conceptos (46)

### nivel-1-fundamentos (8)

| Fichero | Descripción |
|---|---|
| [[arnes-completo]] | La metáfora central de la serie |
| [[sdd]] | Specification-Driven Development |
| [[skills]] | Arnés de comportamiento |
| [[frontmatter]] | Metadatos YAML en ficheros markdown |
| [[okf]] | Open Knowledge Format — estándar para Wiki LLM |
| [[wiki-llm]] | Base de conocimiento para agentes (patrón Karpathy) |
| [[agente-ia]] | Chatbot clásico vs agente que razona |
| [[alucinaciones]] | Cuándo la IA se lo inventa (y cómo protegerte) |

### nivel-2-intermedios (14)

| Fichero | Descripción |
|---|---|
| [[mcp]] | Model Context Protocol |
| [[copilot-instructions]] | Instrucciones persistentes para Copilot |
| [[copilot-studio]] | Plataforma no-code de Microsoft para agentes corporativos |
| [[rag]] | Retrieval-Augmented Generation |
| [[context-engineering]] | Diseño del contexto completo para IA |
| [[embeddings]] | Representación semántica — búsqueda por significado |
| [[function-calling]] | La IA que invoca herramientas externas |
| [[chain-of-thought]] | Razonamiento paso a paso |
| [[system-prompt]] | System prompt vs user prompt |
| [[temperature]] | Control de creatividad del modelo |
| [[structured-output]] | Salida en formatos parseables (JSON, YAML) |
| [[multimodal]] | LLMs que ven, oyen y leen |
| [[context-window-management]] | Gestión de la ventana de contexto |
| [[modelos-abiertos-vs-cerrados]] | Las dos familias del panorama IA (y la residencia de datos) |

### nivel-3-avanzados (14)

| Fichero | Descripción |
|---|---|
| [[agentes-multiples]] | Patrón developer/reviewer |
| [[github-actions]] | Automatización con IA |
| [[graphify]] | Grafo de conocimiento del codebase |
| [[agentic-workflows]] | Flujos de trabajo autónomos con agentes |
| [[memory]] | Memoria a corto y largo plazo de los agentes |
| [[planning-reasoning]] | Planificación y razonamiento en IA |
| [[code-generation-patterns]] | Patrones de generación de código con IA |
| [[eval-benchmarking]] | Medir si la IA funciona bien |
| [[metricas-ia]] | Métricas de agentes conversacionales, DORA y AI Productivity Paradox |
| [[prompt-injection]] | Ataques y seguridad en sistemas con IA |
| [[orchestration-patterns]] | Pipeline, fan-out, supervisor, swarm |
| [[knowledge-graphs]] | GraphRAG — grafos de conocimiento + LLMs |
| [[model-routing]] | Elegir el modelo correcto para cada tarea |
| [[caching-cost]] | Optimización de costes y latencia |

### nivel-4-frontera (10)

| Fichero | Descripción |
|---|---|
| [[reasoning-models]] | Modelos que piensan antes de responder |
| [[computer-use]] | Agentes que controlan la pantalla |
| [[mcp-ecosystem]] | El ecosistema de servidores MCP |
| [[ai-ide-patterns]] | Patrones de integración IA en el IDE |
| [[sdd-variations]] | Variantes de SDD: Design Docs, RFC, ADR |
| [[synthetic-data]] | Datos sintéticos y auto-entrenamiento |
| [[constitutional-ai]] | Cómo se alinean los modelos (RLHF, CAI) |
| [[ai-governance]] | Gobernanza: EU AI Act, ISO 42001 |
| [[federated-ai]] | IA sin depender de un solo proveedor |
| [[autonomous-coding-agents]] | Agentes que programan solos |

---

## Demos

| Fichero | Charla |
|---|---|
| [[demo-jira-charla-7]] | Charla 7 — Jira + SDD con Claude Desktop |
| [[demo-copilot-instrucciones-charla-8]] | Charla 8 — Copilot con instrucciones |
| [[demo-faq-onboarding]] | Charla 13 — FAQ de onboarding con handbook corporativo |
| [[demo-politica-teletrabajo]] | Charla 13 — Política de teletrabajo vía agente + Teams |

---

## Recursos (proyecto RCA + generales)

Ficheros de referencia del proyecto Resin Craft Art usados en las demos, y recursos generales de la serie:

- `copilot-instructions-rca.md` — instrucciones globales de Copilot
- `agents-md-rca.md` — AGENTS.md del proyecto
- `testing-instructions-rca.md` — instrucciones para tests
- `components-instructions-rca.md` — instrucciones para componentes
- `developer-agent-github-rca.md` — agente developer para Copilot
- `reviewer-agent-github-rca.md` — agente reviewer para Copilot
- `developer-agent-claude-rca.md` — agente developer para Claude
- `reviewer-agent-claude-rca.md` — agente reviewer para Claude
- `task-rca-20.md` — task de la RCA-20
- `task-rca-28.md` — task de la RCA-28
- `glosario-ia-nivel-1.md` — glosario general de IA
- [[novedades-ia-semana-21julio2026]] — novedades IA semana del 21 de julio 2026

---

## Proyectos

- **[[Proyectos/RCA/index|RCA — Resin Craft Art]]** — proyecto demo real usado a lo largo de toda la serie
  - `Developer/` — decisiones de arquitectura, dead-ends, sprints
  - `Equipo/` — 7 perfiles de madurez IA, assessment framework, OKR de capacidad IA del equipo

---

## Grafo de conocimiento

Las conexiones principales entre conceptos:

```
arnes-completo
├── sdd
├── skills
└── agente-ia
    ├── copilot-studio
    │   ├── mcp
    │   ├── rag
    │   ├── embeddings
    │   └── metricas-ia
    └── agentes-multiples
        └── frontmatter
            └── okf

mcp
└── copilot-instructions
    └── graphify
```

---

## Estándar de este vault

Todos los ficheros siguen el estándar **[[okf]]** (Open Knowledge Format):
- Campo `type:` obligatorio
- Campo `related:` para conectar conceptos
- Campo `timestamp:` para rastrear cuándo se creó o actualizó
- **Un concepto = un fichero = un nivel.** Si un concepto cambia de nivel, se mueve; nunca se duplica.
