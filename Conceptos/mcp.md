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

Una pregunta habitual al introducir el concepto:

|API|MCP|
|---|---|
|Es la puerta|Es el traductor universal que conoce todas las puertas|
|Tú pones toda la lógica|Claude sabe cómo llamar, qué endpoint usar, cómo formatear|
|Requiere programar la integración|No requiere programar nada|
|La fontanería|El grifo estándar que cualquier IA puede usar|

---

## En la metáfora del arnés

El MCP es el **arnés de integración**: lo que permite a la IA salir de la conversación y actuar en el mundo real con los permisos que el equipo decide.

---

## Configuración de referencia — Atlassian

```json
{
  "mcpServers": {
    "jira": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://mcp.atlassian.com/v1/sse"
      ]
    }
  }
}
```

Autenticación vía OAuth con cuenta de Atlassian. No requiere API token en el config.

> ⚠️ **Pendiente**: El endpoint `/v1/sse` está siendo deprecado. Migrar a `https://mcp.atlassian.com/v1/mcp` antes o durante la serie.

---

## MCPs usados en la serie

|MCP|Herramienta|Charla|
|---|---|---|
|Atlassian oficial|Jira Cloud (`da-ju-ia-talks.atlassian.net`)|7|
|Figma MCP|Figma|9|

---

## Notas técnicas

- Tras configurar, la conexión a Jira aparece en Claude Desktop bajo "connectors", no como icono de herramienta
- El paquete `@cosmix/jira-mcp` devuelve 404 en npm — no usar
- Para proyectos sin sprint creado, usar JQL: `project = RCA ORDER BY created ASC`

---

## Relación con otras piezas

- **[[sdd]]** — El MCP permite actuar sobre el spec directamente (crear issues desde un `spec.md`)
- **[[skills]]** — Skills + MCPs completan el arnés que SDD inicia
- **[[arnes-completo]]** — El MCP es la tercera y última pieza del arnés

---

## Dónde aparece en la serie

| Charla | Rol de los MCPs                               |
| ------ | --------------------------------------------- |
| 7      | Introducción del concepto + demo Jira en vivo |
| 9      | Figma/Stitch MCP para flujos de diseño        |
| 10     | Parte del ciclo completo                      |