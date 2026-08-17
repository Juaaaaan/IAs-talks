---
type: Concepto
title: "Alucinaciones — Cuándo la IA se lo inventa (con buena letra)"
description: "Una alucinación es una respuesta de la IA que suena convincente pero es falsa. No es un fallo raro: es consecuencia de cómo funciona un LLM, que predice el texto más probable en vez de consultar una verdad. La clave práctica no es desconfiar de todo, sino calibrar la verificación según lo que cuesta el error."
tags: [alucinaciones, verificacion, fiabilidad, limites, riesgo, fundamentos]
related: [reasoning-models, rag, wiki-llm, eval-benchmarking]
estado: "✅ Publicado"
timestamp: "2026-08-17"
---

# Alucinaciones — Cuándo la IA se lo inventa (con buena letra)

> _"La IA no se equivoca tartamudeando. Se equivoca con redacción impecable y tono de experta. Lo segura que suena no dice nada de si es verdad."_

---

## Qué es

Una **alucinación** es una respuesta de la IA que parece correcta y bien fundamentada, pero es **falsa**: un dato inventado, una cita que no existe, una cifra que se sacó de la manga. El problema no es solo el error — es que viene envuelto en un lenguaje seguro y profesional que baja la guardia.

---

## Por qué pasa

Un LLM no "sabe" cosas ni consulta una base de datos de verdades. **Predice el texto más probable** dada tu pregunta. Cuando no tiene la información, no dice "no lo sé": completa el hueco con lo que *parece* que iría ahí. Por eso puede sonar seguro y estar equivocado a la vez.

> Predecir ≠ saber. Esa es la raíz de la alucinación.

---

## Dónde alucina más (zonas rojas)

| Zona roja | Ejemplo |
|---|---|
| **Cifras y datos exactos** | Estadísticas, porcentajes, importes |
| **Fechas y nombres propios** | Quién dijo qué, cuándo pasó algo |
| **Citas, referencias, normativa** | "Según el artículo X" / "el estudio de tal" |
| **Lo muy reciente o de nicho** | Cuanto más específico y menos común, más inventa |

---

## Cómo protegerte (sin volverte paranoico)

La clave es **calibrar según el coste del error**, no desconfiar de todo:

| Coste del error | Cuánto verificas |
|---|---|
| **Bajo** (borrador, ideas) | Lectura rápida |
| **Medio** (acta, resumen que reenvías) | Contrastas datos clave contra la fuente |
| **Alto** (cifra a cliente, dato legal) | Verificación total + revisión humana |

**Técnicas prácticas:**
1. **Pedir la fuente:** *"cita la frase exacta"*. Si no puede, desconfía.
2. **Darle el contexto tú:** una IA atada a tu documento (ver [[rag]] / [[wiki-llm]]) inventa mucho menos que una respondiendo de memoria.
3. **Contrastar lo crítico** contra el original.
4. **Saber cuándo un humano revisa sí o sí:** cliente, consecuencia legal o económica, dirección.

---

## Por qué importa

- **Confianza:** el error peligroso no es el obvio, es el sutil que copiarías sin pestañear.
- **Uso responsable:** conecta con gobernanza y seguridad — el humano sigue siendo responsable de lo que firma.
- **Productividad real:** saber cuándo fiarte y cuándo no es lo que separa a un usuario ingenuo de uno con criterio.

---

## Relación con otras piezas

- **[[reasoning-models]]** — Los modelos que "piensan" reducen (no eliminan) las alucinaciones en tareas complejas
- **[[rag]]** — Darle a la IA una fuente concreta es el antídoto más eficaz
- **[[wiki-llm]]** — La versión organizacional del mismo antídoto: responder sobre tus documentos, no sobre el mundo entero
- **[[eval-benchmarking]]** — Medir la tasa de alucinación es parte de evaluar si un modelo sirve

---

## Referencias

- [Wikipedia — Hallucination (artificial intelligence)](https://en.wikipedia.org/wiki/Hallucination_(artificial_intelligence))
