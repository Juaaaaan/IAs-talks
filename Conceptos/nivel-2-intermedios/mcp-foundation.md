---
type: Concepto
title: "MCP Foundation — Model Context Protocol en Foundation"
description: "Uso específico de Model Context Protocol dentro de AI SDLC Foundation para conectar agentes con herramientas y servicios externos bajo permisos y autenticación que siguen viviendo fuera del protocolo."
tags: [ai-sdlc-foundation, mcp-foundation, integracion, herramientas, servicios, provider]
related: [ai-sdlc-foundation, agent, context, provider, mcp]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# MCP Foundation — Model Context Protocol en Foundation

> _"El agente puede salir al mundo real, pero solo a través de una interfaz y unos permisos que alguien más controla."_

---

## Qué es

En AI SDLC Foundation, **MCP Foundation** es la forma de usar **Model Context Protocol** para que un agente interactúe con herramientas y servicios externos de manera estructurada. Su valor específico dentro de Foundation es ofrecer una interfaz común para exponer integraciones sin mezclar cada herramienta con la lógica interna del agente. Para la explicación general del estándar, la referencia amplia sigue siendo [[mcp]].

---

## Papel en AI SDLC Foundation

MCP Foundation conecta al [[agent]] con el exterior sin convertir cada integración en un caso especial irrepetible. Puede anunciarse en [[context]] como capacidad disponible y luego ser consumido por un [[provider]] concreto cuando el runtime arranca. Así, Foundation separa la orquestación interna del sistema de la manera en que el agente consulta GitHub, Jira u otras fuentes documentales.

---

## Cómo funciona

En Foundation, MCP hace disponibles para el agente capacidades externas mediadas por el protocolo, de modo que la interacción con herramientas o servicios no dependa de integraciones ad hoc en cada workflow. Cuando el agente necesita información o una acción fuera de su contexto local, usa esa vía mediada en lugar de acoplarse directamente a cada sistema propietario. El límite crucial es que MCP habilita la integración, pero los permisos, los scopes y la autenticación siguen dependiendo de configuraciones externas al protocolo.

---

## Ejemplos prácticos

### Ejemplo 1 — Consultar GitHub

Un agente de Foundation necesita revisar un pull request y usa una integración MCP para listar ficheros cambiados, leer comentarios o recuperar metadatos del repositorio. El valor está en la interfaz estable, no en acoplar el workflow a una API ad hoc.

### Ejemplo 2 — Leer Jira o una base documental

Otro agente consulta un ticket de Jira o una base de conocimiento corporativa a través de MCP antes de redactar una propuesta. Así reutiliza la misma arquitectura de integración aunque el servicio remoto cambie.

---

## Matices y confusiones habituales

- **Cuidado:** MCP no concede acceso ilimitado a sistemas externos; solo define cómo exponer y consumir herramientas de forma compatible.
- **Cuidado:** Aunque el agente vea una herramienta en el catálogo, la autenticación y los permisos reales siguen resolviéndose fuera del protocolo.
- **Importante:** Usar MCP no elimina la necesidad de gobernanza sobre qué integraciones se permiten y qué datos pueden salir del entorno.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Explica por qué la integración externa forma parte del dominio operativo de Foundation.
- **[[agent]]** — Consume la integración para consultar o accionar servicios externos.
- **[[context]]** — Puede anunciar qué conectores MCP están disponibles en ese entorno.
- **[[provider]]** — Ejecuta el runtime que descubre y expone estas integraciones al agente.
- **[[mcp]]** — Sigue siendo la nota autorizada para el concepto amplio del protocolo más allá de Foundation.
