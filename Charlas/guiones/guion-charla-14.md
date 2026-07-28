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

| Bloque    | Contenido                                              | Tiempo   |
| --------- | ------------------------------------------------------ | -------- |
| Apertura  | Gancho: Shadow AI + puente desde Charla 13             | 3 min    |
| Bloque 1  | Casos reales — cuando la falta de gobernanza sale cara | 7 min    |
| Bloque 2  | Niveles de riesgo — EU AI Act + política interna       | 10 min   |
| Bloque 3  | Qué significa esto según tu rol                        | 6 min    |
| Bloque 4  | Núcleo — política interna de uso de IA punto por punto | 15 min   |
| Bloque 5  | Autoevaluación — en qué nivel estáis vosotros          | 5 min    |
| Cierre    | 3 ideas + referencias                                  | 3 min    |
| Preguntas | Turno abierto                                          | 5-10 min |

**Total estimado:** ~49 min + preguntas

---

## Apertura — Gancho: Shadow AI — 3 min

> _"En la Charla 13 hablamos de cómo medir si un agente funciona. De cómo medir si el código que genera la IA es fiable. Hoy vamos a hablar de algo distinto: no de si la IA funciona bien, sino de si la estamos usando de forma segur a."_

**La pregunta incómoda:**

> _"Levantad la mano — mentalmente, no hace falta que sea literal — quien alguna vez ha pegado un fragmento de código, un email, un dato de un cliente, en una herramienta de IA sin pararse a pensar si estaba permitido."_
>
> _"Eso tiene nombre: se llama Shadow AI. Uso de IA sin control ni conocimiento por parte de la organización. Y la mala noticia es que casi todo el mundo lo ha hecho alguna vez, sin mala intención — simplemente porque nadie le explicó las reglas."_

**Frase que debe quedar:**

> _"Datos internos, de clientes y Shadow AI. Posibles riesgos potenciales que pueden ser minimizados por nosotros"_

---

## Bloque 1 — Casos reales: cuando la falta de gobernanza sale cara — 7 min

> _"Antes de hablar de reglamentos, quiero contaros tres casos reales, públicos, de empresas que se lo tomaron a la ligera. No son de banca ni de seguros, pero podrían serlo perfectamente."_

**Caso 1 — Samsung y el código fuente (2023)**

> _"Varios ingenieros de Samsung pegaron código fuente propietario en ChatGPT para pedirle ayuda a depurar errores y optimizar procesos. El problema: ese código pasó a formar parte de los datos que la herramienta podía usar fuera de la empresa. Samsung acabó prohibiendo el uso de IA generativa pública en toda la compañía. Nadie actuó con mala intención — simplemente nadie les había dicho que no se podía."_

**Caso 2 — Air Canada y el chatbot (2024)**

> _"El chatbot de atención al cliente de Air Canada le dio a un pasajero información incorrecta sobre la política de reembolsos por fallecimiento de un familiar. La aerolínea intentó defenderse diciendo que el chatbot era 'una entidad legal separada' responsable de sus propias palabras. Un tribunal canadiense no lo aceptó: la empresa es responsable de lo que dice su IA, igual que de lo que dice cualquier empleado."_

**Caso 3 — La autoridad italiana de protección de datos y ChatGPT (2023)**

> _"Italia llegó a bloquear temporalmente el acceso a ChatGPT en todo el país por dudas sobre cómo se trataban los datos personales de los usuarios. Fue el primer país occidental en hacerlo. La herramienta volvió semanas después, con cambios. Pero mostró que los reguladores no se van a quedar mirando."_

**El patrón común:**

> _"En los tres casos no hubo mala fe. Hubo falta de reglas claras, y cuando las reglas no existen, las pone otro por vosotros — un tribunal, un regulador, o la propia dirección con una prohibición total después del susto. Gobernar la IA antes de que pase algo es mucho más barato que gobernarla después."_

**Frase que debe quedar:**

> _"Estas tres empresas no tenían gente malintencionada. Tenían gente sin reglas claras. Es la misma situación en la que puede estar cualquiera de esta sala hoy."_

---

## Bloque 2 — Niveles de riesgo: EU AI Act traducido — 10 min

> _"Existe una regulación europea, el EU AI Act, que clasifica cualquier sistema de IA según su nivel de riesgo. No os voy a leer el reglamento — os lo voy a traducir a ejemplos de vuestro día a día."_

| Nivel de riesgo     | Ejemplo genérico (EU AI Act)                                  | Ejemplo aplicado a nuestro contexto                               |
| ------------------- | ------------------------------------------------------------- | ----------------------------------------------------------------- |
| **Inaceptable**     | Scoring social, vigilancia masiva                             | Prohibido por definición — no debería aparecer en nuestro trabajo |
| **Alto riesgo**     | Selección de personal, diagnóstico médico, scoring crediticio | Ver detalle abajo en la política interna                          |
| **Riesgo limitado** | Chatbots (deben avisar que son IA)                            | Agentes de Copilot Studio como el de la Charla 13                 |
| **Riesgo mínimo**   | Autocompletado, filtros de spam                               | Uso de Copilot para autocompletar código                          |

> _"La regla general es simple: cuanto más impacto tiene la decisión sobre una persona real — un cliente, un candidato, un empleado — más control necesita. Y en banca y seguros, muchas de nuestras decisiones tienen justo ese impacto."_

**Frase que debe quedar:**

> _"No toda IA es igual de arriesgada. La pregunta no es '¿puedo usar IA?', es '¿qué está en juego si me equivoco?'"_

### Política interna: nuestros 5 niveles de riesgo

> _"El EU AI Act es el marco legal. Internamente, en la empresa, aterrizamos ese marco en 5 niveles operativos con criterios claros, aprobación mínima y evidencia esperada."_

| Nivel         | Criterios                                                                                                             | Ejemplos                                                                                      | Aprobación mínima                                        | Evidencia                                                         |
| ------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------- | ----------------------------------------------------------------- |
| **Prohibido** | Contrato y/o política                                                                                                 | Herramientas externas, datos de cliente, secrets en prompts y cambios autónomos en producción | No aprobable                                             | Bloqueo inmediato                                                 |
| **Crítico**   | Efectos jurídicos y/o regulatorios, decisiones automatizadas sensibles o exposición elevada de datos                  | Automatizaciones con acción sobre producción y decisiones con impacto material                | Comité de IA, además de Legal/DPO/Security según aplique | Go/no-go, plan de rollback, monitorización reforzada              |
| **Alto**      | Afecta a cliente, usa datos personales, código o información confidencial, impacta en producción o seguridad          | Análisis de tickets con datos reales, código y respuestas de cliente                          | Departamento de IA                                       | Aprobación explícita                                              |
| **Medio**     | Genera artefactos de proyecto o usa datos internos no públicos pero no críticos sin ejecución autónoma                | User stories, documentación técnica, tests, refactorizaciones no críticas                     | Project Manager + Tech/QA Lead                           | Caso de uso documentado, clasificación de datos y revisión humana |
| **Bajo**      | Uso asistencial interno, sin datos personales, sin información confidencial ni efecto directo en cliente o producción | Borradores internos y ayuda sobre sintaxis                                                    | Responsable directo del equipo                           | Registro básico del uso si genera entregable                      |

> _"Fijaos en el detalle importante: cuanto más alto el nivel, no solo cambia lo que podéis o no hacer. Cambia quién tiene que aprobarlo y qué prueba hay que dejar de que la decisión se tomó bien. Esto es lo que separa una política real de un cartel bienintencionado."_

📎 _Para quien quiera profundizar en el marco regulatorio completo (EU AI Act, ISO 42001, NIST AI RMF), la referencia está en la nota [[ai-governance]] del vault._

---

## Bloque 3 — Qué significa esto según tu rol — 6 min

> _"La gobernanza no pesa igual para todos. Vamos rápido por cuatro perfiles que hay hoy en esta sala."_

| Rol                             | Qué le toca vigilar especialmente                                                                                                           |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Developer**                   | Código y datos técnicos en herramientas de IA — conecta con la Dim. 2 y 5 del framework de madurez (desarrollo, configuración)              |
| **Comercial / cara al cliente** | Nunca compartir datos de cliente en herramientas no aprobadas; cualquier propuesta o comunicación generada con IA, revisión antes de enviar |
| **RRHH**                        | Especial cuidado si se usa IA en procesos de selección o evaluación de personas — es zona de "alto riesgo" por definición del EU AI Act     |
| **Management / PM**             | Responsabilidad de que el equipo conozca la política, no solo de aplicarla personalmente — la Dim. 8 (Cultura y Adopción) empieza aquí      |

**Frase que debe quedar:**

> _"La gobernanza no es un documento que lee una persona de compliance. Es una responsabilidad repartida, distinta para cada rol, pero de todos."_

---

## Bloque 4 — Núcleo: política interna de uso de IA, punto por punto — 15 min

> _"Hasta aquí hemos hablado del marco. Ahora entramos en el documento real: la política interna que aplica desde mañana. Cuatro piezas — vamos una a una."_

### 4.1 Escenarios permitidos por fase de trabajo

> _"La primera pregunta es la más práctica: ¿en qué momento del trabajo puedo usar IA y en cuál no? La política lo organiza por fase."_

| Fase / Actividad                  | Permitido                        | Condicionado                                               | Prohibido                                                |
| --------------------------------- | -------------------------------- | ---------------------------------------------------------- | -------------------------------------------------------- |
| Diseño y arquitectura             | Alternativas a diseños genéricos | Propuestas usando el contexto del proyecto                 | Exposición de posibles secrets                           |
| Desarrollo y generación de código | Asistencia a la sintaxis         | Generación de código en herramientas aprobadas para su uso | Herramientas no autorizadas para la generación de código |
| Pruebas y QA                      | Idear casos de prueba            | Generación de pruebas unitarias con contexto del proyecto  | Usar datos reales                                        |

> _"'Condicionado' no es una casilla decorativa. Significa: sí, pero con estos requisitos. Cuando algo cae en condicionado, la responsabilidad de comprobar que se cumplen las condiciones es tuya, no del que escribió la política."_

---

### 4.2 Revisión humana obligatoria

> _"Segunda pieza: ¿quién revisa qué antes de que el output tenga consecuencias reales? Un agente puede equivocarse — la responsabilidad final sigue siendo humana."_

| Output / acción      | Revisión mínima requerida | Aprobador / owner    | Evidencia esperada                       |
| -------------------- | ------------------------- | -------------------- | ---------------------------------------- |
| Código en producción | Code Review humana        | Developer o Reviewer | Pull Request y documento de aceptación   |
| Análisis funcional   | Revisión de contenido     | Manager              | Comprobación del contenido del documento |


> _"La columna de 'evidencia' es la que suele faltar en políticas mal hechas. Sin evidencia — un log, un firmante, una traza — la revisión no existe a efectos de auditoría, aunque haya ocurrido."_

---

### 4.3 Herramientas: corporativas y restricciones con cliente

> _"Tercera pieza: qué se puede usar. Esta tabla la mantendremos actualizada al margen del guion, porque cambia con más frecuencia que el resto de la política."_

| Herramienta                            | Restricciones con cliente       |
| -------------------------------------- | ------------------------------- |
| Microsoft 365 Copilot y GitHub copilot | Aceptación por parte de cliente |

**Caso aplicado:**

> _"Instalarse una extensión de IA de una tienda de navegador porque parece útil, sin pasar por el canal oficial — eso es Shadow AI, aunque la intención sea buena."_

**Segundo caso aplicado:**

> _"Un equipo descubre una herramienta gratuita para transcribir reuniones y la usa en llamadas con clientes sin consultar. La grabación y la transcripción pueden estar pasando por servidores fuera de cualquier control de la empresa — exactamente el tipo de caso que llevó a Samsung a prohibir la IA generativa pública."_

---

### 4.4 Checklist rápido de decisión

> _"Cuarta y última pieza. Antes de usar una IA para algo real, cuatro preguntas — si respondes 'no' a alguna, para y consulta."_

| #   | Pregunta                                                |
| --- | ------------------------------------------------------- |
| 1   | ¿Puedo usar esta herramienta con mi cuenta corporativa? |
| 2   | ¿Puedo usar estos datos en este entorno?                |
| 3   | ¿Mi cliente me permite el uso de esta IA?               |
| 4   | ¿Quién revisa el trabajo realizado? ¿Está documentado?  |

**Frase que debe quedar:**

> _"Una política de gobernanza no existe para frenaros. Existe para que sepáis, en el momento de dudar, qué hacer sin tener que adivinarlo."_

---

## Bloque 5 — Autoevaluación: en qué nivel estáis vosotros — 5 min

> _"Todo esto que hemos visto no es abstracto. Ya tenéis, dentro de la empresa, una forma de medir en qué nivel de madurez estáis exactamente en gobernanza — el mismo framework de 8 dimensiones que usa el embajador de IA para el resto del equipo."_

**Recordatorio rápido de la escala (0-4):**

| Score | Nivel                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | Inexistente / Shadow AI                                            |
| 1     | Inicial — uso individual, sin guías                                |
| 2     | Repetible — acuerdos de equipo, consciencia de riesgos             |
| 3     | Gestionado — integración formal, métricas                          |
| 4     | Optimizado — mejora continua, gobernanza integrada en el día a día |

**Cómo se interpreta, en la práctica:**

> _"Si en la Dimensión 7 — Gobierno, Riesgo y Compliance — vuestro score es 1 o menos, es una señal de alerta inmediata: puede que estéis usando IA sin conocer las restricciones reales del cliente o del proyecto. Eso no es un suspenso personal, es información para saber que hace falta formación urgente, y ahora ya sabéis por dónde empezar — con lo de hoy."_

> _"Si además vuestro score en la Dimensión 8 — Cultura y Adopción — es 3 o más, sois candidatos naturales a ser champions: la persona que ayuda al resto del equipo a subir de nivel, no solo la que cumple la norma."_

**Frase que debe quedar:**

> _"No hace falta esperar a una auditoría externa para saber si estáis en riesgo. La pregunta ya existe dentro de la empresa. Solo hay que hacérsela."_

---

## Cierre — 3 min

> _"Primera idea: el Shadow AI no nace de mala fe, nace de falta de información. La solución no es más control, es más claridad."_
>
> _"Segunda idea: no toda IA tiene el mismo riesgo. Cuanto más impacto tiene la decisión sobre una persona real, más cuidado hace falta."_
>
> _"Tercera idea: esto no es solo cosa de developers. Todos los que estáis en esta sala tomáis decisiones cada semana sobre qué compartir con una IA — la política de hoy es para todos."_

**Referencias para profundizar:**

- [[ai-governance]] — marco regulatorio completo (EU AI Act, ISO 42001, NIST)
- El checklist rápido del Bloque 4.4 es lo que os lleváis a la mesa mañana

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
