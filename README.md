---
type: Indice
title: "IAs-talks — Base de conocimiento"
description: "Vault de conocimiento de la serie de charlas de IA. Wiki LLM en formato OKF navegable por agentes y humanos. 60+ ficheros markdown interconectados."
tags: [indice, vault, wiki-llm, okf, ia, charlas, conocimiento]
timestamp: "2026-07-13"
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
├── CLAUDE.md             ← Instrucciones para agentes que trabajan en el vault
│
├── Charlas/              ← Resumen narrativo de cada sesión impartida
│   └── guiones/          ← Scripts completos para el ponente
├── Conceptos/            ← 41 definiciones de conceptos técnicos de IA
│   ├── nivel-1-fundamentos/  ← Conceptos de la serie de charlas (11)
│   ├── nivel-2-intermedios/  ← Conceptos técnicos intermedios (10)
│   ├── nivel-3-avanzados/    ← Patrones y arquitecturas (10)
│   └── nivel-4-frontera/     ← Tecnologías emergentes 2026-2027 (10)
├── Demos/                ← Paso a paso de demos en vivo
├── Recursos/             ← Ficheros de referencia — configs, agentes, tasks
├── Proyectos/            ← Wikis LLM de proyectos reales (ej. RCA)
│   └── RCA/
│       ├── Developer/    ← Decisiones técnicas del proyecto
│       └── Equipo/       ← Perfiles de madurez IA del equipo
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
| 12 | GitHub Actions + Copilot coding agent | 📋 Planificada |
| 13 | El ciclo completo — cierre del arco | 📋 Planificada |

---

## Conceptos del vault (41)

### Conceptos fundacionales (serie de charlas)

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
- [[github-actions]] — Automatización con IA (charla futura)

### Conceptos de nivel 2 (intermedios)

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

### Conceptos de nivel 3 (avanzados)

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

### Conceptos de nivel 4 (frontera 2026-2027)

- [[reasoning-models]] — Modelos que piensan antes de responder (o1, o3)
- [[computer-use]] — Agentes que controlan la pantalla
- [[mcp-ecosystem]] — El ecosistema de servidores MCP
- [[ai-ide-patterns]] — Patrones de integración IA en el IDE
- [[sdd-variations]] — Variantes de SDD: Design Docs, RFC, ADR
- [[synthetic-data]] — Datos sintéticos y auto-entrenamiento
- [[constitutional-ai]] — Cómo se alinean los modelos (RLHF, CAI)
- [[ai-governance]] — Gobernanza: EU AI Act, ISO 42001
- [[federated-ai]] — IA sin depender de un solo proveedor
- [[autonomous-coding-agents]] — Agentes que programan solos

---

## Principios de la serie

| Principio | Descripción |
|---|---|
| **Demo primero** | La audiencia desconecta en teoría y vuelve en demos |
| **Narrativa acumulativa** | Cada charla es la base de la siguiente |
| **Audiencia mixta** | 60–90 asistentes: developers, RRHH, directivos, comerciales |
| **Herramientas reales** | Demos con proyectos reales (RCA), herramientas del día a día |
| **Estándar OKF** | Todo fichero tiene frontmatter YAML navegable por agentes |

---

## Cómo contribuir

1. **Crear un fichero nuevo:** Usa las plantillas de `Plantillas/` para mantener el formato OKF
2. **Conectar conceptos:** Añade `related:` en el frontmatter y `[[wikilinks]]` en el cuerpo
3. **Mantener el grafo:** Si creas un concepto nuevo, añádelo en `index.md`

---

## Punto de entrada para agentes

Ver **[[index]]** para el mapa de navegación completo del vault. Los agentes deben empezar por ahí para navegar el grafo de conocimiento.
