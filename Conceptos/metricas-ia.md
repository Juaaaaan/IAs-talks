---
type: Concepto
title: "Métricas de IA"
description: "Cómo saber si la IA está funcionando de verdad: métricas de agentes conversacionales (engagement, resolution, deflection), métricas DORA de equipos de desarrollo y el AI Productivity Paradox"
tags: [metricas, dora, copilot-studio, adopcion, productividad, nivel-4]
related: [copilot-studio, agente-ia]
charla: "Charla 13"
estado: "✅ Publicado"
timestamp: "2026-07-22"
---

# Métricas de IA

> _"Medir adopción es fácil. Medir impacto real es el siguiente reto."_

---

## Qué es

Construir un agente o adoptar una herramienta de IA es la parte visible. La pregunta que casi nadie se hace antes de desplegar en producción es: **¿cómo sé si está funcionando bien de verdad?** No basta con que responda — hay que saber si resuelve problemas, si la gente lo usa y si vuelve a usarlo.

---

## Las tres preguntas que simplifican cualquier métrica de IA

| Pregunta | Métrica |
|----------|---------|
| ¿Lo usa la gente? | Adoption rate |
| ¿Les ayuda? | Resolution rate |
| ¿Vuelven? | Retención semana a semana |

Si las tres son positivas, la IA está funcionando. Si alguna falla, ahí está el problema.

---

## Métricas de agentes conversacionales (Copilot Studio)

- **Engagement rate** — % de quienes abrieron el agente que le hicieron al menos una pregunta. Si es bajo, el agente no se está descubriendo o no queda claro para qué sirve.
- **Resolution rate** — % de conversaciones resueltas sin escalar a una persona. La métrica más importante: mide si el agente resuelve, no solo si responde.
- **Deflection rate** — % de solicitudes atendidas sin intervención humana. La que le importa a dirección para justificar la inversión.

Copilot Studio también permite definir **métricas personalizadas en lenguaje natural** (p. ej. "¿el usuario tuvo que reformular su pregunta más de dos veces?"), sin necesidad de código.

---

## Métricas DORA (equipos de desarrollo)

DORA (DevOps Research and Assessment) publica anualmente un informe sobre la salud de los equipos de desarrollo. Cuatro métricas clásicas:

- **Deployment frequency** — con qué frecuencia se despliega a producción
- **Lead time for changes** — tiempo desde que se escribe una línea de código hasta que llega a producción
- **Change failure rate** — % de despliegues que causan problemas
- **Time to restore service** — tiempo de recuperación tras un incidente

### El AI Productivity Paradox (hallazgo DORA 2025)

La adopción masiva de asistentes de código dispara el output individual — hasta un 98% más de pull requests por desarrollador, según los datos. Pero las métricas de entrega organizacional se mantienen planas.

La causa: el tiempo ahorrado escribiendo código regresa como tiempo invertido en revisar y depurar lo que la IA generó — el **"verification tax"**. Más velocidad individual, métricas organizacionales planas: eso es el AI Productivity Paradox.

> Conclusión práctica: más velocidad sin calidad no es progreso, es deuda técnica acumulada.

---

## Relación con otras piezas

- **[[copilot-studio]]** — Fuente de las métricas de agentes conversacionales
- **[[agente-ia]]** — Lo que se está midiendo en el caso de los agentes

---

## Dónde aparece en la serie

| Charla | Rol del concepto |
| ------ | --------------- |
| 13 | Introducción de las métricas de Copilot Studio + apunte técnico sobre DORA y el AI Productivity Paradox |
| 14 (prevista) | Profundización: métricas DORA, developer velocity y cómo medir el impacto real de la IA en equipos de desarrollo |
