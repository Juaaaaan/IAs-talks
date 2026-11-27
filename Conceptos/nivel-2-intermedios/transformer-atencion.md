---
type: Concepto
title: "Transformer y atención — La arquitectura detrás de los LLM"
description: "El transformer es una arquitectura de red neuronal presentada en 2017. Su mecanismo de atención permite que cada parte del texto tenga en cuenta otras partes relevantes. Es la base de los LLM más conocidos."
tags: [transformer, atencion, attention, arquitectura, llm]
related: [llm, machine-learning, token, mixture-of-experts, modelos-difusion]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Transformer y atención

> _"Para entender una palabra, mira a las que la rodean y decide cuáles pesan más."_

---

## Qué es

El **transformer** es una arquitectura presentada en 2017 en el artículo *Attention Is All You Need*. Se apoya en el mecanismo de **atención**. La **T** de GPT viene de *Transformer*.

---

## La atención, con un ejemplo

> "El perito revisó el informe con el cliente porque **él** tenía dudas."

Para interpretar "él" hay que relacionarlo con otras palabras de la frase. La atención calcula **cuánto debe influir** cada parte en la representación de las demás. Aquí, además, la frase es ambigua: ni una persona podría estar segura.

"Atención" es el nombre de una operación matemática, no atención consciente.

---

## Por qué fue importante

- Permite procesar en **paralelo** buena parte del entrenamiento, frente a arquitecturas anteriores que avanzaban paso a paso
- Facilita relacionar elementos **alejados** de una secuencia
- Se ha usado también con imagen y audio

## Un coste

Con las formas habituales de atención, alargar el contexto aumenta mucho el cálculo. Hay numerosas variantes para hacerlo más eficiente.

---

## Relación con otras piezas

- **[[llm]]** — El uso más conocido
- **[[token]]** — Los elementos que se relacionan entre sí
- **[[machine-learning]]** — El marco general de las redes neuronales
- **[[mixture-of-experts]]** — Una técnica que se combina con transformers
- **[[modelos-difusion]]** — Otra familia de técnicas generativas, que puede usar transformers

---

## Referencias

- [Attention Is All You Need (Vaswani et al., 2017)](https://arxiv.org/abs/1706.03762)
