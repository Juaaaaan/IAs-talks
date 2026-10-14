---
type: Demo
title: "Demo — El menú de OpenCode: elegir el motor (Charla 20)"
description: "Paso a paso de la demo de Charla 20: mostrar el selector de modelo/proveedor de OpenCode, los modos Plan vs Build, y un flujo de trabajo de principio a fin sobre un proyecto real, para dejar claro que el motor y los datos quedan bajo control propio."
tags: [demo, opencode, ejecutor, plan-build, gobernanza]
related: [charla-20-el-ejecutor-abierto, opencode]
charla: "Charla 20"
estado: "✅ Ejecutada"
timestamp: "2026-09-16"
---

# Demo — El menú de OpenCode: elegir el motor (Charla 20)

**Charla:** [[charla-20-el-ejecutor-abierto]]
**Herramienta:** OpenCode (TUI)
**Duración:** 10-15 min

---

## Objetivo de la demo

No es una demo de construcción de principio a fin — es mostrar el momento concreto donde la diferencia con un ejecutor cerrado se hace visible: el selector de modelo/proveedor, y el modo Plan que razona sin tocar nada.

---

## Preparación previa

- OpenCode instalado y autenticado contra al menos dos proveedores distintos (p. ej. Anthropic + un modelo vía Ollama local o OpenRouter)
- Un proyecto ya inicializado con `/init` (con `AGENTS.md` generado) abierto en terminal
- Terminal con tamaño de fuente verificado para proyección

---

## Paso a paso

### Paso 1 — Arrancar y mostrar el selector (4 min)

```bash
cd proyecto-demo
opencode
```

Dentro de la TUI:

```
/models
```

**Resultado esperado:** se abre el selector con los proveedores conectados, incluido al menos uno local/interno. Remarcar en voz alta: *"esto, en Claude Code o Copilot, no existe — el motor viene decidido."*

### Paso 2 — Modo Plan (5 min)

Pedir una tarea sencilla y mostrar que, en modo Plan, el agente razona y propone sin tocar ningún fichero:

```
Añade un endpoint para exportar pedidos a CSV, con tests
```

**Resultado esperado:** un plan propuesto, edición y comandos deshabilitados — el "piensa antes de actuar" metido en la herramienta misma.

### Paso 3 — Cambiar a Build y ejecutar (4 min)

Cambiar de modo y dejar que ejecute, mostrando el diff que va generando y, si algún permiso está en `ask`, el momento en que pide confirmación antes de un cambio irreversible — callback directo al checkpoint humano de la Charla 19.

---

## Prompts de referencia

```
/models
```

```
Añade un endpoint para exportar pedidos a CSV, con tests
```

---

## Plan B

Si la autenticación contra el proveedor local falla en directo: tener capturas del selector ya configurado de un ensayo previo y narrar esa parte sin re-conectar en vivo.

---

## Checklist pre-demo

- [ ] Al menos dos proveedores distintos conectados y verificados antes de empezar
- [ ] Proyecto demo con `AGENTS.md` ya generado
- [ ] Ensayo completo realizado
- [ ] Conexión a internet verificada (salvo para el proveedor local)
