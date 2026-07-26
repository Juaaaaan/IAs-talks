---
type: Concepto
title: "Agente de IA"
description: "Sistema de IA que razona sobre una pregunta, busca en su conocimiento y construye una respuesta adaptada, en lugar de seguir flujos conversacionales predefinidos"
tags: [agente, chatbot, razonamiento, copilot-studio, nivel-4]
related: [copilot-studio, rag, agentes-multiples, arnes-completo]
charla: "Charla 13"
estado: "✅ Publicado"
timestamp: "2026-07-22"
---

# Agente de IA

> _"La diferencia entre un chatbot y un agente es la misma que entre un contestador automático y una persona que realmente te escucha."_

---

## Qué es

Un agente de IA no sigue un guión. **Razona.** Cuando recibe una pregunta, entiende lo que se le pide, busca en su conocimiento y construye una respuesta adaptada a esa pregunta concreta — no busca el camino predefinido más parecido, como haría un chatbot clásico.

La consecuencia más importante de este comportamiento: **cuando un agente no sabe algo, lo dice.** No inventa una respuesta plausible ni redirige en bucle. Reconoce el límite de su conocimiento, y eso lo hace más fiable, no menos.

---

## Chatbot clásico vs agente

| Chatbot clásico | Agente |
|---|---|
| Sigue flujos predefinidos diseñados de antemano | Razona sobre la pregunta en el momento |
| Si la pregunta no encaja en un camino, el sistema se rompe | Si no tiene la información, lo reconoce explícitamente |
| Busca el camino más parecido y redirige | Construye una respuesta adaptada o admite el límite |
| Mala fama merecida (bucles, opciones que no encajan) | Comportamiento de confianza: no inventa |

---

## Por qué importa que un agente diga "no lo sé"

Puede parecer un fallo, pero es exactamente lo contrario: es el comportamiento correcto de un sistema en el que se puede confiar. Un agente que reconoce lo que no sabe es más valioso que uno que siempre responde algo — porque cuando sí responde, esa respuesta es fiable.

La solución operativa ante una laguna de conocimiento no es "arreglar" al agente, sino ampliar lo que sabe: añadir el documento correspondiente a su base de conocimiento.

---

## Relación con otras piezas

- **[[copilot-studio]]** — Plataforma donde se construyen agentes de este tipo dentro del ecosistema Microsoft
- **[[rag]]** — Mecanismo por el que el agente busca en su conocimiento antes de responder
- **[[agentes-multiples]]** — Cuando varios agentes de este tipo colaboran entre sí
- **[[arnes-completo]]** — Un agente bien construido es una pieza operativa del arnés completo

---

## Dónde aparece en la serie

| Charla | Rol del concepto |
| ------ | --------------- |
| 13 | Introducción de la distinción chatbot vs. agente + construcción en vivo de un "Agente de bienvenida" en Copilot Studio |
