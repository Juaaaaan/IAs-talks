---
type: Concepto
title: "MCP Ecosystem — El ecosistema de servidores MCP"
description: "Evolución del Model Context Protocol más allá del protocolo: registries, marketplaces, servidores comunitarios y enterprise. El ecosistema que conecta la IA con todo."
tags: [mcp, ecosistema, servidores, marketplace, registry, integraciones]
related: [mcp, function-calling, agentic-workflows, arnes-completo]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# MCP Ecosystem — El ecosistema de servidores MCP

> _"MCP no es solo un protocolo. Es un ecosistema de conexiones entre la IA y el mundo."_

---

## Qué es

El **ecosistema MCP** es el conjunto de servidores, registries, herramientas y estándares que han crecido alrededor del Model Context Protocol desde su lanzamiento por Anthropic en 2024.

Va más allá del protocolo técnico: es un marketplace de integraciones que cualquier agente puede usar.

---

## Componentes del ecosistema

### 1. Servidores MCP
Programas que exponen herramientas para que los agentes las usen.

| Categoría | Ejemplos |
|---|---|
| **Desarrollo** | GitHub, GitLab, Jira, Linear |
| **Datos** | PostgreSQL, BigQuery, Snowflake |
| **Productividad** | Slack, Google Drive, Notion |
| **Diseño** | Figma, Storybook |
| **Cloud** | AWS, GCP, Azure |
| **Observabilidad** | Sentry, Datadog |

### 2. Registries
Catálogos donde descubrir e instalar servidores MCP.

| Registry | Descripción |
|---|---|
| mcp.run | Marketplace oficial |
| Smithery | Catálogo comunitario |
| npmjs.com | Servidores publicados como paquetes npm |

### 3. Clientes MCP
Aplicaciones que se conectan a servidores MCP.

| Cliente | Tipo |
|---|---|
| Claude Desktop | App de escritorio |
| Copilot (VS Code) | IDE |
| Cursor | IDE |
| Windsurf | IDE |
| Continue | IDE (open-source) |

### 4. SDKs
Herramientas para crear tus propios servidores MCP.

- TypeScript SDK (oficial)
- Python SDK (oficial)
- Go, Rust, Java (comunidad)

---

## Evolución

```
2024 Q4: Anthropic publica MCP v1.0
2025 Q1: Primeros servidores comunitarios (GitHub, Slack)
2025 Q2: Copilot y Cursor adoptan MCP
2025 Q3: Registries y marketplaces
2026 Q1: MCP se convierte en estándar de facto
2026 Q2: OpenAI adopta MCP
```

---

## Crear un servidor MCP

```typescript
// Servidor MCP mínimo en TypeScript
const server = new McpServer({ name: "mi-servidor" });

server.tool("buscar_decisiones", { query: z.string() },
  async ({ query }) => {
    // Busca en el vault decisiones relacionadas
    return { content: [{ type: "text", text: resultado }] };
  }
);
```

---

## Relación con otras piezas

- **[[mcp]]** — El protocolo base sobre el que se construye el ecosistema
- **[[function-calling]]** — MCP estandariza el function calling entre proveedores
- **[[agentic-workflows]]** — Los servidores MCP son las herramientas que usan los agentes
- **[[arnes-completo]]** — El arnés de integración se construye sobre el ecosistema MCP

---

## Referencias

- [MCP Specification](https://spec.modelcontextprotocol.io/)
- [MCP Servers — Awesome list](https://github.com/punkpeye/awesome-mcp-servers)
