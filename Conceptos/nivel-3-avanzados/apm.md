---
type: Concepto
title: "APM — Agent Package Manager"
description: "Sistema de distribución de AI SDLC Foundation para instalar y actualizar bundles reutilizables sin confundir la logística del activo con el agente que luego lo usará."
tags: [ai-sdlc-foundation, apm, distribucion, bundles, packs, runtime]
related: [ai-sdlc-foundation, pack, canonical, projection, runtime]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# APM — Agent Package Manager

> _"Antes de ejecutar capacidades, alguien tiene que empaquetarlas, distribuirlas y mantenerlas alineadas."_

---

## Qué es

En AI SDLC Foundation, **APM** significa **Agent Package Manager** y nombra el sistema de distribución que instala, actualiza y organiza bundles reutilizables del ecosistema. Su función es mover activos como packs, catálogos o definiciones empaquetadas entre repositorios y runtimes sin obligar a copiar carpetas manualmente. Habla de distribución y lifecycle de activos, no de la inteligencia que después ejecutará una tarea.

---

## Papel en AI SDLC Foundation

APM permite que la capa [[canonical]] y sus derivados lleguen a distintos entornos de forma repetible. Gracias a él, un equipo puede compartir un [[pack]] de capacidades, publicarlo para varios repositorios y mantener una ruta clara entre el origen, la [[projection]] y el [[runtime]] donde se descubre. Sin una pieza así, Foundation corre el riesgo de volver a instalaciones artesanales difíciles de auditar.

---

## Cómo funciona

El flujo típico consiste en empaquetar activos compatibles con Foundation, publicarlos en un canal de distribución y permitir que otro entorno los instale o actualice cuando los necesite. APM se ocupa de la logística: qué bundle existe, qué versión circula y cómo se incorpora al entorno destino. El límite importante es que no define por sí solo cómo se ejecutará cada activo una vez instalado; esa responsabilidad queda del lado del runtime y de las piezas que el provider descubra.

---

## Ejemplos prácticos

### Ejemplo 1 — Instalar un pack de revisión

Un equipo mantiene un pack con skills y plantillas para revisión técnica. APM distribuye ese bundle a varios repositorios para que todos instalen la misma capacidad sin replicar a mano sus activos en cada proyecto.

### Ejemplo 2 — Actualizar un bundle compartido

Otro equipo publica una nueva versión de un bundle documental que corrige metadatos y reorganiza activos comunes. APM facilita que los consumidores actualicen la distribución compartida y reciban esos cambios sin rehacer la instalación desde cero.

---

## Matices y confusiones habituales

- **Cuidado:** APM distribuye activos; no es un agente que razona o ejecuta tareas por cuenta propia.
- **Cuidado:** No conviene asumir comandos concretos si la implementación real del package manager no está confirmada en ese provider o tooling.
- **Importante:** Instalar un bundle no garantiza que todos sus activos queden ya activos en ejecución; todavía deben ser descubiertos y usados en el runtime adecuado.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Sitúa APM dentro de la cadena completa de definición, distribución y ejecución.
- **[[pack]]** — Es la unidad modular que APM suele instalar o actualizar.
- **[[canonical]]** — Aporta la fuente de verdad desde la que se originan muchos activos distribuibles.
- **[[projection]]** — Traduce definiciones canónicas antes o después de su distribución según el flujo adoptado.
- **[[runtime]]** — Recibe los activos ya distribuidos para que el provider pueda descubrirlos.
