---
type: Concepto
title: "Entrenamiento vs inferencia — Cuándo aprende la IA y cuándo responde"
description: "El entrenamiento es la fase en la que el modelo ajusta sus parámetros a partir de datos. La inferencia es el uso del modelo ya entrenado para responder. Escribirle un mensaje es inferencia."
tags: [entrenamiento, inferencia, modelos, datos, fundamentos]
related: [llm, machine-learning, fecha-de-corte, fine-tuning, privacidad-y-anonimizacion]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Entrenamiento vs inferencia — Cuándo aprende y cuándo responde

> _"Entrenar es estudiar la carrera. Inferir es contestar en el examen."_

---

## Qué es

| | Entrenamiento | Inferencia |
|---|---|---|
| **Qué pasa** | El modelo ajusta sus parámetros a partir de datos | El modelo ya entrenado genera una respuesta |
| **Cuándo** | Antes de que lo uses (y en nuevas versiones) | Cada vez que le pides algo |
| **Coste** | Muy alto y concentrado, en los modelos grandes | Menor por petición, pero se acumula con el uso |
| **¿Cambia el modelo?** | Sí | No, durante la propia respuesta |

---

## La confusión más habitual

> "Se lo he explicado en el chat, así que ya lo ha aprendido."

Lo que escribes entra en el **contexto** de esa conversación. El modelo lo usa para responder, pero sus parámetros no cambian en ese momento. Si más adelante "se acuerda", normalmente es porque la aplicación **guardó** la información y se la volvió a entregar (ver [[memory]]).

---

## Cuidado con la conclusión equivocada

Que el modelo no aprenda en directo **no significa** que tus datos no se guarden ni que nunca puedan usarse para entrenar versiones futuras. Eso lo deciden las condiciones del producto y el contrato de tu empresa. Comprueba la política antes de compartir información sensible (ver [[privacidad-y-anonimizacion]]).

---

## Relación con otras piezas

- **[[llm]]** — El resultado del entrenamiento
- **[[machine-learning]]** — El enfoque general de aprender a partir de datos
- **[[fecha-de-corte]]** — El límite de lo que el modelo pudo ver al entrenarse
- **[[fine-tuning]]** — Un entrenamiento adicional sobre un modelo existente
- **[[privacidad-y-anonimizacion]]** — Qué datos puedes compartir al usarlo
