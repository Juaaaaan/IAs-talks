---
type: Concepto
title: "ODD — Organic Driven Development"
description: "Protocolo por defecto para peticiones sin spec ni escenario: autorizar, explorar en proporción, clasificar pequeño/sustancial y documentar antes de código solo si es sustancial"
tags: [odd, arnes, agentes, protocolo, clasificacion, gentle-ai]
related: [sdd, bdd, arnes-completo, ai-harness-engineering]
charla: "Charla 23"
estado: "✅ Publicado"
timestamp: "2026-10-14"
---

# ODD — Organic Driven Development

> _"No es la opción ligera que elegís cuando no os apetece hacer las cosas bien. Es el comportamiento por defecto — pero solo si alguien le escribió esa disciplina al agente."_

---

## Qué es

ODD es el protocolo que un agente de IA sigue por defecto para cualquier petición que no venga con un spec ([[sdd|SDD]]) ni un escenario ([[bdd|BDD]]) explícito. No es "escribir un prompt y confiar" — es una secuencia de pasos escrita como instrucción persistente, que el agente ejecuta antes de tocar código:

1. **Autorizar** — ¿es un cambio real o solo una pregunta/investigación? Si es solo explicar, no toca código.
2. **Explorar en proporción** — revisa el código relevante según el tamaño de la petición, no todo el proyecto para un cambio trivial.
3. **Resolver dudas con moderación** — como mucho una intervención: una pregunta concreta, o una advertencia sobre una suposición arriesgada. Nunca interroga.
4. **Clasificar** — **sustancial** si la exploración revela 2 o más pasos de implementación reales (o trabajo que merecería poder recuperarse si se interrumpe); **pequeño** en cualquier otro caso.
5. **Sustancial → documento de tareas antes de código.** Objetivo, alcance, límites, checklist con criterios de aceptación, evidencia de verificación, progreso, siguiente paso — normalmente en `odd/tasks/<feature>.md`.
6. **Pequeño → directo, sin rastro.**
7. **Implementar tarea por tarea** (solo sustancial) — cada tarea cierra con su propio commit y con prueba *observada*, nunca porque "debería funcionar".
8. **Cerrar con resumen verificado** — qué se comprobó, qué quedó pendiente o falló, cuál es el siguiente paso.

---

## El matiz que importa

Nada de esto es comportamiento de fábrica de un LLM. Es el mismo modelo de siempre (el que hay detrás de Copilot, Claude Code, etc.) razonando sobre la petición — pero con una regla escrita que debe aplicar antes de actuar. Sin esa instrucción, un buen agente explora algo de forma natural, sí, pero no clasifica el trabajo ni crea un documento de tareas por su cuenta.

Eso es, literalmente, lo que significa [[ai-harness-engineering|AI harness engineering]]: no se cambia el modelo, se le escribe la disciplina que lo rodea.

---

## ODD no compite con SDD ni BDD — los anida

> _"SDD is a branch inside ODD, entered only by an explicit request or an accepted proposal."_ — [gentle-ai docs](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/usage.md#organic-driven-development-odd)

ODD es el chasis que corre siempre. [[sdd|SDD]] es una rama a la que se entra deliberadamente — pedirlo explícitamente no cambia nada de cómo funciona SDD hoy, solo define qué pasa cuando *no* se pide. Un escenario [[bdd|BDD]] tampoco compite: puede ser precisamente el criterio de aceptación que va dentro del documento de tareas que ODD crea para trabajo sustancial.

```
Por defecto, en cualquier petición        →  ODD (explorar, clasificar, hacer con prueba)
Se pide explícitamente spec o escenario   →  SDD / BDD (documento o escenario por escrito)
```

---

## Cómo se activa sin instalar nada

El framework [gentle-ai](https://github.com/Gentleman-Programming/gentle-ai) (de Alan Buscaglia / Gentleman Programming) inyecta este protocolo de fábrica. Pero no hace falta instalarlo: es una instrucción persistente más, como las que ya se usan en `CLAUDE.md` o `copilot-instructions.md` — se puede escribir la misma disciplina a mano, sin ninguna dependencia nueva.

---

## Relación con otras piezas

- **[[sdd]]** — la rama explícita a la que ODD da paso cuando se pide
- **[[bdd]]** — el escenario que puede vivir dentro del documento de tareas de ODD
- **[[ai-harness-engineering]]** — el término de industria que explica por qué esto funciona
- **[[arnes-completo]]** — ODD es el comportamiento por defecto del arnés cuando no se invoca ninguna pieza explícita

---

## Dónde aparece en la serie

| Charla | Rol del concepto |
|---|---|
| 16 | Dejó abierta la pregunta spec manual vs OpenSpec — ODD la responde formalmente |
| 23 | Se introduce por nombre, como contrapeso a BDD para lo que no merece un escenario |
