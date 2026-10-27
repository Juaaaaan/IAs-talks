---
type: guion
title: "Charla 24 — Comprobar después de construir: ai-code-review y RDD"
description: "Cierra la mitad 'después de construir' de Comprobar, abierta en la 22 y empezada en la 23. El cuello de botella pasa de generar a revisar; RDD da vocabulario para decidir cuánta profundidad merece cada cambio. Demo de contraste: dos PRs reales de RCA — las mismas peticiones usadas como ejemplo en la 23 — revisadas a niveles distintos."
tags: [charla, guion, ai-code-review, rdd, revision, pull-request, verificacion, comprobar, rca, 4r]
related:
  - "[[guion-charla-23]]"
  - "[[guion-charla-8]]"
  - "[[guion-charla-22]]"
  - "[[ai-code-review]]"
  - "[[rdd]]"
  - "[[bdd]]"
  - "[[odd]]"
  - "[[ai-harness-engineering]]"
  - "[[arnes-completo]]"
charla: 24
estado: borrador
timestamp: 2026-10-26
---

# Guión Charla 24 — Comprobar después de construir: ai-code-review y RDD

### Fecha por confirmar (próximo miércoles)

> Cierra el ciclo "Comprobar" abierto en la 22 y empezado en la 23. La 23 cubrió la mitad ANTES de construir (BDD, ODD). Esta cubre la mitad DESPUÉS: una vez generado el código, ¿cuánto hay que mirarlo antes de confiar en él? La demo reutiliza, a propósito, las mismas dos peticiones usadas como ejemplo en la 23 — el cambio de color del botón y la validación de stock — para que la sala vea el ciclo completo cerrarse sobre el mismo material, no sobre ejemplos nuevos.

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|---|---|---:|
| 1. Apertura | Callback directo al cierre de la 23: queda la otra mitad | 3 min |
| 2. El cuello de botella | Por qué revisar, no generar, es ahora el problema | 5 min |
| 3. El reviewer ya existe | Callback breve a la 8: el agente reviewer de RCA | 3 min |
| 4. Demo | Dos PRs reales, dos profundidades de revisión | 12 min |
| 5. RDD con nombre | Las 4R y por qué decidir la profundidad a propósito | 7 min |
| 6. Cierre | El arco completo de Comprobar, antes y después | 4 min |

**Total ≈ 34 min** (con margen para preguntas).

## Bloque 1 — Apertura: queda la otra mitad — 3 min

_"Hace dos semanas cerramos la charla con una frase: 'Hoy hemos comprobado antes de construir. Queda la otra mitad.' Hoy es esa otra mitad."_

_"Rápido repaso: en la 23 dijimos que la IA no debería decidir sola qué significa correcto. Para eso escribimos el criterio antes — BDD — o dejamos que el agente siga una disciplina proporcional por defecto — ODD. Las dos cosas pasan ANTES de que exista el código."_

_"Pero en algún momento el código ya existe. Alguien, o algo, lo generó. Y ahí aparece la pregunta de hoy: ¿cuánto hay que revisarlo antes de confiar en él?"_

**En pantalla:**

> **Comprobar antes de construir** → Charla 23 (BDD, ODD)
> **Comprobar después de construir** → Hoy (ai-code-review, RDD)

**Frase que debe quedar:**

> **Definir qué es correcto y comprobar que lo es son dos momentos distintos. Hoy cerramos el segundo.**

**Por qué se cambia:** empezar citando la frase textual de cierre de la 23 ancla la charla de inmediato en la memoria de la sala, sin necesidad de reconstruir el contexto desde cero.

## Bloque 2 — El cuello de botella — 5 min

_"Durante años, escribir código fue el cuello de botella. Un desarrollador tardaba horas en construir algo. Revisarlo era rápido, en comparación."_

_"Eso se ha invertido. Un agente puede abrir varias pull requests en una tarde. Si las revisa una persona a mano, una por una, el cuello de botella ya no es generar. Es leer."_

**Frase que debe quedar:**

> **Si un agente genera diez cambios en una tarde y los revisáis a mano, el tapón ya no es escribir código. Es leerlo.**

_"La respuesta no es 'revisar menos'. Es revisar en capas, de más barato a más caro:"_

**En pantalla:**

| Capa | Qué hace | ¿Opina? |
|---|---|---|
| 1. Checks deterministas | Lint, tests, análisis estático | No — pasa o falla |
| 2. Review agéntico | Un agente comenta el PR contra las reglas del proyecto | Sí, pero no decide solo |
| 3. Review humano | Reservado para lo crítico, con el trabajo previo ya filtrado | Decide |

_"El ojo humano es el recurso escaso. Por eso se gasta donde el riesgo lo justifica, no en todo por igual."_

**Pregunta anticipada: "¿Y si el agente revisor da el visto bueno y está equivocado?"**

_"Un revisor agéntico que da verde en falso es peor que no tener revisor — genera confianza injustificada. Por eso la capa 3 no desaparece nunca para lo crítico. El agente filtra; no sustituye el criterio humano donde el riesgo es real."_

**Por qué se cambia:** la cita ancla la tesis antes de nombrar ninguna sigla, igual que en la 23 el problema se presentó antes que BDD.

## Bloque 3 — El reviewer ya existe — 3 min

_"Esto no es terreno nuevo para vosotros. En la Charla 8 os enseñé un agente reviewer sobre RCA. Solo lee, no escribe. Comprueba los criterios del task.md, las convenciones del proyecto, la cobertura de tests. Lleva con nosotros desde julio."_

_"Lo que no os dije entonces es cuánto debería mirar cada vez. Ese agente aplicaba siempre el mismo nivel de revisión, sin distinguir si el cambio era trivial o crítico."_

**Frase que debe quedar:**

> **El agente que revisa ya existe. Lo que falta es que decida cuánto mirar.**

**Por qué se cambia:** bloque corto a propósito — es un recordatorio, no una reintroducción. Extenderse aquí restaría tiempo a la demo, que es donde se ve el problema real.

## Bloque 4 — Demo: dos PRs, dos profundidades — 12 min

**Caso A — cambio pequeño:** el mismo que pedisteis ver en la 23 como ejemplo de ODD: cambiar el color del botón "Añadir al carrito" a un tono más cálido.

**Caso B — cambio sustancial:** el mismo escenario que vimos como ejemplo de BDD en la 23: no permitir comprar con stock a cero.

```gherkin
Feature: Carrito de compra
  Scenario: No permitir comprar con stock a cero
    Given que una pieza de resina tiene 0 unidades en stock
    When intento añadirla al carrito
    Then el sistema me impide añadirla
    And veo un mensaje de "sin stock"
```

_"Las dos PRs ya están generadas y mergeadas — no las vamos a construir en directo, las vamos a revisar. Lo que importa hoy no es cómo se generó el código. Es cuánto hace falta mirarlo."_

**Secuencia:**

1. Mostrar el informe del reviewer sobre la PR A (color del botón): lint ✅, tests ✅, criterios del task.md ✅. Informe de una línea. Fin.
2. Preguntar a la sala: "¿Hace falta algo más aquí?" — dejar que respondan antes de confirmar que no.
3. Mostrar el informe del reviewer sobre la PR B (stock a cero): mismo formato, pero ahora con cuatro apartados en vez de uno.
4. Recorrer los cuatro apartados uno a uno, señalando la evidencia concreta en cada uno (ver Bloque 5).
5. Mostrar que el reviewer contrasta el resultado directamente contra el escenario Gherkin de la 23 — el criterio escrito entonces es la vara de medir ahora.

**Pausa deliberada tras los dos informes:**

_"Fijaos en lo que decide la diferencia. No es el tamaño del diff. El cambio de color puede tocar menos líneas que la validación de stock, o más — da igual. Lo que cambia el nivel de revisión es el riesgo: qué pasa si esto falla en producción."_

**En pantalla:**

> **El tamaño del cambio no decide cuánto revisar. El riesgo sí.**

**Nota para Juan:** las dos PRs y sus informes de reviewer deben estar generados y guardados antes del miércoles — no se genera nada en directo. El riesgo que la 23 evitó (depender de que el modelo clasifique bien delante de la sala) no aplica aquí de la misma forma, pero mostrar evidencia ya preparada sigue siendo más fiable y dejó mejor sabor de boca la vez anterior.

**Por qué se cambia:** las dos PRs son las mismas peticiones ya usadas en la 23 — no hay ejemplos nuevos que explicar, la sala ya conoce el contexto de ambas, así que todo el tiempo del bloque se dedica al contraste, no a la introducción.

## Bloque 5 — RDD con nombre — 7 min

_"Lo que acabáis de ver tiene un nombre: RDD, Receipt-Driven Development. No es revisar más o menos por costumbre. Es un modelo de tres niveles, para decidir a propósito cuánto hace falta mirar."_

**En pantalla:**

| Nivel | Qué cubre | Ejemplo de hoy |
|---|---|---|
| Pasivo | ¿Compila, pasa lint, pasa tests? | PR A — color del botón |
| Medio | ¿Hace lo que el ticket pedía? | — |
| Alto ("4R") | Risk, Resilience, Readability, Reliability | PR B — stock a cero |

_"El nivel alto tiene cuatro preguntas, y las cuatro aparecieron en el informe de la PR B:"_

- **Risk** — ¿qué pasa si esto falla? Aquí: se vende una pieza que no existe, o se le niega una compra válida a un cliente.
- **Resilience** — ¿aguanta condiciones límite? Aquí: ¿qué pasa si dos personas compran la última unidad a la vez?
- **Readability** — ¿lo entendería otra persona dentro de seis meses sin preguntar?
- **Reliability** — ¿se comprueba contra un criterio explícito? Aquí: el escenario Gherkin de la 23.

**Frase que debe quedar:**

> **No toda PR necesita las cuatro preguntas. Pero las que tocan dinero, datos o personas, sí.**

**Pregunta anticipada: "¿Quién decide el nivel, el agente o la persona?"**

_"Igual que con ODD, el agente explora y propone un nivel. Pero el criterio profesional de quien revisa puede subirlo o bajarlo. RDD da un vocabulario compartido para justificar esa decisión, no la sustituye."_

**Reserva técnica, solo si preguntan:** RDD no sustituye los checks deterministas de la capa 1 ni el review humano reservado a lo crítico — es el modelo de profundidad dentro de la capa 2, la que decide cuánto debe mirar el agente antes de que el humano entre.

> **Verifying beats generating.**
> — Alan Buscaglia, Gentleman Programming

**Por qué se cambia:** el nombre técnico llega después de ver los dos informes, no antes — mismo patrón que ODD en la 23: primero el comportamiento observable, después la etiqueta que lo organiza.

## Bloque 6 — Cierre: el arco completo de Comprobar — 4 min

_"Juntad las dos charlas. Antes de construir: escribimos el criterio cuando importa (BDD), o dejamos que el agente siga una disciplina proporcional por defecto (ODD). Después de construir: decidimos a propósito cuánto hay que mirar el resultado (RDD), en capas, reservando el ojo humano para lo que de verdad lo necesita."_

**En pantalla:**

> **Antes de construir** → BDD + ODD — definir qué es correcto
> **Después de construir** → ai-code-review + RDD — comprobar que lo sigue siendo

_"Una aclaración antes de cerrar: ODD y RDD no están conectados entre sí. Que ODD clasifique un cambio como sustancial no dispara automáticamente una revisión 4R, y viceversa. Son dos interruptores distintos, cada uno con su propia pregunta."_

> **Comprobar antes de construir era "¿qué significa correcto?". Comprobar después es "¿cuánto confío en que lo sigue siendo?"**

**Puente:**

_"Con esto cerramos el ciclo que empezó en la 22 con seis pasos: idea, especificar, construir, comprobar, publicar, mantener. Comprobar ya tiene sus dos mitades. Quedan publicar y mantener — pero esa es otra charla."_

**Por qué se cambia:** cerrar nombrando explícitamente el ciclo de la 22 deja claro que las charlas 22-24 forman un bloque, no tres temas sueltos — refuerza la narrativa acumulativa de la serie.

## Checklist antes del miércoles

### Contenido
- [ ] Confirmar fecha definitiva y actualizar frontmatter + encabezado.
- [ ] Pantalla con la cita de cierre textual de la 23 para el Bloque 1.
- [ ] Tabla de las tres capas de revisión (Bloque 2).
- [ ] Recordatorio visual del reviewer.agent.md de la 8 (Bloque 3) — no hace falta releerlo entero, solo la silueta.

### Demo
- [ ] PR A (color del botón) generada, mergeada y con informe de reviewer guardado — nivel pasivo.
- [ ] PR B (stock a cero) generada, mergeada y con informe de reviewer guardado — nivel 4R, contrastado contra el escenario Gherkin de la 23.
- [ ] Verificar que el informe de la PR B nombra las cuatro R de forma legible en pantalla, no solo en texto corrido.
- [ ] Ruta de recuperación: capturas de ambos informes por si falla la conexión o el repo en directo.

### Ensayo narrativo
- [ ] Cronometrar 3 + 5 + 3 + 12 + 7 + 4 minutos — vigilar el Bloque 4, es el más largo de la serie hasta ahora en una demo de contraste.
- [ ] Comprobar que RDD no se nombra hasta después del Bloque 4.
- [ ] Mantener tres frases principales:
  1. "Si un agente genera diez cambios en una tarde y los revisáis a mano, el tapón ya no es escribir código. Es leerlo."
  2. "El tamaño del cambio no decide cuánto revisar. El riesgo sí."
  3. "Verifying beats generating."

## Decisiones aplicadas y motivo

- **Ancla narrativa:** el gancho de apertura es la frase literal de cierre de la 23, no la Charla 8 — la 8 solo aporta el vehículo técnico (el agente reviewer), no el hilo narrativo.
- **Reutilizar las peticiones de la 23 en vez de inventar ejemplos nuevos:** el cambio de color y la validación de stock ya son conocidos por la sala — todo el tiempo del Bloque 4 se dedica al contraste de profundidad, no a explicar un caso nuevo.
- **Demo de contraste, no de una sola PR:** la tesis de RDD es que no toda PR merece el mismo nivel — una sola PR no la demuestra, solo muestra cómo aplicar un nivel ya elegido.
- **Dos PRs pre-revisadas, no generadas en directo:** aplica la misma lección de la 23 — el público valora ver la evidencia, no el proceso. Aquí además se evita alargar el bloque más allá de los 12 minutos.
- **RDD se nombra al final del Bloque 5, no al principio:** mismo patrón que ODD en la 23 — comportamiento observable antes que etiqueta.
- **Separación ODD/RDD explícita en el cierre:** evita que la sala salga pensando que un interruptor activa el otro — ya se dejó como nota solo para Juan en la 23; aquí pasa a decirse en voz alta porque es el cierre natural del tema.
- **Puente a la 22:** cerrar nombrando el ciclo de seis pasos deja el bloque 22-24 como una unidad reconocible, no tres charlas sueltas sobre el mismo tema.
