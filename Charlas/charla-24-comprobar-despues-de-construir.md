---
type: Charla
title: "Charla 24 — Comprobar después de construir: ai-code-review y RDD"
description: "Cierra la mitad 'después de construir' de Comprobar (ciclo de la 22, mitad anterior en la 23). Checks deterministas, revisión agéntica proporcional al riesgo, candidato congelado, receipt y lentes 4R, demostrados con dos PR reales de RCA revisadas en sesiones separadas."
tags: [charla, ai-code-review, rdd, receipt-driven-development, revision, pull-request, verificacion, comprobar, rca]
related: [guion-charla-24, MATERIAL-CHARLA-24-COMPROBAR-DESPUES-DE-CONSTRUIR, ai-code-review, rdd, bdd, odd, ai-harness-engineering, arnes-completo, guion-charla-23]
charla: "Charla 24"
fecha: "2026-10-28"
estado: "✅ Impartida"
timestamp: "2026-10-28"
---

# Charla 24 — Comprobar después de construir: ai-code-review y RDD

**Fecha:** 28 de octubre de 2026 **Asistentes:** 110 **Estado:** ✅ Impartida

---

## Idea central

> _"Definir qué es correcto y demostrar que un resultado lo cumple son dos momentos diferentes."_

---

## Resultado

110 personas, buena acogida — la gente lo agradeció y, después de la charla, hizo más preguntas de lo habitual sobre cómo aplicarlo a su propio trabajo.

## Estructura

| Bloque | Contenido | Tiempo |
|---|---|---:|
| 1. Apertura | Callback a la charla 23 y pregunta de hoy | 3 min |
| 2. El nuevo cuello de botella | De producir cambios a demostrar que son aceptables | 5 min |
| 3. El reviewer ya existía | Qué teníamos en la charla 8 y qué faltaba | 3 min |
| 4. Demo de contraste | Dos PR abiertas, dos profundidades, dos receipts | 12 min |
| 5. RDD con nombre | Candidato congelado, riesgo, lentes 4R y receipt | 8 min |
| 6. Cierre | El arco completo de Comprobar | 4 min |

## Decisión aplicada en la demo

Las dos PR de contraste (color del botón «Añadir al carrito» y validación de stock a cero) se revisaron en **sesiones separadas** del reviewer agent extendido con RDD — no en la misma conversación. Es la misma disciplina que pide el concepto de **candidato congelado**: mantener cada revisión aislada evita que el contexto de una PR contamine el criterio aplicado a la otra. Los dos receipts resultantes se mostraron en pantalla tal cual, sin reconstruir el proceso en directo.

## Lecciones aprendidas

- El contraste de dos receipts reales (uno breve, uno con las 4R completas) generó más preguntas posteriores que las últimas charlas — señal de que la idea de "evidencia proporcional al riesgo" conectó más allá del minuto de la sesión.
- Revisar cada PR en una sesión propia, en vez de encadenar las dos revisiones en la misma conversación, resultó una forma sencilla y efectiva de aplicar "candidato congelado" en la práctica, no solo en la teoría del guion.

---

## Próxima charla

Quedan **Publicar** y **Mantener**, las dos últimas paradas del ciclo de seis pasos presentado en la charla 22. Todavía sin planificar ni fecha.
