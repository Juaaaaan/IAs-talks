# copilot-instructions.md — Instrucciones persistentes para Copilot

> _"El onboarding que le harías a un desarrollador nuevo, escríbeselo a la IA en un fichero. Solo una vez."_

---

## Qué es

El fichero `.github/copilot-instructions.md` es el mecanismo principal para dar contexto persistente a GitHub Copilot. Lo lee automáticamente en cada sesión, en cualquier IDE compatible (VS Code, JetBrains, Visual Studio).

No es un prompt que escribes cada vez. Es el manual de bienvenida de tu proyecto para la IA.

---

## Qué contiene

Un buen `copilot-instructions.md` recoge:

- **Stack tecnológico** — qué framework, versión, librerías principales
- **Convenciones de código** — patrones, estilos, reglas que el equipo sigue
- **Estructura del proyecto** — dónde vive cada cosa
- **Comandos habituales** — build, test, lint, serve
- **Reglas de negocio** — restricciones importantes que la IA debe respetar

---

## Cómo se crea

No se escribe desde cero. El flujo correcto es:

1. Recopilar el contexto que ya existe — decisiones técnicas, convenciones del equipo, documentación
2. Dárselo a la IA como contexto
3. Pedirle que genere el fichero de instrucciones
4. Revisar, ajustar y commitear al repositorio

> _"La IA no inventa el conocimiento. Lo organiza. Tú sigues siendo el que sabe."_

---

## Dónde vive

```
.github/
└── copilot-instructions.md    # Instrucciones globales del proyecto
```

---

## La diferencia con el prompt

| Sin instrucciones | Con instrucciones |
|---|---|
| Cada sesión empieza desde cero | Cada sesión arranca con el contexto cargado |
| Copilot usa convenciones genéricas | Copilot usa las convenciones del equipo |
| Resultados inconsistentes | Resultados consistentes |
| Hay que explicar el contexto cada vez | El contexto ya está ahí |

---

## Instrucciones por ruta — `instructions/`

Para instrucciones que solo aplican a ciertos ficheros, se usa la carpeta `.github/instructions/` con ficheros `.instructions.md` y frontmatter `applyTo:`:

```markdown
---
applyTo: "**/*.spec.ts"
---

# Testing conventions
...
```

El frontmatter `applyTo:` define el glob de ficheros que activan la instrucción. Si Copilot está trabajando con un fichero que no coincide, la instrucción no se carga.

Ver [[frontmatter]] para más detalle sobre el frontmatter.

---

## Equivalente en Claude Code

| GitHub Copilot | Claude Code |
|---|---|
| `.github/copilot-instructions.md` | `CLAUDE.md` en la raíz del proyecto |
| `.github/instructions/*.instructions.md` | `.claude/rules/*.md` con frontmatter `paths:` |

---

## Relación con otras piezas

- **[[agentes-multiples]]** — Los agentes tienen su propio mecanismo de instrucciones (`AGENTS.md` y `.github/agents/`)
- **[[frontmatter]]** — El sistema de metadatos que controla cuándo se cargan las instrucciones
- **[[sdd]]** — Las instrucciones de Copilot son el equivalente al CLAUDE.md dentro del arnés documental

---

## Dónde aparece en la serie

| Charla | Rol |
|---|---|
| 8 | Concepto central — introducción y demo |
