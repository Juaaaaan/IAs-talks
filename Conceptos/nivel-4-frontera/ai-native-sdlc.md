---
type: Concepto
title: "AI-Native SDLC — El ciclo de vida del desarrollo con IA"
description: "Rediseñar el ciclo de vida del software cuando los agentes escriben la mayor parte del código: por qué el cuello de botella se mueve a planificar, revisar, testear y desplegar. Las seis etapas Plan → Design → Build → Test → Deploy → Maintain."
tags: [sdlc, ciclo-de-vida, agentes, desarrollo, cuello-de-botella, gobernanza]
related: [arnes-completo, sdd-variations, intent-md, agentic-workflows, orchestration-patterns, eval-benchmarking, github-actions, hooks-approval-gates, ai-code-review, metricas-ia]
estado: "✅ Publicado"
timestamp: "2026-09-17"
---

# AI-Native SDLC — El ciclo de vida del desarrollo con IA

> _"Cuando la IA escribe el código en segundos, el cuello de botella deja de ser escribir: pasa a planificar, revisar, testear y desplegar — que siguen a velocidad humana."_

---

## Qué es

El **AI-Native SDLC** es el ciclo de vida del desarrollo de software rediseñado para cuando los agentes escriben la mayor parte del código.

La observación central: las organizaciones ya generan código a una velocidad impensable hace un año, pero los procesos *alrededor* del código —los mismos gates de aprobación, revisiones y handoffs— no han cambiado al mismo ritmo. Resultado: el atasco se desplaza aguas abajo. Escribir deja de ser el cuello de botella; planificar bien, revisar, testear y desplegar pasan a serlo.

Rediseñar el SDLC significa acelerar *esas* etapas, no solo la de teclear.

---

## Las seis etapas

| Etapa | Qué cambia con IA | Pieza del vault |
|---|---|---|
| **1. Plan** | Capturar la intención en un fichero corto y versionado (qué, por qué, restricciones) | [[intent-md]] |
| **2. Design** | Convertir esa intención en spec de requisitos y diseño en una sesión | [[sdd-variations]] |
| **3. Build** | Arrancar en modo plan; el conocimiento vive en ficheros versionados y skills; sesiones paralelas y subagentes | [[agentic-workflows]], [[orchestration-patterns]] |
| **4. Test** | Bucle de feedback para el agente + evals continuas en CI | [[eval-benchmarking]] |
| **5. Deploy** | IA en el review de PRs, hooks como gates de aprobación, integración CI/CD | [[ai-code-review]], [[hooks-approval-gates]], [[github-actions]] |
| **6. Maintain** | Cerrar el bucle: cuando una banda de control se rompe en producción, vuelve a entrar como un nuevo intent.md | [[metricas-ia]] |

---

## El cuello de botella, explicado

Antes, el grueso del esfuerzo era escribir el código y una porción pequeña, el resto. Con agentes, escribir se acerca a coste cero — pero el "resto" no. Un agente puede generar diez PRs en una tarde; si tu equipo revisa a mano, la cola de review se convierte en el nuevo tapón. Lo mismo con el testeo y el despliegue.

Por eso el AI-Native SDLC pone el foco en:
- **Verificación** — cómo pruebas que lo generado es correcto (no solo que compila).
- **Revisión** — cómo revisas a la velocidad a la que se genera, reservando el ojo humano para lo crítico.
- **Gobernanza en ejecución** — cómo pones control *mientras* el agente actúa, no después.

---

## El arnés equipa; el ciclo ordena

Cuidado de no confundirlo con el **[[arnes-completo]]**. Son complementarios:

- El **arnés completo** (SDD + Skills + MCPs) es *con qué equipas* al agente — su documentación, su comportamiento y sus integraciones.
- El **AI-Native SDLC** es *el recorrido* que hace el agente equipado, de la idea a producción.

Uno es la mochila; el otro, la ruta.

---

## Para esta serie

Esta nota es la espina de la **Charla 10 (Full cycle — cierre del arco)**: conecta las piezas sueltas de toda la serie en un único recorrido. Para audiencia mixta, la idea que tiene que aterrizar es una sola: *la IA no elimina el proceso, mueve dónde duele*.

---

## Relación con otras piezas

- **[[arnes-completo]]** — El equipamiento que el agente lleva a través del ciclo
- **[[intent-md]]** — La entrada de la etapa Plan
- **[[sdd-variations]]** — La etapa Design: especificar antes de implementar
- **[[ai-code-review]]** y **[[hooks-approval-gates]]** — El control en la etapa Deploy
- **[[metricas-ia]]** — Cerrar el bucle en Maintain

---

## Referencias

- [The AI-Native SDLC Playbook — Claude Academy](https://academy.claude.com/courses/ai-native-sdlc-playbook)
