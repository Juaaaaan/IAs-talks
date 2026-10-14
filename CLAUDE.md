# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

An Obsidian vault — the second brain for an internal AI talk series. No build system, no tests, no dependencies. All content is Markdown.

The vault is managed via the **Claudian** plugin (`.obsidian/plugins/realclaudian/`), which runs Claude from inside Obsidian. Plugin settings live in `.claudian/claudian-settings.json`.

## Folder structure

| Folder | Purpose |
|---|---|
| `Charlas/` | Narrative summary, script and checklist for each talk session; `Charlas/guiones/` holds the full speaker script |
| `Conceptos/` | Definitions of the key concepts in the series, split into `nivel-1-fundamentos` through `nivel-4-frontera` |
| `Demos/` | Specs, configs, and step-by-step guides for live demos |
| `Recursos/` | Reusable technical references and the RCA project's own configuration artifacts |
| `Proyectos/` | Demo projects used as the live vehicle for the series (currently RCA — Resin Craft Art) |
| `Plantillas/` | OKF templates for new files (talk, concept, decision, demo, team profile) |

## Narrative arc (critical context)

The series builds a cumulative narrative around the **arnés completo** (complete harness) metaphor — known since Charla 23 by its industry term, **AI harness engineering**:

```
SDD           → arnés documental        (what to build)
Skills        → arnés de comportamiento (how to behave)
MCPs          → arnés de integración    (how to act in the real world)
Instrucciones → arnés del proyecto      (how to know the codebase)
Wiki LLM      → arnés del conocimiento  (why things are done this way)
─────────────────────────────────────────────────────────────────────
The five together = el arnés completo = AI harness engineering
```

Each talk adds to, or builds on, one or more pieces. `[[arnes-completo]]` and `[[ai-harness-engineering]]` are the connecting threads across all talks.

## Talk series status

The arc of "el arnés completo" closed at Charla 13. From Charla 14 onward the series continues as independent thematic blocks (governance, security, SDD tooling, choosing AI tools, how AI thinks internally, agents that act, the open executor, IA-first mindset, verifying before building). Charla 21 was given by a colleague, not Juan, and has no file in this vault.

| # | Title | Status |
|---|---|---|
| 1–6 | Previous series (inherited) | Done |
| 7–20 | Delivered — see `index.md` for the full table | Done |
| 21 | Copilot, WorkIQ, PowerPoints (colleague's talk) | Done — not tracked in this vault |
| 22 | Pregúntale primero — IA-first mindset | Done — 7 oct 2026 |
| 23 | Comprobar antes de construir — BDD, ODD, AI harness engineering | Done — 14 oct 2026, attendance record (141) |
| Next | TBD — a future talk is reserved for the "after building" half of Comprobar (ai-code-review + RDD) | Planned |

Always check `index.md` for the authoritative, up-to-date table — this file only tracks the big picture.

## Content conventions

- Internal links use Obsidian `[[wikilink]]` syntax. Cross-references between notes are intentional and load-bearing — preserve them.
- All content is in Spanish.
- Each talk note links to its demo note and relevant concept notes. Keep this structure consistent when adding new talks.
- The `Demos/` folder contains specs and step-by-step configs for live demos; these are separate from the talk narrative notes in `Charlas/`.
- Frontmatter's `related:` field should use simple array syntax (`related: [a, b, c]`), not a multiline list — several notes already drift from this, and normalizing it matters for any tool that will later build the knowledge graph from frontmatter instead of the hand-maintained ASCII tree in `index.md`.
- File naming has drifted across three conventions over the series (`charla-NN-slug.md`, `MATERIAL-CHARLA-N-TEMA.md`/`GUION-CHARLA-N-X.md`, and in `Proyectos/RCA/` an em-dash style). New files should use lowercase-with-hyphens; do not "fix" existing files without being asked.

## Key source of truth

The web repo (Next.js, `Juaaaaan/charlas`) is the source of truth for talk **code** and the live presentation. This vault is the source of truth for **narrative and design decisions**. A migration to embed this vault's knowledge graph as a navigable graph inside the `charlas` web repo is a planned next step (see `ways-of-working.md` in the companion Claude project).

## Principles (affect how content should be written)

- **Demo first, when the risk allows it.** Every talk maximizes live demo time. Theory blocks are kept short and concrete. Since Charla 19, several talks ship a step-by-step reproducible tutorial. Since Charla 23, when classifying the request live is itself part of what's being risked in front of the room, the demo is pre-built rather than generated live — the thesis should never depend on the model guessing correctly in real time.
- **Cumulative narrative.** What is explained in one talk is the foundation for the next. Concepts are not re-introduced without a conscious decision — callbacks to earlier talks are frequent and intentional.
- **Mixed audience.** Attendance has ranged roughly 60–170: junior and senior developers, HR, executives, commercial staff. Concepts must land for everyone; accessibility over technical depth was an explicit mid-series correction.
