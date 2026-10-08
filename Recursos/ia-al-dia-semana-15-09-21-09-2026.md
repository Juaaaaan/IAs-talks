---
type: Recurso
title: "IA al día — Semana del 15 al 21 de septiembre de 2026"
description: "Digest semanal de novedades de IA para la serie IAs-talks (backfill). Selección accesible: Claude Code empieza a leer AGENTS.md cuando falta CLAUDE.md, una posible brecha vía agente de IA investigada por la AEPD española, Google Home abre una interfaz MCP con acciones sensibles bloqueadas, Anthropic fusiona Claude chat y Cowork, Paper2Agent convierte papers en agentes MCP, y la carrera de modelos no da tregua."
tags: [recurso, ia-al-dia, novedades, digest-semanal, semana-15-09-2026]
timestamp: "2026-09-22"
---

# IA al día — Semana del 15 al 21 de septiembre de 2026

Resumen de lo que ha movido la aguja esta semana, contado en cristiano. Por cada noticia: **qué ha pasado** y **por qué te importa**. (Datos a fecha del 22 de septiembre.)

---

## 1. Claude Code aprende a leer AGENTS.md cuando no hay CLAUDE.md

**Qué ha pasado.** Anthropic actualizó Claude Code (versión 2.1.277) para que, si no encuentra un fichero `CLAUDE.md` en el proyecto, busque y lea en su lugar un `AGENTS.md` con las instrucciones de cómo trabajar en ese repositorio.

**Por qué te importa.** Es justo el patrón que ya tenemos en el vault — el `agents-md-rca.md` de RCA es exactamente ese fichero. La idea de la Charla 8 (instrucciones persistentes) y de la Charla 11 (Wiki LLM) sigue ganando terreno como estándar de facto: un fichero de texto normal, leído por cualquier agente, da igual el proveedor.

Fuente: [AI Weekly, 19 sep](https://aiweekly.co/ai-news-today/edition/2026-09-19)

---

## 2. La AEPD investiga una posible brecha causada por un agente de IA

**Qué ha pasado.** La Agencia Española de Protección de Datos recibió una notificación de brecha en la que un agente de IA podría haber encadenado un inicio de sesión, una fase de reconocimiento y el acceso a datos personales. La causa completa todavía no está establecida.

**Por qué te importa.** Es el gap de confianza del que hablamos en el digest anterior, pero ya no en abstracto: es la agencia española, la que nos regula a nosotros si algo sale mal. Enlaza directo con la Charla 15 (seguridad) y con el checkpoint humano de la Charla 19 — un agente que encadena acciones solo, sin que nadie se dé cuenta hasta que llega la notificación de brecha, es justo el escenario que ese checkpoint existe para evitar.

Fuente: [AI Weekly, 17 sep](https://aiweekly.co/ai-news-today/edition/2026-09-17)

---

## 3. Google Home abre una puerta MCP para que los agentes controlen tu casa — con límites

**Qué ha pasado.** Google abrió un acceso anticipado a una interfaz MCP que permite a agentes como Claude o ChatGPT consultar y controlar dispositivos Nest. Las acciones sensibles, como abrir una cerradura, quedan bloqueadas por defecto.

**Por qué te importa.** Es MCP (Charla 7) saliendo del ordenador y entrando en el mundo físico, con el mismo reflejo que ya conocéis: dejar que el agente consulte y actúe, pero dibujando antes una línea roja para lo irreversible. El mismo principio que el checkpoint humano de la Charla 19, aplicado a quién puede abrirte la puerta de casa.

Fuente: [AI Weekly, 17 sep](https://aiweekly.co/ai-news-today/edition/2026-09-17)

---

## 4. Anthropic fusiona el chat de Claude y Cowork en una sola interfaz

**Qué ha pasado.** Anthropic unificó el chat normal de Claude y su entorno de trabajo Cowork en una sola interfaz que enruta automáticamente cada petición a donde mejor se resuelve, con exportación de diapositivas a PDF o PowerPoint. De momento, para usuarios Pro y Max.

**Por qué te importa.** Menos sitios donde decidir "¿esto lo hago en el chat o en el entorno de trabajo?" — la propia herramienta decide por vosotros. Es el mismo criterio "construir o ya existe" que veríamos más adelante en la Charla 22, aplicado esta vez por el propio proveedor: simplificar en vez de añadir una pestaña más.

Fuente: [AI Weekly, 17 sep](https://aiweekly.co/ai-news-today/edition/2026-09-17)

---

## 5. Paper2Agent convierte papers de investigación en agentes utilizables

**Qué ha pasado.** Un equipo de investigación presentó Paper2Agent, un sistema que convirtió 74 de 100 papers de biología computacional en herramientas MCP funcionales, sin necesidad de limpieza manual del código.

**Por qué te importa.** Es la Charla 19 (equipo de agentes que actúa) llevada a un terreno distinto: convertir conocimiento estático — un documento — en algo que se puede consultar y ejecutar. El mismo salto de "responder" a "actuar" que vimos con el Analista de RFP, aplicado a investigación científica.

Fuente: [AI Weekly, 17 sep](https://aiweekly.co/ai-news-today/edition/2026-09-17)

---

## 6. De fondo: la carrera de modelos no da tregua

**Qué ha pasado.** Anthropic estaría evaluando el lanzamiento de un nuevo modelo para hacer frente a GPT-6 Astra de OpenAI, con la salida a bolsa de la compañía en el horizonte; mientras tanto, Huawei anunció sus próximos chips Ascend 960DT y 960PR para 2027.

**Por qué te importa.** La brújula de la Charla 17 sigue siendo la misma: el panorama de modelos y de quién los ejecuta cambia cada pocas semanas. No hace falta seguir cada movimiento — sí conviene no atarse a uno solo.

Fuente: [AI Weekly, 19 sep](https://aiweekly.co/ai-news-today/edition/2026-09-19)

---

## El hilo de la semana

Un patrón se repite en casi todas las noticias de esta semana: el agente deja de ser una caja negra y empieza a tener **puertas con cerradura** — el AGENTS.md que cualquiera puede leer, el bloqueo de acciones sensibles en Google Home, la brecha de la AEPD que obliga a preguntarse quién vigilaba. Es la misma idea de fondo que recorre toda la serie: cuanto más capaz es el agente, más importa quién decide dónde se para.

---

*Digest de la serie IAs-talks. Selección accesible; las fuentes son mayoritariamente agregadores del sector, así que para datos concretos (fechas, cifras) conviene contrastar en la fuente primaria antes de citarlos en algo formal.*
