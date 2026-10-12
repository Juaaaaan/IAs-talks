---
type: Concepto
title: "Gherkin"
description: "Lenguaje estructurado (Feature/Scenario/Given/When/Then) para escribir escenarios BDD legibles tanto por personas como por IA"
tags: [gherkin, bdd, given-when-then, sintaxis, verificacion]
related: [bdd, sdd]
charla: "Charla 23"
estado: "✅ Publicado"
timestamp: "2026-10-14"
---

# Gherkin

> _"El escenario no se negocia después. Se escribe antes."_

---

## Qué es

Gherkin es el lenguaje con el que se escriben los escenarios de [[bdd|BDD]]: casi inglés (o español) natural, pero con una estructura fija que tanto una persona como una IA pueden leer sin ambigüedad.

```
Feature: [nombre de la funcionalidad]

  Scenario: [nombre del caso concreto]
    Given [situación de partida]
    When [ocurre una acción]
    Then [esto es lo que tiene que pasar]
```

---

## Palabras clave

| Palabra | Para qué sirve |
|---|---|
| `Feature` | Agrupa varios escenarios bajo una misma funcionalidad |
| `Scenario` | Un caso concreto, con nombre descriptivo |
| `Given` | El estado de partida — lo que ya es verdad antes de actuar |
| `When` | La acción que dispara el comportamiento a probar |
| `Then` | El resultado esperado — lo que se verifica |
| `And` / `But` | Encadenan pasos sin repetir Given/When/Then |
| `Scenario Outline` + `Examples` | El mismo caso repetido con distintos valores, sin copiar el escenario entero |

---

## Ejemplo

```gherkin
Feature: Inicio de sesión

  Scenario: Credenciales correctas
    Given que estoy en la página de login
    When introduzco un email y contraseña válidos
    Then accedo a mi panel de usuario
```

---

## Dos matices técnicos

- **Gherkin no ejecuta nada por sí mismo** — necesita algo detrás que conecte cada línea con el código real. Herramientas como Cucumber o Behave hacen eso tradicionalmente; con un agente de IA, ese papel lo puede hacer directamente el propio agente: lee el escenario, lo entiende, y comprueba si el comportamiento implementado lo cumple.
- **El `Then` es un contrato** — una vez escrito, no se negocia después. Si el resultado no coincide, el escenario falla y ya está.

---

## También sirve para fixes, no solo features

Un escenario Gherkin puede describir un bug como comportamiento esperado que ahora mismo falla — se escribe antes de tocar el código, no después. El escenario pasa a ser el ticket del bug, escrito como criterio de éxito, y se queda para siempre en la batería de pruebas: si alguien reintroduce el mismo bug meses después, el escenario vuelve a fallar y lo pilla antes de producción.

---

## Relación con otras piezas

- **[[bdd]]** — Gherkin es el lenguaje en el que se escriben los escenarios de BDD
- **[[sdd]]** — un escenario Gherkin puede vivir dentro de un `spec.md` como criterio de aceptación

---

## Dónde aparece en la serie

| Charla | Rol del concepto |
|---|---|
| 16 | Usado sin nombrarse — el spec de OpenSpec para RCA ya incluye escenarios dado/cuando/entonces |
| 22 | BDD se nombra de forma general, sin entrar en la sintaxis Gherkin |
| 23 | Se enseña la sintaxis completa (keywords, Scenario Outline) y su uso en fixes |
