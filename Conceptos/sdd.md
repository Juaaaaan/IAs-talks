---
type: Concepto
title: "SDD — Specification-Driven Development"
description: "Metodología donde los requisitos se expresan en ficheros markdown estructurados antes de que la IA genere código"
tags: [sdd, spec, documentacion, arnes, desarrollo, task, plan]
related: [arnes-completo, skills, mcp, copilot-instructions]
charla: "Charlas 7-8"
estado: "✅ Publicado"
timestamp: "2026-06-17"
---

# SDD — Specification-Driven Development

> _"El arnés documental le dice qué hacer."_

---

## Qué es

SDD es una forma de trabajar con IA en la que los requisitos y el contexto del trabajo se expresan en ficheros de texto estructurados antes de que la IA empiece a generar código o tomar decisiones.

En lugar de darle instrucciones a la IA en conversaciones ad hoc, el equipo mantiene documentos vivos que la IA puede leer y seguir de forma consistente.

---

## Los tres ficheros clave

|Fichero|Qué contiene|Quién lo usa|
|---|---|---|
|`spec.md`|Qué hay que construir: objetivo, usuarios, funcionalidad, criterios de aceptación|IA + equipo|
|`plan.md`|Cómo se organiza el trabajo: fases, dependencias, orden de implementación|IA + tech lead|
|`task.md`|Desglose de tareas concretas listas para ejecutar|IA en cada sesión|

---

## Por qué funciona

Sin SDD, cada conversación con la IA empieza desde cero. Con SDD, la IA siempre tiene el contexto completo de qué se está construyendo y por qué.

El `spec.md` es especialmente importante: es el documento del que nacen los issues de Jira, el `task.md` que guía a Claude Code, y el criterio de aceptación que valida el resultado.

---

## En la metáfora del arnés

El SDD es el **arnés documental**: las instrucciones concretas para una carrera concreta. Le dice al caballo (la IA) adónde tiene que ir hoy.

Se diferencia de [[skills]] en que el SDD es específico por proyecto o feature, mientras que los Skills son transversales a todo el equipo.

---

## Relación con otras piezas

- **[[skills]]** — El SDD define el qué; los Skills definen el cómo comportarse siempre
- **[[mcp]]** — Los MCPs permiten que la IA actúe sobre el `spec.md` directamente (ej: crear issues en Jira a partir del spec)
- **[[arnes-completo]]** — El SDD es la primera pieza del arnés
- **[[copilot-instructions]]** — Las instrucciones del proyecto complementan el SDD con el contexto técnico

---

## Dónde aparece en la serie

|Charla|Rol del SDD|
|---|---|
|6|Concepto central — introducción completa|
|7|Pieza de base sobre la que se añaden Skills y MCPs|
|8|El `task.md` como fuente de verdad para los agentes developer y reviewer|

---

## Ejemplo de spec.md

Ver `Recursos/task-rca-20.md` — el task usado en la demo de Charla 8.
