---
type: guion
title: "Charla 24 — Comprobar después de construir: ai-code-review y RDD"
description: "Cierra la mitad posterior de Comprobar, abierta en la charla 22 y preparada en la 23. Explica cómo revisar cambios generados con IA mediante checks deterministas, revisión agéntica proporcional al riesgo, evidencia vinculada a un candidato concreto y decisión humana final."
tags: [charla, guion, ai-code-review, rdd, receipt-driven-development, revision, pull-request, verificacion, comprobar, rca, 4r]
related: [guion-charla-23, guion-charla-08, guion-charla-22, ai-code-review, rdd, bdd, odd, ai-harness-engineering, arnes-completo]
charla: 24
estado: revisado
timestamp: 2026-10-27
---

# Guión Charla 24 — Comprobar después de construir: ai-code-review y RDD

## 28 de octubre de 2026

Esta charla cierra la etapa **Comprobar** del ciclo presentado en la charla 22. La charla 23 explicó la mitad anterior a la construcción: definir qué significa correcto mediante BDD y aplicar una disciplina proporcional mediante ODD. Esta sesión aborda la mitad posterior: una vez que existe un candidato de código, ¿qué evidencia necesitamos antes de aceptarlo?

La demo reutiliza deliberadamente dos peticiones conocidas por la audiencia:

- cambiar el color del botón «Añadir al carrito»;
- impedir comprar una pieza con stock cero.

El objetivo no es enseñar otra vez cómo genera código la IA. El objetivo es mostrar que **dos cambios no deben recibir automáticamente la misma revisión** y que una revisión útil no termina en «el agente dice que está bien»: debe dejar evidencia trazable sobre una versión concreta del cambio.

> [!important] Tesis central
> **Antes definimos qué significa correcto. Después exigimos evidencia de que un candidato concreto lo cumple.**

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|---|---|---:|
| 1. Apertura | Callback a la charla 23 y pregunta de hoy | 3 min |
| 2. El nuevo cuello de botella | De producir cambios a demostrar que son aceptables | 5 min |
| 3. El reviewer ya existía | Qué teníamos en la charla 8 y qué faltaba | 3 min |
| 4. Demo de contraste | Dos PR abiertas, dos profundidades, dos receipts | 12 min |
| 5. RDD con nombre | Candidato congelado, riesgo, lentes 4R y receipt | 8 min |
| 6. Cierre | El arco completo de Comprobar | 4 min |

**Total aproximado: 35 minutos**, con las preguntas concentradas al final o durante las dos pausas previstas.

---

# Bloque 1 — Apertura: queda la otra mitad — 3 min

_«La charla anterior terminó con una frase: “Hoy hemos comprobado antes de construir. Queda la otra mitad”. Hoy vamos a cerrar esa otra mitad.»_

_«En la charla 23 dijimos que la IA no debería decidir sola qué significa correcto. Para lo importante escribimos el criterio antes, con BDD. Para el trabajo cotidiano dejamos una disciplina proporcional por defecto, con ODD. Todo eso ocurre antes o durante la construcción.»_

_«Pero llega un momento en que el código ya existe. Tenemos un candidato delante. Entonces la pregunta cambia: ¿qué evidencia necesitamos antes de confiar en él?»_

## En pantalla

```text
ANTES DE CONSTRUIR
BDD + ODD
¿Qué significa correcto y qué disciplina seguimos?

                  ↓

DESPUÉS DE CONSTRUIR
Checks + ai-code-review + RDD
¿Qué evidencia demuestra que este candidato es aceptable?
```

## Frase que debe quedar

> **Definir qué es correcto y demostrar que un resultado lo cumple son dos momentos diferentes.**

## Nota narrativa

No reconstruir toda la charla 23. El público solo necesita recordar tres piezas:

1. existía un criterio previo;
2. la IA construyó un candidato;
3. ahora debemos decidir si la evidencia justifica aceptarlo.

---

# Bloque 2 — El nuevo cuello de botella — 5 min

_«Durante años, el coste principal estaba en producir el cambio: entenderlo, escribirlo y hacerlo funcionar. Con agentes de IA podemos generar candidatos mucho más deprisa. Pero eso no elimina el trabajo. Desplaza parte del coste hacia demostrar que esos candidatos son aceptables.»_

_«Si un agente genera diez cambios en una tarde y todos dependen de una lectura manual completa, el tapón ya no está solo en escribir código. Está en revisarlo y, sobre todo, en obtener evidencia fiable.»_

## Frase que debe quedar

> **La IA abarata producir candidatos. No abarata automáticamente demostrar que son correctos.**

_«La respuesta no es revisar menos ni aceptar más deprisa. Es revisar por capas, empezando por lo barato y determinista, y reservando el juicio humano para los riesgos que de verdad lo necesitan.»_

## En pantalla: revisión en capas

| Capa | Qué aporta | Qué no debe hacer |
|---|---|---|
| 1. Checks deterministas | Build, lint, tests, análisis estático, políticas automatizadas | No interpretan por sí solos la intención completa del cambio |
| 2. Revisión agéntica | Contrasta el candidato con criterios, convenciones y señales de riesgo | No obtiene autoridad para fusionar, publicar o aceptar el riesgo |
| 3. Revisión humana | Decide si la evidencia es suficiente y si el riesgo es aceptable | No debería gastar tiempo repitiendo comprobaciones mecánicas ya automatizadas |

_«El ojo humano es el recurso escaso. Debemos gastarlo en decisiones, no en repetir comprobaciones que una máquina puede ejecutar de forma reproducible.»_

## Pregunta anticipada: «¿Y si el agente revisor se equivoca?»

_«Puede equivocarse. Un verde falso es especialmente peligroso porque crea confianza injustificada. Por eso la revisión agéntica no recibe autoridad de entrega. Produce evidencia y observaciones; la política del repositorio y la persona responsable mantienen la decisión final.»_

## Matiz importante

No presentar las tres capas como una garantía acumulativa perfecta. Un lint verde no demuestra la funcionalidad. Un test solo demuestra aquello que realmente comprueba. Un reviewer puede omitir riesgos. La solidez aparece cuando cada afirmación se apoya en una evidencia pertinente y trazable.

---

# Bloque 3 — El reviewer ya existía — 3 min

_«Esto no empieza hoy. En la charla 8 vimos un agente reviewer sobre RCA. Solo leía, no escribía. Contrastaba el cambio con el task.md, las convenciones del proyecto y la cobertura de tests.»_

_«Aquel agente ya podía emitir una opinión. Pero nos faltaban dos propiedades: proporcionalidad y trazabilidad.»_

## En pantalla

```text
Charla 8
Reviewer que inspecciona y comenta

Hoy añadimos
1. Proporcionalidad: no todo cambio merece la misma profundidad
2. Trazabilidad: la evidencia debe corresponder a una versión concreta
```

## Frase que debe quedar

> **El reviewer ya existía. Ahora le damos reglas para revisar cada candidato con la profundidad que exige su riesgo y dejar constancia de qué ha comprobado.**

_«No queremos que el modelo improvise libremente cuánto revisar. Queremos que detecte señales, aplique una política explícita, proponga las lentes adecuadas y deje la decisión de entrega fuera del propio reviewer.»_

---

# Bloque 4 — Demo: dos PR abiertas, dos profundidades y dos receipts — 12 min

> [!warning] Preparación
> Las dos PR deben estar generadas y abiertas, no fusionadas. La revisión forma parte de la decisión anterior al merge. Tener capturas y resultados guardados como ruta de recuperación.

## Introducción de la demo

_«Las dos PR ya están generadas y preparadas. Hoy no vamos a construir código en directo. Vamos a decidir qué evidencia necesita cada candidata antes de aceptarla.»_

_«Son las mismas peticiones que utilizamos en la charla 23. Así no perdemos tiempo explicando ejemplos nuevos y podemos centrarnos en la diferencia de revisión.»_

---

## Caso A — Cambio pequeño: color del botón

**Petición:** cambiar el color del botón «Añadir al carrito» a un tono más cálido.

### Evidencia mínima pertinente

1. El proyecto compila.
2. Lint y tests existentes no introducen regresiones conocidas.
3. La aplicación muestra el botón con el nuevo color.
4. El texto sigue siendo legible sobre el fondo.
5. La evidencia corresponde al commit o candidato que estamos revisando.

### Secuencia en directo

- Abrir la PR A y mostrar el commit candidato.
- Mostrar checks verdes.
- Enseñar una captura o comprobación visual del botón.
- Mostrar el receipt breve.

### Receipt simplificado para la demo

```text
Candidato: PR A / commit <SHA-A>
Petición: cambiar el color del botón «Añadir al carrito»
Riesgo: bajo
Evidencia:
  - build: pass
  - lint: pass
  - tests existentes: pass
  - comprobación visual: pass
  - legibilidad del texto: comprobada
Resultado propuesto: aceptable para revisión humana breve
Autoridad de entrega: humana
```

_«Un cambio pequeño no significa ausencia de evidencia. Significa evidencia barata, directa y proporcionada a lo que se cambió.»_

### Pregunta a la sala

_«¿Necesitamos aquí una revisión arquitectónica completa, analizar concurrencia y recorrer las cuatro lentes?»_

Dejar responder y cerrar:

_«No. Necesitamos demostrar el cambio exacto, detectar regresiones razonables y conservar la relación entre esa evidencia y esta versión concreta.»_

---

## Caso B — Cambio sustancial: no comprar con stock cero

**Criterio escrito en la charla 23:**

```gherkin
Feature: Carrito de compra
  Scenario: No permitir comprar con stock a cero
    Given que una pieza de resina tiene 0 unidades en stock
    When intento añadirla al carrito
    Then el sistema me impide añadirla
    And veo un mensaje de "sin stock"
```

### Primera parte: comprobar el criterio conocido

- Mostrar la PR B y el commit candidato.
- Mostrar build, lint y tests.
- Contrastar cada `Then` contra evidencia observable.
- Verificar que el rechazo ocurre en el comportamiento real que controla la compra, no solo en una representación visual.

_«Aquí el escenario de la charla 23 funciona como vara de medir. El criterio escrito antes de construir reaparece después como una obligación verificable.»_

### Segunda parte: buscar riesgos que el escenario no expresó

_«Pero cumplir este escenario no demuestra todo lo que puede importar. El escenario cubre stock cero. No cubre qué ocurre cuando queda una unidad y dos compradores intentan adquirirla a la vez.»_

```text
Estado inicial: stock = 1
Comprador A consulta el stock
Comprador B consulta el stock
A y B intentan confirmar casi simultáneamente

Pregunta de revisión:
¿Dónde se garantiza que solo una operación puede consumir la última unidad?
```

_«Esto es importante: la revisión profunda no solo comprueba criterios existentes. También puede descubrir criterios que faltaban. Si la concurrencia es un riesgo real del sistema, debemos convertirla en una nueva prueba o en un nuevo escenario, no dejarla como una observación verbal.»_

### Receipt ampliado para la demo

```text
Candidato: PR B / commit <SHA-B>
Petición: impedir añadir al carrito una pieza con stock cero
Riesgo: alto por integridad de inventario y posible operación incorrecta

Evidencia del criterio original:
  - build: pass
  - lint: pass
  - tests: pass
  - rechazo con stock 0: demostrado
  - mensaje «sin stock»: demostrado

Revisión adicional:
  - Risk: identificado impacto sobre inventario y compra
  - Resilience: detectado riesgo de concurrencia sobre la última unidad
  - Readability: revisada claridad de la regla y su localización
  - Reliability: criterio Gherkin cubierto por evidencia reproducible

Hallazgo abierto:
  - falta demostrar o proteger la operación concurrente sobre la última unidad

Resultado propuesto:
  - no aceptar todavía hasta resolver o justificar el hallazgo

Autoridad de entrega: humana
```

### Pausa deliberada

_«Fijaos en lo que ha decidido la diferencia. No es el número de líneas ni el número de archivos. Es la consecuencia de equivocarnos y la evidencia disponible para detectarlo.»_

## Frase en pantalla

> **El tamaño del diff no decide cuánto revisar. El riesgo y la evidencia disponible, sí.**

## Segunda frase que debe quedar

> **La revisión no solo comprueba criterios. También descubre criterios que faltaban.**

---

# Bloque 5 — RDD con nombre — 8 min

_«Lo que acabamos de ver tiene un nombre: Receipt-Driven Development, RDD.»_

_«La palabra importante no es solo review. Es receipt: recibo. Una revisión útil no debería terminar en “el agente dice que está bien”. Debe dejar constancia de qué candidato exacto se revisó, qué comprobaciones se hicieron, qué evidencia se obtuvo, qué hallazgos quedaron abiertos y quién conserva la autoridad de entrega.»_

## 5.1. Qué es un candidato congelado

_«La evidencia tiene que estar vinculada a una versión concreta. Si revisamos un commit y después cambiamos el código, el receipt anterior ya no demuestra nada sobre el nuevo candidato.»_

## En pantalla

```text
Candidato terminado
        ↓
Congelar la versión que se va a revisar
        ↓
Checks + lentes de revisión
        ↓
Evidencia y hallazgos
        ↓
Receipt ligado al candidato
        ↓
Decisión humana de aceptar, corregir o rechazar
```

## Frase que debe quedar

> **Un receipt no certifica “el proyecto”. Registra la evidencia obtenida sobre un candidato concreto.**

---

## 5.2. Profundidad proporcional al riesgo

_«Para entenderlo hoy vamos a simplificar la profundidad en tres niveles. Esta tabla es una explicación pedagógica: lo importante es que la política determine la intensidad por señales de riesgo, no por intuición ni por volumen del diff.»_

| Profundidad para la charla | Cuándo encaja | Tratamiento |
|---|---|---|
| Baja | Cambio pasivo o visual acotado, sin señales críticas | Checks y evidencia directa del cambio |
| Media | Cambio ordinario de código con impacto localizado | Checks más una lente focalizada y contraste con el ticket |
| Alta | Seguridad, permisos, pagos, exposición o pérdida de datos, actualización, concurrencia u otra consecuencia difícil de revertir | Revisión profunda mediante las lentes 4R pertinentes y entrada humana explícita |

_«El agente puede detectar señales y proponer una profundidad. La política del proyecto puede establecer mínimos obligatorios. La persona responsable puede escalar la revisión cuando el contexto lo exige.»_

> **El modelo propone. La política limita. La persona decide.**

---

## 5.3. Las lentes 4R

_«En una revisión profunda podemos observar el candidato mediante cuatro lentes. No son cuatro sellos decorativos. Cada una obliga a formular una pregunta diferente y a buscar evidencia distinta.»_

### Risk

**Pregunta:** ¿qué daño puede causar este cambio si se equivoca?

En la PR de stock:

- vender una unidad que no existe;
- rechazar una compra válida;
- dejar inventario y operación comercial en estados incompatibles.

### Resilience

**Pregunta:** ¿se comporta correctamente en límites, fallos y condiciones adversas?

En la PR de stock:

- stock exactamente igual a cero;
- stock igual a uno;
- dos operaciones concurrentes;
- error al persistir la reducción del inventario.

### Readability

**Pregunta:** ¿otra persona puede comprender la regla, su ubicación y sus límites sin reconstruir toda la intención?

En la PR de stock:

- la regla no debe quedar duplicada de forma contradictoria;
- los nombres deben expresar la restricción;
- la decisión de negocio debe poder localizarse y mantenerse.

### Reliability

**Pregunta:** ¿qué evidencia reproducible detectaría una regresión?

En la PR de stock:

- escenario Gherkin de stock cero;
- prueba que materialice el comportamiento;
- resultado ligado al commit revisado;
- nueva prueba de concurrencia si ese riesgo forma parte del sistema real.

## Matiz que debe decirse en voz alta

_«No todas las PR necesitan ejecutar las cuatro lentes con la misma profundidad. Para cambios de alto riesgo, la política puede exigir una revisión completa. Para otros cambios, puede bastar una lente focalizada. Lo importante es que la elección sea justificable y quede registrada.»_

## Pregunta anticipada: «¿Quién decide el nivel?»

_«No debe depender únicamente del estado de ánimo del reviewer ni de una clasificación libre del LLM. Hay tres mecanismos: señales del cambio, política del repositorio y criterio profesional. El agente detecta y propone; la política fija límites; la persona responsable conserva la autoridad.»_

## Pregunta anticipada: «¿Un receipt garantiza que no hay errores?»

_«No. Un receipt registra qué se comprobó y con qué resultado. Su valor es hacer explícito el alcance de la evidencia y evitar que confundamos un “verde” genérico con una garantía universal.»_

## Reserva técnica, solo si preguntan

RDD no sustituye:

- los checks deterministas;
- BDD o los criterios de aceptación;
- la política de ramas y protección de repositorio;
- la revisión humana de cambios críticos;
- las pruebas especializadas de seguridad, carga, accesibilidad o concurrencia cuando sean necesarias.

RDD organiza la revisión, vincula evidencia al candidato y devuelve la decisión de entrega a la persona o proceso autorizado.

---

# Bloque 6 — Cierre: el arco completo de Comprobar — 4 min

_«Juntemos las dos charlas.»_

## En pantalla

```text
ANTES DE CONSTRUIR

BDD
Definimos el comportamiento esperado cuando importa

ODD
Aplicamos una disciplina proporcional por defecto

Pregunta:
¿Qué significa correcto?

────────────────────────────────────────

DESPUÉS DE CONSTRUIR

Checks deterministas
Descartamos fallos objetivos y repetibles

AI code review
Buscamos incumplimientos, riesgos y criterios ausentes

RDD
Vinculamos la evidencia a un candidato concreto

Pregunta:
¿Qué evidencia justifica aceptar este candidato?
```

_«ODD y RDD forman parte del mismo flujo, pero son decisiones independientes. Que ODD clasifique una tarea como sustancial no activa automáticamente una revisión 4R. Y que RDD detecte riesgo alto no nos dice qué método de construcción se utilizó. Cada mecanismo responde a una pregunta distinta.»_

_«La charla 23 dejó escrito el criterio de stock cero. La charla 24 ha usado ese criterio para revisar el candidato y, además, ha descubierto una pregunta nueva sobre concurrencia. Ahí se cierra el ciclo: especificar, construir, comprobar, aprender y mejorar el criterio.»_

## Frase final

> **Generar produce un candidato. Verificar produce evidencia. Un receipt deja constancia de por qué confiamos, o de por qué todavía no debemos confiar.**

_«Con esto cerramos Comprobar dentro del ciclo de seis pasos de la charla 22: idea, especificar, construir, comprobar, publicar y mantener. Quedan Publicar y Mantener, pero esa es otra charla.»_

---

# Glosario breve para la audiencia

## Check determinista

Comprobación con un resultado reproducible frente a una condición definida, por ejemplo build, lint, tests o una política automatizada. Un resultado verde solo demuestra aquello que el check comprueba.

## AI code review

Uso de un agente para inspeccionar un candidato, contrastarlo con criterios y convenciones, y señalar riesgos o incumplimientos. Produce observaciones y evidencia, no autoridad automática de entrega.

## Candidato

Versión concreta del cambio que se presenta a revisión. Puede representarse mediante una PR, una rama o un commit identificable.

## Candidato congelado

Candidato cuyo contenido no cambia mientras se obtiene la evidencia. Si el contenido cambia, debe revisarse la nueva versión.

## Receipt

Registro trazable de la revisión: candidato, checks, lentes aplicadas, evidencia, hallazgos y resultado. No es una garantía universal ni reemplaza la decisión humana.

## RDD

Receipt-Driven Development. Enfoque que organiza una revisión acotada y auditable, proporcional al riesgo y ligada a un candidato concreto, sin apropiarse de la decisión de entrega.

## 4R

Cuatro lentes de revisión: Risk, Resilience, Readability y Reliability. Ayudan a separar tipos de preguntas que podrían quedar mezcladas en una revisión genérica.

---

# Checklist antes del miércoles

## Contenido

- [x] Fecha actualizada al 28 de octubre de 2026.
- [ ] Pantalla con la frase final de la charla 23.
- [ ] Esquema de las tres capas de revisión.
- [ ] Visual «candidato → evidencia → receipt → decisión humana».
- [ ] Tabla pedagógica de profundidad baja, media y alta.
- [ ] Diapositiva de las 4R con una pregunta por lente.
- [ ] Pantalla final que conecta BDD, ODD, checks, ai-code-review y RDD.

## Demo

- [ ] PR A abierta y sin fusionar.
- [ ] Commit de PR A identificado como `<SHA-A>`.
- [ ] Checks de PR A guardados.
- [ ] Captura o evidencia visual del botón.
- [ ] Receipt breve de PR A.
- [ ] PR B abierta y sin fusionar.
- [ ] Commit de PR B identificado como `<SHA-B>`.
- [ ] Evidencia para cada `Then` del escenario Gherkin.
- [ ] Hallazgo de concurrencia preparado como riesgo adicional, no como criterio ya cubierto.
- [ ] Receipt ampliado de PR B.
- [ ] Ruta de recuperación con capturas de ambas revisiones.
- [ ] Verificar que ninguna captura muestre un estado contradictorio con el relato.

## Ensayo narrativo

- [ ] Cronometrar 3 + 5 + 3 + 12 + 8 + 4 minutos.
- [ ] No nombrar RDD hasta después del contraste entre PR A y PR B.
- [ ] Diferenciar «check verde» de «funcionalidad demostrada».
- [ ] Explicar que cambiar el candidato invalida el receipt anterior.
- [ ] No presentar al reviewer como autoridad de merge.
- [ ] No presentar las 4R como obligatorias con idéntica profundidad en cualquier cambio.
- [ ] Mantener estas cuatro frases principales:
  - «La IA abarata producir candidatos. No abarata automáticamente demostrar que son correctos.»
  - «Un cambio pequeño no significa ausencia de evidencia. Significa evidencia proporcionada.»
  - «El tamaño del diff no decide cuánto revisar. El riesgo y la evidencia disponible, sí.»
  - «Un receipt no certifica el proyecto. Registra evidencia sobre un candidato concreto.»

---

# Decisiones aplicadas y motivo

## 1. PR abiertas, no fusionadas

La revisión se presenta como parte de la decisión anterior al merge. Revisar una PR ya fusionada habría contradicho la tesis de comprobar antes de aceptar el cambio.

## 2. RDD no se reduce a «revisar más o menos»

Se añade el concepto distintivo de receipt: la evidencia queda ligada a un candidato identificable y pierde validez si el contenido cambia.

## 3. Dos receipts visibles

La demo no se limita a dos informes con distinta longitud. Enseña dos registros de evidencia con distinto alcance, lo que hace observable la proporcionalidad.

## 4. El color también exige evidencia

Lint y tests no demuestran por sí solos un cambio visual. Se añade una comprobación directa del botón y de la legibilidad del texto.

## 5. El Gherkin no demuestra concurrencia

El escenario de stock cero se conserva como criterio funcional conocido. La concurrencia se presenta como un riesgo nuevo descubierto por la revisión y, si aplica, debe convertirse en prueba o criterio adicional.

## 6. Los niveles se presentan como simplificación pedagógica

La charla usa profundidad baja, media y alta para facilitar la comprensión. No se presentan como una taxonomía universal separada de la política concreta del repositorio.

## 7. El agente no decide solo

Se sustituye «el agente decide cuánto mirar» por un modelo más preciso: el agente detecta y propone, la política limita y la persona decide.

## 8. Las 4R son lentes, no sellos

Cada R formula una pregunta distinta y exige evidencia pertinente. Para cambios de alto riesgo puede exigirse el conjunto completo; para otros, una lente focalizada puede ser suficiente.

## 9. ODD y RDD son independientes, no desconectados

Ambos mecanismos comparten el flujo de ingeniería, pero uno no activa automáticamente al otro. ODD organiza cómo se aborda el trabajo; RDD organiza cómo se revisa el candidato terminado.

## 10. Cierre basado en criterio, evidencia y autoridad

El arco completo queda formulado así:

```text
Criterio antes
→ candidato construido
→ evidencia después
→ decisión humana de entrega
```

---

# Fuentes técnicas de contraste

- [Organic RDD: atomic review architecture](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/architecture/organic-rdd.md)
- [Receipt-Driven Development and Review Lifecycle](https://deepwiki.com/Gentleman-Programming/gentle-ai/8-receipt-driven-development-and-review-lifecycle)
- [Gates, Risk and Receipts](https://deepwiki.com/Gentleman-Programming/gentle-ai/8.3-gates-risk-and-receipts)
