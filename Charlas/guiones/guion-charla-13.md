# Guión Charla 13 — De saber a medir: Copilot Studio y cómo saber si la IA está funcionando
### 22 de julio de 2026

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|--------|-----------|--------|
| Apertura | Puente desde la Charla 12 — la pregunta que queda abierta | 3 min |
| Bloque 1 | Qué es Copilot Studio y dónde encaja | 7 min |
| Demo — Acto 1 | Construir el agente en vivo en Copilot Studio | 15 min |
| Demo — Acto 2 | Usar el agente en Copilot 365 | 8 min |
| Bloque 2 | Cómo saber si la IA está funcionando — métricas | 8 min |
| Cierre | 3 ideas para llevarse + preview charlas siguientes | 4 min |

**Total: ~45 min**

---

## Herramientas de demo

| Demo | Herramienta |
|------|-------------|
| Construcción del agente | Copilot Studio (make.preview.microsoft.com) |
| Uso del agente | Microsoft Copilot 365 |
| Dashboard de analytics | Copilot Studio — pestaña Analytics |

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

> *"Pero hay preguntas que ese conocimiento genérico no puede responder. ¿Cuántos días de vacaciones tengo según nuestro convenio? ¿Cuál es el proceso para solicitar un cambio de proyecto? ¿Qué incluye nuestra póliza de salud? Esas respuestas no están en internet. Están en vuestros documentos."*

### Qué es

> *"Copilot Studio os permite construir un agente que sí sabe esas cosas. Porque vosotros le dais ese conocimiento. Le subís los documentos, le definís el comportamiento, y el agente responde basándose en lo que vosotros le habéis enseñado."*

> *"Tres cosas clave para que os queden claras:"*

> *"Primera: no necesita código. Cualquier persona de esta sala puede construir un agente en Copilot Studio. No hace falta ser developer."*

> *"Segunda: el conocimiento es vuestro. Los documentos que subís no salen de la empresa. Esto no es IA pública — es IA con vuestros datos, bajo vuestro control."*

> *"Tercera: vive donde ya trabajáis. Un agente de Copilot Studio se despliega en Teams, en Copilot 365, en los canales que ya usáis. No hay que instalar nada nuevo ni cambiar hábitos."*

**Frase que debe quedar:**
> *"La diferencia entre un LLM genérico y un agente de Copilot Studio es la misma que entre un becario recién llegado y alguien que lleva tres años en la empresa y conoce todos los procesos."*

### Dónde encaja en el mapa

> *"En el mapa que visteis la semana pasada, esto es el Nivel 4. Agentic. Automatización profunda. La IA no solo asiste — actúa de forma autónoma dentro de un proceso definido."*

> *"Y lo vais a ver construirse ahora mismo."*

---

## Demo — Acto 1: Construir el agente en Copilot Studio — 15 min

**Configuración previa necesaria:**
- Copilot Studio abierto en el navegador (make.preview.microsoft.com)
- Documento FAQ de onboarding preparado (ficticio) listo para subir
- Política de teletrabajo preparada (ficticia) lista para subir

---

### Paso 1 — Abrir Copilot Studio (1 min)

> *"Esto es Copilot Studio. La interfaz desde la que cualquier persona puede crear un agente."*

Mostrar la pantalla de inicio. Señalar las secciones principales sin detenerse.

> *"No vamos a explorar todo. Vamos directamente a crear."*

---

### Paso 2 — Crear el agente (2 min)

Hacer clic en "Nuevo agente" o equivalente.

> *"Le damos un nombre. Este agente se va a llamar 'Agente de bienvenida'. Su trabajo: responder las preguntas que tiene cualquier persona nueva en la empresa durante sus primeras semanas."*

> *"Pensad en cuántas veces alguien de RRHH responde las mismas cinco preguntas a cada persona que se incorpora. Este agente las responde por ellos."*

Completar nombre y descripción breve en la interfaz.

---

### Paso 3 — Subir el conocimiento (5 min)

> *"Aquí está la clave. El agente sabe lo que vosotros le enseñáis."*

Ir a la sección de Knowledge / Conocimiento. Subir los dos documentos en directo.

> *"Estoy subiendo ahora mismo dos documentos. Un FAQ de incorporación y una política de teletrabajo. Nada más. Eso es todo el conocimiento que tiene este agente."*

Esperar a que procese.

> *"Lo que está pasando ahora mismo: Copilot Studio está leyendo estos documentos, extrayendo el significado de cada párrafo y guardándolo de forma que el agente pueda consultarlo cuando alguien le pregunte. Exactamente lo que visteis en la Charla 12 cuando hablamos de RAG y embeddings. Aquí lo estáis viendo en acción."*

---

### Paso 4 — Primera prueba en el panel de test (7 min)

Abrir el panel de test en la misma pantalla.

> *"Ahora le pregunto."*

**Pregunta 1:**
```
¿Cuántos días de vacaciones tengo durante el primer año?
```

Mostrar la respuesta. Señalar que cita el documento.

> *"Fijaos en algo importante. No se lo ha inventado. Ha buscado en el documento que acabamos de subir y ha extraído la respuesta. Si el documento no lo dijera, el agente lo diría."*

**Pregunta 2:**
```
¿Cómo solicito el teletrabajo? ¿Hay un formulario?
```

Mostrar la respuesta.

> *"Dos preguntas. Dos respuestas basadas en documentos reales. En dos minutos, sin código."*

**Pregunta 3 — la que falla intencionadamente:**
```
¿Cuál es la política de bonus de fin de año?
```

> *"Esto no está en ninguno de los documentos que he subido. Veamos qué hace."*

Mostrar cómo el agente indica que no tiene esa información.

> *"Esto es exactamente lo que debe hacer un agente bien construido. No inventarse respuestas. Reconocer los límites de su conocimiento."*

**Frase de anclaje del momento:**
> *"Un agente que reconoce lo que no sabe es más valioso que uno que siempre responde algo."*

---

## Demo — Acto 2: Usar el agente en Copilot 365 — 8 min

Cambio de ventana. Abrir Copilot 365.

> *"Ahora salimos de Copilot Studio y vamos a donde está la gente: Copilot 365."*

> *"El agente que acabamos de construir hace diez minutos ya está disponible aquí."*

Localizar el agente en la interfaz de Copilot 365.

> *"Esto es lo que vería cualquier persona de la empresa. Sin entrar en Copilot Studio. Sin saber cómo está construido. Solo la conversación."*

**Pregunta de la sala** (pedir a alguien que proponga una pregunta relacionada con incorporación o teletrabajo):

> *"¿Alguien quiere preguntarle algo?"*

Escribir la pregunta que proponga la sala. Mostrar la respuesta.

> *"Lo que veis aquí no lo he preparado esta mañana. Lo hemos construido juntos hace diez minutos."*

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

> *"Y hay algo que me parece especialmente útil: podéis definir vuestras propias métricas en lenguaje natural."*

Mostrar la sección de Custom Metrics.

> *"En lugar de solo medir si respondió o no, podéis medir cosas como: '¿el usuario expresó satisfacción al final de la conversación?' o '¿la respuesta llevó al usuario a completar la acción que buscaba?'. En lenguaje normal. Sin código."*

### El apunte para developers (3 min)

> *"Para los que trabajáis en equipos de desarrollo, hay un nivel más de medición que quiero mencionar brevemente."*

> *"Existen marcos como DORA — cuatro métricas clásicas para medir la salud de un equipo de software: frecuencia de despliegue, tiempo hasta producción, tasa de fallos y tiempo de recuperación."*

> *"El informe DORA 2025 publicó algo importante: la adopción de IA mejora la velocidad de los equipos, pero frecuentemente aumenta la inestabilidad cuando no hay controles de calidad suficientes. Más código generado significa más bugs potenciales si no se revisa bien."*

> *"Y el dato más llamativo: los asistentes de código IA disparan el output individual — hasta un 98% más de pull requests — pero las métricas de entrega organizacional se mantienen planas. Lo llaman el 'AI Productivity Paradox'."*

> *"La conclusión práctica: más velocidad sin calidad no es progreso, es deuda. Medir el impacto de la IA en el equipo requiere ir más allá de contar cuánto código se genera."*

> *"Esto da para una charla entera. Y la tendremos. Hoy solo quería que supierais que ese marco existe y que hay preguntas abiertas muy interesantes sobre cómo medirlo bien."*

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

> *"Segunda: construir es la parte fácil. Medir es la que marca la diferencia. Un agente que nadie usa no sirve de nada. Un agente cuyo uso medís y mejorais se convierte en una pieza real de cómo trabaja el equipo."*

> *"Tercera: esto es el Nivel 4. Lo que acabáis de ver — un agente con conocimiento propio, desplegado en vuestras herramientas, con métricas para mejorarlo — es exactamente donde el mapa decía que ibais. Y lo habéis visto construirse en cuarenta minutos."*

**Frase final:**
> *"La semana pasada os di el mapa. Hoy habéis puesto el primer pin."*

---

## Checklist antes del miércoles

### Lunes — explorar y construir
- [ ] Acceder a Copilot Studio (make.preview.microsoft.com)
- [ ] Explorar la interfaz — familiarizarse sin objetivo durante 30-45 min
- [ ] Tener listos los documentos ficticios de demo (FAQ onboarding + política teletrabajo)
- [ ] Crear el agente "Agente de bienvenida" con esos documentos
- [ ] Probar el panel de test — confirmar que responde bien y que falla bien (pregunta fuera de knowledge)
- [ ] Desplegarlo en Copilot 365 — confirmar que aparece disponible
- [ ] Explorar la pestaña Analytics — ver qué métricas están disponibles
- [ ] Explorar Custom Metrics — probar a definir una en lenguaje natural

### Martes — ensayo
- [ ] Ajustar el guión según lo que hayas descubierto explorando
- [ ] Ensayo completo cronometrado — objetivo: 43-45 min
- [ ] Preparar las dos ventanas: Copilot Studio + Copilot 365
- [ ] Tener los documentos ficticios listos para subir en directo (no presubidos)

### El día de la charla
- [ ] Copilot Studio abierto — con el agente sin crear aún (se crea en directo)
- [ ] Documentos ficticios listos para subir en el momento
- [ ] Copilot 365 abierto en otra ventana con el agente desplegado
- [ ] Analytics de Copilot Studio listo para mostrar al final

---

## Recursos de la charla

- [[copilot-studio]] — Concepto Copilot Studio
- [[metricas-ia]] — Concepto métricas de IA (para charlas futuras)
- Documentación oficial analytics: https://learn.microsoft.com/en-us/microsoft-copilot-studio/analytics-overview
- Guía de KPIs y mejora de rendimiento: https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/analytics
- Documentos de demo: [[demo-faq-onboarding]] · [[demo-politica-teletrabajo]]

---

## Próxima charla

Charla 14 — Métricas de IA en profundidad: DORA, developer velocity y cómo medir el impacto real en equipos de desarrollo.
