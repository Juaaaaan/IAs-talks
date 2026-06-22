# Graphify — Grafo de conocimiento para asistentes de IA

> _"En lugar de que Claude recorra cada fichero como quien busca a pie en una ciudad sin mapa, Graphify construye el mapa primero. Claude lo lee y navega directo."_

---

## Qué es

Graphify es una skill de código abierto para asistentes de IA como Claude Code, Codex u OpenCode. Toma un repositorio — código fuente, documentación, schemas SQL, PDFs, imágenes — y lo convierte en un **grafo de conocimiento consultable**: un mapa de relaciones entre componentes, módulos, funciones y conceptos que el agente puede recorrer en lugar de releer ficheros.

Fue inspirado por una idea de Andrej Karpathy sobre construir bases de conocimiento para LLMs. El proyecto lo mantiene Safi Shamsi, está publicado bajo licencia MIT y se distribuye en PyPI como `graphifyy` (doble y). El comando CLI sigue siendo `graphify`.

---

## El problema que resuelve

Sin Graphify, cada sesión de Claude Code empieza desde cero. El agente no recuerda la arquitectura del proyecto de la sesión anterior. Para orientarse, recorre fichero a fichero con llamadas a `grep` — en un proyecto de ~40 ficheros, eso puede consumir 20.000 tokens solo para que Claude se ubique, antes de que hagas ninguna pregunta real.

En proyectos de 500+ ficheros, ese "impuesto de relectura" hace que las sesiones sean lentas, caras y frustrantes.

**Graphify resuelve el problema en el origen:** construye el mapa una vez, y Claude lee el mapa.

---

## Cómo funciona

Graphify tiene dos fases de análisis:

**Fase 1 — Análisis estático con Tree-sitter (0 tokens)**
Parsea el código directamente: clases, funciones, imports, call graphs. Soporta 31 lenguajes incluyendo TypeScript, JavaScript, Python, Go, Java, SQL y más. No necesita ningún modelo de IA para esta fase.

**Fase 2 — Extracción semántica con LLM (solo para docs, PDFs e imágenes)**
Para ficheros no ejecutables, usa el modelo que ya tienes configurado en tu asistente para extraer conceptos y relaciones que el análisis estático no puede ver.

El resultado son cuatro outputs en `graphify-out/`:

| Fichero | Contenido | Para quién |
|---|---|---|
| `graph.json` | El grafo completo, consultable | Claude Code |
| `GRAPH_REPORT.md` | Resumen: god nodes, conexiones inesperadas, comunidades | Claude Code + tú |
| `graph.html` | Visualización interactiva en el navegador | Revisión humana |
| `cache/` | SHA256 por fichero para actualizaciones incrementales | Interna |

Cuando Claude Code arranca una sesión, lee el `GRAPH_REPORT.md` antes de decidir qué ficheros abrir. En lugar de grepar todo el proyecto, consulta el grafo y carga solo los nodos relevantes.

---

## Graphify en un proyecto Angular

### Qué mapea

En un proyecto Angular, Graphify extrae y relaciona:

- Componentes y sus dependencias de template
- Servicios y qué componentes los inyectan
- Módulos (o standalone imports en Angular 14+)
- Pipes y directivas
- Rutas y los componentes que activan
- Schemas SQL si el proyecto los incluye
- Documentación técnica en Markdown

El resultado es visible desde el primer momento: los **god nodes** son los servicios más inyectados o los módulos más importados — exactamente los ficheros que más riesgo tienen al ser modificados.

### Cuándo usarlo

**Al inicio de una sesión de trabajo significativa** — no de forma continua. Los momentos donde aporta más:

- **Primera vez que Claude Code toca el proyecto** — en lugar de que el agente gaste tokens leyendo fichero a fichero, le das el `graph.json` y arranca orientado desde el primer mensaje.
- **Después de una refactorización grande** — el grafo anterior ya no refleja la realidad. `graphify . --update` regenera solo lo que cambió (usa caché SHA256).
- **Antes de tocar un módulo desconocido** — el `GRAPH_REPORT.md` te muestra las conexiones inesperadas: un componente que parece aislado pero que resulta ser dependencia de ocho módulos.
- **En code review** — para ver si un PR introduce acoplamientos que no existían.
- **Al incorporar a alguien nuevo al proyecto** — el `graph.html` es una forma visual de entender la arquitectura sin leer código.

### Lo que NO hace

Graphify mapea **estructura**, no **intención**. No sabe por qué elegiste standalone components sobre NgModules. No conoce las decisiones de arquitectura que tomaste hace tres semanas. No entiende el contexto de negocio de cada feature. Para eso está Obsidian.

---

## Obsidian en un proyecto Angular

### Qué almacena

Obsidian actúa como la **memoria declarativa** del proyecto: todo lo que no está en el código pero que define cómo trabajáis.

- **Decisiones de arquitectura** — "elegimos standalone components porque el equipo viene de React y el modelo mental es más cercano", "descartamos NgRx porque el estado es local a cada feature"
- **Patrones del equipo** — cómo se estructura un feature module, convenciones de nombrado, qué ficheros genera el CLI y cuáles se modifican siempre a mano
- **El flujo SDD del proyecto** — los `spec.md` de cada feature, sus criterios de aceptación, el estado actual. Ver [[sdd]]
- **Dead ends y advertencias** — "no actualizar a la versión X de la librería Y hasta que resuelvan el issue #1234", "el servicio de autenticación tiene latencia alta en horas pico"
- **Historial de sesiones** — qué se construyó, qué quedó pendiente, por qué se tomó tal decisión

### Cuándo usarlo

Obsidian no es una herramienta de sesión — es un repositorio vivo que crece con el proyecto. Se actualiza:

- **Al cerrar una sesión de Claude Code** — con `/save` o equivalente, para que las decisiones de esa sesión no se pierdan
- **Al escribir un nuevo `spec.md`** — el spec vive en el vault, no solo en el proyecto
- **Al tomar una decisión de arquitectura** — el momento en que se toma, no después
- **Al descubrir un problema recurrente** — para que la siguiente persona (o la siguiente sesión) no lo repita

---

## Cómo se combinan: el flujo completo

Graphify y Obsidian resuelven problemas distintos y se complementan sin solapamiento:

```
Inicio de sesión Claude Code
│
├── Lee CLAUDE.md            → reglas del proyecto
├── Consulta graph.json      → entiende la estructura (Graphify)
└── Consulta vault Obsidian  → entiende las decisiones
        ↓
    Trabaja con contexto completo
        ↓
Fin de sesión
└── /save → genera nota en Obsidian con lo que se hizo y por qué
```

| Capa | Herramienta | Qué aporta |
|---|---|---|
| Estructura del código | Graphify | Qué existe, qué depende de qué, qué es central |
| Decisiones y contexto | Obsidian | Por qué existe así, qué se intentó, qué no tocar |
| Reglas del proyecto | CLAUDE.md | Cómo debe comportarse el agente en este repo |

---

## Instalación rápida

```bash
# Instalar (uv pone graphify en PATH automáticamente)
uv tool install graphifyy

# Alternativas
pipx install graphifyy
pip install graphifyy

# Registrar la skill con Claude Code
graphify install

# Construir el grafo del proyecto
graphify .

# Solo lo que ha cambiado (más rápido)
graphify . --update

# Generar vault de Obsidian desde el grafo
graphify . --obsidian

# Activar watch mode (auto-sync al guardar)
graphify . --watch
```

> ⚠️ El paquete en PyPI se llama `graphifyy` (doble y). Otros paquetes `graphify*` en PyPI no están afiliados al proyecto oficial.

---

## El flag `--obsidian`

Este flag genera automáticamente un vault de Obsidian desde el grafo del repositorio: notas por componente, relaciones como wikilinks, comunidades como carpetas. Es un punto de partida estructural, no un vault completo — las decisiones de arquitectura, los dead ends y el contexto de negocio hay que añadirlos a mano.

En la práctica funciona bien como **mapa inicial** cuando entras a un proyecto nuevo o cuando incorporas a alguien al equipo. No sustituye a un vault mantenido activamente.

---

## Actualización del grafo: cuándo y cómo

Un grafo obsoleto es peor que ningún grafo — orienta mal. Estrategias recomendadas:

- **Post-commit automático** — `graphify hook install` registra un hook que regenera el grafo en cada commit (solo análisis AST, 0 tokens, muy rápido)
- **Manual tras refactorización** — `graphify . --update --force` para forzar regeneración completa
- **No en hooks de Claude Code** — `graphify update` tarda 10s+ en repos grandes. Ponerlo en `Stop` o `PostToolUse` bloquea la sesión o acumula procesos en background

---

## Relación con el proyecto RCA (Charla 8)

El proyecto RCA (Angular 21, `da-ju-ia-talks.atlassian.net`) es el candidato natural para montar esta combinación. La estructura que tendría sentido:

```
vault ai-tools/
└── proyectos/
    └── rca/
        ├── arquitectura.md     → decisiones de diseño del proyecto Angular
        ├── patrones.md         → convenciones del equipo en este repo
        └── historial/          → notas de sesión generadas por /save
```

Graphify generaría el mapa estructural del repo. El vault aportaría el contexto que no está en el código. Juntos permiten una demo para Charla 8 con más impacto que un simple "mira cómo Claude Code lee el proyecto": el agente llega ya orientado, sin releer nada, porque el mapa y las decisiones ya están cargadas.

---

## Notas técnicas

- **TypeScript es un ciudadano de primera clase** — el análisis AST de TypeScript es completo, incluye tipos, interfaces y decoradores de Angular
- **Sin telemetría** — Graphify no envía datos a ningún servidor. El análisis de código es 100% local
- **Los docs sí pasan por el LLM** — si tienes requisitos de residencia de datos, usa `--backend ollama` para mantenerlo todo local
- **MCP server incluido** — `graphify . --mcp` lanza un servidor MCP que expone el grafo como herramienta para cualquier agente compatible. Ver [[mcp]]
- **Compatible con múltiples agentes** — Claude Code, Codex, Cursor, Gemini CLI, GitHub Copilot CLI y más

---

## Relación con otras piezas

- **[[claude-code]]** — Graphify es una skill que se integra directamente con Claude Code vía `CLAUDE.md` y un hook `PreToolUse`
- **[[mcp]]** — Graphify puede exponerse como servidor MCP (`--mcp`), haciéndolo accesible desde cualquier agente compatible
- **[[sdd]]** — Los `spec.md` del flujo SDD son candidatos a incluirse en el vault de Obsidian que complementa el grafo
- **[[skills]]** — Graphify es en sí mismo una skill: se instala como fichero de instrucciones que el agente lee al inicio de sesión

---

## Dónde aparece en la serie

| Charla | Rol de Graphify |
|---|---|
| 8 | Herramienta complementaria para la demo de Claude Code con proyecto Angular (RCA) |
| 10 | Parte del ciclo completo: grafo + vault + SDD + agente |

---

## Referencias

- Repositorio oficial: [github.com/safishamsi/graphify](https://github.com/safishamsi/graphify)
- Sitio web: [graphify.net](https://graphify.net)
- PyPI: `pip install graphifyy`
