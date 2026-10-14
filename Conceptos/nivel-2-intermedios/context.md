---
type: Concepto
title: "Context — El catálogo disponible en runtime"
description: "Registro o catálogo YAML que un agente carga en runtime para descubrir qué activos están disponibles. Informa disponibilidad, pero no equivale a la ventana de contexto del modelo ni concede permisos por sí mismo."
tags: [ai-sdlc-foundation, context, catalogo, runtime, discovery, agent]
related: [ai-sdlc-foundation, agent, skill-foundation, mcp-foundation, context-engineering]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Context — El catálogo disponible en runtime

> _"El agente no adivina qué tiene a mano: lo descubre leyendo un catálogo."_

---

## Qué es

En AI SDLC Foundation, **Context** es el registro que enumera los activos disponibles durante la ejecución: skills instaladas, herramientas, plantillas o packs accesibles. Suele materializarse como un catálogo YAML que el agente carga al arrancar para saber qué puede descubrir. Aquí "contexto" significa inventario operativo, no la ventana de tokens del LLM.

---

## Papel en AI SDLC Foundation

Context hace visible el ecosistema que rodea a un [[agent]] en un [[runtime]] concreto. Su valor está en convertir una instalación dispersa en un catálogo consultable y consistente, de forma que el agente sepa qué piezas existen antes de intentar usarlas. Es la capa de descubrimiento que conecta la ejecución con activos como [[skill-foundation]] o [[mcp-foundation]].

---

## Cómo funciona

Cuando el runtime se inicia, carga un catálogo que describe nombres, tipos, rutas o identificadores de los activos disponibles. El agente consulta ese inventario para decidir qué skill activar, qué plantilla completar o qué integración invocar. El límite importante es que Context anuncia disponibilidad; la autorización real sigue dependiendo de la configuración del runtime y del proveedor.

---

## Ejemplos prácticos

### Ejemplo 1 — Catálogo de skills instaladas

Un equipo mantiene un YAML donde aparecen las skills de seguridad, arquitectura y documentación que el runtime puede activar. El agente lee ese catálogo al comenzar y sabe cuál existe sin tener que recorrer carpetas o confiar en memoria implícita.

### Ejemplo 2 — Catálogo de herramientas o plantillas accesibles

Otro runtime publica en Context qué plantillas de ADR y qué herramientas de revisión están disponibles para ese entorno. El agente puede decidir usar una plantilla concreta o iniciar una integración porque el catálogo la declara como accesible.

---

## Matices y confusiones habituales

- **Cuidado:** Context aquí no es la ventana de contexto del LLM. Es un catálogo de disponibilidad en runtime, no el espacio de tokens que el modelo puede retener.
- **Cuidado:** Registrar un activo no concede permisos automáticamente. Una herramienta puede aparecer en Context y aun así requerir autorización adicional para ejecutarse.
- **Importante:** Un catálogo desactualizado provoca decisiones erróneas del agente aunque el activo exista físicamente en disco.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Ubica Context dentro del modelo operativo de Foundation.
- **[[agent]]** — Es quien consulta el catálogo para decidir con qué piezas trabajar.
- **[[skill-foundation]]** — Puede descubrirse y activarse gracias al registro de Context.
- **[[mcp-foundation]]** — Comparte la misma necesidad de ser catalogado para resultar visible.
- **[[context-engineering]]** — Ayuda a distinguir entre el contexto documental de un sistema y este catálogo de runtime.
