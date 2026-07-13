---
type: Indice
title: "IAs-talks — Índice del vault"
description: "Mapa de navegación del vault de conocimiento de la serie de charlas de IA. Punto de entrada para agentes y colaboradores."
tags: [indice, navegacion, vault, wiki-llm]
timestamp: "2026-07-06"
---

# IAs-talks — Índice del vault

Este fichero es el punto de entrada del vault. Un agente que empiece aquí puede navegar todo el conocimiento de la serie siguiendo los enlaces.

---

## Estructura

```
IAs-talks/
├── index.md              ← estás aquí
├── README.md             ← descripción del proyecto
├── Charlas/              ← resumen narrativo de cada charla
│   └── guiones/          ← scripts completos para el ponente
├── Conceptos/            ← conceptos técnicos explicados
│   ├── nivel-1-fundamentos/  ← conceptos de la serie de charlas
│   ├── nivel-2-intermedios/  ← conceptos técnicos intermedios
│   ├── nivel-3-avanzados/    ← patrones y arquitecturas
│   └── nivel-4-frontera/     ← tecnologías emergentes 2026-2027
├── Demos/                ← paso a paso de demos en vivo
├── Recursos/             ← ficheros de referencia y configuración
├── Proyectos/            ← proyectos demo de la serie
└── Plantillas/           ← plantillas OKF para nuevos ficheros
```

---

## Charlas

| Fichero                             | Charla                                      | Estado      |
| ----------------------------------- | ------------------------------------------- | ----------- |
| [[charla-07-skills-mcps]]           | Charla 7 — Skills, MCPs y el Arnés Completo | ✅ Impartida |
| [[charla-08-copilot-instrucciones]] | Charla 8 — Instruyendo a la IA              | ✅ Impartida |
| [[guion-charla-08]]                  | Charla 8 — Guión charla 8                   | ✅ Impartida |
| [[guion-charla-11]]                  | Charla 11 — Guión Wiki LLM                  | ✅ Impartida |

---

## Conceptos

| Fichero | Descripción |
|---|---|
| [[arnes-completo]] | La metáfora central de la serie |
| [[sdd]] | Specification-Driven Development |
| [[skills]] | Arnés de comportamiento |
| [[mcp]] | Model Context Protocol |
| [[copilot-instructions]] | Instrucciones persistentes para Copilot |
| [[agentes-multiples]] | Patrón developer/reviewer |
| [[frontmatter]] | Metadatos YAML en ficheros markdown |
| [[okf]] | Open Knowledge Format — estándar para Wiki LLM |
| [[wiki-llm]] | Base de conocimiento para agentes (patrón Karpathy) |
| [[graphify]] | Grafo de conocimiento del codebase |
| [[github-actions]] | Automatización con IA (próxima charla) |
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
| [[agentic-workflows]] | Flujos de trabajo autónomos con agentes |
| [[memory]] | Memoria a corto y largo plazo de los agentes |
| [[planning-reasoning]] | Planificación y razonamiento en IA |
| [[code-generation-patterns]] | Patrones de generación de código con IA |
| [[eval-benchmarking]] | Medir si la IA funciona bien |
| [[prompt-injection]] | Ataques y seguridad en sistemas con IA |
| [[orchestration-patterns]] | Pipeline, fan-out, supervisor, swarm |
| [[knowledge-graphs]] | GraphRAG — grafos de conocimiento + LLMs |
| [[model-routing]] | Elegir el modelo correcto para cada tarea |
| [[caching-cost]] | Optimización de costes y latencia |
| [[reasoning-models]] | Modelos que piensan antes de responder (o1, o3) |
| [[computer-use]] | Agentes que controlan la pantalla |
| [[mcp-ecosystem]] | El ecosistema de servidores MCP |
| [[ai-ide-patterns]] | Patrones de integración IA en el IDE |
| [[sdd-variations]] | Variantes de SDD: Design Docs, RFC, ADR |
| [[synthetic-data]] | Datos sintéticos y auto-entrenamiento |
| [[constitutional-ai]] | Cómo se alinean los modelos (RLHF, CAI) |
| [[ai-governance]] | Gobernanza: EU AI Act, ISO 42001 |
| [[federated-ai]] | IA sin depender de un solo proveedor |
| [[autonomous-coding-agents]] | Agentes que programan solos (Devin, Copilot Agent) |

---

## Demos

| Fichero | Charla |
|---|---|
| [[demo-jira-charla-7]] | Charla 7 — Jira + SDD con Claude Desktop |
| [[demo-copilot-instrucciones-charla-8]] | Charla 8 — Copilot con instrucciones |

---

## Recursos (proyecto RCA)

Ficheros de referencia del proyecto Resin Craft Art usados en las demos:

- `copilot-instructions-rca.md` — instrucciones globales de Copilot
- `agents-md-rca.md` — AGENTS.md del proyecto
- `testing-instructions-rca.md` — instrucciones para tests
- `components-instructions-rca.md` — instrucciones para componentes
- `developer-agent-github-rca.md` — agente developer para Copilot
- `reviewer-agent-github-rca.md` — agente reviewer para Copilot
- `developer-agent-claude-rca.md` — agente developer para Claude
- `reviewer-agent-claude-rca.md` — agente reviewer para Claude
- `task-rca-20.md` — task de la RCA-20
- `glosario-ia-nivel-1.md` — glosario general de IA

---

## Grafo de conocimiento

Las conexiones principales entre conceptos:

```
arnes-completo
├── sdd
├── skills
├── mcp
└── copilot-instructions
    ├── agentes-multiples
    │   └── frontmatter
    │       └── okf
    └── graphify
```

---

## Estándar de este vault

Todos los ficheros siguen el estándar **[[okf]]** (Open Knowledge Format):
- Campo `type:` obligatorio
- Campo `related:` para conectar conceptos
- Campo `timestamp:` para rastrear cuándo se creó o actualizó
