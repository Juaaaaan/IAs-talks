---
type: Recurso
title: "IA al día — Semana del 1 al 7 de septiembre de 2026"
description: "Digest semanal de novedades de IA para la serie IAs-talks. Selección accesible (público mayoritariamente no técnico): qué ha pasado y por qué te importa. Cubre la llegada de Claude a Microsoft Copilot y Copilot Studio, la compra de Hugging Face por Nvidia, la demanda de Sony y Warner a Anthropic por las letras, la reordenación de límites de uso entre proveedores, la seguridad de/frente a agentes, y los agentes que se cuelan en los editores de código."
tags: [recurso, ia-al-dia, novedades, digest-semanal, semana-01-09-2026]
timestamp: "2026-09-04"
---

# IA al día — Semana del 1 al 7 de septiembre de 2026

Resumen de lo que ha movido la aguja esta semana, contado en cristiano. Por cada noticia: **qué ha pasado** y **por qué te importa**. (Datos a fecha del 4 de septiembre.)

---

## 1. Claude llega a Microsoft Copilot… y a Copilot Studio

**Qué ha pasado.** Microsoft ha empezado a habilitar modelos de Anthropic (Claude) dentro de su ecosistema Copilot: el 1 de septiembre anunció la disponibilidad de Claude Fable 5.1 en Microsoft Copilot, y los modelos de Anthropic pueden seleccionarse al construir agentes en Copilot Studio, conviviendo con los de OpenAI.

**Por qué te importa.** Es justo el Copilot Studio donde el otro día montamos el "Analista de RFP" con GPT-5.5. Que puedas elegir también modelos de Claude significa poder darle a cada agente el "cerebro" que mejor encaje con su tarea (lo de la Charla 17, elegir IA, dentro de la propia herramienta). Merece la pena revisar si ya te aparece en tu tenant — cuando montamos la charla todavía no estaba.

Fuente: [Microsoft Adoption — Copilot Studio](https://adoption.microsoft.com/en-us/ai-agents/copilot-studio/) · [Power Platform — release plan Copilot Studio](https://learn.microsoft.com/en-us/power-platform/release-plan/2026wave1/microsoft-copilot-studio/)

---

## 2. Nvidia compra Hugging Face por 12.900 millones de dólares

**Qué ha pasado.** Nvidia ha firmado el acuerdo para adquirir Hugging Face, la plataforma donde la comunidad publica y comparte modelos de IA de código abierto (una especie de "GitHub de los modelos"). La operación se cerraría en la primera mitad de 2027.

**Por qué te importa.** Quien fabrica los chips que mueven la IA se queda también con el sitio donde vive gran parte de la IA abierta. Es una señal más de concentración del sector en pocas manos — algo a tener en el radar cuando se decide de qué proveedores depende tu empresa a largo plazo.

Fuente: [AI Weekly](https://aiweekly.co/)

---

## 3. Sony y Warner demandan a Anthropic por las letras de canciones

**Qué ha pasado.** Sony Music Publishing y Warner Chappell han presentado una demanda contra Anthropic (y sus fundadores a título personal) por el uso de letras de canciones protegidas, reclamando hasta 150.000 dólares por canción.

**Por qué te importa.** El debate de "¿con qué datos se han entrenado estos modelos?" sigue vivo y en los tribunales. Para una empresa, es el recordatorio de siempre: vigila qué material protegido entra y sale de estas herramientas, y no des por hecho que "lo que genera la IA" está libre de derechos. Enlaza con lo que vimos en gobernanza (Charla 14).

Fuente: [AI Tools Recap — noticias septiembre 2026](https://aitoolsrecap.com/Blog/AINewsSeptember2026.aspx)

---

## 4. Los proveedores vuelven a reordenar los límites de uso

**Qué ha pasado.** En dos semanas, varios proveedores han reestructurado sus límites y precios: Google introduce límites por consumo en Gemini Notebook, Anthropic ajusta los límites semanales de Claude Code (con un cambio fechado el 14 de septiembre) y reprecia Sonnet 5.

**Por qué te importa.** Muy práctico: las reglas del juego (cuánto puedes usar y a qué precio) cambian cada pocas semanas. Si dependes de una herramienta para algo importante, conviene saber de qué plan y qué límites dependes, y no llevarte la sorpresa a mitad de mes.

Fuente: [AI Tools Recap — noticias septiembre 2026](https://aitoolsrecap.com/Blog/AINewsSeptember2026.aspx)

---

## 5. La seguridad *de* los agentes (y *frente a* ellos) se vuelve un frente propio

**Qué ha pasado.** Con los agentes actuando cada vez más solos, la seguridad se mueve en dos direcciones: empiezan a surgir empresas (y rondas de inversión) dedicadas a bloquear el "tráfico de ataque" generado por agentes, y a la vez los grandes laboratorios avisan de que sus modelos rozan nuevos umbrales de capacidad en ciberseguridad. Google, por su parte, ha lanzado un modelo específico para equipos de defensa.

**Por qué te importa.** Es la otra cara de todo lo que llevamos viendo: cuanto más autónomo es un agente, más importa controlarlo y protegerlo. Conecta directo con la Charla 15 (seguridad) y con el porqué del *checkpoint humano* que montamos en la Charla 19 — un agente que actúa sin control es justo lo que hay que evitar.

Fuente: [AI Weekly](https://aiweekly.co/)

---

## 6. De fondo, para desarrolladores: los agentes se cuelan en el editor de código

**Qué ha pasado.** Visual Studio Code sigue llenándose de funciones de agente: en su versión 1.136 permite continuar sesiones de agentes (de Copilot y de Claude), resolver comentarios de revisión y conflictos de fusión con un asistente ("Agent Merge"), y trabajar con agentes a través de varias carpetas del proyecto.

**Por qué te importa.** Para los perfiles técnicos de la sala: el agente ya no es una pestaña aparte, está dentro de las herramientas de trabajo de siempre. Es la misma idea de la Charla 19 —de responder a actuar— pero en el terreno del desarrollo: el agente hace parte del trabajo y tú revisas y apruebas.

Fuente: [Releasebot — Microsoft](https://releasebot.io/updates/microsoft)

---

## El hilo de la semana

Casi todo apunta a lo mismo: **los agentes están entrando en las herramientas que ya usas** — en Copilot, en Copilot Studio, en el editor de código — mientras el sector se concentra a su alrededor (Nvidia + Hugging Face) y las preguntas de gobierno, seguridad y derechos corren por detrás para alcanzarlos (la demanda a Anthropic, la seguridad frente a agentes). Es exactamente el terreno de la Charla 19: agentes que **actúan**, con un humano que mantiene la última palabra. La semana no cambia el mensaje de la serie; lo confirma.

---

*Digest de la serie IAs-talks. Selección accesible; las fuentes son mayoritariamente agregadores del sector, así que para datos concretos (fechas, cifras) conviene contrastar en la fuente primaria antes de citarlos en algo formal.*
