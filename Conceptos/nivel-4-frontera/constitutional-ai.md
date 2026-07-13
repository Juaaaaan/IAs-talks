---
type: Concepto
title: "Constitutional AI & RLHF — Cómo se alinean los modelos"
description: "Técnicas para hacer que los modelos de IA se comporten de forma segura, útil y honesta. RLHF usa feedback humano, Constitutional AI usa principios escritos."
tags: [constitutional-ai, rlhf, alineamiento, seguridad, etica, entrenamiento]
related: [prompt-injection, reasoning-models, synthetic-data, ai-governance]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Constitutional AI & RLHF — Cómo se alinean los modelos

> _"Un modelo potente sin alineamiento es como un motor potente sin volante."_

---

## Qué es

**Alineamiento** es el proceso de hacer que un modelo de IA se comporte de forma:
- **Útil** — responde a lo que le piden
- **Honesta** — no inventa ni engaña
- **Segura** — no genera contenido dañino

Hay dos técnicas principales:

---

## RLHF — Reinforcement Learning from Human Feedback

```
1. El modelo genera varias respuestas
2. Humanos evalúan cuál es mejor
3. Se entrena un "modelo de recompensa" con esas preferencias
4. El modelo original se ajusta para maximizar la recompensa
```

**Ventaja:** Las preferencias humanas son matizadas y contextuales.
**Desventaja:** Caro, lento, difícil de escalar. Los humanos no siempre coinciden.

---

## Constitutional AI (CAI)

Inventado por Anthropic. En vez de humanos evaluando cada respuesta:

```
1. Se escriben "principios constitucionales" (reglas claras)
   Ej: "No ayudes a crear armas", "Sé honesto sobre tus limitaciones"
2. El modelo genera respuestas
3. OTRO modelo evalúa si cumplen los principios
4. El modelo se ajusta para cumplir la "constitución"
```

**Ventaja:** Escalable, consistente, transparente (los principios son públicos).
**Desventaja:** Solo tan bueno como los principios escritos.

---

## Por qué importa para la empresa

Cuando un modelo dice "no puedo ayudarte con eso" o reformula una respuesta para ser más equilibrada, es el alineamiento en acción.

Entender esto ayuda a:
- Saber **por qué** un modelo se niega a hacer algo
- Diseñar **guardrails** efectivos en aplicaciones empresariales
- Evaluar **qué modelos** son más seguros para tu caso de uso

---

## La cadena de alineamiento

```
Pre-training (datos de internet)
    ↓
Supervised Fine-tuning (ejemplos curados)
    ↓
RLHF / Constitutional AI (preferencias/principios)
    ↓
System prompt (instrucciones del desarrollador)
    ↓
Guardrails (filtros adicionales)
```

Cada capa añade más control sobre el comportamiento del modelo.

---

## Relación con otras piezas

- **[[prompt-injection]]** — Los ataques intentan saltarse el alineamiento
- **[[reasoning-models]]** — Los reasoning models tienen alineamiento adicional sobre el razonamiento
- **[[synthetic-data]]** — CAI usa datos sintéticos para escalar el alineamiento
- **[[ai-governance]]** — El alineamiento es la base técnica de la gobernanza

---

## Referencias

- [Anthropic — Constitutional AI paper](https://arxiv.org/abs/2212.08073)
- [OpenAI — RLHF](https://openai.com/index/instruction-following/)
- [Claude's Constitution](https://www.anthropic.com/news/claudes-constitution)
