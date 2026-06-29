# Guión Charla 8 — Instruyendo a la IA: `.github/` y `.claude/`

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|--------|-----------|--------|
| Apertura | Puente desde Charla 7 + aclaración anticipada | 2 min |
| Bloque 1 | El problema: la IA sin contexto | 3 min |
| Bloque 2 | La solución: ficheros de instrucciones | 5 min |
| Bloque 3 | `.github/` para Copilot — estructura completa | 5 min |
| Demo Acto 1 | El antes: Copilot sin instrucciones | 5 min |
| Demo Acto 2 | Crear instrucciones en vivo | 5 min |
| Demo Acto 3 | El después: Copilot con instrucciones | 5 min |
| Demo Acto 4 | AGENTS.md, frontmatter e instructions/ | 5 min |
| Demo Acto 5 | Múltiples agentes: developer y reviewer | 8 min |
| Bonus | `.claude/` + hook Graphify + RCA-20 | opcional |
| Cierre | 3 ideas + dónde empezar | 3 min |

---

## Apertura — 2 min

> *"La semana pasada terminamos con un prompt escrito pero sin enviar. Decía: 'Implementa la RCA-20, el navbar y el footer definitivos'. Y os dije: lo dejamos aquí, porque antes de lanzar esto necesitamos hablar de algo importante."*
>
> *"Pero antes de entrar en materia, quiero responder una pregunta que me han hecho varios de vosotros esta semana: ¿quién crea todos esos ficheros? El `spec.md`, el `task.md`, el `copilot-instructions.md`... ¿los hace la IA o los hacemos nosotros?"*
>
> *"La respuesta es: los dos juntos. Vosotros tenéis el conocimiento — las conversaciones con el cliente, las decisiones técnicas, las convenciones del equipo. Ese conocimiento existe, pero está disperso: en correos, en reuniones, en vuestra cabeza. La IA lo recoge y lo estructura."*
>
> *"El `copilot-instructions.md` que vais a ver hoy no lo escribí yo desde cero. Le di a Claude el contexto del proyecto — el stack, las convenciones, el sistema de diseño — y me lo generó. Lo revisé, lo ajusté y lo comprometí al repositorio. Eso es el flujo real."*
>
> *"La IA no inventa el conocimiento. Lo organiza. Vosotros seguís siendo los que sabéis."*
>
> *"Y con eso claro — vamos a ver hoy cómo ese conocimiento se convierte en instrucciones persistentes que la IA lee automáticamente cada vez que abre vuestro proyecto."*

**Idea que debe quedar:**
> *"La IA no inventa el conocimiento de tu empresa. Lo organiza. Tú sigues siendo el que sabe."*

---

## Bloque 1 — El problema — 3 min

> *"Imaginad que contratáis a un desarrollador nuevo. El primer día llega, le dais acceso al repo y le decís: 'implementa el navbar'. Sin más."*
>
> *"¿Qué hace? Lo más probable es que use las convenciones que aprendió en su trabajo anterior. Quizás usa NgModules cuando vosotros usáis standalone. Quizás usa constructor injection cuando vosotros usáis `inject()`. Quizás no sabe nada de vuestro sistema de diseño."*
>
> *"Con la IA pasa exactamente lo mismo. Cada sesión empieza desde cero. No sabe cómo trabajáis, no conoce vuestras convenciones, no ha leído vuestro código."*
>
> *"La diferencia es que al desarrollador nuevo le dais documentación, le hacéis onboarding, le explicáis las convenciones del equipo. A la IA también podéis hacerlo — pero de forma persistente, en un fichero que lee automáticamente cada vez que abre vuestro proyecto."*

**Frase que debe quedar:**
> *"El onboarding que le harías a un desarrollador nuevo, escríbeselo a la IA en un fichero. Solo una vez."*

---

## Bloque 2 — La solución: ficheros de instrucciones — 5 min

> *"Tanto GitHub Copilot como Claude tienen un mecanismo para esto. El concepto es idéntico en los dos, solo cambia el nombre del fichero y dónde vive."*
>
> *"La idea es simple: un fichero de texto en vuestro repositorio que le dice a la IA quién sois, cómo trabajáis y qué convenciones seguís. Lo lee automáticamente al principio de cada sesión. Sin que vosotros tengáis que recordar decírselo."*

**La analogía:**
> *"Es como el día uno de una persona nueva en el equipo. Le dais el manual de bienvenida, le explicáis cómo se hacen las cosas aquí. Ese manual es el fichero de instrucciones. La diferencia es que la IA nunca se olvida de lo que hay en él."*

**Los dos ecosistemas:**

| | GitHub Copilot | Claude Code |
|---|---|---|
| Instrucciones globales | `.github/copilot-instructions.md` | `CLAUDE.md` |
| Instrucciones por ruta | `.github/instructions/*.instructions.md` | `.claude/rules/*.md` |
| Agentes | `AGENTS.md` | `.claude/agents/*.md` |
| Hooks y permisos | `.github/hooks/` | `.claude/settings.json` |

> *"Hoy vamos a ver cómo funciona con Copilot porque es lo que usamos en el día a día. Y al final veremos brevemente cómo está configurado en Claude — incluyendo algo que va un paso más allá."*

---

## Bloque 3 — `.github/` para Copilot — 5 min

> *"La carpeta `.github/` ya la conocéis — es donde viven los workflows de GitHub Actions, las plantillas de issues y pull requests. Pero tiene un apartado específico para instruir a Copilot."*

**`copilot-instructions.md`** — el más importante:
> *"Va en `.github/copilot-instructions.md`. Es el fichero principal. Copilot lo lee en cada sesión, en cualquier IDE — VS Code, JetBrains, Visual Studio. Aquí ponéis las convenciones globales del proyecto: tecnologías, patrones, reglas que aplican a todo el código."*

**`instructions/` con frontmatter `applyTo:`** — instrucciones por contexto:
> *"Podéis tener instrucciones que solo se activan cuando Copilot trabaja con ciertos ficheros. Por ejemplo, reglas específicas para los tests, o convenciones distintas para el código de backend. Viven en `.github/instructions/` con frontmatter `applyTo:`."*

**`AGENTS.md`** — para agentes:
> *"Cuando usáis Copilot en modo agente — que trabaja de forma autónoma en tareas — podéis darle instrucciones específicas con un fichero `AGENTS.md`. Puede estar en la raíz del repo o en cualquier carpeta, y el agente lee el más cercano a donde está trabajando."*

**Frase que debe quedar:**
> *"Tres ficheros de texto. Eso es todo lo que separa a Copilot de conocer vuestro proyecto de verdad."*

---

## Demo — 20-25 min

### Acto 1 — El antes: Copilot sin instrucciones (5 min)

> *"Voy a empezar con el repositorio tal como está ahora — sin ningún fichero de instrucciones. Para que veáis la diferencia."*

Con `.github/` vacío, abrir Copilot Chat en VS Code y escribir:

```
Crea el componente app-navbar para el proyecto
```

Dejar que Copilot responda. Va a generar código genérico — sin Signals, sin el sistema de diseño del RCA, sin las convenciones del proyecto.

> *"¿Veis lo que ha generado? Angular estándar. No sabe que usamos standalone components, no sabe que usamos Signals, no conoce nuestro sistema de diseño ni nuestra paleta de colores. Tendríamos que corregirlo todo."*

---

### Acto 2 — Crear las instrucciones en vivo (5 min)

> *"Ahora voy a crear el fichero de instrucciones. Para que veáis exactamente qué contiene y por qué."*

Crear `.github/copilot-instructions.md` en pantalla — pegarlo en vivo:

> *"Le estoy diciendo: qué stack usa el proyecto, qué convenciones seguimos, cómo se generan los componentes, cómo es el sistema de diseño. Todo lo que le explicaríais a un desarrollador nuevo el primer día."*
>
> *"Y recordad lo de antes — este fichero no lo escribí desde cero. Le di el contexto a Claude y me lo generó. Lo revisé y lo ajusté. Ese es el flujo."*

Guardar el fichero.

> *"Listo. Un fichero de texto. Vamos a ver qué cambia."*

---

### Acto 3 — El después: Copilot con instrucciones (5 min)

Misma pregunta en Copilot Chat:

```
Crea el componente app-navbar para el proyecto
```

> *"Fijaos en la diferencia. Ahora sabe que usamos standalone components, Signals, OnPush change detection. Conoce los tokens de diseño — `bg-surface`, `text-on-surface`, `border-outline-variant`. Usa `inject()` en lugar de constructor injection. Sigue nuestras convenciones."*
>
> *"Mismo prompt. Fichero de instrucciones mediante. Resultado completamente distinto."*

---

### Acto 4 — AGENTS.md e instructions/: el nivel siguiente (5 min)

> *"Hay un paso más. Cuando Copilot trabaja en modo agente — de forma autónoma, sin que vosotros estéis guiándole paso a paso — podéis darle instrucciones aún más específicas con el `AGENTS.md`."*

Mostrar el `AGENTS.md` del RCA:

> *"Aquí le digo cómo tiene que comportarse cuando trabaja solo: que lea el `task.md` antes de tocar código, que siga la estructura de carpetas del proyecto, que ejecute los tests antes de dar algo por terminado, que use la convención de commits del proyecto."*
>
> *"La diferencia con `copilot-instructions.md` es el nivel de detalle operacional. Las instrucciones globales le dicen cómo escribir código. El `AGENTS.md` le dice cómo trabajar."*

Mostrar la carpeta `instructions/` con los dos ficheros:

> *"Y luego están las instrucciones por contexto. Fijaos en este bloque al inicio del fichero — entre los tres guiones. Esto se llama frontmatter: son metadatos sobre el fichero en sí, no contenido. En este caso le dice a Copilot cuándo tiene que leer este fichero y cuándo no."*
>
> *"Este `applyTo: '**/*.spec.ts'` significa que Copilot solo carga estas instrucciones cuando está trabajando con ficheros de test. Si está editando un componente, no las lee. Si está editando un test, sí. Las instrucciones correctas, en el momento correcto."*

---

### Acto 5 — Múltiples agentes: developer y reviewer (8 min)

> *"Hasta ahora hemos visto un solo agente que hace todo. Pero hay un patrón mucho más potente: varios agentes especializados, cada uno con una responsabilidad concreta."*
>
> *"En cualquier equipo de desarrollo hay dos roles fundamentales: el que implementa y el que revisa. ¿Por qué no hacer lo mismo con la IA?"*

Mostrar la carpeta `.github/agents/` con los dos ficheros:

> *"Tenemos un `developer.agent.md` y un `reviewer.agent.md`. Son dos agentes distintos, con instrucciones distintas y acceso a herramientas distintas."*

Abrir `developer.agent.md` en pantalla:

> *"El developer lee el `task.md`, analiza la arquitectura, implementa siguiendo las convenciones, pasa los tests y hace el commit. Su trabajo es construir."*
>
> *"Fijaos en el frontmatter — tiene un `tools:` que define exactamente a qué herramientas tiene acceso. No puede hacer más de lo que le permitimos."*

Abrir `reviewer.agent.md` en pantalla:

> *"El reviewer solo tiene acceso de lectura. No puede modificar nada — solo leer y reportar. Verifica los criterios de aceptación del `task.md` uno a uno, comprueba las convenciones, revisa la cobertura de tests y genera un informe."*
>
> *"Si el reviewer dice que algo no está bien, el developer vuelve a trabajar. Si aprueba, se crea la Pull Request."*
>
> *"Esto es lo mismo que hacéis en vuestro equipo hoy — pero automatizado. Y lo bueno es que el reviewer nunca se cansa, nunca tiene prisa y nunca se le pasa nada por alto."*

Mostrar brevemente los equivalentes en `.claude/agents/`:

> *"Y los mismos agentes existen para Claude Code — mismo concepto, mismo patrón, diferente herramienta. El conocimiento que estáis adquiriendo hoy aplica a las dos."*

**Frase que debe quedar:**
> *"Un agente construye. Otro verifica. Ninguno de los dos trabaja sin contexto. Eso es un equipo de IA."*

---

### Bonus — `.claude/` y el hook de Graphify (3 min)

> *"Os prometí tres minutos sobre cómo está configurado esto en Claude. Y hay algo que va un paso más allá."*

Mostrar el `CLAUDE.md` del RCA brevemente:

> *"El concepto es idéntico — mismo fichero, mismas convenciones. Pero en Claude Code hay algo más: el `settings.json` con hooks."*

Mostrar el hook de Graphify en `settings.json`:

> *"Este hook hace que antes de cada sesión, Claude lea automáticamente el grafo de conocimiento del proyecto — generado por una herramienta que se llama Graphify. No solo sabe cómo escribir código con nuestras convenciones, sino que entiende la arquitectura completa: qué ficheros dependen de cuáles, qué módulos existen, cómo está estructurado el proyecto."*
>
> *"Esto lo veremos en detalle en la próxima charla. Pero quería que lo vieseis porque es el siguiente nivel de lo que hemos visto hoy."*

---

### Bonus opcional — Lanzar la RCA-20 (si el tiempo acompaña)

> *"Y ahora sí. Con todo esto configurado — las instrucciones, el agente, el contexto del proyecto — vamos a lanzar el prompt que dejamos pendiente la semana pasada."*

```
Implementa la RCA-20: app-navbar y app-footer definitivos con SSR e i18n
```

> *"Lo dejamos trabajar."*

⚠️ Solo lanzar si el tiempo acompaña y la demo ha ido fluida. Si no, cerrar aquí.

---

## Cierre — 3 min

> *"Primera: la IA sin contexto genera código genérico. Con un fichero de instrucciones en vuestro repositorio, genera código que sigue vuestras convenciones desde el primer intento."*
>
> *"Segunda: no es solo para developers. Cualquier equipo que use Copilot o Claude puede beneficiarse de tener instrucciones claras — cómo redactar documentos, qué tono usar, qué plantillas seguir."*
>
> *"Tercera: esto vive en el repositorio junto al código. Se versiona, se comparte con el equipo, evoluciona con el proyecto. No es configuración personal — es conocimiento del equipo."*

**Dónde empezar hoy:**
> *"Abrid vuestro repositorio, cread la carpeta `.github/` si no la tenéis, y añadid un `copilot-instructions.md`. Con diez líneas que describan vuestro stack y vuestras convenciones ya notaréis la diferencia."*
>
> *"Y si no estáis cómodos con la terminal: GitHub Desktop. Es la aplicación oficial de GitHub con interfaz visual — podéis crear ficheros, subirlos al repositorio, gestionar ramas, todo sin escribir un solo comando."*

**Gancho para la próxima charla:**
> *"Hoy hemos visto cómo darle a la IA el manual de bienvenida de vuestro proyecto. Pero hay algo más: ¿qué pasa con todo el conocimiento que no está en el código? Los procedimientos, las decisiones, la documentación de la empresa, el contexto que solo existe en la cabeza de las personas."*
>
> *"La semana que viene vamos a ver cómo construir una Wiki LLM — un repositorio de conocimiento que la IA puede consultar, mantener y ampliar. Lo veremos con Obsidian, conectado a GitHub, para que ese conocimiento esté siempre disponible y siempre actualizado."*
>
> *"Hoy le hemos dado a la IA el manual de cómo trabajamos. La semana que viene le damos el manual de por qué lo hacemos así."*

**Frase final:**
> *"La IA nunca se olvida de leerlo."*

---

## Checklist antes del miércoles

### Esta semana
- [ ] Crear `.github/copilot-instructions.md` en el RCA con el contenido de la demo
- [ ] Crear `AGENTS.md` en la raíz del RCA
- [ ] Probar el antes/después en vivo — que la diferencia sea visible y clara
- [ ] Tener el `task.md` de la RCA-20 listo por si lanzas el bonus

### Lunes/martes
- [ ] Ensayo completo cronometrado en el portátil corporativo
- [ ] Verificar que Copilot está conectado y funcionando en VS Code
- [ ] Prueba de proyección con un compañero

### El día de la charla
- [ ] VS Code abierto con el proyecto RCA
- [ ] `.github/` vacío preparado para el Acto 1
- [ ] `copilot-instructions.md` y `AGENTS.md` listos para pegar en vivo
- [ ] `task.md` de RCA-20 copiado y listo por si hay tiempo para el bonus
