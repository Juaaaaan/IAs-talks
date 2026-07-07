# Guión Charla 11 — Wiki LLM: la IA que recuerda a tu equipo

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|--------|-----------|--------|
| Apertura | Puente desde Charla 8 + el problema | 4 min |
| Bloque 1 | Qué es un LLM + Qué es un Wiki LLM + OKF | 5 min |
| Bloque 2 | La herramienta: Obsidian + GitHub | 3 min |
| Demo 1 | Perspectiva developer — RCA | 10 min |
| Demo 2 | Perspectiva jefe de proyecto — equipo | 10 min |
| Cierre | 3 ideas + presentación compañero | 3 min |
| Compañero | Demo Wiki LLM complementaria | 5-10 min |

---

## Apertura — 4 min

> *"En la Charla 8 terminamos con una promesa. Dijimos: hoy le hemos dado a la IA el manual de cómo trabajamos. La semana que viene le damos el manual de por qué lo hacemos así."*
>
> *"Hoy es esa semana."*
>
> *"Hasta ahora la IA sabía cómo escribir código siguiendo nuestras convenciones. Sabía qué herramientas usar, qué patrones seguir. Pero no sabía por qué elegimos Angular en lugar de React. No sabía qué intentamos hace tres meses y no funcionó. No sabía quién del equipo domina Copilot y quién acaba de empezar."*
>
> *"Eso es lo que vamos a resolver hoy."*

**El problema:**

> *"Hay un tipo de conocimiento que ningún sistema de vuestra empresa captura bien. No está en el código. No está en los documentos formales. No está en Jira."*
>
> *"Está en la cabeza de las personas."*
>
> *"La decisión que se tomó en aquella reunión de hace seis meses y por qué. El proveedor que se descartó y la razón concreta. El desarrollador que sabe Angular a fondo y el que acaba de empezar. El proceso que funciona pero que nadie ha documentado porque siempre lo hace la misma persona."*
>
> *"Cuando esa persona se va, ese conocimiento desaparece con ella. Cuando la IA necesita ese contexto, no lo encuentra en ningún sitio."*

**Frase que debe quedar:**
> *"El conocimiento más valioso de una empresa no está en los documentos. Está en las cabezas. Y las cabezas no se indexan."*

---

## Bloque 1 — Qué es un LLM + Wiki LLM + OKF — 5 min

### Qué es un LLM

> *"Antes de entrar en materia, una aclaración rápida para quien no lo haya oído antes: ¿qué es un LLM?"*
>
> *"LLM son las siglas de Large Language Model — modelo de lenguaje grande. Es el tipo de IA que hay detrás de Claude, de ChatGPT, de Copilot. Lo que lo hace especial es que entiende y genera texto de forma natural."*
>
> *"Pero tiene un límite importante: no recuerda nada entre sesiones. Cada vez que abres una conversación nueva, empieza desde cero. No sabe quién eres, no sabe en qué proyecto trabajas, no conoce las decisiones que tomasteis la semana pasada."*
>
> *"El Wiki LLM existe precisamente para resolver ese límite."*

### Qué es un Wiki LLM

> *"Un Wiki LLM es una base de conocimiento en ficheros markdown que la IA puede leer, actualizar y mantener."*
>
> *"El concepto lo introdujo Andrej Karpathy — el investigador que cofundó OpenAI. Su observación fue simple: los LLMs no se aburren de mantener una wiki. No se olvidan de actualizar una referencia cruzada. Pueden tocar quince ficheros en un solo paso. Todo lo que hace que los humanos abandonen sus wikis internas es exactamente lo que los LLMs hacen bien."*
>
> *"Google formalizó esto hace unas semanas con un estándar que se llama OKF — Open Knowledge Format. La idea es añadir un pequeño bloque de metadatos al inicio de cada fichero markdown: tipo, descripción, etiquetas, relaciones con otros ficheros."*

Mostrar un fichero del vault con el frontmatter OKF:

> *"Con esto, la wiki deja de ser una carpeta de documentos y se convierte en un grafo de conocimiento que cualquier agente puede navegar. No solo leer — navegar. Sabe que este fichero está relacionado con ese otro, que este concepto lleva a aquella decisión."*

**La diferencia clave:**
> *"Sin Wiki LLM: le explicas el contexto a la IA cada vez que la necesitas."*
>
> *"Con Wiki LLM: el contexto ya está ahí. La IA lo consulta sola."*

**Frase que debe quedar:**
> *"Un Wiki LLM no es una carpeta de notas. Es la memoria persistente de tu empresa."*

---

## Bloque 2 — La herramienta: Obsidian + GitHub — 3 min

> *"Para montarlo necesitáis dos herramientas gratuitas."*
>
> *"Obsidian es una aplicación de notas en markdown. Gratuita, local, sin servidores de terceros. Todo son ficheros de texto en vuestro ordenador."*
>
> *"GitHub es donde vive el repositorio. Cada vez que añadís o modificáis una nota en Obsidian, se sube automáticamente al repo. Cualquier persona del equipo puede ver el vault, contribuir a él, y cualquier agente de IA puede leerlo."*
>
> *"La conexión entre los dos es el plugin de GitHub para Obsidian. Lo configuráis una vez y ya está."*
>
> *"Esto no es para developers. Cualquier persona del equipo puede abrir Obsidian, escribir una nota sobre una reunión, y en treinta segundos esa nota está en el repo, disponible para la IA y para todo el equipo."*

**Frase que debe quedar:**
> *"Obsidian es el cuaderno. GitHub es la memoria compartida. La IA es la que lo mantiene vivo."*

---

## Demo 1 — Perspectiva developer (10 min)

**Contexto antes de abrir Obsidian:**

> *"Os voy a mostrar cómo usaría esto un developer trabajando en un proyecto Angular. El vault tiene una carpeta de developer con decisiones de arquitectura, dead ends y contexto del proyecto. Cosas que no están en el código pero que son igual de importantes."*

### Paso 1 — Mostrar el vault (2 min)

Abrir Obsidian, carpeta `Developer/`. Mostrar los ficheros brevemente:

> *"Aquí tenemos por qué elegimos Angular, por qué no usamos NgRx, qué problemas encontramos con SSR, el estado actual del sprint. Todo en markdown, todo en formato OKF con su frontmatter."*

### Paso 2 — La IA consulta el vault (3 min)

```
Estoy trabajando en el proyecto RCA.
¿Por qué no usamos NgRx? ¿Hay algún dead end
que deba conocer antes de tocar el sistema de estado?
```

> *"No le hemos explicado nada. Ha ido al vault, ha leído los ficheros correctos y ha respondido con el contexto real del proyecto."*

### Paso 3 — Generar nuevo fichero en vivo (5 min)

> *"Ahora el momento importante. Acabamos de tomar una decisión en reunión. En lugar de escribirla en un correo que nadie va a encontrar, se la decimos a la IA."*

```
Acabo de decidir en reunión que no vamos a implementar
modo oscuro en el proyecto RCA porque el sistema de diseño
Artisanal Ether está definido únicamente en tonos cálidos
y la cliente no lo ha pedido. Documenta esta decisión
en formato OKF y guárdala en la carpeta Developer del vault.
```

Señalar el fichero apareciendo en Obsidian → subiendo al repo.

> *"Treinta segundos. La decisión está documentada, está en el repo, y la próxima vez que alguien trabaje en este proyecto sabrá por qué no hay modo oscuro sin que nadie se lo explique."*

**Transición:**
> *"Esto era para developers. Ahora os voy a mostrar exactamente el mismo mecanismo para un problema completamente diferente. Nada de código."*

---

## Demo 2 — Perspectiva jefe de proyecto (10 min)

**Contexto antes de abrir la carpeta:**

> *"Tenemos en la empresa un embajador de IA. Su trabajo es conocer el nivel de cada persona con IA, saber quién está preparado para usar Copilot de forma autónoma, quién necesita formación. Hasta ahora lo hacía con un Excel."*
>
> *"¿Y si la IA pudiera hacer ese trabajo por él?"*

### Paso 1 — Mostrar el vault de equipo (2 min)

Abrir carpeta `Equipo/`. Mostrar los ficheros:

> *"Aquí tenemos el framework de assessment con las 8 dimensiones de madurez, y un perfil por cada persona del equipo. Misma estructura que el Excel real — nombres ficticios."*

### Paso 2 — La pregunta de gestión (3 min)

```
Basándote en los perfiles del equipo que tienes en el vault,
¿a quién asignarías para liderar la adopción de Copilot
en el próximo proyecto? ¿Y quién necesita formación
antes de poder trabajar en modo agentic?
```

> *"No ha necesitado leer el Excel. No ha necesitado reuniones. Ha leído el vault y ha dado una respuesta concreta con nombres y razones."*

### Paso 3 — Generar perfil nuevo en vivo ⭐ El momento wow (5 min)

> *"Y ahora lo más importante. Acaba de incorporarse una persona nueva al equipo. En lugar de rellenar el Excel a mano, le hacemos las preguntas y la IA genera el perfil directamente."*

```
Acabo de entrevistar a un nuevo miembro del equipo.
Sus respuestas del assessment son:
- Usa ChatGPT puntualmente para hacer resúmenes de documentación
- No tiene archivos de contexto en ningún proyecto
- Desconoce qué es un MCP o un agente
- Conoce las políticas básicas de su empresa sobre IA
- Le gustaría aprender más pero no ha tenido formación formal

Genera su perfil de madurez IA en formato OKF
con scores estimados por dimensión y recomendaciones.
Llámalo Carlos V., rol Backend Junior.
Guárdalo en la carpeta Equipo del vault.
```

Señalar el perfil apareciendo en Obsidian → subiendo al repo.

> *"El perfil está en el vault. La próxima vez que alguien pregunte si Carlos está listo para trabajar con Copilot en modo agentic, la IA tiene la respuesta."*

**Frase que debe quedar:**
> *"La IA no solo conoce el código. Ahora también conoce al equipo."*

---

## Cierre — 3 min

> *"Primera: el conocimiento más valioso de vuestra empresa no está en los sistemas. Está en las personas. Un Wiki LLM es la forma de sacarlo de las cabezas y hacerlo disponible para todos."*
>
> *"Segunda: esto no es solo para developers. Hoy hemos visto cómo lo usaría un developer y cómo lo usaría un jefe de proyecto. El mismo mecanismo, dos problemas completamente distintos."*
>
> *"Tercera: montar esto no requiere infraestructura. Obsidian es gratuito, GitHub ya lo usáis. El coste de empezar es cero."*

**Dónde empezar hoy:**
> *"Descargad Obsidian en obsidian.md. Instalad el plugin de Git. Cread una carpeta para vuestras notas de proyecto. Y la próxima decisión importante que toméis, escribidla en un fichero markdown en lugar de en un correo que nadie va a encontrar."*

**Presentación del compañero:**
> *"Y ahora le cedo la palabra a [nombre]. Lleva tiempo trabajando con Wiki LLMs y tiene algo que añadir a lo que hemos visto."*

---

## Checklist antes del miércoles

### Hoy
- [ ] Leer el guión en voz alta una vez completo
- [ ] Cronometrar los dos bloques de demo

### Mañana
- [ ] Ensayo completo de principio a fin
- [ ] Coordinar con el compañero qué cubre él para no solapar
- [ ] Confirmar que el vault está sincronizando correctamente

### El día de la charla
- [ ] Obsidian abierto con el vault de demo
- [ ] Repo conectado y verificado
- [ ] Los 4 prompts de demo copiados y listos para pegar

---

## Prompts de demo — referencia rápida

**Demo 1 — Prompt 1:**
```
Estoy trabajando en el proyecto RCA.
¿Por qué no usamos NgRx? ¿Hay algún dead end
que deba conocer antes de tocar el sistema de estado?
```

**Demo 1 — Prompt 2:**
```
Acabo de decidir en reunión que no vamos a implementar
modo oscuro en el proyecto RCA porque el sistema de diseño
Artisanal Ether está definido únicamente en tonos cálidos
y la cliente no lo ha pedido. Documenta esta decisión
en formato OKF y guárdala en la carpeta Developer del vault.
```

**Demo 2 — Prompt 3:**
```
Basándote en los perfiles del equipo que tienes en el vault,
¿a quién asignarías para liderar la adopción de Copilot
en el próximo proyecto? ¿Y quién necesita formación
antes de poder trabajar en modo agentic?
```

**Demo 2 — Prompt 4:**
```
Acabo de entrevistar a un nuevo miembro del equipo.
Sus respuestas del assessment son:
- Usa ChatGPT puntualmente para hacer resúmenes de documentación
- No tiene archivos de contexto en ningún proyecto
- Desconoce qué es un MCP o un agente
- Conoce las políticas básicas de su empresa sobre IA
- Le gustaría aprender más pero no ha tenido formación formal

Genera su perfil de madurez IA en formato OKF
con scores estimados por dimensión y recomendaciones.
Llámalo Carlos V., rol Backend Junior.
Guárdalo en la carpeta Equipo del vault.
```
