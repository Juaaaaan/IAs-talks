# 🧠 IA Talks — Base de conocimiento

Este vault es el segundo cerebro de la serie de píldoras informativas sobre IA que impartimos internamente. Aquí vive todo lo que no cabe en el repo de la web: narrativa, decisiones de diseño, guiones, demos y lecciones aprendidas.

---

## Qué hay aquí

|Carpeta|Contenido|
|---|---|
|`Charlas/`|Guión, checklist y notas de cada sesión|
|`Conceptos/`|Definiciones de los conceptos clave de la serie|
|`Recursos/`|Ficheros de referencia reutilizables — configs, agentes, tasks|

---

## La narrativa de la serie

La serie construye un arco narrativo a lo largo de diez charlas. El hilo conductor es el **arnés completo**: el conjunto de piezas que permiten a la IA trabajar de forma estructurada, consistente y conectada al entorno real de la empresa.

```
SDD          →  el arnés documental        (qué construir)
Skills       →  el arnés de comportamiento (cómo comportarse)
MCPs         →  el arnés de integración    (cómo actuar)
Instrucciones → el contexto persistente   (cómo conocer el proyecto)
─────────────────────────────────────────────────────────────
Los cuatro juntos = el arnés completo
```

Cada charla añade una pieza. El concepto de [[arnes-completo]] es el eje que las conecta todas.

---

## Charlas de la serie

|#|Título|Estado|
|---|---|---|
|1–6|Serie anterior (heredada)|✅ Impartidas|
|7|[[charla-07-skills-mcps\|Skills, MCPs y el Arnés Completo]]|✅ Impartida — 17 jun 2026|
|8|[[charla-08-copilot-instrucciones\|Instruyendo a la IA: .github/ y .claude/]]|🔜 En preparación|
|9|Wiki LLM con Obsidian y GitHub|📋 Planificada|
|10|GitHub Actions + Copilot coding agent|📋 Planificada|
|11|El ciclo completo — cierre del arco|📋 Planificada|

---

## Conceptos clave

- [[arnes-completo]] — La metáfora central de la serie
- [[sdd]] — Specification-Driven Development
- [[skills]] — El arnés de comportamiento
- [[mcp]] — Model Context Protocol
- [[copilot-instructions]] — Instrucciones persistentes para Copilot
- [[frontmatter]] — Metadatos que controlan cuándo se cargan las instrucciones
- [[agentes-multiples]] — Patrón developer/reviewer con agentes especializados
- [[github-actions]] — Automatización con IA (charla futura)
- [[graphify]] — Grafo de conocimiento del codebase

---

## Principios de la serie

**Demo primero, siempre.** La audiencia desconecta en los bloques teóricos y vuelve en las demos. Cada charla maximiza el tiempo de demostración en vivo.

**Narrativa acumulativa.** Lo que se explica en una charla es la base de la siguiente. No se reintroduce sin una decisión consciente.

**Audiencia mixta.** De 60 a 90 asistentes: developers junior y senior, RRHH, directivos, comerciales. Los conceptos tienen que aterrizar para todos.

**Herramientas reales.** Las demos usan proyectos reales (RCA), herramientas del día a día (Jira, Copilot, GitHub) y flujos que la audiencia puede reproducir.

---

## Para colaboradores

Si eres nuevo en este vault, empieza por leer [[arnes-completo]] — es el mapa mental que da coherencia a toda la serie.

El repo de la web (Next.js) es la fuente de verdad para el código de las charlas. Este vault es la fuente de verdad para la narrativa, los guiones y las decisiones de diseño.
