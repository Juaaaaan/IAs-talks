---
type: Concepto
title: "Jailbreak — Intentar saltarse las protecciones del modelo"
description: "Intento de conseguir que un modelo haga algo que sus protecciones deberían impedir. Está relacionado con la prompt injection, pero no es exactamente lo mismo."
tags: [jailbreak, seguridad, ataques, protecciones, red-team]
related: [prompt-injection, guardrails, constitutional-ai, rlhf, trifecta-letal]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Jailbreak

> _"El jailbreak discute con las protecciones del modelo. La injection se cuela entre los datos."_

---

## Qué es

Un **jailbreak** es un intento de que un modelo **ignore sus protecciones de seguridad** y produzca algo que debería rechazar. Suele recurrir a reformulaciones, juegos de rol o contextos ficticios.

---

## Jailbreak vs prompt injection

Los términos se mezclan a menudo. Una distinción útil, defendida por Simon Willison, es esta:

| | Jailbreak | Prompt injection |
|---|---|---|
| **Objetivo** | Las protecciones del propio modelo | Una aplicación que mezcla instrucciones de confianza con contenido que no lo es |
| **Quién puede escribir el ataque** | Normalmente quien está usando el modelo | Puede ser un tercero, a través de un correo, una web o un documento |
| **Quién puede salir perjudicado** | Quien ofrece el modelo, y terceros si el contenido dañino se usa | A menudo el usuario legítimo de la aplicación y sus datos |

---

## Por qué importa

- Ninguna protección basada solo en el modelo debe darse por infalible
- Lo que el sistema **puede hacer** importa tanto como lo que puede decir
- Probar los propios sistemas (*red teaming*) debe hacerse **con autorización** y un alcance definido

---

## Cómo reducir el riesgo

1. Varias capas de [[guardrails]]
2. Mínimo privilegio en herramientas y datos
3. Registro y seguimiento de usos anómalos
4. Revisión humana en acciones sensibles

---

## Relación con otras piezas

- **[[prompt-injection]]** — El ataque relacionado, con más detalle sobre defensas
- **[[guardrails]]** — Las capas de protección
- **[[constitutional-ai]]** y **[[rlhf]]** — Técnicas de alineamiento del modelo
- **[[trifecta-letal]]** — Cuándo una injection puede acabar en fuga de datos

---

## Referencias

- [Simon Willison — Charla sobre la trifecta letal y la diferencia entre ambos ataques](https://simonwillison.net/2025/Aug/9/bay-area-ai/)
