---
type: Material
title: "Material Charla 23 — Comprobar antes de construir"
description: "Material post-charla 23. Cierra la mitad 'antes de construir' de la etapa Comprobar (ciclo de la 22): BDD y Gherkin para contar el resultado esperado como una historia, ODD como disciplina proporcional por defecto para el resto, y el arnés recibiendo por fin su nombre de industria — AI harness engineering. Incluye la demo real sobre RCA y el hallazgo en vivo de que ODD y BDD no compiten, están anidados. Récord de asistencia de la serie: 141 personas."
tags: [material, charla-23, bdd, gherkin, odd, ai-harness-engineering, verificacion, comprobar, rca]
related:
  - "[[guion-charla-23]]"
  - "[[bdd]]"
  - "[[odd]]"
  - "[[gherkin]]"
  - "[[ai-harness-engineering]]"
  - "[[arnes-completo]]"
  - "[[guion-charla-16]]"
  - "[[guion-charla-22]]"
charla: 23
estado: borrador
timestamp: "2026-10-14"
---

# Material Charla 23 — Comprobar antes de construir

## Qué vimos en la charla

### El punto de partida: ¿quién decide qué es "correcto"?

La Charla 22 dejó una pregunta abierta: antes de construir, hay que preguntarle primero a la IA — pero ¿preguntarle primero qué, exactamente? ¿Cómo sabe la IA cuándo ha terminado bien una tarea, y cuándo solo cree que la ha terminado?

Esa es la pregunta que abre la etapa de **Comprobar** del ciclo de trabajo con IA que venimos construyendo desde la 22. Comprobar tiene dos mitades: una antes de construir (contar qué significa "correcto" antes de que exista una sola línea de código) y otra después de construir (revisar lo que ya existe en producción). La Charla 23 cierra la primera mitad. La segunda queda reservada para una charla futura, con su propio framework.

### Contar el resultado esperado antes de construir: BDD y Gherkin

**BDD (Behavior-Driven Development)** es la respuesta a la pregunta de apertura: en lugar de describir el código que hay que escribir, se describe el comportamiento que el sistema debe tener, contado como una historia con una estructura fija. Esa estructura se llama **Gherkin**, y usa siempre las mismas tres palabras clave:

| Palabra clave | Qué expresa |
|---|---|
| `Given` (Dado) | El estado de partida — el contexto antes de que pase nada |
| `When` (Cuando) | La acción que dispara el comportamiento |
| `Then` (Entonces) | El resultado esperado — lo que tiene que ser verdad al final |

Un ejemplo sencillo, fuera de cualquier proyecto concreto:

```gherkin
Scenario: Solicitar vacaciones con días suficientes
  Given que el empleado tiene 10 días de vacaciones disponibles
  When solicita 5 días de vacaciones
  Then la solicitud se aprueba
  And el saldo de vacaciones queda en 5 días
```

Otro, sobre un flujo de login:

```gherkin
Scenario: Login con contraseña incorrecta
  Given que el usuario existe con email "ana@empresa.com"
  When intenta iniciar sesión con la contraseña incorrecta
  Then el sistema rechaza el acceso
  And muestra el mensaje "Credenciales incorrectas"
```

Y uno ya aplicado a RCA (Resin Craft Art), el proyecto que usamos como vehículo de demo en toda la serie:

```gherkin
Scenario: Añadir una pieza al carrito con stock disponible
  Given que la pieza "Jarrón Ámbar" tiene 3 unidades en stock
  When el cliente añade 1 unidad al carrito
  Then el carrito muestra 1 unidad de "Jarrón Ámbar"
  And el stock disponible pasa a ser 2
```

Lo importante de Gherkin no es la sintaxis — es que convierte "esto tiene que funcionar bien" en una frase que tanto una persona como una IA pueden leer igual, sin ambigüedad. Ese escenario se escribe **antes** de tocar código, y se convierte en el criterio contra el que se juzga el resultado.

Un cuarto ejemplo, el que conecta con lo que vino después en la charla — un bug real de stock a cero:

```gherkin
Scenario: Intentar añadir al carrito una pieza sin stock
  Given que la pieza "Cuenco Terracota" tiene 0 unidades en stock
  When el cliente intenta añadir 1 unidad al carrito
  Then el sistema rechaza la operación
  And muestra el mensaje "Sin stock disponible"
```

### La demo: primero el criterio, después el código

La demo de la charla no generó el escenario Gherkin en directo — se construyó de antemano ("ya creada"), por la misma razón que ya aparece como principio en el vault: cuando lo que está en juego es precisamente que la IA clasifique bien una situación delante de la sala, la tesis no puede depender de que el modelo acierte en tiempo real. Lo que sí se mostró en vivo fue el resultado: partiendo del escenario del stock a cero, se guio a la IA para implementar primero el test que lo expresa, y después el código mínimo que lo hace pasar. El orden importa — primero el criterio, después la solución.

### El comportamiento por defecto: ODD

BDD resuelve la mitad "esto es correcto" cuando el cambio es sustancial y merece un escenario completo. Pero no todo lo que se le pide a una IA necesita ese nivel de ceremonia. Hace falta una disciplina que decida, por defecto, cuánto proceso merece cada petición — y esa disciplina es **ODD (Outcome-Driven Development)**.

La charla lo mostró con dos casos contrastados, ambos sobre RCA:

**Caso 1 — cambio pequeño:** "Cambia el color del botón de 'Añadir al carrito' a un tono más cálido." Es una petición acotada, de bajo riesgo, reversible con un solo commit. ODD dice: hazlo directamente, sin documentar tareas ni abrir una carpeta de seguimiento. La proporcionalidad exige no gastar ceremonia donde no hace falta.

**Caso 2 — cambio sustancial:** "Añade códigos de descuento al carrito." Esto toca varias piezas (modelo de datos, validación, cálculo del total, interfaz), y antes de escribir una línea, ODD exige dejar por escrito el objetivo, el alcance y las tareas en una carpeta de seguimiento — lo que en la charla se vio aparecer como una carpeta `odd/tasks/` nueva en el proyecto.

Reglas que gobiernan esta disciplina:

1. **Proporcionalidad por defecto.** El nivel de proceso se ajusta al riesgo y al tamaño del cambio, no a una regla fija para todo.
2. **El criterio vive en el proyecto, no en la cabeza de quien pide el cambio.** Por eso funciona igual la primera vez que la décima — está escrito en las instrucciones del proyecto.
3. **Cuando hay duda, se documenta.** Ante la ambigüedad entre "pequeño" y "sustancial", ODD empuja hacia dejar rastro antes que hacia improvisar.

Esto conecta directamente con la Charla 16: lo que entonces se presentó como un protocolo para que la IA explorara un proyecto por su cuenta, hoy se ve como la misma lógica aplicada específicamente a decidir cuánta ceremonia merece cada tarea.

### Ahora sí: el arnés recibe nombre — AI harness engineering

Desde la Charla 13, la serie viene construyendo, pieza a pieza, lo que el vault llama el **arnés completo**: instrucciones persistentes, skills, MCPs, documentación del proyecto, wiki de conocimiento. Cada charla añadía una pieza sin que el conjunto tuviera, todavía, un nombre que lo describiera desde fuera de este vault.

La Charla 23 cerró ese hueco: lo que se lleva once charlas construyendo tiene nombre de industria, y es **AI harness engineering**. No es un término inventado para esta serie — es como el sector ya se refiere a la disciplina de diseñar el conjunto de restricciones, contexto y protocolos que hacen que un agente de IA se comporte de forma fiable y predecible, en lugar de depender de que cada petición individual salga bien por azar. BDD y ODD son, vistos así, dos piezas más del mismo arnés: la parte que decide qué significa "terminado correctamente" antes de que el agente escriba nada.

### Lo que pasó de verdad en la demo (y por qué importa)

Dos hallazgos de la propia preparación de la charla merecen quedar por escrito, porque no estaban planeados como contenido — surgieron de ensayar la demo:

1. **La decisión de pre-construir la demo no fue por comodidad, fue por tesis.** Si la demo dependía de que la IA clasificara bien, en directo, un cambio como "pequeño" o "sustancial", y fallaba delante de 141 personas, la charla entera habría quedado desacreditada en el peor momento posible. Pre-construir la demo protege la tesis de la charla, no solo el tiempo de la sesión.

2. **ODD y BDD no compiten — están anidados.** Este fue el hallazgo más importante, y se descubrió en vivo durante los ensayos, no estaba planeado de antemano: ODD decide *si* un cambio merece el nivel de ceremonia de BDD; BDD, cuando se activa, decide *qué* significa que ese cambio concreto esté bien hecho. No son dos frameworks alternativos entre los que elegir — uno vive dentro del otro. ODD es la capa que filtra cuánto proceso corresponde; BDD es el proceso en sí cuando corresponde el máximo.

### Cierre: verificar vale más que generar

La idea de cierre de la charla fue deliberadamente incómoda: escribir código con IA ya no es el cuello de botella — generar código es rápido y cada vez más barato. Lo que de verdad protege la calidad de un proyecto es la capacidad de **comprobar** que lo generado hace lo que se pretendía, antes de que llegue a producción. BDD y ODD son dos maneras concretas de instalar esa comprobación antes de construir. La otra mitad — comprobar lo que ya existe — queda para una charla futura.

## Glosario de conceptos vistos hoy

### [[bdd]] — BDD (Behavior-Driven Development)
Metodología que describe el comportamiento esperado de un sistema como una historia legible por personas y por IA, antes de escribir el código que lo implementa. Se apoya en la sintaxis Gherkin (`Given`/`When`/`Then`) para fijar, sin ambigüedad, cuándo un resultado es correcto.

### [[gherkin]] — Gherkin
Sintaxis estructurada en tres palabras clave (`Given`, `When`, `Then`) usada para escribir escenarios de comportamiento dentro de BDD. Convierte una expectativa en lenguaje natural en un criterio verificable.

### [[odd]] — ODD (Outcome-Driven Development)
Disciplina que decide, de forma proporcional al riesgo y tamaño de cada petición, cuánto proceso merece — desde un cambio directo sin documentación hasta una carpeta de seguimiento con objetivo, alcance y tareas. Es la capa que filtra cuándo activar algo como BDD.

### ODD y BDD, anidados, no alternativos
Hallazgo central de la charla: ODD decide *si* un cambio necesita el nivel de rigor de BDD; BDD, cuando se activa, decide *qué* significa "correcto" para ese cambio concreto. No son opciones entre las que elegir — uno contiene al otro.

### [[ai-harness-engineering]] — AI harness engineering
Nombre de industria para la disciplina de diseñar el conjunto de restricciones, contexto y protocolos (instrucciones, skills, MCPs, documentación de proyecto, wiki de conocimiento) que hacen que un agente de IA se comporte de forma fiable. Es el nombre que recibe, desde la Charla 23, lo que el vault venía llamando "el arnés completo" desde la Charla 13.

## Ideas para llevarse

1. **Contar el resultado esperado antes de construir cuesta poco y evita mucho.** Un escenario Gherkin de cuatro líneas es más barato que descubrir en producción que "correcto" significaba algo distinto para cada persona del equipo.
2. **No todo merece el mismo proceso.** ODD existe precisamente para no gastar la misma ceremonia en un cambio de color que en un sistema de descuentos.
3. **El criterio tiene que vivir en el proyecto, no en la memoria de quien pregunta.** Es la única forma de que la disciplina sea consistente la primera vez y la centésima.
4. **Generar ya no es el reto — comprobar sí lo es.** Cuanto más fácil es que una IA escriba código, más vale la capacidad de verificar que ese código hace lo correcto.

## Enlaces

- [[guion-charla-23]] — guión completo de la charla
- [[charla-23-comprobar-antes-de-construir]] — resumen breve y asistencia
- [[bdd]]
- [[gherkin]]
- [[odd]]
- [[ai-harness-engineering]]
- [[guion-charla-16]] — protocolo de exploración del que deriva parte de la lógica de ODD
- [[guion-charla-22]] — charla anterior, IA-first mindset

*Charla 23 — Serie de formación interna en IA*
