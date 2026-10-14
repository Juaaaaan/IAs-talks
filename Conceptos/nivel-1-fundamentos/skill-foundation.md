---
type: Concepto
title: "Skill — Paquete reutilizable de conocimiento experto"
description: "Paquete reutilizable que aporta conocimiento de dominio a un agente dentro de AI SDLC Foundation. Encapsula criterio y guías de trabajo, pero no es un agente ni una herramienta por sí mismo."
tags: [ai-sdlc-foundation, skill, conocimiento, reusable, pack, agent]
related: [ai-sdlc-foundation, agent, knowledge, pack, skills]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Skill — Paquete reutilizable de conocimiento experto

> _"La skill no hace el trabajo sola: enseña al agente cómo hacerlo mejor."_

---

## Qué es

En AI SDLC Foundation, **Skill** es un paquete reusable de conocimiento experto que se adjunta a un agente para mejorar cómo aborda una tarea. Puede reunir instrucciones, criterios, ejemplos, referencias y límites de alcance sobre un dominio concreto. Su esencia no es ejecutar, sino transferir criterio operativo de forma empaquetada.

---

## Papel en AI SDLC Foundation

Skill sirve para que un [[agent]] no tenga que empezar desde cero cada vez que entra en un problema especializado. Toma material de [[knowledge]], se empaqueta con alcance claro y puede distribuirse como parte de un [[pack]]. En Foundation es una unidad reusable de comportamiento experto, conectada con la nota general [[skills]] pero acotada a este vocabulario del sistema.

---

## Cómo funciona

Una skill se registra como activo disponible y el runtime la pone al alcance del agente cuando corresponde. Al activarse, inyecta contexto experto: qué revisar primero, qué errores evitar, qué evidencia pedir o qué formato respetar. Su frontera es importante: no reemplaza a la herramienta que ejecuta acciones ni al agente que toma decisiones, sino que guía a ambos desde el conocimiento empaquetado.

---

## Ejemplos prácticos

### Ejemplo 1 — Skill de revisión de seguridad

El equipo define una skill que recuerda controles de secretos, permisos, exfiltración de datos y señales de riesgo. Cuando un agente revisa una integración sensible, activa ese paquete y trabaja con un checklist experto ya preparado.

### Ejemplo 2 — Skill de redacción de ADR

Otra skill enseña a redactar ADR con tono técnico, estructura mínima y criterios de decisión comparada. El agente la usa al producir documentación para mantener consistencia entre decisiones arquitectónicas.

---

## Matices y confusiones habituales

- **Cuidado:** Una skill no es un agente. El agente ejecuta el trabajo; la skill le aporta criterio especializado.
- **Cuidado:** Una skill no es una herramienta. Puede recomendar cuándo usar una herramienta, pero no la sustituye ni la implementa.
- **Importante:** Si el alcance de la skill es ambiguo, el agente puede aplicarla fuera de contexto y convertir una ayuda en ruido.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Sitúa la skill dentro del mapa completo del sistema.
- **[[agent]]** — Es quien consume la skill para trabajar con más conocimiento experto.
- **[[knowledge]]** — Alimenta el contenido reusable que la skill empaqueta.
- **[[pack]]** — Puede ser el contenedor de distribución de varias skills relacionadas.
- **[[skills]]** — Enlaza con la explicación general del concepto fuera del alcance específico de Foundation.
