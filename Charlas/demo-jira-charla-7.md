# Demo — Jira + SDD con Claude Desktop (Charla 7)

**Charla:** [[charla-07-skills-mcps]] **Herramienta:** Claude Desktop + MCP Atlassian **Jira:** `da-ju-ia-talks.atlassian.net` — Proyecto **KAN** **Duración:** 20–25 min

---

## Configuración previa

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

Autenticación vía OAuth con cuenta de Atlassian. No requiere API token.

> ⚠️ El endpoint `/v1/sse` está siendo deprecado. Ver [[mcp]] para la migración pendiente.

**Nota:** Tras configurar, la conexión a Jira aparece en Claude Desktop bajo "connectors", no como icono de herramienta independiente.

---

## Checklist antes de la demo

- [ ] Claude Desktop abierto y conectado (verificar que aparece el conector de Jira)
- [ ] Tablero de Jira abierto en segunda ventana, listo para mostrar
- [ ] `spec.md` de Consulta de Pólizas copiado y listo para pegar
- [ ] Tamaño de fuente de Claude Desktop verificado para proyección
- [ ] Las dos ventanas se ven bien en pantalla

---

## Acto 1 — Conectar Claude a Jira en vivo (8 min)

**Objetivo:** Que la audiencia vea exactamente qué implica conectar Claude a una herramienta real, desde cero.

### Pasos

**1.** Mostrar el `claude_desktop_config.json` en pantalla.

> _"Esto es el enchufe. Le estoy diciendo a Claude que tiene acceso a Jira con estos permisos."_

**2.** Abrir Claude Desktop.

**3.** Escribir:

```
Lista los proyectos de Jira que tengo disponibles
```

**4.** Claude responde con el proyecto KAN → primera reacción de la audiencia.

> _"Lo que acabáis de ver es Claude accediendo a un Jira real, en tiempo real, sin que yo haya pegado nada. El arnés está conectado."_

---

## Acto 2 — Claude trabajando con SDD y Jira (12–15 min)

**Objetivo:** Demostrar el ciclo completo: leer sprint → analizar → generar SDD → crear issues.

### Paso 1 — Lectura del sprint

```
¿Qué issues tenemos en el sprint actual y cuál es el estado de cada una?
```

### Paso 2 — Análisis

```
¿Qué debería priorizar el equipo esta semana y por qué?
```

### Paso 3 — Puente con SDD

```
Basándote en el estado actual del sprint, genera un task.md estructurado
listo para usar con nuestro flujo de desarrollo.
```

> 💡 Mostrar el `task.md` generado en pantalla antes de continuar. Es el ancla visual que conecta SDD → MCP → Claude Code para la audiencia no técnica.

### Paso 4 — El círculo completo ⭐

```
Tengo este spec.md — [pegar el spec de Consulta de Pólizas].
Crea los issues correspondientes en Jira directamente.
```

> ⚠️ **Momento clave:** Cambiar a la ventana de Jira mientras Claude trabaja. Cuando los issues aparezcan en el tablero en tiempo real — ese es el momento de mayor impacto de la demo.

> _"Lo que acabáis de ver es el arnés completo. El spec define qué construir. Jira gestiona cómo se construye. Claude los conecta y actúa en los dos sitios a la vez."_

---

## Notas técnicas

- Esta demo fue validada end-to-end en un proyecto personal ("resin craft art") antes de presentarla en vivo
- El paquete `@cosmix/jira-mcp` devuelve 404 en npm — no usar, usar el MCP oficial de Atlassian
- Si no hay sprint creado en el proyecto, el sprint no puede crearse vía MCP — debe hacerse manualmente desde el Backlog de Jira

---

## Spec usado en la demo

Ver [[demo-spec-consulta-polizas]]