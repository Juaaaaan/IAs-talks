---
type: Charla
title: "Charla 13 — De saber a medir: Copilot Studio y cómo saber si la IA está funcionando"
description: "Resumen exhaustivo de la Charla 13. Chatbot vs agente, construcción de un agente con Copilot Studio, demo en Teams con el handbook corporativo, métricas de analytics y apunte sobre DORA y el AI Productivity Paradox."
tags: [charla, copilot-studio, agentes, metricas, teams, rag, dora, nivel-4]
related: [charla-12-mapa-ia, copilot-studio, metricas-ia , rag, embeddings, agentic-workflows]
timestamp: "2026-07-22"
---

# De saber a medir: Copilot Studio y cómo saber si la IA está funcionando
### Charla 13 — 22 de julio de 2026

---

## La pregunta que dejó abierta la Charla 12

La semana pasada vimos el mapa. Cuatro niveles de madurez en IA. Y descubrimos que ya estábamos en el Nivel 3 sin saberlo.

Pero ese mapa dejó una pregunta sin responder: **¿cómo lo sé? ¿Cómo sé que la IA me está ayudando de verdad y no solo parece que me ayuda?**

Esa pregunta tiene dos partes. La primera: cómo construir algo concreto que la IA haga por ti. La segunda: cómo medirlo para saber si está funcionando.

Hoy cubrimos las dos.

---

## Parte 1 — Chatbot vs agente: la distinción que importa

### Por qué los chatbots tienen mala fama (y con razón)

Antes de hablar de lo que hicimos hoy, hay que aclarar algo. Cuando la gente escucha "chatbot", la reacción instintiva es negativa. Y tiene sentido: todos hemos tenido malas experiencias con ellos.

El chatbot de atención al cliente que te da tres opciones y ninguna es la tuya. El del banco que te manda en bucles. El de cualquier web que te pide que "reformules tu pregunta" cuatro veces antes de decirte que no puede ayudarte.

**¿Por qué pasa esto?** Porque los chatbots clásicos funcionan con flujos predefinidos. Alguien diseña de antemano todos los caminos posibles de la conversación. Si tu pregunta encaja en uno de esos caminos, funciona. Si no encaja, el sistema se rompe — y en lugar de reconocerlo, intenta redirigirte hacia el camino más parecido que tiene configurado.

### Qué es un agente y por qué es diferente

Un agente no sigue un guión. **Razona.**

Cuando le haces una pregunta, el agente entiende lo que estás pidiendo, busca en su conocimiento y construye una respuesta adaptada a tu pregunta concreta. No está buscando el camino predefinido más parecido — está pensando.

La consecuencia más importante de esto: **cuando un agente no sabe algo, lo dice.** No te manda en círculos. No inventa una respuesta plausible. Reconoce que no tiene esa información.

Eso puede parecer un fallo, pero es exactamente lo contrario: es el comportamiento correcto de un sistema en el que puedes confiar.

> *"La diferencia entre un chatbot y un agente es la misma que entre un contestador automático y una persona que realmente te escucha."*

### Lo que hicimos hoy encaja en el Nivel 4

En el mapa de la semana pasada, el Nivel 4 es **Agentic** — automatización profunda donde la IA no solo asiste sino que actúa de forma autónoma dentro de un proceso definido. Lo que construimos hoy es exactamente eso: un agente que opera de forma independiente, con conocimiento propio, sin necesidad de supervisión en cada respuesta.

---

## Parte 2 — Qué es Copilot Studio

### La herramienta

Copilot Studio es la plataforma de Microsoft para crear agentes de IA dentro del ecosistema corporativo. Es la respuesta de Microsoft a la pregunta: *¿cómo construyo algo inteligente que sepa cosas de mi empresa sin que ningún dato salga fuera?*

Hay tres cosas que hay que entender bien antes de verlo en acción:

**No necesita código.** La interfaz de Copilot Studio está diseñada para que cualquier persona pueda construir un agente — RRHH, comercial, operaciones, soporte. No hace falta ser developer. El proceso es visual y los pasos son secuenciales: nombre del agente, instrucciones de comportamiento, documentos de conocimiento, canal de despliegue.

**El conocimiento es vuestro y se queda en vuestra empresa.** Esta es la diferencia fundamental con usar ChatGPT o cualquier modelo público. Los documentos que conectáis al agente no salen de la empresa. El agente accede a ellos a través de SharePoint con las mismas credenciales corporativas que usáis cada día. Nadie externo tiene acceso a ese conocimiento.

**Vive donde ya trabajáis.** El agente no crea una nueva aplicación que la gente tenga que aprender a usar. Se despliega en Teams, en el canal que elijáis. Los usuarios finales simplemente ven un chat en Teams — exactamente como cualquier otra conversación.

### La diferencia con un LLM genérico

Cuando le preguntáis algo a ChatGPT o a Copilot 365 sin más configuración, la IA responde con conocimiento general del mundo. Eso es útil para muchas cosas — redactar, explicar, resumir, traducir.

Pero hay preguntas que ese conocimiento general no puede responder:

- ¿Cuántos profesionales somos actualmente en nuestra empresa?
- ¿Cuál es el proceso para pedir un cambio de proyecto aquí?
- ¿Qué dice nuestro handbook sobre el período de prueba?

Esas respuestas no están en internet. Están en vuestros documentos. Un agente de Copilot Studio conectado a esos documentos sí puede responderlas.

> *"La diferencia entre un LLM genérico y un agente de Copilot Studio es la misma que entre un becario recién llegado y alguien que lleva tres años en la empresa y conoce todos los procesos."*

---

## Parte 3 — Cómo se construye un agente: lo que visteis en la demo

### El agente que construimos

El agente de hoy se llama **Agente de bienvenida**. Su propósito: responder las preguntas que tiene cualquier persona nueva en la empresa durante sus primeras semanas.

Es un caso de uso intencionadamente accesible para cualquier rol de la sala — no es técnico, es universal. Todos hemos sido nuevos en algún sitio. Todos sabemos lo que es no saber a quién preguntar en los primeros días.

### Los pasos del proceso

**Paso 1 — Abrir Copilot Studio**
La interfaz principal de Copilot Studio está en `make.preview.microsoft.com`. Desde ahí se gestionan todos los agentes.

**Paso 2 — Crear el agente y configurar instrucciones**
Al crear un agente nuevo, lo primero es darle instrucciones de comportamiento. Estas instrucciones definen:
- Para qué sirve el agente y qué tipo de preguntas debe responder
- Cómo debe comportarse (tono, idioma, nivel de formalidad)
- Qué debe hacer cuando no tiene información — en nuestro caso: reconocerlo explícitamente y redirigir al contacto de RRHH

Las instrucciones son texto en lenguaje natural. No es código. Es exactamente como le explicarías a una persona qué tiene que hacer.

**Paso 3 — Conectar el conocimiento**
En la sección de Knowledge del agente, conectamos el handbook corporativo 2026 a través de una URL de SharePoint.

Lo que ocurre por debajo es el proceso que visteis en la Charla 12 cuando hablamos de **RAG y embeddings**: Copilot Studio lee el documento, extrae el significado semántico de cada párrafo y lo almacena de forma que el agente pueda consultarlo eficientemente cuando alguien le pregunte.

**Nota técnica importante:** En el entorno LITE de Copilot Studio no es posible subir ficheros directamente. El conocimiento se añade mediante URLs de SharePoint. Esto también significa que solo los usuarios autenticados con cuentas corporativas pueden acceder a ese conocimiento — el agente no funciona con el panel de test interno, que no tiene esas credenciales. La forma correcta de probar el agente es desde Teams.

**Paso 4 — Desplegar en Teams**
Una vez configurado el agente, se publica en Teams. El despliegue crea un canal específico en Teams para el agente. Cualquier persona con acceso a ese canal puede hablar con el agente directamente, sin instalar nada adicional.

### Lo que respondió y lo que no — y por qué eso importa

Probamos tres preguntas en directo:

**Pregunta 1: ¿Cuántos profesionales trabajamos en la empresa?**
El agente respondió correctamente, citando el dato del handbook. No lo inventó — lo extrajo del documento que le habíamos conectado.

**Pregunta 2: ¿Cuál es la política de teletrabajo?**
El agente indicó que no tenía esa información en sus documentos. La política de teletrabajo no está en el handbook que conectamos.

**Pregunta 3: ¿Cuál es la política de bonus de fin de año?**
Misma respuesta: no tiene esa información.

Las preguntas 2 y 3 generaron el momento más importante de la demo. No son fallos — son **el comportamiento correcto**. Un agente que reconoce los límites de su conocimiento es mucho más fiable que uno que inventa respuestas para todo.

Y la lección operativa que se desprende de esto es inmediata: si queremos que el agente responda sobre la política de teletrabajo, la solución es añadir ese documento al conocimiento. Un paso, cinco minutos. Eso es exactamente cómo se itera y mejora un agente en producción.

> *"Un agente que reconoce lo que no sabe es más valioso que uno que siempre responde algo."*

---

## Parte 4 — Cómo saber si la IA está funcionando

### El problema que nadie menciona

Construir el agente es la parte más visible. Pero hay una pregunta que muy poca gente se hace antes de desplegarlo en producción: **¿cómo voy a saber si está funcionando bien?**

No es suficiente con que el agente responda. La pregunta real es si está ayudando de verdad a la gente. Si la gente lo usa. Si resuelve sus problemas o si después de hablar con él van igualmente a preguntárselo a una persona.

Copilot Studio tiene un dashboard de analytics integrado. Desde el momento en que el agente está publicado, empieza a acumular datos de cada conversación.

### Las tres métricas que hay que mirar siempre

**Engagement rate**
¿Qué porcentaje de personas que abrieron el agente le hicieron al menos una pregunta?

Si este número es bajo, el agente no está siendo descubierto — la gente lo abre, ve que hay algo ahí y lo cierra sin interactuar. O no entiende para qué sirve. La solución suele ser mejorar la descripción del agente y asegurarse de que las indicaciones sugeridas son relevantes y directas.

**Resolution rate**
¿Qué porcentaje de conversaciones terminaron con el problema resuelto, sin que la persona tuviera que ir a buscar ayuda a otro lado?

Esta es la métrica más importante. Un agente con resolution rate bajo está respondiendo pero no resolviendo. Las razones pueden ser múltiples: el conocimiento es incompleto, las instrucciones son demasiado restrictivas, las respuestas son demasiado generales. Cada caída en esta métrica tiene una causa identificable.

**Deflection rate**
¿Cuántas solicitudes resolvió el agente sin intervención humana?

Si RRHH respondía 50 preguntas al mes y el agente resuelve 35 de ellas de forma autónoma, el deflection rate es del 70%. Esta es la métrica que le interesa a dirección y a cualquier persona que tenga que justificar la inversión en el agente.

### Métricas personalizadas en lenguaje natural

Una de las funcionalidades más potentes del dashboard es la posibilidad de definir métricas propias en lenguaje natural. No hace falta código. Se describe en texto qué quieres medir y Copilot Studio aplica esa lógica a las conversaciones.

Ejemplos prácticos:
- *"¿El usuario expresó satisfacción al final de la conversación?"*
- *"¿La respuesta llevó al usuario a completar la acción que buscaba?"*
- *"¿El usuario tuvo que reformular su pregunta más de dos veces?"*

Esto permite adaptar las métricas al caso de uso específico de cada agente, en lugar de depender solo de los indicadores genéricos.

### Las tres preguntas que cualquier métrica de IA debe responder

Para cualquier rol — RRHH, comercial, developer, directivo — hay tres preguntas que simplifican toda la conversación sobre métricas de IA:

| Pregunta | Métrica |
|----------|---------|
| ¿Lo usa la gente? | Adoption rate |
| ¿Les ayuda? | Resolution rate |
| ¿Vuelven? | Retención semana a semana |

Si las tres son positivas, la IA está funcionando. Si alguna falla, sabéis exactamente en qué punto del ciclo está el problema.

---

## Parte 5 — Apunte para equipos de desarrollo: DORA y el AI Productivity Paradox

Este bloque es más específico para perfiles técnicos, pero el hallazgo central es relevante para cualquier responsable de equipo.

### Qué es DORA

DORA (DevOps Research and Assessment) es un programa de investigación que publica anualmente un informe sobre la salud de los equipos de desarrollo de software. Sus cuatro métricas clásicas son:

- **Deployment frequency** — con qué frecuencia despliega el equipo a producción
- **Lead time for changes** — cuánto tiempo pasa desde que se escribe una línea de código hasta que llega a producción
- **Change failure rate** — qué porcentaje de despliegues causan problemas
- **Time to restore service** — cuánto tarda el equipo en recuperarse de un incidente

### El hallazgo del informe DORA 2025

La adopción masiva de herramientas de IA para desarrollo ha generado un efecto inesperado. Los asistentes de código IA disparan el output individual — los datos apuntan a hasta un 98% más de pull requests generados por desarrollador.

Pero las métricas de entrega organizacional se mantienen planas. No mejoran al mismo ritmo.

¿Por qué? Porque el tiempo ahorrado escribiendo código con frecuencia regresa como tiempo invertido en revisar y depurar las sugerencias de la IA. Los investigadores lo llaman el **"verification tax"** — el coste oculto de validar lo que la IA ha generado.

El nombre que le han dado a este fenómeno es el **AI Productivity Paradox**: más velocidad individual, métricas organizacionales planas.

### La conclusión práctica

Más velocidad sin calidad no es progreso — es deuda técnica acumulada. Medir el impacto de la IA en un equipo de desarrollo requiere ir más allá de contar cuánto código se genera o cuántos pull requests se abren.

Este tema da para una charla completa. Y la tendremos.

> *"Medir adopción es fácil. Medir impacto real es el siguiente reto."*

---

## Tres ideas para llevarse

**Primera: Copilot Studio no es para developers.**
Es para cualquier persona que tenga conocimiento que vale la pena capturar y compartir. Si en vuestro trabajo hay preguntas que se repiten — y en todos los trabajos las hay — hay un agente que puede responderlas.

**Segunda: construir es la parte fácil. Medir es la que marca la diferencia.**
Un agente que nadie usa no sirve de nada. Un agente cuyo uso medís, revisáis y mejoráis de forma continua se convierte en una pieza real de cómo trabaja el equipo.

**Tercera: esto es el Nivel 4.**
Lo que visteis hoy — un agente con conocimiento propio de la empresa, desplegado en Teams, con métricas para mejorarlo — es exactamente donde el mapa de la semana pasada decía que ibais. No es el futuro. Es lo que ya podéis hacer esta semana.

---

## Glosario de conceptos vistos hoy

**[[agente-ia|Agente de IA]]**
Sistema de IA que razona sobre una pregunta, busca en su conocimiento y construye una respuesta. A diferencia de un chatbot clásico, no sigue flujos predefinidos.

**Chatbot clásico**
Sistema conversacional basado en flujos predefinidos. Funciona bien para preguntas que encajan en los caminos diseñados de antemano. Falla cuando la pregunta no encaja.

**[[copilot-studio|Copilot Studio]]**
Plataforma de Microsoft para crear agentes de IA dentro del ecosistema corporativo. Permite conectar documentos propios (vía SharePoint), definir instrucciones de comportamiento y desplegar el agente en Teams.

**[[rag|RAG (Retrieval-Augmented Generation)]]**
Técnica por la que un modelo de IA busca primero en una base de documentos específica antes de responder. Lo que hace el agente de Copilot Studio cuando accede al handbook.

**[[embeddings|Embeddings]]**
Representación matemática del significado de un texto. Copilot Studio convierte cada párrafo del documento en embeddings para buscar eficientemente qué partes son relevantes ante cada pregunta.

**Engagement rate** — Porcentaje de usuarios que interactuaron con el agente al menos una vez.

**Resolution rate** — Porcentaje de conversaciones que el agente resolvió sin escalar a una persona.

**Deflection rate** — Porcentaje de solicitudes que el agente atendió de forma autónoma.

**[[metricas-ia|DORA]]** — DevOps Research and Assessment. Cuatro métricas para medir la salud de equipos de desarrollo: frecuencia de despliegue, tiempo hasta producción, tasa de fallos y tiempo de recuperación.

**AI Productivity Paradox** — Fenómeno DORA 2025: la IA aumenta el output individual pero las métricas organizacionales se mantienen planas por el "verification tax".

---

## Próxima charla

**Charla 14 — Métricas de IA en profundidad**
Métricas DORA, developer velocity y cómo medir el impacto real de la IA en equipos de desarrollo.

---

*Charla 13 — Serie de formación interna en IA — 22 de julio de 2026*
