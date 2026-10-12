---
type: guion
title: "Charla 23 — Comprobar antes de construir: BDD, ODD y el arnés con nombre"
description: "Charla centrada en la mitad 'antes' de Comprobar (ciclo de la 22): BDD para lo que importa, ODD como contrapeso para el resto. Primera vez que 'el arnés' se nombra con su término de industria: AI harness engineering. La mitad 'después' (ai-code-review + RDD) queda para una charla futura con su propia demo."
tags: [charla, guion, bdd, odd, ai-harness-engineering, verificacion, comprobar, gherkin, rca, gentleman-programming]
related:
  - "[[guion-charla-16]]"
  - "[[guion-charla-19]]"
  - "[[guion-charla-22]]"
  - "[[bdd]]"
  - "[[sdd]]"
  - "[[arnes-completo]]"
  - "[[odd]]"
  - "[[gherkin]]"
  - "[[ai-harness-engineering]]"
  - "[[rdd]]"
charla: 23
estado: borrador
timestamp: 2026-10-12
---

# Guión Charla 23 — Comprobar antes de construir: BDD, ODD y el arnés con nombre

### 14 de octubre de 2026

> Charla con una demo real sobre RCA (BDD). Cierra la mitad "antes de construir" de la etapa Comprobar del ciclo de 6 pasos (introducido en la 22). Es también la primera charla que nombra "el arnés" con su término de industria: **AI harness engineering**. La mitad "después de construir" (ai-code-review, con el framework RDD) queda reservada para una charla futura con su propia demo — no se toca hoy.

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|--------|-----------|--------|
| 1. Apertura | Callback a la 22 + el arnés recibe nombre de industria: AI harness engineering | 3 min |
| 2. BDD, el concepto | Contar el resultado esperado como historia (Gherkin) | 7 min |
| 3. Demo BDD | Escenario Gherkin sobre RCA → la IA lo implementa y verifica | 10 min |
| 4. ODD, el contrapeso | El comportamiento por defecto del agente — protocolo real, no solo "un prompt" — callback a la 16 | 10 min |
| 5. Cierre + puente | "Verifying beats generating" + promesa de la otra mitad | 4 min |

**Total ≈ 34 min** (sigue dejando buen margen para preguntas, más que las charlas con dos demos).

---

## Bloque 1 — Apertura: el arnés recibe nombre — 3 min

> *"La semana pasada montamos un ciclo de seis pasos que vale para cualquier trabajo, con IA o sin ella: Idea, Especificar, Construir, Comprobar, Publicar, Mantener. Y dejé una parada coja: Comprobar. Hoy empezamos a cerrarla — la primera mitad, la de ANTES de construir. La segunda mitad, la de DESPUÉS, la dejo para otro día, con su propia demo, porque merece tiempo propio."*

**El nombre del arnés:**

> *"Y antes de entrar, una cosa que quiero deciros porque le da peso a todo lo que lleváis siete charlas escuchando. Esto que yo llamo 'el arnés' —SDD, skills, MCPs, instrucciones persistentes, memoria— no es una metáfora que me haya inventado yo solo en una charla cualquiera. Tiene nombre en la industria: se llama **AI harness engineering**. Lo usa gente de OpenAI, lo ha escrito Martin Fowler, y lo usa también una comunidad hispanohablante enorme detrás de un proyecto llamado Gentleman Programming."*
>
> *"¿Por qué os cuento esto? Porque significa que lo que hacéis aquí cada semana —aprender a poner límites y herramientas alrededor de la IA en vez de confiar en el prompt suelto— no es un capricho nuestro. Es una disciplina con nombre, con gente seria detrás, en varios sitios a la vez."*

**Frase que debe quedar:**
> *"El arnés tiene nombre: AI harness engineering. No nos lo hemos inventado nosotros — lo hemos puesto en práctica antes de saber cómo se llamaba."*

---

## Bloque 2 — BDD: contar el resultado esperado como historia — 7 min

> *"Empecemos por el antes. ¿Os acordáis de la 16? Vimos SDD — Specification-Driven Development: antes de que la IA construya nada, le describes bien QUÉ quieres. Eso reduce ambigüedad en la entrada."*
>
> *"BDD —Behavior-Driven Development— es el primo que vigila la salida. En vez de limitarte a describir qué construir, describes cómo sabrás que funciona, contado como una historia."*

**El lenguaje de esa historia se llama Gherkin.** Es casi inglés (o español) natural, pero con una estructura fija que tanto una persona como una IA pueden leer sin ambigüedad:

```
Feature: [nombre de la funcionalidad]

  Scenario: [nombre del caso concreto]
    Given [situación de partida]
    When [ocurre una acción]
    Then [esto es lo que tiene que pasar]
```

**Las palabras clave (mostrar en pantalla):**

| Palabra | Para qué sirve |
|---|---|
| `Feature` | Agrupa varios escenarios bajo una misma funcionalidad |
| `Scenario` | Un caso concreto, con nombre descriptivo |
| `Given` | El estado de partida — lo que ya es verdad antes de actuar |
| `When` | La acción que dispara el comportamiento a probar |
| `Then` | El resultado esperado — lo que se verifica |
| `And` / `But` | Encadenan pasos sin repetir Given/When/Then |

**Ejemplo neutro, para que se entienda antes de ir a RCA:**

```gherkin
Feature: Inicio de sesión

  Scenario: Credenciales correctas
    Given que estoy en la página de login
    When introduzco un email y contraseña válidos
    Then accedo a mi panel de usuario

  Scenario: Contraseña incorrecta
    Given que estoy en la página de login
    When introduzco un email válido y una contraseña incorrecta
    Then veo un mensaje de error
```

**Ejemplo sobre RCA (puente hacia la demo del Bloque 3):**

```gherkin
Feature: Carrito de compra

  Scenario: Añadir una pieza al carrito
    Given que estoy viendo la ficha de un anillo de resina
    And el carrito está vacío
    When pulso "Añadir al carrito"
    Then el carrito muestra 1 artículo
    And el precio del anillo se suma al total
```

**(Opcional, si hay tiempo o preguntas) Variante con tabla de datos — `Scenario Outline`:** el mismo caso, repetido con distintos valores, sin copiar el escenario entero:

```gherkin
Feature: Descuentos

  Scenario Outline: Aplicar código de descuento
    Given que tengo un pedido de <importe> €
    When aplico el código "<codigo>"
    Then el total final es <total> €

    Examples:
      | importe | codigo   | total |
      | 100     | DTO10    | 90    |
      | 100     | DTO20    | 80    |
```

> *"La diferencia con un prompt suelto tipo 'añade un descuento' es que aquí el criterio de éxito está escrito ANTES, en una frase que cualquiera de vosotros —técnico o no— puede leer y entender. Y eso vale tanto para que la IA lo implemente como para que luego lo verifique sola: le das el mismo escenario y le preguntas '¿se cumple esto o no?'."*

**Dos matices técnicos, por si surge la pregunta (no hace falta explicarlos si nadie pregunta):**

> *"Gherkin no ejecuta nada por sí mismo — necesita algo detrás que conecte cada línea con el código real (herramientas como Cucumber o Behave hacen eso normalmente). En la demo de hoy, ese papel lo hace directamente la IA: lee el escenario, lo entiende, y comprueba si el comportamiento implementado lo cumple, sin que nadie escriba esa conexión a mano."*
>
> *"Y el `Then` es el contrato: una vez escrito, no se negocia después. Si el resultado no coincide, el escenario falla y ya está — no hay 'más o menos funciona'."*

**Reseñable:**
> *"No le pides a la IA que adivine qué es 'correcto'. Se lo cuentas tú, como una historia, antes de que toque una línea de código."*

**Frase que debe quedar:**
> *"BDD es el criterio de éxito escrito antes de empezar — y en un idioma que entiende todo el mundo."*

> ⚠️ *Para la charla en vivo (168 personas, 98% no técnicas): mostrar la tabla de keywords y los dos ejemplos (login + RCA) es suficiente. El Scenario Outline y los dos matices técnicos quedan de reserva — solo si sobra tiempo o alguien pregunta "¿y esto cómo se ejecuta de verdad?".*

**❓ Pregunta anticipada: "¿BDD solo sirve para features nuevas, o también para fixes?"**

> *"Las dos. Y en un fix es donde más se nota el valor."*
>
> *"Para una feature, el escenario describe el comportamiento que quieres que exista, antes de que exista. Para un fix, el escenario describe el bug como comportamiento esperado que ahora mismo falla — se escribe antes de tocar el código, no después."*

Ejemplo de fix sobre RCA, si hace falta aterrizarlo:

```gherkin
Feature: Carrito de compra

  Scenario: No permitir comprar con stock a cero
    Given que una pieza de resina tiene 0 unidades en stock
    When intento añadirla al carrito
    Then el sistema me impide añadirla
    And veo un mensaje de "sin stock"
```

> *"Si hoy ese escenario falla porque el bug deja añadir piezas sin stock, el escenario ES el ticket del bug, escrito como criterio de éxito. Y lo importante no es solo arreglarlo una vez: ese escenario se queda para siempre en la batería de pruebas. Si alguien, meses después, reintroduce el mismo bug, el escenario vuelve a fallar y lo pilla antes de llegar a producción. Es la diferencia entre 'lo arreglé' y 'no puede volver a pasar sin que algo salte'."*

---

## Bloque 3 — Demo BDD sobre RCA — 10 min

**[TODO Juan: caso concreto de RCA — se usan los ejemplos ya escritos arriba (carrito / stock a cero), elegir cuál de los dos se monta en vivo]**

> *"Vamos a verlo sobre RCA, mi proyecto de piezas de resina. Escribo el escenario en vivo: dado que [...], cuando [...], entonces [...]."*

Paso a paso:
1. Escribir el escenario Gherkin en vivo (o mostrarlo ya escrito, según tiempo)
2. Pasárselo a la IA junto con el código relevante de RCA
3. La IA implementa (o ajusta) la funcionalidad
4. La IA verifica el resultado contra el propio escenario — mostrar que el "entonces" se cumple

**Reseñable — pausa aquí:**
> *"Fijaos en el orden: primero el criterio, luego el código. Si algo falla, no discutimos sobre si 'funciona más o menos' — el escenario dice sí o no."*

**Frase que debe quedar:**
> *"El escenario no se negocia después. Se escribe antes."*

> ⚠️ *Con solo una demo en la charla, hay margen de sobra — no hace falta correr. Aprovechar para dejar que la sala haga preguntas sobre la marcha en vez de guardarlas todas para el final.*

---

## Bloque 4 — ODD: el contrapeso — 8 min

> *"Todo lo de antes suena genial, pero pensad en vuestro día a día. ¿Escribiríais un escenario Gherkin para cambiar el color de un botón? ¿Para arreglar una errata en un texto? Si la respuesta que os viene a la cabeza es 'eso sería una locura', tenéis razón — y hay un nombre para esa otra forma de trabajar."*

> *"Se llama **ODD — Organic Driven Development**. Y aquí viene lo importante, lo que lo diferencia de 'simplemente escribir un prompt': ODD no es la opción ligera que elegís cuando no os apetece hacer las cosas bien. **Es el comportamiento por defecto — pero no porque la IA ya venga así de fábrica, sino porque alguien le escribió esa disciplina en sus instrucciones.** Sin esa instrucción, un agente normal explora algo antes de cambios grandes, sí — pero no clasifica el trabajo, no crea un documento con tareas antes de tocar código, ni se limita a una sola pregunta. Eso, en concreto, es lo que añade el protocolo de ODD."*

**Lo que hace el agente por dentro, paso a paso (esto es lo nuevo — no es solo 'un prompt'):**

1. **Primero decide si es un cambio real o solo una pregunta.** Si solo le pedís explicar o investigar algo, no toca nada — se queda en modo lectura.
2. **Explora el proyecto, en proporción a lo que le pedís.** Para cambiar un color no relee todo el código; para algo más gordo, mira más.
3. **Si hay una duda real que importa de verdad, hace como mucho UNA pregunta concreta.** No os interroga con diez preguntas — y si detecta que estáis dando por hecho algo arriesgado sin comprobarlo, os lo señala una vez.
4. **Clasifica el trabajo: pequeño o sustancial.** La regla es simple: si explorar el proyecto revela dos o más pasos de implementación reales, es sustancial. Si no, es pequeño.
5. **Pequeño → lo hace y no deja rastro.** Sustancial → **antes de escribir una sola línea de código**, crea un documento con el objetivo, el alcance, los límites y una lista de tareas con sus criterios de aceptación. Y os dice, en una frase, qué documento creó y cuántas tareas tiene.
6. **Va tarea por tarea.** Cada tarea se marca como terminada solo con prueba observada de que funciona — nunca porque el agente simplemente "diga" que ya está. Cada tarea cierra con su propio commit, con sus tests y su documentación al lado, no después.

**Reseñable — el matiz que de verdad cambia la percepción:**
> *"Esto no es 'le pido algo y confío'. El propio agente decide si lo que le pedisteis merece un documento con tareas o no, y si merece prueba antes de dar algo por hecho. La diferencia con un prompt suelto es que aquí hay un protocolo detrás, aunque no se vea."*

**❓ Pregunta anticipada (técnica): "¿Cómo sabe el agente que cambiar un color es un cambio menor? ¿Hace falta un agente especial para eso?"**

> *"No. No hay un agente aparte, ni un clasificador distinto evaluando la petición antes de que el agente principal actúe. Es exactamente el mismo modelo que ya conocéis — el que está detrás de Copilot, de Claude Code, de cualquiera— razonando sobre vuestra petición. Lo que cambia es que tiene una regla escrita que debe aplicar DESPUÉS de explorar el proyecto y ANTES de escribir código: 'si al explorar aparecen dos o más pasos de implementación reales, es sustancial — creo el documento antes de tocar nada. Si no, es pequeño — lo hago directamente.'"*
>
> *"Dicho de otra forma: no se entrena un modelo nuevo ni se construye un motor de reglas aparte del LLM. Se le escribe al mismo modelo un protocolo que tiene que seguir antes de actuar. Eso es, literalmente, lo que significa 'harness engineering' — no cambias el motor, cambias la disciplina que lo rodea."*

> ⚠️ *Nota para Juan, no para la sala: esta regla de clasificación no viene de fábrica en Copilot CLI ni en Claude Code — es una instrucción que gentle-ai inyecta en la configuración del agente que ya tengas. Sin instalar gentle-ai, tu CLI explorará algo de forma natural antes de un cambio grande (eso sí es comportamiento genérico de cualquier buen agente), pero no va a crear un documento de tareas ni a limitarse a una sola pregunta — esa disciplina concreta no está si nadie se la escribe. La buena noticia: no hace falta el repo de gentle-ai para tenerla. Es una instrucción persistente más, como las que ya vimos en la Charla 8. ✅ Ya está hecho: el protocolo ODD (y la convención BDD de `.feature` por carpeta) está añadido al `CLAUDE.md` y al `.github/copilot-instructions.md` de RCA (rama `develop`) — no había ninguna regla incondicional de SDD con la que chocara. Así que si quieres, el Bloque 4 ya se puede demostrar en vivo de verdad, no solo explicar.*
>
> **Si ya tienes contenido en esos archivos:** no se sustituye, se añade como sección nueva — al final, o junto a cualquier otra regla de comportamiento que ya tengas. El único punto real de fricción sería si ya existe algo que diga "usa siempre SDD/OpenSpec/speckit para toda tarea" de forma incondicional — eso chocaría con que ODD sea el comportamiento por defecto. Si tienes algo así, mátizalo a "solo cuando se pida explícitamente", para que las dos reglas no se contradigan entre sí.
>
> **ODD, SDD y BDD no son alternativas que compiten — están anidados.** Tal cual lo dice la fuente: *"SDD is a branch inside ODD, entered only by an explicit request or an accepted proposal."* ODD es el chasis que corre siempre (autorizar → explorar → clasificar); SDD es una rama a la que entras deliberadamente, dentro de ese mismo flujo, cuando el trabajo lo merece — invocarlo no cambia nada de cómo funciona SDD hoy, solo define qué pasa cuando NO lo invocas. Y BDD tampoco compite con ninguno de los dos: un escenario Gherkin puede ser precisamente el criterio de aceptación que va dentro del documento de tareas que ODD crea para trabajo sustancial, o dentro de la verificación de un spec completo de SDD. Se combinan, no se excluyen — aunque en pantalla, para la sala, simplificamos a "por defecto / cuando lo pides" porque la relación exacta de anidación es más detalle del que necesita un público no técnico.

**Callback a la 11 (Wiki LLM):** ese documento de la tarea sustancial, además, se guarda — espejado en una memoria propia del proyecto, el mismo concepto que vimos con la Wiki LLM. No se pierde cuando se cierra la sesión.

**Ejemplos sobre RCA, para ver la clasificación en vivo (pequeño vs sustancial):**

| Petición | Clasificación | Qué pasa |
|---|---|---|
| "Cambia el color del botón de Añadir al carrito a un tono más cálido" | Pequeño | Lo hace, lo compruebo con un vistazo, no queda ningún documento |
| "Añade códigos de descuento al carrito" | Sustancial (validar el código, aplicar el descuento, mostrarlo en el resumen = varios pasos reales) | Antes de tocar código, crea el documento de la feature con sus tareas; avanza tarea por tarea con su propio commit cada una |

> *"Y si esa segunda petición me preocupa de verdad por el riesgo — dinero real, cálculo de precios — ahí es donde pido explícitamente un escenario BDD como el de antes. ODD no me lo impide ni me lo sustituye. Es lo que pasa por defecto hasta que yo decido que esto merece más peso."*

**Callback directo a la Charla 16:**

> *"¿Os acordáis de la 16? Dejamos abierta la pregunta de spec manual vs OpenSpec, SDD sí o SDD no para cada tarea. Esto es la respuesta formal: el tamaño o el riesgo del cambio NUNCA activan el peso completo por sí solos. Lo decidís vosotros, explícitamente, pidiendo 'usa SDD' o 'hazme el escenario'. Todo lo demás, por defecto, ya es ODD."*

**En pantalla — cuándo cada uno:**

```
Por defecto, en cualquier petición             →  ODD (explorar, clasificar, hacer con prueba)
Tú pides explícitamente spec o escenario       →  SDD / BDD (documento o escenario por escrito)
```

> ⚠️ *Nota para Juan, no para la sala: ODD nunca activa por sí sola la revisión de código (RDD, lo que vimos que se queda para la charla futura de ai-code-review). Son interruptores separados — uno no enciende al otro. No hace falta mencionar RDD por nombre aquí; solo evitar dar la impresión de que "ya vimos la revisión" cuando no es así.*

**Reseñable:**
> *"BDD no sustituye al criterio. Es la herramienta para cuando el criterio dice que esto sí merece pararse a escribirlo."*

**Frase que debe quedar:**
> *"No todo necesita un escenario. Pero lo que de verdad importa, sí — y el agente, bien configurado, ya sabe distinguir uno de otro."*

---

## Bloque 5 — Cierre + puente — 4 min

> *"Recolocad esto en el ciclo de la semana pasada: hoy cerramos la mitad de 'Comprobar' que va ANTES de construir. BDD para lo que pesa, ODD para el resto — las dos son formas de no dejar que la IA decida sola qué es 'correcto'."*

**Frase de cierre — tomada de la propia industria (Gentleman Programming / Alan Buscaglia):**

> *"Y me quedo con una frase que resume todo el espíritu de esta charla, y que no es mía: **'verifying beats generating'** — verificar vale más que generar. No importa lo rápido que la IA escriba. Importa si lo que escribió es lo correcto, y eso solo se sabe comprobando."*

**Puente a la mitad que falta:**

> *"Queda la otra mitad: comprobar DESPUÉS de construir — lo que ya existe, lo que ya lleva meses en producción. Esa va con su propia charla, su propia demo, y un nombre que hoy no os doy todavía: porque merece el tiempo completo, no un resumen con prisa al final de esta sesión."*

**Frase final:**
> *"Hoy aprendisteis a comprobar antes de empezar. La semana que viene —o cuando toque— aprendéis a comprobar lo que ya está hecho."*

---

## Checklist antes del miércoles

### Pendiente de Juan
- [x] ~~Revisar si `CLAUDE.md`/`copilot-instructions.md` de RCA ya obliga a usar SDD/OpenSpec siempre~~ — revisado: no había ninguna regla incondicional, no hacía falta matizar nada.
- [x] ~~Añadir el protocolo ODD y la convención BDD (`.feature` por carpeta) al `CLAUDE.md` y `.github/copilot-instructions.md` de RCA~~ — subido a la rama `develop`.
- [x] ~~Elegir cuál de los dos ejemplos Gherkin ya escritos (carrito / stock a cero) se monta en vivo en el Bloque 3~~ — confirmado: el ejemplo del carrito ya escrito en el Bloque 2 es el que se usa en el Bloque 3, sin cambios.
- [x] ~~Revisar si el ejemplo de ODD (color del botón) encaja o prefieres otro~~ — confirmado: se queda el ejemplo de cambiar el color del botón de "Añadir al carrito".
- [ ] **Decidir si el Bloque 4 se hace solo en explicación o con demo en vivo del protocolo ODD** — pendiente de que Juan pruebe mañana con Copilot sobre RCA (ya con el fragmento subido) si el flujo completo se comporta como se espera antes de arriesgarse a demostrarlo delante de la sala.

### Lunes / Martes
- [ ] Preparar visual del ciclo de 6 pasos (recordatorio de la 22) para el Bloque 1
- [ ] Preparar visual del formato Gherkin (dado/cuando/entonces) para el Bloque 2
- [ ] Preparar el esquema "cuándo ODD / cuándo BDD" del Bloque 4
- [ ] Ensayo cronometrado — con solo una demo, debería sobrar tiempo; aprovechar para dejar hueco a preguntas en vivo

### El día de la charla
- [ ] Escenario Gherkin elegido, abierto y listo para mostrar
- [ ] Frase final preparada para dejar fija en pantalla

---

## Decisiones abiertas (para cerrar contigo)

1. **Caso de la demo BDD (Bloque 3):** ✅ cerrado — se usa uno de los ejemplos ya escritos en el Bloque 2 (carrito o stock a cero); falta solo que elijas cuál.
2. **Estructura general:** ✅ cerrado — la 23 se queda solo con BDD + ODD; ai-code-review (con el framework RDD y su propia demo) se mueve entera a una charla futura.
3. **Encaje de "AI harness engineering" / "verifying beats generating":** ✅ cerrado — el nombre del arnés se da en la apertura (Bloque 1); la frase "verifying beats generating" cierra la charla (Bloque 5). RDD se reserva íntegro para la charla de ai-code-review, para que llegue con fuerza completa junto a su demo.
4. **PR/MR de RCA, GitLab Duo, y las dos técnicas de revisión (terminal + reviewer publicado):** ya investigadas en esta sesión, pero no se usan en la 23 — quedan guardadas para cuando se planifique la charla de ai-code-review. No hace falta volver a investigarlas desde cero.
5. **Nombre/número de la charla futura de ai-code-review + RDD:** por definir.
