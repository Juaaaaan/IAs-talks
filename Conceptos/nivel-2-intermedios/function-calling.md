---
type: Concepto
title: "Function Calling / Tool Use — La IA que actúa"
description: "Mecanismo que permite a un LLM invocar funciones externas (APIs, bases de datos, herramientas) de forma estructurada. Es la base técnica de los MCPs y los agentes."
tags: [function-calling, tool-use, herramientas, agentes, mcp, api]
related: [mcp, skills, arnes-completo, agentes-multiples]
estado: "✅ Publicado"
timestamp: "2026-07-09"
---

# Function Calling / Tool Use — La IA que actúa

> _"Un chatbot contesta. Un agente trabaja. Function calling es lo que hace posible la diferencia."_

---

## Qué es

**Function Calling** (o Tool Use) es el mecanismo que permite a un LLM decidir cuándo necesita invocar una herramienta externa y generar los parámetros correctos para hacerlo.

En lugar de solo generar texto, el modelo puede:
- Leer un fichero
- Consultar una API
- Crear un issue en Jira
- Ejecutar una query SQL
- Editar código

---

## Cómo funciona

```
1. El modelo recibe una lista de herramientas disponibles (schema)
2. El usuario hace una petición
3. El modelo decide SI necesita una herramienta y CUÁL
4. Genera los parámetros en formato estructurado (JSON)
5. El sistema ejecuta la herramienta
6. El resultado vuelve al modelo
7. El modelo genera la respuesta final
```

---

## Ejemplo

```json
// El modelo decide llamar a la herramienta "create_jira_issue"
{
  "tool": "create_jira_issue",
  "parameters": {
    "project": "RCA",
    "type": "Task",
    "title": "Implementar navbar responsive",
    "description": "..."
  }
}
```

---

## Function Calling vs MCP

| Function Calling | MCP |
|---|---|
| Mecanismo genérico del modelo | Protocolo estándar de integración |
| Cada proveedor lo implementa diferente | Una interfaz universal |
| Definición ad-hoc de herramientas | Servidores que exponen herramientas |
| La base | La estandarización |

**MCP usa function calling por debajo**, pero añade un protocolo estándar para que cualquier herramienta se conecte a cualquier modelo.

---

## Por qué importa

Sin function calling, un LLM solo puede generar texto. Con function calling, puede:
- **Leer** información actualizada (no depende del entrenamiento)
- **Escribir** en sistemas reales (crea issues, edita código)
- **Verificar** su propio trabajo (ejecuta tests, comprueba resultados)
- **Orquestar** flujos complejos (encadena varias herramientas)

---

## Relación con otras piezas

- **[[mcp]]** — MCP estandariza el function calling en un protocolo universal
- **[[skills]]** — Los skills definen qué herramientas usar y cuándo
- **[[arnes-completo]]** — El arnés de integración se construye sobre function calling
- **[[agentes-multiples]]** — Los agentes usan function calling para ejecutar acciones

---

## Referencias

- [OpenAI Function Calling docs](https://platform.openai.com/docs/guides/function-calling)
- [Anthropic Tool Use docs](https://docs.anthropic.com/en/docs/build-with-claude/tool-use)
- Concepto en glosario: [[glosario-ia-nivel-1]] §18
