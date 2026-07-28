---
type: Guión
title: "Guión Charla 14 — Gobernanza de IA: las reglas que nadie os ha explicado"
description: "Script completo con tiempos, narrativa y política de uso de IA para la Charla 14, centrada en la Dimensión 7 (Gobierno, Riesgo y Compliance) del framework de madurez."
tags: [guion, charla-14, gobernanza, riesgo, compliance, shadow-ai, eu-ai-act]
related: [ai-governance, metricas-ia, copilot-studio, arnes-completo]
charla: "Charla 14"
estado: "🔲 En preparación"
timestamp: "2026-07-26"
---

# Guión Charla 14 — Gobernanza de IA: las reglas que nadie os ha explicado

> ⚠️ **Pendiente antes de cerrar el guion:** revisar los ficheros internos de la empresa sobre gobernanza de IA (políticas ya existentes, herramientas aprobadas, canales de escalado) y sustituir los bloques marcados con 🔲 TODO por el contenido real de Sopra Steria. Todo lo marcado así en este borrador es genérico o de ejemplo — no son datos reales de la empresa.

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|--------|-----------|--------|
| Apertura | Gancho: Shadow AI + puente desde Charla 13 | 3 min |
| Bloque 1 | Casos reales — cuando la falta de gobernanza sale cara | 7 min |
| Bloque 2 | Niveles de riesgo — EU AI Act + política interna | 10 min |
| Bloque 3 | Qué significa esto según tu rol | 6 min |
| Bloque 4 | Núcleo — política interna de uso de IA punto por punto | 15 min |
| Bloque 5 | Autoevaluación — en qué nivel estáis vosotros | 5 min |
| Cierre | 3 ideas + referencias | 3 min |
| Preguntas | Turno abierto | 5-10 min |

**Total estimado:** ~49 min + preguntas

---

## Apertura — Gancho: Shadow AI — 3 min

> *"En la Charla 13 hablamos de cómo medir si un agente funciona. De cómo medir si el código que genera la IA es fiable. Hoy vamos a hablar de algo distinto: no de si la IA funciona bien, sino de si la estamos usando de forma segura."*

**La pregunta incómoda:**

> *"Levantad la mano — mentalmente, no hace falta que sea literal — quien alguna vez ha pegado un fragmento de código, un email, un dato de un cliente, en una herramienta de IA sin pararse a pensar si estaba permitido."*
>
> *"Eso tiene nombre: se llama Shadow AI. Uso de IA sin control ni conocimiento por parte de la organización. Y la mala noticia es que casi todo el mundo lo ha hecho alguna vez, sin mala intención — simplemente porque nadie le explicó las reglas."*

**Frase que debe quedar:**
> *"El Shadow AI no es un problema de mala fe. Es un problema de que nadie ha explicado las reglas con claridad. Hoy las explicamos."*

---

## Bloque 1 — Casos reales: cuando la falta de gobernanza sale cara — 7 min

> *"Antes de hablar de reglamentos, quiero contaros tres casos reales, públicos, de empresas que se lo tomaron a la ligera. No son de banca ni de seguros, pero podrían serlo perfectamente."*

**Caso 1 — Samsung y el código fuente (2023)**
> *"Varios ingenieros de Samsung pegaron código fuente propietario en ChatGPT para pedirle ayuda a depurar errores y optimizar procesos. El problema: ese código pasó a formar parte de los datos que la herramienta podía usar fuera de la empresa. Samsung acabó prohibiendo el uso de IA generativa pública en toda la compañía. Nadie actuó con mala intención — simplemente nadie les había dicho que no se podía."*

**Caso 2 — Air Canada y el chatbot (2024)**
> *"El chatbot de atención al cliente de Air Canada le dio a un pasajero información incorrecta sobre la política de reembolsos por fallecimiento de un familiar. La aerolínea intentó defenderse diciendo que el chatbot era 'una entidad legal separada' responsable de sus propias palabras. Un tribunal canadiense no lo aceptó: la empresa es responsable de lo que dice su IA, igual que de lo que dice cualquier empleado."*

**Caso 3 — La autoridad italiana de protección de datos y ChatGPT (2023)**
> *"Italia llegó a bloquear temporalmente el acceso a ChatGPT en todo el país por dudas sobre cómo se trataban los datos personales de los usuarios. Fue el primer país occidental en hacerlo. La herramienta volvió semanas después, con cambios. Pero mostró que los reguladores no se van a quedar mirando."*

**El patrón común:**
> *"En los tres casos no hubo mala fe. Hubo falta de reglas claras, y cuando las reglas no existen, las pone otro por vosotros — un tribunal, un regulador, o la propia dirección con una prohibición total después del susto. Gobernar la IA antes de que pase algo es mucho más barato que gobernarla después."*

**Frase que debe quedar:**
> *"Estas tres empresas no tenían gente malintencionada. Tenían gente sin reglas claras. Es la misma situación en la que puede estar cualquiera de esta sala hoy."*

---

## Bloque 2 — Niveles de riesgo: EU AI Act traducido — 10 min

> *"Existe una regulación europea, el EU AI Act, que clasifica cualquier sistema de IA según su nivel de riesgo. No os voy a leer el reglamento — os lo voy a traducir a ejemplos de vuestro día a día."*

| Nivel de riesgo | Ejemplo genérico (EU AI Act) | Ejemplo aplicado a nuestro contexto |
|---|---|---|
| **Inaceptable** | Scoring social, vigilancia masiva | Prohibido por definición — no debería aparecer en nuestro trabajo |
| **Alto riesgo** | Selección de personal, diagnóstico médico, scoring crediticio | Ver detalle abajo en la política interna |
| **Riesgo limitado** | Chatbots (deben avisar que son IA) | Agentes de Copilot Studio como el de la Charla 13 |
| **Riesgo mínimo** | Autocompletado, filtros de spam | Uso de Copilot para autocompletar código |

> *"La regla general es simple: cuanto más impacto tiene la decisión sobre una persona real — un cliente, un candidato, un empleado — más control necesita. Y en banca y seguros, muchas de nuestras decisiones tienen justo ese impacto."*

**Frase que debe quedar:**
> *"No toda IA es igual de arriesgada. La pregunta no es '¿puedo usar IA?', es '¿qué está en juego si me equivoco?'"*

### Política interna: nuestros 5 niveles de riesgo

> *"El EU AI Act es el marco legal. Internamente, en la empresa, aterrizamos ese marco en 5 niveles operativos con criterios claros, aprobación mínima y evidencia esperada."*

| Nivel | Criterios | Ejemplos | Aprobación mínima | Evidencia |
|-------|-----------|----------|-------------------|-----------|
| **Prohibido** | 🔲 TODO | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| **Crítico** | 🔲 TODO | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| **Alto** | 🔲 TODO | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| **Medio** | 🔲 TODO | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| **Bajo** | 🔲 TODO | 🔲 TODO | 🔲 TODO | 🔲 TODO |

> *"Fijaos en el detalle importante: cuanto más alto el nivel, no solo cambia lo que podéis o no hacer. Cambia quién tiene que aprobarlo y qué prueba hay que dejar de que la decisión se tomó bien. Esto es lo que separa una política real de un cartel bienintencionado."*

📎 *Para quien quiera profundizar en el marco regulatorio completo (EU AI Act, ISO 42001, NIST AI RMF), la referencia está en la nota [[ai-governance]] del vault.*

---

## Bloque 3 — Qué significa esto según tu rol — 6 min

> *"La gobernanza no pesa igual para todos. Vamos rápido por cuatro perfiles que hay hoy en esta sala."*

| Rol | Qué le toca vigilar especialmente |
|---|---|
| **Developer** | Código y datos técnicos en herramientas de IA — conecta con la Dim. 2 y 5 del framework de madurez (desarrollo, configuración) |
| **Comercial / cara al cliente** | Nunca compartir datos de cliente en herramientas no aprobadas; cualquier propuesta o comunicación generada con IA, revisión antes de enviar |
| **RRHH** | Especial cuidado si se usa IA en procesos de selección o evaluación de personas — es zona de "alto riesgo" por definición del EU AI Act |
| **Management / PM** | Responsabilidad de que el equipo conozca la política, no solo de aplicarla personalmente — la Dim. 8 (Cultura y Adopción) empieza aquí |

**Frase que debe quedar:**
> *"La gobernanza no es un documento que lee una persona de compliance. Es una responsabilidad repartida, distinta para cada rol, pero de todos."*

---

## Bloque 4 — Núcleo: política interna de uso de IA, punto por punto — 15 min

> *"Hasta aquí hemos hablado del marco. Ahora entramos en el documento real: la política interna que aplica desde mañana. Seis piezas — vamos una a una."*

### 4.1 Escenarios permitidos por fase de trabajo

> *"La primera pregunta es la más práctica: ¿en qué momento del trabajo puedo usar IA y en cuál no? La política lo organiza por fase."*

| Fase / Actividad | Permitido | Condicionado | Prohibido |
|---|---|---|---|
| Ideación, discovery y business analysis | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| Diseño y arquitectura | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| Desarrollo y generación de código | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| Pruebas y QA | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| 🔲 TODO — añadir el resto de fases relevantes | | | |

> *"'Condicionado' no es una casilla decorativa. Significa: sí, pero con estos requisitos. Cuando algo cae en condicionado, la responsabilidad de comprobar que se cumplen las condiciones es tuya, no del que escribió la política."*

---

### 4.2 Datos permitidos y restringidos

> *"Segunda pieza: qué datos pueden entrar en qué tipo de IA. Aquí es donde se juega la parte más sensible — la que dio problemas a Samsung."*

| Clase de dato | Público / no homologado | Cliente aprobado / dedicado | Condiciones mínimas |
|---|---|---|---|
| 🔲 TODO — Ej.: datos técnicos internos | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| 🔲 TODO — Ej.: datos de cliente identificables | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| 🔲 TODO — Ej.: información pública / no sensible | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| 🔲 TODO — Ej.: credenciales, claves, tokens | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| 🔲 TODO — completar con el resto de clases de dato de la política | | | |

**Caso aplicado:**
> *"Un compañero pide a una IA que le ayude a mejorar el tono de un email para un cliente. El texto que ha escrito él, sí. El nombre y los datos bancarios del cliente para 'que quede más personalizado', no."*

**Segundo caso aplicado:**
> *"Una persona de RRHH quiere que una IA le ayude a redactar el feedback de una evaluación. El texto genérico sobre feedback constructivo, sin problema. Pegar el historial de rendimiento real del empleado para que 'lo resuma', ya es otra cosa — son datos personales de una persona identificable."*

---

### 4.3 Revisión humana obligatoria

> *"Tercera pieza: ¿quién revisa qué antes de que el output tenga consecuencias reales? Un agente puede equivocarse — la responsabilidad final sigue siendo humana."*

| Output / acción | Revisión mínima requerida | Aprobador / owner | Evidencia esperada |
|---|---|---|---|
| 🔲 TODO — Ej.: comunicación a cliente | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| 🔲 TODO — Ej.: código a producción | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| 🔲 TODO — Ej.: documento contractual o legal | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| 🔲 TODO — Ej.: borrador interno de uso propio | 🔲 TODO | 🔲 TODO | 🔲 TODO |
| 🔲 TODO — completar según política real | | | |

> *"La columna de 'evidencia' es la que suele faltar en políticas mal hechas. Sin evidencia — un log, un firmante, una traza — la revisión no existe a efectos de auditoría, aunque haya ocurrido."*

---

### 4.4 Herramientas: corporativas y restricciones con cliente

> *"Cuarta pieza: qué se puede usar. Esta tabla la mantendremos actualizada al margen del guion, porque cambia con más frecuencia que el resto de la política."*

| Herramienta | Estado | Restricciones con cliente |
|---|---|---|
| 🔲 TODO — Juan pondrá el listado real de herramientas corporativas aprobadas | | |

**Caso aplicado:**
> *"Instalarse una extensión de IA de una tienda de navegador porque parece útil, sin pasar por el canal oficial — eso es Shadow AI, aunque la intención sea buena."*

**Segundo caso aplicado:**
> *"Un equipo descubre una herramienta gratuita para transcribir reuniones y la usa en llamadas con clientes sin consultar. La grabación y la transcripción pueden estar pasando por servidores fuera de cualquier control de la empresa — exactamente el tipo de caso que llevó a Samsung a prohibir la IA generativa pública."*

---

### 4.5 Proceso de incidentes relacionados con IA

> *"Quinta pieza — la que más tranquiliza a la sala cuando se explica: qué hacer si algo ya ha salido mal. Porque va a pasar. Y lo peor no es el incidente en sí; es esconderlo."*

**Pasos del proceso:**

1. 🔲 TODO — Paso 1 (detección: cómo se identifica que ha habido un incidente)
2. 🔲 TODO — Paso 2 (notificación: a quién y en qué plazo)
3. 🔲 TODO — Paso 3 (contención: qué hacer inmediatamente)
4. 🔲 TODO — Paso 4 (análisis y registro)
5. 🔲 TODO — Paso 5 (comunicación a cliente / regulador si aplica)
6. 🔲 TODO — Paso 6 (aprendizaje y actualización de la política)

**Frase que debe quedar:**
> *"Un incidente reportado a tiempo es un problema resuelto. Un incidente escondido es un problema que crece. Y no venimos aquí a señalar culpables — venimos a evitar el segundo caso."*

---

### 4.6 Checklist rápido de decisión

> *"Sexta y última pieza. Antes de usar una IA para algo real, cuatro preguntas — si respondes 'no' a alguna, para y consulta."*

| # | Pregunta |
|---|---|
| 1 | 🔲 TODO — Ej.: ¿Sé en qué nivel de riesgo cae lo que voy a hacer? |
| 2 | 🔲 TODO — Ej.: ¿La herramienta que voy a usar está aprobada para este tipo de dato? |
| 3 | 🔲 TODO — Ej.: ¿Sé quién tiene que revisar el output antes de que salga? |
| 4 | 🔲 TODO — Ej.: ¿Sé qué hacer si algo sale mal? |
| 🔲 TODO — añadir preguntas adicionales de la política real | |

**Frase que debe quedar:**
> *"Una política de gobernanza no existe para frenaros. Existe para que sepáis, en el momento de dudar, qué hacer sin tener que adivinarlo."*

---

## Bloque 5 — Autoevaluación: en qué nivel estáis vosotros — 5 min

> *"Todo esto que hemos visto no es abstracto. Ya tenéis, dentro de la empresa, una forma de medir en qué nivel de madurez estáis exactamente en gobernanza — el mismo framework de 8 dimensiones que usa el embajador de IA para el resto del equipo."*

**Recordatorio rápido de la escala (0-4):**

| Score | Nivel |
|-------|-------|
| 0 | Inexistente / Shadow AI |
| 1 | Inicial — uso individual, sin guías |
| 2 | Repetible — acuerdos de equipo, consciencia de riesgos |
| 3 | Gestionado — integración formal, métricas |
| 4 | Optimizado — mejora continua, gobernanza integrada en el día a día |

**Cómo se interpreta, en la práctica:**

> *"Si en la Dimensión 7 — Gobierno, Riesgo y Compliance — vuestro score es 1 o menos, es una señal de alerta inmediata: puede que estéis usando IA sin conocer las restricciones reales del cliente o del proyecto. Eso no es un suspenso personal, es información para saber que hace falta formación urgente, y ahora ya sabéis por dónde empezar — con lo de hoy."*

> *"Si además vuestro score en la Dimensión 8 — Cultura y Adopción — es 3 o más, sois candidatos naturales a ser champions: la persona que ayuda al resto del equipo a subir de nivel, no solo la que cumple la norma."*

**Frase que debe quedar:**
> *"No hace falta esperar a una auditoría externa para saber si estáis en riesgo. La pregunta ya existe dentro de la empresa. Solo hay que hacérsela."*

---

## Cierre — 3 min

> *"Primera idea: el Shadow AI no nace de mala fe, nace de falta de información. La solución no es más control, es más claridad."*
>
> *"Segunda idea: no toda IA tiene el mismo riesgo. Cuanto más impacto tiene la decisión sobre una persona real, más cuidado hace falta."*
>
> *"Tercera idea: esto no es solo cosa de developers. Todos los que estáis en esta sala tomáis decisiones cada semana sobre qué compartir con una IA — la política de hoy es para todos."*

**Referencias para profundizar:**
- [[ai-governance]] — marco regulatorio completo (EU AI Act, ISO 42001, NIST)
- 🔲 TODO: enlazar política interna oficial de Sopra Steria
- El checklist rápido del Bloque 4.6 es lo que os lleváis a la mesa mañana

---

## Checklist antes del miércoles

### Mañana
- [ ] Revisar ficheros internos de la empresa sobre gobernanza de IA
- [ ] Sustituir los bloques 🔲 TODO con información real (herramientas aprobadas, canal de escalado, matices banca/seguros)
- [ ] Confirmar si existe ya una política de uso de IA oficial, o si esta charla es la primera vez que se formaliza

### Días siguientes
- [ ] Leer el guión en voz alta una vez cerrado el contenido real
- [ ] Cronometrar los bloques 2 y 4 (son los más largos y densos)
- [ ] Ensayo completo de principio a fin

### El día de la charla
- [ ] Documento de política proyectable listo (sin depender de ninguna herramienta en vivo)
- [ ] Casos aplicados revisados para que suenen naturales, no leídos
