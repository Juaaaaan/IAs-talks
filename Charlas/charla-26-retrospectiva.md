---
type: Charla
title: "Charla 26 — Retrospectiva: qué hemos visto y para qué sirve cada cosa"
description: "Repaso de la serie para afianzar lo visto: 32 piezas ordenadas en diez preguntas de trabajo y cuatro tramos, con la descripción de cada pieza difuminada para que la sala respondiera por el chat antes de revelarla. Incluye consulta al vault con GitHub Copilot Desktop y un vistazo a la Biblioteca web."
tags: [charla, retrospectiva, repaso, arnes, ciclo, dinamica, biblioteca, vault]
related: [guion-charla-26, charla-22-preguntale-primero, charla-24-comprobar-despues-de-construir, arnes-completo, ai-harness-engineering, ia-first, wiki-llm, rag, okf]
charla: "Charla 26"
fecha: "2026-11-25"
estado: "✅ Impartida"
timestamp: "2026-11-27"
---

# Charla 26 — Retrospectiva: qué hemos visto y para qué sirve cada cosa

**Fecha:** 25 de noviembre de 2026 **Estado:** ✅ Impartida **Asistencia:** 111 personas

---

## Idea central

> _"No hace falta recordar veinticinco charlas. Hace falta recordar qué pregunta responde cada cosa."_

No se presentó ninguna herramienta nueva: la sesión sirvió para poner orden y afianzar lo visto desde el 17 de junio.

---

## Resultado

Asistieron 111 personas. Buena acogida: gustó la retrospectiva y ver cómo funcionaba la dinámica del texto difuminado. También gustó la idea de la Biblioteca; queda pendiente hablar con la persona de despliegue para ver cómo ponerla a disposición de la audiencia.

## Estructura

| Bloque | Contenido | Tiempo |
|---|---|---:|
| 1. Apertura | No añadimos otra herramienta: ponemos orden y participamos | 3 min |
| 2. El mapa | Cuatro tramos, diez preguntas | 3 min |
| 3. Las diez preguntas | 32 piezas, con 12 intervenciones y revelado ágil del resto | 20 min |
| 4. Preguntarle al vault | Dos consultas con GitHub Copilot Desktop y fuentes visibles | 5 min |
| 5. La Biblioteca | Dónde va a vivir todo esto | 2 min |
| 6. Cierre | La chuleta de preguntas y una acción para la semana | 4 min |

## Las diez preguntas

| Tramo | Pregunta | Piezas |
|---|---|---|
| A. Darle contexto | 1. ¿Cómo le pido las cosas? | Hablar su idioma, dar ejemplos (18) |
| | 2. ¿Cómo le doy contexto estable sobre mi trabajo? | Instrucciones persistentes (8), skills (7), Wiki LLM (11) |
| | 3. ¿Cómo encuentra lo que necesita en tanta información? | Fuente delante (18), ventana de contexto (18), RAG (12), metadatos y enlaces/OKF (11) |
| B. Fiarse con cabeza | 4. ¿Me puedo fiar de lo que dice? | Predicción del siguiente token y alucinaciones (18), pedir la fuente y verificar según lo que cuesta equivocarse (17) |
| | 5. ¿Qué puedo usar y con qué riesgos? | Shadow AI y gobernanza (14), inyección de instrucciones (15) |
| | 6. ¿Qué modelo y qué modo uso? | Elegir bien (17), modos de trabajo (17), rápido o razonador (17) |
| C. Que haga cosas | 7. ¿Cómo la conecto con mis herramientas? | MCP (7), permisos mínimos (15) |
| | 8. ¿Cómo creo un asistente para mi equipo? | Agente, Copilot Studio y métricas (13) |
| | 9. ¿Cómo le encargo un trabajo grande? | SDD con OpenSpec (16), equipo de agentes (19), ejecutor abierto (20) |
| D. Comprobar | 10. ¿Cómo defino y compruebo que está bien? | Ciclo de seis paradas (22), BDD y ODD (23), revisión con IA y RDD (24) |

## Dinámica

Cada pieza aparecía con su explicación **difuminada**; 12 de las 32 se preguntaban a la sala (una frase en el chat sobre para qué creían que servía) y el resto se revelaba directamente. Después de leer una o dos respuestas se mostraba el texto y se decía la frase ancla de la pregunta.

## Decisiones aplicadas

- **Solo piezas trazables a la serie:** se retiraron las piezas sin charla confirmada, para no introducir contenido nuevo en una sesión de repaso.
- **Sin demo en directo** (lección de la 23): la consulta al vault y la Biblioteca se ensayaron antes y llevaban capturas como plan B.
- **Privacidad:** el vault de la demo era una copia limpia, sin guiones, proyectos ni demos con datos internos.
- **Sin encuesta** y sin bloque de «repeticiones».

---

## Siguiente

La charla 27 (2 de diciembre) corre a cargo de un compañero. Pendiente de la Biblioteca: acordar con despliegue cómo y dónde alojarla. Del ciclo de la 22 siguen sin trabajar a fondo **Publicar** y **Mantener**.
