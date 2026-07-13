---
type: Concepto
title: "Graphify — Grafo de conocimiento para asistentes de IA"
description: "Herramienta que genera un grafo de conocimiento del proyecto para que la IA entienda la arquitectura completa sin explorar fichero a fichero."
tags: [graphify, grafo, arquitectura, claude, contexto, angular, codebase, graphrag]
related: [arnes-completo, sdd, mcp, okf, wiki-llm, knowledge-graphs]
charla: "Charla 8 (bonus), Charla 11"
nivel: 3
estado: "✅ Publicado"
timestamp: "2026-07-02"
---

# Graphify — Grafo de conocimiento para asistentes de IA

> _"En lugar de que Claude recorra cada fichero como quien busca a pie en una ciudad sin mapa, Graphify construye el mapa primero. Claude lo lee y navega directo."_

---

## Qué es

Graphify es una skill de código abierto para asistentes de IA como Claude Code, Codex u OpenCode. Toma un repositorio — código fuente, documentación, schemas SQL, PDFs, imágenes — y lo convierte en un **grafo de conocimiento consultable**: un mapa de relaciones entre componentes, módulos, funciones y conceptos que el agente puede recorrer en lugar de releer ficheros.

Fue inspirado por una idea de Andrej Karpathy sobre construir bases de conocimiento para LLMs. Se distribuye en PyPI como `graphifyy` (doble y).

---

## Relación con knowledge graphs

Graphify es una implementación práctica de [[knowledge-graphs]] aplicada al código. Donde knowledge-graphs es el concepto general, Graphify es la herramienta específica para codebases.

---

## El problema que resuelve

Sin Graphify, cada sesión de Claude Code empieza desde cero. En un proyecto de ~40 ficheros, el agente puede consumir 20.000 tokens solo para orientarse.

**Graphify resuelve el problema en el origen:** construye el mapa una vez, y Claude lee el mapa.

---

## Cómo funciona

**Fase 1 — Análisis estático con Tree-sitter (0 tokens)**
Parsea el código: clases, funciones, imports, call graphs. Soporta 31 lenguajes.

**Fase 2 — Extracción semántica con LLM (solo para docs, PDFs e imágenes)**
Para ficheros no ejecutables, usa el modelo configurado para extraer conceptos y relaciones.

### Outputs en `graphify-out/`

| Fichero | Contenido |
|---|---|
| `graph.json` | El grafo completo, consultable |
| `GRAPH_REPORT.md` | Resumen: god nodes, conexiones inesperadas |
| `graph.html` | Visualización interactiva en el navegador |

---

## Instalación rápida

```bash
uv tool install graphifyy
graphify install
graphify .
graphify . --update
graphify . --obsidian
```

---

## Dónde aparece en la serie

| Charla | Rol de Graphify |
|---|---|
| 8 | Bonus — hook en `settings.json` que lee el grafo antes de cada sesión |
| 11 | Parte del ciclo completo: grafo + vault OKF + SDD + agente |
