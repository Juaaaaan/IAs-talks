---
type: Concepto
title: "System Prompt vs User Prompt — Las dos voces del contexto"
description: "Distinción fundamental entre las instrucciones del sistema (identidad, reglas, comportamiento) y el mensaje del usuario (la petición concreta). Comprender la diferencia es clave para context engineering."
tags: [system-prompt, user-prompt, contexto, instrucciones, roles]
related: [context-engineering, copilot-instructions, skills, chain-of-thought]
estado: "✅ Publicado"
timestamp: "2026-07-09"
---

# System Prompt vs User Prompt — Las dos voces del contexto

> _"El system prompt define QUIÉN es la IA. El user prompt define QUÉ le pides."_

---

## Qué es

Todo LLM recibe dos tipos de instrucciones con roles diferentes:

- **System Prompt:** Define la identidad, reglas, comportamiento y contexto persistente del modelo. Es "invisible" para el usuario final.
- **User Prompt:** Es la petición concreta del usuario en cada interacción.

---

## La analogía

| System Prompt | User Prompt |
|---|---|
| El manual del empleado | La tarea del día |
| "Eres un developer Angular senior que sigue estas convenciones..." | "Implementa el componente navbar" |
| Se define una vez | Cambia en cada interacción |
| Define quién eres | Define qué haces ahora |

---

## Ejemplo real

```
SYSTEM:
Eres un asistente de desarrollo del proyecto RCA.
Stack: Angular 21, signals, Supabase.
No uses NgRx. Sigue el sistema de diseño Artisanal Ether.
Responde en español.

USER:
Crea un componente de tarjeta de producto con imagen,
nombre y precio.
```

---

## Dónde vive cada uno

| Tipo | Dónde se configura |
|---|---|
| System prompt | `copilot-instructions.md`, `CLAUDE.md`, skills, settings |
| User prompt | Lo que escribes en el chat/editor |

---

## Jerarquía de prioridad

```
System prompt (más autoridad)
    ↓
Instrucciones persistentes (.github/, .claude/)
    ↓
Documentos inyectados (RAG)
    ↓
Historial de conversación
    ↓
User prompt (menos autoridad pero más reciente)
```

> **Nota:** En la práctica, los modelos pueden dar más peso al user prompt si contradice al system — esto es un vector de ataque (prompt injection).

---

## Por qué importa

Entender esta separación es la base de:
- **copilot-instructions.md** → es system prompt persistente
- **CLAUDE.md** → es system prompt a nivel de proyecto
- **Skills** → inyectan system prompt condicional
- **Prompt injection** → ataques que intentan que el user prompt sobreescriba el system

---

## Relación con otras piezas

- **[[copilot-instructions]]** — Son system prompt persistente que vive en el repo
- **[[context-engineering]]** — El system prompt es la primera capa del contexto
- **[[skills]]** — Los skills inyectan instrucciones a nivel de system
- **[[chain-of-thought]]** — Se puede forzar CoT desde el system prompt

---

## Referencias

- [OpenAI System Message docs](https://platform.openai.com/docs/guides/text-generation)
- [Anthropic System Prompts](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching#system-prompts)
