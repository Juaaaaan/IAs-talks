---
type: Indice
title: "IAs-talks — Base de conocimiento"
description: "Vault de conocimiento de la serie de charlas de IA. Sigue el estándar OKF para que cualquier agente pueda navegar el contenido semánticamente."
tags: [indice, vault, wiki-llm, okf, ia, charlas]
timestamp: "2026-07-06"
---

# 🧠 IA Talks — Base de conocimiento

Este vault es el segundo cerebro de la serie de píldoras informativas sobre IA que impartimos internamente. Sigue el estándar **[[okf]]** (Open Knowledge Format) — todos los ficheros tienen frontmatter estructurado para que cualquier agente pueda navegar el contenido semánticamente.

---

## Qué hay aquí

|Carpeta|Contenido|
|---|---|
|`Charlas/`|Resumen narrativo de cada sesión impartida|
|`Conceptos/`|Definiciones de los conceptos clave de la serie|
|`Demos/`|Paso a paso de las demos en vivo|
|`Recursos/`|Ficheros de referencia reutilizables — configs, agentes, tasks|
|`Proyectos/`|Proyectos demo de la serie (ej. RCA)|

---

## La narrativa de la serie

La serie construye un arco narrativo. El hilo conductor es el **arnés completo**: el conjunto de piezas que permiten a la IA trabajar de forma estructurada, consistente y conectada al entorno real de la empresa.

```
SDD          →  el arnés documental        (qué construir)
Skills       →  el arnés de comportamiento (cómo comportarse)
MCPs         →  el arnés de integración    (cómo actuar)
Instrucciones → el arnés del proyecto     (cómo conocer el código)
Wiki LLM     →  el arnés del conocimiento  (por qué se hacen las cosas)
────────────────────────────────────────────────────────
Las cinco juntas = el arnés completo
```

---

## Charlas de la serie

|#|Título|Estado|
|---|---|---|
|1–6|Serie anterior (heredada)|✅ Impartidas|
|7|[[charla-07-skills-mcps\|Skills, MCPs y el Arnés Completo]]|✅ Impartida — 17 jun 2026|
|8|[[charla-08-copilot-instrucciones\|Instruyendo a la IA: .github/ y .claude/]]|✅ Impartida|
|9-10|Serie empresa (heredadas)|✅ Impartidas|
|11|Wiki LLM con Obsidian, GitHub y OKF|🔜 En preparación|
|12|GitHub Actions + Copilot coding agent|📋 Planificada|
|13|El ciclo completo — cierre del arco|📋 Planificada|

---

## Conceptos clave

- [[arnes-completo]] — La metáfora central de la serie
- [[sdd]] — Specification-Driven Development
- [[skills]] — El arnés de comportamiento
- [[mcp]] — Model Context Protocol
- [[copilot-instructions]] — Instrucciones persistentes para Copilot
- [[agentes-multiples]] — Patrón developer/reviewer
- [[frontmatter]] — Metadatos YAML en ficheros markdown
- [[okf]] — Open Knowledge Format — estándar para Wiki LLM
- [[graphify]] — Grafo de conocimiento del codebase
- [[github-actions]] — Automatización con IA (charla futura)

---

## Principios de la serie

**Demo primero, siempre.** La audiencia desconecta en los bloques teóricos y vuelve en las demos.

**Narrativa acumulativa.** Lo que se explica en una charla es la base de la siguiente.

**Audiencia mixta.** De 60 a 90 asistentes: developers, RRHH, directivos, comerciales.

**Herramientas reales.** Las demos usan proyectos reales (RCA), herramientas del día a día.

**Estándar OKF.** Todos los ficheros siguen [[okf]] para que cualquier agente pueda navegar el vault semánticamente.

---

## Punto de entrada para agentes

Ver [[index]] para el mapa de navegación completo del vault.
