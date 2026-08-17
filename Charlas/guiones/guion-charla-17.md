---
type: Guión
title: "Guión Charla 17 — Elegir bien la IA: herramienta, modelo y modo de trabajo"
description: "Charla transversal y accesible, de vuelta al público general tras el bloque técnico (14-15-16). Método de decisión en cuatro capas que no caduca: qué IA abrir (herramienta), qué modelo elegir (el dial rápido/razonador + el mapa de proveedores), en qué modo de trabajo ponerla (preguntar/investigar/recordar/actuar) y cuánto verificar. Dirigida a gente que ya usa IA pero sin método. Teoría + capturas comparativas (sin demo en vivo). ~50 min + preguntas."
tags: [guion, charla-17, model-routing, eleccion-herramienta, eleccion-modelo, modos-de-trabajo, proveedores, verificacion, transversal]
related: [model-routing, reasoning-models, mcp-ecosystem, memory, rag, wiki-llm, ai-governance]
charla: "Charla 17"
estado: "🔲 Borrador — listo para revisión y ensayo"
timestamp: "2026-08-17"
---

# Guión Charla 17 — Elegir bien la IA: herramienta, modelo y modo de trabajo

> ⚠️ **Nota de alcance:** charla **transversal y accesible**, cambio de registro tras tres charlas densas (14 Gobernanza, 15 Seguridad, 16 SDD con herramientas — técnica). Objetivo: **recuperar al público general**. Nada de instalar, nada de código.
>
> **Perfil real del público (clave del diseño):** no son recién llegados. **Ya usan IA, pero sin método** — la usan a veces, abren "la de siempre" por inercia, se quedan en el modo por defecto, y usan solo una fracción de lo que la IA ya sabe hacer. El hueco no es *enseñarles que existe*: es llevarlos de *usuario ingenuo* a *usuario con criterio*.
>
> **Foco:** **elegir bien**. Una decisión que casi nadie toma a conciencia y que tiene **cuatro capas**: qué IA, qué modelo, en qué modo de trabajo, y cuánto verificar.
>
> **Formato:** **teoría + capturas comparativas**. Sin demo en vivo — cero riesgo de wifi/licencias/atascos. Las comparativas van como pantallazos preparados en las diapositivas.
>
> **Nota de enfoque (crítica):** NO es un comparador de productos ni un catálogo de modelos. Los nombres cambian cada semana. Se enseñan **familias y criterios que no envejecen**; los nombres concretos van solo en las slides con aviso de caducidad.
>
> **Nota sobre alucinaciones:** ya tratado en la serie. Aquí entra aplicado (Bloque 4) como un factor de la decisión, no como explicación desde cero.

---

## Estructura de tiempos

| Bloque    | Contenido                                                             | Tiempo   |
| --------- | -------------------------------------------------------------------- | -------- |
| Apertura  | Gancho + la brújula de 4 capas                                        | 4 min    |
| Bloque 1  | Capa 1 — ¿Qué IA abro? (herramienta)                                  | 9 min    |
| Bloque 2  | Capa 2 — ¿Qué modelo elijo? (el dial + el mapa de proveedores)        | 13 min   |
| Bloque 3  | Capa 3 — ¿En qué modo de trabajo? (preguntar/investigar/recordar/actuar) | 9 min |
| Bloque 4  | Capa 4 — ¿Cuánto me la juego? (verificación)                         | 7 min    |
| Bloque 5  | Qué se lleva cada rol                                                 | 3 min    |
| Cierre    | El kit del lunes + conexión con el arnés y la serie                  | 5 min    |
| Preguntas | Turno abierto                                                         | 8-12 min |

**Total estimado:** ~50 min + preguntas

---

## Apertura — ¿Cómo eliges qué IA usar? — 4 min

> _"Después de tres charlas intensas — gobernanza, seguridad y la de la semana pasada, puro código — hoy bajamos a tierra. Sin instalar nada, sin programar. Para todos."_
>
> _"Y hoy no vengo a descubriros la IA. Ya la usáis. Vengo con algo más incómodo: creo que muchos la usáis regular sin saberlo. Dos preguntas, con manos de verdad. Una: ¿cuántos habéis usado una IA esta semana para el trabajo? Dos, la buena: ¿cuántos ELEGISTEIS cuál, en qué modelo, y en qué modo? ¿O abristeis la de siempre y a ver qué salía?"_
>
> _"Casi nadie elige. Y hoy os voy a enseñar que detrás de 'usar la IA' hay cuatro decisiones que casi nunca tomáis a conciencia. Cuando las tomáis, la misma IA os da el doble. Y os llevaréis un método que no caduca aunque los nombres cambien cada mes — que cambian."_

**La brújula — mostrarla ya, es el mapa de toda la charla (se repite en el cierre):**

| # | Capa | La pregunta | Qué decide |
|---|---|---|---|
| **1** | Herramienta | **¿Qué IA abro?** | ¿Código? ¿Datos de empresa? ¿General? |
| **2** | Modelo | **¿Qué modelo elijo?** | Rápido o razonador — y de qué proveedor |
| **3** | Modo de trabajo | **¿Cómo la pongo a trabajar?** | Preguntar / investigar / recordar / actuar |
| **4** | Confianza | **¿Cuánto me la juego?** | Cuánto verifico |

**Frase que debe quedar:**

> _"'Usar la IA' no es una cosa. Son cuatro decisiones. Y la calidad de lo que os devuelve depende de acertarlas."_

---

## Bloque 1 — Capa 1: ¿Qué IA abro? — 9 min

> _"Primera capa. Y empieza con una confusión que tiene medio mundo: la palabra 'Copilot' no señala una cosa. Señala tres cosas distintas con el mismo apellido."_

### El lío de los nombres

- **Microsoft Copilot** (a secas, web/app) → chat general, tipo ChatGPT. Consultas generales.
- **Microsoft 365 Copilot** ("Copilot 365") → la IA DENTRO de Word/Excel/Outlook/Teams. La única que **ve los documentos y correos de tu empresa**.
- **GitHub Copilot** → para programar, dentro del editor. Solo devs.
- **Claude** (claude.ai) → chat general, fuerte redactando y analizando documentos que le subes.

> _"Y un cuarto que puede sonaros: GitHub Desktop. Ese ni es IA — es una app para gestionar código. Lo digo para que no os líe."_

### El criterio — la regla de 3 segundos

1. **¿Es para programar?** → GitHub Copilot (o Claude Code).
2. **¿Es sobre mis correos / documentos / reuniones de la empresa?** → Microsoft 365 Copilot (el único que ve tu contenido interno).
3. **¿Es algo general — redactar, resumir algo que le pego, analizar un PDF —?** → Microsoft Copilot o Claude.

### En pantalla — capturas comparativas (misma pregunta, tres formas)

> ⚠️ **Capturas a preparar.** Misma pregunta cuya respuesta esté en un documento de empresa (ej: *"¿cuántos días de permiso por mudanza me corresponden?"*):

1. **Chat general, sin darle nada** → responde algo que suena bien y **se lo inventa**.
   > _"Suena convincente. Y es mentira. No conoce vuestro convenio."_
2. **La misma IA, con el documento cargado** → PDF + *"cítame la página"*. Responde bien y cita.
   > _"Misma IA, misma pregunta. Solo cambió que le di el contexto."_
3. **365 Copilot, que ya ve los documentos de empresa** → responde sin subir nada.
   > _"Si tu empresa la tiene conectada, ni subes nada."_

> _"Las tres 'funcionan', pero cada una es para una situación. Y esto conecta con el Wiki LLM que llevamos toda la serie viendo: darle a la IA vuestro conocimiento para que no invente."_

**Frase que debe quedar:**

> _"No hay una IA mejor. Hay una correcta para cada tarea. Para tus datos, la clave es quién tiene tu contexto."_

---

## Bloque 2 — Capa 2: ¿Qué modelo elijo? — 13 min

> _"Segunda capa, y esta casi nadie la conoce. Dentro de cada herramienta no hay UN modelo: hay un selector. Y hay dos decisiones dentro: qué potencia, y de qué fabricante."_

### 2a — El dial: rápido vs razonador

> _"Buena noticia: no tenéis que aprenderos cincuenta nombres. La industria entera ha convergido en lo mismo. Dentro de cada IA, elegís entre dos cosas. Un dial."_

- **Modo RÁPIDO** → tareas simples: redactar, resumir corto, reformular, preguntas directas. Instantáneo.
- **Modo RAZONADOR** ("que piensa") → tareas complejas: analizar, comparar, varios pasos, una decisión, coste alto. Tarda, pero razona.

> _"En ChatGPT eso es 'Instant' contra 'Thinking'. En Claude, los modelos ligeros contra el más potente. Los nombres cambian; el dial no."_

**El error de método (el "ajá"):**
> _"El modo rápido viene por defecto. Así que la gente lo usa PARA TODO, también para lo complejo, y luego dice 'la IA razona fatal'. No. Le pediste que corriera cuando necesitabas que pensara. Usaste el dial mal."_

**En pantalla — capturas:** una tarea compleja (analizar un contrato, comparar dos opciones) en **modo rápido** (superficial) vs **razonador** (estructurado, con matices).
> _"Misma IA, misma pregunta. Solo cambié el dial. Esa es la diferencia entre usar IA y usarla con método."_

### 2b — El mapa de proveedores (pinceladas)

> _"Y la otra decisión: hoy no hay dos o tres IAs. Hay un montón, y conviene saber quién es quién. No para que os los aprendáis, sino para que sepáis que existe elección. Dos grandes familias."_

**Familia 1 — Los cerrados de pago (frontera occidental).** Fiables, fáciles, pensados para empresa. Primera opción para la mayoría:
- **OpenAI** (ChatGPT / GPT-5.6, en tres niveles: **Sol** el potente, **Terra** el equilibrado, **Luna** el rápido) → el más conocido, todoterreno.
- **Anthropic** (Claude, en tres niveles: **Opus 4.8** el potente, **Sonnet 5** el equilibrado, **Haiku 4.5** el rápido) → fuerte en escritura y código, razonamiento largo.
- **Google** (**Gemini 3 Pro**) → contexto larguísimo, multimodal, integrado con Google.
- **xAI** (**Grok 4.6**) → el de X.

**Familia 2 — Los abiertos (open-weight, muchos chinos).** Potentes, mucho más baratos, te los puedes descargar y ejecutar en tu propia máquina:
- **DeepSeek V4**, **Qwen 3 Max** (Alibaba), **Kimi K3** (Moonshot), **GLM-5.2** (Z.ai) → capacidad de frontera a una fracción del precio.
- **Mistral Large 3** → la opción europea.

> _"El titular de 2026: estos modelos abiertos, muchos chinos, han alcanzado a los grandes en muchas tareas, y cuestan una fracción. Han sacudido el mercado entero."_

**El aviso que conecta con la serie (gobernanza + seguridad):**
> _"Pero atención, y aquí enlazo con las charlas de gobernanza y seguridad. 'Potente y barato' no basta en una empresa. Las APIs de muchos de estos modelos chinos corren desde China: hay una cuestión de dónde acaban vuestros datos. Para una empresa regulada como la nuestra, eso es un factor de decisión, no un detalle. Regla de oro: en el trabajo, usad solo lo aprobado por la empresa. En casa, experimentad lo que queráis."_

**Frase que debe quedar:**

> _"No os aprendáis los nombres, que la semana que viene son otros. Aprendeos que hay elección — y que en la empresa, la elección la marca también dónde acaban tus datos."_

---

## Bloque 3 — Capa 3: ¿Cómo la pongo a trabajar? — 9 min

> _"Tercera capa, y esta es la que más os va a sorprender. Porque casi todos usáis la IA de UNA sola forma — preguntar y que responda — y eso es como usar el 20% de un móvil solo para llamar. La IA de 2026 tiene cuatro modos de trabajo. Y solo conocéis uno."_

- **PREGUNTAR** (lo que ya hacéis): pregunta → respuesta. Perfecto para lo rápido.
- **INVESTIGAR A FONDO** ("deep research"): le das un tema y, en vez de contestar en 3 segundos, se pasa varios minutos rastreando muchas fuentes y te devuelve un informe con referencias. Para cuando necesitas profundidad, no una respuesta rápida.
- **RECORDAR** (proyectos / memoria / instrucciones persistentes): la IA que te conoce. Le das tu contexto una vez — tu rol, tu proyecto, tu estilo — y no empiezas de cero cada conversación.
- **ACTUAR** (conectores / agentes): la IA que entra en tus apps — tu correo, tu calendario, tus documentos — y HACE cosas, no solo habla.

> _"Y aquí cierro el círculo de toda la serie. ¿Os suena 'recordar'? Es el Wiki LLM, la memoria, las instrucciones persistentes — las charlas 8 y 11. ¿Os suena 'actuar'? Son los MCPs, la charla 7. Todo eso que sonaba técnico y de programadores… es esto. Los cuatro modos de trabajo que cualquiera puede usar hoy."_

**En pantalla — capturas:** el mismo tema tratado como *pregunta rápida* (respuesta corta) vs *investigar a fondo* (informe con fuentes).
> _"Mirad la diferencia. No es otra IA. Es la misma, puesta a trabajar de otra forma."_

**Frase que debe quedar:**

> _"Preguntar es el modo fácil, pero es solo uno de cuatro. Investigar, recordar y actuar es donde está el 80% que os estáis perdiendo."_

---

## Bloque 4 — Capa 4: ¿Cuánto me la juego? — 7 min

> _"Última capa. Habéis elegido herramienta, modelo y modo. Queda la pregunta que decide cuánto verificar: ¿cuánto me la juego? Esto ya lo hemos hablado en la serie, así que os doy la versión práctica."_

### La regla del coste del error

> _"Verificarlo todo es imposible. Calibrad: cuanto más caro el error, más verificas. Y cuanto más caro, más te empuja al modo razonador de la capa 2. Todo conecta."_

| Coste del error | Ejemplos | Cuánto verificas |
|---|---|---|
| **Bajo** | Borrador que reescribirás, ideas, correo interno | Lectura rápida |
| **Medio** | Un acta, un resumen que reenvías | Contrastas datos clave contra la fuente |
| **Alto** | Cifra en una oferta, dato legal, algo a cliente o dirección | Verificación total + revisión humana |

### Zonas rojas (desconfiar siempre)

Cifras y datos exactos · fechas y nombres propios · citas, referencias, normativa · lo muy reciente o de nicho.

> _"Y el detalle que baja la guardia de todos: la IA no se equivoca tartamudeando. Se equivoca con redacción impecable y tono de experta. Lo segura que suena no dice NADA de si es verdad."_

### Técnicas para mañana

1. **Pedir la fuente:** *"cita la frase exacta"*. Si no puede, desconfía.
2. **Darle el contexto tú** (la capa 1): atada a tu documento, inventa mucho menos.
3. **Contrastar lo crítico** contra el original.
4. **Saber cuándo un humano revisa sí o sí:** cliente, consecuencia legal o económica, dirección.

**Frase que debe quedar:**

> _"La IA se equivoca con muy buena letra. Tu trabajo no es desconfiar de todo — es saber cuánto te juegas, y verificar en consecuencia."_

---

## Bloque 5 — Qué se lleva cada rol — 3 min

| Rol | Qué te llevas |
|---|---|
| **HR / funcional** | Para datos de empresa, quién tiene tu contexto (365 Copilot o subir el PDF). Prueba el modo "investigar" para preparar temas a fondo |
| **Comercial** | Coste del error alto por defecto (todo lo que va a cliente se verifica). Sube el dial para propuestas complejas |
| **Management** | Las cuatro capas son enseñables. Y "recordar/actuar" es donde tu equipo puede ganar tiempo de verdad. Pasadlo |
| **Developer** | Herramienta especializada + modelo potente + modos "actuar" (agentes). Es vuestro terreno natural |

**Frase que debe quedar:**

> _"Programéis o no, cada día tomáis estas cuatro decisiones. La única pregunta es si las tomáis por inercia o con criterio."_

---

## Cierre — El kit del lunes — 5 min

> _"Recojo en tres ideas."_
>
> _"Primera: 'usar la IA' son cuatro decisiones, no una. Qué IA, qué modelo, qué modo de trabajo, cuánto verifico. La brújula —enseñarla otra vez—."_
>
> _"Segunda: no os aprendáis nombres, que caducan. Aprendeos los criterios: ¿código, datos de empresa o general? ¿rápido o razonador? ¿pregunto o pongo a investigar/recordar/actuar? ¿cuánto me la juego?"_
>
> _"Tercera: la seguridad con la que responde no mide si tiene razón. Verificad según lo que os jugáis. Y en la empresa, usad solo lo aprobado — que ahí no solo cuenta lo bueno que es el modelo, sino dónde acaban vuestros datos."_
>
> _"Y el círculo de la serie: llevamos meses viendo el arnés completo — especificaciones, comportamiento, herramientas, memoria. Hoy habéis visto que ese arnés no era cosa de programadores. Recordar y actuar es algo que cualquiera de vosotros puede usar mañana. El arnés era esto, para todos."_

**Frase final:**

> _"La próxima vez, no abráis la de siempre en automático ni os quedéis en el modo por defecto. Cuatro preguntas de treinta segundos. Esa es la diferencia entre usar la IA… y usarla bien."_

---

## Anexo — Las cuatro capas en detalle (por si preguntan)

> ⚠️ **Munición para el turno de preguntas / slides de reserva.** El método no caduca; los nombres sí. Sin precios (dependen de licencia corporativa).

### Capa 1 — Herramienta

| Herramienta | Qué es | Cuándo | Ve tus datos de empresa |
|---|---|---|---|
| **Microsoft Copilot** (web) | Chat general de Microsoft | Consultas generales | No |
| **Microsoft 365 Copilot** | IA en Word/Excel/Outlook/Teams | Tareas sobre tu contenido (vía Microsoft Graph) | **Sí** (el único) |
| **GitHub Copilot** | Código en el editor | Solo programar | — |
| **Claude** (claude.ai) | Chat general, fuerte en redacción/análisis | Redactar, analizar documentos que subes, razonar | Solo lo que subas |
| **Claude Code** | Agente de código en terminal | Programar autónomo | — |

### Capa 2 — Modelo: el dial

| Tu tarea es… | Modo | En ChatGPT (hoy) | En Claude (hoy) |
|---|---|---|---|
| **Simple** (redactar, resumir corto) | **Rápido** | Instant | Gama ligera (Haiku/Sonnet) |
| **Compleja** (analizar, decidir, coste alto) | **Razonador** | Thinking | Gama potente (Opus) |

### Capa 2 — Modelo: el mapa de proveedores (agosto 2026)

| Familia | Proveedores | Destaca en | Nota para empresa |
|---|---|---|---|
| **Cerrados occidentales** | OpenAI (GPT), Anthropic (Claude), Google (Gemini), xAI (Grok) | Fiabilidad, facilidad, soporte enterprise | Primera opción; verificar licencia corporativa |
| **Abiertos / open-weight** | DeepSeek, Qwen, Kimi, GLM (chinos); Mistral (EU) | Capacidad de frontera a bajo coste; ejecutables en tu propia máquina | ⚠️ Residencia de datos: muchas APIs corren desde China. Cargas reguladas → solo lo aprobado |

> ⚠️ Nombres a agosto 2026 (GPT-5.6, Gemini 3.x, DeepSeek V4, Kimi K3, Qwen 3.x…). **Cambian cada semana.** El criterio "familia + para qué + dónde acaban mis datos" no.

### Capa 2 — Modelos concretos (agosto 2026, cambian rápido)

| Modelo | Proveedor | Familia | Bueno para |
|---|---|---|---|
| **GPT-5.6 Sol** | OpenAI 🇺🇸 | Cerrado | Razonamiento y tareas complejas (el potente) |
| **GPT-5.6 Luna** | OpenAI 🇺🇸 | Cerrado | Volumen y velocidad (el rápido y barato) |
| **Claude Opus 4.8** | Anthropic 🇺🇸 | Cerrado | Análisis a fondo, código, escritura larga (el potente) |
| **Claude Sonnet 5** | Anthropic 🇺🇸 | Cerrado | El equilibrado del día a día |
| **Claude Haiku 4.5** | Anthropic 🇺🇸 | Cerrado | Respuestas rápidas y simples |
| **Gemini 3 Pro** | Google 🇺🇸 | Cerrado | Contexto larguísimo, multimodal, ecosistema Google |
| **Grok 4.6** | xAI 🇺🇸 | Cerrado | Generalista, integrado con X |
| **DeepSeek V4** | DeepSeek 🇨🇳 | Abierto | Razonamiento barato; el que sacudió el mercado |
| **Kimi K3** | Moonshot 🇨🇳 | Abierto | Todoterreno abierto más potente ahora mismo |
| **Qwen 3 Max** | Alibaba 🇨🇳 | Abierto | Código y agentes; variantes que corren en un portátil |
| **GLM-5.2** | Z.ai 🇨🇳 | Abierto | Código y agentes de largo recorrido |
| **Mistral Large 3** | Mistral 🇪🇺 | Abierto | La opción europea (mejor encaje de residencia de datos) |

> ⚠️ **Aviso de residencia de datos:** los 🇨🇳 tienen su API corriendo desde China. Potentes y baratos, pero para cargas de empresa reguladas → solo lo aprobado internamente. En la empresa priman los 🇺🇸/🇪🇺 aprobados.

### Capa 3 — Modos de trabajo

| Modo | Qué hace | Concepto de la serie |
|---|---|---|
| **Preguntar** | Pregunta → respuesta | (lo básico) |
| **Investigar** | Rastrea muchas fuentes → informe con referencias | eval / research |
| **Recordar** | Proyectos, memoria, instrucciones persistentes | Wiki LLM, memoria (charlas 8, 11) |
| **Actuar** | Conectores/agentes que entran en tus apps | MCPs (charla 7) |

---

## Checklist antes del miércoles

- [ ] **Capturas Bloque 1** — misma pregunta: sin contexto → inventa / con documento → cita / 365 Copilot → ya lo tiene. ⚠️ La 3ª requiere 365 Copilot licenciado; si no, quitarla
- [ ] **Capturas Bloque 2** — tarea compleja en modo rápido vs razonador
- [ ] **Capturas Bloque 3** — mismo tema como pregunta rápida vs "investigar a fondo" (informe con fuentes)
- [ ] **Documento de ejemplo** — genérico corporativo (política, pliego, manual), no RCA
- [ ] **Slide de la brújula (4 capas)** — se repite en apertura y cierre; clarísima
- [ ] **Slide "lío de los nombres"** (3 Copilot + Claude + GitHub Desktop)
- [ ] **Slide del dial** (rápido vs razonador)
- [ ] **Slide del mapa de proveedores** (2 familias) — con el aviso de residencia de datos bien visible
- [ ] **Slide de los 4 modos de trabajo** — con la conexión al arnés
- [ ] **Anexo (tablas) como slides de reserva** para preguntas
- [ ] **Confirmar referencia** de la(s) charla(s) donde se trató "fiarnos de la IA"
- [ ] **Verificar** que los nombres de modelos del anexo siguen vigentes el día de la charla (cambian rápido)
- [ ] **Mensaje a compañeros** avisando de que es transversal/accesible

### Si hace falta recortar a ~45 min

1. Reducir el mapa de proveedores (Bloque 2b) a las dos familias sin desglosar proveedores uno a uno (~-3 min)
2. Comprimir zonas rojas del Bloque 4 en una slide (~-2 min)
3. Bloque 3: mencionar los 4 modos pero desarrollar solo "investigar" y "actuar" (~-2 min)
4. **Mantener intactos:** la brújula, el dial (Bloque 2a), los 4 modos de trabajo (Bloque 3 — es la novedad que da profundidad) y la regla del coste del error

---

## Nota de mantenimiento del vault (no es contenido de la charla)

Esta charla desarrolla a fondo varios conceptos ya en la biblioteca: **`model-routing`** (capa 2), **`mcp-ecosystem`** y **`memory`** (capa 3), **`ai-governance`** (el aviso de residencia de datos). La capa 1 (elección de herramienta) y un concepto de **`modelos-abiertos-vs-cerrados`** no tienen nota propia y podrían merecerla. Sigue faltando **`alucinaciones`** en nivel-1. **Pendiente de tu OK** — no creo nada sin que me lo digas.
