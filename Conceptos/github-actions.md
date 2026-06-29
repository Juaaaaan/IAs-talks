# GitHub Actions — Automatización con IA

> Concepto introducido brevemente en Charla 8. Contenido completo en una charla futura.

---

## Qué es

GitHub Actions es el sistema de automatización de GitHub. Permite definir flujos de trabajo (workflows) que se ejecutan automáticamente cuando ocurre algo en el repositorio: un push, una pull request, un merge, una etiqueta, o incluso en un horario definido.

Los workflows se definen en ficheros YAML dentro de `.github/workflows/`.

---

## Casos de uso básicos

- Ejecutar tests automáticamente en cada push
- Hacer el build de producción antes de mergear
- Desplegar automáticamente cuando se mergea a main
- Notificar al equipo cuando falla algo

---

## Por qué es relevante con IA

GitHub Actions + Copilot coding agent es una combinación especialmente potente:

- Copilot puede ejecutarse automáticamente en respuesta a eventos del repo
- Un agente puede revisar pull requests, generar tests o documentación de forma autónoma
- Los workflows pueden orquestar múltiples agentes en pipelines complejos

---

## Relación con lo que ya sabemos

Los ficheros de `.github/` que vimos en la Charla 8 conviven con los workflows de Actions en la misma carpeta:

```
.github/
├── copilot-instructions.md    # Instrucciones para Copilot
├── AGENTS.md                  # Instrucciones para agentes
├── agents/                    # Agentes especializados
├── instructions/              # Instrucciones por contexto
└── workflows/                 # GitHub Actions — automatización
    └── ci.yml
```

---

## Dónde aparece en la serie

| Charla | Rol |
|---|---|
| 8 | Mención de contexto — la carpeta `.github/` |
| Futura | Charla completa — GitHub Actions + Copilot coding agent |
