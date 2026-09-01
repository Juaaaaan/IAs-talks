---
type: Guion
title: "Guion Charla 19 (parte 1) — De responder a actuar: varios agentes que colaboran en Copilot Studio"
description: "Guion de la Charla 19 parte 1. Recorrido guiado (sin reconstruir en vivo) del agente multiagente 'Analista de RFP' construido en Copilot Studio: orquestador + 3 agentes hijo + flujo de Power Automate que vuelca requisitos a Excel, con checkpoint humano. 45-50 min, audiencia 98% no técnica."
tags: [guion, charla-19, copilot-studio, agentes, multiagente, orquestacion, power-automate, rfp, nivel-4]
related: [charla-13-copilot-studio-metricas, charla-18-como-piensa-la-ia, copilot-studio, agente-ia, agentic-workflows, power-automate]
charla: 19
estado: listo-para-impartir
timestamp: "2026-09-01"
---

# Guion — Charla 19 (parte 1)
## De responder a actuar: varios agentes que colaboran

**Duración objetivo:** 45-50 min
**Formato:** recorrido guiado. NO se reconstruye nada en vivo. Se enseña el agente ya montado y se para en cada punto reseñable.
**Audiencia:** ~168 personas, 98% no técnica (RRHH, dirección, comercial).
**Demo:** agente **Analista de RFP** (Copilot Studio) analizando el pliego sintético de la academia de baile Compás.

> **Frase-tesis de la charla (repetir 2-3 veces):**
> *"En la charla 13 construimos un agente que **respondía**. Hoy vais a ver varios agentes que **trabajan juntos** para resolver algo, y que al final **te dejan a ti la última palabra**."*

---

## CHECKLIST PREVIO (hacer ANTES de empezar)

- [ ] Pliego de Compás **en PDF** abierto y a mano (NO markdown — no lo lee bien).
- [ ] Agente **Analista de RFP** abierto en el navegador, en la pestaña Información general.
- [ ] **Grabación de respaldo** de la demo funcionando (ver nota de riesgo abajo).
- [ ] `Entregable-RFP.xlsx` en OneDrive **vacío** (borrar filas de pruebas anteriores) y abierto en otra pestaña.
- [ ] Pestañas del navegador ordenadas: Información general → Agentes → Herramientas → panel Test.
- [ ] Excel visible en pantalla dividida o segunda pestaña rápida de alcanzar.
- [ ] Silenciar notificaciones de Teams/Outlook (van a compartir pantalla).

> **NOTA DE RIESGO (decisión tuya):** la demo en vivo funciona, pero depende de red y de que el modelo construya bien el JSON. **Recomendación fuerte: lleva grabada la ejecución completa que ya te funcionó** y nárrala por encima. Si prefieres vivo, ten la grabación como red de seguridad y lánzala sin tocar nada más que el prompt. El resto de la charla (paradas 1-4) es 100% estática y sin riesgo.

---

## BLOQUE 0 — Enganche (0:00 – 0:04) · 4 min

**Objetivo:** conectar con la 13 y con la 18, y plantar la pregunta.

Arranque en frío, sin pantalla todavía:

> "Hace unas semanas, en la charla 13, montamos delante de vosotros un agente en Copilot Studio. Le conectamos el handbook de la empresa y respondía preguntas de gente nueva. Y dijimos una cosa importante: cuando no sabía algo, **lo decía**, en vez de inventárselo."

> "Ese agente **respondía**. Sabía cosas. Pero no **hacía** nada — no cambiaba un fichero, no rellenaba un Excel, no tomaba una decisión. Hoy vamos a dar el salto siguiente."

**Frase ancla 🔑:**
> *"Un agente que responde es un buen bibliotecario. Hoy vais a ver un equipo de agentes que además hace el trabajo."*

Plantea la pregunta que estructura toda la charla:
> "¿Qué pasa cuando un problema es demasiado grande para un solo agente? ¿Cuando hay que leer, luego juzgar, luego calcular, y encima que alguien humano dé el visto bueno antes de cerrar? Eso es lo que vamos a ver, con un caso real de negocio."

Presenta el caso SIN tecnicismos:
> "Imaginad que llega un pliego de licitación — una RFP, un documento de 8 páginas donde un cliente pide una propuesta. Alguien tiene que leérselo entero, sacar qué te están pidiendo, detectar dónde están las trampas, y estimar cuánto trabajo es. Es tedioso, es fácil que se te escape algo, y lo hace gente cara. Vamos a montar un equipo de IA que lo haga… y os voy a enseñar por dentro cómo está hecho."

---

## BLOQUE 1 — Chatbot → Agente → Equipo de agentes (0:04 – 0:10) · 6 min

**Objetivo:** dar el marco conceptual antes de tocar pantalla. Denso pero sin jerga.

Recupera la escalera de la 13 y añade el peldaño nuevo:

1. **Chatbot clásico** — sigue un guión predefinido. Si tu pregunta no encaja en un camino, se rompe y te manda en bucles. *(guiño: "todos hemos sufrido el del banco")*.
2. **Agente** — no sigue guión: **razona**. Entiende, busca, responde adaptándose. Y reconoce lo que no sabe. *(esto es lo de la 13)*.
3. **Equipo de agentes (hoy)** — varios agentes, **cada uno especialista en una cosa**, coordinados por uno que reparte el trabajo. Como un equipo humano.

**Frase ancla 🔑:**
> *"No le he pedido a una IA que lo haga todo. He montado un equipo pequeño donde cada uno hace una sola cosa y la hace bien. Exactamente como organizarías a personas."*

La analogía que ancla todo el resto (dila despacio, es la columna vertebral):
> "Pensadlo como una asesoría. Hay **un jefe de proyecto** que recibe el encargo y reparte. Hay un **analista** que lee el pliego y saca la lista de lo que piden. Hay un **experto en riesgos** que busca las trampas. Y hay alguien que **estima** cuánto costará. El jefe no hace el trabajo: **coordina** y junta las piezas. Eso es, literalmente, lo que habéis venido a ver hoy en una pantalla."

Cierre del bloque, enlazando con la 18:
> "Y hay una cosa que aprendimos hace dos semanas, cuando abrimos la caja de cómo piensa la IA: no hay que fiarse a ciegas. Así que este equipo, antes de dar nada por bueno, **para y te pregunta**. Guardad esa idea, es el momento más importante del día."

---

## BLOQUE 2 — Parada 1: El cerebro del coordinador (0:10 – 0:17) · 7 min

**PANTALLA:** Analista de RFP → Información general → Instrucciones.

**Reseñable #1 — Un agente es un rol que se define POR ESCRITO.**
> "Esto no es código. Es un texto donde le explico al agente quién es y qué hace, igual que se lo explicarías a una persona nueva en su primer día."

Lee en alto una frase de las instrucciones del padre y subráyala:
> "Fijaos en lo que le he escrito: *'Tu función NO es analizar tú el pliego, sino repartir el trabajo entre tus especialistas.'* Le estoy diciendo que sea jefe, no que sea currante. Y se comporta como tal."

**Reseñable #2 — Las secciones de la instrucción.**
Enseña que las instrucciones están ordenadas: directrices generales, habilidades (el orden en que llama a los especialistas), manejo de errores, ejemplos, cierre.
> "Le he dado hasta ejemplos de cómo debería responder. A la IA, un ejemplo concreto le vale más que mil instrucciones abstractas — esto lo vimos en la charla del prompting."

**Reseñable #3 — La regla de oro anti-invención.**
Señala la línea de "nunca inventes un requisito que no esté en el pliego; si algo no está claro, márcalo como duda".
> "¿Os acordáis de la 18? El peligro de la IA es cuando rellena huecos inventando. Aquí se lo prohíbo por escrito: si no está en el documento, no te lo inventes, márcalo como duda. Esto es el arnés — le pongo límites de comportamiento."

**Frase ancla 🔑:**
> *"Programar esto no ha sido escribir código. Ha sido escribir bien un encargo."*

---

## BLOQUE 3 — Parada 2: La sala de expertos (0:17 – 0:27) · 10 min

**PANTALLA:** pestaña **Agentes** → mostrar los tres hijos.

Este es el bloque conceptual más potente. Ir despacio.

**Reseñable #4 — Cada agente hace UNA cosa (y sabe qué NO hace).**
Abre los tres uno a uno:
- **Extractor de requisitos** — solo lee y saca la lista. No juzga, no estima.
- **Detector de riesgos** — solo busca trampas, ambigüedades, contradicciones, huecos. No extrae.
- **Estimador de tareas** — solo estima esfuerzo. No lee ni juzga.

> "¿Por qué separarlos, si un solo agente 'podría' hacerlo todo? Por lo mismo que en una empresa no le pides a una sola persona que sea contable, abogado y comercial a la vez. **Especializar mejora la calidad.** Cada uno tiene la cabeza en una sola tarea."

**Reseñable #5 — EL DETALLE QUE VUELA CABEZAS: cómo decide el jefe a quién llamar.**
Abre la **descripción** de un hijo (ej. el Detector).
> "Mirad bien esto, porque es lo más sorprendente de todo. ¿Cómo sabe el coordinador a quién llamar? **No hay ninguna programación, ningún 'si pasa esto, llama a aquel'.** Simplemente cada especialista tiene escrito en lenguaje normal *'úsame para detectar riesgos'*. Y el coordinador lo **lee** y decide. La coordinación se hace con **palabras**, no con código."

**Frase ancla 🔑:**
> *"El pegamento que une a estos agentes no es código. Es lenguaje. Se entienden leyéndose la descripción unos a otros."*

**Reseñable #6 — "No responder": por qué el trabajo vuelve al jefe.**
Enseña el ajuste de finalización de un hijo.
> "Cada especialista, cuando termina, no le habla al usuario directamente. Le devuelve su parte **al coordinador**. Por eso al final veis UN informe único y ordenado, no tres agentes hablando a la vez y pisándose. El jefe recoge las tres piezas y las presenta juntas."

---

## BLOQUE 4 — Parada 3 y 4: El cerebro y las manos (0:27 – 0:33) · 6 min

**PANTALLA:** Información general (modelo) → luego Herramientas.

**Reseñable #7 — Se le puede cambiar el cerebro (guiño charla 17).**
Señala el selector de modelo (GPT-5.5).
> "¿Os acordáis de la charla de 'elegir la IA'? Aquí se ve literal: puedo elegir qué modelo mueve a este agente, como quien elige el motor de un coche. He puesto uno potente y estable, no un experimental, porque esto va en serio."

**Reseñable #8 — EL SALTO DE LA CHARLA: de responder a ACTUAR.**
Cambia a la pestaña **Herramientas** y enseña "Requisitos a Excel".
> "Y aquí está la diferencia con el agente de la charla 13. Aquel **respondía** — sabía cosas y te las contaba. Este, además, tiene **manos**: puede coger el resultado y **escribirlo en un Excel de verdad**, en vuestro OneDrive, un fichero que abrís mañana. Ha pasado de saber a hacer."

**Frase ancla 🔑:**
> *"Un agente que responde te ahorra buscar. Un agente que actúa te ahorra el trabajo."*

Explica sin tecnicismo qué hay debajo:
> "Por debajo hay una pequeña automatización — lo que en Microsoft se llama Power Automate — que coge la lista de requisitos y la vuelca fila a fila. No hace falta que entendáis cómo; lo importante es la idea: **el agente piensa, y una herramienta ejecuta.** El agente no hace las cuentas de memoria, que es donde se equivocaría — le encarga el trabajo mecánico a la herramienta que lo hace bien."

*(Este es el eco directo de la 18: la IA no cuenta celdas de cabeza, delega lo determinista.)*

---

## BLOQUE 5 — Parada 5: LA DEMO (0:33 – 0:44) · 11 min

**PANTALLA:** panel Test (o grabación). Pliego de Compás en PDF.

**Momento 0 — Lanzar.**
Adjunta el PDF, escribe: *"Analízame este pliego."*
> "Le paso el pliego de una academia de baile que quiere un sistema de gestión. 8 páginas. Miradlo trabajar."

Mientras procesa, narra la traza:
> "¿Veis? Está llamando al Extractor… ahora al Detector… El coordinador está repartiendo, como dijimos."

**Momento 1 — La trampa de las fechas. (WOW #1)**
Cuando aparezca el riesgo de fechas, PARA y subráyalo:
> "Mirad esto. El agente ha detectado que en el pliego **la fecha de decisión es ANTERIOR a la fecha de entrega de propuestas**. Deciden antes de recibir lo que van a juzgar. Es imposible. Yo metí esa trampa a propósito en el documento — y **la ha cazado**. No ha copiado el texto: lo ha **entendido** y ha visto que se contradice."

**Frase ancla 🔑:**
> *"No ha leído el pliego. Lo ha comprendido. Por eso ve una contradicción que a un humano cansado, a las 7 de la tarde, se le escapa."*

**Momento 2 — El requisito escondido. (WOW #2)**
> "Otra trampa: en el apartado de 'lo que queda fuera del proyecto', escondí una frase que dice que la segunda sede **sí** hay que preverla. Un descuido clásico que te cambia el presupuesto. El agente lo ha **rescatado** y lo ha puesto como requisito. Leyó la letra pequeña."

**Momento 3 — EL CHECKPOINT HUMANO. (el corazón)**
Cuando el agente pregunte *"¿quieres corregir algo antes de generar el Excel?"*, PARA del todo:
> "Y aquí está el momento más importante de toda la charla. El agente **no ha generado nada todavía**. Ha hecho el análisis, me ha enseñado lo que encontró, y **se ha parado a preguntarme**. No cierra a mis espaldas. La decisión final es mía."

> "Esto es lo que aprendimos en la 18 hecho práctica: la IA hace el trabajo pesado, te enseña lo dudoso, y **tú decides**. No es un piloto automático. Es un copiloto que te pasa el control en el momento clave."

**Frase ancla 🔑:**
> *"La IA que da miedo es la que actúa sola. Esta, antes de tocar nada, levanta la mano y te pregunta."*

**Momento 4 — Corregir en vivo (opcional, muy potente).**
Corrige algo que el agente asumió (ej. "no, contemplad app móvil nativa"):
> "Y puedo corregirle en lenguaje normal, sin tocar ninguna configuración. Le digo lo que falta y rehace. Manda el humano."

Confirma: *"Sí, genéralo."*

**Momento 5 — El Excel apareciendo. (cierre tangible)**
Cambia a la pestaña del Excel, refresca, enseña las filas escritas.
> "Y ahí está. Los requisitos, en un Excel de verdad, en OneDrive. Esto no es una demo de laboratorio que se queda en la pantalla: acaba en un fichero que RRHH, comercial o quien sea abre mañana y usa."

---

## BLOQUE 6 — Cierre: qué os lleváis (0:44 – 0:50) · 6 min

**PANTALLA:** apagada o slide final simple.

**Las tres ideas para llevarse:**

**1. Un agente ya no solo responde: puede hacer el trabajo.**
> "El salto de hoy respecto a la 13: de un agente que sabe cosas a un equipo que las hace y las deja escritas donde trabajáis."

**2. Coordinar agentes se hace con lenguaje, no con código.**
> "Lo más sorprendente: montar esto ha sido sobre todo **escribir bien** — buenos encargos, buenas descripciones. La herramienta la maneja gente de negocio, no solo developers."

**3. El humano sigue teniendo la última palabra — y eso es un diseño, no una carencia.**
> "El agente para y pregunta a propósito. Cuanto más potente es la IA, más importa ese punto de control humano. No es que no sepa cerrar solo: es que **no debe**."

**Puente a la parte 2 (sembrar, no prometer de más):**
> "Hoy os lo he enseñado por encima, para que entendáis QUÉ hace y POR QUÉ. En una próxima charla bajaremos al taller: cómo se construye esto paso a paso, cómo se comunican los agentes por dentro, y cómo lo aplicaríais a VUESTRO problema del día a día — porque RRHH ya nos ha pedido uno para cruzar sus Excel. Pero eso, otro miércoles."

**Frase de cierre 🔑:**
> *"La pregunta ya no es si la IA puede ayudaros. Es qué trabajo tedioso le vais a delegar primero — sabiendo que vosotros seguís teniendo la última palabra."*

---

## APÉNDICE — Preguntas probables de la sala y respuestas cortas

**"¿Esto se equivoca? ¿Me puedo fiar?"**
> Se puede equivocar, como cualquiera. Por eso está diseñado para **pararse y enseñarte** lo que encontró antes de hacer nada. Tú validas. Y le prohibimos inventar: si no está en el documento, lo marca como duda.

**"¿La estimación de cuánto cuesta el proyecto es fiable?"**
> Es una estimación de **magnitud**, para decidir si merece la pena ofertar, no un presupuesto cerrado. El propio agente lo marca como orientativo y lista sus supuestos.

**"¿Esto no le quita el trabajo a alguien?"**
> Le quita la parte tediosa — leerse 8 páginas y no dejarse nada. La decisión, el criterio y la relación con el cliente siguen siendo de la persona. Hace de becario meticuloso, no de sustituto.

**"¿Nuestros datos salen fuera de la empresa?"**
> No. Igual que en la 13: vive en el ecosistema corporativo, con vuestras credenciales. *(Para el directo del miércoles usamos un pliego inventado de una academia de baile, precisamente para no enseñar datos reales de nadie.)*

**"¿Yo podría montar uno?"**
> Sí, y de eso irá la parte 2. Si en tu día a día hay una tarea repetitiva de leer-y-ordenar, hay un agente para eso.

---

## NOTAS DE PRODUCCIÓN (para ti, no para decir)

- El JSON se estabilizó pidiendo exhaustividad explícita ("la lista COMPLETA, todos, sin resumir"). Pasó de 3 a 34 requisitos. Si en el ensayo vuelve a quedarse corto, refuerza esa instrucción antes del directo.
- Pliego SOLO en PDF. El markdown no lo ingiere bien.
- El flujo Power Automate quedó cerrado con ayuda de un compañero (Compose → Parse JSON → ForEach → Excel → Responder). El paso frágil histórico fue el esquema del Parse JSON; no tocarlo antes del directo.
- Parte 2 pendiente: taller de construcción + orquestación interna + caso RRHH (cruce de Excel). No mezclar con esta.
