---
type: Material
title: "Material Charla 19 — De responder a actuar: varios agentes que colaboran"
description: "Material post-charla 19 (parte 1). Del agente que responde (charla 13) al equipo de agentes que actúa: orquestador + agentes especialistas + una herramienta que escribe en Excel, con checkpoint humano. Caso: análisis de un pliego (RFP). Incluye tutorial completo de construcción. Audiencia no técnica."
tags: [material, charla-19, copilot-studio, agentes, multiagente, orquestacion, power-automate, rfp, checkpoint-humano, tutorial, nivel-4]
related: [charla-13-copilot-studio-metricas, charla-18-como-piensa-la-ia, copilot-studio, agente-ia, agentic-workflows, power-automate]
charla: 19
estado: publicado
timestamp: "2026-09-02"
---

# Material Charla 19 — De responder a actuar: varios agentes que colaboran

---

## Qué vimos en la charla

### De dónde venimos

En la **charla 13** montamos un agente en Copilot Studio. Le conectamos el handbook de la empresa y respondía preguntas de gente nueva. Aprendimos una distinción clave: un **chatbot** sigue un guión predefinido y se rompe cuando tu pregunta no encaja; un **agente** razona, se adapta y —lo más importante— reconoce lo que no sabe en vez de inventárselo.

Pero aquel agente **respondía**. Sabía cosas y te las contaba. No cambiaba un fichero, no rellenaba un Excel, no tomaba una decisión.

Hoy hemos dado el salto siguiente: de un agente que **responde** a un equipo de agentes que **actúa** — y que, antes de cerrar, te devuelve a ti la última palabra.

> *"Un agente que responde es un buen bibliotecario. Un equipo de agentes que actúa hace además el trabajo."*

---

### El problema real: analizar un pliego (RFP)

Una RFP (Request for Proposal / pliego de licitación) es un documento en el que un cliente describe lo que necesita y pide una propuesta. Analizar una implica:

- Leerse el documento entero sin dejarse nada.
- Extraer **qué te están pidiendo** exactamente (los requisitos).
- Detectar las **trampas**: ambigüedades, plazos imposibles, contradicciones, información que falta.
- Estimar **cuánto trabajo** supone.

Es tedioso, es fácil que se escape algo, y lo hace gente cara. El candidato perfecto para delegar en un equipo de IA.

---

### La idea central: un equipo, no un superagente

No le pedimos a **una** IA que lo hiciera todo. Montamos un **equipo pequeño** donde cada agente hace una sola cosa y la hace bien — igual que organizarías a personas.

La analogía que usamos toda la charla: una **asesoría**.

| Rol en la asesoría | Agente | Su única misión |
|---|---|---|
| Jefe de proyecto | **Analista de RFP** (orquestador) | recibe el encargo, reparte, junta las piezas y presenta |
| Analista | **Extractor de requisitos** | lee el pliego y saca la lista de lo que piden |
| Experto en riesgos | **Detector de riesgos** | busca trampas, contradicciones y huecos |
| Estimador | **Estimador de tareas** | calcula el esfuerzo aproximado |

El jefe **no hace el trabajo**: coordina. Cada especialista tiene la cabeza en una sola tarea, y por eso la hace mejor.

> *"No le pedí a una IA que lo hiciera todo. Monté un equipo donde cada uno hace una cosa. Exactamente como organizarías a personas."*

---

### Lo más sorprendente: se coordinan con lenguaje, no con código

¿Cómo sabe el jefe a quién llamar en cada momento? **No hay ninguna programación, ningún "si pasa esto, llama a aquel".**

Cada especialista tiene escrita, en lenguaje normal, una descripción del tipo *"úsame para detectar riesgos: ambigüedades, plazos, contradicciones y qué información falta"*. El orquestador **lee** esas descripciones y decide. El pegamento que une a los agentes es el lenguaje.

> *"El pegamento que une a estos agentes no es código. Es lenguaje. Se entienden leyéndose la descripción unos a otros."*

Y hay un detalle de diseño importante: cuando un especialista termina, **no le habla al usuario directamente** — le devuelve su parte al jefe. Por eso al final ves un informe único y ordenado, y no tres agentes hablando a la vez y pisándose.

---

### El salto de verdad: de responder a ACTUAR

El agente de la charla 13 respondía. El de hoy, además, tiene **manos**: al final del análisis coge la lista de requisitos y la **escribe en un Excel de verdad**, en OneDrive, un fichero que abres al día siguiente.

Por debajo hay una pequeña automatización (Power Automate) que vuelca los datos fila a fila. No hace falta entender el cómo; la idea es la que importa:

> *"El agente piensa; una herramienta ejecuta."*

Esto enlaza directo con la **charla 18**: la IA no debe hacer las cuentas "de cabeza" —ahí es donde se equivoca—, sino **encargarle el trabajo mecánico a la herramienta que lo hace bien**. El modelo aporta el juicio; la herramienta, la precisión.

---

### La demo: el pliego de la academia de baile "Compás"

Usamos un pliego **inventado** (una academia de baile ficticia) para no enseñar datos reales de nadie. Dentro escondimos varias trampas a propósito. El equipo de agentes las cazó:

| La trampa escondida en el pliego | Qué hizo el agente |
|---|---|
| La **fecha de decisión es anterior a la de entrega** de propuestas (deciden antes de recibir lo que van a juzgar) | La detectó como **contradicción**: no copió el texto, lo entendió y vio que no cuadra |
| La **segunda sede**, colada en el apartado de "lo que queda fuera del proyecto", pero que **sí** hay que prever | La **rescató** y la puso como requisito: leyó la letra pequeña |
| **Presupuesto "limitado" sin cifra** y "responder bien con mucha gente" **sin número** | Los marcó como **huecos de información** que hay que confirmar para poder ofertar |
| No hay personal técnico, pero "alguien tendrá que mantener el sistema" | Lo señaló como **riesgo / contradicción** |

> *"No ha leído el pliego. Lo ha comprendido. Por eso ve una contradicción que a un humano cansado, a las siete de la tarde, se le escapa."*

---

### El momento más importante: el checkpoint humano

Antes de generar el Excel, el agente **no cerró nada**. Hizo el análisis, mostró lo que encontró y **se paró a preguntar**: *"¿quieres corregir, añadir o quitar algo antes de que lo genere?"*.

Esto es lo aprendido en la charla 18 hecho práctica: la IA hace el trabajo pesado, te enseña lo dudoso, y **tú decides**. No es un piloto automático; es un copiloto que te pasa el control en el momento clave. Y no es una carencia — es un **diseño**: cuanto más potente es la IA, más importa ese punto de control humano.

> *"La IA que da miedo es la que actúa sola. Esta, antes de tocar nada, levanta la mano y te pregunta."*

---

## Cómo montarlo tú, paso a paso (tutorial completo)

Esta sección es un manual reproducible: siguiéndola de arriba abajo, cualquiera con acceso a Copilot Studio puede montar exactamente esta solución. El orden importa — construimos primero el "cerebro" (los agentes) y al final las "manos" (el flujo que escribe en Excel).

> **La lógica de la conversación que vamos a construir es siempre la misma:**
> **analizar → mostrar → preguntar → (confirmación humana) → actuar.**

---

### Paso 0 — Comprobaciones previas (pre-flight)

Antes de invertir tiempo, verifica que tu tenant te deja hacer todo esto. Si algo falla aquí, mejor saberlo ya:

- [ ] Tienes **licencia de Microsoft 365 Copilot** y acceso a **Copilot Studio**.
- [ ] Puedes **crear un agente** y, dentro, añadir **agentes hijo** (pestaña *Agentes*).
- [ ] En *Herramientas* puedes añadir un **Flujo de Agente** (una acción), no solo *Conocimiento*. Este es el punto clave: sin acciones, el agente responde pero no actúa.
- [ ] La política de datos (**DLP**) de tu organización permite los conectores de **SharePoint / OneDrive** y **Excel Online**. Si al añadir la herramienta esos conectores aparecen disponibles, vía libre.
- [ ] Tienes una carpeta de **OneDrive o una biblioteca de SharePoint** donde el agente pueda escribir el fichero.

---

### Paso 1 — Crear el agente orquestador ("Analista de RFP")

Crea un agente nuevo. En **Información general**:

**Nombre:** `Analista de RFP`

**Modelo:** elige **GPT-5.5** — el más reciente de los que **no** están en vista previa. Para algo que va en serio no quieres un modelo "(vista previa)" que se comporte de forma inestable.

**Descripción:**
> Analiza pliegos de licitación (RFP): extrae los requisitos, detecta riesgos y huecos, y estima el esfuerzo, coordinando a varios agentes especialistas. Antes de generar ningún documento, muestra un borrador para que un humano lo revise.

**Instrucciones** (si tu Copilot Studio ofrece la plantilla de cinco secciones, úsala tal cual):

*Directrices generales:*
> Eres el coordinador de un equipo de agentes que analiza pliegos de licitación (RFP). Tu función NO es analizar tú el pliego, sino repartir el trabajo entre tus agentes especialistas, esperar sus resultados, juntarlos y presentarlos con claridad. Hablas en español, directo y pensando en alguien de negocio que no es técnico. Nunca inventes un requisito, un plazo, una penalización o cualquier dato que no aparezca en el pliego: si algo no está o es ambiguo, márcalo como "duda / falta confirmar", no lo rellenes. No cierras el análisis ni generas ningún documento sin la confirmación explícita del usuario.

*Habilidades:*
> Coordinas a tres agentes especialistas, en este orden:
> 1. Cuando el usuario aporte un pliego (adjunto o desde SharePoint), llama a **"Extractor de requisitos"** y espera su lista estructurada de requisitos.
> 2. Pasa esa lista a **"Detector de riesgos"** y espera los riesgos y huecos que detecte.
> 3. Si el usuario pide estimación, llama a **"Estimador de tareas"** con la lista de requisitos y espera su estimación.
> 4. Combina los tres resultados en un único resumen: primero los requisitos (separando obligatorios y deseables), luego riesgos e información que falta, y por último la estimación si la hay.
> 5. *(Este punto se completa en el Paso 6, cuando conectemos la herramienta que escribe el Excel.)*

*Manejo de errores:*
> Si un agente especialista no devuelve resultado o falla, díselo al usuario con naturalidad en vez de continuar como si nada. Si el pliego no se ha aportado, pídelo antes de empezar. Si el texto es demasiado corto o no parece un pliego, avísalo en lugar de inventar un análisis.

*Ejemplos de interacción:*
> Usuario: "Analízame este pliego" (adjunta un documento).
> Tú: llamas a los especialistas en orden y respondes: "He analizado el pliego. Requisitos obligatorios: [...]. Deseables: [...]. Riesgos y huecos que he detectado: [...]. Hay 3 puntos marcados como 'falta confirmar'. ¿Quieres corregir o añadir algo antes de que genere el Excel?"

*Seguimiento y cierre:*
> Antes de generar cualquier documento, muestra siempre el resumen y pregunta explícitamente si hay que corregir, añadir o quitar algo. No generes el entregable hasta recibir un "sí" claro. Tras entregarlo, ofrece un siguiente paso útil y cierra sin inventar tareas que el usuario no haya pedido.

Deja **Conocimiento** y **Herramientas** del orquestador **vacíos** de momento: el orquestador solo coordina. Guarda.

---

### Paso 2 — Crear los tres agentes especialistas (agentes hijo)

En la pestaña **Agentes** → **Agregar** → **Agente ligero dentro del agente existente**. Vas a crear tres, uno por uno.

**Ajustes del panel — idénticos para los tres** (esto es tan importante como el texto):

- **¿Cuándo se utiliza?** → **"El agente elige: basado en la descripción"**. Esto es lo que permite que el orquestador delegue leyendo la descripción. Ninguna de las otras opciones.
- **Conocimiento** y **Herramientas** → **vacíos** (leen el pliego del historial de la conversación).
- **Entradas** → **ninguna**. Vamos en modo generativo: el orquestador pasa el contexto en lenguaje natural. No declares entradas tipadas.
- **Finalización → Después de ejecutar** → **"No responder (predeterminado)"**. Así el especialista devuelve su resultado **al orquestador**, no directamente al usuario. Es lo que hace que al final salga un informe único y no tres volcados sueltos.
- **Avanzado** (Condición / Prioridad / salidas) → por defecto, sin tocar.

> ⚠️ Los nombres de los tres agentes deben coincidir **exactos** con los que el orquestador menciona en sus Habilidades, o no sabrá a quién llamar.

**Agente hijo 1 — Nombre:** `Extractor de requisitos`
*Descripción:*
> Úsame para leer un pliego de licitación (RFP) y extraer TODOS sus requisitos en una lista estructurada, clasificados como obligatorios o deseables. Solo extraigo y clasifico requisitos: no detecto riesgos ni estimo esfuerzo.

*Instrucciones:*
> Tu única función es leer el pliego (RFP) que aparece en la conversación y extraer todos sus requisitos. No detectas riesgos ni estimas esfuerzo. Para cada requisito, genera una fila con estas columnas exactas:
> - **ID**: R1, R2, R3…
> - **Requisito**: redactado de forma concisa y clara.
> - **Categoría**: Técnico / Funcional / Legal-Administrativo / Económico / Plazos.
> - **Tipo**: Obligatorio o Deseable (fíjate en el lenguaje: "deberá", "imprescindible" → Obligatorio; "se valorará", "preferiblemente" → Deseable).
> - **Referencia**: el apartado o página de donde lo sacas.
> - **Estado**: "OK" si está claro, o "Duda – falta confirmar" si es ambiguo.
>
> Reglas: extrae SOLO lo que está en el texto, nunca inventes. Si dudas entre Obligatorio y Deseable, ponlo como Deseable y marca Estado como "Duda – falta confirmar". Devuelve solo la tabla, en español.

**Agente hijo 2 — Nombre:** `Detector de riesgos`
*Descripción:*
> Úsame después de extraer los requisitos, para analizar riesgos: cláusulas ambiguas, plazos y penalizaciones, requisitos técnicamente difíciles, contradicciones internas y qué información falta para ofertar con seguridad. No extraigo requisitos ni estimo esfuerzo.

*Instrucciones:*
> Tu única función es analizar un pliego (RFP) y su lista de requisitos ya extraída, y señalar riesgos y huecos. Localiza:
> - **Cláusulas ambiguas**: requisitos vagos o interpretables de varias maneras.
> - **Plazos y penalizaciones**: fechas ajustadas, penalizaciones, condiciones comprometidas.
> - **Riesgo técnico**: requisitos difíciles, tecnología poco habitual, dependencias externas.
> - **Huecos de información**: datos que el pliego NO aporta pero que harían falta para ofertar.
> - **Contradicciones e inconsistencias**: datos que se contradicen dentro del propio pliego — fechas que no cuadran, condiciones incompatibles, afirmaciones opuestas.
>
> Para cada punto, una fila con: **ID** (el del requisito afectado, o G1, G2… si es general), **Tipo** (Ambigüedad / Plazo-Penalización / Riesgo técnico / Falta información / Contradicción), **Descripción**, **Por qué importa**, **Severidad** (Alta / Media / Baja).
>
> Reglas: básate solo en lo que dice o calla el pliego. Un hueco de información es tan importante como un riesgo explícito. Devuelve solo la tabla, en español.

**Agente hijo 3 — Nombre:** `Estimador de tareas`
*Descripción:*
> Úsame cuando el usuario pida estimar el esfuerzo de un pliego ya analizado. Convierto la lista de requisitos en tareas con una estimación aproximada. No extraigo requisitos ni detecto riesgos.

*Instrucciones:*
> Tu única función es convertir una lista de requisitos ya extraída en un plan de tareas con esfuerzo estimado. Para cada requisito, genera una o varias tareas, con una fila por tarea: **ID tarea** (T1, T2…), **Requisito** (el ID de origen), **Tarea** (en una frase), **Esfuerzo** (talla XS/S/M/L/XL: XS ≈ <½ día, S ≈ 1 día, M ≈ 2-3 días, L ≈ 1 semana, XL ≈ >1 semana), **Supuestos**.
>
> Al final, una línea de **total aproximado**. Reglas: la estimación es orientativa y de alto nivel (dilo así), no un presupuesto cerrado. Si un requisito tiene dudas, refléjalo en Supuestos como "pendiente de confirmar". Devuelve solo la tabla y el total, en español.

Con esto, la "sala de expertos" está montada. Puedes probarla ya en el panel **Test** con un pliego en **PDF** (el Markdown no se ingiere bien): debería delegar en los tres y terminar preguntándote si quieres corregir algo. Falta darle las "manos".

---

### Paso 3 — Preparar la plantilla de Excel

El flujo que escribe en Excel necesita un fichero con una **tabla ya creada** (no basta un Excel en blanco):

1. En tu OneDrive, crea `Entregable-RFP.xlsx`.
2. En la fila 1, las cabeceras, una por columna (A→F): `ID | Requisito | Categoría | Tipo | Referencia | Estado`.
3. Selecciona esa fila y un par de filas vacías → **Insertar → Tabla** (marca "La tabla tiene encabezados").
4. Con la tabla seleccionada, en **Diseño de tabla**, pon el **Nombre de tabla**: `TablaRequisitos`. El flujo la buscará por ese nombre.
5. Guarda y cierra.

Las seis columnas coinciden con lo que devuelve el Extractor: eso es lo que hace que el volcado sea limpio.

---

### Paso 4 — Crear el flujo que escribe en Excel

En **Herramientas → Agregar → Flujos de Agente → diseñar el flujo**. Vas a encadenar cinco acciones:

**4.1 · Desencadenador "Cuando un agente llama al flujo".**
Añade **una** entrada:
- Nombre: `requisitos`
- Tipo: **Texto**
- Deja el valor de ejemplo **vacío** (lo rellena el agente en tiempo real).

El agente le pasará los requisitos como **texto en formato JSON**. La conversión a filas la hace el flujo.

**4.2 · "Redactar" (Compose).**
Añade una acción *Redactar* y ponle como entrada el campo `requisitos`. Normaliza el texto antes de interpretarlo y da un punto de anclaje limpio para el paso siguiente. *(Este paso intermedio evita varios problemas de parseo.)*

**4.3 · "Analizar JSON" (Parse JSON).**
- **Contenido**: la salida del *Redactar* anterior (o directamente el campo `requisitos`).
- **Esquema**: pégalo **directamente en el campo Esquema** (ver errores abajo): **no** uses "Generar a partir de una muestra" — eso genera un esquema equivocado. Pega esto tal cual, que empieza por `"type": "array"`:

```json
{
    "type": "array",
    "items": {
        "type": "object",
        "properties": {
            "ID": { "type": "string" },
            "Requisito": { "type": "string" },
            "Categoria": { "type": "string" },
            "Tipo": { "type": "string" },
            "Referencia": { "type": "string" },
            "Estado": { "type": "string" }
        }
    }
}
```

> Nota: `Categoria` va **sin tilde** en la clave JSON (evita sustos de codificación). La columna de Excel sí lleva tilde; se mapean a mano en el paso siguiente.

**4.4 · "Agregar una fila a una tabla" (Excel Online - Business).**
Al mapear campos del *Analizar JSON*, Power Automate envuelve la acción automáticamente en un **"Aplicar a cada uno"** — perfecto, recorre la lista y escribe un requisito por vuelta. Configura:
- **Ubicación**: OneDrive for Business.
- **Archivo**: `Entregable-RFP.xlsx`.
- **Tabla**: `TablaRequisitos`.
- Mapea columna ← campo JSON: `ID`←ID, `Requisito`←Requisito, **`Categoría`←`Categoria`** (el único que no coincide letra a letra), `Tipo`←Tipo, `Referencia`←Referencia, `Estado`←Estado.

**4.5 · "Responder al agente".**
Añade una salida de texto (fuera del bucle, al final):
- Nombre: `resultado`
- Valor: `Entregable generado con los requisitos en el Excel Entregable-RFP.xlsx`

Guarda el flujo. Si quieres probarlo aislado, hazlo con este ejemplo pegado como valor de `requisitos`:

```json
[{"ID":"R1","Requisito":"Portal de alumno para reservar plazas","Categoria":"Funcional","Tipo":"Obligatorio","Referencia":"4.3","Estado":"OK"},{"ID":"R2","Requisito":"Gestion de menores con consentimiento del tutor","Categoria":"Legal-Administrativo","Tipo":"Obligatorio","Referencia":"4.2","Estado":"OK"}]
```

Debe terminar en verde y escribir dos filas en el Excel.

---

### Paso 5 — Conectar el flujo al orquestador

En **Analista de RFP → Herramientas → Agregar** y elige tu flujo **"Requisitos a Excel"** (si no aparece, refresca con F5 y asegúrate de que está guardado).

Al añadirlo, configura la entrada `requisitos`:
- **Rellenar con:** **"Rellenar dinámicamente con IA"** — el agente construye el JSON él mismo a partir de los requisitos extraídos.
- **Valor → personalizar:** describe con precisión qué debe construir. Pega esto:

> La lista **COMPLETA** de requisitos extraídos del pliego, TODOS ellos sin excepción ni resumen (si hay 20 requisitos, el array tiene 20 elementos). Formato: array JSON donde cada requisito es un objeto con exactamente estos campos: "ID", "Requisito", "Categoria" (sin tilde), "Tipo", "Referencia", "Estado". Incluye solo requisitos, no riesgos ni estimación. Ejemplo de un elemento: {"ID":"R1","Requisito":"texto","Categoria":"Funcional","Tipo":"Obligatorio","Referencia":"4.3","Estado":"OK"}

Los dos detalles que evitan los fallos más comunes: **`Categoria` sin tilde** (o el Parse JSON no reconoce esa columna) y pedir la **lista COMPLETA** de forma explícita (o el modelo tiende a resumir).

---

### Paso 6 — Decirle al orquestador cuándo llamar a la herramienta

Vuelve a las **Instrucciones** del orquestador y completa el punto 5 de **Habilidades**:

> 5. Cuando el usuario confirme el resumen, llama a la herramienta **"Requisitos a Excel"** pasándole **todos** los requisitos extraídos, la lista íntegra, sin resumirla ni seleccionar solo los principales. Pásale solo los requisitos, no los riesgos ni la estimación. Cuando la herramienta responda, devuelve al usuario el mensaje de confirmación que te dé.

---

### Paso 7 — Publicar y probar el ciclo completo

1. **Publica el agente.** Importante: los flujos de agente se activan **al publicar el agente**, no desde Power Automate.
2. En el panel **Test**, adjunta el pliego **en PDF** y escribe: *"Analízame este pliego."*
3. Cuando muestre el resumen y pregunte, responde: *"Sí, genéralo."*
4. Comprueba que aparecen las filas en `Entregable-RFP.xlsx` (ábrelo de verdad; no te fíes solo del mensaje de "hecho").

Ciclo completo: **analizar → mostrar → preguntar → confirmar → escribir en Excel.**

---

### Errores que te vas a encontrar (y cómo se arreglan)

Estos son reales, salieron durante el montaje:

| Síntoma | Causa | Solución |
|---|---|---|
| `ValidationFailed. Expected Object but got array` en *Analizar JSON* | El esquema se metió con "Generar a partir de una muestra", que crea un esquema equivocado | Borra el esquema y **pégalo directamente**; debe empezar por `"type": "array"` |
| El agente solo escribe **3 requisitos** de muchos | El modelo resume por defecto | Refuerza "lista **COMPLETA**, TODOS, sin resumir" en la descripción de la entrada y en las instrucciones (con esto pasó de 3 a 34) |
| El flujo sale **deshabilitado** en Power Automate y no deja activarlo ("nunca se ha publicado") | Los flujos de agente no se activan desde Power Automate | Conéctalo como herramienta del agente y **publica el agente** |
| El agente **no lee el pliego** o lo interpreta mal | Formato Markdown | Usa **PDF** |
| El flujo **no aparece** en Herramientas del agente | Cache / flujo no guardado | Refresca (**F5**) y verifica que está guardado |
| El desplegable **Tabla** aparece vacío en la acción de Excel | El Excel no se guardó como tabla con nombre | Vuelve al Excel: Insertar → Tabla → nómbrala `TablaRequisitos` |

---

## Tres ideas para llevarse

**1. Un agente ya no solo responde: puede hacer el trabajo.**
El salto respecto a la charla 13 es de un agente que *sabe* cosas a un equipo que las *hace* y las deja escritas donde trabajas.

**2. Coordinar agentes se hace con lenguaje, no con código.**
Montar esto fue, sobre todo, **escribir bien**: buenos encargos y buenas descripciones. Es una herramienta que maneja gente de negocio, no solo desarrolladores.

**3. El humano tiene la última palabra a propósito.**
El agente se para y pregunta por diseño. No es que no sepa cerrar solo: es que **no debe** hacerlo sin ti.

---

## Por dónde empezar a pensar

No hace falta que montes nada todavía. La pregunta útil es:

> **¿Qué tarea de tu día a día consiste en "leer algo largo y ordenarlo o revisarlo", y se repite?**

Ahí es donde un equipo de agentes aporta. Algunos ejemplos por perfil:

- **Comercial / preventa:** analizar pliegos, comparar propuestas, revisar contratos largos.
- **RRHH:** cruzar y revisar información dispersa en varios ficheros (justo lo que veremos en una charla dedicada).
- **Dirección / PMO:** sacar riesgos y estimaciones de magnitud de un documento de alcance.
- **Cualquiera:** convertir un documento denso en una lista accionable, con las dudas marcadas.

---

## Lo que viene (parte 2)

La charla fue el **qué** y el **porqué**; el tutorial de arriba te da el **cómo** para reproducir este caso. En una próxima sesión iremos más allá:

- Cómo se comunican los agentes entre sí a más profundidad, y patrones de orquestación más complejos.
- Cómo adaptar este mismo esqueleto a **tu** problema concreto — empezando por el caso que ya nos pidió RRHH: cruzar sus Excel de forma fiable.
- Buenas prácticas para llevar un agente de la demo al uso diario (permisos, datos, gobierno).

---

## Glosario de conceptos vistos hoy

**[[agente-ia|Agente de IA]]**
Sistema de IA que razona sobre una petición, decide qué hacer y actúa, en lugar de seguir un guión predefinido. A diferencia de un chatbot, se adapta y reconoce lo que no sabe.

**Orquestador (o agente coordinador)**
El agente "jefe de proyecto": no realiza el trabajo especializado, sino que reparte tareas entre otros agentes, espera sus resultados y los junta en una respuesta única.

**Agente especialista (agente hijo)**
Agente con una única misión bien acotada (extraer, detectar riesgos, estimar…). Su **descripción** en lenguaje natural es lo que permite al orquestador saber cuándo llamarlo.

**Orquestación por descripciones**
Mecanismo por el que el coordinador decide a qué especialista llamar **leyendo la descripción** de cada uno, sin lógica programada. La coordinación se hace con lenguaje.

**[[checkpoint-humano|Checkpoint humano (human-in-the-loop)]]**
Punto del proceso en el que el agente se detiene y pide validación a una persona antes de ejecutar una acción con consecuencias. Diseño clave para poder confiar en un agente que actúa.

**Agente que responde vs. agente que actúa**
El primero consulta conocimiento y contesta (charla 13). El segundo, además, ejecuta acciones en el mundo real —escribir un fichero, lanzar un proceso— a través de herramientas.

**[[power-automate|Power Automate]]**
Herramienta de Microsoft para crear automatizaciones. Aquí, la "mano" que ejecuta la parte mecánica y precisa (volcar los requisitos a un Excel) que el agente no debe hacer de memoria.

**[[copilot-studio|Copilot Studio]]**
Plataforma de Microsoft para crear agentes de IA dentro del ecosistema corporativo. Permite definir instrucciones, conectar conocimiento, añadir herramientas y coordinar varios agentes.

**RFP (pliego de licitación)**
Documento en el que un cliente describe una necesidad y solicita una propuesta. El caso de uso de la demo.

**Regla anti-invención**
Instrucción explícita que prohíbe al agente rellenar huecos inventando: si un dato no está en la fuente, lo marca como duda. Aplicación directa de lo aprendido en la charla 18.

---

*Charla 19 (parte 1) — Serie de formación interna en IA*
