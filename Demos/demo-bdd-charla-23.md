---
type: Demo
title: "Demo — BDD con Gherkin sobre el carrito de RCA (Charla 23)"
description: "Paso a paso de la demo de Charla 23: implementar y verificar el escenario Gherkin 'Añadir una pieza al carrito' sobre RCA, pre-construida para no depender de que el modelo clasifique bien la petición en directo. Hallazgo colateral: la carpeta odd/tasks/ aparece sola, confirmando que ODD y BDD están anidados."
tags: [demo, bdd, gherkin, odd, rca, verificacion]
related: [charla-23-comprobar-antes-de-construir, bdd, odd, gherkin]
charla: "Charla 23"
estado: "✅ Ejecutada"
timestamp: "2026-10-14"
---

# Demo — BDD con Gherkin sobre el carrito de RCA (Charla 23)

**Charla:** [[charla-23-comprobar-antes-de-construir]]
**Herramienta:** Copilot (vía GitLab corporativo, copia de RCA por permisos) / agente de código
**Proyecto:** Resin Craft Art (RCA) — carrito de compra
**Duración:** 10 min

---

## Objetivo de la demo

Mostrar que, cuando el criterio de éxito se escribe antes como un escenario Gherkin, implementar y verificar deja de ser una negociación posterior: se contrasta el resultado contra el mismo escenario, con evidencia observable para cada `Then`.

---

## Decisión de última hora (importante)

Tras probar el protocolo ODD con Copilot sobre RCA el día antes, se decidió montar la demo **con todo ya creado**, no generando en directo, para no depender de que el modelo clasificara bien la petición delante de la sala. La tesis de la charla no puede depender de un acierto de clasificación en vivo.

---

## Preparación previa

- RCA copiado a un GitLab corporativo (el repo personal de Juan es en GitHub; demo por temas de permisos)
- El escenario y su implementación ya construidos de antemano, verificados en un ensayo
- Escenario Gherkin visible y listo para mostrar en pantalla

---

## Paso a paso

### Paso 1 — Mostrar el escenario ya escrito (2 min)

```gherkin
Feature: Carrito de compra
  Scenario: Añadir una pieza al carrito
    Given que estoy viendo la ficha de un anillo de resina
    And el carrito está vacío
    When pulso "Añadir al carrito"
    Then el carrito muestra 1 artículo
    And el precio del anillo se suma al total
```

No redactarlo en vivo — mostrarlo ya escrito y leerlo en voz alta. Redactarlo en directo añade riesgo sin reforzar la tesis.

### Paso 2 — Mostrar la implementación y la verificación (6 min)

Mostrar, ya ejecutada, la verificación del comportamiento implementado contra el escenario — evidencia observable para cada `Then` (el carrito muestra 1 artículo, el precio se suma).

**Pausa deliberada (el momento pedagógico central):**

> _"Fijaos en lo que NO ha ocurrido. No hemos discutido si nos gusta. No hemos discutido si 'parece que funciona'. El criterio estaba escrito antes de empezar y, al terminar, lo hemos contrastado con ese mismo criterio."_

### Paso 3 — El hallazgo colateral: ODD y BDD anidados (2 min)

Mostrar que, al implementar el escenario Gherkin, el agente generó automáticamente una carpeta `odd/tasks/` con el documento de la tarea — sin que nadie lo pidiera. Usar esto como confirmación en vivo (sin necesitar una demo ODD separada) de que ODD y BDD no son alternativas que compiten: están anidados.

---

## Lecciones aprendidas

- Preparar la demo "ya creada" en vez de generar en directo reduce el riesgo sin perder fuerza narrativa — el público valora ver la evidencia (el `Then` cumplido, el documento de tarea), no el proceso de generación en sí.
- El patrón "ODD y BDD anidados, no alternativos" se puede mostrar con evidencia real (la carpeta `odd/tasks/` generada como efecto colateral de una demo BDD) sin necesitar una demo ODD separada.
- Para cambios de verificación (no solo features nuevas), el mismo patrón de escenario Gherkin aplica igual o mejor: describe el comportamiento que hoy falla y que no debe volver a romperse.

---

## Checklist pre-demo

- [ ] Implementación y verificación ya ejecutadas y confirmadas estables en un ensayo previo
- [ ] Escenario Gherkin visible, legible, sin necesidad de redactarlo en vivo
- [ ] Carpeta `odd/tasks/` generada verificada antes de la sesión (para no depender de que reaparezca en directo)
- [ ] RCA copiado y accesible en el GitLab corporativo
