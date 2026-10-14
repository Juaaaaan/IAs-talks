---
type: Concepto
title: "Tier — Nivel abstracto de capacidad del modelo"
description: "Nivel abstracto de capacidad, desde opciones económicas hasta frontier, que AI SDLC Foundation usa para hablar de potencia de modelo sin casarse con un proveedor ni con un nombre concreto."
tags: [ai-sdlc-foundation, tier, capacidad, routing, provider, abstraccion]
related: [ai-sdlc-foundation, model-policy, provider, station, model-routing]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Tier — Nivel abstracto de capacidad del modelo

> _"Primero decides el nivel de potencia que necesitas; después ya mapearás qué modelo concreto lo cumple hoy."_

---

## Qué es

En AI SDLC Foundation, **Tier** es un nivel abstracto de capacidad que ordena opciones desde las más económicas hasta las frontier sin nombrar modelos concretos. Sirve para hablar de potencia, profundidad de razonamiento y coste esperado con una capa de abstracción portable. Así, Foundation puede gobernar decisiones de capacidad sin atarse a una marca específica ni a un catálogo que cambiará con el tiempo.

---

## Papel en AI SDLC Foundation

Tier es la pieza que permite que una [[model-policy]] y una [[station]] hablen el mismo idioma sobre capacidad requerida. Un workflow puede declarar que cierta tarea necesita un tier económico para formato o uno frontier para razonamiento profundo, y dejar para después el mapping real sobre cada provider. Esto encaja con la visión general de [[model-routing]], pero aterrizado al vocabulario operativo de Foundation.

---

## Cómo funciona

El sistema define varios niveles abstractos y luego otra capa decide qué modelo concreto satisface cada uno según disponibilidad, coste o rendimiento observado. Durante la ejecución, workflows y políticas referencian tiers, no nombres de catálogo cerrados. La frontera esencial es que tier no es un modelo ni un provider: es una abstracción estable que permite cambiar asignaciones sin reescribir todo el sistema.

---

## Ejemplos prácticos

### Ejemplo 1 — Tier económico para formato

Una estación dedicada a limpiar JSON, clasificar etiquetas sencillas o normalizar documentos puede pedir un tier económico. La tarea necesita consistencia, pero no la máxima profundidad de razonamiento.

### Ejemplo 2 — Tier frontier para razonamiento profundo

Otra etapa evalúa trade-offs arquitectónicos, dependencias cruzadas y riesgos de integración, por lo que la policy le asigna un tier frontier. El workflow sigue hablando en términos abstractos aunque el modelo concreto cambie más adelante.

---

## Matices y confusiones habituales

- **Cuidado:** Tier no es un modelo concreto; es una categoría de capacidad que puede mapearse a distintos modelos con el tiempo.
- **Cuidado:** Tier tampoco es el provider; la misma plataforma puede ofrecer varias opciones que cubran tiers diferentes.
- **Importante:** Si los tiers se definen con demasiada vaguedad, la model policy pierde precisión y el routing se vuelve inestable.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Sitúa los tiers dentro de la gobernanza de capacidad del sistema.
- **[[model-policy]]** — Selecciona el tier apropiado para cada tipo de tarea.
- **[[provider]]** — Puede mapear distintos modelos concretos a los tiers definidos por Foundation.
- **[[station]]** — Ejecuta tareas cuyo nivel de capacidad puede declararse mediante tiers.
- **[[model-routing]]** — Conecta esta abstracción con la conversación general sobre routing entre modelos.
