---
type: Recurso
title: "IA al día — Semana del 13 al 19 de octubre de 2026"
description: "Digest semanal de novedades de IA para la serie IAs-talks. Selección accesible (público mayoritariamente no técnico): Google lanza Gemini 4 Argon a nivel mundial, OpenAI encuentra un dispositivo de grabación oculto en sus oficinas, Liquid AI publica un modelo de razonamiento que corre en un portátil, TypeSafe AI dispara su valoración con Jev (un modelo de decisiones, no de texto), y sube el uso de IA en entrevistas de trabajo en Reino Unido."
tags: [recurso, ia-al-dia, novedades, digest-semanal, semana-13-10-2026]
timestamp: "2026-10-16"
---

# IA al día — Semana del 13 al 19 de octubre de 2026

Resumen de lo que ha movido la aguja esta semana, contado en cristiano. Por cada noticia: **qué ha pasado** y **por qué te importa**. (Datos a fecha del 16 de octubre.)

---

## 1. Google lanza Gemini 4 Argon a nivel mundial

**Qué ha pasado.** Google ha puesto Gemini 4 Argon a disposición general de desarrolladores, empresas y consumidores, tras meses de retraso y cambios de liderazgo en DeepMind. Soporta hasta 1 millón de tokens de contexto, y Google asegura que sus propios ingenieros han aumentado más de un 35% el código escrito por agentes desde que lo usan internamente.

**Por qué te importa.** Es el mismo tablero de la Charla 17 (elegir IA): cada pocas semanas cambia quién va en cabeza. Si el equipo tiene algo montado sobre un modelo "porque siempre se usó ese", esta semana es un buen momento para comprobar si sigue siendo la mejor opción para la tarea.

Fuente: [Unrot, 14 oct](https://www.unrot.co/ai-news/2026/10/14)

---

## 2. OpenAI encuentra un dispositivo de grabación oculto en sus oficinas

**Qué ha pasado.** OpenAI descubrió un micrófono oculto en una sala de reuniones ejecutiva de su oficina de San Francisco a finales de septiembre. Usando sus propios modelos para rastrear el origen, identificó a un empleado, que fue detenido por el FBI el 9 de octubre y despedido. La compañía afirma no tener indicios de que se accediera a los pesos del modelo, al código o a datos de clientes.

**Por qué te importa.** Es un recordatorio de que la seguridad de la IA no es solo "que el modelo no haga cosas raras" (Charla 15) — también es la seguridad física y operativa alrededor de quien la construye. Y de propina: la propia IA fue la herramienta usada para destapar el caso.

Fuente: [The Neuron, 13 oct](https://www.theneuron.ai/digest/everything-that-happened-in-ai-today-tuesday-october-13-2026/)

---

## 3. Liquid AI publica un modelo de razonamiento que corre en tu portátil

**Qué ha pasado.** Liquid AI ha lanzado LFM2.5-24B-A2B, un modelo de pesos abiertos de 24.000 millones de parámetros (solo ~2.000 millones activos por token), pensado para agentes de varios pasos corriendo en portátiles y PCs normales — 184 tokens por segundo en un Apple M5 Max, con ventana de contexto de 131.000 tokens.

**Por qué te importa.** Encaja directo con la Charla 20 (el ejecutor abierto): cada vez hace menos falta depender de la nube de un proveedor grande para tener un agente útil — se puede ejecutar donde viven los datos, sin salir de la máquina.

Fuente: [Unrot, 14 oct](https://www.unrot.co/ai-news/2026/10/14)

---

## 4. Sube el uso de IA en entrevistas de trabajo en Reino Unido

**Qué ha pasado.** Según The Guardian, reclutadores británicos reportan que cada vez más candidatos usan IA durante las entrevistas de trabajo, y una asociación que representa a grandes empleadores de graduados registra el nivel más alto hasta ahora de conducta irregular por parte de candidatos.

**Por qué te importa.** Conecta con el tema que nos trajo RRHH tras la Charla 18: la IA ya está en procesos que antes dábamos por "solo humanos", y las reglas del juego (qué es trampa, qué no) todavía se están escribiendo sobre la marcha, no solo aquí.

Fuente: [The Neuron, 13 oct](https://www.theneuron.ai/digest/everything-that-happened-in-ai-today-tuesday-october-13-2026/)

---

## 5. TypeSafe AI dispara su valoración con Jev, un modelo que no genera texto: decide

**Qué ha pasado.** TypeSafe AI — fundada en 2024 por Diogo Almeida, que pasó cuatro años en OpenAI trabajando en RLHF, InstructGPT, ChatGPT y GPT-4 — lanzó el 15 de septiembre su modelo Jev en acceso limitado, junto a una ronda semilla de 40 millones de dólares liderada por DCVC. Jev no es un modelo generativo: es discriminativo. Recibe un estado y una o varias preguntas de opción cerrada (verdadero/falso, elección, puntuación), las responde todas en paralelo, y devuelve valores tipados con probabilidad y confianza — pensado para que lo consuma software, no personas. TypeSafe dice que responde en 70-500 milisegundos, entre 40 y 200 veces más rápido y hasta 400 veces más barato que un LLM de frontera en pruebas propias. Bloomberg informó el 9 de octubre que la compañía ya habría levantado unos 870 millones de dólares a una valoración de 7.500 millones, liderados por Andreessen Horowitz — sin confirmación oficial de cuándo cerró la ronda.

**Por qué te importa.** Encaja con lo que vimos en la Charla 23: ODD depende de clasificar rápido y barato si un cambio es "pequeño" o "sustancial" antes de decidir cuánto proceso merece. Un modelo como Jev es justo esa pieza — no sustituye al LLM que escribe o razona, resuelve la decisión rápida que hoy delegamos, por comodidad, al mismo modelo grande que hace todo lo demás.

Fuente: [RuntimeWire, 9 oct](https://runtimewire.com/article/typesafe-jev-reported-870m-financing)

---

## 6. De fondo: ¿se puede frenar la carrera de la IA, o solo gobernarla?

**Qué ha pasado.** Un artículo de Noema argumenta que frenar la carrera entre laboratorios de IA puede ser, directamente, imposible — y que la vía realista no es esperar que las empresas se autolimiten, sino construir supervisión externa que funcione aunque la carrera siga.

**Por qué te importa.** Es la pregunta de fondo de la Charla 14 (gobernanza) formulada de otra manera: si nadie va a pisar el freno voluntariamente, ¿qué reglas hacen falta para que la velocidad no se traduzca en descontrol? No hay respuesta cerrada todavía, pero el debate está más vivo que nunca.

Fuente: [The Neuron, 13 oct](https://www.theneuron.ai/digest/everything-that-happened-in-ai-today-tuesday-october-13-2026/)

---

## El hilo de la semana

Un modelo de frontera disponible para todo el mundo (Gemini 4 Argon), un modelo abierto que cabe en un portátil (Liquid AI), y un modelo que ni siquiera genera texto — solo decide, 200 veces más rápido (Jev): la IA se está partiendo en especialidades distintas en vez de converger en una sola. Y mientras tanto, sigue entrando por la puerta de atrás en sitios que no esperábamos — una entrevista de trabajo, una sala de reuniones — antes de que nadie haya terminado de decidir las reglas. El patrón de la serie se repite: la tecnología no espera a la gobernanza, así que la gobernanza tiene que aprender a correr.

---

*Digest de la serie IAs-talks. Selección accesible; las fuentes son mayoritariamente agregadores del sector, así que para datos concretos (fechas, cifras) conviene contrastar en la fuente primaria antes de citarlos en algo formal.*
