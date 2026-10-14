---
type: Charla
title: "Charla 15 — Seguridad en IA: cuando el dato y la instrucción se confunden"
description: "Por qué dato e instrucción viajan por el mismo canal en un LLM y qué hace eso posible: prompt injection directa e indirecta, exfiltración vía Markdown, el marco OWASP Top 10 para LLM, las 6 capas de defensa, y nueve brechas reales documentadas (EchoLeak, Slack AI, Samsung, Bing Chat, Chevrolet, Cursor, GitHub Copilot, OpenAI/Hugging Face)."
tags: [charla, seguridad, prompt-injection, owasp, mcp, cadena-de-suministro]
related: [MATERIAL-CHARLA-15-SEGURIDAD, guion-charla-15, prompt-injection, mcp-ecosystem, constitutional-ai, ai-governance]
charla: "Charla 15"
fecha: "2026-08-05"
estado: "✅ Impartida"
timestamp: "2026-08-05"
---

# Charla 15 — Seguridad en IA: cuando el dato y la instrucción se confunden

**Estado:** ✅ Impartida

---

## Idea central

> _"En seguridad tradicional preguntas '¿quién tiene permiso para ejecutar esto?'. En seguridad de IA preguntas '¿quién tiene permiso para hablarle a esto?' — y la respuesta, muchas veces, es: cualquiera que le mande un email."_

En un LLM, instrucciones del sistema, preguntas del usuario y contenido externo entran por el mismo canal, como texto plano. No hay separación nativa entre "orden a seguir" y "dato a procesar" — es la raíz estructural de todo lo que cubre la charla.

## Hilo narrativo

Conecta con la Charla 14 (gobernanza, shadow AI) bajando un nivel: ya no es "¿puedo usar esta herramienta?", sino "¿puede alguien manipular la herramienta que ya uso?".

## Estructura

| Bloque | Contenido |
|---|---|
| Prompt injection | Directa vs indirecta; técnica de exfiltración vía Markdown; marco OWASP Top 10 para LLM (2025→2026) |
| 6 capas de defensa | Sanitización, separación de contexto, mínimo privilegio, validación de salida, humano en el bucle, guardrails |
| Casos reales (categoría A — fuga por diseño) | EchoLeak/Copilot (zero-click, CVE-2025-32711), Slack AI (exfiltración vía Markdown), Samsung/ChatGPT |
| Casos reales (categoría B — manipulación conversacional) | Bing Chat/Sydney, Chevrolet de Watsonville (el coche de 1$), ChatGPT y la clave de Windows |
| Casos reales (categoría C — autonomía sin control) | Cursor/CurXecute (RCE vía MCP), GitHub Copilot \"modo YOLO\", OpenAI/Hugging Face (escape de sandbox) |
| Cadena de suministro | MCP como superficie de ataque; modelos maliciosos en Hugging Face (pickle vs Safetensors) |
| Alineamiento | RLHF vs Constitutional AI |

Sin demo en vivo — charla de concienciación y marco de referencia.

## Conceptos que introduce

- [[prompt-injection]] — directa, indirecta, exfiltración vía Markdown, OWASP Top 10 para LLM
- [[mcp-ecosystem]] — ampliado: MCP como superficie de ataque, cadena de suministro de modelos
- [[constitutional-ai]] — RLHF vs Constitutional AI, qué hay detrás de un "no puedo ayudarte con eso"

## Material asociado

- [[MATERIAL-CHARLA-15-SEGURIDAD]] — las nueve brechas documentadas en profundidad, con fuentes, y el procedimiento de reporte de incidentes

## Frases clave

> _"Cargar una imagen es un comportamiento automático de cualquier cliente de chat o navegador."_ (sobre exfiltración vía Markdown)

> _"El coste de decirlo pronto siempre es menor que el coste de que se descubra tarde."_

---

## Retrospectiva

_(pendiente de completar)_
