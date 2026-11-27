---
type: guion
title: "Charla 26 — Retrospectiva: qué hemos visto y para qué sirve cada cosa"
description: "Repaso para afianzar lo visto en la serie: 32 piezas ordenadas en diez preguntas de trabajo y cuatro tramos. Dinámica de texto difuminado para que la sala responda, consulta al vault con GitHub Copilot Desktop y un vistazo a la Biblioteca web."
tags: [charla, guion, retrospectiva, repaso, arnes, ciclo, biblioteca, dinamica]
related: [charla-26-retrospectiva, guion-charla-24, guion-charla-23, guion-charla-22, guion-charla-19, guion-charla-13, guion-charla-12, arnes-completo, ai-harness-engineering, ia-first, rdd, odd]
charla: 26
estado: impartida
timestamp: 2026-11-27
---

# Guión Charla 26 — Retrospectiva: qué hemos visto y para qué sirve cada cosa

## 25 de noviembre de 2026

Hoy no se añade otra herramienta a la lista. El objetivo es **afianzar y ordenar**: que cada persona de la sala salga sabiendo, para cada pieza que hemos visto, **qué pregunta responde y para qué sirve**.

La charla se apoya en una dinámica: cada pieza aparece con su descripción **difuminada** y la sala intenta responder en el chat antes de que se revele. Las piezas van de lo más sencillo a lo más avanzado dentro de cada pregunta.

Las partes de pantalla (consulta al vault y Biblioteca) se **ensayan antes** y llevan plan B con capturas (lección de la 23).

> [!important] Tesis única
> **No hace falta recordar veinticinco charlas. Hace falta recordar qué pregunta responde cada cosa.**

> [!warning] Nota de encuadre — qué NO decir
> La serie sigue: hay una charla el miércoles 2 de diciembre que da un compañero. Esta sesión **no** es una despedida ni un cierre de calendario. No decir «la última del año», «hasta el año que viene» ni nada con fechas de 2027. Tampoco «cierre del arco». No preguntar a la sala si «les suena» o si «se repite» algo: la dinámica pide **qué creen que hace** cada pieza, no si la conocen. El relevo final es neutro y breve.

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|---|---|---:|
| 1. Apertura | No añadimos otra herramienta: ponemos orden y participamos | 3 min |
| 2. El mapa | Cuatro tramos, diez preguntas | 3 min |
| 3. Las diez preguntas | 32 piezas, con 12 intervenciones y revelado ágil del resto | 20 min |
| 4. Preguntarle al vault | Dos consultas con GitHub Copilot Desktop y fuentes visibles | 5 min |
| 5. La Biblioteca | Dónde va a vivir todo esto | 2 min |
| 6. Cierre | La chuleta de preguntas, una acción | 4 min |

**Total aproximado: 37 minutos**, incluidas las intervenciones previstas; las preguntas abiertas quedan para el final.

Si hay que recortar, por este orden: Bloque 5, las preguntas 3 y 6 del Bloque 3 (se revelan sin pedir respuesta), Bloque 4.

---

# Bloque 1 — Apertura — 3 min

_«Hoy no vengo a añadir otra herramienta a la lista. Desde el 17 de junio hemos visto muchas piezas. Hoy las ponemos en una mesa, una al lado de otra, para ver para qué sirve cada una.»_

_«Y os pido una cosa: vais a ver cada pieza con su explicación borrosa. Escribid en el chat, con vuestras palabras, para qué creéis que sirve. No hay respuestas malas: leo unas pocas y luego lo aclaramos.»_

## En pantalla

```text
17 jun → 25 nov
Qué hemos visto, qué pregunta responde y para qué sirve
```

## Frase que debe quedar

> **Hoy no añadimos otra herramienta. Hoy ponemos orden a lo que ya sabemos.**

---

# Bloque 2 — El mapa — 3 min

_«Si ponéis las charlas en fila parece una lista de temas. Pero cada una nace de una pregunta que tiene cualquiera que trabaje con IA. Son diez, en cuatro tramos.»_

## En pantalla

| Tramo | Preguntas |
|---|---|
| **A. Darle contexto** | 1 ¿Cómo le pido las cosas? · 2 ¿Cómo le doy contexto estable sobre mi trabajo? · 3 ¿Cómo encuentra lo que necesita en tanta información? |
| **B. Fiarse con cabeza** | 4 ¿Me puedo fiar de lo que dice? · 5 ¿Qué puedo usar y con qué riesgos? · 6 ¿Qué modelo y qué modo uso para cada cosa? |
| **C. Que haga cosas** | 7 ¿Cómo la conecto con mis herramientas? · 8 ¿Cómo creo un asistente para mi equipo? · 9 ¿Cómo le encargo un trabajo grande sin que se desvíe? |
| **D. Comprobar** | 10 ¿Cómo defino y compruebo que está bien? |

_«Cada pieza tiene su nombre y lo que hace. Si no programáis, no pasa nada: las reconoceréis por lo que hacen, no por cómo se llaman.»_

_Las charlas de mi compañero —la 21 sobre Copilot, WorkIQ y PowerPoints, y la 25— completan el mapa por el lado de la herramienta._

## Frase que debe quedar

> **No son temas sueltos: son diez preguntas.**

---

# Bloque 3 — Las diez preguntas — 20 min

## Cómo funciona la dinámica (12 intervenciones, 45–60 segundos cada una)

1. Aparece la **pieza** (nombre y charla donde la vimos). El texto de «para qué sirve» está **difuminado**.
2. Pregunta a la sala: _«¿Para qué creéis que sirve? Una frase en el chat.»_
3. Leer **una o dos** respuestas en voz alta, sin juzgar ni abrir debate en ese momento.
4. Se revela el texto. Se dice la frase ancla.

Las piezas marcadas con ❓ son las que se **preguntan** a la sala (12 en total). El resto se revela agrupado y directamente, en unos diez segundos por pieza, para no alargar.

- Si una pieza suena técnica, pregúntala igual con otras palabras: _«Por el nombre, ¿qué creéis que hace?»_ Vale cualquier intuición.

Si la sala tarda en escribir: en las primeras tres o cuatro piezas, esperar 20–30 segundos (escribir en el chat lleva su tiempo); después, unos 10. Si nadie escribe, lanzar una intuición propia («yo diría que…») y seguir.

> [!warning] Antes de ponerlo en pantalla
> Los textos de «para qué sirve» salen de las fichas de `Conceptos/` leídas esta semana. La columna «Charla» solo se rellena donde la ficha o el resumen lo confirma.

---

## Tramo A — Darle contexto

### Pregunta 1 — ¿Cómo le pido las cosas para que me entienda?

| | Pieza | Charla | Para qué sirve (texto que se difumina) |
|---|---|---|---|
| | Hablar su idioma | 18 | Usar el término correcto («acta de reunión», «resumen ejecutivo») hace que la IA active el patrón adecuado. |
| ❓ | Dar ejemplos | 18 | Un ejemplo de lo que quieres vale más que tres frases describiéndolo. |

> **Cómo le pides cambia lo que te devuelve.**

### Pregunta 2 — ¿Cómo le doy contexto estable sobre mi trabajo?

| | Pieza | Charla | Para qué sirve (texto que se difumina) |
|---|---|---|---|
|  | Instrucciones persistentes | 8 | Dejar escritas tus reglas para que la IA las siga en cada conversación sin repetírselas. |
| ❓ | Skills | 7 | Recetas reutilizables para tareas que repites; se cargan cuando hacen falta. |
| | Wiki LLM | 11 | Una carpeta de ficheros de texto ordenados que la IA lee y ayuda a mantener, como memoria de largo plazo. |

> **Contexto: que no empiece de cero.**

### Pregunta 3 — ¿Cómo encuentra lo que necesita en tanta información?

| | Pieza | Charla | Para qué sirve (texto que se difumina) |
|---|---|---|---|
| | Ponerle la fuente delante | 18 | Darle el documento en vez de preguntarle de memoria: con la fuente delante, inventa mucho menos. |
| ❓ | Ventana de contexto | 18 | Hay un límite de lo que puede leer a la vez; meter más no es mejor, importa qué entra. |
| ❓ | RAG | 12 | Buscar primero en tus documentos y responder después usándolos. |
| | Metadatos y enlaces entre fichas (OKF) | 11 | Etiquetas al principio de cada ficha (tipo, descripción, enlaces a otras fichas) para que la IA se oriente sin leerlo todo. |

> **No es leerlo todo: es encontrar lo que toca.**

---

## Tramo B — Fiarse con cabeza

### Pregunta 4 — ¿Me puedo fiar de lo que dice?

| | Pieza | Charla | Para qué sirve (texto que se difumina) |
|---|---|---|---|
|  | Predicción del siguiente token | 18 | Por dentro solo completa el patrón más probable: predecir no es saber. |
| ❓ | Alucinaciones | 18 | Respuestas que suenan seguras y son falsas; con la fuente delante el riesgo baja, sin fuente sigue ahí. |
|  | Pedir la fuente | 17 | Pedir la fuente o la frase exacta ayuda a comprobar si la respuesta está apoyada o solo suena convincente. |
| | Verificar según lo que cuesta equivocarse | 17 y 18 | Cuanto más caro es el error, más compruebas: una lectura rápida para un borrador, contraste total y revisión humana para una cifra a cliente. |

> **Que suene seguro no dice nada de si es verdad.**

### Pregunta 5 — ¿Qué puedo usar y con qué riesgos?

| | Pieza | Charla | Para qué sirve (texto que se difumina) |
|---|---|---|---|
|  | Shadow AI | 14 | Usar IA sin reglas claras ni aprobación; casi nunca es rebeldía: aparece cuando faltan reglas claras. |
| | Gobernanza de IA | 14 | Normas y controles para usarla con responsabilidad: qué datos, qué herramientas aprobadas, quién revisa. |
| ❓ | Inyección de instrucciones | 15 | Texto externo con órdenes ocultas que manipula a la IA; se defiende por capas, no con una sola barrera. |

> **Usar IA sin reglas no es rebeldía: es que faltan reglas claras.**

### Pregunta 6 — ¿Qué modelo y qué modo uso para cada cosa?

| | Pieza | Charla | Para qué sirve (texto que se difumina) |
|---|---|---|---|
| ❓ | Elegir bien: cuatro decisiones | 17 | «Usar la IA» no es una acción, son cuatro decisiones: herramienta, modelo, modo de trabajo y cuánto verificar. |
| | Los modos de trabajo | 17 | Preguntar, investigar a fondo, recordar o actuar: elegir el modo según lo que necesitas. |
| | Modelos que razonan (rápido o razonador) | 17 | Piensan antes de responder: más precisos en tareas complejas, más lentos y más caros; para lo simple, el modo rápido. |

> **No os aprendáis los nombres: aprended los criterios.**

---

## Tramo C — Que haga cosas

### Pregunta 7 — ¿Cómo la conecto con mis herramientas?

| | Pieza | Charla | Para qué sirve (texto que se difumina) |
|---|---|---|---|
| ❓ | MCP | 7 | Un enchufe estándar entre la IA y el mundo real (la demo fue con Jira). |
| | Permisos mínimos | 15 | Darle solo el acceso que necesita: tú decides qué conectas y qué puede hacer. |

> **Que pueda leer y actuar en vuestras herramientas, con permiso.**

### Pregunta 8 — ¿Cómo creo un asistente para mi equipo?

| | Pieza | Charla | Para qué sirve (texto que se difumina) |
|---|---|---|---|
| ❓ | Agente de IA | 13 | No sigue un guion: razona, usa herramientas y, cuando no sabe algo, lo dice. |
|  | Copilot Studio | 13 | Plataforma de Microsoft para crear agentes propios. |
| | Métricas de IA | 13 | Datos para saber si el agente funciona: cuánto se usa, cuánto resuelve y cuánto resuelve sin ayuda de una persona. |

> **Un agente que reconoce lo que no sabe vale más que uno que siempre responde algo.**

### Pregunta 9 — ¿Cómo le encargo un trabajo grande sin que se desvíe?

| | Pieza | Charla | Para qué sirve (texto que se difumina) |
|---|---|---|---|
| ❓ | SDD con OpenSpec | 16 | Escribir primero qué quieres y construir después contra eso. |
| | Equipo de agentes | 19 (y 8) | Un orquestador y especialistas, con un punto en el que una persona decide; en la 8, uno construye y otro verifica. |
| | Ejecutor abierto (OpenCode) | 20 | Un ejecutor que usa el modelo que tú eliges, dentro de tus reglas. |

> **Antes de ejecutar: ¿qué quieres, exactamente?**

---

## Tramo D — Comprobar

### Pregunta 10 — ¿Cómo defino y compruebo que está bien?

| | Pieza | Charla | Para qué sirve (texto que se difumina) |
|---|---|---|---|
| ❓ | El ciclo de seis paradas | 22 | Un orden para cualquier trabajo con IA: Idea, Especificar, Construir, Comprobar, Publicar, Mantener. |
| | BDD | 23 | Escribir antes de construir los ejemplos de comportamiento que demostrarán que está bien. |
| | ODD | 23 | Protocolo por defecto del agente cuando no hay spec ni escenario: explorar en proporción, clasificar y documentar solo si es sustancial. |
| ❓ | Revisión con IA | 24 | Agentes que revisan los cambios antes que una persona; la persona se reserva lo crítico. |
| | RDD | 24 | Revisar con recibo: constancia de qué versión se comprobó y con qué evidencia. El modelo propone, la política limita, la persona decide. |

Con la pieza del ciclo en pantalla, enseñar dónde hemos estado:

| Parada | Dónde la hemos trabajado |
|---|---|
| Idea | El encargo de RRHH |
| Especificar | 16 — SDD con OpenSpec |
| Construir | 20 — el ejecutor abierto |
| Comprobar | 23 antes y 24 después |
| Publicar | Tocada con el punto de control de la 19 |
| Mantener | Tocada con la Wiki LLM (11) y las instrucciones (8) |

_Publicar y Mantener: solo describir que son las dos paradas que hemos rozado. No prometer fecha ni charla._

> **Definir qué es correcto y comprobar que se cumple son dos momentos distintos.**

---

# Bloque 4 — Preguntarle al vault — 5 min

_«Todo lo que acabáis de ver no está en mi cabeza: está en una carpeta de ficheros de texto, la Wiki LLM de la charla 11. Vamos a usarla para lo que sirve: hacerle preguntas en lenguaje normal.»_

_«Ya lo preparé ayer, con dos preguntas. Os enseño la respuesta, las fichas utilizadas y la frase que permite comprobarla.»_

## Cómo se hace

- Aplicación: **GitHub Copilot Desktop** abierta sobre una **copia limpia del vault** (ver «Preparación de hoy»).
- Dos preguntas ya ejecutadas. Para cada una, enseñar: **pregunta → respuesta → fichas utilizadas → frase exacta de respaldo** (unos 2 minutos por pregunta). La conclusión añadida por el modelo, solo si sobra tiempo.

| Pregunta preparada | Debería llevar a |
|---|---|
| «Quiero pasar un documento con datos de clientes a una IA. ¿Qué conceptos me aplican y qué debo comprobar antes?» | Pregunta 5: gobernanza, inyección de instrucciones |
| «Quiero que la IA haga un trabajo repetitivo de varios pasos. ¿Qué piezas necesito y en qué orden?» | Preguntas 9 y 10 |

> [!important] Regla de seguridad de la demo
> Las dos preguntas se ejecutan hoy martes, se revisan contra las fichas y se guardan con capturas como plan B. En directo se enseña **la captura**, y solo si va todo bien se hace una pregunta nueva de la sala **al final del bloque**. Si falla o tarda, se dice sin drama («esto es justo la pregunta 4») y se vuelve a la captura.

## Frase que debe quedar

> **Sobre nuestro trabajo, lo que no está escrito no puede conocerlo de forma fiable. Lo que está en el vault puede encontrarlo, citarlo y contrastarlo.**

---

# Bloque 5 — La Biblioteca — 2 min

_«El vault guarda el conocimiento estructurado. La Biblioteca es una forma más cómoda de navegarlo: permite localizar charlas y conceptos sin recorrer las carpetas.»_

## En pantalla

Enseñar la ruta `/biblioteca` en **local**: índice, buscador, una nota con sus enlaces y el mini-grafo de conexiones. _«Todavía no está disponible para toda la empresa; es un trabajo en marcha.»_

> [!warning] Reglas para este bloque
> - **No prometer fecha ni dirección.** El despliegue interno no está definido. Decir «cuando esté, lo diré por aquí».
> - Mostrar solo **Charlas y Conceptos** (alcance de la v1). Comprobar el día antes que no aparece nada de `Proyectos/` ni de `Demos/`.
> - Que no se vea una dirección de despliegue personal ni pestañas con datos de cliente: usar una ventana limpia.
> - Si la web da problemas, pasar a capturas.

---

# Bloque 6 — Cierre — 4 min

## La chuleta

_«Si os lleváis una sola cosa, que sean estas diez preguntas.»_

| Si te preguntas… | Mira… |
|---|---|
| 1. ¿Cómo le pido las cosas? | Hablar su idioma (término correcto) y dar ejemplos (18) |
| 2. ¿Cómo le doy contexto estable sobre mi trabajo? | Instrucciones (8), skills (7), Wiki LLM (11) |
| 3. ¿Cómo encuentra lo que necesita? | Fuente delante (18), ventana de contexto (18), RAG (12), metadatos y enlaces (11) |
| 4. ¿Me puedo fiar? | Predicción de token y alucinaciones (18), pedir la fuente y verificar según lo que cuesta equivocarse (17) |
| 5. ¿Qué puedo usar y con qué riesgos? | Shadow AI y gobernanza (14), inyección de instrucciones (15) |
| 6. ¿Qué modelo uso? | Elegir bien (17), modos de trabajo (17), rápido o razonador (17) |
| 7. ¿Cómo la conecto? | MCP (7), permisos mínimos (15) |
| 8. ¿Cómo creo un asistente? | Agente y Copilot Studio (13), métricas (13) |
| 9. ¿Cómo le encargo algo grande? | SDD (16), equipo de agentes (19), ejecutor abierto (20) |
| 10. ¿Cómo defino y compruebo que está bien? | Ciclo (22), BDD y ODD (23), revisión y RDD (24) |

_«La chuleta la dejo luego en Teams, para que la tengáis a mano.»_ [Hacerlo solo si la subes realmente.]

## Una acción esta semana

_«Elegid una sola de estas preguntas, la que más os toque, y mirad la pieza correspondiente esta semana. Una. No diez.»_

## Frase final — dejar fija en pantalla

> **No recordéis herramientas. Recordad preguntas. La IA abre opciones; vuestro criterio decide.**

## Relevo

_«Seguimos. Gracias por el rato, y nos vemos en la siguiente.»_ [Sin mencionar el tema de la charla del 2 de diciembre: no se conoce.]

---

# Para la web del repaso (dinámica del difuminado)

Cada pieza es una tarjeta con estos campos. Es el mismo contenido de las tablas del Bloque 3, así que se puede generar de ahí.

| Campo | Ejemplo |
|---|---|
| `pregunta` | 4 — ¿Me puedo fiar de lo que dice? |
| `tramo` | B — Fiarse con cabeza |
| `pieza` | Alucinaciones |
| `charla` | 18 (o vacío) |
| `que_sirve` | El texto que se difumina |
| `frase_ancla` | La frase de cierre de la pregunta |
| `preguntar` | true / false (el ❓) |
| `nota` | Ruta de la ficha en el vault |

Comportamiento mínimo:
- El texto `que_sirve` aparece con desenfoque; un clic (o tecla) lo revela.
- Navegación con teclado entre piezas (siguiente / anterior), para llevarla desde la presentación.
- Filtro «solo las ❓», por si hay que acortar en directo.
- Vista de pregunta completa, con todas sus piezas a la vez, para la chuleta final.

> [!important] Plan B
> Si la web no está lista mañana por la mañana, **la dinámica se hace igual con diapositivas**: cada pieza con su texto que aparece al avanzar. Lo importante es la dinámica, no la web. La Biblioteca del Bloque 5 se enseña en cualquier caso solo como vistazo.

---

# Preparación de hoy (martes)

## 1. Las 32 piezas

- Revisar cada texto contra su ficha.
- Decidir si las ❓ son las que propongo o cambiar alguna.
- Montarlas en la web o en diapositivas (plan B).

## 2. Copia limpia del vault para Copilot Desktop

- Copia local aparte (no el vault de trabajo): solo `Charlas/` (**solo las fichas, no `Charlas/guiones/`**: los guiones llevan notas internas y avisos de «qué no decir») y `Conceptos/`.
- **Fuera**: `Proyectos/` (hay una nota de capacidades con personas con nombre), `Demos/` (la demo de Jira lleva una dirección de Atlassian), `Recursos/` y `Plantillas/`.
- Comprobar con una búsqueda de texto que no queda ningún nombre propio de compañeros, ningún cliente ni ninguna dirección interna.
- Comprobar que la licencia de Copilot que uses es la aprobada para este uso (lo que contamos en la 14).
- Comprobar en el ensayo que Copilot Desktop **muestra de verdad las fichas que ha usado**. Si no lo hace, cambiar ese paso por abrir a mano la ficha que respalda la respuesta.

## 3. Las dos preguntas (y una de reserva)

Ejecutar las dos preguntas principales, revisar cada afirmación contra las fichas y guardar capturas. La pregunta sobre alucinaciones queda como reserva. Si una respuesta inventa o no encuentra, **no se enseña esa pregunta**: se cambia por otra.

## 4. La Biblioteca en local

- Regenerar los datos (`prebuild`) y levantar en local.
- Revisar que solo hay Charlas y Conceptos, y que el buscador y el grafo funcionan.
- Dejar capturas por si hay que cambiar de plan.

## 5. Aviso en Teams (borrador, a revisar con tu tono)

> ¡Buenas! Mañana, miércoles 25, volvemos a la hora de siempre con la **Charla 26**. Esta vez no añadimos otra herramienta a la lista ni hace falta saber nada técnico: ordenamos todo lo que hemos visto y para qué sirve cada cosa, con una pequeña dinámica en la que podréis participar por el chat. Además os enseño algo en lo que estoy trabajando. ¡Hasta mañana! :)

---

# Glosario breve para la audiencia

## Retrospectiva
Mirar hacia atrás de forma ordenada para ver qué hemos visto y para qué sirve cada cosa.

## Arnés
El conjunto de piezas (instrucciones, memoria, herramientas, comprobaciones) que hacen que la IA trabaje de forma disciplinada.

## Pieza
Cada herramienta, técnica o concepto de la serie, con su ficha en el vault.

## MCP
Una forma estándar de conectar la IA con aplicaciones y datos.

## SDD, BDD, ODD, RDD
Cuatro formas de decir qué es «correcto» o cómo comprobarlo: guiada por especificación, por comportamiento, por protocolo orgánico y por recibo de revisión.

---

# Checklist antes del miércoles

## Contenido

- [ ] Pantalla de apertura (Bloque 1).
- [ ] Mapa de los cuatro tramos y las diez preguntas (Bloque 2).
- [ ] 32 piezas montadas en web o diapositivas, con texto difuminado y frase ancla (Bloque 3).
- [ ] Tabla del ciclo con Publicar y Mantener señaladas (pregunta 10).
- [ ] Dos preguntas ejecutadas, con fichas y frase de respaldo visibles, y capturas guardadas (Bloque 4).
- [ ] Copia limpia del vault revisada (sin `guiones/`, `Proyectos/`, `Demos/`).
- [ ] Biblioteca en local con solo Charlas y Conceptos, y capturas de reserva (Bloque 5).
- [ ] La chuleta final lista para dejar en Teams (Bloque 6).

## Ensayo narrativo

- [ ] Cronometrar 3 + 3 + 20 + 5 + 2 + 4 minutos, con la dinámica incluida.
- [ ] No decir «última del año», «hasta el año que viene», «cierre» ni nada que suene a despedida de la serie.
- [ ] Una sola tesis: qué pregunta responde cada cosa. Si un bloque se va por otro lado, recortarlo.
- [ ] Mantener estas frases:
  - «Hoy no añadimos otra herramienta. Hoy ponemos orden a lo que ya sabemos.»
  - «No son temas sueltos: son diez preguntas.»
  - «Sobre nuestro trabajo, lo que no está escrito no puede conocerlo de forma fiable.»
  - «No recordéis herramientas. Recordad preguntas.»

---

# Decisiones aplicadas

- **Retrospectiva para afianzar**: el eje es «pieza → para qué sirve», agrupado en diez preguntas de trabajo.
- **Catálogo amplio, dinámica corta**: 32 piezas en pantalla, 12 preguntadas a la sala; el resto se revela directo.
- **Solo piezas trazables a la serie**: se retiran las piezas sin charla confirmada que introducían contenido nuevo.
- **Sin encuesta**, sin bloque de «repeticiones» y sin novedades del mes.
- **Sin demo en directo** (lección de la 23): consulta al vault y Biblioteca se ensayan antes, con capturas.
- **Privacidad**: copia limpia del vault, sin guiones, proyectos ni demos con datos internos.
- **Sin cierre de calendario**: hay charla el 2 de diciembre.

# Decisiones abiertas

1. **¿Diez preguntas en directo?** Se mantienen las diez, pero solo 12 piezas solicitan respuesta. Si el tiempo aprieta, las preguntas 3 y 6 se revelan sin interacción.
2. **Web o diapositivas.** La dinámica sirve en ambas; la web no es imprescindible para mañana.
3. **Número de fichas.** Resuelta el 27 de noviembre de 2026: el índice se corrigió a 81 conceptos (16 + 21 + 27 + 17) y ahora lista todas las fichas de `Conceptos/`.
4. **Niveles de riesgo.** La ley europea tiene 4 categorías y la política interna de la 14 tiene 5 niveles. Si se menciona, decir de cuál se habla.
5. **Piezas que han quedado fuera.** El vocabulario interno de la «AI SDLC Foundation» (prompt como comando, workflow, runtime, station, tier, pack…) y piezas como graphify, caching-cost o github-actions. Quedaron fuera por no estar confirmadas en ninguna charla; las fichas de Foundation figuran ya en el índice, con estado Planificado.
6. **Charla 25 y 21.** Falta el tema exacto de la 25.
7. **Fichas sin retrospectiva.** Las fichas de la 14 a la 22 tienen el apartado «Retrospectiva» vacío; se pueden rellenar tras la charla.
8. **Formato de `related`.** Lista plana como el guion de la 24; las instrucciones del proyecto piden `[[nombre]]`.
