---
type: Concepto
title: "BDD — Behavior-Driven Development"
description: "Técnica de verificación: describir el resultado esperado como una historia (dado/cuando/entonces) antes de dar una tarea por terminada"
tags: [bdd, tdd, testing, verificacion, given-when-then]
related: [sdd, ia-first, gherkin, odd]
charla: "Charla 22"
estado: "✅ Publicado"
timestamp: "2026-10-07"
---

# BDD — Behavior-Driven Development

> _"Antes de dar algo por bueno tú solo, pregúntale a la IA que lo ponga a prueba."_

---

## Qué es

BDD describe el resultado que esperas de una tarea como una historia, en formato dado/cuando/entonces, en vez de darla por buena solo porque te lo parece: *"dado que [contexto], cuando [acción], entonces [resultado esperado]"*. Ese relato sirve como criterio de verificación — algo contra lo que comprobar si la tarea cumple lo que de verdad querías.

No hace falta saber programar para usarlo: funciona igual para un filtro de una web que para un email delicado, pidiéndole a la IA que actúe como el destinatario y busque ambigüedades, objeciones o cosas que podrían entenderse mal. La IA no valida la verdad ni sustituye una revisión experta — hace de segundo par de ojos.

---

## El lenguaje de los escenarios: Gherkin

El formato dado/cuando/entonces tiene nombre y sintaxis propia: **[[gherkin|Gherkin]]**. Define palabras clave (`Feature`, `Scenario`, `Given`, `When`, `Then`, `Scenario Outline`...) que hacen que un escenario sea legible tanto por una persona como por una IA, sin ambigüedad. Ver [[gherkin]] para la sintaxis completa y ejemplos.

---

## BDD vs TDD

Quien programa tiene una versión más técnica del mismo instinto: **TDD** (Test-Driven Development), donde el "dado/cuando/entonces" se escribe como test automático antes que el propio código. Para el día a día de la mayoría, con contar la historia en lenguaje llano (BDD) basta — TDD es la forma de llevar la misma idea al terreno del código.

---

## No todo merece un escenario

BDD vale la pena cuando el criterio de éxito merece quedar escrito — no para cada cambio trivial. Para lo que no lo merece (cambiar un color, una errata), el contrapeso es **[[odd|ODD]]**: el agente explora, clasifica y actúa sin necesidad de un escenario formal.

---

## Relación con otras piezas

- **[[sdd]]** — SDD especifica qué construir antes de construirlo; BDD verifica que lo construido cumple lo pedido. Dos mitades de la misma disciplina
- **[[ia-first]]** — BDD es la forma concreta de aplicar la segunda pregunta de IA-first ("¿cómo verifico?")
- **[[gherkin]]** — el lenguaje concreto en el que se escriben los escenarios de BDD
- **[[odd]]** — el contrapeso: lo que se usa cuando no merece la pena escribir un escenario

---

## Dónde aparece en la serie

| Charla | Rol del concepto |
|---|---|
| 16 | Usado sin nombrarse — el spec de OpenSpec para RCA incluye escenarios dado/cuando/entonces |
| 22 | Se le pone nombre explícitamente, generalizado fuera del código, con TDD como su versión técnica |
| 23 | Se enseña la sintaxis Gherkin completa (keywords, Scenario Outline) y su uso también para fixes, no solo features; se contrasta con ODD como contrapeso |
