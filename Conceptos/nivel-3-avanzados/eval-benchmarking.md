---
type: Concepto
title: "Eval & Benchmarking — Medir si la IA funciona bien"
description: "Métodos y métricas para evaluar si un agente o modelo produce resultados correctos, útiles y fiables. Sin evaluación, no sabes si la IA ayuda o si está generando errores silenciosos."
tags: [eval, benchmarking, metricas, calidad, testing, evaluacion]
related: [agentic-workflows, code-generation-patterns, chain-of-thought]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Eval & Benchmarking — Medir si la IA funciona bien

> _"No basta con que la IA responda. Hay que comprobar si responde bien."_

---

## Qué es

**Eval** (evaluación) es el proceso de medir si un modelo o agente de IA produce resultados correctos, útiles y fiables para una tarea concreta.

**Benchmarking** es comparar diferentes modelos, prompts o configuraciones usando las mismas métricas y datasets de prueba.

---

## Por qué importa

| Sin eval | Con eval |
|---|---|
| "Parece que funciona bien" | "Acierta el 87% de las veces en este tipo de tarea" |
| No sabes si un cambio de prompt mejora o empeora | Mides antes y después |
| Elegir modelo por marketing | Elegir modelo por rendimiento en TU tarea |
| Errores silenciosos | Errores detectados y cuantificados |

---

## Tipos de evaluación

### 1. Evaluación automática
- Comparar la salida con una respuesta esperada
- Métricas: exactitud, BLEU, ROUGE, pass@k
- Ejemplo: ¿El código generado pasa los tests?

### 2. Evaluación con LLM-as-judge
- Otro modelo evalúa la calidad de la respuesta
- Útil cuando no hay una respuesta "correcta" única
- Ejemplo: "¿Esta explicación es clara y correcta?"

### 3. Evaluación humana
- Personas revisan y puntúan las respuestas
- Gold standard pero caro y lento
- Ejemplo: Revisión de código por developers

### 4. A/B testing
- Comparar dos versiones del prompt/modelo con usuarios reales
- Medir cuál produce mejores resultados en producción

---

## Métricas comunes

| Métrica | Qué mide | Ejemplo |
|---|---|---|
| **Accuracy** | % de respuestas correctas | 92% de queries SQL válidos |
| **pass@k** | % de código que pasa tests en k intentos | pass@1 = 78% |
| **Latencia** | Tiempo de respuesta | 2.3s por request |
| **Coste** | Tokens consumidos | $0.02 por tarea |
| **Satisfacción** | Valoración humana | 4.2/5 |

---

## Eval en la práctica (este vault)

Para evaluar si el vault OKF funciona bien como fuente de contexto:
- ¿El agente encuentra la respuesta correcta en el vault? (accuracy)
- ¿Cuántos ficheros necesita leer? (eficiencia)
- ¿Las respuestas incluyen el contexto real del proyecto? (grounding)

---

## Relación con otras piezas

- **[[agentic-workflows]]** — Los workflows necesitan eval para verificar cada paso
- **[[code-generation-patterns]]** — Los tests son la eval del código generado
- **[[chain-of-thought]]** — Evaluar el razonamiento, no solo la respuesta final

---

## Referencias

- [OpenAI Evals](https://github.com/openai/evals)
- [LMSYS Chatbot Arena](https://chat.lmsys.org/)
- Concepto en glosario: [[glosario-ia-nivel-1]] §22
