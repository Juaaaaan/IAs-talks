---
type: Charla
title: "Charla 12 — El mapa de la IA: dónde estáis y adónde va esto"
description: "Charla de cierre de ciclo. Presenta un mapa de madurez en 4 niveles (Fundamentos, Intermedios, Avanzados, Frontera), repasa 10 conceptos técnicos con demos en Copilot 365 y GitHub Copilot Desktop, y revela que el equipo ya opera en Nivel 3 sin saberlo."
tags: [charla, mapa-ia, niveles-madurez, rag, embeddings, function-calling, temperature, chain-of-thought, agentic-workflows, ai-governance, demo]
related: [arnes-completo, sdd, skills, mcp, wiki-llm, okf, guion-charla-12, charla-07-skills-mcps, charla-08-copilot-instrucciones]
charla: "Charla 12"
fecha: "2026-07-15"
estado: "✅ Impartida"
timestamp: "2026-07-15"
---

# Charla 12 — El mapa de la IA: dónde estáis y adónde va esto

**Fecha:** 15 de julio de 2026 (aprox.) **Asistentes:** ~60–90 (developers junior/senior, RRHH, directivos, comercial) **Estado:** ✅ Impartida

---

## Idea central

Esta charla no introduce una herramienta nueva. Es la charla de cierre de ciclo: da el **mapa** que conecta todo lo visto en las charlas anteriores (SDD, Skills, MCPs, instrucciones persistentes, Wiki LLM) dentro de un marco de cuatro niveles de madurez en IA, y revela a la audiencia que, sin saberlo, ya llevan semanas operando en el Nivel 3 (avanzado).

> *"No hace falta saber cómo está hecho el motor para saber conducir. Pero sí ayuda saber en qué marcha estás."*

El mapa tiene cuatro niveles:

```
Nivel 1 — Fundamentos     → lo que hemos construido juntos
Nivel 2 — Intermedios     → lo que se ve en esta charla
Nivel 3 — Avanzados       → donde ya estaban sin saberlo
Nivel 4 — Frontera        → hacia dónde va esto
```

---

## Estructura

| Bloque | Contenido | Tiempo |
|--------|-----------|--------|
| Apertura | El mapa — presentación de los niveles | 3 min |
| Nivel 1 | Repaso relámpago — lo ya construido | 2 min |
| Nivel 2 | 10 conceptos técnicos, con demos | 20 min |
| Nivel 3 | El momento wow — ya están ahí | 8 min |
| Nivel 4 | Hacia dónde va esto | 8 min |
| Cierre | Mapa completo + ideas para llevarse | 4 min |

**Herramientas de demo:** Copilot 365 (system prompt, context engineering, temperature, structured output) y GitHub Copilot Desktop (RAG con el vault de RCA, chain-of-thought, multimodal).

---

## Narrativa por bloques

### Apertura

Puente desde las charlas anteriores: se ha conectado Claude a Jira ([[charla-07-skills-mcps]]), se han dado instrucciones persistentes a Copilot ([[charla-08-copilot-instrucciones]]), se ha construido una wiki que recuerda el conocimiento del equipo. Pero nunca se había dado el marco que conecta todas esas piezas entre sí. Esta charla lo hace.

### Nivel 1 — Repaso relámpago (2 min)

Repaso sin profundizar, solo para anclar la base: **SDD**, **Skills**, **Wiki LLM + OKF**, **Arnés completo**. Es la base sobre la que se construye el resto de la charla.

### Nivel 2 — Los 10 conceptos (20 min)

Bloque técnico central, dos minutos por concepto, todos anclados a algo que la audiencia ya vio en vivo en charlas anteriores:

1. **System prompt** — demo en Copilot 365 comparando respuesta con y sin instrucciones previas. Se conecta directamente con el `CLAUDE.md` y `copilot-instructions.md` de la Charla 8.
2. **Context engineering** — mismo prompt, distinto contexto, resultado radicalmente distinto. Sin demo en vivo, solo comparación en pantalla.
3. **RAG (Retrieval-Augmented Generation)** — se identifica como lo que ya se construyó en la Charla 11: la IA consultando el vault antes de responder.
4. **Embeddings** — explicado con la metáfora del mapa de significados (rey/reina cerca, banco financiero/banco de parque lejos). Es la base que hace funcionar el RAG.
5. **Function calling** — se identifica como el mecanismo que había por debajo de la demo de Jira de la Charla 7.
6. **Temperature** — demo en vivo comparando una respuesta conservadora y una creativa ante el mismo prompt.
7. **Chain-of-thought** — demo con un problema de cálculo simple, resuelto mal sin "piensa paso a paso" y bien con esa instrucción.
8. **Multimodal** — demo con una imagen (gráfica o tabla) analizada por GitHub Copilot Desktop.
9. **Structured output** — demo pidiendo una tabla con columnas concretas a partir de feedback en texto libre.
10. **Context window management** — explicado con la metáfora de la mesa de trabajo que se llena. Se conecta con por qué existe el Wiki LLM de la Charla 11: para que el conocimiento persista fuera de la conversación.

**Frase añadida al cierre de este bloque:**
> *"Estos diez conceptos os dan las palancas. Pero la habilidad más importante con IA no es saber usarla. Es saber cuándo dudar del resultado."*

### Nivel 3 — El momento wow (8 min)

Bloque de mayor impacto emocional de la charla. Se vuelve al mapa y se señala, concepto a concepto, cómo la audiencia ya ha trabajado en el Nivel 3 sin saberlo:

- **Agentic workflows** → el patrón developer/reviewer de la Charla 8
- **Memory (short/long term)** → context window (corto plazo) + vault de Obsidian (largo plazo) de la Charla 11
- **Knowledge graphs** → Graphify sobre el codebase (bonus de la Charla 8); GraphRAG como RAG sobre un grafo
- **Orchestration patterns** → el patrón developer/reviewer es un Supervisor Pattern
- **Prompt injection** → se intentó semanas atrás y Copilot lo bloqueó; conocerlo y defenderse de él también es Nivel 3

**Frase de anclaje:**
> *"No estáis en el Nivel 2 mirando el Nivel 3 desde fuera. Estáis dentro."*

**Frase añadida como refuerzo:**
> *"Habéis seguido un patrón que se repite en toda la historia de la tecnología: primero accedéis, luego exploráis, luego combináis, y de repente estáis construyendo algo más complejo de lo que parecía."*

### Nivel 4 — Hacia dónde va esto (8 min)

Mirada a la frontera, con horizonte de 12–18 meses: **computer use** (la IA que maneja el ordenador como un humano), **reasoning models** (modelos que piensan antes de responder), **autonomous coding agents** (evolución del patrón developer/reviewer hacia la autonomía completa) y **AI Governance / EU AI Act** (entrada en vigor progresiva 2024–2027, clasificación de sistemas por riesgo).

**Frase añadida tras autonomous coding agents** (contrarresta el miedo al reemplazo, apoyada en el efecto Jevons):
> *"Cada vez que una tecnología ha hecho algo más barato, no se ha hecho menos — se ha hecho más. [...] No vais a tener menos trabajo. Vais a poder hacer cosas que antes ni os planteabais."*

**Frase añadida tras el AI Act** (aterriza la gobernanza en términos no técnicos):
> *"La IA puede decidir, pero no puede ser responsable. No firma. No asume riesgo. No responde legalmente. Alguien tiene que hacerlo."*

### Cierre (4 min)

Vuelta al mapa completo. Cuatro ideas para llevarse (la cuarta añadida en esta revisión):

1. El vocabulario importa — da las palancas para usar mejor la IA.
2. No están en el principio — llevan semanas en Nivel 3 sin saberlo.
3. El Nivel 4 no queda lejos — si llegaron al 3 sin darse cuenta, el 4 es cuestión de tiempo.
4. **La IA no quita el trabajo de ejecutar, da el trabajo de decidir** — cierre que conecta con la narrativa del arnés completo: decidir cómo decide la IA.

**Frase final:**
> *"Ahora cuando alguien os hable de RAG, de agentic workflows o de reasoning models, no vais a necesitar que os lo expliquen. Tenéis el mapa."*

---

## Origen de las frases añadidas

Varias frases de refuerzo de esta charla (marcadas 📌 en el guión) provienen del análisis de tres documentos que un compañero de trabajo escribió como reflexión sobre IA (mayo–junio 2026):

- **"De la línea de comandos a los sistemas invisibles"** — inspira la distinción entre corrección y plausibilidad, y la idea del "nuevo analfabetismo digital" (saber cuándo dudar del resultado).
- **"De la simplicidad a las capas"** — inspira el patrón cíclico democratización → exploración → combinación → complejidad, usado como refuerzo del Nivel 3.
- **"De tareas a sistemas de asignación"** — inspira el efecto Jevons aplicado a la IA y la idea de la responsabilidad como límite estructural de la automatización, usada para aterrizar el AI Act.

El análisis completo de alineamiento entre estos documentos y la charla está en la conversación previa con Claude; el guión con las frases integradas vive en [[guion-charla-12]].

---

## Material de referencia

- **Guión completo con tiempos y prompts de demo:** [[guion-charla-12]]
- **Prompts usados en las demos de Nivel 2:** ver sección "Prompts de demo — referencia rápida" del guión.

---

## Próxima charla

Pendiente de definir. El autor original de la serie retoma la titularidad de las charlas en septiembre.
