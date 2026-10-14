---
type: Concepto
title: "Projection — De canonical a cada provider"
description: "Transformación que convierte definiciones canónicas de AI SDLC Foundation en ficheros y estructuras específicas para el runtime de cada provider sin perder la trazabilidad hacia la fuente de verdad."
tags: [ai-sdlc-foundation, projection, canonical, provider, runtime, generacion]
related: [ai-sdlc-foundation, canonical, provider, runtime, instruction]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Projection — De canonical a cada provider

> _"La misma intención no se despliega igual en todas partes: primero se traduce al dialecto de cada plataforma."_

---

## Qué es

En AI SDLC Foundation, **Projection** es la transformación que toma definiciones de [[canonical]] y las convierte en artefactos concretos para cada [[provider]]. Esa traducción adapta nombres, rutas, formatos y convenciones para generar el [[runtime]] que una plataforma concreta sabe descubrir. No es una copia ciega de ficheros, sino una proyección desde una fuente neutral hacia una forma ejecutable específica.

---

## Papel en AI SDLC Foundation

Projection protege la portabilidad de Foundation. Permite definir una [[instruction]], una skill o un workflow una sola vez y luego derivar las variantes que GitHub Copilot, Claude Code u otra CLI necesiten para ejecutarlas. Sin esa capa, la promesa de tener una fuente de verdad agnóstica quedaría rota por configuraciones manuales divergentes.

---

## Cómo funciona

La proyección toma definiciones de [[canonical]] y las transforma en ficheros de [[runtime]] específicos para el [[provider]] que los va a ejecutar. La idea clave es la transformación entre una fuente neutral y una salida adaptada al entorno de destino, sin convertir esos artefactos generados en la fuente de verdad del sistema. El límite esencial es doble: la proyección no consiste en copiar literalmente directorios, y los artefactos generados no pasan a ser la fuente de verdad del sistema.

---

## Ejemplos prácticos

### Ejemplo 1 — Generar `.github/`

Una definición canónica de agentes e instrucciones se proyecta a un árbol `.github/` para que GitHub Copilot lo descubra al iniciar el entorno. El contenido final responde al contrato del provider, no necesariamente al layout interno de Canonical.

### Ejemplo 2 — Generar `.claude/`

El mismo activo base se transforma a una estructura `.claude/` con los ficheros y convenciones que Claude Code espera. La capacidad sigue siendo la misma, pero el runtime generado habla el dialecto de otra plataforma.

---

## Matices y confusiones habituales

- **Cuidado:** Projection no es copiar ficheros literalmente de una carpeta a otra; hay adaptación semántica y estructural.
- **Cuidado:** Los ficheros generados no deben considerarse la fuente principal, porque un nuevo ciclo de proyección puede sobrescribir cambios manuales.
- **Importante:** Si las reglas de mapping son ambiguas, la portabilidad aparente se rompe y cada provider termina comportándose de forma distinta.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Explica por qué Foundation necesita una capa de traducción entre diseño y ejecución.
- **[[canonical]]** — Es la fuente neutral desde la que parte la proyección.
- **[[provider]]** — Recibe la variante adaptada a sus convenciones de descubrimiento.
- **[[runtime]]** — Es la salida materializada que el provider acabará cargando.
- **[[instruction]]** — Ejemplifica uno de los activos que puede definirse en canonical y proyectarse a múltiples formatos.
