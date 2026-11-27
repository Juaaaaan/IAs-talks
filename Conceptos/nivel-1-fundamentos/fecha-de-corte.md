---
type: Concepto
title: "Fecha de corte del conocimiento — Hasta dónde llega lo que sabe el modelo"
description: "Es el momento a partir del cual un modelo no tiene información de su entrenamiento. Lo posterior solo lo conoce si se lo das o si puede buscarlo."
tags: [fecha-de-corte, knowledge-cutoff, actualidad, limites, fundamentos]
related: [entrenamiento-vs-inferencia, alucinaciones, rag, grounding, deep-research]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Fecha de corte del conocimiento

> _"El modelo es como quien vuelve de meses sin noticias: sabe mucho, pero no lo último."_

---

## Qué es

La **fecha de corte** (*knowledge cutoff*) es el límite temporal de la información usada para entrenar un modelo. De lo que ocurrió después no sabe nada **por entrenamiento**.

---

## Por qué importa

- Puede darte como vigente algo que **ya ha cambiado**: una norma, un precio, un cargo, una versión de software
- No siempre avisa de que su información puede estar desfasada
- De los meses cercanos al corte suele haber menos información
- Un asistente con **búsqueda web** o acceso a documentos puede ir más allá, pero solo con lo que realmente consulte

---

## Ejemplo práctico

Preguntas: *"¿Cuándo se aplican las obligaciones de alto riesgo del AI Act?"*. Un modelo entrenado antes de la modificación de julio de 2026 puede responder con las fechas antiguas, y sonar totalmente seguro (ver [[ai-act]]).

---

## Cómo protegerte

1. En temas que cambian, **pide que busque** y que cite la fuente
2. **Abre la fuente** y mira su fecha
3. **Dale tú el documento vigente** cuando lo tengas
4. No des por hecho que el modelo sabe qué día es hoy

---

## Relación con otras piezas

- **[[entrenamiento-vs-inferencia]]** — Por qué existe un corte
- **[[alucinaciones]]** — El riesgo de rellenar lo que no sabe
- **[[grounding]]** — Apoyar la respuesta en fuentes
- **[[rag]]** — Aportar documentos actualizados en el momento
- **[[deep-research]]** — Búsqueda e informe a partir de múltiples fuentes
