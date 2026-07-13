---
type: Concepto
title: "Structured Output — Salida estructurada de la IA"
description: "Técnica para que la IA devuelva respuestas en formatos controlados y parseables: JSON, tablas, plantillas. Esencial para integrar la IA en flujos automatizados."
tags: [structured-output, json, formato, automatizacion, parsing, agentes]
related: [function-calling, context-engineering, temperature, okf]
estado: "✅ Publicado"
timestamp: "2026-07-09"
---

# Structured Output — Salida estructurada de la IA

> _"No basta con que la IA responda. Necesitas que responda en un formato que tu código pueda usar."_

---

## Qué es

**Structured Output** es la capacidad de hacer que un LLM devuelva respuestas en un formato concreto y predecible (JSON, YAML, tablas, XML) en lugar de texto libre.

Es esencial cuando la salida de la IA va a ser procesada por otro sistema, no leída directamente por un humano.

---

## Por qué importa

| Texto libre | Structured Output |
|---|---|
| "El usuario se llama Juan y tiene 30 años" | `{"nombre": "Juan", "edad": 30}` |
| Difícil de parsear | Parseable directamente |
| Formato impredecible | Formato garantizado |
| Solo para humanos | Para humanos Y máquinas |
| No encadena con otros sistemas | Se integra en pipelines |

---

## Cómo se consigue

### 1. Instrucción en el prompt
```
Responde ÚNICAMENTE con JSON válido con este schema:
{"nombre": string, "nivel": 1-5, "recomendacion": string}
```

### 2. JSON Mode (API)
Los proveedores ofrecen modos que garantizan JSON válido:
- OpenAI: `response_format: { type: "json_object" }`
- Anthropic: Tool use con schema definido

### 3. Schema enforcement
Definir un JSON Schema que el modelo DEBE seguir — el output se valida contra el schema.

---

## Ejemplo práctico

Generar un fichero OKF automáticamente:

```
Prompt: "Documenta la decisión de no usar dark mode en formato OKF"

Output (structured):
---
type: Decisión
title: "No implementar modo oscuro"
description: "El sistema de diseño Artisanal Ether usa tonos cálidos exclusivamente"
tags: [decision, ui, dark-mode, artisanal-ether]
related: [contexto-proyecto]
estado: "✅ Aprobada"
timestamp: "2026-07-09"
---
```

---

## Cuándo usar Structured Output

✅ **Necesario cuando:**
- La salida alimenta otro sistema (API, base de datos)
- Generas ficheros con formato definido (OKF, YAML configs)
- Encadenas múltiples llamadas al LLM (pipeline)
- Necesitas validar la respuesta programáticamente

❌ **No necesario cuando:**
- La respuesta es para lectura humana directa
- Quieres explicaciones o razonamiento libre
- El formato no importa

---

## Relación con otras piezas

- **[[function-calling]]** — Function calling produce structured output por diseño
- **[[context-engineering]]** — Definir el formato de salida es parte del diseño del contexto
- **[[temperature]]** — Temperature baja mejora la adherencia al formato
- **[[okf]]** — El frontmatter OKF es un structured output que los agentes generan

---

## Referencias

- [OpenAI Structured Outputs](https://platform.openai.com/docs/guides/structured-outputs)
- Concepto en glosario: [[glosario-ia-nivel-1]] §30
