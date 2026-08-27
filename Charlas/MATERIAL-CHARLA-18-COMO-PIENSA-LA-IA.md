---
type: Material
title: "Material Charla 18 — Abriendo la caja: cómo piensa la IA por dentro"
description: "Guía de referencia exhaustiva de la Charla 18. Desarrolla, para quien quiera profundizar, los cuatro mecanismos internos que vimos en directo sobre el Excel de proyecto: predicción del siguiente token, embeddings (búsqueda por significado — el bloque más desarrollado), alucinación y el desplazamiento del riesgo en 2026, y la ventana de contexto. Sin código: modelos mentales, analogías, y el 'kit del lunes' con técnicas prácticas. Cierra explicando cómo los cuatro mecanismos son, en el fondo, el mismo motor."
tags: [material, charla-18, mecanismos-internos, prediccion-siguiente-token, embeddings, alucinaciones, ventana-de-contexto, busqueda-semantica, rag]
related: [prediccion-siguiente-token, embeddings, alucinaciones, context-window-management, rag, wiki-llm, temperature, model-routing]
charla: "Charla 18"
timestamp: "2026-08-26"
---

# Material Charla 18 — Abriendo la caja: cómo piensa la IA por dentro

Esto no es un resumen: es la **guía larga** para quien salió de la charla con ganas de más. Si solo quieres las cuatro ideas, están en la sección siguiente. Si quieres entender de verdad por qué la IA hace lo que hace —sobre todo los **embeddings**, que es lo que más pregunta la gente— sigue leyendo con calma. Cero código.

---

## Las cuatro preguntas (el mapa)

Toda la charla giró en torno a cuatro preguntas sobre una IA a la que le dimos un Excel de proyecto real:

1. **¿Cómo "entiende" la hoja?** → No entiende: **predice el patrón** más probable.
2. **¿Cómo agrupa cosas parecidas?** → Por **significado**, no por palabras (embeddings).
3. **¿Cuándo se lo inventa (y cuándo ya no)?** → **Alucina** — pero en 2026 el peligro se ha movido.
4. **¿Por qué "se le olvida" en chats largos?** → Su **ventana de contexto** se llena.

La idea que las cose todas, y que conviene tener de fondo mientras lees: **por dentro, la IA hace una sola cosa —predecir lo que viene después— y los otros tres comportamientos son consecuencias de esa única cosa.**

---

## Mecanismo 1 — Predice el patrón más probable

Cuando le dimos la hoja y le preguntamos "¿de qué va esto?", la dedujo sola: plan de proyecto, estimaciones PERT, responsables… sin que nadie se lo dijera. Pareció que entendía. No entiende.

Un modelo de lenguaje hace, por debajo, **una sola cosa**: predecir el **siguiente trozo de texto** (token) más probable, dado todo lo que lleva delante. Genera uno, lo añade, y vuelve a predecir el siguiente. Palabra a palabra, así construye la respuesta entera. Es un **autocompletar con esteroides**.

¿Por qué acierta tanto? Porque ha leído cantidades bestiales de texto y ha aprendido **qué continúa a qué**. No memoriza frases: aprende patrones. Ante columnas "optimista / probable / pesimista", el patrón "esto es una estimación de tres puntos" es abrumadoramente probable, así que lo completa y da en el clavo.

**La distinción que lo cambia todo:** *predecir el patrón ≠ saber la verdad.* De aquí sale casi todo lo demás.

**Para el lunes:** si funciona por patrones, tu trabajo es **darle un patrón nítido** — usa el término correcto, da un ejemplo de lo que quieres, aporta contexto. No es magia ni suerte: le estás eligiendo el patrón.

> Nota de concepto en el vault: [[prediccion-siguiente-token]].

---

## Mecanismo 2 — Busca por significado: EMBEDDINGS

Este es el que más cuesta y el que más rinde entenderlo. Vamos despacio y por capas.

### 2.1 El problema que resuelve

Imagina que buscas en la intranet "vacaciones" y la política se titula "días de asuntos propios". Un buscador **por palabras** no la encuentra: no coincide el texto. Pero tú y yo sabemos que hablan de lo mismo. Durante décadas, los ordenadores solo sabían buscar por palabra exacta. Los embeddings son lo que les enseñó a buscar **por significado**.

En la charla lo vimos con los riesgos del Excel: la IA juntó "esperando credenciales del ERP", "bloqueado por la API del proveedor" y "acceso al entorno del cliente" en un mismo grupo. **Cero palabras en común. Misma idea.** ¿Cómo?

### 2.2 La idea central: convertir significado en geometría

Un **embedding** es convertir un trozo de texto —una palabra o una frase— en una **lista de números** (un vector). Piensa en esa lista como unas **coordenadas**: como el "punto" donde vive esa frase en un mapa.

Y aquí está la magia, en una sola frase:

> **Los números están fabricados de forma que lo que significa parecido queda cerca, y lo que significa distinto queda lejos.**

Los números sueltos no significan nada. Lo que importa es la **distancia**. "Esperando credenciales del ERP" y "bloqueado por la API del proveedor" acaban con coordenadas parecidas —vecinas en el mapa— porque las dos quieren decir "dependo de alguien de fuera". El significado se ha vuelto **posición en el espacio**.

### 2.3 El ejemplo que lo hace clic (rey − hombre + mujer ≈ reina)

La prueba de que esos números capturan significado de verdad es que puedes hacer **aritmética** con ellos. El ejemplo clásico:

**coordenadas de "rey" − coordenadas de "hombre" + coordenadas de "mujer" ≈ coordenadas de "reina".**

Suena a brujería, pero es geometría. La "dirección" que separa hombre de mujer en el mapa es casi la misma que separa rey de reina, o actor de actriz. El modelo ha colocado las palabras de forma que las **relaciones de significado** se convierten en **direcciones** en el espacio. Eso no se programa a mano: emerge.

### 2.4 ¿De dónde salen esos números? (la hipótesis distribucional)

Nadie coloca las palabras a mano. El modelo las aprende leyendo, apoyándose en una idea con casi un siglo de antigüedad, que se resume así: **"sabrás lo que significa una palabra por la compañía que tiene"**.

Es decir: las palabras que aparecen en **contextos parecidos** deben significar cosas parecidas. "Coche" y "automóvil" salen en frases casi idénticas ("aparqué el ___", "arranqué el ___"), así que el modelo les da coordenadas casi iguales. De tanto leer, el significado **emerge del uso**. Ningún humano le dijo que fueran sinónimos: lo dedujo de que se usan igual.

### 2.5 Dos generaciones (por si te lo preguntan)

- **Vectores de palabra** (la generación clásica, tipo word2vec/GloVe): un número fijo por palabra, sin contexto. "Banco" tiene un único vector, dé igual si es de dinero o de sentarse. Para una frase, se promedian los de sus palabras. Funciona, pero es tosco.
- **Embeddings modernos** (los de los modelos actuales): leen la **frase entera en contexto** y producen un vector para todo el fragmento. "Banco" recibe coordenadas distintas según la frase. Son mucho mejores justo en lo nuestro: "misma idea, otras palabras". El mapa de la charla ilustra estos.

### 2.6 Cómo esto hace funcionar la búsqueda de tus documentos (RAG)

Aquí es donde el concepto deja de ser curiosidad y se vuelve la palanca de media IA útil de empresa. El patrón se llama **RAG** (búsqueda + generación) y es, paso a paso:

1. **Trocear:** se parten tus documentos en trozos (párrafos).
2. **Embeber:** cada trozo se convierte en su vector y se guarda en una "base de datos de significados" (base vectorial).
3. **Preguntar:** cuando escribes tu pregunta, tu pregunta también se convierte en un vector.
4. **Buscar por cercanía:** el sistema busca los trozos cuyo vector está **más cerca** del de tu pregunta — o sea, los que más se le parecen en significado, no en palabras.
5. **Responder con fuente:** esos trozos se le dan a la IA como fuente, y responde a partir de ellos.

Por eso preguntas "vacaciones" y te encuentra "días de asuntos propios": sus vectores están cerca. Y por eso el **Wiki LLM** que llevamos toda la serie viendo funciona. Los embeddings son el motor de búsqueda; el LLM es quien redacta la respuesta con lo encontrado.

> Notas relacionadas en el vault: [[embeddings]], [[rag]], [[wiki-llm]].

### 2.7 El mapa de la charla, explicado

El mapa que enseñamos (riesgos agrupados en islas) es una **ilustración**. Dos matices honestos:

- Los embeddings reales no tienen 2 dimensiones, sino **cientos o miles**. No caben en una hoja. Para dibujarlos se usan técnicas que "aplastan" esas cientos de dimensiones a 2 (se llaman t-SNE o UMAP), conservando lo esencial: lo que estaba cerca sigue cerca.
- Nuestro mapa está colocado a mano según el significado real de cada riesgo, para que se lea limpio en una slide. La lección es idéntica a la de un mapa computado; solo cambia que el nuestro prioriza legibilidad.

### 2.8 Usos de oficina, sin tecnicismos

- **Buscar en tus propios documentos** por lo que quieres decir, no por la palabra exacta.
- **Agrupar** respuestas de una encuesta, tickets o quejas por tema, aunque cada persona lo redacte distinto.
- **Encontrar duplicados** o casos parecidos (dos incidencias que son "la misma" con otras palabras).
- **Recomendar** ("documentos parecidos a este").

### 2.9 Límites y trampas

- **Hereda sesgos** del texto con el que se entrenó (la aritmética de significados también aprende estereotipos).
- **Depende del dominio:** un embedding general puede no captar bien jerga muy específica de tu sector.
- **El troceado importa:** si partes mal los documentos, la búsqueda empeora, por muy bueno que sea el embedding.
- **No "entiende" como tú:** sigue siendo geometría de patrones, no comprensión. Cerca en el mapa ≠ verdad garantizada.

**Para el lunes:** cuando una herramienta te deje "buscar en tus documentos" o "preguntar a tus datos", por debajo casi siempre hay embeddings. Escríbele como hablas: la gracia es precisamente que no necesitas acertar las palabras exactas.

---

## Mecanismo 3 — Alucina… ¿o ya no? El peligro se ha movido

En el ensayo intentamos, en directo, pillar a la IA inventándose una tarea del proyecto que no existe. **Y no picó.** Con la hoja delante y un modelo moderno, dijo "eso no lo veo". Esa sorpresa es la lección de 2026.

### 3.1 Qué es alucinar (y por qué es el Mecanismo 1 otra vez)

Alucinar es dar una respuesta que suena perfecta pero es falsa. No es un bug raro: es el **mismo motor de predicción**. Si le preguntas por algo que no tiene, no hay un botón interno de "no lo sé": completa con lo que **parece** que iría ahí. Predecir el patrón, cuando no hay dato, es exactamente inventar.

### 3.2 Por qué los buenos modelos ya casi no alucinan con una fuente delante

Los modelos actuales han mejorado mucho en dos cosas: **decir "no lo sé"** y **apoyarse en la fuente que les das**. Cuando tienen el Excel, el documento o la web delante, dejan de "adivinar de memoria" y leen el dato. Por eso, con fuente + buen modelo, el riesgo de invención baja muchísimo.

### 3.3 Dónde vive hoy el peligro

No es que ya no alucine. Es que se ha **mudado de sitio**. Hoy inventa sobre todo cuando:

- **No hay fuente y le pides un dato específico** (una cita exacta, una cifra de nicho, una referencia con autor y año).
- **Usas un modelo flojo o un modo con la guardia baja** (una versión pequeña, o sin acceso a la fuente).
- **Le cuelas una premisa falsa:** si preguntas "¿por qué la tarea de migración va con retraso?", das por hecho que existe, y muchos modelos siguen el hilo en vez de corregirte.
- **El tema es muy reciente o muy de nicho**, fuera de lo que "ha leído".

### 3.4 El kit del lunes (la regla de la 17, actualizada)

- **Dale siempre la fuente.** Es lo que más apaga la invención. Un dato importante → que salga de un documento, no de su memoria.
- **Vigila tus propias preguntas.** No le metas hechos sin verificar; se los traga y construye encima.
- **Sospecha de lo específico sin fuente** y de lo muy reciente. Pídele que **cite** de dónde lo saca; si no puede, desconfía.
- **Calibra según lo que cuesta el error.** No verificas igual un borrador interno que una cifra que va a un cliente.

> Nota de concepto en el vault: [[alucinaciones]].

---

## Mecanismo 4 — La ventana de contexto se llena

La IA no tiene memoria: tiene una **mesa de tamaño fijo**. Todo lo que hay en la conversación —lo que le pegaste, sus respuestas, tus preguntas— está encima de esa mesa. Eso es la **ventana de contexto**.

Cuando la mesa se llena, para meter algo nuevo **empuja lo viejo por el borde**. No lo "olvida" por despiste: es que ya no le cabe delante. Y ojo con la conexión: cuando algo se le ha caído de la mesa y le preguntas por ello, no te dice "ya no lo tengo" — **completa el patrón**, o sea, te lo puede alucinar. Los cuatro mecanismos están enlazados.

**Matiz 2026:** las ventanas de hoy son **enormes**. Con una tabla de 34 filas puede que no se le caiga nada. El efecto se nota en conversaciones **muy** largas o con mucho material pegado. Que no lo veas en una charla corta no significa que no exista: significa que la mesa era más grande que lo que pusiste encima.

**Para el lunes:**
- En conversaciones largas, **resume y reenfoca** de vez en cuando, o **empieza una nueva** con lo esencial.
- Para trabajos grandes, dale el material **como fuente** (un documento, la hoja) en vez de pegándolo en el chat: así no compite por sitio en la mesa.

> Nota de concepto en el vault: [[context-window-management]].

---

## El hilo que lo cose todo

Si te llevas una sola idea, que sea esta: **los cuatro mecanismos son el mismo motor.**

- La IA **predice el patrón más probable** (Mec. 1).
- Para saber qué es "probable", representa el **significado** como posición en un espacio — embeddings (Mec. 2).
- Cuando no tiene el dato, predice igual, y eso es **alucinar** (Mec. 3).
- Solo puede predecir sobre lo que **le cabe delante**; lo que se sale de la ventana deja de contar, y puede rellenarlo inventando (Mec. 4).

Entender esto es lo que separa a quien usa la IA a ciegas de quien la dirige. No hace falta programar. Hace falta el modelo mental.

---

## El kit del lunes (todo junto)

1. **Elige el patrón:** habla con el término correcto y da ejemplos de lo que quieres.
2. **Dale la fuente:** ancla a un documento o dato real lo que importe; así busca por significado y no inventa.
3. **Verifica lo que cuesta:** pide citas, desconfía de lo específico sin fuente, calibra según el riesgo del error.
4. **Cuida la mesa:** en lo largo, resume, reenfoca o empieza de nuevo; da el material como fuente, no pegado.
5. **Elige la herramienta:** dentro de la app cuando tenga la fuente delante (Copilot en Excel); un chatbot para razonar en abierto. (Guiño a la Charla 17.)

---

## Glosario rápido

- **Token:** el trozo mínimo de texto con el que trabaja el modelo (una palabra o un pedazo). Piensa "palabra".
- **Predicción del siguiente token:** el único motor del modelo; completar el trozo más probable, uno tras otro.
- **Embedding:** convertir texto en una lista de números (coordenadas) donde el significado parecido queda cerca.
- **Búsqueda semántica:** buscar por significado en lugar de por palabra exacta, usando embeddings.
- **RAG:** darle a la IA tus documentos como fuente (buscándolos por significado) para que responda con ellos.
- **Alucinación:** respuesta que suena bien pero es falsa; predecir el patrón cuando no hay dato.
- **Ventana de contexto:** lo que la IA puede tener "delante" a la vez; la mesa de tamaño fijo.

---

## Para profundizar

**En el vault:** [[prediccion-siguiente-token]] · [[embeddings]] · [[rag]] · [[wiki-llm]] · [[alucinaciones]] · [[context-window-management]] · [[temperature]] · [[model-routing]]

**Fuera (divulgación, sin código):**
- *The Illustrated Word2Vec*, Jay Alammar — la mejor explicación visual de los embeddings de palabra.
- 3Blue1Brown, serie sobre cómo funcionan los LLMs — visual y sin código.
- Wikipedia: "Word embedding", "Large language model" — para las definiciones formales.

---

*Material de referencia de la Charla 18 de la serie IAs-talks. Si algo no se entiende, es fallo de esta guía, no tuyo: dímelo y lo reescribo más claro.*
