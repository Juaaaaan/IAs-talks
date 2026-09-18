---
type: Recurso
title: "IA al día — Semana del 8 al 14 de septiembre de 2026"
description: "Digest semanal de novedades de IA para la serie IAs-talks. Selección accesible (público mayoritariamente no técnico): qué ha pasado y por qué te importa. Cubre la API de agentes de OpenAI (harness gestionado, sin retención cero), los agentes 'de fábrica' de Salesforce Agentforce, el gap de confianza en la gobernanza de agentes, el movimiento regulatorio europeo, la carrera de modelos que no para, y los agentes metiéndose en el editor de código."
tags: [recurso, ia-al-dia, novedades, digest-semanal, semana-08-09-2026]
timestamp: "2026-09-15"
---

# IA al día — Semana del 8 al 14 de septiembre de 2026

Resumen de lo que ha movido la aguja esta semana, contado en cristiano. Por cada noticia: **qué ha pasado** y **por qué te importa**. (Datos a fecha del 15 de septiembre; recoge también lo destacado desde el último digest.)

---

## 1. OpenAI empaqueta su "motor" de agentes como servicio… pero con letra pequeña

**Qué ha pasado.** El 10 de septiembre, OpenAI abrió en beta pública su **Agents API**: básicamente, alquilan el mismo "harness" (el motor que coordina al agente: contexto, herramientas, sesiones largas) que mueve su Codex, para que cualquiera lo use como un servicio gestionado. Lo que antes tenías que montar tú, ahora te lo dan hecho. Pero trae dos avisos: durante la beta **los datos solo residen en EE. UU. y no hay retención cero de datos**, ni siquiera si conectas tu propia infraestructura.

**Por qué te importa.** Es justo la película de la Charla 20, y en directo. Un ejecutor de agentes potentísimo, pero cerrado y con tus datos viviendo fuera y sin garantía de que no se retengan. Para un trabajo regulado (pólizas, clientes), esas dos líneas deciden si es un juguete de pruebas o algo que puedes llevar a producción. Es el contraste perfecto con lo abierto: *quién controla el motor y dónde viven los datos*.

Fuente: [OpenAI — Introducing the Agents API](https://openai.com/index/introducing-the-agents-api/) · [DEV — qué cambió en la beta 2026-09-10](https://dev.to/commerceframe_015eb18e5bb/openai-agents-api-for-teams-what-changed-in-the-2026-09-10-public-beta-13fa)

---

## 2. Salesforce saca agentes "de fábrica" con nombre y apellido

**Qué ha pasado.** El 11 de septiembre, Salesforce presentó **siete agentes Agentforce ya montados** (Casey, Paige, Carter, Hunter, Marshall, Piper y Fin), cada uno para una función concreta: ventas, atención, comercio, IT/RRHH, cadena de suministro… Se apoyan en los datos que la empresa ya tiene y operan **dentro de las reglas, permisos y seguridad existentes**.

**Por qué te importa.** Es la otra vía frente a montártelo tú (como hicimos con el "Analista de RFP" en la [[guion-charla-19|Charla 19]]): agentes prefabricados que enchufas. Cómodo para arrancar rápido, pero fíjate en el matiz que sí importa a todos — que operen dentro de los permisos y la seguridad de la empresa. Ese "dentro de las reglas" es justo lo que separa un agente útil de un agente peligroso.

Fuente: [AI Agent Store — noticias de agentes](https://aiagentstore.ai/ai-agent-news/this-week)

---

## 3. Las empresas confían en sus agentes… pero no los controlan

**Qué ha pasado.** Un informe (Harness) pone número a algo incómodo: hay un **"gap de confianza"** grande. El 77 % de las organizaciones dice tener un inventario completo de sus agentes, pero solo el 44 % usa herramientas para descubrirlos de verdad; el 74 % confía en que sus pruebas pillarán los fallos, pero solo el 19 % tiene un freno automático que bloquee una versión mala antes de soltarla.

**Por qué te importa.** Traducido: mucha gente está confiando en fe, no en controles. Es exactamente el porqué del **checkpoint humano** que montamos en la Charla 19, y enlaza con la Charla 15 (seguridad): un agente que actúa solo, sin un botón de "para" y sin saber siquiera cuántos agentes tienes sueltos, es un riesgo real de producción y de datos.

Fuente: [AI Agent Store — noticias de agentes](https://aiagentstore.ai/ai-agent-news/this-week)

---

## 4. Europa mueve ficha con la Ley de IA

**Qué ha pasado.** Desde la Comisión Europea, Ursula von der Leyen planea sentar a los grandes laboratorios de IA y usar la Ley de IA para ayudar a fijar estándares globales de seguridad, citando como riesgos inmediatos el **hackeo autónomo** y los **modelos que se automejoran**.

**Por qué te importa.** Nos toca de cerca: somos una empresa europea, y la regulación que salga de aquí marca las reglas del juego para lo que podemos y no podemos usar. Es el terreno de la Charla 14 (gobernanza) — mientras las herramientas corren, las reglas intentan alcanzarlas, y en Europa esas reglas pesan.

Fuente: [LLM Stats — noticias de IA](https://llm-stats.com/ai-news)

---

## 5. La carrera de modelos no da tregua ("fatiga de modelos")

**Qué ha pasado.** Sigue la avalancha: en septiembre se han publicado más de una docena de modelos nuevos de varios proveedores, con Anthropic (Claude Fable 5.1 y Mythos 5.1), OpenAI (GPT-6 Astra), Meta y Google soltando versiones casi la misma semana. Hasta en el sector hablan ya de *"model fatigue"*, fatiga de tanto lanzamiento.

**Por qué te importa.** Lo práctico de siempre (Charla 17, elegir IA): el "mejor modelo" cambia cada pocas semanas, y con él el precio y los límites. No te cases con uno; lo que importa es poder cambiar de motor sin rehacerlo todo — que es, otra vez, la ventaja de no estar atrapado.

Fuente: [CNBC — 'model fatigue' en los laboratorios de IA](https://www.cnbc.com/2026/09/06/meta-google-openai-anthropic-ai-model-fatigue.html)

---

## 6. De fondo, para desarrolladores: el agente se muda al editor

**Qué ha pasado.** Los agentes siguen metiéndose dentro de las herramientas de trabajo de siempre: los editores de código incorporan sesiones de agente que continúan tareas, resuelven conflictos de fusión y trabajan sobre varias carpetas; y en Microsoft ya hablan de apoyarse en agentes para construir aplicaciones nativas más rápido.

**Por qué te importa.** Para los perfiles técnicos de la sala: el agente ya no es una pestaña aparte, es parte del sitio donde trabajas. Es la idea de la Charla 19 —de responder a actuar— aplicada al desarrollo: el agente hace parte del trabajo y tú revisas y apruebas.

Fuente: [AI Agents Directory — brief de agentes](https://aiagentsdirectory.com/news/ai-agents-news-brief-september-6-2026)

---

## El hilo de la semana

Todo apunta al mismo sitio: **el "motor" de los agentes se está convirtiendo en producto.** OpenAI lo vende gestionado (cómodo, pero cerrado, en EE. UU. y sin retención cero), Salesforce lo vende prefabricado, y por detrás corren las preguntas de gobierno (el gap de confianza, Europa) intentando alcanzarlo. Es, palabra por palabra, el terreno de la Charla 20: cuando el motor lo pone otro, la pregunta no es si funciona, sino **quién lo controla y dónde viven tus datos**. La semana no cambia el mensaje; lo pone sobre la mesa.

---

*Digest de la serie IAs-talks. Selección accesible; las fuentes son mayoritariamente agregadores del sector, así que para datos concretos (fechas, cifras) conviene contrastar en la fuente primaria antes de citarlos en algo formal.*
