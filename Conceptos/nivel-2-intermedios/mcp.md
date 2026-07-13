---
type: Concepto
title: "MCP — Model Context Protocol"
description: "Protocolo estándar abierto que permite a la IA conectarse a herramientas externas como Jira, GitHub, Notion con permisos controlados"
tags: [mcp, protocolo, integracion, jira, github, arnes, atlassian]
related: [arnes-completo, sdd, skills, copilot-instructions, function-calling]
charla: "Charla 7"
nivel: 2
estado: "✅ Publicado"
timestamp: "2026-06-17"
---

# MCP — Model Context Protocol

> _"Un MCP es un enchufe estándar entre la IA y el mundo real. Vosotros controláis qué enchufáis."_

---

## Qué es

MCP es un protocolo abierto que permite a modelos de IA como Claude conectarse a herramientas externas — Jira, GitHub, Google Drive, Notion — de forma estandarizada, con los mismos permisos y el mismo control.

Lo creó Anthropic y lo donaron como **estándar abierto en diciembre de 2024**. Hoy lo usan también OpenAI y Google. No es una feature de Claude — es infraestructura que está cambiando cómo la IA se integra en el trabajo real.

---

## La analogía del USB

Antes del USB, cada fabricante tenía su propio conector: ratón, teclado, impresora, cada uno con su cable diferente. El USB estandarizó eso — un conector que funciona con todo.

MCP es el USB de la IA: un estándar que funciona con cualquier herramienta que lo implemente.

---

## Sin MCP vs Con MCP

|Sin MCP|Con MCP|
|---|---|
|El usuario pega información en Claude|Claude accede directamente a la fuente|
|El usuario es el puente|El protocolo es el puente|
|La IA trabaja con datos estáticos|La IA trabaja con datos en tiempo real|
|La IA puede describir cómo crear un issue|La IA puede crear el issue directamente|

---

## MCP vs API

|API|MCP|
|---|---|
|Es la puerta|Es el traductor universal que conoce todas las puertas|
|Tú pones toda la lógica|Claude sabe cómo llamar, qué endpoint usar, cómo formatear|
|Requiere programar la integración|No requiere programar nada|
|La fontanería|El grifo estándar que cualquier IA puede usar|

---

## Relación con function calling

MCP usa [[function-calling]] internamente. Cuando Claude se conecta a Jira via MCP, por debajo está ejecutando function calls contra el servidor MCP que traduce esas llamadas a la API de Jira.

---

## Configuración de referencia — Atlassian

```json
{
  "mcpServers": {
    "jira": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://mcp.atlassian.com/v1/mcp"
      ]
    }
  }
}
```

Autenticación vía OAuth con cuenta de Atlassian. No requiere API token en el config.

> ✅ Endpoint actualizado a `/v1/mcp`. El endpoint `/v1/sse` fue deprecado el 30 de junio de 2026.

---

## Notas técnicas

- Tras configurar, la conexión a Jira aparece en Claude Desktop bajo "connectors"
- El paquete `@cosmix/jira-mcp` devuelve 404 en npm — no usar
- Demo usada en Charla 7 con cuenta personal de Atlassian (`da-ju-ia-talks.atlassian.net`)

---

## Dónde aparece en la serie

| Charla | Rol de los MCPs |
| ------ | --------------- |
| 7 | Introducción del concepto + demo Jira en vivo |
| Futura | GitHub Actions + Copilot coding agent |
