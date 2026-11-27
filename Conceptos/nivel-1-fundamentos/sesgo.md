---
type: Concepto
title: "Sesgo — Cuando la IA hereda y repite desequilibrios"
description: "Un sesgo es una inclinación sistemática en las respuestas o decisiones de un modelo que puede perjudicar a ciertos grupos o perspectivas. Puede venir de los datos, del diseño o de cómo se usa."
tags: [sesgo, bias, etica, fiabilidad, riesgo, fundamentos]
related: [alucinaciones, sycophancy, human-in-the-loop, ai-act, ai-governance]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Sesgo — Cuando la IA hereda desequilibrios

> _"La IA aprende del mundo tal como está escrito, no tal como debería ser."_

---

## Qué es

Un **sesgo** es una desviación **sistemática**: no un error suelto, sino una inclinación que se repite. En IA puede hacer que se trate peor a ciertos grupos o que una perspectiva aparezca como si fuera la única.

---

## De dónde puede venir

| Origen | Ejemplo |
|---|---|
| **Datos de entrenamiento** | Reflejan estereotipos o infrarrepresentan a parte de la población |
| **Ajuste del modelo** | Las preferencias de quienes lo evalúan influyen en cómo responde |
| **Planteamiento** | La pregunta ya sugiere la respuesta |
| **Uso** | Se aplica a personas o situaciones distintas de aquellas para las que se probó |

---

## Ejemplo práctico

Un sistema que ordena candidaturas y aprende de contrataciones pasadas puede reproducir las preferencias de esas contrataciones. Quitar la columna "sexo" no garantiza que desaparezca el problema: otros datos pueden actuar como pistas indirectas.

---

## Qué hacer

1. **Probar con casos comparables** cambiando solo la característica que no debería influir
2. **Revisar resultados por grupos**, no solo la media
3. **Pedir criterios explícitos** y revisarlos
4. **No delegar** decisiones sobre personas sin supervisión humana y sin revisar la normativa aplicable

---

## Relación con otras piezas

- **[[alucinaciones]]** — Otro límite de fiabilidad, pero distinto: inventar no es lo mismo que inclinarse
- **[[sycophancy]]** — La inclinación a darte la razón
- **[[human-in-the-loop]]** — Revisión humana en decisiones sensibles
- **[[ai-act]]** — La norma europea que regula usos de alto riesgo
- **[[ai-governance]]** — Controles de la organización
