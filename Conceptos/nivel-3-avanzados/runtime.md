---
type: Concepto
title: "Runtime — Los ficheros generados que descubre el provider"
description: "Conjunto de ficheros generados y auto-descubiertos por cada provider al iniciar, derivados de la fuente canónica y sujetos a regeneración en futuras proyecciones."
tags: [ai-sdlc-foundation, runtime, provider, discovery, generados, instruction]
related: [ai-sdlc-foundation, canonical, projection, provider, instruction]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Runtime — Los ficheros generados que descubre el provider

> _"Lo que el provider ve al arrancar no es la definición abstracta, sino su materialización concreta y lista para descubrir."_

---

## Qué es

En AI SDLC Foundation, **Runtime** es el conjunto de ficheros generados que un [[provider]] auto-descubre al iniciar para saber qué agentes, instrucciones o integraciones tiene disponibles. Es la salida operativa que baja a tierra lo que antes estaba definido de forma neutral en [[canonical]]. Por eso runtime describe una materialización concreta de ejecución, no la fuente de verdad del sistema.

---

## Papel en AI SDLC Foundation

Runtime es el punto donde la teoría se vuelve descubrimiento real. La [[projection]] escribe aquí las variantes que la plataforma sabe cargar, y a partir de ese momento el provider puede activar una [[instruction]], registrar catálogos o exponer capacidades al agente. Foundation lo necesita para separar claramente origen, transformación y ejecución.

---

## Cómo funciona

Cuando se proyectan los activos canónicos, el sistema genera carpetas, catálogos y configuraciones con el formato que el provider espera. Al arrancar, la plataforma inspecciona esas ubicaciones y construye su vista operativa del entorno. El límite central es que runtime es una salida derivada: si alguien edita manualmente esos ficheros, la siguiente proyección puede borrar o reemplazar esos cambios.

---

## Ejemplos prácticos

### Ejemplo 1 — `.github/agents/`

Un provider descubre un árbol `.github/agents/` generado por Foundation y lo usa para registrar agentes disponibles dentro del proyecto. Esa carpeta representa el runtime listo para consumo, no el diseño canónico que originó el contenido.

### Ejemplo 2 — `.claude/skills/`

Otro entorno recibe una estructura `.claude/skills/` con skills proyectadas para Claude Code. El provider carga esos ficheros al iniciar porque forman parte del runtime específico que reconoce.

---

## Matices y confusiones habituales

- **Cuidado:** Runtime no es la capa canonical; es la salida derivada que el provider consume en ejecución.
- **Cuidado:** Cambiar a mano los ficheros generados puede funcionar temporalmente, pero esos cambios pueden perderse en la siguiente proyección.
- **Importante:** Un runtime válido para un provider puede ser inútil para otro si no respeta sus convenciones de descubrimiento.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Da contexto al runtime como capa ejecutable del sistema.
- **[[canonical]]** — Sigue siendo el origen del contenido que el runtime materializa.
- **[[projection]]** — Genera los ficheros concretos que acaban en runtime.
- **[[provider]]** — Es quien descubre y carga esos archivos al iniciar.
- **[[instruction]]** — Es uno de los activos que puede vivir dentro del runtime generado.
