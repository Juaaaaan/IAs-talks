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
timestamp: 2026-10-13
---

# Guión Charla 23 — Comprobar antes de construir: BDD, ODD y el arnés con nombre

### 14 de octubre de 2026

> Charla con una demo real sobre RCA. Cierra la mitad "antes de construir" de la etapa Comprobar, introducida en la charla 22. Toda la sesión gira alrededor de una única idea: **la IA no debería decidir por sí sola qué significa correcto**. Primero se define el criterio de éxito; después se genera y se verifica. BDD, ODD y AI harness engineering aparecen como nombres técnicos al servicio de esa idea, no como tres temas independientes. La mitad "después de construir" queda reservada para una charla futura.

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|---|---|---:|
| 1. Apertura | Callback a la 22 y tesis única: definir qué significa correcto | 3 min |
| 2. Escenarios antes de construir | Ejemplo cotidiano, BDD/Gherkin y ejemplo RCA | 8 min |
| 3. Demo BDD | Implementación y verificación contra el criterio previo | 10 min |
| 4. Comportamiento por defecto | Dos peticiones observables, ODD y nombre del arnés | 9 min |
| 5. Cierre y puente | Verificar vale más que generar | 4 min |

**Total ≈ 34 min** (con margen para preguntas y desviaciones de la demo).

## Bloque 1 — Apertura: definir qué significa correcto — 3 min

_"La semana pasada montamos un ciclo de seis pasos que vale para cualquier trabajo, con IA o sin ella: Idea, Especificar, Construir, Comprobar, Publicar y Mantener. Y dejamos una parada coja: Comprobar. Hoy vamos a cerrar la mitad que ocurre ANTES de construir. La mitad de después tendrá su propia charla y su propia demo."_

_"La IA genera cada vez más deprisa. Pero generar deprisa no sirve de mucho si nadie ha definido antes qué significa que el resultado esté bien."_

_"Esa es toda la idea de hoy: no le pedimos a la IA que adivine qué significa correcto. Se lo decimos antes de empezar."_

**En pantalla:**

> **La IA no debería decidir por sí sola qué significa correcto.**
>
> Primero definimos el criterio. Después generamos y verificamos.

_"Hoy veremos dos niveles. Para lo importante, escribiremos explícitamente el resultado esperado. Para lo pequeño, daremos al agente una disciplina proporcional para no convertir cada cambio en un proceso pesado. Al final pondremos nombre técnico a todo ese sistema."_

**Por qué se cambia:** primero se presenta el problema y la tesis. El término «AI harness engineering» se reserva hasta que la audiencia haya visto para qué sirve.

## Bloque 2 — Escenarios: contar el resultado esperado antes de construir — 8 min

_"Vamos a empezar sin hablar todavía de código. Imaginad una solicitud de vacaciones."_

```gherkin
Feature: Solicitud de vacaciones
  Scenario: Solicitar días disponibles
    Given que tengo días de vacaciones disponibles
    When solicito tres días
    Then la solicitud queda registrada para aprobación
```

_"Sin saberlo, acabáis de leer un criterio de éxito. Cualquier persona puede entender la situación, la acción y el resultado esperado. No hemos pedido a la IA que interprete qué sería correcto: se lo hemos contado antes."_

_"Esta forma de expresar comportamiento tiene un nombre: BDD, Behavior-Driven Development. El lenguaje estructurado se llama Gherkin."_

**En pantalla, solo lo imprescindible:**

| Palabra | Pregunta que responde |
|---|---|
| Feature | ¿Qué capacidad describimos? |
| Scenario | ¿Qué caso concreto comprobamos? |
| Given | ¿De qué situación partimos? |
| When | ¿Qué acción ocurre? |
| Then | ¿Qué resultado debe cumplirse? |
| And / But | ¿Qué condiciones adicionales existen? |

_"Lo importante no es memorizar las palabras en inglés. Es el orden mental: situación, acción y resultado observable."_

**Ejemplo sencillo de software:**

```gherkin
Feature: Inicio de sesión
  Scenario: Contraseña incorrecta
    Given que estoy en la página de acceso
    When introduzco un email válido y una contraseña incorrecta
    Then veo un mensaje de error
```

**Ejemplo sobre RCA, puente hacia la demo:**

```gherkin
Feature: Carrito de compra
  Scenario: Añadir una pieza al carrito
    Given que estoy viendo la ficha de un anillo de resina
    And el carrito está vacío
    When pulso "Añadir al carrito"
    Then el carrito muestra 1 artículo
    And el precio del anillo se suma al total
```

_"Frente a un prompt como ‘añade un carrito’, aquí el criterio de éxito está escrito ANTES, en un formato que puede leer una persona y que la IA puede usar para implementar y verificar."_

**Frase que debe quedar:**

> **No le pedimos a la IA que adivine qué es correcto. Se lo contamos antes de que toque el resultado.**

**Pregunta anticipada: “¿Solo sirve para funcionalidades nuevas?”**

_"No. En una corrección de error puede ser incluso más valioso, porque el escenario describe el comportamiento que hoy falla y que no debe volver a romperse."_

```gherkin
Feature: Carrito de compra
  Scenario: No permitir comprar con stock a cero
    Given que una pieza de resina tiene 0 unidades en stock
    When intento añadirla al carrito
    Then el sistema me impide añadirla
    And veo un mensaje de "sin stock"
```

_"La diferencia no es solo ‘lo arreglé’. Es ‘no puede volver a pasar sin que una comprobación salte’."_

**Reserva técnica, solo si preguntan:** Gherkin no ejecuta nada por sí mismo. Normalmente se conecta con código mediante herramientas de automatización. En la demo, la IA leerá el escenario y contrastará el comportamiento implementado con ese criterio.

**Por qué se cambia:** el ejemplo cotidiano reduce la barrera técnica. Los nombres BDD y Gherkin aparecen después de entender el patrón, evitando que las siglas se conviertan en el tema.

## Bloque 3 — Demo: primero el criterio, después el código — 10 min

**Caso:** el carrito de RCA. Se reutiliza el mismo escenario mostrado antes para no introducir un segundo problema durante la demo.

```gherkin
Feature: Carrito de compra
  Scenario: Añadir una pieza al carrito
    Given que estoy viendo la ficha de un anillo de resina
    And el carrito está vacío
    When pulso "Añadir al carrito"
    Then el carrito muestra 1 artículo
    And el precio del anillo se suma al total
```

**Secuencia:**

1. Mostrar el escenario ya escrito. Redactarlo entero en vivo añade riesgo y no refuerza la tesis.
2. Pasarlo a la IA con el contexto necesario de RCA.
3. Pedir que implemente o ajuste la funcionalidad.
4. Pedir que verifique el resultado contra el mismo escenario.
5. Mostrar evidencia observable para cada `Then`.

**Pausa deliberada tras verificar:**

_"Fijaos en lo que NO ha ocurrido."_

_"No hemos discutido si nos gusta. No hemos discutido si ‘parece que funciona’. No hemos permitido interpretaciones distintas sobre el resultado. El criterio estaba escrito antes de empezar y, al terminar, lo hemos contrastado con ese mismo criterio."_

_"Esto no significa que una comprobación garantice toda la calidad. Significa algo más preciso: para este comportamiento concreto sabemos de antemano qué evidencia necesitamos observar."_

**En pantalla:**

> **El escenario no se negocia después. Se escribe antes.**

**Por qué se cambia:** la pausa transforma la demo en aprendizaje. Sin ella, la sala podría recordar únicamente que la IA programó un carrito y perder la idea central.

## Bloque 4 — Un comportamiento proporcional por defecto — 9 min

_"Ahora aparece el problema contrario. ¿Escribiríamos un escenario formal para cambiar el color de un botón o corregir una errata? No. Si cada cambio pequeño activara un proceso completo, añadiríamos más fricción que valor."_

_"Veamos primero dos comportamientos y después les ponemos nombre."_

### Caso 1: cambio pequeño

**Petición:** “Cambia el color del botón de Añadir al carrito a un tono más cálido.”

```text
Explora lo necesario
→ determina que es un cambio pequeño
→ realiza el cambio
→ muestra una comprobación observable
→ termina sin documentación innecesaria
```

### Caso 2: cambio sustancial

**Petición:** “Añade códigos de descuento al carrito.”

```text
Explora el proyecto
→ detecta varios pasos reales
→ crea antes un documento con objetivo, alcance, límites y tareas
→ trabaja tarea por tarea
→ cierra cada tarea con evidencia
```

_"No hay un agente para cambios pequeños y otro para cambios grandes. Es el mismo modelo siguiendo un protocolo persistente: primero explora, después clasifica y solo entonces actúa."_

_"Ese comportamiento por defecto tiene un nombre en el enfoque que estamos usando: ODD, Organic Driven Development. Pero la sigla no es lo importante. Lo importante es que el agente no improvisa el proceso en cada conversación."_

**Reglas que sí merece la pena contar:**

- Si la petición solo pide explicar o investigar, no modifica nada.
- Explora en proporción al cambio.
- Solo pregunta cuando existe una duda relevante.
- Distingue trabajo pequeño de trabajo sustancial.
- Para trabajo sustancial, deja plan y criterios antes de modificar código.
- No declara una tarea terminada sin evidencia observada.

_"¿Dónde entra BDD? Cuando el comportamiento importa o el riesgo merece dejar el criterio por escrito. ODD aporta disciplina proporcional por defecto. BDD formaliza qué significa correcto cuando nuestro criterio profesional decide que hace falta."_

_"Esto es, además, la respuesta formal a algo que dejamos abierto en la charla 16: ¿spec manual o SDD con OpenSpec para cada tarea? Ya no lo decide el tamaño ni el riesgo del cambio por sí solos — lo decidís vosotros, explícitamente, pidiendo spec o escenario. Todo lo demás, por defecto, es esto que acabamos de ver."_

```text
Por defecto
→ explorar, clasificar, actuar y demostrar

Cuando el comportamiento importa o el riesgo lo exige
→ escribir el criterio de éxito antes de construir
```

### Ahora sí: el arnés recibe nombre

_"Todo lo que llevamos varias charlas colocando alrededor de la IA —instrucciones persistentes, memoria, skills, MCPs, especificaciones, criterios, comprobaciones y límites— tiene un nombre en la industria: AI harness engineering."_

_"No consiste en cambiar el motor. Consiste en diseñar la disciplina, las herramientas y las verificaciones que rodean al modelo para que el sistema sea más útil y controlable."_

**Frase que debe quedar:**

> **El arnés no hace más inteligente al modelo. Hace más disciplinado el sistema.**

**Reserva técnica:** no explicar el umbral exacto de clasificación, los commits por tarea ni el árbol completo ODD/SDD/BDD salvo pregunta. Son detalles válidos, pero competirían con la tesis.

**Nota para Juan:** el protocolo ODD y la convención BDD están añadidos a `CLAUDE.md` y `.github/copilot-instructions.md` de RCA en `develop`. La demo ODD solo debe hacerse en vivo si el ensayo reproduce de forma estable ambos comportamientos. Si no, utilizar capturas o una secuencia preparada. La tesis no puede depender de que el modelo clasifique perfectamente una petición en directo.

**Nota para Juan (revisión):** ODD nunca activa por sí sola la revisión de código (RDD, reservado para la charla futura de ai-code-review) — son interruptores separados, uno no enciende al otro. No hace falta mencionar RDD por nombre en la sala; solo evitar que, si alguien pregunta por revisión de PRs aquí, suene como si ya se hubiera cubierto.

**Por qué se cambia:** ODD se entiende primero mediante conductas observables. AI harness engineering llega como conclusión que organiza algo que la audiencia ya ha visto, no como una etiqueta abstracta de apertura. Se mantiene en el cierre del bloque (y no al principio de la charla, como en el borrador anterior) porque el resto de la sesión ya está construida como una progresión hacia ese nombre — moverlo a la apertura rompería ese arco sin arreglar nada más.

## Bloque 5 — Cierre: verificar vale más que generar — 4 min

_"Recolocadlo en el ciclo anterior. Hoy hemos trabajado la mitad de Comprobar que ocurre ANTES de construir: definir el resultado esperado y decidir cuánta formalidad merece cada tarea."_

_"Para lo importante, el criterio de éxito se escribe. Para lo pequeño, el agente sigue una disciplina proporcional. En ambos casos evitamos que sea la IA quien decida sin reglas qué significa que algo está bien."_

> **Verifying beats generating. Verificar vale más que generar.**

_"La calidad de una solución generada por IA no depende de lo bien que genere. Depende de lo claro que hayamos definido qué significa que esté bien y de la evidencia con la que podamos comprobarlo."_

**Puente:**

_"Hoy hemos comprobado antes de construir. Queda la otra mitad: revisar lo que ya se ha construido, detectar problemas y demostrar que sigue cumpliendo lo esperado. Esa tendrá su propia charla y su propia demo."_

**Última pantalla:**

> **La IA es muy buena generando.**
>
> **El trabajo profesional consiste en definir y comprobar qué resultado es el correcto.**

**Por qué se cambia:** se conserva la frase de industria, pero se traduce en una conclusión propia y accionable. La audiencia no necesita recordar las siglas para recordar el criterio profesional.

## Checklist antes del miércoles

### Contenido
- [ ] Visual del ciclo de seis pasos de la charla 22.
- [ ] Pantalla con la tesis: «La IA no debería decidir por sí sola qué significa correcto».
- [ ] Ejemplo de vacaciones antes de login y RCA.
- [ ] BDD, ODD y AI harness engineering solo después de explicar la idea que representa cada término.

### Demo BDD
- [ ] RCA y escenario del carrito abiertos antes de comenzar.
- [ ] Ruta de recuperación preparada: código o commit previo para continuar si falla la generación.
- [ ] Evidencia observable para cada `Then`.
- [ ] Pausa preparada: «Fijaos en lo que NO ha ocurrido».

### ODD
- [ ] Ensayar «cambiar color» y «añadir descuentos».
- [ ] Demo en vivo solo si el comportamiento es estable.
- [ ] Si no lo es, usar capturas o una secuencia preparada. No presentar como determinista lo que no lo es.

### Ensayo narrativo
- [ ] Cronometrar 3 + 8 + 10 + 9 + 4 minutos — cronometrar el Bloque 4 por separado: ahora concentra dos momentos clave (los dos casos ODD y el nombre del arnés) en solo 9 min.
- [ ] Comprobar que ninguna sigla aparece antes de entender su función.
- [ ] Mantener tres frases principales:
  1. «No le pedimos a la IA que adivine qué significa correcto».
  2. «El escenario no se negocia después. Se escribe antes».
  3. «Verificar vale más que generar».

## Decisiones aplicadas y motivo

- **Tesis central:** una sola idea gobierna la charla: definir y comprobar qué significa correcto. Reduce la carga cognitiva.
- **AI harness engineering:** se mueve al final del bloque 4, como conclusión tras mostrar ODD en acción — decisión tomada a propósito, no heredada: rompe la apertura original (donde el nombre daba autoridad desde el minuto 1) a cambio de un remate más fuerte.
- **Ejemplo no técnico:** vacaciones abre BDD. Permite que la audiencia no técnica entienda el patrón antes del código.
- **BDD/Gherkin:** se reduce a la estructura mínima necesaria. La sintaxis no compite con el aprendizaje.
- **Demo:** reutiliza el escenario del carrito y añade una pausa narrativa. Se destaca el criterio previo, no la capacidad de generación.
- **ODD:** se presenta mediante dos comportamientos observables. La teoría se explica después de ver sus efectos.
- **Siglas:** cada término se retrasa hasta después de explicar su función.
- **Callback a la 16:** recuperado como una frase dentro del Bloque 4 — la pregunta abierta en esa charla (spec manual vs OpenSpec) tiene ahora respuesta formal y explícita, no solo disponible si alguien pregunta.
- **Separación ODD/RDD:** recuperada como nota solo para Juan — evita dar la impresión en Q&A de que la revisión de código ya se cubrió.
- **Cierre:** «verifying beats generating» se acompaña de una conclusión propia y accionable.
- **Revisión posterior:** continúa fuera de esta sesión para preservar el foco.
