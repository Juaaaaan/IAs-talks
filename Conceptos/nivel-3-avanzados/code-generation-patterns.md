---
type: Concepto
title: "Code Generation Patterns — Patrones de generación de código con IA"
description: "Patrones probados para generar código con IA de forma fiable: SDD, TDD con IA, pair programming, edit-test loops. No basta con pedir código — hay que saber cómo pedirlo."
tags: [code-generation, patrones, sdd, tdd, pair-programming, desarrollo]
related: [sdd, copilot-instructions, agentes-multiples, agentic-workflows, structured-output]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Code Generation Patterns — Patrones de generación de código con IA

> _"La IA puede escribir código. Pero el código bueno necesita un patrón bueno."_

---

## Qué es

Son las **estrategias probadas** para que la IA genere código de calidad de forma consistente. No es suficiente con pedir "haz un componente" — el resultado depende enormemente de cómo estructures la petición.

---

## Patrones principales

### 1. SDD — Specification-Driven Development
```
spec.md → task.md → código → tests
```
Primero defines QUÉ construir (spec), después el plan (task), y la IA implementa siguiendo ambos. Es el patrón central de esta serie.

### 2. TDD con IA
```
Test primero → implementación → verificación
```
Escribes (o pides) los tests antes del código. La IA implementa hasta que los tests pasan.

### 3. Pair Programming con IA
```
Humano guía → IA ejecuta → humano revisa → IA ajusta
```
Interacción continua donde el humano dirige y la IA implementa en ciclos cortos.

### 4. Edit-Test Loop
```
IA edita → ejecuta tests → si fallan → IA corrige → repite
```
Ciclo autónomo donde el agente se autocorrige basándose en resultados de tests.

### 5. Developer/Reviewer
```
Agente developer → genera código → agente reviewer → revisa
```
Dos agentes con roles distintos. El developer implementa, el reviewer valida.

---

## Qué patrón usar

| Situación | Patrón recomendado |
|---|---|
| Feature nueva compleja | SDD |
| Bugfix con tests existentes | Edit-Test Loop |
| Exploración / prototipo | Pair Programming |
| Feature con requisitos claros | TDD con IA |
| Código crítico | Developer/Reviewer |

---

## Anti-patrones

❌ **"Hazme una app"** — Demasiado vago, resultado impredecible
❌ **Generar sin tests** — Sin verificación, no sabes si funciona
❌ **No revisar el código** — La IA puede generar código que compila pero es incorrecto
❌ **Copiar sin entender** — Si no entiendes el código, no puedes mantenerlo

---

## Relación con otras piezas

- **[[sdd]]** — El patrón SDD es el enfoque principal de la serie
- **[[copilot-instructions]]** — Las instrucciones hacen que el código generado siga convenciones
- **[[agentes-multiples]]** — El patrón developer/reviewer
- **[[agentic-workflows]]** — Los edit-test loops son agentic workflows
- **[[structured-output]]** — El código generado debe seguir una estructura definida
