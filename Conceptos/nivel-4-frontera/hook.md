---
type: Concepto
title: "Hook — La comprobación automática pre o post"
description: "Comprobación automática que se ejecuta antes o después de una estación para validar entradas o salidas sin confundir la verificación con la decisión final de calidad."
tags: [ai-sdlc-foundation, hook, automatizacion, validacion, station, trace]
related: [ai-sdlc-foundation, station, gate, script, trace, hooks-approval-gates]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Hook — La comprobación automática pre o post

> _"Hay verificaciones que conviene disparar solas, justo antes o justo después del trabajo principal."_

---

## Qué es

En AI SDLC Foundation, **Hook** es una comprobación automática que se ejecuta antes o después de una [[station]]. Su función es validar entradas, salidas o condiciones esperadas alrededor de ese paso sin convertir la estación entera en una cadena manual de revisiones. Habla de verificaciones automáticas, no del veredicto final sobre si el flujo debe continuar.

---

## Papel en AI SDLC Foundation

Hook añade disciplina repetible a los bordes del workflow. Puede detectar pronto problemas de formato, contexto insuficiente o calidad básica antes de que se propague el error a otras estaciones. En Foundation sirve como pieza auxiliar de control local: aporta evidencia reutilizable que luego un [[gate]] puede interpretar y que un [[trace]] puede dejar registrada.

---

## Cómo funciona

El hook se engancha conceptualmente al inicio o al final de una estación y lanza una comprobación automática sobre aquello que conviene vigilar de forma rutinaria. Puede validar la entrada antes de delegar el trabajo o inspeccionar la salida justo después de producirla. Su frontera es clara: el hook ejecuta la comprobación; no reemplaza al gate que decide pass, warn o block, ni al [[script]] interno que mantiene Foundation fuera del flujo funcional del usuario.

---

## Ejemplos prácticos

### Ejemplo 1 — Pre-hook de validación de entrada

Antes de una estación de análisis, un pre-hook comprueba que la petición trae los datos mínimos o el contexto necesario para que el agente no arranque a ciegas. Si detecta que falta información básica, deja constancia temprana para que el flujo no construya sobre una entrada defectuosa.

### Ejemplo 2 — Post-hook de lint

Después de una estación que genera o modifica artefactos, un post-hook ejecuta una comprobación de lint o formato para detectar inconsistencias rápidas. Ese resultado no es aún el gate, pero sí evidencia útil para la decisión posterior.

---

## Matices y confusiones habituales

- **Cuidado:** Un hook ejecuta una comprobación automática; no interpreta por sí solo la calidad global del paso ni sustituye al [[gate]].
- **Cuidado:** No toda comprobación debe ser un hook. Solo conviene automatizar lo que realmente aporta señal repetible en el borde pre o post de una estación.
- **Importante:** Aunque pueda apoyarse en herramientas internas, hook no es sinónimo de [[script]]. El script describe herramientas de Foundation; el hook describe una comprobación insertada en el flujo de ejecución.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Sitúa los hooks dentro del modelo operativo del sistema.
- **[[station]]** — Marca el paso antes o después del cual el hook se dispara.
- **[[gate]]** — Usa o interpreta la evidencia generada por el hook para decidir cómo sigue el flujo.
- **[[script]]** — Ayuda a distinguir entre herramientas internas de mantenimiento y comprobaciones automáticas del workflow.
- **[[trace]]** — Conserva la señal producida por el hook dentro del historial auditable del proceso.
- **[[hooks-approval-gates]]** — Nota general del vault sobre comprobaciones automáticas y puertas de aprobación; Hook es su aplicación concreta dentro de Foundation.
