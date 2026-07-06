---
type: Concepto
title: "Graphify — Grafo de conocimiento para asistentes de IA"
description: "Skill de código abierto que convierte un repositorio en un grafo de conocimiento consultable. La IA lee el mapa del proyecto en lugar de recorrer fichero a fichero."
tags: [graphify, grafo, arquitectura, claude, contexto, angular, codebase, karpathy]
related: [arnes-completo, sdd, mcp, okf, wiki-llm]
charla: "Charla 8 (bonus), Charla 11"
estado: "✅ Publicado"
timestamp: "2026-07-02"
---

# Graphify — Grafo de conocimiento para asistentes de IA

> _"En lugar de que Claude recorra cada fichero como quien busca a pie en una ciudad sin mapa, Graphify construye el mapa primero. Claude lo lee y navega directo."_

---

## Qué es

Graphify es una skill de código abierto para asistentes de IA como Claude Code, Codex u OpenCode. Toma un repositorio — código fuente, documentación, schemas SQL, PDFs, imágenes — y lo convierte en un **grafo de conocimiento consultable**: un mapa de relaciones entre componentes, módulos, funciones y conceptos que el agente puede recorrer en lugar de releer ficheros.

Fue inspirado por una idea de Andrej Karpathy sobre construir bases de conocimiento para LLMs. El proyecto lo mantiene Safi Shamsi, está publicado bajo licencia MIT y se distribuye en PyPI como `graphifyy` (doble y). El comando CLI sigue siendo `graphify`.

---

## El problema que resuelve

Sin Graphify, cada sesión de Claude Code empieza desde cero. El agente no recuerda la arquitectura del proyecto de la sesión anterior. Para orientarse, recorre fichero a fichero con llamadas a `grep` — en un proyecto de ~40 ficheros, eso puede consumir 20.000 tokens solo para que Claude se ubique.

**Graphify resuelve el problema en el origen:** construye el mapa una vez, y Claude lee el mapa.

---

## Cómo funciona

**Fase 1 — Análisis estático con Tree-sitter (0 tokens)**
Parsea el código directamente: clases, funciones, imports, call graphs. Soporta 31 lenguajes incluyendo TypeScript, JavaScript, Python, Go, Java, SQL y más.

**Fase 2 — Extracción semántica con LLM (solo para docs, PDFs e imágenes)**
Para ficheros no ejecutables, usa el modelo configurado para extraer conceptos y relaciones que el análisis estático no puede ver.

### Outputs en `graphify-out/`

| Fichero | Contenido | Para quién |
|---|---|---|
| `graph.json` | El grafo completo, consultable | Claude Code |
| `GRAPH_REPORT.md` | Resumen: god nodes, conexiones inesperadas | Claude Code + tú |
| `graph.html` | Visualización interactiva en el navegador | Revisión humana |
| `cache/` | SHA256 por fichero para actualizaciones incrementales | Interna |

---

## Instalación rápida

```bash
# Instalar
uv tool install graphifyy

# Registrar la skill con Claude Code
graphify install

# Construir el grafo del proyecto
graphify .

# Solo lo que ha cambiado (más rápido)
graphify . --update

# Generar vault de Obsidian desde el grafo
graphify . --obsidian
```

> ⚠️ El paquete en PyPI se llama `graphifyy` (doble y).

---

## Graphify vs Obsidian

| Capa | Herramienta | Qué aporta |
|---|---|---|
| Estructura del código | Graphify | Qué existe, qué depende de qué |
| Decisiones y contexto | Obsidian | Por qué existe así, qué no tocar |
| Reglas del proyecto | CLAUDE.md | Cómo debe comportarse el agente |

Graphify mapea **estructura**, no **intención**. Para el contexto de negocio y las decisiones está Obsidian.

---

## Notas técnicas

- TypeScript es ciudadano de primera clase — incluye tipos, interfaces y decoradores de Angular
- Sin telemetría — el análisis de código es 100% local
- MCP server incluido: `graphify . --mcp` expone el grafo como herramienta para cualquier agente compatible
- Compatible con Claude Code, Codex, Cursor, Gemini CLI, GitHub Copilot CLI y más

---

## Relación con otras piezas

- **[[mcp]]** — Graphify puede exponerse como servidor MCP (`--mcp`)
- **[[sdd]]** — Los `spec.md` del flujo SDD son candidatos a incluirse en el vault de Obsidian que complementa el grafo
- **[[skills]]** — Graphify es en sí mismo una skill: se instala como fichero de instrucciones
- **[[okf]]** — El flag `--obsidian` genera un vault inicial al que luego se aplica OKF

---

## Dónde aparece en la serie

| Charla | Rol de Graphify |
|---|---|
| 8 | Bonus — hook en `settings.json` que lee el grafo antes de cada sesión |
| 11 | Parte del ciclo completo: grafo + vault OKF + SDD + agente |

---

## Referencias

- Repositorio oficial: [github.com/safishamsi/graphify](https://github.com/safishamsi/graphify)
- PyPI: `pip install graphifyy`
