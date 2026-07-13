---
type: Concepto
title: "Computer Use — Agentes que controlan la pantalla"
description: "Capacidad de los agentes de IA de ver, navegar y operar interfaces gráficas como lo haría un humano: hacer clic, escribir, navegar webs y usar aplicaciones de escritorio."
tags: [computer-use, browser-use, interfaz, automatizacion, agentes, vision]
related: [multimodal, agentic-workflows, function-calling, autonomous-coding-agents]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Computer Use — Agentes que controlan la pantalla

> _"La IA ya no necesita una API para interactuar con un sistema. Puede usar la interfaz como un humano."_

---

## Qué es

**Computer Use** (o Browser Use) es la capacidad de un agente de IA de:
- Ver la pantalla (screenshot)
- Mover el ratón y hacer clic
- Escribir texto
- Navegar interfaces web o de escritorio
- Interactuar con aplicaciones que no tienen API

---

## Por qué es revolucionario

| Con API | Con Computer Use |
|---|---|
| Necesitas integración técnica | Funciona con cualquier aplicación |
| Solo sistemas que exponen API | Cualquier sistema con interfaz gráfica |
| Requiere desarrollo | Plug and play |
| Estructurado y rápido | Más lento pero universal |

---

## Ejemplo práctico

**Rellenar un formulario de RRHH que no tiene API:**

```
1. El agente ve el formulario (screenshot)
2. Identifica los campos (nombre, fecha, departamento)
3. Hace clic en cada campo
4. Escribe los datos
5. Hace clic en "Enviar"
```

**Antes:** Necesitabas un desarrollador para crear una integración.
**Ahora:** El agente usa la app como lo haría un humano.

---

## Casos de uso

| Caso | Descripción |
|---|---|
| **Testing visual** | El agente navega la app y verifica que se ve correctamente |
| **Data entry** | Rellenar formularios en sistemas legacy |
| **Web scraping inteligente** | Navegar webs dinámicas que no tienen API |
| **Automatización de escritorio** | Usar Excel, SAP, o cualquier app de escritorio |
| **Demo automation** | Preparar demos grabando interacciones |

---

## Proveedores actuales (2026)

| Herramienta | Tipo |
|---|---|
| Anthropic Computer Use | Agente que controla el escritorio |
| OpenAI Operator | Agente web autónomo |
| Playwright + LLM | Browser automation con IA |
| Browser Use (open-source) | Framework para navegación web con LLM |

---

## Riesgos

- **Seguridad:** Un agente con acceso a la pantalla puede ver datos sensibles
- **Velocidad:** Mucho más lento que una API directa
- **Fragilidad:** Los cambios de UI rompen el flujo
- **Control:** Difícil de limitar qué puede hacer el agente

---

## Relación con otras piezas

- **[[multimodal]]** — Computer Use requiere visión (procesamiento de screenshots)
- **[[agentic-workflows]]** — Computer Use habilita workflows sobre sistemas sin API
- **[[function-calling]]** — Computer Use es la alternativa cuando no hay function calling disponible
- **[[autonomous-coding-agents]]** — Algunos agentes de código usan Computer Use para IDEs

---

## Referencias

- [Anthropic Computer Use](https://docs.anthropic.com/en/docs/agents-and-tools/computer-use)
- [Browser Use](https://github.com/browser-use/browser-use)
