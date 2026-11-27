---
type: Concepto
title: "Few-shot — Enseñar con ejemplos dentro de la petición"
description: "Técnica que consiste en incluir en la petición unos pocos ejemplos de lo que esperas para que el modelo siga el mismo patrón. Zero-shot es pedirlo sin ejemplos."
tags: [few-shot, zero-shot, prompting, ejemplos, tecnica]
related: [prediccion-siguiente-token, chain-of-thought, structured-output, context-engineering, fine-tuning]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Few-shot — Enseñar con ejemplos

> _"Un buen ejemplo ahorra tres párrafos de explicación."_

---

## Qué es

| Técnica | En qué consiste |
|---|---|
| **Zero-shot** | Pides la tarea sin ejemplos |
| **One-shot** | Das un ejemplo |
| **Few-shot** | Das varios ejemplos |

El modelo **no se reentrena**: usa los ejemplos como contexto solo para esa petición.

---

## Ejemplo práctico

```
Clasifica cada mensaje como CONSULTA, RECLAMACIÓN o GESTIÓN.

"¿Mi póliza cubre daños por agua?" → CONSULTA
"Llevo tres semanas sin respuesta" → RECLAMACIÓN
"Quiero cambiar mi cuenta de cobro" → GESTIÓN

"Me habéis cobrado dos veces el recibo" →
```

---

## Cómo hacerlo bien

1. Ejemplos **representativos**, también de los casos dudosos
2. **Variados**: si todos se parecen, copiará rasgos que no querías
3. **Mismo formato** que la salida que esperas
4. **Sin datos reales de clientes**: usa ejemplos ficticios

---

## Relación con otras piezas

- **[[prediccion-siguiente-token]]** — Los ejemplos dejan claro el patrón a completar
- **[[structured-output]]** — Los ejemplos ayudan a fijar el formato
- **[[chain-of-thought]]** — Otra técnica para mejorar la respuesta
- **[[fine-tuning]]** — La alternativa que sí modifica el modelo

---

## Referencias

- [Language Models are Few-Shot Learners (Brown et al., 2020)](https://arxiv.org/abs/2005.14165)
