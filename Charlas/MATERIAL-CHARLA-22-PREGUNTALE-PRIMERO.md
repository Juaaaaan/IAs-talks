---
type: Material
title: "Material Charla 22 — Pregúntale primero"
description: "Material post-charla 22. Charla de hábito, no de adopción: define la mentalidad IA-first (con respaldo en la distinción real AI-enabled vs AI-first) como una segunda mirada temprana — entender el problema, pensar una solución, y antes de ejecutarla preguntarle a la IA dónde puede ayudar. Incluye el criterio para decidir entre construir un agente o usar algo ya existente (PowerApps/Power Automate), y el ciclo de seis paradas (idea → especificar → construir → comprobar → publicar → mantener) aplicado con callbacks reales a charlas anteriores (16, 19, 20, 11, 8)."
tags: [material, charla-22, ia-first, habito, criterio, sdlc, callbacks]
related:
  - "[[guion-charla-22]]"
  - "[[ia-first]]"
  - "[[bdd]]"
  - "[[sdd]]"
  - "[[agente-ia]]"
  - "[[agentic-workflows]]"
  - "[[el-arnes]]"
charla: 22
estado: borrador
timestamp: "2026-10-07"
---

# Material Charla 22 — Pregúntale primero

---

## Qué vimos en la charla

### El punto de partida: no es un problema de adopción

A estas alturas de la serie, nadie necesita que le convenzan de que la IA funciona. RRHH ya la ha usado para cruzar datos de Excel. La charla anterior de un compañero, sobre Copilot y WorkIQ, ya les cambió a varios cómo montan una presentación. Casi todo el mundo le ha pedido ya un resumen, un email, o que le explique algo raro de un contrato.

El problema no es si la usáis. Es **cuándo os acordáis de usarla**.

> *"No hace falta que os convenza de que funciona. Hace falta que os acordéis de usarla."*

Esa es la diferencia entre una charla de adopción y una charla de hábito. Esta fue la segunda.

---

### El giro: qué es pensar en IA-first

El cambio de hoy, en una frase: **antes de hacerlo vosotros, preguntadle primero.**

Pero "primero" no significa apagar la cabeza. El orden correcto es:

1. Entendéis el problema y pensáis cómo lo resolveríais de manera tradicional.
2. Antes de comprometer tiempo y esfuerzo en esa solución, hacéis una segunda pasada: ¿en qué partes puede ayudar la IA? ¿qué camino puede simplificar? ¿qué ángulo no estoy viendo?
3. Decidís si seguís vosotros, sigue ella, o lo hacéis entre los dos.

La IA no sustituye el primer pensamiento ni toma la última decisión. Se incorpora **al principio de la exploración**, antes de ejecutar.

> *"La IA es la primera conversación sobre tu solución, no la última decisión."*

Esto tiene nombre: **mentalidad IA-first**. No es un concepto inventado para la charla — lleva meses circulando en medios como *Wired*, que distingue entre dos formas de relacionarse con la IA:

| AI-enabled | IA-first |
|---|---|
| Usas la IA puntualmente para una tarea suelta | La IA es el punto de partida, no un añadido al final |
| La incorporas cuando te acuerdas | La consultas por reflejo, antes de empezar |
| Un complemento a tu forma de trabajar de siempre | Redefine el primer paso de esa forma de trabajar |

Normalmente esta distinción se aplica a escala de empresa entera — cómo rediseña sus procesos y su estrategia. En la charla se bajó a escala personal: el mismo principio, aplicado a cada tarea del día a día.

**Una precisión importante, para que no se malinterprete:**

> *"IA-first no es IA-only ni IA-always."*

No significa que la IA sea siempre la solución, que haga todo el trabajo, o que decida por vosotros. Significa que, una vez entendido el problema y antes de ejecutar, comprobáis si puede aportar algo. A veces sí. Otras veces no merece la pena.

### El antes/después

Caso sencillo a propósito, para que se vea claro: mañana tenéis una reunión con un cliente nuevo.

- **Modelo tradicional:** entendéis que hace falta preparar la reunión, pensáis los objetivos, abrís un Word y escribís el guion. Esa primera reflexión es necesaria — el problema es recorrer todo el camino sin una segunda pregunta: ¿en qué puede ayudarme aquí la IA? Quizá falte un riesgo, una objeción, una pregunta que no se había considerado.
- **Modelo IA-first:** después de aclarar qué reunión es y qué resultado se busca, pero antes de redactarlo todo, se le pregunta: *"mañana tengo una reunión con un cliente nuevo sobre esto, ¿qué debería cubrir, y qué me preguntaría si estuviera en su lugar?"*. Diez segundos después hay un primer borrador, con cosas que no se habían contemplado. Y ahí se decide: seguirlo tal cual, afinarlo, o descartarlo entero.

La diferencia no está en quién acaba haciendo el trabajo — puede que el guion final se escriba enteramente a mano. La diferencia está en no pasar directo de entender el problema a ejecutar la primera solución, sin abrir antes esa exploración con IA.

**El giro mental que ayuda a interiorizarlo:** dejar de pensar en la tarea ("voy a escribir este documento") y pensar en el resultado ("quiero llegar a X") — y preguntarle primero cómo llegar. Cambia una tarea entera por una conversación.

---

### ¿Construir un agente, o ya existe algo hecho?

Parte del mismo reflejo, no una excepción: preguntar primero no significa "móntate un agente para todo". A veces la pregunta correcta no es *"¿qué agente necesito?"*, es **¿hace falta construir algo, o ya existe una herramienta que lo resuelve?**

Microsoft tiene PowerApps y Power Automate: aplicaciones y automatizaciones que se montan sin programar, pensadas para tareas estructuradas y repetitivas — aprobar un gasto, recoger datos de un formulario, mover algo de un sitio a otro. Si el problema es ese, construir un agente a medida es como contratar un arquitecto para colgar un cuadro.

¿Cuándo sí hace falta un agente — o un equipo de agentes, como el de la **Charla 19**? Cuando hay que leer, juzgar, decidir con criterio: cosas sin un camino fijo de pasos. El Analista de RFP de la 19 no podía ser un PowerApp — tenía que entender un pliego de verdad, detectar contradicciones, razonar. Eso no se arrastra con el ratón.

> *"Camino claro y pasos fijos, PowerApps. Hay que pensar y decidir en cada caso, agente."*

Y un límite más, todavía más sencillo: a veces la conclusión es que **no hace falta IA en absoluto**. Corregir una fecha, confirmar un dato conocido, responder un sí o un no — ahí meter un modelo añade más fricción que valor. IA-first también es evaluar pronto si aporta algo, y descartarla pronto cuando no lo aporta.

---

### El hilo: un ciclo que ya conocíais sin saberlo

Para que la frase no se quede en un eslogan, se repitió seis veces, en seis sitios distintos, cada uno con un ejemplo que la serie ya ha visto.

Casi todo lo que hacéis, por pequeño que sea, pasa por las mismas etapas: tenéis una idea, decidís qué queréis exactamente, lo hacéis, lo comprobáis, lo soltáis fuera, y luego hay que mantenerlo vivo.

```
Idea → Especificar → Construir → Comprobar → Publicar → Mantener
```

En el mundo del software esto tiene nombre propio, pero no es cosa exclusiva de developers: es el ciclo de un email, de una propuesta, de un evento que organizáis, de una decisión que tomáis.

---

### Las seis paradas

En cada una, la misma pregunta aplicada a un ejemplo real ya visto en la serie:

| Parada | La pregunta | El ejemplo real |
|---|---|---|
| **1. Idea** | ¿Le habéis preguntado qué forma podría tener, o dais por hecho que ya la sabíais? | El encargo de RRHH — cruzar Excel con IA empezó siendo una idea suelta, sin forma todavía |
| **2. Especificar** | Si le pidierais ayuda ahora mismo, ¿sabría la IA qué queréis de verdad, o le faltaría contexto? | **SDD** (Charla 16) — un ticket de Jira de dos frases se convirtió, sin escribir el spec a mano, en un plan completo |
| **3. Construir** | La parte de "hacerlo" — ¿la ibais a hacer entera vosotros, o le habéis dejado sitio a la IA? | El menú de **OpenCode** (Charla 20) — elegir qué motor hace el trabajo, no asumir que hay uno solo |
| **4. Comprobar** | Antes de dar vuestra tarea por terminada, ¿le habéis pedido que la revise desde otro ángulo? | El mismo spec de la 16, reinterpretado como **BDD** — contar el resultado esperado como una historia para poder comprobarlo |
| **5. Publicar** | Cuando le deis al botón final, ¿va a ser la primera vez que alguien le ha echado un segundo vistazo? | El **checkpoint humano** del Analista de RFP (Charla 19) — se para y pregunta antes de generar el Excel |
| **6. Mantener** | Dentro de tres meses, ¿va a estar anotado por qué se hizo así, o va a depender de que os acordéis? | **Wiki LLM** (Charla 11) e **instrucciones persistentes** (Charla 8) — memoria que no depende de que alguien se acuerde |

Cada parada cierra con la misma frase: **antes de hacerlo tú, pregúntale primero.**

---

### Cierre

> *"Antes de invertir esfuerzo, pregúntale primero."*
>
> *"IA-first no es IA-only ni IA-always: la IA abre opciones; vuestro criterio decide."*

Y el guiño final, para quien quiera llevarse una idea más: el arnés que la serie lleva meses montando para la IA, se puede poner también uno mismo. Primero entendéis el camino. La IA ayuda a explorarlo y a recorrerlo mejor. El criterio sigue llevando la rienda.

---

## Glosario de conceptos vistos hoy

**[[ia-first|Mentalidad IA-first]]**
Reflejo de preguntarle a la IA al principio de la exploración de una tarea — no al final, ni en lugar de pensar. Se distingue de ser simplemente *AI-enabled* (usar la IA puntualmente) en que la IA pasa a ser el punto de partida. No es IA-only ni IA-always: abre opciones, no decide.

**AI-enabled vs IA-first**
Distinción tomada de la cobertura de *Wired* y otros medios: AI-enabled es incorporar la IA como un complemento ocasional; IA-first es que sea el primer paso por reflejo. Normalmente se aplica a empresas enteras; en esta charla se bajó a escala de tarea individual.

**Criterio "construir o ya existe"**
Antes de montar un agente, preguntar si una herramienta ya resuelve el problema. Camino claro y pasos fijos (aprobar, recoger, mover) → PowerApps/Power Automate. Juicio, lectura, decisión sin pasos fijos → agente. Y, a veces, ni lo uno ni lo otro: no hace falta IA.

**[[bdd|BDD]]**
Describir el resultado esperado de algo como una historia ("dado que... cuando... entonces...") para poder comprobar si se cumple, sin necesidad de ser developer. Visto sin nombrar en la Charla 16, nombrado explícitamente en la 22.

**El ciclo de seis paradas**
Idea → Especificar → Construir → Comprobar → Publicar → Mantener. No es un ciclo de software: es el ciclo de cualquier cosa que se hace, grande o pequeña. Marco usado en esta charla para repetir la pregunta IA-first en seis momentos distintos, cada uno con un callback a una charla anterior.

---

## Tres ideas para llevarse

**1. El reflejo importa más que la herramienta.**
Nadie en la sala necesitaba aprender una herramienta nueva hoy. Todo lo citado (SDD, BDD, OpenCode, el checkpoint humano, Wiki LLM) ya se había visto. Lo nuevo era el hábito de preguntar primero, no el contenido técnico.

**2. IA-first tiene un límite explícito, y es importante decirlo en voz alta.**
No es que la IA decida todo ni que haga falta usarla siempre. Es evaluar pronto si aporta, y descartarla pronto cuando no.

**3. El mismo criterio sirve para decidir si hace falta un agente.**
"Construir o ya existe" es una aplicación directa de preguntar primero: antes de añadir complejidad (un agente a medida), comprobar si una herramienta más simple (PowerApps, Power Automate) ya resuelve el problema — o si directamente no hace falta IA.

---

## Enlaces

- Guion completo: [[guion-charla-22]]
- Concepto nuevo: [[ia-first]]
- Concepto nuevo: [[bdd]]
- Callback: [[guion-charla-16]] (SDD, especificar)
- Callback: [[guion-charla-19]] (Analista de RFP, checkpoint humano)
- Callback: [[guion-charla-20]] (OpenCode, construir)
- Callback: [[guion-charla-11]] (Wiki LLM, mantener)
- Callback: [[guion-charla-08]] (instrucciones persistentes, mantener)

---

*Charla 22 — Serie de formación interna en IA*
