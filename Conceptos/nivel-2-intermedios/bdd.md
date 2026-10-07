---
type: Concepto
title: "BDD — Behavior-Driven Development"
description: "Técnica de verificación: describir el resultado esperado como una historia (dado/cuando/entonces) antes de dar una tarea por terminada"
tags: [bdd, tdd, testing, verificacion, given-when-then]
related: [sdd, ia-first]
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

## BDD vs TDD

Quien programa tiene una versión más técnica del mismo instinto: **TDD** (Test-Driven Development), donde el "dado/cuando/entonces" se escribe como test automático antes que el propio código. Para el día a día de la mayoría, con contar la historia en lenguaje llano (BDD) basta — TDD es la forma de llevar la misma idea al terreno del código.

---

## Relación con otras piezas

- **[[sdd]]** — SDD especifica qué construir antes de construirlo; BDD verifica que lo construido cumple lo pedido. Dos mitades de la misma disciplina
- **[[ia-first]]** — BDD es la forma concreta de aplicar la segunda pregunta de IA-first ("¿cómo verifico?")

---

## Dónde aparece en la serie

| Charla | Rol del concepto |
|---|---|
| 16 | Usado sin nombrarse — el spec de OpenSpec para RCA incluye escenarios dado/cuando/entonces |
| 22 | Se le pone nombre explícitamente, generalizado fuera del código, con TDD como su versión técnica |
