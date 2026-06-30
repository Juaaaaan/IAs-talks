# Guión Charla 8 — Instruyendo a la IA: `.github/` y `.claude/`

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|--------|-----------|--------|
| Apertura | Puente desde Charla 7 + aclaración anticipada | 2 min |
| Bloque 1 | El problema: la IA sin contexto | 3 min |
| Bloque 2 | La solución: ficheros de instrucciones | 5 min |
| Bloque 3 | `.github/` para Copilot — estructura completa | 5 min |
| Demo Acto 1 | Tour por el `.github/` completo | 8 min |
| Demo Acto 2 | Prompts en vivo: modificaciones reales | 7 min |
| Demo Acto 3 | AGENTS.md en acción: developer y reviewer | 10 min |
| Demo Acto 4 | ¿Cómo confiar en el resultado? | 5 min |
| Bonus | `.claude/` + hook Graphify | opcional |
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

### Acto 1 — El `.github/` completo: tour por las instrucciones (8 min)

> *"En lugar de construir esto desde cero delante de vosotros, os voy a enseñar el `.github/` ya configurado del proyecto RCA — porque lo importante no es verme escribir, sino entender qué contiene cada pieza y por qué."*

Abrir el explorador de ficheros en VS Code y mostrar la carpeta `.github/` completa:

```
.github/
├── copilot-instructions.md
├── AGENTS.md
├── instructions/
│   ├── testing.instructions.md
│   └── components.instructions.md
└── agents/
    ├── developer.agent.md
    └── reviewer.agent.md
```

**Mostrar `copilot-instructions.md`:**
> *"Esto es lo primero que lee Copilot en cada sesión. Stack, convenciones de Angular, sistema de diseño. Y recordad cómo se generó — no lo escribí desde cero. Le di a Claude el contexto del proyecto y me lo generó. Lo revisé y lo ajusté. Ese es el flujo real: vosotros tenéis el conocimiento, la IA lo organiza."*

**Mostrar `instructions/testing.instructions.md` y `components.instructions.md`:**
> *"Estas son instrucciones que solo se activan en contextos concretos. Fijaos en este bloque al inicio del fichero, entre los tres guiones — se llama frontmatter, son metadatos sobre el fichero. El `applyTo: '**/*.spec.ts'` le dice a Copilot que solo cargue estas instrucciones cuando trabaja con ficheros de test."*

**Mostrar `AGENTS.md`:**
> *"Este es el manual de comportamiento autónomo. Le dice qué leer antes de tocar código, qué verificar antes de terminar, qué nunca debe hacer."*

**Frase que debe quedar:**
> *"Cinco ficheros de texto. Eso es todo lo que separa a Copilot de conocer vuestro proyecto de verdad."*

**Anécdota rápida (30 segundos):**
> *"Una anécdota rápida de esta semana: probé una extensión de terceros llamada Superpowers, instalada en mi VS Code. Sin yo saberlo, estaba interceptando mis prompts y generando su propia estructura de carpetas para specs — una que no tenía nada que ver con la nuestra. Tuve que desactivarla. Y esto es exactamente el problema del que hablamos: si no controláis explícitamente qué contexto sigue la IA, algo más lo va a decidir por vosotros. A veces ese 'algo' es una extensión que ni recordáis haber instalado."*

---

### Acto 2 — Prompts en vivo: modificaciones reales con contexto (7 min)

> *"Ahora vamos a verlo funcionar. No voy a crear un componente entero — vamos a hacer cambios pequeños y reales, como los que hacéis vosotros cada día."*

Abrir el Copilot CLI en el proyecto RCA con el `.github/` ya configurado.

**Prompt 1 — Cambio de texto:**
```
Cambia el texto del botón principal del footer a "Contáctanos"
```

> *"Fijaos en el resultado — usa los tokens de diseño correctos, no toca nada que no debía, respeta la estructura del componente."*

**Prompt 2 — Añadir un elemento pequeño:**
```
Añade un botón secundario en el header que ponga "Suscríbete" y no haga nada, solo mostrar el botón
```

> *"Mismo patrón: botón secundario con `border border-outline-variant`, transición de 300ms, exactamente como dicta nuestro sistema de diseño. Esto no lo ha adivinado — lo sabe porque se lo dijimos una vez, en `copilot-instructions.md`."*

**Frase que debe quedar:**
> *"No hace falta repetir las convenciones en cada prompt. Las dice una vez el fichero, las respeta Copilot siempre."*

---

### Acto 3 — AGENTS.md en acción: developer y reviewer trabajando (10 min)

> *"Hasta ahora hemos visto un agente que responde a prompts sueltos. Pero hay un patrón más potente: agentes especializados, invocados explícitamente, cada uno con una responsabilidad concreta."*

**Invocar al developer:**
```
@developer Añade un badge que muestre el número de items en el carrito
```

> *"El `@developer` lee sus propias instrucciones del fichero `developer.agent.md` — analiza la arquitectura, identifica componentes reutilizables, implementa siguiendo las convenciones."*

**Invocar al reviewer:**
```
@reviewer Revisa la implementación del badge
```

> *"El reviewer solo tiene acceso de lectura. No puede modificar nada — solo leer y reportar. Verifica los criterios, las convenciones, la cobertura de tests, y genera un informe."*

⚠️ **Nota de preparación:** Si en el ensayo el reviewer encuentra un fallo real (como ocurrió en las pruebas — un test de regresión fallido), mostradlo tal cual. Es el momento más potente de la demo.

> *"Mirad esto — el reviewer ha encontrado un fallo real. No le dijimos qué buscar en este caso concreto, simplemente está siguiendo los criterios que le dimos. Esto es el valor real de un segundo agente: pilla cosas que se nos escapan."*

Mostrar brevemente los equivalentes en `.claude/agents/`:

> *"Y los mismos agentes existen para Claude Code — mismo concepto, mismo patrón, diferente herramienta."*

**Frase que debe quedar:**
> *"Un agente construye. Otro verifica. Ninguno de los dos trabaja sin contexto. Eso es un equipo de IA."*

---

### Acto 4 — ¿Cómo sabemos si podemos confiar en el resultado? (5 min)

> *"Una pregunta que seguro tenéis en la cabeza: ¿cómo sabemos si podemos fiarnos del código que genera la IA?"*

> *"No hay un número mágico de confianza. Pero sí señales que se pueden combinar."*

**Señales automatizables:**
> *"Tests que pasan y cobertura suficiente. Build sin errores. Linter limpio. Y la que acabáis de ver — un segundo agente, el reviewer, que verifica de forma objetiva contra los criterios del `task.md`."*

**Señales humanas:**
> *"La lógica de negocio solo la valida una persona que conoce el dominio. Y toda Pull Request, por mucho que el reviewer la apruebe, pasa por una persona antes de mergear — al menos mientras el equipo gana confianza con el flujo."*

**Frase que debe quedar:**
> *"La confianza se construye en capas. La IA no sustituye la verificación humana — la hace más rápida porque ya ha filtrado la mayoría de los problemas antes de que lleguen a vosotros."*

---

### Bonus — `.claude/` y el hook de Graphify (3 min)

> *"Os prometí unos minutos sobre cómo está configurado esto en Claude. Y hay algo que va un paso más allá."*

Mostrar el `CLAUDE.md` del RCA brevemente:

> *"El concepto es idéntico — mismo fichero, mismas convenciones. Pero en Claude Code hay algo más: el `settings.json` con hooks."*

Mostrar el hook de Graphify en `settings.json`:

> *"Este hook hace que antes de cada sesión, Claude lea automáticamente el grafo de conocimiento del proyecto — generado por una herramienta que se llama Graphify. No solo sabe cómo escribir código con nuestras convenciones, sino que entiende la arquitectura completa: qué ficheros dependen de cuáles, qué módulos existen, cómo está estructurado el proyecto."*
>
> *"Esto lo veremos en detalle en la próxima charla. Pero quería que lo vieseis porque es el siguiente nivel de lo que hemos visto hoy."*

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
- [ ] Verificar que `.github/copilot-instructions.md`, `AGENTS.md`, `instructions/` y `agents/` están completos en el RCA
- [ ] Desactivar cualquier extensión/plugin de terceros (ej. Superpowers) que pueda interferir en la demo
- [ ] Ensayar los dos prompts del Acto 2 (cambio de texto + botón secundario) y confirmar que el resultado es rápido y limpio
- [ ] Ensayar la invocación de `@developer` y `@reviewer` en el Copilot CLI
- [ ] Si el reviewer encuentra un fallo real en el ensayo, decidir si se deja para mostrarlo en directo

### Lunes/martes
- [ ] Ensayo completo cronometrado en el portátil corporativo
- [ ] Verificar que Copilot CLI funciona con fluidez (sin tiempos de espera largos)
- [ ] Prueba de proyección con un compañero

### El día de la charla
- [ ] VS Code y Copilot CLI abiertos con el proyecto RCA
- [ ] `.github/` completo y verificado
- [ ] Prompts del Acto 2 y Acto 3 copiados y listos para pegar
- [ ] `CLAUDE.md` y hook de Graphify en `settings.json` listos para el bonus
