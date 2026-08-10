---
type: Guión
title: "Guión Charla 16 — Del prompt al blueprint: SDD con herramientas (spec manual vs OpenSpec)"
description: "Charla técnica, con pantalla y demo en directo. Gancho de actualidad (agentes que programan solos), refresco compacto de SDD, anatomía de un spec manual, el ecosistema SDD 2026 (OpenSpec vs Spec Kit vs Kiro), demo en vivo de un issue de Jira a código con OpenSpec sobre RCA, y criterio de cuándo usar cada opción. Formato ~50-55 min + preguntas."
tags: [guion, charla-16, sdd, spec-driven-development, openspec, spec-kit, kiro, agentes-autonomos, demo-jira, rca]
related: [sdd, sdd-variations, autonomous-coding-agents, code-generation-patterns]
charla: "Charla 16"
estado: "🔲 Borrador — listo para revisión y ensayo"
timestamp: "2026-08-08"
---

# Guión Charla 16 — Del prompt al blueprint: SDD con herramientas

> ⚠️ **Nota de alcance:** esta es una charla **técnica**, de perfil developer, con **pantalla compartida y demo en directo**. Es un cambio deliberado de registro tras varias charlas transversales. Conviene avisarlo en la apertura para que los perfiles no técnicos sepan a qué atenerse (y que aun así se llevan algo — ver Bloque 6).
>
> **Nota de duración:** formato ~50-55 min + preguntas. La demo (Bloque 4) es el corazón y el bloque más elástico: si va larga, se recorta por el final (ver checklist). Vuelve al formato habitual tras la extendida de la 15.
>
> **Nota de refresco:** SDD ya se vio en profundidad en la serie (Charla 7 y siguientes). Aquí NO se re-explica el concepto entero — solo un refresco de 3-4 min para el público nuevo (la audiencia rota y crece), con puntero a la grabación anterior para quien quiera el deep dive.

---

## Estructura de tiempos

| Bloque    | Contenido                                                              | Tiempo   |
| --------- | ---------------------------------------------------------------------- | -------- |
| Apertura  | Gancho: los agentes ya programan solos — ¿dónde queda el cuello de botella? | 4 min    |
| Bloque 1  | Refresco compacto: qué es un spec y por qué (para el público nuevo)     | 4 min    |
| Bloque 2  | Spec manual — cómo lo he estado haciendo yo (en pantalla)              | 7 min    |
| Bloque 3  | Spec con herramienta — el ecosistema SDD 2026 (OpenSpec / Spec Kit / Kiro) | 10 min   |
| Bloque 4  | **DEMO EN DIRECTO** — de un issue de Jira a código, con OpenSpec sobre RCA (incluye tutorial de instalación)  | 20 min   |
| Bloque 5  | Cuándo cada cosa — criterio práctico (y cuándo NO usar spec formal)     | 5 min    |
| Bloque 6  | Qué se lleva cada rol (también los no-devs)                            | 3 min    |
| Cierre    | Recap + conexión con el arnés y la serie                              | 4 min    |
| Preguntas | Turno abierto                                                          | 8-12 min |

**Total estimado:** ~57 min + preguntas

---

## Apertura — Los agentes ya programan solos — 4 min

> _"Antes de empezar, un aviso: esta charla es distinta. Es la primera del año claramente técnica — voy a compartir pantalla, vais a ver herramientas de verdad y vamos a hacer una demo en directo. Si no programáis, no os vayáis: al final hay algo que os toca a todos, os lo prometo. Pero avisado queda que hoy nos ensuciamos las manos."_
>
> _"Empiezo por lo que ha pasado esta misma semana. Meta ha sacado un agente que programa desde la terminal con workers en segundo plano. Un framework llamado Prime Agent, combinado con el nuevo Claude Opus 5, ha superado por primera vez la línea base de un humano experto en un benchmark de razonamiento. Los agentes ya no autocompletan líneas: cogen una tarea y la construyen enteros."_
>
> _"Y aquí viene la pregunta incómoda: si el agente ya sabe escribir el código, ¿cuál es ahora nuestro trabajo? ¿Dónde está el cuello de botella?"_
>
> _"El cuello de botella se ha movido. Ya no es escribir el código. Es decirle al agente QUÉ construir, sin ambigüedad, de forma que no se invente la mitad. Y resulta que eso tiene nombre, tiene disciplina, y desde este año tiene herramientas. Eso es de lo que va hoy."_

**Frase que debe quedar:**

> _"Cuando la IA escribe el código gratis, el valor deja de estar en teclear. Pasa a estar en saber pedir. Y saber pedir, bien hecho, es una habilidad de ingeniería."_

---

## Bloque 1 — Refresco: qué es un spec y por qué — 4 min

> _"Para quien no estuvo en la Charla 7, treinta segundos de contexto — el resto lo tenéis en la grabación."_ ⚠️ *(confirmar cuál es la charla donde explicaste SDD en detalle: Charla 7 o la de SDD en Angular, y darla como referencia en pantalla)*

- **Vibe coding** = le sueltas un prompt vago a la IA y rezas. Funciona para un script de diez líneas; se desmorona en cuanto el proyecto crece o pasan los días.
- **Spec-Driven Development (SDD)** = escribes la intención de forma estructurada (qué, por qué, criterios de aceptación) *antes* de que se escriba una sola línea, y el agente ejecuta contra eso.
- La metáfora de siempre: **no le das a un contratista "hazme una casa, ya te apañas". Le das planos.** El SDD son los planos para agentes de IA. La especificación es la fuente de verdad, no el código.

> _"Y no es una moda de nicho. Este año el SDD ha pasado de rareza a estándar: Martin Fowler ha escrito sobre ello, hay cursos dedicados, y la herramienta principal de GitHub para esto ha pasado de los cien mil favoritos. Pero hay un dato que lo resume mejor que ninguno."_

**El dato ancla** (encuesta JetBrains, enero 2026, 11.000 devs):

> _"El 90% de los desarrolladores ya usa IA en su trabajo. Pero solo el 13% la usa en todo el ciclo de desarrollo. Casi todos la usamos para escribir trozos sueltos de código. Casi nadie la usa para gobernar el proyecto entero. Ese salto — del 90% al 13% — es exactamente lo que el SDD intenta cerrar."_

⚠️ *Verificar la cifra de favoritos de Spec Kit y el dato de JetBrains antes del miércoles por si han cambiado — evolucionan rápido.*

**Frase que debe quedar:**

> _"Casi todos usamos IA para escribir código. Muy pocos la usamos para dirigir el proyecto. El spec es el puente entre esas dos cosas."_

---

## Bloque 2 — Spec manual: cómo lo he estado haciendo yo — 7 min

> _"Antes de enseñaros ninguna herramienta, quiero enseñaros lo que he estado haciendo yo a mano durante toda esta serie — porque el 90% del valor está aquí, y no necesita instalar nada."_

**En pantalla — abrir un spec manual real del proyecto RCA:**
- Mostrar `task-rca-28.md` (o `task-rca-20.md`) del vault — un spec de tarea escrito a mano

**La anatomía de un buen spec manual** (señalarla en pantalla sobre el fichero real):

| Parte | Qué contiene | Por qué importa |
|---|---|---|
| **Qué / objetivo** | La funcionalidad en lenguaje claro, sin el "cómo" técnico todavía | El agente necesita saber la meta, no adivinarla |
| **Por qué** | El contexto y la intención detrás | Sin el porqué, el agente toma decisiones que rompen el sentido |
| **Criterios de aceptación** | Cuándo se considera "hecho", de forma verificable | Es lo que separa "creo que funciona" de "sé que funciona" |
| **Contexto técnico** | Stack, patrones, restricciones (ej. Angular, convenciones RCA) | Evita que reinvente lo que ya existe |
| **Tareas** | El desglose paso a paso | El agente ejecuta la lista, no improvisa el orden |

> _"Fijaos en que esto no tiene magia. Es un fichero de texto, en el repo, al lado del código. Lo escribo yo, lo reviso yo, y el agente lo ejecuta. Control total."_

**Ventajas y límites del spec manual** (honestidad, es la base de la comparación del Bloque 3):

- ✅ **Control total** — cada línea la has decidido tú
- ✅ **Cero dependencias** — no instalas nada, no dependes de ningún vendor
- ✅ **Lo entiendes entero** — no hay caja negra
- ⚠️ **Toda la disciplina la pones tú** — nada te obliga a incluir los criterios de aceptación; si un día tienes prisa, los saltas
- ⚠️ **No hay estructura impuesta** — cada spec puede acabar con un formato distinto
- ⚠️ **Se degrada con el tiempo** — cuando el proyecto cambia, actualizar los specs a mano es trabajo que casi nadie hace, y el spec deja de reflejar la realidad

**Frase que debe quedar:**

> _"El spec manual es SDD con las manos. Funciona perfectamente… mientras tengas la disciplina de mantenerlo. El problema nunca es empezar un spec. Es mantenerlo vivo cuando el proyecto evoluciona y hay prisa."_

---

## Bloque 3 — Spec con herramienta: el ecosistema SDD 2026 — 10 min

> _"Ese problema — 'lo hago a mano pero se me degrada' — es exactamente el que resuelven las herramientas de SDD. Y este año han explotado. Os voy a enseñar los tres arquetipos, porque representan tres filosofías opuestas, y os interesa saber cuál encaja con vosotros antes de casaros con ninguna."_

### OpenSpec — el ligero

- Capa **ligera**, pensada para proyectos que **ya existen** (brownfield), open-source, sin claves de API
- Su idea diferencial: **delta specs**. En vez de reescribir toda la especificación cada vez, describes solo lo que cambia, con secciones **AÑADIDO / MODIFICADO / ELIMINADO** sobre un **único spec vivo** que hace de fuente de verdad
- Cada cambio vive en su carpeta: `proposal`, `specs`, `design`, `tasks`
- **Funciona con las herramientas que ya usáis** (Copilot, Claude Code y ~20 más) vía slash commands — sin lock-in
- Requiere Node 20.19+
- El "peaje": el *drift* del spec lo gestionas tú a mano

### Spec Kit (GitHub) — el estándar de comunidad

- CLI open-source (`specify`), licencia MIT, la opción **más adoptada** (>100k favoritos en GitHub)
- Flujo de cinco fases: **Constitución → Especificar → Planificar → Tareas → Implementar**
- La "constitución" son las reglas no negociables del proyecto que todo spec futuro respeta
- Funciona con 30+ agentes (Copilot, Claude Code, Cursor, Gemini CLI…), specs en Markdown puro que viven en el repo
- El "peaje": las specs son **estáticas** — no gobiernan nada tras la primera generación hasta que un humano las actualiza; y genera **mucho** markdown (a veces repetitivo — para tareas pequeñas el overhead es desproporcionado)

### Kiro (AWS) — el integrado

- No es una CLI: es un **IDE entero** construido alrededor del spec (sobre la base de VS Code, con CLI y web también). Reemplazo del difunto Amazon Q Developer
- Las specs son **objetos de primera clase** en el editor, no ficheros que gestionas aparte
- Usa **notación EARS** (Easy Approach to Requirements Syntax), un formato de requisitos de grado aeroespacial (viene de Rolls-Royce) que fuerza frases testeable y sin ambigüedad. Ejemplo adaptado a RCA:
  > *"CUANDO un cliente añade una pieza agotada al carrito, EL SISTEMA DEBE mostrar un aviso de 'sin stock' y deshabilitar el botón de compra."*
- **Agent Hooks**: automatizaciones que se disparan solas cuando cambias el código (actualizan tests, docs…) — un bucle bidireccional que Spec Kit no tiene
- El "peaje": **lock-in** (specs en `.kiro/`, modelos por AWS Bedrock, no traes tus propias claves) y un **modelo de precios por créditos** que ha generado bastante rechazo en la comunidad

### La tabla para decidir de un vistazo

| Criterio | Spec manual | OpenSpec | Spec Kit | Kiro |
|---|---|---|---|---|
| **Filosofía** | Tú y un `.md` | Ligero, cambios incrementales | Estándar de comunidad, CLI | IDE integrado y opinado |
| **Spec vivo o estático** | Lo mantienes tú | Vivo (delta specs) | Estático hasta que lo actualizas | Vivo (con Agent Hooks) |
| **Lock-in** | Ninguno | Ninguno | Ninguno | Alto (Bedrock + IDE) |
| **Mejor para** | Tareas pequeñas, control total | Proyectos que ya existen | Empezar de cero, saltar entre stacks | Equipos ya dentro de AWS |
| **Coste** | Gratis | Gratis | Gratis | Créditos con markup |
| **Funciona con tu stack (Copilot/Claude Code)** | Sí | Sí | Sí | Solo dentro de Kiro |

> _"El patrón que quiero que veáis: no hay un ganador. Hay un espectro. A la izquierda, control absoluto y cero estructura. A la derecha, un IDE que te lo da todo hecho pero te ata. La herramienta te da estructura y persistencia a cambio de imponerte su forma de trabajar. La pregunta no es 'cuál es la mejor', es 'cuánta estructura necesito y cuánta libertad quiero ceder'."_

⚠️ *Verificar antes del miércoles: versión/estado actual de los tres (evolucionan cada pocas semanas). Confirmar en pantalla los datos concretos (favoritos, releases) solo si están frescos; si no, hablar en cualitativo.*

**Frase que debe quedar:**

> _"Manual contra herramienta no es una guerra. Es un espectro entre cuánta estructura necesitas y cuánta libertad estás dispuesto a ceder."_

---

## Bloque 4 — DEMO EN DIRECTO: de un issue de Jira a código, con OpenSpec — 20 min

> ⚠️ **El corazón de la charla.** Ensayar de principio a fin. Tener plan B (ver checklist). Si algo falla en vivo, se reencuadra como lo que es: los agentes no son magia, y ver dónde cojean es parte del aprendizaje.

**Escenario:** el proyecto real de la serie, **Resin Craft Art** (Angular), y la instancia demo de **Jira** (proyectos KAN / RCA). Un ciclo completo: de una tarea que alguien apunta en Jira, a código, pasando por un spec generado — sin escribir el spec a mano.

---

### Paso 0 — Instalar y configurar OpenSpec (en pantalla, ~3 min)

> _"Antes de la demo, os enseño lo que hay que instalar — porque si cuando acabe esto alguien quiere probarlo, que sepa que se tarda dos minutos."_

#### Requisitos previos

- **Node.js 20.19.0 o superior.** Verificar en terminal:
  ```bash
  node --version   # debe ser >= 20.19.0
  ```
  ⚠️ *Si no tienes Node o es una versión anterior, instalarlo primero. OpenSpec no funcionará con versiones más bajas.*

#### Instalación

```bash
# Instalar OpenSpec como paquete global
npm install -g @fission-ai/openspec@latest

# Verificar que se ha instalado correctamente
openspec --version
```

> _"Una línea de npm. Nada más. Sin claves de API, sin cuenta, sin registro. Open-source puro."_

⚠️ *Si `openspec` no se reconoce como comando tras la instalación, es un problema de PATH: npm ha instalado el binario en un directorio que tu shell no ve. Mostrar dónde lo puso (`npm config get prefix`) y cómo añadirlo. No editar `.bashrc`/`.zshrc` en directo — enseñar el cambio y que el usuario lo aplique.*

#### Inicialización en el proyecto

```bash
cd rca   # o el directorio raíz de tu proyecto
openspec init
```

**Lo que pasa durante `openspec init`** (en pantalla, señalar cada paso):
1. **Te pregunta qué herramienta de IA usas.** Seleccionar `github-copilot`. Otras opciones: `claude-code`, `cursor`, `devin`, `generic`… OpenSpec genera ficheros diferentes según la herramienta.
2. **Para Copilot, te pregunta si también quieres configurar el cloud coding agent** (el agente de GitHub que trabaja en background). Para la demo, no hace falta — decir que no.
3. **Opcionalmente, te propone crear un `openspec/config.yaml`** con contexto del proyecto (nombre, stack, convenciones). Recomendable hacerlo — el agente usa este contexto al generar las propuestas.
4. **Genera la estructura.**

**Lo que se crea en tu proyecto** (mostrar el árbol de ficheros):
```
openspec/
├── config.yaml          ← configuración del proyecto (stack, convenciones)
├── specs/               ← fuente de verdad: el estado actual del sistema
│   └── (vacío al inicio — se llena conforme archivas cambios)
├── changes/             ← propuestas de cambio activas
│   └── (vacío al inicio)
└── AGENTS.md            ← instrucciones para el agente de IA

.github/
└── prompts/             ← slash commands para Copilot (generados por OpenSpec)
    ├── opsx-propose.prompt.md
    ├── opsx-explore.prompt.md
    ├── opsx-apply.prompt.md
    └── opsx-archive.prompt.md
```

> _"Fijaos en dos cosas. Primera: todo es Markdown, todo vive en el repo, todo se versiona con Git. No hay base de datos, no hay servidor, no hay nada opaco. Segunda: esos ficheros de `.github/prompts/` son los que hacen que cuando yo escriba `/opsx-propose` en el chat de Copilot, Copilot sepa qué hacer. OpenSpec le ha enseñado los comandos."_

⚠️ *Detalle importante para la demo: los slash commands de OpenSpec en GitHub Copilot se escriben con guion, no con dos puntos. Es `/opsx-propose`, no `/opsx:propose`. La documentación oficial usa `/opsx:propose` como nombre canónico porque es agnóstico de herramienta, pero Copilot usa el formato con guion porque así es como VS Code registra los custom prompts. Los ficheros generados por `openspec init` ya usan la forma correcta para tu herramienta — no hay que cambiar nada.*

#### Los comandos que vamos a usar (chuleta para la pantalla)

| Dónde | Comando | Qué hace |
|---|---|---|
| **Chat de Copilot** | `/opsx-explore` | Pensar en voz alta con el agente antes de proponer nada — sin artefactos, sin código |
| **Chat de Copilot** | `/opsx-propose <nombre>` | Crear una propuesta de cambio completa (proposal + specs + design + tasks) |
| **Chat de Copilot** | `/opsx-apply` | El agente implementa las tareas del `tasks.md`, una a una |
| **Chat de Copilot** | `/opsx-archive` | Archivar el cambio completado y fusionar las delta specs en el spec principal |
| **Terminal** | `openspec --version` | Verificar instalación |
| **Terminal** | `openspec init` | Inicializar en un proyecto |
| **Terminal** | `openspec update` | Regenerar los ficheros de instrucciones tras actualizar la CLI |

> _"Dos sitios. Terminal para instalar y configurar. Chat de Copilot para trabajar. Esa separación es lo que más confunde al principio — casi todo el mundo intenta escribir `/opsx-propose` en la terminal la primera vez. No. Va en el chat de la IA."_

---

### Paso 1 — Punto de partida: Jira (~1 min)

Mostrar un issue real de la instancia demo.

⚠️ *Elegir de antemano un issue pequeño y acotado (una funcionalidad concreta de RCA), y tenerlo creado — [decidir: KAN-XX o RCA-XX]. Ideal: algo visual que se pueda ver funcionar al final de la demo (ej. "añadir badge de 'agotado' en las tarjetas de producto", "añadir filtro por categoría en el catálogo").*

> _"Esto es lo que tendríais cualquiera de vosotros: una tarea en el backlog, escrita en dos frases por un PM. Ambigua, incompleta. Justo lo que un agente odia."_

---

### Paso 2 — El puente Jira → spec: cómo funciona (~5 min)

> _"Ahora quiero convertir esta tarea de Jira en algo que un agente pueda ejecutar sin inventarse la mitad. Hay dos formas de hacerlo."_

#### Opción A — Directa (lo que vamos a hacer en la demo)

Copiar el título y la descripción del issue de Jira y pasárselo a OpenSpec como contexto del propose:

```
/opsx-propose filtro-por-categoria

Contexto del ticket Jira RCA-XX:
Título: Añadir filtro por categoría en el catálogo
Descripción: Como usuario, quiero poder filtrar los productos del catálogo
por categoría (anillos, colgantes, pulseras) para encontrar más rápido
lo que busco.
Criterios de aceptación del PM:
- Se ven las categorías disponibles
- Al seleccionar una, solo se muestran los productos de esa categoría
- Se puede volver a "todas"
```

> _"Le estoy pasando exactamente lo que había en Jira, con copia y pega. No he tenido que reformatear nada. OpenSpec coge esto y genera la propuesta estructurada."_

#### Opción B — Con MCP (mencionarlo, no demostrarlo)

> _"Si tenéis un MCP de Jira configurado en vuestro agente — como el que hemos enseñado en charlas anteriores —, el agente puede leer el ticket directamente. Le decís 'lee el ticket RCA-XX de Jira y propón un cambio con OpenSpec', y se conecta solo. El patrón está documentado para Linear y aplica igual a Jira y Asana. No lo voy a hacer hoy para no complicar la demo, pero el camino está ahí."_

#### Lo que genera OpenSpec

**En pantalla** — mostrar la carpeta creada y abrir cada fichero:

```
openspec/changes/filtro-por-categoria/
├── proposal.md         ← POR QUÉ: intención, alcance, fuera de alcance
├── specs/
│   └── catalogo/
│       └── spec.md     ← QUÉ: la delta spec (ADDED / MODIFIED / REMOVED)
├── design.md           ← CÓMO: enfoque técnico, decisiones de arquitectura
└── tasks.md            ← HACER: checklist de implementación paso a paso
```

**Recorrer cada fichero brevemente** (señalar en pantalla):

| Fichero | Qué contiene | Para qué sirve |
|---|---|---|
| `proposal.md` | Intención del cambio, qué está dentro del alcance y qué no, motivación | Es el "contrato" entre tú y el agente: aquí se negocia el "qué" antes de escribir una línea |
| `specs/<dominio>/spec.md` | Requisitos en formato escenario (GIVEN/WHEN/THEN o SHALL/MUST), **solo los que cambian** | La delta spec — el corazón diferencial de OpenSpec (ver Paso 3) |
| `design.md` | Enfoque técnico: qué componentes se tocan, qué patrones se usan, qué librerías se necesitan | El "cómo" técnico — aquí es donde el agente propone la arquitectura del cambio |
| `tasks.md` | Lista de tareas ordenadas, con checkboxes, que el agente ejecutará una a una | El plan de ejecución — lo que el agente usa como guía durante `/opsx-apply` |

> _"De las dos frases del PM en Jira, OpenSpec ha generado cuatro documentos estructurados. El agente ha leído mi código, ha entendido la arquitectura del proyecto, y ha propuesto un plan. Pero — y esto es lo importante — no ha tocado una sola línea de código todavía. Todo esto es planificación. La pregunta ahora es: ¿me convence este plan?"_

---

### Paso 3 — Revisar la propuesta: en qué fijarse (~4 min)

> _"Este es el paso que separa SDD de vibe coding. En vibe coding, el agente te devuelve código y tú miras si funciona. En SDD, revisas el plan antes de que exista el código. Es más barato corregir un párrafo de Markdown que deshacer 500 líneas."_

#### Checklist de revisión de la propuesta

**En `proposal.md` — comprobar:**
- ¿Ha entendido la intención del cambio? ¿El "por qué" es correcto?
- ¿El alcance (in scope / out of scope) tiene sentido? ¿Ha metido algo que no le pediste? ¿Le falta algo que sí necesitas?
- Si algo no cuadra → corregirlo en el propio fichero o decirle al agente "el alcance está mal, X no debería estar incluido"

**En `design.md` — comprobar:**
- ¿El enfoque técnico es compatible con tu stack? (En RCA: ¿usa Angular y las convenciones del proyecto, o se ha inventado otra cosa?)
- ¿Ha elegido las librerías correctas? ¿Ha añadido dependencias innecesarias?
- Si propone algo que no te convence (ej. un patrón que no usas en el proyecto) → corregir aquí, antes de implementar

**En `tasks.md` — comprobar:**
- ¿Los pasos son concretos y atómicos? ("Crear componente CategoryFilter" es bueno; "Implementar la funcionalidad" es demasiado vago)
- ¿El orden tiene sentido? (Primero el servicio, luego el componente, luego conectarlos)
- ¿Falta algo? (Tests, accesibilidad, actualizar rutas…)

#### La delta spec — el concepto central de OpenSpec

**Abrir `specs/catalogo/spec.md`** y señalar las secciones:

```markdown
## ADDED Requirements

### Requirement: Category Filtering
The catalog page SHALL allow users to filter products by category.

#### Scenario: Filter by category
- GIVEN the user is on the catalog page
- WHEN the user selects a category (rings, pendants, bracelets)
- THEN only products of that category are displayed

#### Scenario: Clear filter
- GIVEN a category filter is active
- WHEN the user selects "all"
- THEN all products are displayed again

## MODIFIED Requirements

### Requirement: Catalog Display
The catalog page SHALL display a category selector above the product grid.
```

> _"Esto es lo que hace diferente a OpenSpec. Fijaos: no ha reescrito la especificación entera del catálogo. Solo dice qué se AÑADE (el filtro) y qué se MODIFICA (el layout del catálogo para incluir el selector). Es un diff de requisitos, como un diff de código. Por eso se llama delta spec."_

**Por qué importa la delta spec** (explicar brevemente):
- **Cuando archivas el cambio** (`/opsx-archive`), OpenSpec fusiona automáticamente estas deltas en el spec principal (`openspec/specs/`). El spec principal siempre refleja el estado actual del sistema.
- **Dos cambios en paralelo** pueden tocar el mismo spec sin conflicto, porque cada uno describe solo su delta — igual que dos ramas pueden tocar el mismo fichero si editan líneas diferentes.
- **El spec crece orgánicamente** con cada cambio archivado, sin que nadie tenga que reescribirlo entero.

> _"Compárad esto con mi spec manual del Bloque 2. En el spec manual, yo escribía todo desde cero cada vez. Si el proyecto cambiaba, tenía que actualizar el spec a mano o se quedaba obsoleto. Aquí, el spec se actualiza solo cada vez que archivas un cambio. Esa es la ganancia: disciplina automatizada."_

#### El contraste clave — enseñar el paralelo

**Poner al lado el `task-rca-28.md` del Bloque 2.**

> _"Esto de aquí —señalar la carpeta de OpenSpec— es exactamente lo que antes hacía a mano —señalar task-rca-28—. La misma información: qué, por qué, criterios, tareas. La diferencia es que ahora tiene estructura impuesta (cuatro ficheros, siempre los mismos), vive en el repo con el código, persiste entre sesiones, y el spec se actualiza solo al archivar. No he perdido control; he ganado disciplina."_

---

### Paso 4 — El agente implementa: cómo ejecutar con Copilot (~5 min)

> _"La propuesta me convence, los specs están bien. Ahora le digo al agente: construye."_

#### Elegir el modelo en Copilot

**Antes de lanzar `/opsx-apply`**, seleccionar el modelo adecuado en el picker de Copilot (menú desplegable en la parte superior del panel de chat en VS Code).

> _"No todos los modelos sirven igual para esto. OpenSpec recomienda modelos de alto razonamiento — modelos que piensan antes de escribir. Para una tarea de implementación con spec, la recomendación es clara."_

**Criterio de selección de modelo para SDD/OpenSpec:**

| Modelo | Cuándo usarlo con OpenSpec | Coste en Copilot |
|---|---|---|
| **Claude Sonnet 4.6** | **Recomendado para la mayoría de tareas.** Buen equilibrio entre razonamiento, velocidad y coste. Es el modelo que mejor relación calidad-precio tiene en Copilot ahora mismo | 1x (sin premium extra) |
| **Claude Opus 4.8** | Para tareas complejas, multi-fichero, o cuando Sonnet se atasca. Más lento pero más profundo | 9x premium requests |
| **GPT-5.4** | Alternativa competitiva a Sonnet. Buena opción si prefieres el ecosistema OpenAI | Variable |
| **Gemini 3.1 Pro** | Cuando necesitas contexto muy grande (muchos ficheros abiertos a la vez) | Variable |

> _"Para esta demo voy a usar [modelo que uses]. Si estáis empezando, Claude Sonnet 4.6 es el más seguro: rápido, barato, y razona bien. Si la tarea es complicada y Sonnet se atasca, subid a Opus."_

⚠️ *Verificar qué modelos tiene disponibles tu plan de Copilot Pro antes de la demo. Los modelos premium consumen "premium requests" con multiplicador (Opus 4.8 = 9x). Copilot Free y Pro básico tienen límites más estrechos.*

#### Preparar el contexto antes de aplicar

> _"Un detalle que marca la diferencia: antes de lanzar la implementación, aseguraos de que el agente tiene el contexto limpio."_

**Buenas prácticas antes de `/opsx-apply`:**
- **Abrir una sesión nueva de chat** (no reutilizar un hilo largo con conversaciones previas). OpenSpec funciona mejor con la ventana de contexto despejada — los artefactos del cambio (`proposal.md`, `specs/`, `design.md`, `tasks.md`) ya contienen todo el contexto que el agente necesita.
- **Tener abierto el proyecto en VS Code** con el workspace apuntando a la raíz (donde vive la carpeta `openspec/`).
- **No hace falta cargar nada más manualmente** — el agente lee los ficheros de OpenSpec automáticamente al ejecutar el comando.

#### Lanzar la implementación

```
/opsx-apply
```

**Lo que pasa** (mostrar en pantalla en tiempo real):
1. El agente lee `tasks.md` del cambio activo
2. Ejecuta las tareas **una a una**, en orden
3. Cada tarea completada se marca con un checkbox ✓ en `tasks.md`
4. Si algo falla o no está claro, el agente pregunta antes de continuar
5. Al terminar todas las tareas, propone archivar

> _"Fijaos en que no le he dado instrucciones vagas. No le he dicho 'hazme un filtro'. Le he dicho 'ejecuta este plan que yo he revisado'. El agente trabaja contra una checklist, no contra su imaginación."_

⚠️ *Si durante la demo el agente tarda mucho o se atasca en una tarea: no entrés en pánico. Comentad en voz alta qué está pasando ("está leyendo el código existente", "está decidiendo dónde crear el componente"). Si se bloquea de verdad, cortad y mostrad el resultado parcial — es una oportunidad para narrar que los agentes no son perfectos y que el spec es lo que te permite retomar donde lo dejó.*

#### Skill recomendada para Copilot: `openspec-sdd`

> _"Un tip extra: existe una skill comunitaria para Copilot que integra todo el flujo de OpenSpec. Se llama `openspec-sdd` y la podéis encontrar en SkillsMP o instalarla directamente."_

La skill `openspec-sdd` es una skill de routing que:
- Enseña a Copilot a reconocer los comandos `/opsx-*` con instrucciones detalladas para cada fase
- Se compone de cuatro sub-skills (una por cada fase: propose, apply, verify, archive)
- La genera automáticamente `openspec init` cuando seleccionas `github-copilot` — ya la tienes en `.github/prompts/` si has hecho el init correctamente
- Si usas la extensión [OpenSpec for Copilot](https://github.com/atman-33/openspec-for-copilot) en VS Code, tienes además un panel visual para gestionar specs, lanzar tareas y archivar desde la barra lateral, sin escribir slash commands

⚠️ *Comprobar antes del miércoles que `openspec init --tools github-copilot` genera correctamente los prompt files en `.github/prompts/` para tu versión de Copilot. Si usas Copilot CLI (en terminal, no en VS Code), tener en cuenta que no consume los `.prompt.md` directamente — los slash commands solo funcionan en las extensiones de IDE (VS Code, JetBrains, Visual Studio).*

---

### Paso 5 — Cierre del ciclo: archivar (~2 min)

Una vez que el agente ha completado todas las tareas:

```
/opsx-archive
```

**Lo que pasa:**
1. OpenSpec **fusiona las delta specs** del cambio en el spec principal (`openspec/specs/`)
2. **Mueve la carpeta del cambio** a `openspec/changes/archive/2026-08-12-filtro-por-categoria/`
3. El spec principal ahora refleja el estado actualizado del sistema — incluye el filtro por categoría como comportamiento documentado
4. El escenario queda limpio para el siguiente cambio

> _"Ese es el ciclo completo: idea en Jira → propuesta estructurada → revisión humana → código → archivo. El agente ha escrito el código. Yo he dirigido el qué y he revisado el plan. Y el spec del proyecto ha crecido solo, sin que yo haya tenido que reescribir nada a mano."_

**Frase que debe quedar:**

> _"El agente escribió el código. Yo dirigí el qué. Y el spec se actualizó solo. Ese es el reparto de trabajo del que va toda esta charla — y lo acabáis de ver funcionando de una tarea de Jira a código real."_

---

## Bloque 5 — Cuándo cada cosa — 5 min

> _"Vale, ¿y qué me llevo yo el lunes? No 'instala OpenSpec'. Me llevo un criterio."_

| Situación | Qué usar |
|---|---|
| Tarea pequeña, bien acotada, la tienes clara | **Spec manual** — el overhead de una herramienta no compensa |
| Proyecto que ya existe, cambios iterativos, quieres ligereza sin atarte | **OpenSpec** |
| Empiezas de cero, quieres el estándar con más comunidad, saltas entre stacks | **Spec Kit** |
| Tu equipo ya vive dentro de AWS y quieres rigor formal e IDE integrado | **Kiro** |

**La advertencia honesta — cuándo NO usar spec formal:**

> _"Y ahora la parte que las páginas de marketing no os cuentan: para tareas triviales, montar un spec formal es contraproducente. Genera más papeleo que valor. Corregir un typo o cambiar un color no necesita una constitución de proyecto. El propio Martin Fowler lo señala: para tareas pequeñas, la disciplina del spec pesa más de lo que ayuda. La regla es sencilla: cuanto más grande y más ambigua es la tarea, más te salva el spec. Cuanto más pequeña y clara, más te estorba."_

**Frase que debe quedar:**

> _"El spec no es un impuesto que pagas siempre. Es un seguro que contratas cuando la tarea es lo bastante grande como para que valga la pena. Saber cuándo NO usarlo es tan importante como saber usarlo."_

---

## Bloque 6 — Qué se lleva cada rol — 3 min

> _"Y aquí está lo que os prometí a los que no programáis. Esto no era una charla solo para devs."_

| Rol | Qué te llevas |
|---|---|
| **Developer** | Adopta un flujo de spec, pero empieza ligero — un `.md` a mano o OpenSpec. La herramienta no sustituye la disciplina; la refuerza |
| **PM / Project Manager** | El spec es el punto donde se negocia y se cierra el "qué" *antes* de construir. Un issue de Jira de dos frases es exactamente el problema que hemos resuelto hoy: escribir mejor la tarea es la mitad del trabajo |
| **Cualquier perfil que use IA** | Todo esto es, en el fondo, cómo se le dan instrucciones sin ambigüedad a un agente. La lección — "di qué quieres, con criterios de éxito, antes de pedir el resultado" — vale para pedirle un correo, un análisis o un resumen a cualquier IA. El spec es esa idea, llevada al código |

**Frase que debe quedar:**

> _"Programéis o no, todos le pedís cosas a una IA. Y todos os beneficiáis de la misma disciplina: decir el qué y el porqué antes de pedir el cómo."_

---

## Cierre — 4 min

> _"Primera idea: el cuello de botella se ha movido. Cuando la IA escribe el código, el trabajo pasa a ser saber pedir. Los agentes de esta semana lo dejan claro."_
>
> _"Segunda idea: pedir bien tiene disciplina y tiene nombre — SDD. Y desde este año tiene herramientas: OpenSpec si quieres ligereza, Spec Kit si quieres el estándar, Kiro si vives en AWS. Manual contra herramienta es un espectro, no una guerra."_
>
> _"Tercera idea: la habéis visto funcionar de una tarea de Jira a código real, con el agente escribiendo y yo dirigiendo el qué."_
>
> _"Y esto cierra el círculo con lo primero que os enseñé en la serie. El SDD era la primera capa del arnés completo: el 'qué construir'. Hoy lo hemos visto crecido, dos años después, con herramientas de verdad. La pieza más antigua de la serie es también la que más ha madurado."_

**Frase final:**

> _"La próxima vez que abráis un chat de IA para pedirle algo — código o cualquier cosa — la pregunta ya no es '¿qué le escribo?'. Es '¿le he dicho con claridad qué quiero y cómo sabré que lo ha hecho bien?'. Eso es un spec. Y ahora ya sabéis hacerlo a mano y con herramientas."_

---

## Checklist antes del miércoles

- [ ] **Preparar el entorno de la demo end-to-end:**
  - [ ] RCA (Angular) funcionando en local, sin errores de compilación
  - [ ] `node --version` ≥ 20.19.0
  - [ ] `npm install -g @fission-ai/openspec@latest` ejecutado y verificado (`openspec --version`)
  - [ ] `openspec init` ejecutado en el proyecto RCA con `github-copilot` seleccionado
  - [ ] Verificar que los ficheros `.github/prompts/opsx-*.prompt.md` se han generado
  - [ ] Verificar que `/opsx-propose` aparece en el menú de slash commands de Copilot en VS Code
  - [ ] Instancia Jira demo accesible (`da-ju-ia-talks.atlassian.net`)
- [ ] **Elegir el issue de Jira de la demo** — pequeño, acotado y visual (que se vea funcionar al final). Tenerlo creado de antemano en el proyecto RCA. Ideal: algo que se resuelva en 2-3 ficheros (componente + servicio + template)
- [ ] **Elegir el modelo de Copilot para la demo** — verificar qué modelos tienes disponibles en tu plan (Claude Sonnet 4.6 recomendado; si quieres demostrar músculo, Opus 4.8). Comprobar que no te quedas sin premium requests a mitad de demo
- [ ] **Ensayar la demo completa al menos una vez** — cronometrar los 20 min; saber qué pasos se pueden saltar si va larga. Especialmente: comprobar que `/opsx-apply` ejecuta las tareas correctamente contra RCA con el modelo elegido
- [ ] **Plan B para la demo** — grabación de respaldo o capturas de cada paso (instalación, propuesta generada, delta spec, implementación). Si falla en vivo, reencuadrar como aprendizaje sobre los límites reales de los agentes
- [ ] **Verificar el estado actual de los tres tools** — versiones/favoritos de OpenSpec, Spec Kit y Kiro por si han cambiado; el dato de JetBrains (90% / 13%)
- [ ] **Confirmar la referencia del refresco** — cuál es la grabación donde explicaste SDD en detalle (Charla 7 o la de SDD en Angular), para citarla en el Bloque 1
- [ ] **Tener a mano `task-rca-28.md`** para el contraste manual vs herramienta del Bloque 2 y Paso 3
- [ ] **Preparar el ejemplo EARS adaptado a RCA** para el Bloque 3 (el del carrito y el stock, o el que prefieras)
- [ ] **Avisar en la apertura** de que es una charla técnica con demo — señalizar el cambio de registro
- [ ] **Comprobar la extensión OpenSpec for Copilot** (opcional) — si decides mencionarla, tenerla instalada y verificar que funciona con tu versión de VS Code

### Si hace falta recortar a ~45 min

Orden de recorte sugerido (de menos a más prioritario mantener):
1. Reducir el Bloque 3 a **dos** arquetipos (OpenSpec + Kiro, los más opuestos), dejando Spec Kit como una mención de la tabla (~-4 min)
2. Acortar el Paso 0 de la demo (instalación): hacer la instalación con el `openspec init` ya ejecutado de antemano, y solo mostrar el resultado del árbol de ficheros (~-2 min)
3. Saltar el Paso 5 (archivar) si va larga — mencionarlo verbalmente sin ejecutarlo (~-2 min)
4. Fusionar Bloque 5 y Bloque 6 en un único cierre práctico (~-3 min)
5. **Mantener intactos:** Apertura (el gancho), el refresco del Bloque 1, el Paso 2 (puente Jira→spec), el Paso 3 (revisión con delta spec), y el Paso 4 (implementación con Copilot) — sin estos, la charla pierde su razón de ser
