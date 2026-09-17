---
type: Concepto
title: "IA en el review de PRs — La revisión como cuello de botella"
description: "Usar agentes para revisar pull requests: capas de review agéntico + review humano reservado a lo crítico. Cuando la IA escribe el código, revisar es el nuevo tapón."
tags: [code-review, pull-request, revision, agentes, calidad, ci]
related: [orchestration-patterns, agentes-multiples, eval-benchmarking, ai-native-sdlc, github-actions]
estado: "✅ Publicado"
timestamp: "2026-09-17"
---

# IA en el review de PRs — La revisión como cuello de botella

> _"Si un agente abre diez PRs en una tarde y tú revisas a mano, el tapón ya no es escribir código: es leerlo."_

---

## Qué es

Es usar **agentes de IA para revisar pull requests**: comentar el diff, detectar bugs, fallos de seguridad, incumplimientos de estilo o de las reglas del proyecto, *antes* (o junto a) la revisión humana.

La idea de fondo del AI-Native SDLC: cuando la IA genera el código, la **revisión** se convierte en el cuello de botella. Escalar la generación sin escalar la revisión solo mueve el atasco.

---

## Cómo se estructura

Por capas, de barato a caro:

1. **Checks deterministas** — lint, tests, [[eval-benchmarking|evals]], análisis estático. No opinan: pasan o fallan.
2. **Review agéntico** — un agente revisor comenta el PR contra las reglas del proyecto y los criterios de la spec.
3. **Review humano** — reservado para lo **crítico y regulado**. El humano no revisa todo; revisa lo que importa, con el trabajo previo ya filtrado.

La clave es esa reserva: el ojo humano es el recurso escaso, así que se gasta donde el riesgo lo justifica.

---

## No confundir con el patrón

El patrón de coordinación developer/reviewer está en **[[orchestration-patterns]]** (el "cómo se coordinan"). Esta nota es la *etapa* del ciclo: el review como control de calidad de entrega, con la reserva humana para lo crítico. Topología vs. práctica de entrega.

---

## Ojo con

- Un revisor agéntico que da **verde en falso** es peor que no tenerlo: genera confianza injustificada. Por eso, review humano en lo crítico, siempre.
- El agente que revisa no debería ser el mismo que escribió (sesgo). Mejor un agente o rol distinto — enlaza con [[agentes-multiples]].

---

## Relación con otras piezas

- **[[orchestration-patterns]]** — El patrón developer/reviewer que implementa este review
- **[[agentes-multiples]]** — Separar quien escribe de quien revisa
- **[[eval-benchmarking]]** — La capa determinista bajo el review
- **[[ai-native-sdlc]]** — Es la etapa Deploy (review de PRs) del ciclo
- **[[github-actions]]** — Donde se enganchan los checks automáticos

---

## Referencias

- [AI in the PR review loop — Claude Academy](https://academy.claude.com/courses/ai-native-sdlc-playbook/ai-in-the-pr-review-loop)
