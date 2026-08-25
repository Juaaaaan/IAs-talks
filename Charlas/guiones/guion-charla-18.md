---
type: Guión
title: "Guión Charla 18 — Abriendo la caja: cómo piensa la IA por dentro (con datos en la mano)"
description: "Charla transversal pero un peldaño más adentro: tras aprender a ELEGIR bien la IA (Charla 17), hoy abrimos la tapa y enseñamos cómo piensa por dentro — sin una sola línea de código. El vehículo es una demo en vivo sobre un Excel de gestión de proyecto real (plan a un año: WBS con PERT, equipo, presupuesto, timeline, KPIs y Gantt). Sobre esa hoja afloran cuatro mecanismos internos: (1) predice el patrón más probable, (2) busca por significado (embeddings), (3) alucina sin fuente — el peligro se ha movido, (4) tiene una ventana de contexto que se le llena. Cada mecanismo se cierra con un 'y por eso, cuando la uses, haz X'. Reparto deliberado de herramientas — Copilot dentro de Excel vs chatbot general — como guiño a la brújula de la Charla 17. ~50 min + preguntas."
tags: [guion, charla-18, mecanismos-internos, prediccion-siguiente-token, embeddings, alucinaciones, ventana-de-contexto, demo-excel, copilot-en-excel, transversal]
related: [alucinaciones, embeddings, rag, context-window-management, temperature, model-routing, wiki-llm]
charla: "Charla 18"
estado: "🔲 Borrador — pendiente de revisión y ensayo de demo"
timestamp: "2026-08-24"
---

# Guión Charla 18 — Abriendo la caja: cómo piensa la IA por dentro

> ⚠️ **Nota de alcance:** charla **transversal pero un peldaño más adentro**. La 17 enseñó a *elegir* bien la IA (qué herramienta, qué modelo, qué modo, cuánto verificar). Hoy contestamos el *por qué*: **cómo piensa por dentro**. No es un notebook, no es código, no es "construir IA". Es el **modelo mental** que hace que todo lo de la 17 salga mejor.
>
> **Perfil real del público (clave del diseño):** el de siempre — ~168 personas, ~98% no técnicas (HR, management, comercial) + algunos devs. Ya usan IA. El riesgo aquí NO es que sea "demasiado técnico"; es quedarse en "tareas de oficina" y perder la lección. **La misión pedagógica manda: enseñamos técnica de verdad, pero sin código.** "Predice la siguiente palabra" a un experto le parece trivial; a la sala le reordena la intuición entera.
>
> **Foco:** cuatro mecanismos internos, cada uno **visto ocurrir** sobre datos reales, no explicado en abstracto. Los datos son la linterna que ilumina la caja negra.
>
> **Formato:** **demo en vivo** sobre un Excel de proyecto (con capturas de respaldo). Cambio de registro respecto a la 17, que fue solo teoría + capturas. Un único fichero, dos herramientas.
>
> **El meta-hilo (importante):** la charla salta a propósito de **Copilot dentro de Excel** a un **chatbot general** y viceversa. Ese salto no es accidente: es un guiño vivo a la brújula de la 17 — *la misma IA se comporta distinto según dónde vive y con qué la alimentas*.
>
> **Nota sobre el Gantt / el Excel:** es **escenografía**, el gancho de apertura ("un plan de proyecto de verdad"), NO un quinto mecanismo. Que no se coma el foco de los cuatro.

---

## Estructura de tiempos

| Bloque    | Contenido                                                        | Tiempo   |
| --------- | --------------------------------------------------------------- | -------- |
| Apertura  | Gancho + el Excel en pantalla + las 4 preguntas que abriremos    | 5 min    |
| Bloque 1  | Mecanismo 1 — Predice el patrón (Copilot en Excel)              | 9 min    |
| Bloque 2  | Mecanismo 2 — Busca por significado / embeddings (Excel + mapa) | 12 min   |
| Bloque 3  | Mecanismo 3 — Alucina… ¿o ya no? El peligro se ha movido        | 9 min    |
| Bloque 4  | Mecanismo 4 — La ventana de contexto se llena (chatbot)         | 7 min    |
| Bloque 5  | Qué se lleva cada rol                                            | 3 min    |
| Cierre    | El kit del lunes + conexión con la serie                        | 5 min    |
| Preguntas | Turno abierto                                                    | 8-12 min |

**Total estimado:** ~51 min + preguntas

---

## Apertura — La caja negra sobre la mesa — 5 min

> _"La semana pasada aprendimos a ELEGIR bien la IA: qué herramienta, qué modelo, qué modo, cuánto verificar. Hoy hacemos algo distinto y, creo, más divertido: abrimos la tapa. ¿Por qué se comporta como se comporta? Porque cuando entendéis un poco cómo piensa por dentro, todo lo de la semana pasada os sale solo."_
>
> _"Y os prometo dos cosas. Una: no vais a ver ni una línea de código. Dos: os vais a ir sabiendo cosas de cómo funciona la IA que ahora mismo no sabe el 95% de la gente que la usa a diario."_

**En pantalla — el Excel (gancho):** abrir el fichero de proyecto. Enseñar la hoja **Gantt** y un par de hojas (Tareas, Resumen).

> _"Esto no es un ejemplo de juguete. Es un plan de proyecto a un año: desglose de tareas, estimaciones, equipo, presupuesto, su Gantt… lo que muchos de vosotros sufrís cada semana. Hoy se lo vamos a dar a la IA — y en vez de quedarnos en 'mira qué bien lo resume', vamos a mirar POR DENTRO cada vez que hace algo."_

**Las cuatro preguntas — mostrar ya, es el mapa de la charla (se repite en el cierre):**

| # | La pregunta | Lo que descubriremos |
|---|---|---|
| **1** | ¿Cómo "entiende" la hoja? | No entiende: **predice el patrón** más probable |
| **2** | ¿Cómo agrupa cosas parecidas? | Por **significado**, no por palabras (embeddings) |
| **3** | ¿Cuándo se lo inventa (y cuándo ya no)? | El peligro se ha movido: **alucina sin fuente**, no con ella |
| **4** | ¿Por qué "se le olvida" en chats largos? | Su **ventana de contexto** se llena |

**Frase que debe quedar:**

> _"No os pido que os creáis cómo funciona. Os lo voy a enseñar pasando, en directo, sobre este Excel."_

---

## Bloque 1 — Mecanismo 1: predice el patrón — 9 min

**Herramienta: Copilot DENTRO de Excel** (panel lateral).

> _"Primer experimento. No le voy a explicar nada de esta hoja. Ni qué es, ni qué columnas tiene. Solo se la enseño y le pregunto."_

**En pantalla — prompt en Copilot de Excel:**
> `Sin que te dé ninguna explicación, ¿de qué trata esta hoja y qué representa cada columna?`

Copilot responde: es un plan de proyecto, identifica el desglose de tareas, las estimaciones, el PERT, los responsables, el estado…

> _"Fijaos en lo que acaba de pasar. Nadie le ha dicho que 'PERT' es una estimación, ni que esa columna son responsables. Lo ha… ¿adivinado? No exactamente. Y aquí viene la idea más importante de toda la charla."_

### El "ajá": no entiende, predice

> _"Por dentro, un modelo de lenguaje hace UNA cosa, muy tonta y muy potente a la vez: predecir lo que viene después. Palabra a palabra. Ha leído cantidades gigantescas de texto — millones de hojas de proyecto entre ellas — y ha aprendido qué patrones son probables. Cuando ve una columna con 'optimista, probable, pesimista', el patrón 'esto es una estimación PERT' es abrumadoramente probable. Así que lo completa."_
>
> _"No 'sabe' lo que es un proyecto como lo sabéis vosotros. Reconoce el patrón. Es un autocompletar con esteroides. Y esto no es un defecto que le vayan a quitar en la próxima versión: es LO QUE ES."_

**La consecuencia práctica (por qué os importa):**

> _"¿Y esto para qué me sirve un lunes? Para lo siguiente: si funciona por patrones, la forma en que le habláis cambia el patrón que activa. Una hoja con columnas bien nombradas, una pregunta clara con el término correcto… le da un patrón nítido y acierta más. Una pregunta vaga le da un patrón borroso y rellena huecos. No es magia ni suerte: le estáis eligiendo el patrón."_

**Frase que debe quedar:**

> _"La IA no entiende: predice el patrón más probable. Por eso cómo le preguntáis no es un detalle — es lo que decide lo que os devuelve."_

---

## Bloque 2 — Mecanismo 2: busca por significado (embeddings) — 12 min

**Herramienta: Copilot en Excel + mapa pre-cocinado.** Este es el fotograma que se les queda grabado. **Tómate tu tiempo aquí** — es el concepto más importante que se llevan de toda la charla, así que no corras.

> _"Segundo experimento. Esta hoja tiene una columna de riesgos y notas, texto libre, escrito como lo escribiríais vosotros. Le voy a pedir algo que parece imposible sin leérselo todo entero."_

**En pantalla — prompt en Copilot de Excel:**
> `Agrupa las tareas por el tipo de riesgo que describen, aunque estén en fases distintas del proyecto.`

Copilot junta, por ejemplo, todos los riesgos de **dependencia de terceros** (esperar credenciales del ERP, esperar la API de la pasarela, esperar acceso al CRM…) aunque están en meses distintos y **redactados con palabras diferentes**.

> _"Parad un momento en esto. Yo no he buscado una palabra. En ningún riesgo pone 'dependencia de terceros'. Uno dice 'esperando credenciales', otro 'bloqueado hasta que el proveedor publique su API', otro 'acceso al entorno del cliente'. Palabras distintas, MISMA idea. Y los ha juntado. ¿Cómo lo hace? Os lo enseño con un dibujo, y es más fácil de lo que parece."_

**En pantalla — el mapa (imagen). Primero enseñar a LEERLO, antes de explicar el concepto:**

> _"Cómo se lee este mapa, tres cosas y ya. Una: cada punto es un riesgo de vuestra hoja, uno de verdad. Dos: la distancia ES el significado — dos puntos juntos quieren decir cosas parecidas; dos lejos, cosas distintas. Tres: esas islas de colores no las he agrupado yo a mano. Se agrupan solas. Cada isla es un tema que ha emergido por sí mismo: dependencias de terceros, disponibilidad del equipo, alcance poco definido…"_

### El "ajá": el significado se convierte en números, y los números en distancia

> _"Ahora, ¿qué ha hecho por dentro para conseguir esto? Una sola cosa, y quedaos con ella porque es la idea clave: ha convertido cada frase en una lista de números. Una especie de coordenada. A eso se le llama un embedding — apuntad la palabra, es de las pocas que merece la pena saberse."_
>
> _"¿Y qué tienen de especial esos números? Que están fabricados de forma que lo que significa parecido sale con números parecidos, y por tanto cae cerca en el mapa. Fijaos en las dos frases que he marcado con un círculo: 'esperando las credenciales del ERP' y 'bloqueado por la API del proveedor'. No comparten NI UNA palabra. Pero significan lo mismo — 'estoy esperando a alguien de fuera' — así que sus números se parecen y acaban pegaditas. El significado se ha convertido en distancia. Eso es un embedding funcionando."_

> _"¿Y de dónde salen esos números? Nadie los pone a mano. El modelo los ha aprendido leyendo cantidades bestiales de texto y fijándose en algo muy simple: las palabras que se usan en los mismos contextos deben significar cosas parecidas. De tanto leer, 'coche' y 'automóvil' acaban con números casi idénticos. El significado no se lo enseña nadie: emerge del uso."_

**(Opcional — la versión que impresiona, solo si el público está enganchado):**

> _"Y esto lo llevan tan lejos que se puede hacer aritmética con el significado. El ejemplo clásico: coges los números de 'rey', le restas los de 'hombre', le sumas los de 'mujer'… y caes casi encima de 'reina'. Suena a magia. Es solo geometría del significado."_

**La consecuencia práctica (conecta con toda la serie):**

> _"¿Y esto por qué os cambia el lunes? Porque es EXACTAMENTE así como la IA encuentra el documento correcto cuando le dais los papeles de vuestro equipo. Escribís 'vacaciones' y os encuentra la política que habla de 'días de asuntos propios', aunque no aparezca vuestra palabra por ningún lado. Buscar por significado en lugar de por palabra exacta es lo que hace funcionar al Wiki LLM que llevamos toda la serie viendo — y a cualquier buscador moderno."_

**Frase que debe quedar:**

> _"La IA no busca palabras, busca significados. Convierte cada texto en números donde 'parecido' quiere decir 'cerca' — y por eso os entiende aunque cambiéis las palabras, y encuentra el documento bueno aunque esté escrito de otra forma."_

> 🔎 **Reparto en/fuera de directo:** "agrupa los riesgos" es **en vivo** dentro de Excel; el **mapa 2D va pre-cocinado** (`mapa-embeddings-riesgos.png`, con guía de lectura y el recuadro «misma idea, otras palabras» ya incorporados en la imagen).
>
> 🧭 **Munición si preguntan (sobre todo devs):**
> - _"¿Es un t-SNE real?"_ → No. El mapa es una **ilustración fiel** del concepto (lleva la marca "ilustración"). Los riesgos están colocados según su significado real, pero la proyección no es la salida de un modelo. Para la lección da exactamente igual; si alguien quiere el computado de verdad, se genera aparte.
> - _"¿Esos números salen de un modelo grande?"_ → Hay dos generaciones. **Vectores de palabra**: un número fijo por palabra, sin contexto (más antiguo). **Embeddings modernos**: leen la frase entera en contexto, mucho mejores justo en esto de "misma idea, otras palabras". Lo de hoy ilustra los segundos.
> - Enlaza directo con **`rag`** y **`wiki-llm`** de la biblioteca.

---

## Bloque 3 — Mecanismo 3: alucina… ¿o ya no? El peligro se ha movido — 9 min

**Herramienta: Copilot en Excel + chatbot general.** El bloque más honesto de la charla: en 2026 la lección ha cambiado, y lo cuento tal cual me pasó preparándola.

> _"Tercer experimento. Yo venía a pillar a la IA mintiendo en directo… y no lo he conseguido. Y esa sorpresa es justo la lección de hoy. Mirad."_

### 3A — Intento engañarla con la fuente delante (y no puedo)

**En pantalla — con el Excel/tabla delante, lanzarle trampas seguidas:**
> `¿Cómo va la tarea de migración de los servidores a la nube?` · `Resume el riesgo de la tarea T40.` · `La tarea de migración a la nube va con retraso, ¿cuál es la causa más probable?`

Nada de eso existe en el plan. Y el modelo, en vez de picar, **se contiene**: dice que no lo ve, o te corrige la premisa.

> _"Fijaos: tres trampas. Una tarea que no existe, un ID que no existe, y hasta le he colado como un hecho que 'la migración va con retraso'… y no ha picado ni una. Con la fuente delante y un modelo moderno, sabe decir 'eso yo no lo tengo'. El 'botón de no lo sé' que hace dos años casi no existía, hoy los buenos modelos lo tienen mucho más."_

**El remate (real, enséñalo en pantalla):** la captura de cuando le preguntaste a la propia IA por qué no alucinaba.

> _"Y lo mejor de todo: se lo pregunté a la propia IA, y me respondió — 'tu demo ha funcionado precisamente porque no he alucinado'. Tiene razón. Ese es el titular de hoy."_

### 3B — ¿Entonces ya no alucina? Sí, pero el peligro se ha mudado

> _"Que no os quede la idea equivocada: SÍ alucina. Lo que ha cambiado es DÓNDE. El peligro se ha movido de sitio."_

**En pantalla — dónde sigue fallando hoy** (captura pre-cocinada, o en vivo si pica):
- **Sin fuente + dato específico:** pídele la cita exacta — autor, año, estudio — de una cifra de nicho. Ahí inventa referencias con soltura.
- **Modelos flojos o modos con la guardia baja:** una versión pequeña, o sin web, pica donde el bueno aguanta.
- **Premisa falsa bien colada, o temas muy recientes / de nicho.**

> _"Es el mismo mecanismo del Bloque 1: completar el patrón más probable. Lo que pasa es que darle la fuente y usar un buen modelo apaga la mayor parte. Lo que queda encendido es esto: sin fuente, modelo flojo, o premisa falsa que le cuelas tú."_

### El "ajá"

> _"El titular de 2026: con una fuente delante, un buen modelo ya no se lo inventa — sabe decir 'no lo tengo'. Alucina cuando le quitas la fuente, cuando usas un modelo con la guardia baja, o cuando le metes tú un hecho sin verificar."_

**La consecuencia práctica (la regla de la 17, actualizada):**

> _"El kit del lunes, en tres. Uno: dadle SIEMPRE la fuente — es lo que más apaga la invención. Dos: vigilad VUESTRAS propias preguntas; no le metáis hechos sin verificar, que se los traga. Tres: sospechad más de datos específicos sin fuente y de lo muy reciente. Y calibrad según lo que cuesta el error, como en la 17."_

**Frase que debe quedar:**

> _"En 2026 el peligro se ha movido: con la fuente delante, un buen modelo sabe decir 'no lo tengo'. Alucina cuando le quitas la fuente o le cuelas una premisa falsa — ahí es donde hay que mirar."_

> 🔎 **Nota de demo (importante):** este bloque ya **no depende de que el modelo pique**. La parte 3A (que se resista) es **fiable en vivo** — ensayado: con el modelo actual resiste todas las trampas de tabla. Para la 3B, si tu modelo tampoco inventa la cita, tira de **captura pre-cocinada** de un modelo flojo/sin fuente inventando, más la captura del propio mensaje de la IA reconociendo que no alucinó.

---

## Bloque 4 — Mecanismo 4: la ventana de contexto se llena — 7 min

**Herramienta: chatbot general.**

> _"Último experimento. ¿A quién le ha pasado que en una conversación larga con la IA, al final, empieza a contestar peor, se contradice, o se le olvida algo que le dijiste al principio? [manos] A todos. No es que se canse. Tiene una explicación muy concreta."_

**En pantalla — en el chatbot:** pegar las 34 tareas, tener una conversación de ida y vuelta de varios turnos, y al final preguntar por un detalle del principio:
> `De la tarea de análisis de requisitos que te pasé al principio, ¿cuál era el riesgo que mencionaba?`

Empieza a perder precisión o mezcla detalles.

> _"Ahí está el bajón. ¿Por qué?"_

### El "ajá": la IA no tiene memoria, tiene una mesa

> _"Imaginaos que la IA trabaja sobre una mesa de tamaño fijo. Todo lo que hay en la conversación — lo que le pegasteis, sus respuestas, vuestras preguntas — está encima de esa mesa. Eso es la ventana de contexto. Cuando la mesa se llena, para meter algo nuevo, empuja lo viejo por el borde. No lo 'olvida' porque se despiste: es que literalmente ya no le cabe delante."_
>
> _"Y ojo con el detalle del Bloque 3 aplicado aquí: cuando algo se le ha caído de la mesa y le preguntáis por ello… no os dice 'ya no lo tengo'. Completa el patrón. O sea, os lo puede alucinar. Los cuatro mecanismos están conectados."_

**La consecuencia práctica:**

> _"El kit: en conversaciones largas, no fiéis todo a que 'se acuerde'. Resumidle de vez en cuando lo importante, reenfocad, o empezad una conversación nueva con lo esencial. Y para trabajos grandes, dadle el material como fuente (un documento, la hoja) en vez de pegándolo en el chat — que ahí no se le cae de la mesa."_

**Frase que debe quedar:**

> _"La IA no recuerda: mantiene delante lo que le cabe. En cuanto se llena la mesa, lo viejo se cae — y puede rellenarlo inventando."_

---

## Bloque 5 — Qué se lleva cada rol — 3 min

| Rol | Qué te llevas |
|---|---|
| **HR / funcional** | El mecanismo 2 (significado) es tu amigo: la IA encuentra la política correcta aunque no uses su palabra exacta. Y el 3: todo lo que va con un dato sensible, ánclalo a la fuente |
| **Comercial** | El mecanismo 3 es tu alarma: la IA suena igual de segura acierte o mienta. Todo lo que va a cliente, verificado contra el dato real |
| **Management** | Los cuatro mecanismos son enseñables a tu equipo en dos frases cada uno. Entenderlos es lo que separa a quien usa la IA de quien la usa bien |
| **Developer** | Nada nuevo bajo el capó, pero es la mejor forma de explicárselo a un no-técnico. Robadme las metáforas (la mesa, el mapa de significados) |

**Frase que debe quedar:**

> _"No hace falta programar para entender la máquina. Y entenderla un poco es lo que hace que os devuelva el doble."_

---

## Cierre — El kit del lunes — 5 min

> _"Recojo en las cuatro preguntas del principio, ahora ya con respuesta."_
>
> _"Una: la IA no entiende, PREDICE el patrón más probable. Por eso cómo le preguntáis decide lo que os da."_
>
> _"Dos: no busca palabras, busca SIGNIFICADOS. Por eso os entiende aunque cambiéis las palabras, y encuentra el documento bueno."_
>
> _"Tres: el peligro se ha MOVIDO. Con la fuente delante ya sabe decir 'no lo tengo'; alucina sin fuente o si le cuelas una premisa falsa. Dadle la fuente y vigilad vuestras preguntas — la capa 4 de la semana pasada."_
>
> _"Cuatro: tiene una MESA de tamaño fijo. En lo largo, resumid, reenfocad o empezad de nuevo."_
>
> _"Y el círculo con la 17: la semana pasada aprendisteis a elegir la herramienta, el modelo y el modo. Hoy habéis visto POR QUÉ funciona así por dentro. Fijaos que hasta hemos cambiado de herramienta a propósito — Copilot dentro de Excel para lo que tiene la fuente delante, el chatbot para lo demás. Elegir bien y entender por dentro son la misma moneda."_

**Frase final:**

> _"La próxima vez que la IA os deslumbre o os falle, ya no será magia. Sabréis qué mecanismo está funcionando por debajo. Y eso, más que cualquier truco, es lo que os hace buenos usándola."_

---

## Guion de la demo (resumen operativo)

| # | Mecanismo | Herramienta | Acción en pantalla | En vivo / pre-cocinado |
|---|---|---|---|---|
| 1 | Predice el patrón | Copilot en Excel | "¿De qué trata esta hoja y qué es cada columna?" → la deduce | En vivo (+ captura respaldo) |
| 2 | Embeddings | Copilot en Excel + imagen | "Agrupa por tipo de riesgo" → junta significados; luego el mapa 2D | Agrupar en vivo · **mapa pre-cocinado** |
| 3 | Alucinación (el peligro se ha movido) | Excel → chatbot | Con la fuente delante RESISTE las trampas; sin fuente / premisa falsa inventa | 3A en vivo · 3B captura pre-cocinada |
| 4 | Ventana de contexto | Chatbot | Pegar 34 tareas, charlar, preguntar por el principio → pierde detalle | En vivo (+ captura respaldo) |

> **Beat opcional de apertura (fuera de ruta crítica):** "Copilot, retócame este Gantt" (p. ej. cambiar un color o resaltar una fase). Pedir un cambio sobre algo que YA existe falla menos que generarlo de cero. Si hay dudas de wifi/tiempo, se salta.

---

## Checklist antes de la charla

- [ ] **Fichero Excel listo** (`proyecto-anual-gestion.xlsx`) — 5 hojas + Gantt, fórmulas OK, plan a un año
- [ ] **Copilot en Excel operativo** — licencia Copilot premium confirmada; **probar el día antes en la máquina de la demo** (no fiarlo al directo)
- [x] **Mapa de embeddings pre-cocinado** (`mapa-embeddings-riesgos.png`) — riesgos agrupados en islas por significado, con recuadro «misma idea, otras palabras» y guía de lectura ya en la imagen
- [ ] **Chatbot general elegido** para los bloques 3 y 4 (el aprobado internamente) y sesión abierta con la tabla ya a mano
- [ ] **Bloque 3 reenfocado ("el peligro se ha movido")** — trampas de tabla listas (migración a la nube, T40, premisa falsa) para mostrar que RESISTE; captura pre-cocinada de una alucinación sin fuente; y captura del mensaje de la IA reconociendo que no alucinó
- [ ] **Capturas de respaldo** de los cuatro mecanismos por si el modelo se pone tonto ese día
- [ ] **Slide de las 4 preguntas** — se repite en apertura y cierre
- [ ] **Cuatro metáforas afinadas** — autocompletar con esteroides / mapa de significados / muy buena letra / la mesa que se llena
- [ ] **Mensaje a compañeros** avisando de que es transversal y con demo en vivo (voz de siempre)

### Si hace falta recortar a ~45 min

1. Bloque 2: enseñar el mapa pre-cocinado y explicar el agrupamiento **sin** hacerlo en vivo (~-3 min)
2. Bloque 4: contarlo con una captura en vez de la conversación larga en directo (~-3 min)
3. **Mantener intactos:** el mecanismo 1 (es la base de todo), el mapa de embeddings (es el fotograma) y la alucinación en directo (es el más útil y el que engancha con la 17)

---

## Nota de mantenimiento del vault (no es contenido de la charla)

- El **mecanismo 1 (predicción del siguiente token / "completar el patrón")** no tiene nota de concepto propia y es el más fundamental de la charla. **Candidata clara a nota nueva** en `nivel-1-fundamentos` (p. ej. `prediccion-siguiente-token.md`), usando `alucinaciones` como nota vecina — de hecho, esta charla enseña que **alucinación y predicción son el mismo mecanismo**, y las dos notas deberían enlazarse.
- Conceptos ya en biblioteca que esta charla desarrolla aplicados: **`embeddings`** (Bloque 2), **`context-window-management`** (Bloque 4), **`alucinaciones`** (Bloque 3), **`rag`** y **`wiki-llm`** (la consecuencia práctica del Bloque 2).
- **Aviso de estado:** el `index.md` sigue marcando la **Charla 17** como "guión listo, pendiente de impartir" y como "próxima". Si la 17 ya se ha dado, conviene actualizar el índice antes de cerrar la 18. **Pendiente de tu OK** — no toco nada sin que me lo digas.
