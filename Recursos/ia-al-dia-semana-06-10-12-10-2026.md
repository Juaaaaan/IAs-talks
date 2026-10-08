---
type: Recurso
title: "IA al día — Semana del 6 al 12 de octubre de 2026"
description: "Digest semanal de novedades de IA para la serie IAs-talks. Selección accesible (público mayoritariamente no técnico): OpenAI retira GPT-6.1 Astra por seguridad, Anthropic añade 'mods' programables a Claude Code, Sierra y Meta publican un protocolo abierto de agentes personales, Mistral Large 4 en abierto, y el nuevo precio de GPT-6.1 Sol."
tags: [recurso, ia-al-dia, novedades, digest-semanal, semana-06-10-2026]
timestamp: "2026-10-08"
---

# IA al día — Semana del 6 al 12 de octubre de 2026

Resumen de lo que ha movido la aguja esta semana, contado en cristiano. Por cada noticia: **qué ha pasado** y **por qué te importa**. (Datos a fecha del 8 de octubre.)

---

## 1. OpenAI retira el lanzamiento de GPT-6.1 Astra por fallos de seguridad

**Qué ha pasado.** OpenAI tenía previsto lanzar GPT-6.1 Astra este mes como un modelo capaz de completar tareas complejas de principio a fin sin supervisión humana. Las pruebas internas detectaron regresiones serias de seguridad y alineamiento, y la compañía ha decidido no sacarlo.

**Por qué te importa.** Es el mismo reflejo del que hablamos en la Charla 22, pero a la escala de quien construye los modelos: antes de soltarlo, alguien se paró a comprobar que no había nada raro — y lo frenó. El checkpoint humano antes de publicar no es solo cosa de vuestras tareas; hasta los laboratorios más grandes lo aplican sobre sí mismos.

Fuente: [AI Magazine, 3 oct](https://aimagazine.com/news/this-weeks-top-five-stories-in-ai-week-1-october)

---

## 2. Claude Code incorpora "mods": el agente de código se vuelve programable

**Qué ha pasado.** Anthropic ha añadido a Claude Code pequeños módulos en TypeScript que pueden reescribir prompts, bloquear o reintentar llamadas a herramientas, decidir permisos, tachar secretos y sustituir partes de la interfaz, en cualquier punto del bucle del agente.

**Por qué te importa.** Es exactamente el patrón de "hooks como puertas de aprobación" que vimos con los permisos de OpenCode en la Charla 20: convertir al agente en algo que se puede gobernar en el momento en que actúa, no solo revisar después. La propia noticia avisa de la otra cara: revisar esos módulos de terceros pasa a ser, de facto, un requisito de seguridad.

Fuente: [AI Weekly, 2 oct](https://aiweekly.co/ai-news-today/edition/2026-10-02)

---

## 3. Sierra y Meta publican un protocolo abierto para que tu agente se identifique ante una empresa

**Qué ha pasado.** El 6 de octubre, Sierra y Meta publicaron el Personal Agent Protocol v0.1, un estándar abierto basado en OAuth, respaldado por Walmart, que permite que el agente de IA de una persona se autentique ante un negocio y declare qué alcance tiene nada más llegar.

**Por qué te importa.** Es el "¿hace falta construir algo, o ya existe?" de la Charla 22 llevado al terreno de la identidad de los agentes: en vez de que cada empresa invente su propia forma de reconocer a un agente ajeno, empieza a haber un estándar común. Si algún día un agente vuestro —o de un cliente— interactúa con sistemas externos, esto es lo que vendrá detrás.

Fuente: [AI Weekly, 7 oct](https://aiweekly.co/ai-news-today/edition/2026-10-07)

---

## 4. Mistral presenta Large 4 en abierto, con 1 billón de parámetros

**Qué ha pasado.** Mistral AI ha anunciado una vista previa pública de Mistral Large 4, un modelo nativamente multimodal de 1 billón de parámetros totales (49.000 millones activos), con publicación en abierto prevista.

**Por qué te importa.** Encaja con el hilo de la Charla 20 (ejecutor abierto, modelo abierto): cada mes hay una alternativa europea más seria a los modelos cerrados de los grandes proveedores americanos, con la ventaja añadida de poder auditarla o alojarla donde haga falta.

Fuente: [Artificial Intelligence News, 7 oct](https://www.artificialintelligence-news.com/)

---

## 5. GPT-6.1 Sol sale a un quinto del precio de su predecesor

**Qué ha pasado.** OpenAI ha lanzado GPT-6.1 Sol a 2$ por millón de tokens de entrada y 10$ de salida — una quinta parte de lo que costaba GPT-6 Astra.

**Por qué te importa.** La brújula de la Charla 17 sigue vigente: no hay "el mejor modelo", hay el que mejor encaja en precio y tarea. Si tenéis algo montado sobre un modelo por costumbre, esta semana es un buen momento para comprobar si sigue siendo la opción más barata para lo que hace.

Fuente: [AI Weekly, 1 oct](https://aiweekly.co/ai-news-today/edition/2026-10-01)

---

## 6. De fondo: Europa sigue apretando el nudo regulatorio

**Qué ha pasado.** El Consejo de Europa y Microsoft firmaron el 7 de octubre un acuerdo de cooperación en IA, en la misma semana en que Microsoft publicaba recomendaciones de control de datos para la adopción de IA en el sector público.

**Por qué te importa.** Enlaza con la Charla 14 (gobernanza): el marco regulatorio europeo sigue moviéndose, y las recomendaciones de hoy sobre datos públicos suelen convertirse en requisitos de mañana para el resto de sectores regulados — seguros incluido.

Fuente: [Artificial Intelligence News, 7 oct](https://www.artificialintelligence-news.com/)

---

## El hilo de la semana

Astra frenado antes de salir, Claude Code vuelto programable para poder controlarlo mientras actúa, un protocolo para que los agentes declaren su alcance al llegar, Europa firmando acuerdos de cooperación: esta semana, toda la IA agéntica que avanza viene acompañada de más control, no menos. Es el mismo mensaje de la Charla 22 a escala de industria: ganar velocidad con la IA solo compensa si alguien —tú, o quien la construye— sigue preguntando primero y comprobando después.

---

*Digest de la serie IAs-talks. Selección accesible; las fuentes son mayoritariamente agregadores del sector, así que para datos concretos (fechas, cifras) conviene contrastar en la fuente primaria antes de citarlos en algo formal.*
