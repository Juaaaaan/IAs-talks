# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

An Obsidian vault — the second brain for an internal AI talk series. No build system, no tests, no dependencies. All content is Markdown.

The vault is managed via the **Claudian** plugin (`.obsidian/plugins/realclaudian/`), which runs Claude from inside Obsidian. Plugin settings live in `.claudian/claudian-settings.json`.

## Folder structure

| Folder | Purpose |
|---|---|
| `Charlas/` | Script, checklist, and notes for each talk session |
| `Conceptos/` | Definitions of the key concepts in the series |
| `Demos/` | Specs, configs, and step-by-step guides for live demos |
| `Recursos/` | Reusable technical references |

## Narrative arc (critical context)

The series builds a cumulative narrative across ten talks around the **arnés completo** (complete harness) metaphor:

```
SDD    → arnés documental   (what to build)
Skills → arnés de comportamiento  (how to behave)
MCPs   → arnés de integración     (how to act in the real world)
─────────────────────────────────────────────────
The three together = el arnés completo
```

Each talk adds one piece. `[[arnes-completo]]` is the connecting thread across all talks.

## Talk series status

| # | Title | Status |
|---|---|---|
| 1–6 | Previous series (inherited) | Done |
| 7 | Skills, MCPs y el Arnés Completo | Done — 17 Jun 2026 |
| 8 | SDD applied to an Angular project | In preparation |
| 9 | Figma/Stitch MCP for design flows | Planned |
| 10 | Full cycle — arc closing | Planned |

## Content conventions

- Internal links use Obsidian `[[wikilink]]` syntax. Cross-references between notes are intentional and load-bearing — preserve them.
- All content is in Spanish.
- Each talk note links to its demo note and relevant concept notes. Keep this structure consistent when adding new talks.
- The `Demos/` folder contains specs and step-by-step configs for live demos; these are separate from the talk narrative notes in `Charlas/`.

## Key source of truth

The web repo (Next.js) is the source of truth for talk **code**. This vault is the source of truth for **narrative and design decisions**.

## Principles (affect how content should be written)

- **Demo first, always.** Every talk maximizes live demo time. Theory blocks are kept short and concrete.
- **Cumulative narrative.** What is explained in one talk is the foundation for the next. Concepts are not re-introduced without a conscious decision.
- **Mixed audience.** 60–90 attendees: junior and senior developers, HR, executives. Concepts must land for everyone.
