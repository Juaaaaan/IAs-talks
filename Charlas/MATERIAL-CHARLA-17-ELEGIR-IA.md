---
type: Material
title: "Material Charla 17 — Elegir bien la IA: herramienta, modelo y modo de trabajo"
description: "Guía exhaustiva de la Charla 17 para consulta posterior. Desarrolla las cuatro capas de decisión (qué IA, qué modelo, en qué modo de trabajo, cuánto verificar) con explicaciones a fondo, ejemplos, tablas de referencia y enlaces externos. Pensada para leer con calma, no como resumen rápido."
tags: [material, charla-17, eleccion-herramienta, eleccion-modelo, modos-de-trabajo, proveedores, verificacion, alucinaciones]
related: [model-routing, modelos-abiertos-vs-cerrados, reasoning-models, mcp-ecosystem, memory, rag, wiki-llm, ai-governance, alucinaciones]
charla: "Charla 17"
estado: "✅ Publicado"
timestamp: "2026-08-24"
---

# Material Charla 17 — Elegir bien la IA: herramienta, modelo y modo de trabajo

> Esta guía recoge y amplía lo que vimos en la charla. No es un resumen: es un documento para consultar cuando tengas una duda concreta ("¿qué IA uso para esto?", "¿por qué me ha inventado un dato?"). Léela por bloques, no del tirón.

---

## La idea en una frase

**"Usar la IA" no es una acción, son cuatro decisiones.** La mayoría abrimos "la de siempre", escribimos y esperamos a ver qué sale. Cuando en cambio tomamos cuatro decisiones a conciencia —qué herramienta, qué modelo, en qué modo de trabajo y cuánto verificar— la misma IA nos da mucho más. Este documento desarrolla esas cuatro capas.

La brújula, que es lo único que hay que llevarse a la cabeza:

| # | Capa | La pregunta | Qué decide |
|---|---|---|---|
| 1 | Herramienta | ¿Qué IA abro? | ¿Código? ¿Datos de empresa? ¿General? |
| 2 | Modelo | ¿Qué modelo elijo? | Rápido o razonador — y de qué proveedor |
| 3 | Modo de trabajo | ¿Cómo la pongo a trabajar? | Preguntar / investigar / recordar / actuar |
| 4 | Confianza | ¿Cuánto me la juego? | Cuánto verifico |

---

## Capa 1 — ¿Qué IA abro? (la herramienta)

### El lío de los nombres

La confusión número uno no es culpa de nadie: **"Copilot" no es una cosa, son tres**, y comparten apellido pero son productos distintos.

- **Microsoft Copilot** (a secas, la web o la app): es el chat general de Microsoft, equivalente a ChatGPT. Sirve para consultas generales y tareas personales. No accede a los datos de tu empresa.
- **Microsoft 365 Copilot** ("Copilot 365"): es la IA integrada **dentro** de Word, Excel, Outlook, Teams y PowerPoint. Es la única de la lista que **ve los documentos, correos y reuniones de tu organización** (a través de Microsoft Graph). Por eso puede resumir *tus* reuniones de Teams o redactar en Word sobre *tus* datos.
- **GitHub Copilot**: es el asistente para **programar**, dentro del editor de código. Solo tiene sentido si escribes código.

Y un cuarto nombre que se cuela por parecido: **GitHub Desktop**, que **no es IA** — es una aplicación para gestionar repositorios de código (control de versiones) con ratón. Nada que ver.

Fuera del mundo Microsoft, la otra herramienta que usamos mucho es **Claude** (de Anthropic, en claude.ai): un chat general especialmente fuerte redactando, razonando y analizando documentos largos que le subas.

### El criterio (la regla de 3 segundos)

No hay que memorizar catálogos. Ante una tarea, tres preguntas y la herramienta cae sola:

1. **¿Es para programar?** → GitHub Copilot (o Claude Code).
2. **¿Es sobre mis correos, documentos o reuniones de la empresa?** → Microsoft 365 Copilot (el único que ve tu contenido interno).
3. **¿Es algo general** —redactar, resumir algo que le pego, analizar un PDF, generar ideas—**?** → Microsoft Copilot o Claude.

### Por qué el contexto lo cambia todo

El punto clave de esta capa: una IA genérica **sabe mucho del mundo y nada de tu empresa**. Si tu pregunta depende de un documento tuyo (un convenio, un pliego, una política), tienes dos opciones: usar una herramienta que ya tenga ese contexto (365 Copilot) o **dársela tú** subiendo el documento. Si no haces ninguna de las dos, la IA rellenará el hueco con lo que le parezca — y ahí empiezan los inventos. Esto enlaza con el concepto de [[wiki-llm]] y [[rag]] que vimos en charlas anteriores.

**Enlaces útiles:**
- Comparativa enterprise de las cuatro grandes: https://intuitionlabs.ai/articles/claude-vs-chatgpt-vs-copilot-vs-gemini-enterprise-comparison
- Novedades de Microsoft Copilot Studio (oficial): https://learn.microsoft.com/en-us/microsoft-copilot-studio/whats-new

---

## Capa 2 — ¿Qué modelo elijo? (potencia y proveedor)

Dentro de casi todas las herramientas no hay **un** modelo: hay un selector. Y ahí se toman dos decisiones.

### 2a — El dial: rápido vs razonador

La buena noticia es que no hay que aprenderse cincuenta nombres. Toda la industria ha convergido en lo mismo: dentro de cada IA eliges, en el fondo, entre dos modos.

- **Modo rápido:** para tareas simples —redactar, resumir corto, reformular, preguntas directas—. Responde al instante. (En ChatGPT, "Instant"; en Claude, la gama ligera.)
- **Modo razonador** ("que piensa"): para tareas complejas —analizar, comparar, decidir, varios pasos, coste alto—. Tarda más, pero razona de verdad. (En ChatGPT, "Thinking"; en Claude, la gama potente.)

**El error que casi todos cometemos sin saberlo:** el modo rápido viene por defecto, así que lo usamos para todo, también para lo complejo, y luego decimos "la IA razona fatal". No es la IA: le pedimos que corriera cuando necesitábamos que pensara. Cambiar de modo según la tarea es, probablemente, el gesto de mayor impacto de toda la charla. Amplía en [[model-routing]] y [[reasoning-models]].

### 2b — El mapa de proveedores

Hoy no hay dos o tres IAs: hay muchas. No hace falta aprendérselas, pero sí saber que **existe elección** y que se agrupan en dos grandes familias. (Detalle completo en el concepto [[modelos-abiertos-vs-cerrados]].)

**Familia 1 — Cerrados de pago (frontera occidental).** Fiables, fáciles, pensados para empresa. Primera opción para la mayoría:
- **OpenAI** (ChatGPT / GPT) — el más conocido, todoterreno.
- **Anthropic** (Claude) — fuerte en escritura, código y razonamiento largo.
- **Google** (Gemini) — contexto larguísimo, multimodal, integrado con Google.
- **xAI** (Grok) — el de X.

**Familia 2 — Abiertos (open-weight, muchos chinos).** Potentes, mucho más baratos, y descargables para ejecutar en tu propia máquina:
- **DeepSeek, Qwen** (Alibaba), **Kimi** (Moonshot), **GLM** (Z.ai) — capacidad de frontera a una fracción del precio.
- **Mistral** — la opción europea.

**El aviso importante para la empresa (gobernanza + seguridad):** "potente y barato" no basta en un entorno corporativo. Muchas APIs de modelos chinos **corren desde China**, lo que plantea una cuestión de **residencia de datos**: dónde acaban los datos que envías. Para cargas reguladas eso es un factor de decisión, no un detalle. Regla de oro: **en el trabajo, solo lo aprobado por la empresa**; en casa, experimenta lo que quieras. Enlaza con [[ai-governance]].

**Enlaces útiles:**
- Índice de capacidad y precio (independiente): https://artificialanalysis.ai/
- Ranking por caso de uso, actualizado mensualmente: https://felloai.com/best-ai-models/

---

## Capa 3 — ¿Cómo la pongo a trabajar? (el modo de trabajo)

Casi todos usamos la IA de **una sola forma**: preguntar y que responda. Es como usar un móvil solo para llamar. La IA de 2026 tiene cuatro modos de trabajo, y conocer los otros tres es donde está el salto de productividad.

- **Preguntar** — pregunta → respuesta. Perfecto para lo rápido y puntual.
- **Investigar a fondo** ("deep research") — le das un tema y, en vez de responder en 3 segundos, dedica varios minutos a rastrear muchas fuentes y te devuelve un informe con referencias. Para cuando necesitas profundidad, no una respuesta rápida.
- **Recordar** (proyectos, memoria, instrucciones persistentes) — la IA que te conoce. Le das tu contexto una vez (tu rol, tu proyecto, tu estilo) y no empiezas de cero en cada conversación. Es la idea de [[memory]] y [[wiki-llm]].
- **Actuar** (conectores, agentes) — la IA que entra en tus aplicaciones (correo, calendario, documentos) y **hace** cosas, no solo habla. Es la versión de bolsillo de los MCPs ([[mcp-ecosystem]]).

**La conexión con toda la serie:** "recordar" y "actuar" son, en el fondo, el *arnés completo* que llevamos meses viendo (memoria, instrucciones, MCPs), pero explicado para cualquiera. No era cosa de programadores: son modos que cualquiera puede usar hoy.

**Enlaces útiles:**
- Comparativa de agentes de trabajo (ChatGPT Work, Claude Cowork, Gemini Spark, Copilot): https://felloai.com/best-ai-agents/
- Changelog de novedades de producto (ChatGPT, Gemini, Copilot, Perplexity): https://reconn-ai.com/llm-changelog.php

---

## Capa 4 — ¿Cuánto me la juego? (verificación)

Ya elegiste herramienta, modelo y modo. Queda la pregunta que decide cuánto verificar. Esto ya lo tratamos en la serie, así que aquí va la versión práctica. Concepto completo en [[alucinaciones]].

### La regla del coste del error

Verificarlo todo es imposible y agotador. Se calibra: cuanto más caro el error, más verificas. Y cuanto más caro, más conviene subir al modo razonador de la capa 2.

| Coste del error | Ejemplos | Cuánto verificas |
|---|---|---|
| **Bajo** | Un borrador que reescribirás, ideas, un correo interno | Lectura rápida |
| **Medio** | Un acta, un resumen que reenvías, algo que va a otras personas | Contrastas los datos clave contra la fuente |
| **Alto** | Una cifra en una oferta, un dato legal, algo a cliente o dirección | Verificación total + revisión humana |

### Zonas rojas (desconfiar siempre)

Cifras y datos exactos · fechas y nombres propios · citas, referencias y normativa · cualquier cosa muy reciente o muy de nicho. Y el detalle que baja la guardia de todos: **la IA no se equivoca tartamudeando; se equivoca con redacción impecable y tono de experta**. Lo segura que suena no dice nada de si es verdad.

### Técnicas para el día a día

1. **Pedir la fuente:** *"cita la frase exacta", "¿en qué página lo pone?"*. Si no puede señalarla, desconfía.
2. **Darle el contexto tú** (la capa 1): una IA atada a tu documento inventa mucho menos.
3. **Contrastar lo crítico** contra el original — treinta segundos que evitan un disgusto.
4. **Saber cuándo un humano tiene que revisar sí o sí:** cliente, consecuencia legal o económica, dirección.

**Enlace útil:**
- Alucinaciones (introducción general): https://en.wikipedia.org/wiki/Hallucination_(artificial_intelligence)

---

## Chuleta rápida por rol

| Rol | Lo esencial que te llevas |
|---|---|
| **HR / funcional** | Para datos de empresa, quién tiene tu contexto (365 Copilot o subir el PDF). Prueba el modo "investigar" para preparar temas a fondo |
| **Comercial** | Coste del error alto por defecto: todo lo que va a cliente se verifica. Sube el dial para propuestas complejas |
| **Management** | Las cuatro capas son enseñables; "recordar" y "actuar" es donde el equipo gana tiempo de verdad |
| **Developer** | Herramienta especializada + modelo potente + modos "actuar" (agentes). Terreno natural |

---

## Anexo — Tabla de modelos concretos (agosto 2026)

> ⚠️ Los nombres cambian **cada semana**. Esta tabla es una foto de hoy; lo que no caduca es el criterio "familia + para qué + dónde acaban mis datos".

| Modelo | Proveedor | Familia | Bueno para |
|---|---|---|---|
| GPT-5.6 Sol | OpenAI 🇺🇸 | Cerrado | Razonamiento y tareas complejas (el potente) |
| GPT-5.6 Luna | OpenAI 🇺🇸 | Cerrado | Volumen y velocidad (el rápido y barato) |
| Claude Opus 4.8 | Anthropic 🇺🇸 | Cerrado | Análisis a fondo, código, escritura larga |
| Claude Sonnet 5 | Anthropic 🇺🇸 | Cerrado | El equilibrado del día a día |
| Claude Haiku 4.5 | Anthropic 🇺🇸 | Cerrado | Respuestas rápidas y simples |
| Gemini 3 Pro | Google 🇺🇸 | Cerrado | Contexto larguísimo, multimodal, ecosistema Google |
| Grok 4.6 | xAI 🇺🇸 | Cerrado | Generalista, integrado con X |
| DeepSeek V4 | DeepSeek 🇨🇳 | Abierto | Razonamiento barato; el que sacudió el mercado |
| Kimi K3 | Moonshot 🇨🇳 | Abierto | Todoterreno abierto muy potente |
| Qwen 3 Max | Alibaba 🇨🇳 | Abierto | Código y agentes; variantes que corren en un portátil |
| GLM-5.2 | Z.ai 🇨🇳 | Abierto | Código y agentes de largo recorrido |
| Mistral Large 3 | Mistral 🇪🇺 | Abierto | La opción europea (mejor encaje de residencia de datos) |

> ⚠️ Los 🇨🇳 tienen su API corriendo desde China: para cargas de empresa reguladas, solo lo aprobado internamente.

---

## Para seguir tirando del hilo (conceptos del vault)

[[model-routing]] · [[modelos-abiertos-vs-cerrados]] · [[reasoning-models]] · [[mcp-ecosystem]] · [[memory]] · [[rag]] · [[wiki-llm]] · [[ai-governance]] · [[alucinaciones]]
