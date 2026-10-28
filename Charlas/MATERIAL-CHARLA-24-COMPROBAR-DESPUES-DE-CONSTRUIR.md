---
type: Material
title: "Material Charla 24 — Comprobar después de construir"
description: "Material post-charla 24. Cierra la mitad 'después de construir' de la etapa Comprobar (ciclo de la 22; mitad anterior en la 23). Checks deterministas, revisión agéntica proporcional al riesgo, candidato congelado, receipt y las lentes 4R, demostrados con dos PR reales de RCA — una visual, otra de riesgo alto con un hallazgo de concurrencia no previsto en el escenario original."
tags: [material, charla-24, ai-code-review, rdd, receipt, candidato-congelado, verificacion, comprobar, rca]
related:
  - "[[guion-charla-24]]"
  - "[[charla-24-comprobar-despues-de-construir]]"
  - "[[ai-code-review]]"
  - "[[rdd]]"
  - "[[bdd]]"
  - "[[odd]]"
  - "[[guion-charla-23]]"
  - "[[guion-charla-8]]"
charla: 24
estado: "✅ Publicado"
timestamp: "2026-10-28"
---

# Material Charla 24 — Comprobar después de construir

## Qué vimos en la charla

### El punto de partida: queda la otra mitad

La Charla 23 cerró la mitad "antes de construir" de la etapa Comprobar: BDD para escribir el criterio cuando el cambio importa, ODD como disciplina proporcional por defecto para el resto. Las dos cosas ocurren antes de que exista una sola línea de código.

Pero en algún momento el código ya existe. Hay un candidato delante. Y ahí cambia la pregunta: **ya no es "¿qué significa correcto?", sino "¿qué evidencia necesito antes de confiar en este resultado concreto?"**. Esa es la mitad que cierra la Charla 24.

> _"Definir qué es correcto y demostrar que un resultado lo cumple son dos momentos diferentes."_

### El nuevo cuello de botella

Durante años, el coste principal de programar estaba en producir el cambio: entenderlo, escribirlo, hacerlo funcionar. Con agentes de IA, ese coste se reduce mucho. Pero no desaparece — se desplaza hacia demostrar que esos candidatos son aceptables.

> _"La IA abarata producir candidatos. No abarata automáticamente demostrar que son correctos."_

Si un agente genera diez cambios en una tarde y cada uno depende de una lectura manual completa para confiar en él, el tapón ya no está en escribir código. Está en revisarlo — y, sobre todo, en obtener evidencia fiable de que hace lo que debía.

La respuesta no es revisar menos ni aceptar más deprisa. Es revisar **por capas**, de lo barato y determinista a lo caro y humano:

| Capa | Qué aporta | Qué no debe hacer |
|---|---|---|
| 1. Checks deterministas | Build, lint, tests, análisis estático, políticas automatizadas | No interpretan por sí solos la intención completa del cambio |
| 2. Revisión agéntica | Contrasta el candidato con criterios, convenciones y señales de riesgo | No obtiene autoridad para fusionar, publicar o aceptar el riesgo |
| 3. Revisión humana | Decide si la evidencia es suficiente y si el riesgo es aceptable | No debería repetir comprobaciones mecánicas que una máquina ya ejecuta de forma reproducible |

El ojo humano es el recurso escaso de este sistema. La idea es gastarlo en decisiones, no en repetir comprobaciones automatizables. Y un matiz importante: estas tres capas no son una garantía acumulativa perfecta. Un lint verde no demuestra la funcionalidad; un test solo demuestra aquello que efectivamente comprueba; un revisor agéntico puede omitir riesgos. Un verde falso en la capa 2 es especialmente peligroso porque crea confianza injustificada — por eso esa capa nunca recibe autoridad de entrega.

### El reviewer ya existía

Esto no empezó en la Charla 24. En la Charla 8 ya se construyó un agente reviewer sobre RCA: solo lectura, contrastaba el cambio con el `task.md`, las convenciones del proyecto y la cobertura de tests. Lo que le faltaba eran dos propiedades: **proporcionalidad** (no todo cambio merece la misma profundidad de revisión) y **trazabilidad** (la evidencia debe corresponder a una versión concreta del cambio, no a "el proyecto" en general).

> _"El reviewer ya existía. Ahora le damos reglas para revisar cada candidato con la profundidad que exige su riesgo y dejar constancia de qué ha comprobado."_

### La demo: dos PR, dos profundidades, dos receipts

La demo reutilizó deliberadamente las dos peticiones ya conocidas de la Charla 23 — así no hizo falta explicar ejemplos nuevos, y todo el tiempo se dedicó al contraste de revisión:

**Caso A — cambio pequeño:** cambiar el color del botón «Añadir al carrito» a un tono más cálido.

Evidencia mínima pertinente: que el proyecto compile, que lint y tests existentes no introduzcan regresiones, que el botón se muestre con el nuevo color, que el texto siga siendo legible, y que esa evidencia corresponda exactamente al commit revisado. El receipt de esta PR fue breve — riesgo bajo, sin necesidad de las cuatro lentes:

```text
Candidato: PR A / commit <SHA-A>
Riesgo: bajo
Evidencia: build pass, lint pass, tests pass, comprobación visual pass, legibilidad comprobada
Resultado propuesto: aceptable para revisión humana breve
Autoridad de entrega: humana
```

**Caso B — cambio sustancial:** impedir comprar una pieza con stock a cero, el mismo criterio escrito como escenario Gherkin en la Charla 23:

```gherkin
Feature: Carrito de compra
  Scenario: No permitir comprar con stock a cero
    Given que una pieza de resina tiene 0 unidades en stock
    When intento añadirla al carrito
    Then el sistema me impide añadirla
    And veo un mensaje de "sin stock"
```

Aquí la revisión tuvo dos partes. Primero, contrastar cada `Then` del escenario contra evidencia observable — el criterio escrito antes de construir reaparece después como una obligación verificable. Segundo, **buscar riesgos que el escenario no expresaba**: el escenario cubre stock cero, pero no dice qué pasa cuando queda una sola unidad y dos personas intentan comprarla casi a la vez. Ese hueco se convirtió en un **hallazgo abierto** en el receipt, no en un comentario suelto:

```text
Candidato: PR B / commit <SHA-B>
Riesgo: alto — integridad de inventario y posible operación incorrecta
Evidencia del criterio original: build, lint, tests, rechazo con stock 0 y mensaje "sin stock", todo demostrado
Revisión 4R: Risk, Resilience, Readability y Reliability recorridas una por una
Hallazgo abierto: falta demostrar o proteger la operación concurrente sobre la última unidad
Resultado propuesto: no aceptar todavía hasta resolver o justificar el hallazgo
Autoridad de entrega: humana
```

> _"Fijaos en lo que ha decidido la diferencia. No es el número de líneas ni el número de archivos. Es la consecuencia de equivocarnos y la evidencia disponible para detectarlo."_

> _"El tamaño del diff no decide cuánto revisar. El riesgo y la evidencia disponible, sí."_

> _"La revisión no solo comprueba criterios. También descubre criterios que faltaban."_

Las dos PR se revisaron **en sesiones separadas** — no en la misma conversación — para que el candidato de una no contaminara el criterio aplicado a la otra. Es la misma idea de "candidato congelado" aplicada a cómo se preparó la propia demo, no solo a lo que cuenta la teoría.

### RDD con nombre

Lo que la demo acababa de mostrar tiene un nombre: **RDD, Receipt-Driven Development**. La palabra importante no es *review*, es **receipt** — recibo. Una revisión útil no debería terminar en "el agente dice que está bien". Debe dejar constancia de qué candidato exacto se revisó, qué se comprobó, qué evidencia se obtuvo, qué quedó abierto y quién conserva la autoridad de entrega.

**Candidato congelado:** la evidencia tiene que estar vinculada a una versión concreta. Si el contenido cambia después de revisarlo, el receipt anterior deja de demostrar nada sobre la nueva versión.

> _"Un receipt no certifica 'el proyecto'. Registra la evidencia obtenida sobre un candidato concreto."_

**Profundidad proporcional al riesgo**, simplificada en tres niveles pedagógicos:

| Nivel | Cuándo encaja | Tratamiento |
|---|---|---|
| Baja | Cambio pasivo o visual acotado, sin señales críticas | Checks y evidencia directa del cambio |
| Media | Cambio ordinario de código con impacto localizado | Checks más una lente focalizada y contraste con el ticket |
| Alta | Seguridad, permisos, pagos, datos, concurrencia u otra consecuencia difícil de revertir | Revisión profunda con las lentes 4R y entrada humana explícita |

> **El modelo propone. La política limita. La persona decide.**

**Las lentes 4R**, cuatro preguntas distintas, no sellos decorativos:

- **Risk** — ¿qué daño puede causar este cambio si se equivoca?
- **Resilience** — ¿se comporta correctamente en límites, fallos y condiciones adversas?
- **Readability** — ¿otra persona puede comprender la regla sin reconstruir toda la intención?
- **Reliability** — ¿qué evidencia reproducible detectaría una regresión?

RDD no sustituye los checks deterministas, ni BDD, ni la política de ramas, ni la revisión humana de lo crítico. Organiza la revisión, vincula la evidencia al candidato, y devuelve la decisión de entrega a la persona.

### Cierre: el arco completo de Comprobar

```text
ANTES DE CONSTRUIR          DESPUÉS DE CONSTRUIR
BDD + ODD                   Checks + ai-code-review + RDD
¿Qué significa correcto?    ¿Qué evidencia justifica aceptar este candidato?
```

ODD y RDD forman parte del mismo flujo, pero son decisiones independientes: que ODD clasifique una tarea como sustancial no activa automáticamente una revisión 4R, y que RDD detecte riesgo alto no dice nada sobre qué método de construcción se usó. Cada mecanismo responde a una pregunta distinta.

> _"Generar produce un candidato. Verificar produce evidencia. Un receipt deja constancia de por qué confiamos, o de por qué todavía no debemos confiar."_

Con esto se cierra la etapa Comprobar dentro del ciclo de seis pasos de la Charla 22: idea, especificar, construir, comprobar, publicar y mantener. Quedan Publicar y Mantener — pero esa es otra charla.

## Glosario de conceptos vistos hoy

### [[ai-code-review]] — AI code review
Uso de un agente para inspeccionar un candidato, contrastarlo con criterios y convenciones, y señalar riesgos o incumplimientos. Produce observaciones y evidencia, nunca autoridad automática de entrega.

### Check determinista
Comprobación con resultado reproducible frente a una condición definida — build, lint, tests, una política automatizada. Un resultado verde solo demuestra aquello que ese check comprueba, nada más.

### Candidato
Versión concreta del cambio que se presenta a revisión: una PR, una rama o un commit identificable.

### Candidato congelado
Candidato cuyo contenido no cambia mientras se obtiene la evidencia. Si el contenido cambia, hay que revisar la nueva versión — el receipt anterior no se actualiza, se invalida.

### [[rdd]] — RDD (Receipt-Driven Development)
Enfoque que organiza una revisión proporcional al riesgo y ligada a un candidato concreto, mediante checks, clasificación de profundidad y, cuando el riesgo lo exige, las lentes 4R — sin apropiarse de la decisión de entrega.

### Receipt
Registro trazable de la revisión: candidato, checks, lentes aplicadas, evidencia, hallazgos abiertos y resultado propuesto. No es una garantía universal ni sustituye la decisión humana.

### 4R
Cuatro lentes de revisión: Risk, Resilience, Readability y Reliability. Separan preguntas que, en una revisión genérica, tienden a mezclarse.

## Ideas para llevarse

1. **Generar ya era barato — ahora lo barato empieza a ser también demostrar que algo está bien, si se hace con disciplina.** La revisión en capas (determinista → agéntica → humana) es lo que permite escalar sin perder confianza.
2. **El tamaño de un cambio no dice nada sobre cuánto hay que revisarlo. El riesgo, sí.** Un botón de color y una validación de stock pueden tener diffs de tamaño parecido y merecer niveles de revisión completamente distintos.
3. **Una revisión que no deja receipt es una opinión, no una evidencia.** Saber qué candidato exacto se comprobó, con qué resultado, es lo que distingue "parece que está bien" de "esto es lo que sabemos con certeza".
4. **Revisar también descubre, no solo confirma.** El hallazgo de concurrencia de la demo no estaba en el escenario original — apareció porque la revisión profunda fue más allá de comprobar lo ya escrito.

## Enlaces

- [[guion-charla-24]] — guión completo de la charla
- [[charla-24-comprobar-despues-de-construir]] — resumen breve y asistencia
- [[ai-code-review]]
- [[rdd]]
- [[bdd]]
- [[odd]]
- [[guion-charla-23]] — charla anterior, mitad "antes de construir" de Comprobar
- [[guion-charla-8]] — origen del reviewer agent que esta charla extiende

*Charla 24 — Serie de formación interna en IA*
