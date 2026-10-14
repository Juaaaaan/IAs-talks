---
type: Charla
title: "Charla 23 — Comprobar antes de construir: BDD, ODD y el arnés con nombre"
description: "Cierra la mitad 'antes de construir' de Comprobar (ciclo de la 22): BDD para lo que importa, ODD como contrapeso para el resto. Primera charla que nombra el arnés con su término de industria: AI harness engineering. Récord de asistencia de la serie."
tags: [charla, bdd, odd, ai-harness-engineering, gherkin, rca, verificacion, comprobar]
related: [guion-charla-23, bdd, odd, gherkin, ai-harness-engineering, arnes-completo, rdd]
charla: "Charla 23"
fecha: "2026-10-14"
estado: "✅ Impartida"
timestamp: "2026-10-14"
---

# Charla 23 — Comprobar antes de construir: BDD, ODD y el arnés con nombre

**Fecha:** 14 de octubre de 2026 **Asistentes:** 141 **Estado:** ✅ Impartida

---

## Idea central

> _"La IA no debería decidir por sí sola qué significa correcto. Primero definimos el criterio. Después generamos y verificamos."_

---

## Resultado

La asistencia venía bajando en las charlas previas (80–100 personas). Con la 23 subió a **141** — el salto más grande de la serie hasta la fecha, y la recepción fue muy positiva.

## Estructura

| Bloque | Contenido | Tiempo |
|---|---|---:|
| 1. Apertura | Callback a la 22 y tesis única: definir qué significa correcto | 3 min |
| 2. Escenarios | Ejemplo cotidiano (vacaciones), BDD/Gherkin y ejemplo RCA | 8 min |
| 3. Demo BDD | Implementación y verificación contra el criterio previo (carrito RCA) | 10 min |
| 4. Comportamiento por defecto | Dos casos ODD + nombre del arnés (AI harness engineering) | 9 min |
| 5. Cierre | "Verifying beats generating" | 4 min |

## Decisión de última hora sobre la demo

Tras probar el protocolo ODD con Copilot sobre RCA el día antes, Juan decidió montar la demo **con todo ya creado** en lugar de generar en directo, para no depender de que el modelo clasificara bien la petición delante de la sala.

Hallazgo útil del ensayo: al implementar el escenario Gherkin del Bloque 3, el agente generó automáticamente una carpeta `odd/tasks/` con el documento de la tarea — confirmación en vivo de que ODD y BDD no son alternativas que compiten, sino que están anidados (el escenario Gherkin convive con, e incluso alimenta, la disciplina ODD para trabajo sustancial).

## Lecciones aprendidas

- Preparar la demo "ya creada" en vez de generar en directo reduce el riesgo sin perder fuerza narrativa — el público valora ver la evidencia (el `Then` cumplido, el documento de tarea), no el proceso de generación en sí.
- El patrón "ODD y BDD anidados, no alternativos" puede mostrarse con evidencia real (la carpeta `odd/tasks/` generada como efecto colateral de una demo BDD) sin necesitar una demo ODD separada.
- Una tesis única por charla (aquí: "la IA no debería decidir sola qué es correcto") sigue funcionando mejor que repartir la atención entre varios conceptos con el mismo peso.

---

## Próxima charla

La mitad "después de construir" de Comprobar —revisar código ya existente— queda reservada para una charla futura, con su propio framework (RDD) y su propia demo.
