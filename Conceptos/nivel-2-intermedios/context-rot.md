---
type: Concepto
title: "Context rot — Cuando el contexto se degrada"
description: "Pérdida de capacidad de un modelo para aprovechar su contexto cuando este crece o se llena de ruido, contradicciones o información obsoleta. Puede ocurrir antes de llenar la ventana."
tags: [context-rot, contexto, degradacion, agentes, fiabilidad]
related: [context-window-management, context-engineering, compactacion, subagentes, token]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Context rot

> _"Que quepa en la ventana no significa que le preste atención."_

---

## Qué es

El **context rot** es la **degradación del rendimiento** cuando el contexto se hace largo, ruidoso o difícil de navegar. No hace falta llegar al límite de la ventana para que aparezca.

---

## Síntomas

- Olvida o ignora una instrucción dada al principio
- Recupera una versión **antigua** de algo que ya se corrigió
- Repite intentos que ya habían fallado
- Mezcla temas de distintas partes de la conversación

Estos síntomas también pueden tener otras causas.

---

## Ejemplo práctico

En un chat de todo el día preparas un informe, preguntas por una fórmula y redactas un correo. Al volver al informe, arrastra datos de un borrador descartado.

---

## Qué hacer

1. **Conversación nueva** para un tema nuevo
2. Antes de cambiar, pide un **resumen de decisiones** y revísalo
3. Guarda lo importante en un **documento** y aporta la versión vigente
4. No pegues más de lo necesario

---

## Relación con otras piezas

- **[[context-window-management]]** — Cómo gestionar el espacio disponible
- **[[context-engineering]]** — Diseñar qué entra en el contexto
- **[[compactacion]]** — Resumir para seguir trabajando
- **[[subagentes]]** — Aislar subtareas en contextos separados

---

## Referencias

- [Thoughtworks — Context rot in AI agents](https://www.thoughtworks.com/insights/blog/generative-ai/what-is-context-rot)
- [Lost in the Middle (Liu et al., 2023)](https://arxiv.org/abs/2307.03172)
