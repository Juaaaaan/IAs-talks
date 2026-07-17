---
type: Charla
title: "Charla 12 — El mapa de la IA: dónde estamos y adónde va esto"
description: "Material extenso de referencia. Desarrolla en profundidad los 10 conceptos técnicos del Nivel 2 (system prompt, context engineering, RAG, embeddings, function calling, temperature, chain-of-thought, multimodal, structured output, context window), los 5 del Nivel 3 (agentic workflows, memoria, knowledge graphs, orchestration patterns, prompt injection) y los 4 del Nivel 4 (computer use, reasoning models, autonomous coding agents, AI Governance/EU AI Act), conectando cada uno con charlas anteriores."
tags: [charla, mapa-ia, niveles-madurez, rag, embeddings, function-calling, temperature, chain-of-thought, agentic-workflows, knowledge-graphs, ai-governance, demo]
related: [arnes-completo, sdd, skills, mcp, wiki-llm, okf, guion-charla-12, charla-07-skills-mcps, charla-08-copilot-instrucciones, material-charla-11-wiki-llm]
charla: "Charla 12"
fecha: "2026-07-15"
estado: "✅ Impartida"
timestamp: "2026-07-17"
---

# Material Charla 12 — El mapa de la IA: dónde estamos y adónde va esto

---

## Qué vimos en la charla

### El problema

Después de once charlas, habíamos visto piezas sueltas: SDD, Skills, MCPs, instrucciones persistentes, Wiki LLM. Cada una funcionó como charla independiente, con su demo y su cierre. Pero nunca nos habíamos dado el mapa que conecta esas piezas entre sí ni nos habíamos dicho, con honestidad, en qué nivel de madurez estamos respecto al estado del arte.

Esto genera dos problemas simétricos. El primero es la falsa sensación de estar empezando: si hemos conectado Claude a Jira, hemos configurado instrucciones persistentes en un repositorio y hemos construido una wiki que la IA consulta sola, no estamos "empezando con IA" — estamos operando en un nivel que buena parte del mercado todavía no alcanza, y no lo sabíamos. El segundo es el efecto contrario: sin marco de referencia, es fácil sentir que la IA es un pozo sin fondo de términos inconexos (RAG, embeddings, agentic workflows...) que nunca vamos a terminar de entender.

El mapa de cuatro niveles resuelve ambos problemas a la vez: ordena el vocabulario y, de paso, revela que estamos más adelante de lo que creíamos.

> *"No hace falta saber cómo está hecho el motor para saber conducir. Pero sí ayuda saber en qué marcha estamos."*

---

### El mapa de los cuatro niveles

```
Nivel 1 — Fundamentos     → lo que hemos construido juntos
Nivel 2 — Intermedios     → lo que vemos hoy
Nivel 3 — Avanzados       → donde ya estamos sin saberlo
Nivel 4 — Frontera        → hacia dónde va esto
```

| Nivel | Qué representa | Quién suele estar aquí |
|---|---|---|
| 1 — Fundamentos | Usar la IA de forma básica, con contexto persistente propio | Cualquier equipo que haya seguido esta serie de charlas |
| 2 — Intermedios | Entender el vocabulario técnico que hay detrás de lo que ya usamos | Equipos técnicos con curiosidad, pocos lo dominan sin formación |
| 3 — Avanzados | Trabajar con sistemas agénticos, memoria persistente y orquestación sin necesariamente saber que tiene nombre técnico | Equipos que ya han construido flujos reales, aunque no se lo llamen así |
| 4 — Frontera | Lo que está en laboratorios o en fase temprana de producción | Early adopters, equipos de investigación, proveedores de IA |

La idea central de la charla es que estos niveles **no son necesariamente secuenciales en la práctica**: se puede llegar al Nivel 3 sin pasar conscientemente por el Nivel 2, simplemente por haber construido cosas reales. Es exactamente lo que nos ha pasado como equipo.

---

## Nivel 1 — Repaso relámpago

No profundizamos en este bloque durante la charla porque ya es contenido conocido, pero conviene tenerlo enlazado aquí como base:

- **[[sdd]]** — especificar qué construir antes de que la IA toque código.
- **[[skills]]** — contexto persistente sobre cómo trabajamos.
- **[[wiki-llm]] + [[okf]]** — memoria documental del equipo, ver [[material-charla-11-wiki-llm]] para el detalle completo.
- **[[arnes-completo]]** — el marco que conecta SDD, Skills, MCPs y Wiki LLM.

Este nivel es la base sobre la que se apoya todo lo demás. Sin contexto persistente (Skills) ni sin memoria documental (Wiki LLM), ninguno de los conceptos del Nivel 2 tiene mucho sentido práctico: de nada sirve saber qué es RAG si no hay un vault sobre el que hacer retrieval.

---

## Nivel 2 — Los 10 conceptos técnicos

Este es el bloque central de la charla: diez piezas de vocabulario técnico que ya estamos usando de forma indirecta a través de las herramientas corporativas, pero sin nombre. Ponerles nombre tiene un efecto práctico: una vez sabemos que existe la "temperature", podemos pedir explícitamente una respuesta más creativa o más precisa en lugar de reformular el prompt a ciegas hasta dar con el resultado que queremos.

---

### 1. System prompt

Cuando abrimos una conversación nueva con Claude o Copilot, da la sensación de que la IA empieza completamente en blanco. No es así. Antes de que escribamos la primera letra, ya existe un conjunto de instrucciones previas que definen quién es la IA en ese contexto, cómo debe comportarse y qué tipo de respuestas debe dar. A eso le llamamos **system prompt**.

El `CLAUDE.md` y el `copilot-instructions.md` que vimos en la Charla 8 son, técnicamente, la forma que adopta el system prompt cuando se aplica a un repositorio de código: en lugar de decirle a la IA "eres un asistente general", le decimos "eres un desarrollador Angular que sigue estas convenciones concretas de este proyecto".

**Demostración en Copilot 365:**

| Sin system prompt | Con system prompt |
|---|---|
| `Resume esta reunión: hemos hablado de plazos y el cliente no está contento.` | `[Eres jefe de proyecto de una consultora. Responde siempre en formato ejecutivo con puntos de acción.]` + el mismo prompt |
| Resumen genérico en prosa | Resumen estructurado en bullets accionables, con lenguaje de gestión de proyecto |

El contraste es siempre más marcado de lo que esperamos — la misma pregunta produce respuestas con un tono y una estructura completamente distintos según qué instrucciones previas existan.

> *"El system prompt es la diferencia entre una IA genérica y una IA que trabaja para nosotros."*

---

### 2. Context engineering

Si el system prompt define **quién es** la IA, el context engineering define **qué sabe** en el momento de responder. Es la disciplina de construir deliberadamente el contexto que le damos a la IA antes de pedirle algo, en lugar de confiar en que "ya lo sabrá".

| ❌ Prompt sin contexto | ✅ Prompt con contexto |
|---|---|
| `Escribe un correo de seguimiento al cliente.` | `Escribe un correo de seguimiento al cliente. Cliente: director de operaciones de un banco. Prometimos entregar el informe el viernes y no llegamos. Tono: formal pero cercano. Objetivo: disculparnos, dar nueva fecha (martes) y transmitir confianza.` |

La diferencia de calidad entre ambos resultados no es un matiz — son dos correos que ningún profesional confundiría. El primero es genérico y podría servir para cualquier situación; el segundo está listo para enviar tal cual.

> *"Basura entra, basura sale. Contexto entra, valor sale."*

Este concepto conecta directamente con el Nivel 3 (memoria) y con el propio Wiki LLM: cuanto mejor esté documentado el contexto de un proyecto o de un equipo, menos esfuerzo manual de context engineering hace falta cada vez, porque la IA puede ir a buscarlo sola.

---

### 3. RAG — Retrieval-Augmented Generation

RAG es el mecanismo por el cual la IA, antes de responder, **busca información relevante en una fuente externa** (documentos, bases de datos, un vault de Obsidian) y usa esa información para construir la respuesta, en lugar de responder únicamente con lo que "recuerda" de su entrenamiento.

Este concepto ya lo construimos en la práctica en la Charla 11: cuando le preguntamos a la IA "¿por qué no usamos NgRx?" y respondió con la razón real documentada en el vault de RCA, eso era RAG funcionando en directo, aunque en aquel momento no lo llamáramos así.

**Demostración en GitHub Copilot Desktop:**

```
Estoy trabajando en el proyecto RCA.
¿Por qué no usamos NgRx? ¿Hay algún dead end
que deba conocer antes de tocar el sistema de estado?
```

La diferencia entre una IA sin RAG y una con RAG sobre nuestro propio vault es la diferencia entre un consultor que sabe mucho de Angular en general y uno que además conoce las decisiones concretas de nuestro proyecto.

> *"RAG es la diferencia entre una IA que sabe mucho en general y una IA que sabe lo que necesitamos en concreto."*

---

### 4. Embeddings

Los embeddings son la pieza matemática que hace posible que RAG funcione, y es probablemente el concepto más abstracto de los diez, por lo que nos apoyamos en una metáfora visual.

Un embedding representa el significado de una palabra o de un fragmento de texto como un punto en un espacio de muchas dimensiones. Palabras con significados parecidos ocupan posiciones cercanas en ese espacio; palabras con significados distintos, aunque se escriban igual, quedan lejos.

> *"Imaginad un mapa donde cada palabra ocupa una posición según su significado. Rey y reina están cerca. Gato y perro están cerca. Banco financiero y banco del parque están lejos aunque se escriban igual."*

Cuando buscamos "coche" en un sistema con RAG y embeddings bien construidos, el sistema también puede encontrar documentos que hablan de "automóvil" o "vehículo", porque en el espacio de embeddings esas palabras están próximas. Esa es la razón técnica por la que RAG "entiende" la intención de una búsqueda y no solo hace coincidir palabras exactas.

> *"Los embeddings son la razón por la que la IA entiende lo que queremos decir, no solo lo que escribimos."*

---

### 5. Function calling

Un modelo de lenguaje, por sí solo, únicamente puede generar texto. No puede, de forma nativa, crear un ticket en Jira, consultar el estado de un servidor o ejecutar código. **Function calling** es el mecanismo que le permite pedirle a otro sistema que ejecute esa acción por él: el modelo decide qué herramienta necesita, con qué parámetros, y delega la ejecución.

Esto es exactamente lo que ocurría por debajo en la demo de la Charla 7, cuando Claude consultaba y creaba issues en Jira en tiempo real a través del MCP de Atlassian. La conexión MCP nos daba las herramientas disponibles; function calling es el mecanismo por el que el modelo decide usarlas.

> *"Function calling es lo que convierte a la IA de un generador de texto en un agente que actúa."*

---

### 6. Temperature

La temperature es un parámetro que controla cuánta variabilidad o "improvisación" tiene la IA al generar una respuesta. Una temperature baja produce respuestas más predecibles y conservadoras; una temperature alta produce respuestas más variadas y creativas, a costa de mayor riesgo de desviarse o de cometer errores.

**Demostración en Copilot 365**, mismo prompt con dos configuraciones distintas:

```
[Conservador] Sugiere un nombre para un servicio de consultoría de IA.
Sé profesional y sobrio.

[Creativo] Sugiere un nombre para un servicio de consultoría de IA.
Sé atrevido, sorprendente, que nadie lo haya visto antes.
```

La versión conservadora tiende a producir nombres seguros y predecibles (del estilo "Consultoría IA Soluciones"); la versión creativa arriesga con nombres poco convencionales. Ninguna configuración es "mejor" en abstracto — depende de la tarea. Para un informe financiero, la temperature baja es la correcta; para una tormenta de ideas de naming, la alta.

> *"Temperature baja para informes. Temperature alta para ideas."*

**Idea de refuerzo tras esta demo:** hay algo que estos sistemas han cambiado y que no es evidente a primera vista. Antes, cuando un sistema fallaba, lo sabíamos — error, pantalla en rojo, algo se rompía visiblemente. Ahora la IA no se rompe: nos da una respuesta que suena bien, que está bien escrita, que parece correcta, y precisamente por eso no la cuestionamos. Antes la corrección era lo normal y los errores eran visibles; ahora lo normal es que suene bien, y los errores son invisibles.

---

### 7. Chain-of-thought

Cuando le pedimos a la IA que resuelva algo con varios pasos lógicos de golpe, a veces comete errores que un humano no cometería porque salta directamente a una respuesta sin descomponer el problema. **Chain-of-thought** es la técnica de pedirle explícitamente que razone paso a paso antes de dar la respuesta final.

**Demostración en GitHub Copilot Desktop:**

```
[Sin chain-of-thought]
Un equipo de 5 personas trabaja 8h/día. El proyecto necesita 320h.
2 están de vacaciones esta semana. ¿Cuántos días necesitan?

[Con chain-of-thought]
Un equipo de 5 personas trabaja 8h/día. El proyecto necesita 320h.
2 están de vacaciones esta semana. ¿Cuántos días necesitan?
Piensa paso a paso antes de responder.
```

En la primera versión es habitual que el modelo se equivoque, calculando la capacidad con los 5 miembros del equipo en lugar de los 3 disponibles esa semana. Con la instrucción "piensa paso a paso", el modelo descompone el problema explícitamente (capacidad diaria real, horas necesarias, división) y llega a la respuesta correcta con mucha más fiabilidad.

> *"Tres palabras que mejoran cualquier prompt: 'piensa paso a paso'."*

---

### 8. Multimodal

Los modelos multimodales no solo procesan texto: entienden también imágenes, y en algunos casos audio y vídeo. Esto significa que podemos darle una foto de una pizarra tras una reunión, el escaneo de un contrato o la captura de pantalla de una gráfica, y pedirle que la analice como si fuera texto.

**Demostración en GitHub Copilot Desktop:**

```
[Subir imagen de gráfica o tabla]
Analiza lo que ves y dame tres conclusiones para un jefe de proyecto.
```

Esta capacidad elimina un paso manual muy habitual: ya no hace falta transcribir a texto lo que hay en una imagen para poder trabajar con ello. El modelo lee directamente la imagen y razona sobre su contenido.

> *"Si podemos verlo, la IA puede analizarlo."*

---

### 9. Structured output

Por defecto, una IA conversacional responde en texto libre, en forma de prosa. Muchas veces, sin embargo, lo que necesitamos es un formato concreto — una tabla, un JSON, una lista con columnas fijas — que podamos copiar directamente a otro sistema sin tener que reformatear nada a mano. Eso es **structured output**: pedirle explícitamente a la IA el formato de salida que necesitamos.

**Demostración en Copilot 365:**

```
Analiza este feedback y devuélvemelo en una tabla con tres columnas:
Problema | Severidad (Alta/Media/Baja) | Acción recomendada

Feedback: La plataforma va lenta por las mañanas, el módulo de informes
falla con más de 100 registros y el soporte tarda demasiado en responder.
```

El resultado es una tabla ya lista para pegar en un documento de seguimiento o en una hoja de cálculo, sin necesidad de reescribir nada.

> *"Pídele el formato que necesitas, no el que la IA quiera darte."*

---

### 10. Context window management

La **context window** es la cantidad de información que la IA puede tener en cuenta simultáneamente en una conversación — su "memoria de trabajo". Tiene un límite finito. Cuando una conversación se alarga mucho, en algún momento la IA empieza a perder de vista las partes más antiguas de esa misma conversación.

> *"Es como una mesa de trabajo. Si se llena, guardamos algo para sacar algo nuevo — y lo que guardamos ya no lo vemos."*

Este concepto es la razón técnica por la que existe el Wiki LLM presentado en la Charla 11: si el conocimiento importante solo vive dentro de una conversación, desaparece de la vista de la IA en cuanto la conversación crece lo suficiente. Sacar ese conocimiento a ficheros persistentes fuera de la context window (el vault de Obsidian) es lo que permite que sobreviva más allá de una sola sesión.

> *"La context window es la mesa de trabajo de la IA. Mantengámosla ordenada."*

**Idea de cierre de este bloque:** estos diez conceptos nos dan las palancas para usar mejor la IA. Pero la habilidad más importante no es saber usarla — es saber cuándo dudar del resultado. Cualquiera puede escribir un prompt. No cualquiera sabe detectar cuándo la respuesta que ha recibido no es de fiar.

---

## Nivel 3 — El momento wow: ya estamos aquí

Este es el bloque de mayor impacto de toda la charla, porque no introduce contenido nuevo: revela que llevamos semanas operando en el Nivel 3 sin que nadie nos lo dijera. Recorremos el mapa concepto a concepto, señalando en qué charla anterior ya ocurrió cada uno de estos conceptos en la práctica.

### Agentic workflows

Un **agentic workflow** es un flujo de trabajo en el que uno o varios agentes de IA ejecutan una secuencia de tareas de forma autónoma, tomando decisiones intermedias, sin que un humano supervise cada paso individual.

En la Charla 8 construimos exactamente esto: un agente **developer** implementaba código y un agente **reviewer** verificaba ese trabajo de forma autónoma, sin intervención humana en cada paso intermedio. Eso, con nombre técnico, es un agentic workflow.

### Memory: short term / long term

Los sistemas con memoria distinguen entre memoria a corto plazo (lo que cabe dentro de la conversación actual, es decir, la context window del Nivel 2) y memoria a largo plazo (información que persiste más allá de una sola sesión, normalmente en algún almacenamiento externo).

El vault de Obsidian que construimos en la Charla 11 es, literalmente, nuestra memoria a largo plazo como equipo. Y lo construimos nosotros mismos, sin saber que estábamos implementando un concepto que en el sector se llama "long-term memory" en sistemas de IA.

### Knowledge graphs

Un knowledge graph es una representación del conocimiento en forma de nodos (conceptos, entidades) conectados por relaciones explícitas, que un agente puede recorrer para entender cómo se relacionan las piezas de información entre sí, no solo qué dice cada pieza por separado.

Graphify, la herramienta que usamos como bonus en la Charla 8 para generar un grafo de conocimiento del codebase de RCA, hace exactamente esto sobre código. **GraphRAG** —mencionado en círculos técnicos como técnica avanzada— no es más que RAG aplicado sobre un grafo de conocimiento en lugar de sobre documentos sueltos: la recuperación de información tiene en cuenta las relaciones entre los datos, no solo su similitud textual.

### Orchestration patterns

Cuando varios agentes o sistemas colaboran en una tarea, existen patrones conocidos de cómo se coordinan entre sí. Uno de los más comunes es el **Supervisor Pattern**: un agente supervisa y valida el trabajo de otro antes de que el resultado se considere terminado.

El patrón developer/reviewer que construimos en la Charla 8 es, técnicamente, un Supervisor Pattern: el reviewer actúa como supervisor del trabajo del developer antes de dar el resultado por bueno.

### Prompt injection

La prompt injection es una técnica de ataque en la que se intenta manipular el comportamiento de un sistema de IA insertando instrucciones maliciosas dentro de contenido que, en teoría, el sistema solo debería tratar como datos a procesar, no como órdenes a seguir.

Semanas atrás probamos exactamente este tipo de ataque contra Copilot en un entorno de prueba, y el sistema lo bloqueó correctamente. Saber que este riesgo existe, entender cómo funciona y confirmar que nuestras herramientas corporativas tienen defensas frente a él, también es contenido de Nivel 3 — no hace falta ser capaz de ejecutar el ataque para operar con criterio sobre este riesgo.

---

**El momento clave de este bloque:**

> *"No estamos en el Nivel 2 mirando el Nivel 3 desde fuera. Estamos dentro."*

> *"El Nivel 3 no es algo que tengamos que alcanzar. Es algo que ya estamos haciendo."*

Refuerzo adicional: hay un patrón que se repite en toda la historia de la tecnología y que hemos seguido sin planificarlo — primero accedemos a una capacidad nueva, luego la exploramos, luego la combinamos con otras capacidades, y de repente estamos construyendo algo bastante más complejo de lo que parecía al principio. Eso es exactamente lo que ha ocurrido a lo largo de estas doce charlas: de un prompt suelto en la Charla 6 a un sistema con memoria persistente, orquestación de agentes y defensas frente a ataques en la Charla 11.

---

## Nivel 4 — Hacia dónde va esto

El último bloque mira hacia la frontera: lo que hoy está en fase de laboratorio o de adopción muy temprana, y que en un horizonte de 12 a 18 meses es razonable esperar que llegue a nuestras herramientas de uso diario.

### Computer use

Los sistemas de "computer use" son modelos capaces de manejar un ordenador de la misma forma que lo haría una persona: ven la pantalla, mueven el cursor, hacen clic, rellenan formularios, navegan entre aplicaciones. No se trata de una integración específica con una API concreta, sino de la capacidad genérica de operar cualquier interfaz visual pensada originalmente para humanos.

> *"No es ciencia ficción — está en producción hoy."*

### Reasoning models

Los modelos de razonamiento dedican un paso explícito de "pensar" antes de generar la respuesta final, de forma similar (aunque a mucha mayor escala y de forma más sistemática) al chain-of-thought que vimos en el Nivel 2. En lugar de generar la respuesta directamente token a token, el modelo invierte tiempo de cómputo adicional en explorar el problema antes de comprometerse con una salida. Para tareas complejas —matemáticas, razonamiento lógico en varios pasos, depuración de código difícil— la diferencia de calidad frente a un modelo que responde directamente es considerable.

### Autonomous coding agents

Son agentes capaces de implementar funcionalidades completas de software de forma autónoma, desde la interpretación de un requisito hasta el código funcionando, con el desarrollador revisando el resultado final en lugar de supervisar cada paso intermedio del proceso.

El patrón developer/reviewer que vimos en embrión en la Charla 8 es precisamente la semilla de este concepto llevado a sus últimas consecuencias: cuanta más autonomía y fiabilidad gane el agente developer, menos supervisión paso a paso hace falta, y más se acerca ese flujo de trabajo a un autonomous coding agent en el sentido estricto del término.

**Idea de contexto tras este punto:** existe la creencia extendida de que la IA va a reducir la cantidad de trabajo disponible. Pero, históricamente, cada vez que una tecnología ha abaratado significativamente el coste de hacer algo, el resultado no ha sido menos actividad, sino más: cuando el correo electrónico eliminó el coste de enviar una carta, no enviamos menos mensajes — enviamos órdenes de magnitud más. Es razonable esperar un efecto similar con la IA: no necesariamente menos trabajo, sino la posibilidad de abordar cosas que hasta ahora nos parecían demasiado caras o lentas como para planteárnoslas.

### AI Governance — EU AI Act

El **Reglamento europeo de Inteligencia Artificial (EU AI Act)** entró en vigor en 2024 y se aplica de forma progresiva hasta 2027. Clasifica los sistemas de IA por nivel de riesgo (inaceptable, alto, limitado, mínimo) e impone obligaciones distintas según esa clasificación. Cualquier empresa que desarrolle o despliegue sistemas de IA dentro de la Unión Europea está afectada, con requisitos que van desde la simple transparencia hasta auditorías y evaluaciones de conformidad para los sistemas de mayor riesgo.

**Por qué importa esto en términos prácticos:** la IA puede decidir, pero no puede ser responsable de esa decisión. No firma contratos, no asume riesgo legal, no responde ante un cliente o un regulador. Alguien tiene que hacerlo, y ese alguien somos nosotros o nuestra empresa. El AI Act no existe porque la IA sea intrínsecamente peligrosa — existe porque, cuando el resultado de un sistema de IA no es correcto o causa un daño, tiene que haber alguien identificable que responda por ello.

> *"El Nivel 4 no es el futuro. Es el presente de los que van un paso por delante."*

---

## Cierre

Cuatro ideas para llevarnos de la charla:

1. **El vocabulario importa.** Entender qué es RAG o qué hace la temperature no es un ejercicio académico — nos permite usar la IA con más precisión, sabiendo exactamente qué palanca tocar para el resultado que necesitamos.
2. **No estamos en el principio.** Llevamos semanas operando en Nivel 3 sin saberlo, simplemente por haber construido cosas reales a lo largo de estas charlas.
3. **El Nivel 4 no nos queda lejos.** Si llegamos al Nivel 3 sin darnos cuenta, alcanzar el Nivel 4 es más una cuestión de tiempo que de un salto extraordinario.
4. **La IA no nos quita el trabajo de ejecutar — nos da el trabajo de decidir.** Ya no se trata tanto de hacer las cosas nosotros mismos como de saber qué le damos a la IA, cuándo confiamos en su resultado y cuándo la corregimos. Decidir cómo decide la IA es, en esencia, el arnés completo del que hemos hablado en toda esta serie de charlas.

> *"Ahora cuando alguien nos hable de RAG, de agentic workflows o de reasoning models, no vamos a necesitar que nos lo expliquen. Tenemos el mapa."*

---

## Dónde seguir profundizando

1. **Los conceptos del Nivel 2** ya los estamos usando de forma indirecta a través de Copilot 365 y GitHub Copilot Desktop — la próxima vez que usemos cualquiera de estas herramientas, merece la pena nombrar explícitamente qué concepto estamos aplicando (¿estoy dando contexto suficiente? ¿necesito bajar la temperature para este informe? ¿le estoy pidiendo que piense paso a paso?).
2. **El vault de Obsidian de la Charla 11** ([[material-charla-11-wiki-llm]]) es la base sobre la que se apoyan RAG, embeddings y memoria a largo plazo — cuanto más completo lo mantengamos, mejor funcionan estos conceptos en la práctica.
3. **El patrón developer/reviewer de la Charla 8** es nuestro punto de partida real hacia agentic workflows más sofisticados y, eventualmente, hacia autonomous coding agents.

---

## Recursos

- Guión completo de la charla, con tiempos y prompts de demo: [[guion-charla-12]]
- Material de la Charla 11 (Wiki LLM), referenciado varias veces en este documento: [[material-charla-11-wiki-llm]]
- Reglamento europeo de IA (EU AI Act) — texto oficial y cronograma de aplicación: [artificialintelligenceact.eu](https://artificialintelligenceact.eu)
- GitHub Copilot Desktop: disponible a través de nuestra licencia corporativa de GitHub Copilot
- Copilot 365: disponible a través de nuestra licencia corporativa de Microsoft 365
