---
type: Material
title: "Material Charla 14 — Gobernanza de IA: guía práctica para el equipo"
description: "Documento exhaustivo post-charla con contexto teórico, casos reales, marco regulatorio (EU AI Act, ISO 42001, NIST AI RMF), política interna, autoevaluación y referencias externas."
tags: [material, charla-14, gobernanza, riesgo, compliance, shadow-ai, eu-ai-act, iso-42001, nist]
related: [ai-governance, metricas-ia, copilot-studio, agente-ia, arnes-completo]
charla: "Charla 14"
estado: "✅ Publicado"
timestamp: "2026-07-30"
asistentes: 168
---

# Material Charla 14 — Gobernanza de IA: guía práctica para el equipo

> Este documento amplía y complementa lo visto en la charla del 29 de julio de 2026. No sustituye al guion ([`guion-charla-14.md`](guiones/guion-charla-14.md)) — lo desarrolla con más contexto, referencias externas y detalle práctico. Léelo con tranquilidad. Los enlaces externos están al final de cada sección.

---

## Índice

1. [Punto de partida: de qué venimos hablando](#punto-de-partida-de-qué-venimos-hablando)
2. [Shadow AI: el fenómeno que da nombre a la charla](#shadow-ai-el-fenómeno-que-da-nombre-a-la-charla)
3. [Tres casos reales explicados en profundidad](#tres-casos-reales-explicados-en-profundidad)
4. [El marco legal: EU AI Act](#el-marco-legal-eu-ai-act)
5. [Marcos complementarios: ISO 42001 y NIST AI RMF](#marcos-complementarios-iso-42001-y-nist-ai-rmf)
6. [Nuestra política interna: los 5 niveles de riesgo](#nuestra-política-interna-los-5-niveles-de-riesgo)
7. [La política, punto por punto](#la-política-punto-por-punto)
8. [Qué significa esto según tu rol](#qué-significa-esto-según-tu-rol)
9. [Autoevaluación: el framework de 8 dimensiones](#autoevaluación-el-framework-de-8-dimensiones)
10. [Preguntas frecuentes de la sala](#preguntas-frecuentes-de-la-sala)
11. [Glosario](#glosario)
12. [Recursos para profundizar](#recursos-para-profundizar)

---

## Punto de partida: de qué venimos hablando

En la [[guion-charla-13|Charla 13]] pasamos de saber a medir: construimos un agente en Copilot Studio y aprendimos a leer sus métricas — engagement rate, resolution rate, deflection rate. Sabíamos si un agente funcionaba.

Pero medir si funciona no es lo mismo que asegurar que se usa bien. Un agente puede tener un resolution rate del 90% y estar filtrando datos de cliente en cada respuesta. Una IA de asistencia al desarrollo puede ser productiva y estar exponiendo secretos en cada commit sugerido. **La eficacia y la seguridad de uso son dos preguntas distintas — y hasta ahora la serie solo había respondido la primera.**

La Charla 14 responde la segunda: cómo se usa la IA con criterio, sabiendo qué está permitido, qué está condicionado, qué está prohibido, y qué hacer cuando algo sale mal.

---

## Shadow AI: el fenómeno que da nombre a la charla

**Shadow AI** es el uso de herramientas de inteligencia artificial dentro de una organización sin conocimiento, aprobación ni control de esa organización. Es el equivalente actual del "Shadow IT" — cuando la gente usaba Dropbox personal para compartir archivos de trabajo porque el canal oficial era lento o inexistente.

### Por qué aparece

El Shadow AI casi nunca es un acto de rebeldía. Aparece por tres motivos, y los tres son estructurales, no individuales:

1. **Falta de reglas claras.** Nadie ha dicho explícitamente qué se puede y qué no se puede. Ante la ambigüedad, cada persona decide por su cuenta — y decide mal, porque no tiene por qué conocer las restricciones del cliente o del contrato.
2. **Herramientas oficiales insuficientes o lentas.** Si la IA aprobada tarda dos semanas en configurarse o no cubre el caso de uso, la gente busca alternativas por su cuenta.
3. **Presión de productividad.** "El compañero de al lado usa X y va mucho más rápido" — sin que nadie haya validado si X está permitido.

### Por qué es un problema

Los datos que salen de la organización no vuelven. Un fragmento de código, un extracto de un email a cliente, un identificador personal — una vez pegado en una herramienta pública, sale del perímetro de control de la empresa y puede quedar como parte del corpus de entrenamiento, almacenamiento, o incluso ser visible para otros usuarios en caso de un fallo de seguridad de la propia herramienta.

Además de la fuga en sí, hay consecuencias regulatorias (GDPR, secreto profesional, cláusulas contractuales con cliente) y reputacionales.

**Referencias externas:**

- [Shadow AI — Gartner Glossary](https://www.gartner.com/en/information-technology/glossary)
- Ross, A. (2024). *Shadow AI: Why It's Everywhere and What to Do About It*. Harvard Business Review, junio 2024.
- Cyberhaven Labs (2023). *Confidential company data pasted into ChatGPT*. Estudio empírico sobre uso no autorizado.

---

## Tres casos reales explicados en profundidad

Los tres casos que vimos en la charla son reales, verificables y documentados. Aquí van con más detalle y referencias.

### Caso 1 — Samsung y el código fuente (abril-mayo 2023)

**Antecedentes.** A principios de 2023, tras el lanzamiento público de ChatGPT, Samsung —como la mayoría de grandes tecnológicas— no tenía una política formal que regulara su uso por parte de los empleados. La herramienta se había adoptado de forma orgánica y espontánea entre los equipos de ingeniería como asistente de productividad, sin pasar por ningún proceso de aprobación ni evaluación de riesgo.

**El incidente.** Varios ingenieros de la división de semiconductores de Samsung pegaron código fuente propietario en ChatGPT en tres incidentes separados, ocurridos en menos de un mes:

- Un ingeniero pegó código fuente de una base de datos interna para pedirle a ChatGPT que le ayudara a corregir errores.
- Otro pegó código relacionado con la identificación de defectos en semiconductores para optimizarlo.
- Un tercero convirtió una grabación de una reunión interna en texto y la pegó para generar un resumen.

**La solución adoptada.** En mayo de 2023, en cuestión de semanas desde la detección, Samsung tomó tres medidas: (1) prohibió con efecto inmediato el uso de IA generativa pública (ChatGPT, Bard, Bing Chat) en todos los dispositivos corporativos y en los personales conectados a la red interna; (2) estableció un límite de tamaño de subida de 1024 bytes por consulta mientras duraba la prohibición total, como control transitorio; (3) anunció el desarrollo de una herramienta de IA generativa interna y controlada, para no renunciar a la productividad que la tecnología ofrecía.

**Qué ocurrió después.** La prohibición se mantuvo mientras la compañía desarrollaba su gobernanza interna. Samsung acabó lanzando su propia herramienta de IA generativa de uso interno meses después, con controles de qué tipo de datos podían introducirse. El caso se convirtió en una referencia citada de forma recurrente en el sector como el ejemplo de manual de fuga de datos por Shadow AI, y aceleró que otras muchas empresas tecnológicas publicaran sus propias políticas de uso de IA generativa ese mismo año.

**Lección para nosotros:** ninguno de los tres ingenieros actuaba de mala fe. Todos estaban intentando ser más productivos. El problema no fue humano — fue de gobierno: no había una política que dijera "esto no se puede hacer".

- [Samsung bans staff's AI use after spotting ChatGPT data leak — Bloomberg (mayo 2023)](https://www.bloomberg.com/news/articles/2023-05-02/samsung-bans-chatgpt-and-other-generative-ai-use-by-staff-after-leak)
- [Samsung Ban on ChatGPT Impacts Global Companies — Forbes](https://www.forbes.com/sites/siladityaray/2023/05/02/samsung-bans-chatgpt-and-other-chatbots-for-employees-after-sensitive-code-leak/)

### Caso 2 — Moffatt v. Air Canada (2022-2024)

**Antecedentes.** En noviembre de 2022, Air Canada desplegó un chatbot de atención al cliente en su web para resolver dudas frecuentes, incluida información sobre tarifas y políticas de reembolso. El chatbot se alimentaba de la documentación de políticas de la aerolínea, pero sin un proceso robusto de validación de las respuestas generadas frente al contenido oficial actualizado.

**El incidente.** En noviembre de 2022, Jake Moffatt, cuyo abuelo había fallecido, consultó al chatbot sobre la política de tarifas por duelo (*bereavement fares*). El chatbot le indicó que podía reservar un vuelo a precio normal y solicitar el descuento retroactivamente durante los 90 días siguientes. Esa información **era incorrecta**: la política real de Air Canada requería solicitar la tarifa de duelo antes de viajar, no después.

**La respuesta inicial de la empresa.** Cuando Moffatt solicitó el reembolso conforme a lo que el chatbot le había prometido, Air Canada lo rechazó. La aerolínea argumentó ante el tribunal que el chatbot era "una entidad legal separada, responsable de sus propias palabras" — es decir, intentó deslindar su responsabilidad como empresa de lo que había dicho su propio sistema automatizado.

**La solución — vía judicial, no corporativa.** El caso llegó al Civil Resolution Tribunal de la Columbia Británica (Canadá). En febrero de 2024, el tribunal falló a favor de Moffatt, rechazando el argumento de Air Canada y dictaminando que la empresa era responsable de toda la información proporcionada por su sitio web, chatbot incluido. Air Canada tuvo que pagar 812,02 dólares canadienses en concepto de daños y costas.

**Qué ocurrió después.** Air Canada retiró la información incorrecta y actualizó el chatbot. El caso se convirtió en el precedente legal más citado internacionalmente sobre responsabilidad corporativa por outputs de IA conversacional, y ha sido usado desde entonces como referencia en otros litigios y en el diseño de políticas de gobernanza de agentes conversacionales en distintos sectores, incluido el financiero.

**Lección para nosotros:** la responsabilidad de lo que dice un agente conversacional recae en la empresa que lo despliega. Igual que la responsabilidad de lo que dice un empleado. No hay una "capa de agente autónomo" que absuelva de responsabilidad — al menos, no en tribunal.

- [Air Canada must honor refund policy invented by its chatbot — The Guardian (febrero 2024)](https://www.theguardian.com/world/2024/feb/16/air-canada-chatbot-lawsuit)
- [Moffatt v. Air Canada, 2024 BCCRT 149 — Texto de la resolución](https://decisions.civilresolutionbc.ca/crt/sc/en/nav.do)

### Caso 3 — El Garante italiano y ChatGPT (marzo–abril 2023)

**Antecedentes.** ChatGPT se lanzó públicamente en noviembre de 2022 y su adopción masiva ocurrió sin que OpenAI hubiera completado un análisis de conformidad específico con el marco de protección de datos europeo (GDPR), pese a estar disponible y en uso activo en la Unión Europea desde el primer momento.

**El incidente.** El **Garante per la protezione dei dati personali** (autoridad italiana de protección de datos, equivalente a la AEPD española) investigó la herramienta y, el 31 de marzo de 2023, ordenó el bloqueo temporal e inmediato de ChatGPT en Italia. Fue el **primer país occidental** en tomar una medida de este calibre contra un servicio de IA generativa pública. Los motivos citados: falta de base legal para procesar los datos personales usados en el entrenamiento del modelo, ausencia de mecanismos de verificación de edad para menores, y falta de transparencia sobre el uso de datos de los usuarios de la plataforma.

**La solución adoptada.** OpenAI negoció directamente con el Garante y, en menos de un mes, implementó un paquete de cambios concretos: mecanismos de opt-out para que los usuarios europeos pudieran solicitar que sus datos no se usaran para entrenar el modelo, información de tratamiento de datos más clara y accesible desde la propia interfaz, y un sistema de verificación de edad para restringir el acceso a menores.

**Qué ocurrió después.** El servicio volvió a estar disponible en Italia el 28 de abril de 2023. El caso sentó un precedente de cómo un solo regulador nacional europeo puede forzar cambios de producto globales en una herramienta usada por cientos de millones de personas, y aceleró el trabajo legislativo que terminaría materializándose en el EU AI Act. Desde entonces, otras autoridades de protección de datos europeas han abierto investigaciones similares sobre distintas herramientas de IA generativa, usando el caso italiano como referencia de procedimiento.

**Lección para nosotros:** los reguladores no se van a quedar mirando. La tolerancia inicial hacia la IA generativa está cerrándose rápidamente, y los sectores más regulados — como banca y seguros — son los primeros en notar la presión.

- [Italy became the first Western country to ban ChatGPT — Reuters (marzo 2023)](https://www.reuters.com/technology/italy-data-protection-agency-opens-chatgpt-probe-privacy-concerns-2023-03-31/)
- [Nota oficial del Garante — Provvedimento del 30 marzo 2023](https://www.garanteprivacy.it/web/guest/home/docweb/-/docweb-display/docweb/9870832)

---

## El marco legal: EU AI Act

El **Reglamento (UE) 2024/1689 del Parlamento Europeo y del Consejo, de 13 de junio de 2024, por el que se establecen normas armonizadas en materia de inteligencia artificial** — conocido como **EU AI Act** — es la primera regulación integral de la IA a nivel de bloque económico. Entró en vigor el 1 de agosto de 2024, con una aplicación escalonada:

- **2 de febrero de 2025:** prohibiciones de sistemas de riesgo inaceptable (efectivas).
- **2 de agosto de 2025:** obligaciones para modelos fundacionales (GPAI).
- **2 de agosto de 2026:** obligaciones de transparencia (Artículo 50) y obligaciones plenas para sistemas de alto riesgo — justo esta semana, ver el documento de novedades de esta semana.
- **2 de agosto de 2027:** aplicación plena, incluyendo sistemas de alto riesgo integrados en productos regulados.

### Las 4 categorías de riesgo

El reglamento clasifica los sistemas de IA en cuatro niveles según el impacto potencial sobre los derechos fundamentales, la seguridad y el bienestar de las personas:

**1. Riesgo inaceptable (prohibidos)**
Sistemas que suponen una amenaza clara para la seguridad, los medios de vida o los derechos fundamentales. Están **prohibidos por completo** dentro del territorio de la UE. Incluyen:
- Manipulación cognitivo-conductual de personas o grupos vulnerables.
- Puntuación social por parte de gobiernos.
- Identificación biométrica en tiempo real en espacios públicos (con excepciones muy tasadas para fuerzas de seguridad).
- Categorización biométrica basada en datos sensibles (raza, orientación sexual, opiniones políticas).
- Predicción policial individualizada basada únicamente en perfiles.
- Scraping masivo no dirigido de imágenes faciales para bases de datos de reconocimiento.
- Reconocimiento de emociones en el lugar de trabajo y en instituciones educativas.

**2. Alto riesgo**
Sistemas que pueden afectar significativamente a la seguridad o a los derechos fundamentales de las personas. **Permitidos, pero con obligaciones estrictas** de evaluación de conformidad, transparencia, supervisión humana y trazabilidad. Ejemplos relevantes para nosotros:
- IA usada en selección o gestión de personal (contratación, evaluaciones, promociones).
- IA en scoring crediticio o determinación de acceso a servicios financieros.
- IA en evaluación de riesgos de seguros.
- IA en la administración de justicia y procesos democráticos.
- IA como componente de seguridad en infraestructuras críticas.

**3. Riesgo limitado**
Sistemas con obligaciones específicas de transparencia. Los usuarios deben saber que están interactuando con una IA. Se aplica principalmente a:
- Chatbots y asistentes conversacionales.
- Deepfakes y contenido generado o manipulado.
- Sistemas de reconocimiento de emociones (fuera del ámbito de alto riesgo).

**4. Riesgo mínimo**
Todo lo demás. Sin obligaciones específicas más allá del cumplimiento general del resto de normativa (GDPR, ciber, etc.). Incluye la inmensa mayoría de usos productivos: autocompletado, filtros de spam, videojuegos, recomendaciones de contenido no crítico.

### Un detalle importante: dónde está la responsabilidad

El EU AI Act distingue entre **proveedor** (quien desarrolla o comercializa el sistema) y **usuario profesional** (quien lo despliega en su actividad). Ambos tienen obligaciones — no basta con "yo solo estoy usando ChatGPT, la responsabilidad es de OpenAI". Si desplegamos un agente de Copilot Studio para atender a clientes, somos usuarios profesionales de un sistema de IA y asumimos las obligaciones asociadas a esa figura.

**Referencias oficiales:**

- [Reglamento (UE) 2024/1689 — Texto oficial en EUR-Lex](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
- [AI Act Explorer — Herramienta oficial de la Comisión Europea](https://artificialintelligenceact.eu/)
- [Preguntas y respuestas oficiales sobre el AI Act](https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai)

---

## Marcos complementarios: ISO 42001 y NIST AI RMF

El EU AI Act es el marco **legal**. No dice **cómo** cumplirlo — dice **qué** hay que cumplir. Para el "cómo" existen dos referencias técnicas que son las que usan las empresas maduras para operativizar la gobernanza:

### ISO/IEC 42001:2023

Publicada en diciembre de 2023, la **ISO/IEC 42001** es la primera norma internacional certificable de gestión de sistemas de inteligencia artificial. Sigue la misma estructura que otras normas ISO conocidas — ISO 27001 (seguridad de la información), ISO 9001 (calidad) — con el ciclo Plan-Do-Check-Act.

**Qué cubre:**
- Requisitos para establecer, implementar, mantener y mejorar continuamente un sistema de gestión de IA.
- Evaluación y tratamiento de riesgos relacionados con la IA.
- Obligaciones para toda la organización, no solo el equipo técnico.

**Por qué importa:** para clientes de banca y seguros, la certificación ISO 42001 empieza a aparecer como requisito o factor diferenciador en licitaciones. Si un cliente pide "gestión de IA certificable", es probable que se refiera a este marco.

- [ISO/IEC 42001:2023 — Ficha oficial](https://www.iso.org/standard/81230.html)

### NIST AI Risk Management Framework (AI RMF 1.0)

Publicado por el **National Institute of Standards and Technology** (EE.UU.) en enero de 2023, el **NIST AI RMF** es un marco voluntario, no certificable, muy usado como referencia técnica global. Está estructurado en cuatro funciones:

- **GOVERN** — establecer cultura, procesos y responsabilidades de gestión de riesgos de IA.
- **MAP** — identificar contexto y riesgos específicos del sistema de IA.
- **MEASURE** — evaluar, analizar y monitorizar los riesgos identificados.
- **MANAGE** — priorizar y actuar sobre los riesgos.

Aunque el NIST es una institución estadounidense, el marco tiene alcance internacional y muchas empresas europeas lo usan como guía técnica junto con ISO 42001.

- [NIST AI Risk Management Framework 1.0 (PDF)](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf)
- [NIST AI RMF Playbook](https://www.nist.gov/itl/ai-risk-management-framework)

### Cómo se relacionan entre sí

- **EU AI Act:** dice **qué** cumplir. Obligatorio en la UE.
- **ISO 42001:** dice **cómo** gestionarlo internamente. Certificable. Ayuda a demostrar cumplimiento.
- **NIST AI RMF:** dice **cómo** analizar y tratar los riesgos técnicos. Referencia global no certificable.

Los tres son complementarios y no compiten. Nuestra política interna se apoya conceptualmente en los tres.

📎 Ver también la nota [[ai-governance]] del vault para el detalle completo de estos marcos.

---

## Nuestra política interna: los 5 niveles de riesgo

La política interna aterriza el marco legal (4 categorías del EU AI Act) en **5 niveles operativos**. Los 5 niveles no sustituyen a los 4 de la ley — los especifican. La diferencia clave respecto al marco legal es que la política interna incorpora dos dimensiones que el reglamento no fija: **quién aprueba cada uso** y **qué evidencia hay que dejar** de esa aprobación.

### Los 5 niveles

**Nivel Prohibido**
- **Criterios:** contradicción directa con contrato de cliente o con la política de la empresa.
- **Ejemplos:** herramientas externas no aprobadas, datos de cliente identificables en IA pública, secretos (credenciales, tokens, claves) en prompts, cambios autónomos en producción sin revisión humana.
- **Aprobación mínima:** **no aprobable.** No hay figura interna con autoridad para permitirlo.
- **Evidencia:** bloqueo inmediato del uso al detectarlo.

**Nivel Crítico**
- **Criterios:** el uso tiene efectos jurídicos o regulatorios, incorpora decisiones automatizadas sensibles, o expone datos con alto grado de confidencialidad.
- **Ejemplos:** automatizaciones con acción sobre producción, decisiones con impacto material sobre cliente o empleado.
- **Aprobación mínima:** Comité de IA. Legal, DPO y Security participan según aplique.
- **Evidencia:** go/no-go documentado, plan de rollback definido antes del despliegue, monitorización reforzada durante el uso.

**Nivel Alto**
- **Criterios:** el uso afecta directamente a cliente, procesa datos personales, incorpora código o información confidencial, o tiene impacto en producción o en seguridad.
- **Ejemplos:** análisis de tickets con datos reales, generación de código que va a producción, respuestas automatizadas a cliente.
- **Aprobación mínima:** Departamento de IA.
- **Evidencia:** aprobación explícita registrada.

**Nivel Medio**
- **Criterios:** el uso genera artefactos de proyecto o consume datos internos no públicos pero no críticos. No hay ejecución autónoma.
- **Ejemplos:** generación de user stories, documentación técnica, tests unitarios, refactorizaciones no críticas.
- **Aprobación mínima:** Project Manager junto con Tech Lead o QA Lead.
- **Evidencia:** caso de uso documentado, clasificación de los datos utilizados, revisión humana del output.

**Nivel Bajo**
- **Criterios:** uso asistencial interno, sin datos personales, sin información confidencial, sin efecto directo en cliente ni en producción.
- **Ejemplos:** borradores internos, consultas de sintaxis, ayuda para redactar un correo interno.
- **Aprobación mínima:** responsable directo del equipo.
- **Evidencia:** registro básico si el uso genera un entregable.

### La lógica detrás de los 5 niveles

Fijaos en el patrón: **cuanto más alto el nivel, no solo cambia lo que se puede o no hacer — cambian dos cosas más importantes**:

- **Quién aprueba.** De un compañero de equipo (Bajo), a un PM+Lead (Medio), a Departamento de IA (Alto), a Comité de IA con Legal/DPO/Security (Crítico), a nadie (Prohibido).
- **Qué prueba hay que dejar.** Del simple registro (Bajo), al caso de uso documentado (Medio), a la aprobación explícita (Alto), al plan de rollback y monitorización reforzada (Crítico), al bloqueo (Prohibido).

Esa es la diferencia entre una política operativa real y un cartel bienintencionado colgado en la intranet.

---

## La política, punto por punto

### 4.1 Escenarios permitidos por fase de trabajo

La política no habla solo de "usar IA" en abstracto — habla de en qué **momento** del ciclo de trabajo se puede usar y en cuál no.

**Diseño y arquitectura**
- ✅ *Permitido:* usar IA para explorar alternativas a diseños genéricos, brainstorming de patrones arquitectónicos, referencias comparativas.
- ⚠️ *Condicionado:* pedir propuestas usando el contexto real del proyecto. Requiere estar en una herramienta aprobada y no exponer secretos.
- ❌ *Prohibido:* exponer secretos del proyecto (claves, tokens, endpoints internos) en ninguna herramienta de IA, aprobada o no.

**Desarrollo y generación de código**
- ✅ *Permitido:* asistencia a la sintaxis, autocompletado de estructuras conocidas, explicación de errores.
- ⚠️ *Condicionado:* generación de código en herramientas aprobadas para ese uso, con revisión humana obligatoria antes del merge.
- ❌ *Prohibido:* usar herramientas no autorizadas para generar código que vaya a producción. Aunque la herramienta parezca inocua.

**Pruebas y QA**
- ✅ *Permitido:* idear casos de prueba, plantillas de test, explorar cobertura.
- ⚠️ *Condicionado:* generar pruebas unitarias usando el contexto real del proyecto, en herramienta aprobada.
- ❌ *Prohibido:* usar datos reales de cliente (aunque sean de test o preproducción) en herramientas no dedicadas.

**El significado de "Condicionado" — atención especial.** No es una casilla decorativa. Significa: "sí, pero con estos requisitos". Y la responsabilidad de verificar que se cumplen esos requisitos **es de quien va a usar la herramienta, no del que escribió la política**. Si tienes dudas sobre si un uso concreto cumple las condiciones, pregunta antes.

### 4.2 Revisión humana obligatoria

Un agente puede equivocarse. De hecho, lo bueno de un agente bien construido — como vimos en la Charla 13 — es que **reconoce cuándo no sabe algo**. Pero la responsabilidad final de lo que sale hacia un cliente, de lo que se despliega a producción, o de lo que se firma como documento oficial, **sigue siendo humana**.

| Output / acción | Revisión mínima | Aprobador / owner | Evidencia esperada |
|---|---|---|---|
| Código en producción | Code Review humana | Developer o Reviewer | Pull Request + documento de aceptación |
| Análisis funcional | Revisión de contenido | Manager | Comprobación documentada del contenido |

**Por qué importa tanto la columna "Evidencia".** Es la que suele faltar en políticas mal hechas. Sin evidencia — un log, un firmante, una traza en un sistema — la revisión **no existe a efectos de auditoría**, aunque de hecho haya ocurrido. En sectores regulados como banca y seguros, un cliente puede pedirnos demostrar quién revisó qué. Si la única prueba es "confía en mí, lo revisamos", eso no vale.

### 4.3 Herramientas: corporativas y restricciones con cliente

Hoy, el listado de herramientas corporativamente aprobadas para uso profesional con datos internos es:

| Herramienta | Restricciones con cliente |
|---|---|
| Microsoft 365 Copilot y GitHub Copilot | Aceptación por parte del cliente |

Notas importantes:

- **"Aceptación por parte del cliente" significa aceptación formal, no verbal.** Muchos contratos actuales de cliente incluyen cláusulas que **prohíben** el uso de asistentes de IA sobre su propiedad intelectual, aunque la herramienta esté aprobada por nuestra empresa. Antes de usar Copilot sobre código o documentación de cliente, hay que confirmar por escrito que ese cliente lo permite.
- **Cualquier otra herramienta** — ChatGPT, Claude, Gemini, Perplexity, extensiones de navegador con IA, transcriptores de reunión gratuitos, etc. — está **fuera del listado aprobado** por defecto. Su uso con datos de trabajo cae automáticamente en Prohibido.
- **Este listado cambia con más frecuencia que el resto de la política.** No lo memorices — consúltalo cuando dudes.

**Los dos errores más comunes:**

1. *"Instalarse una extensión de navegador con IA porque parece útil"* — sin pasar por canal oficial. Esto es Shadow AI aunque la intención sea buena. Antes de instalar, canal oficial.
2. *"Usar una herramienta gratuita para transcribir una reunión con cliente"* — la grabación y la transcripción pueden estar pasando por servidores fuera de cualquier control. Es exactamente el patrón que hizo caer a Samsung.

### 4.4 Checklist rápido de decisión

Antes de usar una IA para algo real, cuatro preguntas. **Si respondes "no" a alguna, para y consulta antes de continuar:**

1. **¿Puedo usar esta herramienta con mi cuenta corporativa?**
   Si la respuesta es "estoy en mi cuenta personal", la respuesta a esta pregunta es "no".
2. **¿Puedo usar estos datos en este entorno?**
   Datos de cliente, secretos, información confidencial — no en cualquier entorno.
3. **¿Mi cliente me permite el uso de esta IA?**
   Aunque la herramienta esté aprobada internamente, el contrato con el cliente manda.
4. **¿Quién revisa el trabajo realizado? ¿Está documentado?**
   Un output sin revisión humana definida no puede llegar a producción ni al cliente.

Esta política **no existe para frenaros.** Existe para que sepáis, en el momento de dudar, qué hacer sin tener que adivinarlo.

---

## Qué significa esto según tu rol

La gobernanza no pesa igual para todos los perfiles de la sala. Aquí van las tres o cuatro cosas más importantes por rol:

### Developer

**Lo que te toca vigilar especialmente:**
- Código y datos técnicos en herramientas de IA. Conecta con las dimensiones **2 (Desarrollo)** y **5 (Configuración y Assets)** del framework de madurez.
- Nunca pegar credenciales, tokens, claves de API, endpoints internos, ni fragmentos de código con datos reales.
- Confirmar que el cliente permite Copilot antes de usarlo sobre su código.
- Revisión humana obligatoria de todo código generado antes de ir a producción — aunque la sugerencia parezca obvia.

**Señales de alerta cotidianas:** ver a un compañero pegando output de un log con datos de cliente en una herramienta pública para pedir ayuda a depurar. Ver a alguien usar una extensión de VS Code con IA no aprobada. Ver `.env` copiado a un prompt.

### Comercial / cara al cliente

**Lo que te toca vigilar especialmente:**
- **Nunca compartir datos identificables de cliente** (nombres, cuentas, contratos, condiciones económicas) en herramientas de IA no aprobadas — ni siquiera para "mejorar el tono de un email".
- Cualquier propuesta o comunicación generada o asistida por IA: **revisión humana antes de enviar**. Los outputs de IA pueden sonar bien y contener errores factuales — Air Canada aprendió esto por las malas.
- Si un cliente pregunta sobre nuestro uso de IA, ser transparente. La opacidad hoy es más costosa que la honestidad.

**Señales de alerta cotidianas:** "voy a pedirle a ChatGPT que me ayude a redactar la respuesta a este cliente enfadado" — con datos del cliente en el prompt.

### RRHH

**Lo que te toca vigilar especialmente:**
- **Especial cuidado si se usa IA en procesos de selección, evaluación o promoción de personas.** Es zona de "alto riesgo" por definición explícita del EU AI Act. Aunque la herramienta parezca inocente ("solo me resume los CVs"), estás en zona regulada.
- Nunca pegar datos personales identificables de empleados o candidatos en herramientas no aprobadas.
- La IA no toma la decisión — la persona lo hace. Los outputs de IA son insumo, no veredicto.

**Señales de alerta cotidianas:** "he pedido a una IA que preseleccione candidatos" — sin evaluación de sesgo previa, sin trazabilidad, sin revisión humana documentada.

### Management / PM

**Lo que te toca vigilar especialmente:**
- Responsabilidad no solo de aplicar la política tú mismo, sino de que **el equipo la conozca**. La cultura de gobernanza empieza aquí. Conecta con la dimensión **8 (Cultura y Adopción)** del framework de madurez.
- Facilitar el canal de escalado: la gente tiene que saber a quién preguntar cuando duda, sin miedo a parecer que "no sabe algo básico".
- Detectar Shadow AI en el equipo temprano — normalmente aparece como aumento inusual de productividad sin explicación clara.
- Si el equipo pide una herramienta que no está aprobada, no responder solo "no". Escalar al Departamento de IA para que evalúen la incorporación o la alternativa.

**Señales de alerta cotidianas:** un miembro del equipo entrega mucho más de lo que su ritmo normal justifica, sin haber hablado de nuevas herramientas. Un equipo con score bajo en Dim. 7 del framework de madurez y sin plan de formación.

---

## Autoevaluación: el framework de 8 dimensiones

Todo esto no es abstracto. Dentro de la empresa ya tenéis una forma de medir vuestro nivel de madurez en gobernanza — el mismo framework de 8 dimensiones que usa el embajador de IA con el resto del equipo. Es un instrumento operativo para el jefe de proyecto, para RRHH y para el propio interesado.

### La escala (0-4)

| Score | Nivel | Descripción |
|-------|-------|-------------|
| 0 | Inexistente / Shadow AI | No hay uso oficial. Uso oculto sin control. |
| 1 | Inicial | Uso individual y esporádico. Sin guías ni consistencia. |
| 2 | Repetible | Acuerdos de equipo. Prompts básicos compartidos. Consciencia de riesgos. |
| 3 | Gestionado | Integración formal en el flujo de trabajo. Plantillas, métricas. |
| 4 | Optimizado | Automatización profunda. IA en CI/CD, mejora continua. |

### Las 8 dimensiones (breve recordatorio)

1. **Ideación, Planning y Diseño** — uso de IA en ceremonias, ADRs, estimaciones.
2. **Desarrollo y Generación de Código** — autocompletado, pair programming, agentic.
3. **Testing, Calidad y Seguridad** — generación de tests, SAST/DAST, quality gates.
4. **Validación de Código Generado por IA** — checklists de revisión, trazabilidad.
5. **Configuración y Assets de IA** — AGENTS.md, rules, skills, MCPs, hooks.
6. **Automatización y Agentes Autónomos** — bots en CI/CD, agentes autónomos.
7. **Gobierno, Riesgo y Compliance** ← **el foco de esta charla**.
8. **Cultura, Skills y Adopción** — formación, champions, compartición.

### Cómo se interpreta, en la práctica

- **Score ≤ 1 en Dimensión 7 (Gobierno):** señal de alerta inmediata. Es probable que se esté usando IA sin conocer las restricciones reales del cliente o del proyecto. **Acción recomendada:** formación urgente en políticas — empezar por revisar este documento y el guion de la charla.
- **Score ≥ 3 en Dimensión 8 (Cultura y Adopción):** buen indicador. Estas personas ya no solo cumplen la política — la explican al resto del equipo. **Acción recomendada:** proponerles el rol de champion en su equipo.
- **Score ≥ 3 en Dimensiones 2 (Desarrollo) y 5 (Config) + ≥ 2 en Dimensión 7 (Gobierno):** perfil listo para trabajar con Copilot en modo agentic autónomo en proyectos reales.
- **Score ≤ 1 en todas las dimensiones:** perfil que necesita onboarding completo antes de integrarse en un proyecto con flujo de IA.

**No hace falta esperar a una auditoría externa para saber si estás en riesgo. La pregunta ya existe dentro de la empresa. Solo hay que hacérsela.**

---

## Preguntas frecuentes de la sala

Recojo aquí las preguntas que suelen aparecer sobre este tema. Si tienes otra, coméntala en el canal habitual y la añadimos.

**"¿Y si ya se me ha escapado un dato en ChatGPT? ¿Qué hago?"**
No lo escondas. Habla con tu manager o con el Departamento de IA cuanto antes. La gestión temprana de un incidente es siempre más barata y menos dolorosa que su descubrimiento tardío. No venimos a señalar culpables — venimos a evitar que el problema crezca.

**"¿Puedo usar ChatGPT en mi cuenta personal para cosas del trabajo?"**
No con datos del trabajo. Con datos genéricos o de conocimiento público — un concepto técnico, un ejemplo sintético — sí; con cualquier cosa que se refiera a un cliente, a código propio o interno, o a compañeros identificables, no.

**"¿Puedo dictarle a una IA una reunión con cliente para que me haga el acta?"**
No en herramientas no aprobadas. La transcripción de una reunión con cliente contiene datos personales, información contractual y posibles secretos de negocio — todo eso pasaría por servidores fuera de nuestro control. Si necesitas esta funcionalidad, escálalo al Departamento de IA: existen soluciones aprobadas para ello.

**"¿Puedo usar Copilot en un cliente si el contrato no dice nada?"**
Por defecto, no. La ausencia de mención explícita no equivale a autorización. Consultar con el equipo de contratación o con Legal para verificar.

**"¿La política se aplica también al uso personal fuera del trabajo?"**
La política se aplica al **uso profesional** — cualquier cosa relacionada con la empresa, sus clientes, sus datos o su propiedad intelectual. En tu vida personal usas lo que quieras. Pero el momento en el que abres un documento del trabajo, entra en juego la política.

**"¿Qué pasa si un cliente nos pide desarrollar una IA que caería en 'alto riesgo' del EU AI Act?"**
Se puede — pero con las obligaciones asociadas. Evaluación de conformidad, documentación técnica, sistema de gestión de riesgos, transparencia, supervisión humana. Escalar al Departamento de IA y Legal antes de aceptar el alcance del proyecto.

**"¿Cómo sé si mi caso concreto es 'Alto' o 'Medio'?"**
Ante la duda, súbelo un nivel y pregunta. Es más barato aprobar algo que resultó no necesitarlo que ejecutar sin aprobación algo que sí la necesitaba.

---

## Glosario

**Agente de IA** — sistema que razona sobre una entrada, consulta su base de conocimiento y construye una respuesta adaptada, en lugar de seguir flujos predefinidos. Ver [[agente-ia]].

**AI Act / EU AI Act** — Reglamento (UE) 2024/1689. Marco legal europeo de la IA. Entrada en vigor escalonada 2024-2027.

**Copilot Studio** — plataforma de Microsoft para crear agentes de IA sin código dentro del ecosistema corporativo. Ver [[copilot-studio]].

**DLP (Data Loss Prevention)** — conjunto de tecnologías y políticas para prevenir la fuga o exposición no autorizada de datos.

**Embeddings** — representación matemática del significado de un texto usada para búsqueda semántica. Ver [[embeddings]].

**Evidencia (en contexto de gobernanza)** — prueba documental de que una acción, aprobación o revisión ocurrió, apta para auditoría.

**GPAI (General Purpose AI)** — sistemas de IA de propósito general, como los grandes modelos de lenguaje fundacionales. Categoría específica en el EU AI Act.

**ISO 42001** — Norma internacional certificable de sistemas de gestión de IA publicada en diciembre de 2023.

**NIST AI RMF** — Marco voluntario del National Institute of Standards and Technology para gestión de riesgos de IA.

**RAG (Retrieval-Augmented Generation)** — técnica por la que un modelo consulta una base de documentos específica antes de responder. Ver [[rag]].

**Shadow AI** — uso de herramientas de IA en una organización sin conocimiento ni aprobación de la misma.

**Shadow IT** — término análogo de años anteriores referido a herramientas informáticas no autorizadas.

---

## Recursos para profundizar

### Legislación y marcos oficiales

- [Reglamento (UE) 2024/1689 — EU AI Act (texto oficial EUR-Lex)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
- [AI Act Explorer — Comisión Europea](https://artificialintelligenceact.eu/)
- [ISO/IEC 42001:2023](https://www.iso.org/standard/81230.html)
- [NIST AI Risk Management Framework 1.0](https://www.nist.gov/itl/ai-risk-management-framework)
- [OECD AI Principles](https://oecd.ai/en/ai-principles)

### Autoridades y organismos

- [AEPD — Agencia Española de Protección de Datos, sección de IA](https://www.aepd.es/tecnologia/inteligencia-artificial)
- [Garante per la protezione dei dati personali (Italia)](https://www.garanteprivacy.it/)
- [European AI Office (Comisión Europea)](https://digital-strategy.ec.europa.eu/en/policies/ai-office)

### Casos reales analizados

- [Samsung ChatGPT ban — Bloomberg (mayo 2023)](https://www.bloomberg.com/news/articles/2023-05-02/samsung-bans-chatgpt-and-other-generative-ai-use-by-staff-after-leak)
- [Moffatt v. Air Canada — The Guardian (febrero 2024)](https://www.theguardian.com/world/2024/feb/16/air-canada-chatbot-lawsuit)
- [Italian Garante ChatGPT ban — Reuters (marzo 2023)](https://www.reuters.com/technology/italy-data-protection-agency-opens-chatgpt-probe-privacy-concerns-2023-03-31/)

### Lectura recomendada

- Kate Crawford — *Atlas of AI* (Yale University Press, 2021). Contexto amplio de los sistemas de IA y sus implicaciones.
- Cathy O'Neil — *Weapons of Math Destruction* (Crown, 2016). Sistemas algorítmicos y sus consecuencias sociales; buena introducción al pensamiento sobre riesgo.
- Comisión Europea — *Ethics Guidelines for Trustworthy AI* (2019). Precursor conceptual del EU AI Act.

### Recursos internos del vault

- [[ai-governance]] — Marco regulatorio ampliado
- [[copilot-studio]] — Herramienta corporativa principal
- [[agente-ia]] — Conceptos base
- [[metricas-ia]] — Cómo medir la eficacia (Charla 13)
- [[guion-charla-14]] — Guion de la charla
