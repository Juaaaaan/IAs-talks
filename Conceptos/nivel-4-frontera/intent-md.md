---
type: Concepto
title: "intent.md — Capturar la intención antes de la spec"
description: "El paso previo a la especificación: un fichero corto y versionado que declara qué se quiere, por qué y bajo qué restricciones. La entrada de la etapa Plan del AI-Native SDLC."
tags: [intent, plan, especificacion, sdd, versionado, requisitos]
related: [sdd-variations, ai-native-sdlc, code-generation-patterns, arnes-completo]
estado: "✅ Publicado"
timestamp: "2026-09-17"
---

# intent.md — Capturar la intención antes de la spec

> _"Antes de decir QUÉ construir, escribe POR QUÉ lo quieres. La spec sin intención es un mapa sin destino."_

---

## Qué es

Un **`intent.md`** es un fichero corto, versionado en el repo, que captura la *intención* de un trabajo antes de escribir la especificación técnica:

- **Qué** se quiere conseguir
- **Por qué** (el problema o el valor)
- **Bajo qué restricciones** (tiempo, tecnología, cumplimiento, lo que no se puede tocar)

Es el eslabón que va *antes* de la spec. La spec responde "qué construir y con qué criterios"; el intent responde "qué queremos y por qué", que es de donde la spec debería derivarse.

---

## Por qué un fichero, y no un prompt

Un prompt en un chat se pierde. Un `intent.md` versionado:
- Deja **traza** de por qué se decidió algo (oro en entornos regulados).
- Se puede **revisar** como se revisa cualquier cambio.
- Es el **contrato** del que derivan spec, tareas y, al final, la validación.

---

## Ejemplo mínimo

```
# intent: portal de pólizas — alta de cliente

## Qué
Permitir dar de alta un cliente y su primera póliza en un solo flujo.

## Por qué
Hoy son dos aplicativos distintos; una parte grande de las altas se queda a medias.

## Restricciones
- Cumplir la política de datos de la compañía (no PII a modelos externos).
- Integrarse con el core actual vía la API existente.
- No romper el flujo de renovación ya en producción.
```

De ahí sale la spec, no al revés.

---

## Cuándo usarlo

| Situación | ¿intent.md? |
|---|---|
| Feature con un "por qué" no obvio | Sí — captura la intención primero |
| Trabajo en entorno regulado | Sí — la traza es requisito |
| Bugfix trivial | No hace falta — issue-as-spec basta |

---

## Relación con otras piezas

- **[[sdd-variations]]** — El intent es el paso previo del que derivan todas las variantes de spec
- **[[ai-native-sdlc]]** — Es la entrada de la etapa Plan
- **[[code-generation-patterns]]** — Cuanto mejor la intención, mejor el código generado
- **[[arnes-completo]]** — Parte del arnés documental, aguas arriba de la spec

---

## Referencias

- [Capture as intent.md — Claude Academy](https://academy.claude.com/courses/ai-native-sdlc-playbook/capture-intent)
