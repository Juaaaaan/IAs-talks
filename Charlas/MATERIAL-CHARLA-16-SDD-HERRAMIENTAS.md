# Material Charla 16 — SDD con herramientas: spec manual vs OpenSpec

---

## Por qué esta charla

El 90% de los desarrolladores ya usa IA en su trabajo. Pero solo el 13% la usa en todo el ciclo de desarrollo (encuesta JetBrains, enero 2026, 11.000 desarrolladores). Casi todos hemos adoptado la IA para escribir trozos sueltos de código — autocompletar una función, generar un test, resolver un error. Muy pocos la usamos para gobernar un proyecto entero: definir qué se construye, planificar la arquitectura, desglosar las tareas y mantener la coherencia entre sesiones.

Ese salto — del 90% al 13% — es exactamente lo que el Spec-Driven Development (SDD) intenta cerrar. Y 2026 ha sido el año en que ha dejado de ser una idea de nicho para convertirse en un ecosistema con herramientas dedicadas.

La charla de esta semana fue técnica, con pantalla compartida y demo en directo. Se hizo una demo real del ciclo completo: de un ticket de Jira (RCA-21, Cart Drawer) a código implementado, usando OpenSpec con Claude Code sobre el proyecto Resin Craft Art (Angular).

Este documento amplía y profundiza todo lo que se vio en la sesión.

---

## Vibe Coding vs. Spec-Driven Development

Antes de entrar en herramientas, conviene tener clara la diferencia entre las dos formas de trabajar con un agente de IA:

**Vibe coding** es lo que hace la mayoría: abrir un chat, escribir un prompt vago ("hazme un componente de carrito") y esperar que salga algo razonable. Funciona bien para tareas aisladas y pequeñas — un script de diez líneas, una función puntual. Se desmorona en cuanto el proyecto crece, pasan los días, o interviene más de una persona: el agente no recuerda lo que hizo ayer, no conoce las convenciones del proyecto, y no sabe cómo encaja su trabajo con el del resto del equipo.

**Spec-Driven Development (SDD)** invierte el orden: escribes la intención de forma estructurada — qué se va a construir, por qué, cuáles son los criterios de aceptación — *antes* de que se escriba una sola línea de código. El agente ejecuta contra ese spec, no contra su imaginación. La especificación es la fuente de verdad, no el código.

La metáfora es sencilla: no le das a un contratista "hazme una casa, ya te apañas". Le das planos. El SDD son los planos para agentes de IA.

---

## Anatomía de un spec manual

Un spec manual es, en su forma más simple, un fichero de texto (`.md`) que vive en el repositorio al lado del código. No requiere instalar nada ni depende de ninguna herramienta. Lo escribes tú, lo revisas tú, y el agente lo ejecuta.

Las cinco partes de un buen spec:

| Parte | Qué contiene | Por qué importa |
|---|---|---|
| **Qué / objetivo** | La funcionalidad en lenguaje claro, sin el "cómo" técnico todavía | El agente necesita saber la meta, no adivinarla |
| **Por qué** | El contexto y la intención detrás del cambio | Sin el porqué, el agente toma decisiones que rompen el sentido del proyecto |
| **Criterios de aceptación** | Cuándo se considera "hecho", de forma verificable | Es lo que separa "creo que funciona" de "sé que funciona" |
| **Contexto técnico** | Stack, patrones del proyecto, restricciones | Evita que el agente reinvente lo que ya existe o use convenciones incompatibles |
| **Tareas** | El desglose paso a paso | El agente ejecuta la lista en orden, no improvisa la secuencia |

**Ventajas del spec manual:**
- Control total — cada línea la has decidido tú
- Cero dependencias — no instalas nada, no dependes de ningún vendor
- Lo entiendes entero — no hay caja negra

**Límites del spec manual:**
- Toda la disciplina la pones tú — nada te obliga a incluir los criterios de aceptación; si un día tienes prisa, los saltas
- No hay estructura impuesta — cada spec puede acabar con un formato distinto
- Se degrada con el tiempo — cuando el proyecto evoluciona, actualizar los specs a mano es trabajo que casi nadie hace, y el spec deja de reflejar la realidad

El spec manual es SDD con las manos. Funciona perfectamente mientras tengas la disciplina de mantenerlo. El problema nunca es empezar un spec. Es mantenerlo vivo cuando el proyecto evoluciona y hay prisa. Ese es precisamente el problema que resuelven las herramientas de SDD.

---

## El ecosistema SDD 2026: tres arquetipos

Este año han aparecido (o madurado) tres herramientas que representan tres filosofías opuestas de cómo abordar el SDD con asistencia de IA. No hay un ganador — hay un espectro entre cuánta estructura necesitas y cuánta libertad estás dispuesto a ceder.

### OpenSpec — el ligero

OpenSpec es una capa ligera de SDD, open-source, pensada especialmente para proyectos que ya existen (brownfield). Su idea diferencial son las **delta specs**: en vez de reescribir toda la especificación cada vez que cambias algo, describes solo lo que cambia — secciones ADDED / MODIFIED / REMOVED sobre un único spec vivo que actúa como fuente de verdad.

Cada cambio vive en su propia carpeta con cuatro documentos: propuesta (proposal), especificación (specs), diseño técnico (design) y lista de tareas (tasks). Funciona con más de 20 herramientas de IA (Copilot, Claude Code, Cursor, Cline, Devin, Gemini CLI…) vía slash commands, sin lock-in. No tiene servidor, no hace peticiones de red y no requiere claves de API — solo Node.js 20.19+ y un `npm install`.

- **Repositorio:** [github.com/Fission-AI/OpenSpec](https://github.com/Fission-AI/OpenSpec)
- **Licencia:** MIT
- **Coste:** Gratis

### Spec Kit (GitHub) — el estándar de comunidad

Spec Kit es la opción más adoptada (más de 100.000 estrellas en GitHub), una CLI open-source que se instala con `pip install specify`. Su flujo tiene cinco fases: Constitución → Especificar → Planificar → Tareas → Implementar. La "constitución" son las reglas no negociables del proyecto que todo spec futuro respeta — el equivalente a un `AGENTS.md` con esteroides.

Funciona con más de 30 agentes, genera specs en Markdown puro que viven en el repo, y tiene la mayor comunidad de todas las opciones. El peaje: las specs son estáticas (no se actualizan solas tras la implementación) y genera mucho Markdown — para tareas pequeñas, el overhead es desproporcionado.

- **Repositorio:** [github.com/speckit/speckit](https://github.com/speckit/speckit)
- **Licencia:** MIT
- **Coste:** Gratis

### Kiro (AWS) — el integrado

Kiro no es una CLI: es un IDE entero construido alrededor del concepto de spec (basado en VS Code, con CLI y versión web también). Es el reemplazo del difunto Amazon Q Developer. Las specs son objetos de primera clase en el editor, no ficheros que gestionas aparte.

Usa notación EARS (Easy Approach to Requirements Syntax), un formato de requisitos de grado aeroespacial (originado en Rolls-Royce) que fuerza frases testeables y sin ambigüedad. Ejemplo adaptado a un e-commerce:

> *"CUANDO un cliente añade una pieza agotada al carrito, EL SISTEMA DEBE mostrar un aviso de 'sin stock' y deshabilitar el botón de compra."*

Su característica más diferencial son los **Agent Hooks**: automatizaciones que se disparan solas cuando cambias el código (actualizan tests, documentación…), creando un bucle bidireccional spec↔código que las otras herramientas no tienen. El peaje es significativo: lock-in completo (specs en `.kiro/`, modelos limitados a AWS Bedrock, no puedes traer tus propias claves de API), y un modelo de precios por créditos que ha generado bastante rechazo en la comunidad de desarrolladores.

- **Web:** [kiro.dev](https://kiro.dev)
- **Licencia:** Propietaria
- **Coste:** Créditos con markup sobre el coste base de los modelos

### Tabla comparativa

| Criterio | Spec manual | OpenSpec | Spec Kit | Kiro |
|---|---|---|---|---|
| **Filosofía** | Tú y un `.md` | Ligero, cambios incrementales | Estándar de comunidad, CLI | IDE integrado y opinado |
| **Spec vivo o estático** | Lo mantienes tú | Vivo (delta specs) | Estático hasta que lo actualizas | Vivo (con Agent Hooks) |
| **Lock-in** | Ninguno | Ninguno | Ninguno | Alto (Bedrock + IDE) |
| **Mejor para** | Tareas pequeñas, control total | Proyectos existentes (brownfield) | Empezar de cero, saltar entre stacks | Equipos ya dentro del ecosistema AWS |
| **Coste** | Gratis | Gratis | Gratis | Créditos con markup |
| **Funciona con Copilot / Claude Code** | Sí | Sí | Sí | Solo dentro de Kiro |

---

## OpenSpec en profundidad: instalación, configuración y uso

### Requisitos previos

- **Node.js 20.19.0 o superior.** Verificar:
  ```bash
  node --version   # debe ser >= 20.19.0
  ```

### Instalación

```bash
npm install -g @fission-ai/openspec@latest
openspec --version   # verificar
```

Para entornos corporativos, es recomendable desactivar la telemetría:
```bash
export OPENSPEC_TELEMETRY=0
# o bien
export DO_NOT_TRACK=1
```

OpenSpec es una herramienta CLI local: no tiene servidor, no escucha en ningún puerto de red y no tiene ningún daemon privilegiado. Lee y escribe Markdown dentro del directorio donde la ejecutas, con tus propios permisos de usuario. Con la telemetría desactivada, no sale ningún dato de tu máquina.

### Inicialización en un proyecto

```bash
cd mi-proyecto
openspec init
```

Durante el `init`, OpenSpec te pregunta:
1. **Qué herramienta de IA usas** — seleccionar `github-copilot`, `claude-code`, `cursor`, u otra. OpenSpec genera ficheros diferentes según la herramienta.
2. **Si quieres configurar el cloud coding agent** (solo para Copilot — el agente de GitHub que trabaja en background). Para uso local, no hace falta.
3. **Si quieres crear un `config.yaml`** con contexto del proyecto (nombre, stack, convenciones). Recomendable — el agente usa este contexto al generar las propuestas.

### Qué genera `openspec init` en tu proyecto

```
openspec/
├── config.yaml          ← Configuración del proyecto
│                          Contiene: nombre del proyecto, stack técnico,
│                          convenciones de código, contexto que el agente
│                          usa al generar propuestas. Editable a mano.
│
├── specs/               ← Fuente de verdad: el estado actual del sistema
│                          Vacío al inicio. Se llena automáticamente cada
│                          vez que archivas un cambio completado (/opsx-archive).
│                          Aquí vive el "spec principal" — el documento que
│                          describe qué hace tu sistema ahora mismo.
│
├── changes/             ← Propuestas de cambio activas
│                          Vacío al inicio. Cada vez que propones un cambio
│                          (/opsx-propose), se crea una subcarpeta aquí con
│                          los cuatro documentos del cambio (proposal, specs,
│                          design, tasks). Puede haber varios cambios activos
│                          en paralelo.
│
└── AGENTS.md            ← Instrucciones para el agente de IA
                           Fichero que OpenSpec genera para que tu agente
                           (sea Copilot, Claude Code u otro) entienda el
                           flujo SDD y sepa dónde buscar los specs.
```

**Si seleccionaste `github-copilot`**, además se genera:

```
.github/
└── prompts/             ← Slash commands para Copilot en VS Code
    ├── opsx-propose.prompt.md    ← Define /opsx-propose
    ├── opsx-explore.prompt.md    ← Define /opsx-explore
    ├── opsx-apply.prompt.md      ← Define /opsx-apply
    └── opsx-archive.prompt.md    ← Define /opsx-archive
```

Estos ficheros `.prompt.md` son lo que permite escribir `/opsx-propose` en el chat de Copilot y que Copilot sepa qué hacer. OpenSpec le ha enseñado los comandos.

**Si seleccionaste `claude-code`**, se genera un fichero `CLAUDE.md` (o se integra con el existente) que contiene las instrucciones equivalentes para Claude Code.

Todo es Markdown. Todo vive en el repo. Todo se versiona con Git. No hay base de datos, no hay servidor, no hay nada opaco.

### Referencia de comandos de OpenSpec

| Dónde se ejecuta | Comando | Qué hace |
|---|---|---|
| **Chat del agente** (Copilot / Claude Code) | `/opsx-explore` | Pensar en voz alta con el agente antes de proponer nada. Sin artefactos, sin código — solo exploración y discusión. Útil para entender el problema antes de comprometerse con una propuesta. |
| **Chat del agente** | `/opsx-propose <nombre>` | Crear una propuesta de cambio completa. Genera una carpeta en `openspec/changes/<nombre>/` con cuatro documentos: `proposal.md`, `specs/`, `design.md` y `tasks.md`. El agente lee tu código, entiende la arquitectura y propone un plan estructurado. |
| **Chat del agente** | `/opsx-apply` | El agente implementa las tareas del `tasks.md` del cambio activo, una a una, en orden. Cada tarea completada se marca con un checkbox. Si algo falla o no está claro, pregunta antes de continuar. |
| **Chat del agente** | `/opsx-archive` | Archivar el cambio completado. Fusiona las delta specs en el spec principal (`openspec/specs/`), mueve la carpeta del cambio a `archive/`, y deja el escenario limpio para el siguiente cambio. |
| **Terminal** | `openspec --version` | Verificar la versión instalada. |
| **Terminal** | `openspec init` | Inicializar OpenSpec en un proyecto. Genera la estructura de carpetas y los ficheros de instrucciones para tu agente. |
| **Terminal** | `openspec update` | Regenerar los ficheros de instrucciones tras actualizar la CLI. Importante ejecutarlo después de un `npm install -g @fission-ai/openspec@latest`. |
| **Terminal** | `openspec config profile` | Configurar o revisar tu perfil global (herramienta preferida, workflows activos). |

**Nota importante sobre formato de comandos:** en GitHub Copilot los slash commands se escriben con guion (`/opsx-propose`), no con dos puntos (`/opsx:propose`). La documentación oficial de OpenSpec usa el formato con dos puntos como nombre canónico (agnóstico de herramienta), pero Copilot usa guiones porque así es como VS Code registra los custom prompts. Los ficheros generados por `openspec init` ya usan la forma correcta para tu herramienta — no hay que cambiar nada.

---

## Ejemplo 1: Flujo completo con Claude Code

Este es el flujo que se demostró en la charla, usando Claude Code como agente y RCA-21 (Cart Drawer) como tarea.

### 1. Inicializar OpenSpec para Claude Code

```bash
cd rca
openspec init
# Seleccionar: claude-code
# Aceptar config.yaml con contexto del proyecto
```

### 2. Proponer un cambio desde un ticket de Jira

En el chat de Claude Code, escribir:

```
Usa OpenSpec para proponer un cambio. Lee las instrucciones de openspec/AGENTS.md.

Contexto del ticket Jira RCA-21:
Título: Cart Drawer
Descripción: Implementar un panel lateral (drawer) que muestre el contenido
del carrito de compra. Se abre al hacer clic en el icono del carrito
en la barra de navegación y permite ver los productos añadidos,
modificar cantidades y proceder al checkout.

Nombre del cambio: cart-drawer
```

Claude Code lee el AGENTS.md, entiende el flujo de OpenSpec, y genera la carpeta `openspec/changes/cart-drawer/` con los cuatro documentos.

### 3. Revisar la propuesta

Abrir y revisar cada fichero antes de implementar:
- **`proposal.md`** — ¿Ha entendido la intención? ¿El alcance es correcto?
- **`design.md`** — ¿El enfoque técnico usa Angular y las convenciones de RCA?
- **`specs/`** — ¿Los escenarios GIVEN/WHEN/THEN cubren todos los casos?
- **`tasks.md`** — ¿Los pasos son concretos, atómicos y en el orden correcto?

Si algo no cuadra, decirle a Claude Code qué corregir antes de implementar. Es más barato corregir un párrafo de Markdown que deshacer 500 líneas de código.

### 4. Implementar

```
Aplica el cambio de OpenSpec cart-drawer. Sigue las instrucciones
de openspec/AGENTS.md para el flujo de apply.
```

Claude Code lee `tasks.md` y ejecuta las tareas una a una.

### 5. Archivar

```
Archiva el cambio cart-drawer de OpenSpec siguiendo las instrucciones
de openspec/AGENTS.md.
```

Las delta specs se fusionan en el spec principal. El cambio se mueve a `archive/`.

### 6. Git (manual — aquí se para OpenSpec)

```bash
git checkout -b feat/cart-drawer
git add .
git commit -m "feat(cart): implementar cart drawer (RCA-21)"
git push origin feat/cart-drawer
# Abrir PR → code review → merge
```

---

## Ejemplo 2: Flujo completo con GitHub Copilot

El mismo flujo, pero usando Copilot en VS Code con los slash commands nativos.

### 1. Inicializar OpenSpec para Copilot

```bash
cd rca
openspec init
# Seleccionar: github-copilot
# Responder "no" al cloud coding agent
# Aceptar config.yaml
```

Verificar que los ficheros `.github/prompts/opsx-*.prompt.md` se han generado y que `/opsx-propose` aparece en el menú de slash commands del panel de chat de Copilot en VS Code.

### 2. Proponer un cambio

En el panel de chat de Copilot (VS Code), escribir:

```
/opsx-propose cart-drawer

Contexto del ticket Jira RCA-21:
Título: Cart Drawer
Descripción: Implementar un panel lateral (drawer) que muestre el contenido
del carrito de compra. Se abre al hacer clic en el icono del carrito
en la barra de navegación y permite ver los productos añadidos,
modificar cantidades y proceder al checkout.
```

Copilot lee los prompt files de OpenSpec y genera la propuesta estructurada.

### 3. Revisar la propuesta

Igual que con Claude Code: abrir los cuatro ficheros generados y revisar antes de implementar.

### 4. Seleccionar el modelo adecuado

Antes de lanzar la implementación, seleccionar el modelo en el picker de Copilot (menú desplegable en la parte superior del panel de chat):

| Modelo | Cuándo usarlo | Coste en Copilot |
|---|---|---|
| **Claude Sonnet 4.6** | Recomendado para la mayoría de tareas. Buen equilibrio entre razonamiento, velocidad y coste | 1x (sin premium extra) |
| **Claude Opus 4.8** | Para tareas complejas, multi-fichero, o cuando Sonnet se atasca | 9x premium requests |
| **GPT-5.4** | Alternativa competitiva a Sonnet | Variable |
| **Gemini 3.1 Pro** | Cuando necesitas un contexto muy grande | Variable |

**Consejo:** Claude Sonnet 4.6 es la opción más segura para empezar. Si la tarea es complicada y Sonnet se atasca, subir a Opus 4.8 — pero tener en cuenta que cada request de Opus consume 9x del cupo de premium requests.

### 5. Implementar

Abrir una sesión nueva de chat (contexto limpio) y escribir:

```
/opsx-apply
```

Copilot lee `tasks.md` y ejecuta las tareas una a una.

### 6. Archivar

```
/opsx-archive
```

### 7. Git (manual)

Igual que con Claude Code. OpenSpec ha terminado; Git toma el relevo.

---

## La delta spec: el concepto central de OpenSpec

La delta spec es lo que diferencia a OpenSpec del resto de herramientas. En vez de mantener un documento de especificación monolítico que hay que reescribir cada vez que algo cambia, cada cambio describe solo su diferencia respecto al estado actual.

Un ejemplo concreto. Supón que quieres añadir un filtro por categoría al catálogo de RCA. La delta spec no reescribe toda la especificación del catálogo — solo dice qué se añade y qué se modifica:

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

Es un diff de requisitos, como un diff de código. Cuando archivas el cambio (`/opsx-archive`), OpenSpec fusiona automáticamente estas deltas en el spec principal (`openspec/specs/`). El spec principal siempre refleja el estado actual del sistema, sin que nadie tenga que reescribirlo entero.

Dos cambios en paralelo pueden tocar el mismo spec sin conflicto, porque cada uno describe solo su delta — igual que dos ramas de Git pueden tocar el mismo fichero si editan líneas diferentes. El spec crece orgánicamente con cada cambio archivado.

---

## Dónde se para OpenSpec: el ciclo completo

Un punto que generó preguntas en la charla y que conviene dejar claro: OpenSpec gobierna el ciclo de *qué construir y cómo*, pero se para ahí. Todo lo que viene después es Git estándar, manual, como siempre.

```
┌─────────────────────────────────────────────────┐
│  OpenSpec (qué construir y cómo)                │
│                                                 │
│  /opsx-propose → revisar → /opsx-apply → /opsx-archive  │
└─────────────────────┬───────────────────────────┘
                      │
                      ▼  ← aquí se para OpenSpec
┌─────────────────────────────────────────────────┐
│  Git (cómo gestionas tu repositorio)            │
│                                                 │
│  git checkout -b feat/nombre-feature            │
│  git add . && git commit                        │
│  git push → abrir PR → code review → merge      │
└─────────────────────────────────────────────────┘
```

OpenSpec te dice qué construir. Git te dice cómo lo gestionas. Son dos flujos separados que no se pisan. Cada equipo tiene su forma de trabajar con ramas (trunk-based, GitFlow, feature branches) y OpenSpec no se mete ahí. La última palabra — subirlo, abrir la PR, mergearlo — sigue siendo del desarrollador.

Si mañana quieres hacer otra tarea con OpenSpec, el flujo es exactamente el mismo: otro propose, otro apply, otro archive. Cada tarea genera su carpeta de cambio, su delta spec, y al archivar se fusiona con el spec principal. El spec va creciendo tarea a tarea.

---

## Criterio práctico: cuándo usar cada cosa

| Situación | Qué usar |
|---|---|
| Tarea pequeña, bien acotada, la tienes clara (ej. cambiar un color, corregir un typo) | **Spec manual o nada** — el overhead de una herramienta no compensa |
| Proyecto que ya existe, cambios iterativos, quieres ligereza sin atarte a ningún vendor | **OpenSpec** |
| Empiezas de cero, quieres el estándar con más comunidad, saltas entre stacks | **Spec Kit** |
| Tu equipo ya vive dentro del ecosistema AWS y quieres rigor formal con IDE integrado | **Kiro** |

La regla de oro es sencilla: cuanto más grande y más ambigua es la tarea, más te salva el spec. Cuanto más pequeña y clara, más te estorba. El spec no es un impuesto que pagas siempre — es un seguro que contratas cuando la tarea es lo bastante grande como para que valga la pena. Saber cuándo NO usarlo es tan importante como saber usarlo.

---

## Consideraciones de seguridad para uso corporativo

Si quieres usar OpenSpec en un entorno corporativo, estas son las consideraciones relevantes:

### OpenSpec CLI

**Riesgo: bajo.** OpenSpec es una herramienta CLI local que no tiene servidor, no escucha en ningún puerto de red y no tiene ningún daemon privilegiado. Lee y escribe Markdown dentro del directorio donde la ejecutas, con tus propios permisos de usuario. El script `postinstall.js` solo imprime una línea sugiriendo autocompletado de shell — no hace peticiones de red, no escribe ficheros y no ejecuta ningún shell. Cualquier input del usuario se pasa como array de argumentos con `shell: false`, lo que previene inyección de comandos.

La telemetría envía solo el nombre del comando ejecutado, la versión de OpenSpec y un UUID generado localmente al azar. No envía rutas de ficheros, contenido de ficheros, variables de entorno ni hostname, y la captura de IP está explícitamente deshabilitada. Se desactiva con `OPENSPEC_TELEMETRY=0`.

**Recomendación:** instalar con telemetría desactivada. Si IT exige whitelist de paquetes npm, solicitar aprobación para `@fission-ai/openspec`.

### MCP de Jira

**Riesgo: depende de la instancia.** El MCP de Jira implica que tu agente de IA lee datos reales de tu instancia de Jira (títulos de tickets, descripciones, comentarios, nombres de personas asignadas). Contra una instancia de demo sin datos reales no hay riesgo. Contra la instancia corporativa con datos de clientes de banca/seguros, los datos viajan al modelo de IA (Copilot vía Azure, Claude Code vía Anthropic), lo que requiere aprobación de IT/seguridad.

**Recomendación:** para demos y formación, usar siempre la instancia demo. Para uso contra la instancia corporativa, consultar con IT/seguridad antes de conectar un agente de IA a datos reales de clientes.

### Copilot en entorno corporativo

Si Copilot ya está aprobado como herramienta corporativa, no hay acción adicional necesaria — OpenSpec no añade riesgo sobre Copilot porque toda la ejecución pasa por Copilot.

---

## Qué se lleva cada rol

| Rol | Qué te llevas |
|---|---|
| **Developer** | Adopta un flujo de spec, pero empieza ligero — un `.md` a mano o OpenSpec. La herramienta no sustituye la disciplina; la refuerza. El ciclo completo de la demo (Jira → spec → código → PR) es reproducible mañana mismo con cualquier ticket del backlog. |
| **PM / Project Manager** | El spec es el punto donde se negocia y se cierra el "qué" antes de construir. Un issue de Jira de dos frases es exactamente el problema que se resolvió en la demo: escribir mejor la tarea es la mitad del trabajo. Cuanto más claro sea el ticket, mejor será el spec que genera OpenSpec, y mejor será el código que escribe el agente. |
| **Cualquier perfil que use IA** | Todo esto es, en el fondo, cómo se le dan instrucciones sin ambigüedad a un agente. La disciplina — "di qué quieres, con criterios de éxito, antes de pedir el resultado" — vale exactamente igual para pedirle un correo, un análisis, un resumen o una presentación a cualquier IA. El spec es esa idea, llevada al código. |

---

## Glosario

- **SDD (Spec-Driven Development):** metodología en la que se escribe una especificación estructurada antes de que el agente de IA escriba código. La especificación es la fuente de verdad.
- **Vibe coding:** estilo de trabajo en el que se le da un prompt vago a la IA y se espera que el resultado sea adecuado. Funciona para tareas pequeñas; se degrada con la complejidad.
- **Delta spec:** en OpenSpec, la especificación parcial que describe solo lo que cambia (ADDED / MODIFIED / REMOVED) respecto al estado actual del sistema. Al archivar, se fusiona con el spec principal.
- **Spec principal (Main Spec):** el documento en `openspec/specs/` que refleja el estado actual completo del sistema. Se actualiza automáticamente al archivar cada cambio.
- **OpenSpec:** herramienta CLI open-source de SDD, ligera, local, sin servidor. Funciona con más de 20 agentes de IA.
- **Spec Kit:** CLI open-source de SDD, la más adoptada (>100k estrellas en GitHub). Flujo de cinco fases con "constitución" del proyecto.
- **Kiro:** IDE de AWS construido alrededor del concepto de spec. Usa notación EARS y Agent Hooks. Lock-in alto.
- **EARS (Easy Approach to Requirements Syntax):** formato de requisitos de grado aeroespacial (Rolls-Royce) que fuerza frases testeables y sin ambigüedad.
- **Agent Hooks:** en Kiro, automatizaciones que se disparan cuando el código cambia, actualizando tests y documentación automáticamente.
- **Slash command:** comando que se escribe en el chat de una herramienta de IA (ej. `/opsx-propose`) para activar un comportamiento específico definido por ficheros de instrucciones.

---

## Recursos

### OpenSpec
- Repositorio oficial: [github.com/Fission-AI/OpenSpec](https://github.com/Fission-AI/OpenSpec)
- Documentación de la CLI: [github.com/Fission-AI/OpenSpec/blob/main/docs/cli.md](https://github.com/Fission-AI/OpenSpec/blob/main/docs/cli.md)
- Política de seguridad oficial: [github.com/Fission-AI/OpenSpec/security](https://github.com/Fission-AI/OpenSpec/security)
- Paquete npm: [npmjs.com/package/@fission-ai/openspec](https://www.npmjs.com/package/@fission-ai/openspec)
- Extensión para Copilot en VS Code: [github.com/atman-33/openspec-for-copilot](https://github.com/atman-33/openspec-for-copilot)

### Spec Kit
- Repositorio oficial: [github.com/speckit/speckit](https://github.com/speckit/speckit)

### Kiro
- Web oficial: [kiro.dev](https://kiro.dev)

### SDD — Lecturas de fondo
- Dato JetBrains (90% / 13%): [JetBrains Developer Ecosystem Survey 2026](https://www.jetbrains.com/lp/devecosystem-2026/)

### Documentos previos de la serie
- Guion completo de la Charla 16 (`Charlas/guiones/guion-charla-16.md` en el vault)
- Demo realizada sobre el issue RCA-21 (Cart Drawer): [da-ju-ia-talks.atlassian.net/browse/RCA-21](https://da-ju-ia-talks.atlassian.net/browse/RCA-21)
- Charla 7 — Skills y MCPs (primera vez que se introdujo SDD y el concepto del "arnés completo")
