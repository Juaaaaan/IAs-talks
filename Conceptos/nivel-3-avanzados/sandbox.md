---
type: Concepto
title: "Sandbox — Un recinto controlado para que actúe el agente"
description: "Entorno aislado que limita a qué ficheros, redes y sistemas puede acceder un agente, para acotar el daño si se equivoca o le manipulan."
tags: [sandbox, aislamiento, seguridad, permisos, agentes]
related: [guardrails, trifecta-letal, prompt-injection, autonomous-coding-agents, computer-use]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Sandbox

> _"No hace falta suponer que el agente no fallará. Hay que limitar lo que puede romper."_

---

## Qué es

Un **sandbox** es un **entorno aislado** donde el agente puede leer, escribir o ejecutar dentro de unos límites impuestos por el sistema, no por la buena conducta del modelo.

---

## Qué se puede limitar

| Ámbito | Pregunta clave |
|---|---|
| **Ficheros** | ¿Qué carpetas puede leer y modificar? |
| **Red** | ¿A qué destinos puede conectarse? |
| **Credenciales** | ¿A qué claves tiene acceso? |
| **Comandos** | ¿Qué puede ejecutar? |
| **Recursos** | ¿Cuánto tiempo, memoria o gasto? |

---

## Ejemplo práctico

Un agente de código trabaja sobre una **copia** del proyecto, sin credenciales de producción y con la red restringida a lo necesario.

---

## Lo que un sandbox no hace

- No asegura que el resultado sea **correcto**
- No protege lo que **sí** está dentro de sus permisos
- Una configuración demasiado abierta lo deja en poco más que un nombre
- No elimina la [[prompt-injection]]: **reduce su alcance**

---

## Relación con otras piezas

- **[[guardrails]]** — Una capa más de control
- **[[trifecta-letal]]** — Cortar la red ayuda a romper la vía de salida
- **[[autonomous-coding-agents]]** — A más autonomía, más importa el aislamiento
- **[[computer-use]]** — Agentes que operan interfaces
