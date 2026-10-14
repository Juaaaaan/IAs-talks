---
type: Concepto
title: "Provider — La plataforma que ejecuta Foundation"
description: "Plataforma de IA que descubre runtimes y ejecuta agentes o workflows de AI SDLC Foundation, separada tanto del modelo concreto como de la política abstracta de capacidad."
tags: [ai-sdlc-foundation, provider, plataforma, runtime, discovery, ejecucion]
related: [ai-sdlc-foundation, projection, runtime, tier, federated-ai]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Provider — La plataforma que ejecuta Foundation

> _"Foundation diseña las capacidades, pero alguien concreto tiene que descubrirlas y ponerlas en marcha."_

---

## Qué es

En AI SDLC Foundation, **Provider** es la plataforma de IA que ejecuta agentes, workflows y activos derivados del sistema, como GitHub Copilot, Claude Code o una CLI especializada. Es quien descubre el runtime que tiene delante, interpreta sus convenciones y ofrece el entorno real de operación. Hablar del provider es hablar de la plataforma anfitriona, no del modelo concreto que esa plataforma termine usando por debajo.

---

## Papel en AI SDLC Foundation

Provider es el destino de [[projection]] y el lector natural del [[runtime]] generado. Gracias a esta separación, la misma capacidad puede funcionar en más de una plataforma mientras cada una reciba la forma que sabe auto-descubrir. Foundation necesita este concepto para distinguir entre la lógica portable del sistema y las particularidades de ejecución de cada anfitrión.

---

## Cómo funciona

Cada provider define sus rutas de descubrimiento, su formato de archivos y su manera de exponer agentes, instrucciones o integraciones al usuario. Foundation adapta sus activos a esas reglas y deja que la plataforma los cargue al iniciar. La frontera clave es que provider no equivale a modelo: una misma [[model-policy]] o un mismo [[tier]] abstracto puede mapearse sobre varios providers diferentes.

---

## Ejemplos prácticos

### Ejemplo 1 — GitHub Copilot descubre `.github/`

Un runtime proyectado a `.github/` queda disponible porque GitHub Copilot sabe recorrer esa estructura y cargar los activos correspondientes. El provider pone en marcha Foundation al reconocer ese layout.

### Ejemplo 2 — Claude Code descubre `.claude/`

Otro proyecto proyecta sus activos a `.claude/` y Claude Code los auto-descubre al arrancar. La capacidad del sistema es similar, pero el punto de entrada lo resuelve otro provider con convenciones propias.

---

## Matices y confusiones habituales

- **Cuidado:** Provider no es sinónimo de modelo; una plataforma puede cambiar los modelos subyacentes sin dejar de ser el mismo provider.
- **Cuidado:** Que una política funcione en un provider no implica que dependa exclusivamente de él; muchas reglas pueden portarse a varios entornos.
- **Importante:** Si se mezclan responsabilidades de provider y runtime, resulta difícil saber si un problema nace en la plataforma anfitriona o en los artefactos generados.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Sitúa al provider como capa de ejecución del dominio.
- **[[projection]]** — Genera la variante específica que cada provider sabrá consumir.
- **[[runtime]]** — Es el conjunto de ficheros que la plataforma descubre al iniciar.
- **[[tier]]** — Ayuda a separar la plataforma anfitriona de la capacidad abstracta que luego se le asigna.
- **[[federated-ai]]** — Amplía la conversación sobre múltiples plataformas y entornos interoperables.
