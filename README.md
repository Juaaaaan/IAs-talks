---
type: Indice
title: "IAs-talks — Base de conocimiento"
description: "Vault de conocimiento de la serie de charlas de IA. Wiki LLM en formato OKF navegable por agentes y humanos. 100+ ficheros markdown interconectados."
tags: [indice, vault, wiki-llm, okf, ia, charlas, conocimiento]
timestamp: "2026-11-27"
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
├── Conceptos/            ← 126 conceptos, todos clasificados por nivel, sin ficheros sueltos
│   ├── nivel-1-fundamentos/  ← Conceptos de la serie de charlas (31)
│   ├── nivel-2-intermedios/  ← Conceptos técnicos intermedios (36)
│   ├── nivel-3-avanzados/    ← Patrones y arquitecturas (41)
│   └── nivel-4-frontera/     ← Tecnologías emergentes 2026-2027 (18)
├── Demos/                ← Paso a paso de demos en vivo (8)
├── Recursos/             ← Ficheros de referencia — configs, agentes, tasks, novedades
├── Proyectos/            ← Wikis LLM de proyectos reales (ej. RCA)
│   └── RCA/
│       ├── Developer/    ← Decisiones técnicas del proyecto
│       └── Equipo/       ← Perfiles de madurez IA del equipo (7 perfiles)
└── Plantillas/           ← Templates OKF para nuevos ficheros
```

> **Nota sobre `Conceptos/`:** cada concepto vive en un único fichero, en su carpeta `nivel-X` correspondiente. No hay ficheros sueltos en la raíz ni ficheros "redirect" duplicando nombres entre niveles.

---

## La narrativa de la serie

La serie construye un arco acumulativo. El hilo conductor es el **arnés completo**: el conjunto de piezas que permiten a la IA trabajar de forma estructurada, consistente y conectada al entorno real de la empresa. Desde la Charla 23, este arnés tiene nombre de industria: **AI harness engineering**.

```
SDD           →  arnés documental          (qué construir)
Skills        →  arnés de comportamiento   (cómo comportarse)
MCPs          →  arnés de integración      (cómo actuar en el mundo real)
Instrucciones →  arnés del proyecto        (cómo conocer el código)
Wiki LLM      →  arnés del conocimiento    (por qué se hacen las cosas)
──────────────────────────────────────────────────────────────────────────────────────────────────────────
Las cinco juntas = el arnés completo = AI harness engineering
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
| 14 | [[charla-14-gobernanza\|Gobernanza de la IA: Shadow AI, EU AI Act y los 5 niveles de riesgo]] | ✅ Impartida — 29 jul 2026 |
| 15 | [[charla-15-seguridad\|Seguridad en IA: cuando el dato y la instrucción se confunden]] | ✅ Impartida — 5 ago 2026 |
| 16 | [[charla-16-sdd-herramientas\|SDD con herramientas: spec manual vs OpenSpec]] | ✅ Impartida — 12 ago 2026 |
| 17 | [[charla-17-elegir-ia\|Elegir bien la IA: herramienta, modelo y modo de trabajo]] | ✅ Impartida — 19 ago 2026 |
| 18 | [[charla-18-como-piensa-la-ia\|Abriendo la caja: cómo piensa la IA por dentro]] | ✅ Impartida — 26 ago 2026 |
| 19 | [[charla-19-de-responder-a-actuar\|De responder a actuar: equipo de agentes y checkpoint humano]] | ✅ Impartida — 2 sep 2026 |
| 20 | [[charla-20-el-ejecutor-abierto\|La otra correa del arnés: el ejecutor abierto (OpenCode)]] | ✅ Impartida — 16 sep 2026 |
| 21 | — Copilot, WorkIQ y PowerPoints (impartida por un compañero, sin ficha en el vault) | ✅ Impartida |
| 22 | [[charla-22-preguntale-primero\|Pregúntale primero: mentalidad IA-first]] | ✅ Impartida — 7 oct 2026 |
| 23 | [[charla-23-comprobar-antes-de-construir\|Comprobar antes de construir: BDD, ODD y el arnés con nombre]] | ✅ Impartida — 14 oct 2026 — récord de asistencia (141) |

> Serie en curso (7–23 impartidas, con la 21 fuera del pipeline del vault por no haberla dado Juan). El propietario original de la serie recuperó la titularidad en septiembre y sigue coexistiendo con este pipeline. El arco del arnés completo se cerró en la 13; desde la 14 la serie continúa con bloques temáticos independientes. Próxima charla: por definir — queda reservada una sesión futura para la mitad "después de construir" de Comprobar (ai-code-review + RDD).

---

## Conceptos del vault (126)

| Nivel | Fichas |
|---|---|
| nivel-1-fundamentos | 31 |
| nivel-2-intermedios | 36 |
| nivel-3-avanzados | 41 |
| nivel-4-frontera | 18 |

La lista completa, con una descripción de cada concepto, está en **[[index]]**. Aquí no se repite para que no se quede desactualizada.

---

## Demos (8)

| Fichero | Charla |
|---|---|
| [[demo-jira-charla-7]] | Charla 7 — Jira + SDD con Claude Desktop |
| [[demo-copilot-instrucciones-charla-8]] | Charla 8 — Copilot con instrucciones |
| [[demo-faq-onboarding]] | Charla 13 — FAQ de onboarding con handbook corporativo |
| [[demo-politica-teletrabajo]] | Charla 13 — Política de teletrabajo vía agente + Teams |
| [[demo-openspec-charla-16]] | Charla 16 — OpenSpec + Claude Code sobre RCA |
| [[demo-rfp-charla-19]] | Charla 19 — El Analista de RFP: equipo de agentes con checkpoint humano |
| [[demo-opencode-charla-20]] | Charla 20 — El menú de OpenCode |
| [[demo-bdd-charla-23]] | Charla 23 — BDD con Gherkin sobre el carrito de RCA |

---

## Principios de la serie

| Principio | Descripción |
|---|---|
| **Demo primero** | La audiencia desconecta en teoría y vuelve en demos |
| **Narrativa acumulativa** | Cada charla es la base de la siguiente |
| **Audiencia mixta** | 60–170 asistentes: developers, RRHH, directivos, comerciales |
| **Herramientas reales** | Demos con proyectos reales (RCA), herramientas del día a día |
| **Estándar OKF** | Todo fichero tiene frontmatter YAML navegable por agentes |
| **Un concepto, un fichero, un nivel** | Nada de duplicados ni redirects — si un concepto sube de nivel, se mueve, no se copia |
| **Accesibilidad sobre tecnicismo** | Lección de mitad de serie: preferir framing universal a jerga técnica |
| **Demos reproducibles cuando el riesgo lo permite** | Desde la 19, varias charlas incluyen tutorial paso a paso reproducible; desde la 23, cuando clasificar la petición en vivo es parte del riesgo, se prepara la demo de antemano en vez de generar en directo |

---

## Proyecto demo: RCA (Resin Craft Art)

Proyecto real usado como hilo demo a lo largo de toda la serie. Ver **[[Proyectos/RCA/index]]** para el detalle completo:

- `Developer/` — decisiones de arquitectura, dead-ends, sprints
- `Equipo/` — 7 perfiles de madurez IA + assessment framework + OKR de capacidad IA del equipo

---

## Cómo contribuir

1. **Crear un fichero nuevo:** Usa las plantillas de `Plantillas/` para mantener el formato OKF
2. **Conectar conceptos:** Añade `related:` en el frontmatter y `[[wikilinks]]` en el cuerpo — en formato de array simple (`related: [a, b, c]`), no en lista multilínea, para que el grafo se pueda generar automáticamente
3. **Un concepto = un nivel = un fichero:** Clasifica cada concepto nuevo directamente en su carpeta `nivel-X` — nunca sueltos en la raíz de `Conceptos/`, y nunca duplicado en dos niveles a la vez
4. **Mantener el grafo:** Si creas un concepto nuevo, añádelo en `index.md`

---

## Punto de entrada para agentes

Ver **[[index]]** para el mapa de navegación completo del vault. Los agentes deben empezar por ahí para navegar el grafo de conocimiento.
