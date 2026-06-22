# Charla 7 — Skills, MCPs y el Arnés Completo

**Fecha:** 17 de junio de 2026 **Asistentes:** ~60–90 (developers junior/senior, RRHH, directivos) **Estado:** ✅ Impartida

---

## Idea central

Esta charla cierra el arco del [[arnes-completo]]. La Charla 6 introdujo el arnés documental ([[sdd]]). Esta añade las dos piezas que lo completan: [[skills]] y [[mcp]].

> _"SDD os dio el arnés documental. Hoy completamos el arnés."_

---

## Estructura

|Bloque|Contenido|Tiempo|
|---|---|---|
|Apertura|Puente desde SDD y arnés|2 min|
|Bloque 1|El problema: la IA vive en una burbuja|3 min|
|Bloque 2|Skills — el arnés de comportamiento|5 min|
|Bloque 3|MCPs — el arnés de integración|5 min|
|Demo|Jira + SDD con Claude Desktop|20–25 min|
|Cierre|3 ideas + dónde empezar|3 min|

---

## Narrativa por bloques

### Apertura

La IA necesita un arnés para ser útil. La Charla 6 dio la primera pieza (SDD). Hoy se añaden Skills y MCPs para completarlo.

### Bloque 1 — El problema

La IA no sabe nada de la empresa. Cada conversación empieza desde cero. Y aunque supiera, no puede actuar fuera de la conversación: puede describir cómo crear un issue en Jira, pero no puede crearlo.

**Frase de anclaje:**

> _"El arnés documental le dice qué hacer. Los Skills le dicen cómo comportarse. Los MCPs le permiten actuar. Los tres juntos son el arnés completo."_

### Bloque 2 — Skills

Un Skill no es un prompt. Es contexto persistente: lo que la IA ya sabe sobre cómo trabaja la empresa antes de que le pidas nada. En Claude se implementa con **Projects** en `claude.ai`.

**Frase de anclaje:**

> _"El Skill no es lo que le pedís a la IA. Es lo que la IA ya sabe sobre cómo trabajáis antes de que le pidáis nada."_

### Bloque 3 — MCPs

MCP es el USB de la IA: un estándar abierto que permite conectar Claude a cualquier herramienta con los mismos permisos y el mismo control. Creado por Anthropic, donado como estándar abierto. Lo usan también OpenAI y Google.

Aclaración anticipada incluida en el guión: **API vs MCP** (la fontanería vs el grifo estándar).

**Frase de anclaje:**

> _"Un MCP es un enchufe estándar entre la IA y el mundo real. Vosotros controláis qué enchufáis."_

### Demo — Dos actos

Ver [[demo-jira-charla-7]] para el flujo completo.

**Acto 1** — Conectar Claude Desktop a Jira en vivo (8 min): mostrar el `claude_desktop_config.json`, listar proyectos, primera reacción de la audiencia al ver el proyecto KAN real.

**Acto 2** — Claude trabajando con SDD y Jira (12–15 min): lectura del sprint → análisis → generación de `task.md` → creación de issues en Jira a partir del [[demo-spec-consulta-polizas|spec de Consulta de Pólizas]].

El momento clave: los issues aparecen en el tablero de Jira en tiempo real mientras la audiencia lo ve.

### Cierre

Tres ideas para llevarse + dónde empezar hoy (Claude Desktop gratuito, MCP de Atlassian disponible para cualquier cuenta Jira Cloud, Projects en `claude.ai`).

**Frase final:**

> _"La semana pasada os dieron las riendas. Hoy habéis visto cómo engancharlas al caballo."_

---

## Lecciones aprendidas

- **La demo es el núcleo.** El momento en que los issues aparecen en Jira en tiempo real es el de mayor impacto. Todo lo anterior es preparación para ese momento.
- **La aclaración API vs MCP funciona.** Es una pregunta que la audiencia técnica tiene siempre en la cabeza; anticiparla en el guión evita que interrumpa el flujo.
- **El bloque teórico de Skills es el más frágil.** Es el único sin demo visual. Conviene tenerlo acotado y apoyarse en el ejemplo del equipo de siniestros para hacerlo concreto.
- **Dos ventanas en pantalla.** Claude Desktop + tablero de Jira simultáneos son imprescindibles para que el efecto visual funcione.

---

## Recursos de la charla

- [[demo-jira-charla-7]] — Flujo completo de la demo
- [[demo-spec-consulta-polizas]] — El spec usado en el Acto 2
- [[mcp]] — Concepto MCP con config de referencia
- [[skills]] — Concepto Skills
- [[sdd]] — Concepto SDD

---

## Próxima charla

[[charla-08-sdd-angular]] — SDD aplicado a un proyecto Angular (proyecto RCA en Jira como demo vehicle).