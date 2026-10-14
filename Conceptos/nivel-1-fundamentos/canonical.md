---
type: Concepto
title: "Canonical — La fuente de verdad agnóstica"
description: "Representación en `.apm/` donde AI SDLC Foundation define activos una sola vez sin depender de un proveedor concreto. Es la entrada de proyección, no un runtime ejecutable."
tags: [ai-sdlc-foundation, canonical, apm, proyeccion, runtime, provider]
related: [ai-sdlc-foundation, projection, runtime, provider, sdd]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Canonical — La fuente de verdad agnóstica

> _"Primero defines el activo una vez; luego ya decidirás a qué runtimes lo proyectas."_

---

## Qué es

En AI SDLC Foundation, **Canonical** es la capa fuente que vive en `.apm/` y concentra la definición neutral de skills, workflows, instrucciones y otros activos. Su objetivo es describir qué existe y cómo se relaciona sin casarse todavía con el formato de un proveedor concreto. Por eso actúa como fuente de verdad, pero no como un runtime listo para ejecutarse.

---

## Papel en AI SDLC Foundation

Canonical existe para evitar que el conocimiento reusable se duplique entre plataformas. El sistema toma esta capa como entrada y, a partir de ahí, lanza la [[projection]] hacia los formatos que cada [[provider]] necesita. Si cambias la definición canónica, el cambio se propaga; si cambias solo el runtime generado, rompes esa trazabilidad.

---

## Cómo funciona

El flujo habitual es: editar activos en `.apm/`, validarlos como fuente neutral y después proyectarlos a un [[runtime]] específico. Esa proyección puede generar ficheros, catálogos o configuraciones para distintas herramientas, pero el contrato original sigue viviendo en Canonical. El límite importante es que Canonical describe y organiza; no es la capa que se invoca directamente en producción.

---

## Ejemplos prácticos

### Ejemplo 1 — Editar una skill una vez y proyectarla a Copilot y Claude

Un equipo actualiza la definición de una skill de revisión técnica en `.apm/`. Desde esa única versión canónica, AI SDLC Foundation genera la variante necesaria para GitHub Copilot y la variante equivalente para Claude, sin mantener dos fuentes manuales.

### Ejemplo 2 — Versionar un workflow sin duplicar formatos

Un workflow de creación de ADR se versiona en Canonical con sus pasos, entradas y salidas esperadas. La proyección posterior lo adapta al runtime que corresponda, pero el historial de cambios y la intención del workflow siguen centralizados en la misma definición.

---

## Matices y confusiones habituales

- **Cuidado:** Canonical no significa "configuración global de todo el sistema". Significa "fuente primaria neutral" para los activos que Foundation sabe proyectar.
- **Cuidado:** El runtime generado no debe editarse como fuente principal. Si el cambio importante se hace ahí, el siguiente ciclo de proyección puede sobrescribirlo.
- **Importante:** Que un activo esté en Canonical no implica que ya esté desplegado o disponible en todos los proveedores; todavía necesita pasar por [[projection]].

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Sitúa Canonical dentro del vocabulario completo del sistema.
- **[[projection]]** — Toma la definición canónica y la traduce a formatos concretos.
- **[[runtime]]** — Consume el resultado generado, no la fuente neutral directamente.
- **[[provider]]** — Recibe la proyección ajustada a sus propias convenciones.
- **[[sdd]]** — Complementa la especificación de trabajo con una capa reusable y portable.
