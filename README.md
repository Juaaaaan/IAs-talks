---
type: Indice
title: "IAs-talks — Base de conocimiento"
description: "Vault de conocimiento de la serie de charlas de IA. Wiki LLM en formato OKF navegable por agentes y humanos. 100+ ficheros markdown interconectados."
tags: [indice, vault, wiki-llm, okf, ia, charlas, conocimiento]
timestamp: "2026-07-26"
---

# 🧠 IA Talks — Base de conocimiento

Este vault es el **segundo cerebro** de la serie de píldoras informativas sobre IA que impartimos internamente. Es un **Wiki LLM** — una base de conocimiento en markdown que los agentes de IA pueden leer, navegar y mantener.

Todos los ficheros siguen el estándar **[[okf]]** (Open Knowledge Format): frontmatter YAML con `type`, `title`, `description`, `tags`, `related` y `timestamp`.

---

## Estructura del vault

```
IAs-talks/
├── index.md              ← Punto de entrada para agentes (mapa del grafo)
├── README.md             ← Este fichero (orientación para humanos)
├── CLAUDE.md              ← Instrucciones para agentes que trabajan en el vault
│
├── Charlas/              ← Resumen narrativo de cada sesión impartida
│   └── guiones/          ← Scripts completos para el ponente
├── Conceptos/            ← 46 conceptos clasificados + 3 nuevos pendientes de clasificar
│   ├── nivel-1-fundamentos/  ← Conceptos de la serie de charlas (11)
│   ├── nivel-2-intermedios/  ← Conceptos técnicos intermedios (12)
│   ├── nivel-3-avanzados/    ← Patrones y arquitecturas (13)
│   └── nivel-4-frontera/     ← Tecnologías emergentes 2026-2027 (10)
├── Demos/                ← Paso a paso de demos en vivo (6)
├── Recursos/             ← Ficheros de referencia — configs, agentes, tasks, novedades
├── Proyectos/            ← Wikis LLM de proyectos reales (ej. RCA)
│   └── RCA/
│       ├── Developer/    ← Decisiones técnicas del proyecto
│       └── Equipo/       ← Perfiles de madurez IA del equipo (7 perfiles)
└── Plantillas/           ← Templates OKF para nuevos ficheros
```

---

## La narrativa de la serie

La serie construye un arco acumulativo. El hilo conductor es el **arnés completo**: el conjunto de piezas que permiten a la IA trabajar de forma estructurada, consistente y conectada al entorno real de la empresa.

```
SDD           →  arnés documental          (qué construir)
Skills        →  arnés de comportamiento   (cómo comportarse)
MCPs          →  arnés de integración      (cómo actuar en el mundo real)
Instrucciones →  arnés del proyecto        (cómo conocer el código)
Wiki LLM      →  arnés del conocimiento    (por qué se hacen las cosas)
──────────────────────────────────────────────────────────────────────────────────────────────────────────
Las cinco juntas = el arnés completo
```

---

## Charlas de la serie

| # | Título | Estado |
|---|---|---|
| 1–6 | Serie anterior (heredada) | ✅ Impartidas |
| 7 | [[charla-07-skills-mcps\|Skills, MCPs y el Arnés Completo]] | ✅ Impartida — 17 jun 2026 |
| 8 | [[charla-08-copilot-instrucciones\|Instruyendo a la IA: .github/ y .claude/]] | ✅ Impartida — 2 jul 2026 |
| 9–10 | Serie empresa (heredadas) | ✅ Impartidas |
| 11 | [[guion-charla-11\|Wiki LLM: la IA que recuerda a tu equipo]] | ✅ Impartida — 9 jul 2026 |
| 12 | [[charla-12-mapa-ia\|El mapa de la IA: dónde estamos y adónde va esto]] | ✅ Impartida |
| 13 | [[charla-13-copilot-studio-metricas\|Copilot Studio, agentes y métricas — demo real con handbook corporativo y Teams]] | ✅ Impartida |

> Serie completa (7-13). El propietario original de la serie recupera la titularidad en septiembre.

---

## Conceptos del vault

### Conceptos fundacionales (nivel-1-fundamentos, 11)

- [[arnes-completo]] — La metáfora central de la serie
- [[sdd]] — Specification-Driven Development
- [[skills]] — El arnés de comportamiento
- [[mcp]] — Model Context Protocol
- [[copilot-instructions]] — Instrucciones persistentes para Copilot
- [[agentes-multiples]] — Patrón developer/reviewer
- [[frontmatter]] — Metadatos YAML en ficheros markdown
- [[okf]] — Open Knowledge Format — estándar para Wiki LLM
- [[wiki-llm]] — Base de conocimiento para agentes (patrón Karpathy)
- [[graphify]] — Grafo de conocimiento del codebase
- [[github-actions]] — Automatización con IA

### Conceptos de nivel 2 — intermedios (12)

- [[rag]] — Retrieval-Augmented Generation
- [[context-engineering]] — Diseño del contexto completo para IA
- [[embeddings]] — Representación semántica — búsqueda por significado
- [[function-calling]] — La IA que invoca herramientas externas
- [[chain-of-thought]] — Razonamiento paso a paso (CoT)
- [[system-prompt]] — System prompt vs user prompt
- [[temperature]] — Control de creatividad del modelo
- [[structured-output]] — Salida en formatos parseables (JSON, YAML)
- [[multimodal]] — LLMs que ven, oyen y leen
- [[context-window-management]] — Gestión de la ventana de contexto
- [[copilot-instructions]] — (versión nivel 2, más técnica)
- [[mcp]] — (versión nivel 2, más técnica)

### Conceptos de nivel 3 — avanzados (13)

- [[agentic-workflows]] — Flujos de trabajo autónomos con agentes
- [[memory]] — Memoria a corto y largo plazo de los agentes
- [[planning-reasoning]] — Planificación y razonamiento en IA
- [[code-generation-patterns]] — Patrones de generación de código con IA
- [[eval-benchmarking]] — Medir si la IA funciona bien
- [[prompt-injection]] — Ataques y seguridad en sistemas con IA
- [[orchestration-patterns]] — Pipeline, fan-out, supervisor, swarm
- [[knowledge-graphs]] — GraphRAG — grafos de conocimiento + LLMs
- [[model-routing]] — Elegir el modelo correcto para cada tarea
- [[caching-cost]] — Optimización de costes y latencia
- [[agentes-multiples]] — (versión nivel 3, patrones avanzados)
- [[github-actions]] — (versión nivel 3, más técnica)
- [[graphify]] — (versión nivel 3, más técnica)

### Conceptos de nivel 4 — frontera 2026-2027 (10)

- [[reasoning-models]] — Modelos que piensan antes de responder
- [[computer-use]] — Agentes que controlan la pantalla
- [[mcp-ecosystem]] — El ecosistema de servidores MCP
- [[ai-ide-patterns]] — Patrones de integración IA en el IDE
- [[sdd-variations]] — Variantes de SDD: Design Docs, RFC, ADR
- [[synthetic-data]] — Datos sintéticos y auto-entrenamiento
- [[constitutional-ai]] — Cómo se alinean los modelos (RLHF, CAI)
- [[ai-governance]] — Gobernanza: EU AI Act, ISO 42001
- [[federated-ai]] — IA sin depender de un solo proveedor
- [[autonomous-coding-agents]] — Agentes que programan solos

### ⚠️ Pendientes de clasificar (Charla 13, sin carpeta nivel-X asignada)

- [[agente-ia]] — Qué es un agente de IA (nuevo)
- [[copilot-studio]] — Microsoft Copilot Studio (nuevo)
- [[metricas-ia]] — Cómo medir el impacto de la IA (nuevo)
- `Conceptos/embeddings.md` y `Conceptos/rag.md` — **duplicados**: ya existen en `nivel-2-intermedios/`. Revisar si hace falta fusionar o eliminar la copia suelta.

---

## Demos (6)

| Fichero | Charla |
|---|---|
| [[demo-jira-charla-7]] | Charla 7 — Jira + SDD con Claude Desktop |
| [[demo-copilot-instrucciones-charla-8]] | Charla 8 — Copilot con instrucciones |
| [[demo-faq-onboarding]] | Charla 13 — FAQ de onboarding con handbook corporativo |
| [[demo-politica-teletrabajo]] | Charla 13 — Política de teletrabajo vía agente + Teams |

---

## Principios de la serie

| Principio | Descripción |
|---|---|
| **Demo primero** | La audiencia desconecta en teoría y vuelve en demos |
| **Narrativa acumulativa** | Cada charla es la base de la siguiente |
| **Audiencia mixta** | 60–90 asistentes: developers, RRHH, directivos, comerciales |
| **Herramientas reales** | Demos con proyectos reales (RCA), herramientas del día a día |
| **Estándar OKF** | Todo fichero tiene frontmatter YAML navegable por agentes |
| **Accesibilidad sobre tecnicismo** | Lección de mitad de serie: preferir framing universal a jerga técnica |

---

## Proyecto demo: RCA (Resin Craft Art)

Proyecto real usado como hilo demo a lo largo de toda la serie. Ver **[[Proyectos/RCA/index]]** para el detalle completo:

- `Developer/` — decisiones de arquitectura, dead-ends, sprints
- `Equipo/` — 7 perfiles de madurez IA + assessment framework + OKR de capacidad IA del equipo

---

## Cómo contribuir

1. **Crear un fichero nuevo:** Usa las plantillas de `Plantillas/` para mantener el formato OKF
2. **Conectar conceptos:** Añade `related:` en el frontmatter y `[[wikilinks]]` en el cuerpo
3. **Mantener el grafo:** Si creas un concepto nuevo, añádelo en `index.md` y clasifícalo en el `nivel-X` correspondiente (evita dejarlo suelto en la raíz de `Conceptos/`)

---

## Punto de entrada para agentes

Ver **[[index]]** para el mapa de navegación completo del vault. Los agentes deben empezar por ahí para navegar el grafo de conocimiento.
