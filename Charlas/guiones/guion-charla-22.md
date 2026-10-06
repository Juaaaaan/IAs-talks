---
type: guion
title: "Charla 22 — Pregúntale primero"
description: "Charla de hábito, no de adopción: la IA ya se usa, falta el reflejo de incorporarla de forma consciente. Define la mentalidad IA-first como una segunda mirada temprana: primero entender el problema y pensar una solución base; antes de ejecutarla, preguntar dónde puede ayudar la IA, sin convertirla en solución automática ni sustituto del criterio, con respaldo en la distinción real AI-enabled vs AI-first y un ejemplo antes/después, y luego el ciclo de vida de cualquier trabajo (idea → especificar → construir → comprobar → publicar → mantener) repite esa pregunta seis veces, cada parada anclada a un ejemplo real ya visto en la serie: RRHH (idea), OpenSpec/RCA (16, especificar), OpenCode + Hermes Agent/9Router (20, construir), el spec BDD de la 16 (comprobar), el Analista de RFP y su checkpoint humano (19, publicar), Wiki LLM e instrucciones persistentes (11/8, mantener). Incluye ejercicio en vivo con una tarea real de cada asistente."
tags: [charla, guion, ia-first, habito, sdlc, criterio, arnes, callbacks]
related:
  - "[[guion-charla-16]]"
  - "[[guion-charla-19]]"
  - "[[guion-charla-20]]"
  - "[[guion-charla-11]]"
  - "[[guion-charla-08]]"
  - "[[sdd]]"
  - "[[el-arnes]]"
  - "[[opencode]]"
  - "[[rca]]"
charla: 22
estado: borrador
timestamp: 2026-10-05
---

# Guión Charla 22 — Pregúntale primero

### 7 de octubre de 2026

> Charla de hábito, no de adopción. La audiencia ya usa la IA — no hay que convencer de que funciona. El objetivo es un cambio de reflejo más preciso: ante una tarea, primero entender el problema y plantear una solución razonable; antes de invertir tiempo en ejecutarla, preguntarse qué partes puede acelerar, enriquecer o simplificar la IA. No se trata de pensar menos, sino de no recorrer solos un camino que puede hacerse mejor acompañados. Un ejercicio en vivo ancla el concepto a una tarea real de cada asistente, y cada parada del ciclo se apoya en un ejemplo que la sala ya ha visto — nada nuevo que aprender, solo un hilo que lo conecta todo.

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|---|---|---:|
| 1. Apertura | Uso cotidiano y problema del hábito | 4 min |
| 2. El giro | Pensar la tarea, explorar con IA y decidir con criterio | 8 min |
| 3. ¿Construir o ya existe? | Aplicar criterio antes de añadir complejidad | 4 min |
| 4. Ejercicio en vivo | Una tarea real de esta semana | 3 min |
| 5. El hilo | Un ciclo que ya conocéis | 3 min |
| 6. Las seis paradas | Idea · Especificar · Construir · Comprobar · Publicar · Mantener | 19 min |
| 7. Cierre | Los límites y el criterio humano | 4 min |

**Total ≈ 45 min** (preguntas aparte).

---

## Bloque 1 — Apertura: lo que ya tenéis delante — 4 min

Abrir con lo que la sala ya ha visto funcionar. Cero necesidad de convencer. Mención breve y honesta al compañero — sin entrar en detalle, porque Juan no ha visto la charla todavía.

> *"La semana pasada mi compañero os habló de Copilot, WorkIQ y PowerPoints — no he podido verla aún, así que no voy a meterme ahí, pero seguro que a más de uno ya le ha cambiado cómo monta una presentación. Y antes, RRHH nos pidió ayuda para cruzar datos de Excel con IA. Y seguro que la mayoría ya le ha pedido un resumen, un email, o que os explique algo raro de un contrato."*
>
> *"O sea: no vengo hoy a convenceros de que la IA funciona. Eso ya está hecho — lo habéis visto vosotros mismos, esta misma semana."*
>
> *"Vengo a hablaros de otra cosa, mucho más pequeña y mucho más importante: no de si la usáis, sino de cuándo os acordáis de usarla."*

**Frase que debe quedar:**
> *"No hace falta que os convenza de que funciona. Hace falta que os acordéis de usarla."*

---

## Bloque 2 — El giro: qué es pensar en IA-first — 8 min

> *"Y aquí está el cambio de hoy, en una frase: antes de hacerlo vosotros, preguntadle primero."*
>
> *"Pero 'primero' no significa apagar vuestra cabeza. Ante una tarea, primero entendéis el problema y pensáis cómo la resolveríais de manera tradicional. Antes de comprometer tiempo y esfuerzo con esa solución, hacéis una segunda pasada: ¿en qué partes puede ayudarme la IA?, ¿qué camino puede hacer más fácil?, ¿qué ángulo no estoy viendo? Después decidís si seguís vosotros, sigue ella o lo hacéis entre los dos."*
>
> *"La IA no sustituye el primer pensamiento ni toma la última decisión. Se incorpora al principio de la exploración, antes de ejecutar. La IA es la primera conversación sobre vuestra solución, no la última palabra."*

**Ponerle nombre (el concepto que da título a hoy):**

> *"Esto tiene nombre, y quiero decirlo una vez para que os lo llevéis: se llama mentalidad IA-first. No me lo invento yo — es un concepto real que lleva meses en boca de empresas y medios como Wired: hay diferencia entre usar la IA de vez en cuando para una tarea suelta —eso tiene nombre aparte, se llama AI-enabled— y ser de verdad AI-first, donde la IA es el punto de partida, no un complemento que añades al final."*
>
> *"Normalmente se habla de esto a nivel de empresa entera: cómo rediseña sus procesos, su estrategia, su forma de decidir. Hoy lo bajamos a una escala mucho más pequeña y mucho más vuestra: no la empresa, vosotros. El mismo principio, aplicado a cada tarea de vuestro día a día."*
>
> *"Y quiero ser muy preciso: IA-first no es IA-only ni IA-always. No significa que la IA sea siempre la solución, que haga todo el trabajo o que decida por vosotros. Una vez entendido el problema y antes de ejecutar vuestra solución, comprobáis si puede aportar opciones, preguntas, velocidad o contraste. A veces la respuesta será sí; otras veces, no merece la pena usarla."*

**El antes/después — para que no quede abstracto:**

> *"Os lo enseño con un caso tonto, a propósito, para que se vea clarísimo. Mañana tenéis una reunión con un cliente nuevo."*
>
> *"Modelo tradicional: entendéis que necesitáis preparar la reunión, pensáis los objetivos y abrís un Word para escribir el guion. Esa primera reflexión es necesaria. El problema es ejecutar todo el camino sin una segunda pregunta: ¿en qué puede ayudarme aquí la IA? Quizá os falte un riesgo, una objeción o una pregunta que no habíais considerado."*
>
> *"Modelo IA-first: después de aclarar qué reunión tenéis y qué resultado buscáis, pero antes de redactarlo todo, le preguntáis: 'mañana tengo una reunión con un cliente nuevo sobre esto, ¿qué debería cubrir, y qué le preguntaría yo si estuviera en su lugar?'. Diez segundos después tenéis un primer borrador — con cosas en las que ni habíais caído. Y AHORA decidís: lo seguís tal cual, lo afináis juntos, o lo tiráis entero y empezáis de cero. Pero decidís después de preguntar, no antes."*
>
> *"Fijaos en que la diferencia no está en quién acaba haciendo el trabajo. Puede que al final el guion lo escribáis enteramente vosotros. La diferencia está en no pasar directamente de entender el problema a ejecutar la primera solución. Entre ambas cosas abrís una exploración con IA y luego aplicáis vuestro criterio. Eso es IA-first: incorporar la IA temprano, no obedecerla automáticamente."*

**El giro mental (pensar en el resultado, no en la tarea):**

> *"Hay un pequeño truco que ayuda muchísimo: dejad de pensar en la tarea que tenéis delante, y pensad en el resultado al que queréis llegar. No 'voy a escribir este documento', sino 'quiero llegar a X' — y preguntadle primero cómo llegar. Cambia una tarea entera por una conversación."*

**Frases que deben quedar:**
> *"La IA es la primera conversación sobre tu solución, no la última decisión."*
>
> *"IA-first no es IA-only ni IA-always."*
>
> *"Antes de invertir esfuerzo, pregúntale primero."*


---

## Bloque 3 — ¿Construir un agente, o ya existe algo hecho? — 4 min

> *"Y aquí va algo que forma parte del mismo reflejo, no una excepción a él: preguntar primero no significa 'móntate un agente para todo'. A veces la pregunta correcta no es '¿qué agente necesito?', es '¿hace falta construir algo, o ya existe una herramienta que lo resuelve?'. Esa pregunta también se la hacéis primero a la IA."*
>
> *"Microsoft tiene PowerApps y Power Automate — aplicaciones y automatizaciones que se montan arrastrando piezas, sin programar, pensadas para tareas estructuradas y repetitivas: aprobar un gasto, recoger datos de un formulario, mover algo de un sitio a otro. Si vuestro problema es eso, construir un agente a medida es como contratar un arquitecto para colgar un cuadro."*
>
> *"¿Cuándo sí hace falta un agente, o un equipo de agentes como el de la Charla 19? Cuando hay que leer, juzgar, decidir con criterio — cosas sin un camino fijo de pasos. El Analista de RFP de la 19 no podía ser un PowerApp: tenía que entender un pliego de verdad, detectar contradicciones, razonar. Eso no se arrastra con el ratón."*
>
> *"La regla corta: camino claro y pasos fijos, PowerApps. Hay que pensar y decidir en cada caso, agente. De la segunda parte —qué motor usar cuando sí hace falta un agente— hablamos más adelante, en la parada de Construir."*

**Frase que debe quedar:**
> *"No todo lo que automatizáis necesita un agente. A veces la pregunta IA-first es la contraria: ¿hace falta construir algo, o ya existe?"*

**Microejemplo de límite:**
> *"Y a veces la conclusión será todavía más sencilla: no hace falta IA. Si solo vais a corregir una fecha, confirmar un dato conocido o responder un sí o un no, introducir un modelo puede añadir más fricción que valor. IA-first significa evaluar pronto si aporta algo y descartarla pronto cuando no lo aporta."*

---

## Bloque 4 — Ejercicio en vivo: pensad en una tarea real vuestra — 3 min

El punto donde la charla deja de ser teoría y se engancha a algo de cada persona. Nada de compartir en voz alta — es un ejercicio mental (o para quien quiera, en el chat de Teams).

> *"Antes de seguir, quiero que penséis en algo. Una cosa real que tengáis que hacer esta semana — de las que ibais a hacer vosotros solos, sin pensarlo dos veces. Un email que os da pereza, una propuesta, organizar algo, preparar una reunión."*
>
> *"No hace falta decirlo en voz alta. Solo tenedlo en la cabeza, porque lo vamos a usar ahora mismo: el recorrido que viene son seis paradas, y en cada una os voy a pedir que la apliquéis a esa cosa que acabáis de pensar. Si alguien quiere escribirla en el chat, adelante — pero no hace falta."*

**Frase que debe quedar:**
> *"Pensad en algo real. Lo vamos a usar."*

---

## Bloque 5 — El hilo: un ciclo que ya conocéis sin saberlo — 3 min

> *"Para que esa frase no se quede en un eslogan bonito, os la voy a repetir seis veces, en seis sitios distintos — y en cada una, con un ejemplo que ya habéis visto en esta serie. Nada nuevo que aprender hoy: solo el hilo que lo conecta todo."*
>
> *"Resulta que casi todo lo que hacéis, por pequeño que sea, pasa por las mismas etapas: tenéis una idea, decidís qué queréis exactamente, lo hacéis, lo comprobáis, lo soltáis fuera, y luego hay que mantenerlo vivo."*
>
> *"Eso, en el mundo del software, tiene hasta nombre propio. Pero no os asustéis — no es cosa de developers. Es el ciclo de un email, de una propuesta, de un evento que organizáis, de una decisión que tomáis."*

En pantalla:

```
Idea → Especificar → Construir → Comprobar → Publicar → Mantener
```

**Frase que debe quedar:**
> *"No es un ciclo de software. Es el ciclo de todo lo que hacéis."*

---

## Bloque 6 — Las seis paradas (con ejemplos ya vistos) — 19 min

En cada parada: el concepto, el ejemplo real de una charla anterior, y una pregunta directa para aplicarlo a la tarea del Bloque 4.

### 6.1 Idea — 2 min — *el encargo de RRHH*

> *"Primera parada: la idea. Antes de poneros a planificar algo desde cero, pregúntale primero qué forma podría tener. Ni siquiera hace falta tener ya media idea en la cabeza."*
>
> *"Y aquí tenéis un ejemplo de verdad, no inventado: lo de RRHH que os contaba al principio. Cruzar datos a Excel con IA empezó siendo justo eso — una idea suelta, sin forma todavía. Nadie sabía aún si iba a ser un agente, un script o media hora de trabajo con un chat. Eso también se le pregunta primero a la IA."*
>
> *"Aplicado a lo vuestro: la tarea que pensasteis antes — ¿le habéis preguntado ya qué forma podría tener, o habéis dado por hecho que la forma ya la sabíais vosotros?"*

**Antes de hacerlo tú, pregúntale primero.**

### 6.2 Especificar — 4 min — *SDD, el Cart Drawer de RCA (Charla 16)*

> *"Segunda parada: especificar. Antes de picar nada, pregúntale qué le falta por saber. En la Charla 16 le pusimos nombre, SDD, y lo vimos con las manos en la masa: un ticket de Jira de dos frases — un filtro por categoría para el catálogo de RCA — se convirtió, sin escribir el spec a mano, en un plan completo. La IA no empezó a programar: primero preguntó qué quería decir exactamente 'filtrar por categoría', y lo dejó por escrito antes de tocar una línea."*
>
> *"Aplicado a lo vuestro: si le pidierais ayuda ahora mismo con vuestra tarea, ¿sabría la IA qué queréis de verdad, o le faltaría contexto que solo tenéis en la cabeza?"*

**Antes de hacerlo tú, pregúntale primero.** *(callback: [[guion-charla-16]])*

### 6.3 Construir — 4 min — *el menú de OpenCode (Charla 20)*

> *"Tercera parada: construir, hacerlo de verdad. En la Charla 20 vimos que, a la hora de ejecutar, hay quien decide el motor por vosotros y hay quien os deja elegirlo. ¿Os acordáis del menú de OpenCode, donde elegíais qué IA hacía el trabajo? Esa es la pregunta de esta parada, aplicada: antes de hacerlo vosotros, preguntadle quién —o qué— lo hace mejor."*
>
> *"El ejemplo no depende de que una herramienta concreta sobreviva. OpenCode fue el caso que vimos; Hermes Agent o 9Router pueden servir como apunte de actualidad si siguen vigentes. La idea duradera es otra: antes de elegir herramienta, preguntad qué hace mejor, qué contexto necesita, cuánto control os deja y qué ocurre con vuestros datos."*
>
> *"Aplicado a lo vuestro: la parte de 'hacerlo' de vuestra tarea — ¿la ibais a hacer entera vosotros, o le habéis dejado sitio a la IA?"*

**Antes de hacerlo tú, pregúntale primero.** *(callback: [[guion-charla-20]])*

### 6.4 Comprobar — 3 min — *el mismo spec de la 16, visto con otros ojos*

> *"Cuarta parada: comprobar. Antes de dar algo por bueno vosotros solos, pregúntale que lo ponga a prueba. ¿Os acordáis de aquel fichero de la 16, con las frases 'dado que el usuario está en el catálogo, cuando selecciona una categoría, entonces solo se muestran esos productos'? Eso, sin que lo supierais entonces, ya era BDD: contarle el resultado esperado como una historia, para poder comprobar si se cumple. Quien programa tiene su versión más técnica, TDD — pero con contar la historia basta para la mayoría."*
>
> *"Esto no es solo para código. Antes de enviar un correo delicado, una propuesta o una presentación, podéis pedirle: actúa como el destinatario; busca ambigüedades, objeciones y cosas que podrían entenderse mal. La IA no valida la verdad ni sustituye una revisión experta: hace de segundo par de ojos."*
>
> *"Aplicado a lo vuestro: antes de dar vuestra tarea por terminada, ¿le habéis pedido que la revise desde otro punto de vista?"*

**Antes de hacerlo tú, pregúntale primero.** *(mismo ejemplo que 6.2, otro ángulo)*

### 6.5 Publicar — 4 min — *el checkpoint del Analista de RFP (Charla 19)*

> *"Quinta parada: publicar, soltarlo fuera. Antes de darle al botón, pregúntale si hay algo que se os escapa. ¿Os acordáis del Analista de RFP de la Charla 19? Analizaba el pliego, encontraba las trampas... y antes de escribir una sola fila en el Excel, se paraba y preguntaba: '¿quieres corregir algo antes de generar el Excel?'. No cerró a vuestras espaldas. Esa pausa es la quinta parada, aplicada."*
>
> *"Aplicado a lo vuestro: cuando le deis al botón final de vuestra tarea, ¿va a ser la primera vez que alguien —o algo— le ha echado un segundo vistazo?"*

**Antes de hacerlo tú, pregúntale primero.** *(callback: [[guion-charla-19]])*

### 6.6 Mantener — 2 min — *Wiki LLM e instrucciones persistentes (Charlas 11 y 8)*

> *"Y última parada: mantener, que no se pierda. Antes de que se os olvide por qué tomasteis una decisión, pregúntale que os lo deje anotado. En la Charla 11 vimos cómo, en segundos, documentamos por qué RCA no tendría modo oscuro — y generamos el perfil de un compañero nuevo sin tocar un Excel. Y en la 8, el 'manual de bienvenida' que le escribimos una vez a Copilot para que no se le olvidara nunca cómo trabajamos. Memoria que no depende de que alguien se acuerde."*
>
> *"Aplicado a lo vuestro: dentro de tres meses, ¿va a estar anotado en algún sitio por qué hicisteis esta tarea así, o va a depender de que os acordéis vosotros?"*

**Antes de hacerlo tú, pregúntale primero.** *(callback: [[guion-charla-11]], [[guion-charla-08]])*

---

## Bloque 7 — Cierre: la frase, seis veces — 4 min

> *"Habéis oído la misma frase seis veces, aplicada a algo vuestro de verdad y a cosas que ya habíamos visto juntos. Es a propósito: eso es el hábito, haciéndose."*
>
> *"Esto no iba de un ciclo de software. Iba del ciclo de cualquier cosa que hacéis: una idea, decidir qué queréis, hacerlo, comprobarlo, soltarlo, y que no se pierda. En cada parada, la misma pregunta."*

**Momento opcional — recoger una respuesta de la sala:**
> *"¿Alguien se ha dado cuenta, en alguna de las seis paradas, de algo que no había pensado de su tarea? Lo leo si alguien lo escribe en el chat."*

**Frase final — dejar fija en pantalla:**
> *"Antes de invertir esfuerzo, pregúntale primero."*
>
> *"IA-first no es IA-only ni IA-always: la IA abre opciones; vuestro criterio decide."*

**Guiño al arnés mental:**
> *"Y si os lleváis una idea más: el arnés que llevamos meses montando para la IA, podéis ponéroslo también a vosotros mismos. Primero entendéis el camino. La IA os ayuda a explorarlo y a recorrerlo mejor. Vuestro criterio sigue llevando la rienda."*

---

## Checklist antes del miércoles

### Cuanto antes
- [ ] Confirmar título definitivo (ver Decisiones abiertas)
- [ ] Decidir si el ejercicio del Bloque 4 se apoya en el chat de Teams o queda puramente mental

### Lunes / Martes
- [ ] Esquema visual del ciclo (Bloque 5) listo para proyectar
- [ ] Verificar que 9Router y Hermes Agent siguen activos/vigentes antes de nombrarlos en directo (se mueven rápido)
- [ ] Ensayo cronometrado — vigilar que la repetición de la frase no se note mecánica, y que las 19 min del Bloque 6 no se disparen

### El día de la charla
- [ ] Esquema del ciclo (idea→...→mantener) listo para proyectar
- [ ] Frase final preparada para dejar fija en pantalla
- [ ] Chat de Teams a la vista por si alguien comparte su tarea o su respuesta final

---

## Decisiones abiertas (para cerrar contigo)

1. **Título:** de trabajo "Pregúntale primero". Alternativas que barajamos: *"El ciclo de todo: pregúntale primero, hazlo después"* / *"De cuándo te acuerdas a por defecto"*.
2. **6.2 y 6.4 comparten el mismo ejemplo** (el spec de la 16) visto desde dos ángulos — es intencional, para que quede ligero y no meta un caso nuevo cada vez. Si prefieres un ejemplo distinto para Comprobar, lo cambio.
3. **9Router / Hermes Agent (6.3):** verificar vigencia cerca de la fecha — es ecosistema que se mueve semana a semana.
4. **Mención al compañero (Bloque 1):** dejada deliberadamente breve y sin detalle, ya que no has visto la charla todavía — ajústala si después de verla quieres meter algo concreto.
5. **Ejemplo antes/después del Bloque 2 (reunión con cliente nuevo):** es genérico, a propósito, para que se entienda sin depender de contexto previo. Si tienes un caso real tuyo donde el "modelo antiguo" te costó algo, sustitúyelo — pega más que uno inventado.
6. **Frase descartada del Bloque 2 anterior** ("el problema no es la confianza, es el hábito") — se cae con el cambio de bloque. Era buena, así que si quieres recuperarla en otro punto (encajaría en el Bloque 1 o el 2), dímelo.
