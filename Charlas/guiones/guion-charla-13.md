# Guión Charla 13 — De saber a medir: Copilot Studio y cómo saber si la IA está funcionando
### 22 de julio de 2026

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|--------|-----------|--------|
| Apertura | Puente desde la Charla 12 — la pregunta que queda abierta | 3 min |
| Bloque 1 | Qué es Copilot Studio y dónde encaja | 7 min |
| Demo — Acto 1 | Construir el agente en vivo en Copilot Studio | 15 min |
| Demo — Acto 2 | Usar el agente en Teams | 8 min |
| Bloque 2 | Cómo saber si la IA está funcionando — métricas | 8 min |
| Cierre | 3 ideas para llevarse + preview charlas siguientes | 4 min |

**Total: ~45 min**

---

## Herramientas de demo

| Demo | Herramienta |
|------|-------------|
| Construcción del agente | Copilot Studio (make.preview.microsoft.com) |
| Uso del agente | Microsoft Teams |
| Dashboard de analytics | Copilot Studio — pestaña Analytics |

---

## Notas técnicas aprendidas en la preparación

- El entorno LITE de Copilot Studio **no permite subir ficheros directamente**. El conocimiento se añade mediante **URLs de SharePoint** autenticadas.
- El panel de prueba interno de Copilot Studio **no puede autenticarse** contra SharePoint — las respuestas del panel de test no son fiables. El canal correcto para probar es **Teams**.
- El agente funciona correctamente en Teams porque los usuarios están autenticados con sus cuentas corporativas.
- El handbook corporativo 2026 está cargado como fuente de conocimiento vía SharePoint.
- **El agente ya está publicado y disponible en Teams** — no es necesario crearlo en directo el día de la charla. Ver sección de checklist.

---

## Apertura — 3 min

> *"La última charla os di el mapa. Cuatro niveles de madurez en IA. Y os dije algo que espero que os quedara: que ya estabais en el Nivel 3 sin saberlo."*

> *"Pero esa charla dejó una pregunta sin responder. Una que es probable que alguien se haya hecho esta semana."*

**Pausa.**

> *"¿Cómo lo sé? ¿Cómo sé que la IA me está ayudando de verdad y no solo parece que me ayuda?"*

> *"Esa pregunta tiene dos partes. La primera: cómo construir algo concreto que la IA haga por ti. La segunda: cómo medirlo para saber si está funcionando."*

> *"Hoy hacemos las dos cosas. Y lo hacemos con una herramienta que ya tenéis disponible: Copilot Studio."*

**Frase que debe quedar:**
> *"No basta con usar IA. Hay que saber si está funcionando."*

---

## Bloque 1 — Qué es Copilot Studio — 7 min

> *"Antes de entrar en la demo, necesito que tengáis claro qué es Copilot Studio y qué no es."*

### Qué no es

> *"No es un chatbot genérico. Cuando le preguntáis algo a ChatGPT o a Copilot 365 sin más, la IA responde con conocimiento general del mundo. Eso está bien para muchas cosas."*

> *"Pero hay preguntas que ese conocimiento genérico no puede responder. ¿Cuántos profesionales somos en la empresa? ¿Cuál es el proceso para solicitar un cambio de proyecto? ¿Qué dice nuestro handbook sobre las incorporaciones? Esas respuestas no están en internet. Están en vuestros documentos."*

### Qué es

> *"Copilot Studio os permite construir un agente que sí sabe esas cosas. Porque vosotros le dais ese conocimiento. Le conectáis los documentos, le definís el comportamiento, y el agente responde basándose en lo que vosotros le habéis enseñado."*

> *"Tres cosas clave para que os queden claras:"*

> *"Primera: no necesita código. Cualquier persona de esta sala puede construir un agente en Copilot Studio. No hace falta ser developer."*

> *"Segunda: el conocimiento es vuestro. Los documentos que conectáis no salen de la empresa. Esto no es IA pública — es IA con vuestros datos, bajo vuestro control, con las mismas credenciales corporativas que usáis cada día."*

> *"Tercera: vive donde ya trabajáis. Este agente vive en Teams. No hay que instalar nada nuevo ni cambiar hábitos."*

**Frase que debe quedar:**
> *"La diferencia entre un LLM genérico y un agente de Copilot Studio es la misma que entre un becario recién llegado y alguien que lleva tres años en la empresa y conoce todos los procesos."*

### Dónde encaja en el mapa

> *"En el mapa que visteis la semana pasada, esto es el Nivel 4. Agentic. La IA no solo asiste — actúa de forma autónoma dentro de un proceso definido."*

> *"Y lo vais a ver ahora mismo."*

---

## Demo — Acto 1: Construir el agente en Copilot Studio — 15 min

> ⚠️ **El agente ya está creado y publicado en Teams.** El Acto 1 muestra el proceso de construcción para que la audiencia entienda cómo funciona por dentro. No es necesario crear un agente nuevo — se muestra la configuración del agente existente.

---

### Paso 1 — Abrir Copilot Studio (1 min)

> *"Esto es Copilot Studio. La interfaz desde la que cualquier persona puede crear un agente."*

Mostrar la pantalla de inicio. Abrir el agente ya creado.

> *"Este es el agente que hemos preparado para hoy. Se llama 'Agente de bienvenida'. Vamos a ver cómo está construido."*

---

### Paso 2 — Mostrar la configuración (2 min)

Navegar por las secciones del agente: nombre, descripción, instrucciones.

> *"Le hemos dado instrucciones muy concretas: responde solo sobre lo que sabe, en español, con tono cercano. Si no tiene la información, lo dice — no se inventa nada."*

> *"Pensad en cuántas veces alguien de RRHH responde las mismas preguntas a cada persona que se incorpora. Este agente las responde por ellos."*

---

### Paso 3 — Mostrar el conocimiento (5 min)

Ir a la sección de Knowledge / Conocimiento. Mostrar la URL de SharePoint conectada.

> *"Aquí está la clave. El conocimiento del agente viene de un documento real de la empresa: nuestro handbook 2026. No de internet. No de un modelo genérico. De nuestro propio documento, al que solo tienen acceso las personas autenticadas con cuentas corporativas."*

> *"Lo que ocurre por debajo: Copilot Studio lee ese documento, extrae el significado de cada párrafo y lo guarda de forma que el agente pueda consultarlo cuando alguien le pregunte. Exactamente lo que visteis en la Charla 12 cuando hablamos de RAG y embeddings. Aquí lo estáis viendo en acción."*

---

### Paso 4 — Las preguntas que responde y las que no (7 min)

Mostrar el panel de configuración de temas o abrir Teams directamente.

> *"Antes de ver el agente en acción, quiero contaros algo que descubrimos preparando esta demo. Algo que ilustra perfectamente cómo funciona un agente bien construido."*

> *"Le preguntamos cuántos profesionales somos en la empresa. Responde perfectamente — está en el handbook."*

> *"Pero le preguntamos por la política de teletrabajo. Y dice que no tiene esa información. ¿Por qué? Porque no está en el handbook. No se la inventa. Reconoce el límite de su conocimiento."*

> *"Y si le preguntamos por los bonus de fin de año, igual: no tiene esa información."*

**Frase de anclaje:**
> *"Un agente que reconoce lo que no sabe es más valioso que uno que siempre responde algo."*

> *"Y la pregunta natural es: ¿qué habría que hacer para que supiera sobre teletrabajo? Añadir ese documento al conocimiento. Así de simple. Eso es exactamente cómo se itera y mejora un agente."*

---

## Demo — Acto 2: Usar el agente en Teams — 8 min

Cambio de ventana. Abrir Teams.

> *"Salimos de Copilot Studio y vamos a donde está la gente: Teams."*

> *"El agente está disponible aquí. Esto es lo que vería cualquier compañero. Sin entrar en Copilot Studio. Sin saber cómo está construido. Solo la conversación."*

Localizar el agente en Teams y abrirlo.

**Pregunta 1 — responde bien:**
```
¿Cuántos profesionales trabajamos en la empresa?
```

Mostrar la respuesta.

> *"Responde con datos reales de nuestro handbook. No de internet."*

**Pregunta de la sala** (pedir a alguien que proponga una pregunta sobre la empresa):

> *"¿Alguien quiere preguntarle algo sobre la empresa?"*

Escribir la pregunta que proponga la sala. Mostrar la respuesta.

> *"Lo que veis aquí está funcionando con nuestros propios documentos, con nuestras propias credenciales, dentro de nuestro entorno corporativo."*

**Frase que debe quedar:**
> *"Cualquier persona de esta sala puede tener algo así funcionando esta semana."*

---

## Bloque 2 — Cómo saber si la IA está funcionando — 8 min

> *"Tenemos el agente. Funciona. Pero aquí viene la pregunta que da título a la charla."*

> *"¿Cómo sé si está funcionando bien? ¿Cómo sé si la gente lo usa? ¿Cómo sé si les ayuda de verdad o si hacen la pregunta, no entienden la respuesta y van igualmente a preguntárselo a una persona?"*

> *"Copilot Studio tiene un dashboard de analytics integrado. Vamos a verlo."*

### El dashboard de Copilot Studio (3 min)

Abrir la pestaña Analytics en Copilot Studio.

> *"Tres métricas que mirar siempre:"*

> *"**Engagement rate** — qué porcentaje de personas que abrieron el agente le hicieron al menos una pregunta. Si es bajo, el agente no está siendo descubierto o la gente no entiende para qué sirve."*

> *"**Resolution rate** — qué porcentaje de conversaciones terminaron con el problema resuelto, sin que la persona tuviera que ir a buscar ayuda a otro lado. Esta es la métrica más importante."*

> *"**Deflection rate** — cuántas solicitudes resolvió el agente sin intervención humana. Si RRHH respondía 50 preguntas al mes y el agente resuelve 35, el deflection rate es del 70%."*

> *"Y hay algo especialmente útil: podéis definir vuestras propias métricas en lenguaje natural."*

Mostrar la sección de Custom Metrics.

> *"En lugar de solo medir si respondió o no, podéis medir cosas como: '¿el usuario expresó satisfacción al final de la conversación?' o '¿la respuesta llevó al usuario a completar la acción que buscaba?'. En lenguaje normal. Sin código."*

### El apunte para developers (3 min)

> *"Para los que trabajáis en equipos de desarrollo, hay un nivel más de medición que quiero mencionar brevemente."*

> *"Existen marcos como DORA — cuatro métricas clásicas para medir la salud de un equipo de software: frecuencia de despliegue, tiempo hasta producción, tasa de fallos y tiempo de recuperación."*

> *"El informe DORA 2025 publicó algo importante: la adopción de IA mejora la velocidad de los equipos, pero frecuentemente aumenta la inestabilidad cuando no hay controles de calidad suficientes. Más código generado significa más bugs potenciales si no se revisa bien."*

> *"Y el dato más llamativo: los asistentes de código IA disparan el output individual — hasta un 98% más de pull requests — pero las métricas de entrega organizacional se mantienen planas. Lo llaman el 'AI Productivity Paradox'."*

> *"La conclusión práctica: más velocidad sin calidad no es progreso, es deuda. Medir el impacto de la IA en el equipo requiere ir más allá de contar cuánto código se genera."*

> *"Esto da para una charla entera. Y la tendremos. Hoy solo quería que supierais que ese marco existe."*

**Frase que debe quedar:**
> *"Medir adopción es fácil. Medir impacto real es el siguiente reto."*

### Las tres preguntas que toda métrica de IA debe responder (2 min)

> *"Para cualquier rol de esta sala — RRHH, comercial, developer, directivo — hay tres preguntas simples que cualquier métrica de IA debería poder responder:"*

> *"¿Lo usa la gente? → Adoption rate."*
> *"¿Les ayuda? → Resolution rate."*
> *"¿Vuelven? → Retención semana a semana."*

> *"Si las tres son positivas, la IA está funcionando. Si alguna falla, sabéis exactamente dónde mirar."*

---

## Cierre — 4 min

> *"Tres ideas para llevarse hoy."*

> *"Primera: Copilot Studio no es para developers. Es para cualquier persona que tenga conocimiento que vale la pena capturar y compartir. RRHH, operaciones, comercial, soporte. Si hay preguntas que se repiten, hay un agente que puede responderlas."*

> *"Segunda: construir es la parte fácil. Medir es la que marca la diferencia. Un agente que nadie usa no sirve de nada. Un agente cuyo uso medís y mejoráis se convierte en una pieza real de cómo trabaja el equipo."*

> *"Tercera: esto es el Nivel 4. Lo que acabáis de ver — un agente con conocimiento propio, desplegado en Teams, con métricas para mejorarlo — es exactamente donde el mapa decía que ibais."*

**Frase final:**
> *"La semana pasada os di el mapa. Hoy habéis puesto el primer pin."*

---

## Checklist antes del miércoles

### Martes — ensayo
- [ ] Ensayo completo cronometrado — objetivo: 43-45 min
- [ ] Confirmar que el agente sigue disponible en Teams
- [ ] Preparar las dos ventanas: Copilot Studio (configuración) + Teams (uso)
- [ ] Tener la pestaña Analytics de Copilot Studio lista para mostrar
- [ ] Pensar qué pregunta pedirás a la sala en el Acto 2

### El día de la charla
- [ ] Copilot Studio abierto con el agente existente (no crear uno nuevo)
- [ ] Teams abierto con el agente localizado y listo
- [ ] Analytics de Copilot Studio listo para mostrar al final
- [ ] Recordar: el panel de test interno no funciona con SharePoint — usar siempre Teams para probar

---

## Recursos de la charla

- [[copilot-studio]] — Concepto Copilot Studio
- [[metricas-ia]] — Concepto métricas de IA (para charlas futuras)
- Documentación oficial analytics: https://learn.microsoft.com/en-us/microsoft-copilot-studio/analytics-overview
- Guía de KPIs y mejora de rendimiento: https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/analytics

---

## Próxima charla

Charla 14 — Métricas de IA en profundidad: DORA, developer velocity y cómo medir el impacto real en equipos de desarrollo.
