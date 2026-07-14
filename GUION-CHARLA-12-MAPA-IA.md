# Guión Charla 12 — El mapa de la IA: dónde estáis y adónde va esto

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|--------|-----------|--------|
| Apertura | El mapa — presentación de los niveles | 3 min |
| Nivel 1 | Repaso relámpago — lo que ya sabéis | 2 min |
| Nivel 2 | Los 10 conceptos que os faltan — con demos | 20 min |
| Nivel 3 | El momento wow — ya estáis aquí | 8 min |
| Nivel 4 | Hacia dónde va esto | 8 min |
| Cierre | El mapa completo + siguientes pasos | 4 min |

---

## Herramientas de demo

| Demo | Herramienta |
|------|-------------|
| System prompt | Copilot 365 |
| Context engineering | Copilot 365 |
| Structured output | Copilot 365 |
| Temperature | Copilot 365 |
| RAG con vault | GitHub Copilot Desktop |
| Chain-of-thought | GitHub Copilot Desktop |
| Multimodal | GitHub Copilot Desktop (pendiente confirmar) |

---

## Apertura — 3 min

Mostrar en pantalla el mapa de los cuatro niveles:

```
Nivel 1 — Fundamentos     → lo que hemos construido juntos
Nivel 2 — Intermedios     → lo que vemos hoy
Nivel 3 — Avanzados       → donde ya estáis sin saberlo
Nivel 4 — Frontera        → hacia dónde va esto
```

> *"Llevamos meses trabajando con IA. Hemos conectado Claude a Jira, hemos dado instrucciones a Copilot en el repositorio, hemos construido una wiki que recuerda el conocimiento del equipo."*
>
> *"Pero nunca os he dado el mapa. El marco que explica dónde está cada cosa y cómo se conecta todo."*
>
> *"Hoy hacemos eso. Cuatro niveles de madurez en IA. Vais a ver dónde estáis y, lo más importante, vais a descubrir que estáis más avanzados de lo que creéis."*

**Frase que debe quedar:**
> *"No hace falta saber cómo está hecho el motor para saber conducir. Pero sí ayuda saber en qué marcha estás."*

---

## Nivel 1 — Repaso relámpago — 2 min

> *"El Nivel 1 son los fundamentos. Lo que hemos construido juntos en estas semanas."*

Mostrar en pantalla:

- **SDD** — especificar qué construir antes de que la IA toque código
- **Skills** — el contexto persistente de cómo trabaja la empresa
- **Wiki LLM + OKF** — la memoria documental del equipo
- **Arnés completo** — las piezas que conectan todo

> *"Esto ya lo tenéis. No vamos a repetirlo. Lo traigo aquí porque es la base sobre la que se construye todo lo demás."*

---

## Nivel 2 — Los 10 conceptos — 20 min

> *"Diez conceptos. Dos minutos cada uno. Con ejemplos de vuestro trabajo diario."*

---

### 1. System prompt (2 min + demo)

> *"Cuando abrís Claude o Copilot, parece que la IA empieza desde cero. Pero antes de que escribáis la primera letra, alguien ya le ha dado instrucciones. Le ha dicho quién es, cómo debe comportarse, qué puede responder."*
>
> *"Eso es el system prompt. El CLAUDE.md y el copilot-instructions.md que visteis en la Charla 8 eran exactamente eso — vuestro system prompt para vuestro proyecto."*

**Demo en Copilot 365:**

```
[Sin system prompt]
Resume esta reunión: hemos hablado de plazos y el cliente no está contento.
```

```
[Con system prompt: "Eres jefe de proyecto de una consultora.
Responde siempre en formato ejecutivo con puntos de acción."]
Resume esta reunión: hemos hablado de plazos y el cliente no está contento.
```

**Frase que debe quedar:**
> *"El system prompt es la diferencia entre una IA genérica y una IA que trabaja para ti."*

---

### 2. Context engineering (2 min)

> *"Mismo prompt, diferente contexto, resultado completamente diferente. La calidad del output depende directamente de la calidad del contexto que le das."*

**En pantalla — sin demo:**

```
❌ Escribe un correo de seguimiento al cliente.
```

```
✅ Escribe un correo de seguimiento al cliente.
   Cliente: director de operaciones de un banco.
   Prometimos entregar el informe el viernes y no llegamos.
   Tono: formal pero cercano.
   Objetivo: disculparnos, dar nueva fecha (martes) y transmitir confianza.
```

**Frase que debe quedar:**
> *"Basura entra, basura sale. Contexto entra, valor sale."*

---

### 3. RAG (2 min)

> *"RAG: Retrieval-Augmented Generation. La IA busca en vuestros documentos antes de responder."*
>
> *"Esto es exactamente lo que construimos en la Charla 11. Cuando la IA respondía '¿por qué no usamos NgRx?' buscó en el vault y usó esa información. Eso es RAG."*

**Demo en GitHub Copilot Desktop — mostrar el vault:**

```
Estoy trabajando en el proyecto RCA.
¿Por qué no usamos NgRx? ¿Hay algún dead end
que deba conocer antes de tocar el sistema de estado?
```

**Frase que debe quedar:**
> *"RAG es la diferencia entre una IA que sabe mucho en general y una IA que sabe lo que necesitas en concreto."*

---

### 4. Embeddings (2 min)

> *"Los embeddings son la forma en que la IA representa el significado de las palabras como números. Por eso si buscáis 'coche' también encuentra 'automóvil' o 'vehículo'."*
>
> *"Imaginad un mapa donde cada palabra ocupa una posición según su significado. Rey y reina están cerca. Gato y perro están cerca. Banco financiero y banco del parque están lejos aunque se escriban igual."*
>
> *"Los embeddings son ese mapa. Es la razón por la que RAG funciona."*

**Frase que debe quedar:**
> *"Los embeddings son la razón por la que la IA entiende lo que queréis decir, no solo lo que escribís."*

---

### 5. Function calling (2 min)

> *"Un LLM solo puede generar texto. Pero con function calling, puede pedirle a otra herramienta que ejecute código, consulte una base de datos o llame a una API."*
>
> *"Esto es exactamente lo que pasaba en la Charla 7 cuando Claude consultaba Jira en tiempo real. Por debajo estaba usando function calling contra el servidor MCP."*

**Frase que debe quedar:**
> *"Function calling es lo que convierte a la IA de un generador de texto en un agente que actúa."*

---

### 6. Temperature (2 min + demo)

> *"La temperature controla cuánto improvisa la IA. Baja: predecible y precisa. Alta: creativa y variada — y más propensa a equivocarse."*

**Demo en Copilot 365:**

```
Sugiere un nombre para un servicio de consultoría de IA.
Sé profesional y sobrio.
```

```
Sugiere un nombre para un servicio de consultoría de IA.
Sé atrevido, sorprendente, que nadie lo haya visto antes.
```

**Frase que debe quedar:**
> *"Temperature baja para informes. Temperature alta para ideas."*

---

### 7. Chain-of-thought (2 min + demo)

> *"Si le pedís a la IA que resuelva algo complejo de golpe, a veces falla. Chain-of-thought es pedirle que piense en voz alta, paso a paso, antes de responder."*

**Demo en GitHub Copilot Desktop:**

```
Un equipo de 5 personas trabaja 8h/día. El proyecto necesita 320h.
2 están de vacaciones esta semana. ¿Cuántos días necesitan?
```

```
Un equipo de 5 personas trabaja 8h/día. El proyecto necesita 320h.
2 están de vacaciones esta semana. ¿Cuántos días necesitan?
Piensa paso a paso antes de responder.
```

**Frase que debe quedar:**
> *"Tres palabras que mejoran cualquier prompt: 'piensa paso a paso'."*

---

### 8. Multimodal (2 min + demo)

> *"Los modelos multimodales entienden texto, imágenes, audio y vídeo. Podéis darle una foto de una pizarra, un escáner de un contrato o una captura de una gráfica y pedirle que los analice."*

**Demo en GitHub Copilot Desktop — captura de pantalla:**

```
[Subir imagen de gráfica o tabla]
Analiza lo que ves y dame tres conclusiones para un jefe de proyecto.
```

> ⚠️ Pendiente confirmar que GitHub Copilot Desktop acepta imágenes en el chat.

**Frase que debe quedar:**
> *"Si podéis verlo, la IA puede analizarlo."*

---

### 9. Structured output (2 min + demo)

> *"Por defecto la IA responde en texto libre. Pero muchas veces necesitáis una tabla o un formato concreto que podáis copiar a otro sistema sin reformatear nada."*

**Demo en Copilot 365:**

```
Analiza este feedback y devuélvemelo en una tabla con tres columnas:
Problema | Severidad (Alta/Media/Baja) | Acción recomendada

Feedback: La plataforma va lenta por las mañanas, el módulo de informes
falla con más de 100 registros y el soporte tarda demasiado en responder.
```

**Frase que debe quedar:**
> *"Pídele el formato que necesitas, no el que la IA quiera darte."*

---

### 10. Context window management (2 min)

> *"La context window es la memoria de trabajo de la IA — todo lo que puede tener en cuenta a la vez. Tiene un límite. Cuando la conversación es muy larga, la IA empieza a olvidar las partes más antiguas."*
>
> *"Es como una mesa de trabajo. Si se llena, guardáis algo para sacar algo nuevo — y lo que guardáis ya no lo veis."*
>
> *"Por eso el Wiki LLM de la Charla 11 existe: para que el conocimiento persista fuera de la conversación."*

**Frase que debe quedar:**
> *"La context window es la mesa de trabajo de la IA. Mantenedla ordenada."*

---

## Nivel 3 — El momento wow — 8 min

> *"Antes de pasar al Nivel 4, necesito deciros algo."*

**Pausa. Volver al mapa en pantalla.**

> *"Mirad el Nivel 3. Creíais que estabais en el Nivel 2. Pero llevamos semanas trabajando en el Nivel 3 sin que os lo dijera."*

Ir concepto a concepto señalando en el mapa:

> *"**Agentic workflows** — Charla 8. El agente developer implementa y el reviewer verifica de forma autónoma. Eso es un agentic workflow."*
>
> *"**Memory: short term / long term** — Charla 11. La context window es la memoria a corto plazo. El vault de Obsidian es la memoria a largo plazo. Lo construisteis vosotros mismos."*
>
> *"**Knowledge graphs** — Charla 8, bonus. Graphify genera un grafo de conocimiento del codebase. GraphRAG es exactamente eso: RAG sobre un grafo de conocimiento."*
>
> *"**Orchestration patterns** — el patrón developer/reviewer es un Supervisor Pattern: un agente supervisa el trabajo del otro antes de que salga."*
>
> *"**Prompt injection** — lo intentamos hace unas semanas. Copilot lo bloqueó — saber que existe y cómo defenderse también es Nivel 3."*

**El momento:**
> *"No estáis en el Nivel 2 mirando el Nivel 3 desde fuera. Estáis dentro."*

**Frase que debe quedar:**
> *"El Nivel 3 no es algo que tengáis que alcanzar. Es algo que ya estáis haciendo."*

---

## Nivel 4 — Hacia dónde va esto — 8 min

> *"El Nivel 4 es la frontera. Lo que está pasando ahora en los laboratorios y que en 12-18 meses va a estar en vuestras herramientas del día a día."*

**Computer use:**
> *"La IA que usa el ordenador como un humano. Ve la pantalla, mueve el ratón, rellena formularios. No es ciencia ficción — está en producción hoy."*

**Reasoning models:**
> *"Modelos que piensan antes de responder. En lugar de generar la respuesta directamente, el modelo dedica tiempo a razonar sobre el problema. Para tareas complejas, la diferencia es enorme."*

**Autonomous coding agents:**
> *"Agentes que implementan features completas de forma autónoma. El developer revisa el resultado, no cada paso."*
>
> *"Lo visteis en embrión en la Charla 8 con el agente developer. Esto es ese concepto llevado hasta sus consecuencias."*

**AI Governance — EU AI Act:**
> *"Para los que gestionáis proyectos o tomáis decisiones: el AI Act europeo entró en vigor en 2024 y se aplica progresivamente hasta 2027. Clasifica los sistemas de IA por riesgo. Si vuestra empresa desarrolla o despliega IA, esto os afecta."*

**Frase que debe quedar:**
> *"El Nivel 4 no es el futuro. Es el presente de los que van un paso por delante."*

---

## Cierre — 4 min

Volver al mapa completo en pantalla:

> *"Empezamos hace semanas con prompts y contexto. Hoy tenéis el mapa completo."*

**Tres ideas para llevarse:**

> *"Primera: el vocabulario importa. Cuando entendéis qué es RAG o qué hace la temperature, usáis la IA mejor — sabéis qué palancas tocar."*
>
> *"Segunda: no estáis en el principio. Lleváis semanas trabajando en Nivel 3 sin saberlo."*
>
> *"Tercera: el Nivel 4 no os queda lejos. Si llegasteis al Nivel 3 sin daros cuenta, el Nivel 4 es cuestión de tiempo."*

**Frase final:**
> *"Ahora cuando alguien os hable de RAG, de agentic workflows o de reasoning models, no vais a necesitar que os lo expliquen. Tenéis el mapa."*

---

## Checklist antes del miércoles

### Mañana — probar demos
- [ ] System prompt en Copilot 365
- [ ] Temperature en Copilot 365
- [ ] Structured output en Copilot 365
- [ ] RAG con vault en GitHub Copilot Desktop
- [ ] Chain-of-thought en GitHub Copilot Desktop
- [ ] Multimodal en GitHub Copilot Desktop — confirmar si acepta imágenes

### Martes
- [ ] Ajustar guión según resultados
- [ ] Preparar imagen para demo multimodal
- [ ] Ensayo completo cronometrado
- [ ] Preparar el mapa visual de los 4 niveles para proyectar

### El día de la charla
- [ ] Copilot 365 abierto y listo
- [ ] GitHub Copilot Desktop abierto con el vault de RCA
- [ ] Mapa de niveles preparado para la apertura
- [ ] Prompts de demo copiados y listos para pegar

---

## Prompts de demo — referencia rápida

**System prompt (Copilot 365):**
```
[Sin system prompt]
Resume esta reunión: hemos hablado de plazos y el cliente no está contento.

[Con system prompt]
Eres jefe de proyecto de una consultora.
Responde siempre en formato ejecutivo con puntos de acción.
---
Resume esta reunión: hemos hablado de plazos y el cliente no está contento.
```

**Temperature (Copilot 365):**
```
[Conservador] Sugiere un nombre para un servicio de consultoría de IA. Sé profesional y sobrio.
[Creativo] Sugiere un nombre para un servicio de consultoría de IA. Sé atrevido y sorprendente.
```

**Structured output (Copilot 365):**
```
Analiza este feedback y devuélvemelo en una tabla con tres columnas:
Problema | Severidad (Alta/Media/Baja) | Acción recomendada

Feedback: La plataforma va lenta por las mañanas, el módulo de informes
falla con más de 100 registros y el soporte tarda demasiado en responder.
```

**RAG (GitHub Copilot Desktop):**
```
Estoy trabajando en el proyecto RCA.
¿Por qué no usamos NgRx? ¿Hay algún dead end
que deba conocer antes de tocar el sistema de estado?
```

**Chain-of-thought (GitHub Copilot Desktop):**
```
Un equipo de 5 personas trabaja 8h/día. El proyecto necesita 320h.
2 están de vacaciones esta semana. ¿Cuántos días necesitan?
Piensa paso a paso antes de responder.
```

**Multimodal (GitHub Copilot Desktop — pendiente confirmar):**
```
[Subir imagen de gráfica o tabla]
Analiza lo que ves y dame tres conclusiones para un jefe de proyecto.
```
