---
type: Demo
title: "Demo — El Analista de RFP: equipo de agentes con checkpoint humano (Charla 19)"
description: "Paso a paso de la demo de Charla 19: orquestador + tres agentes especialistas en Copilot Studio analizan el pliego ficticio de una academia de baile, cazan las trampas escondidas, y antes de escribir el Excel final se paran a pedir confirmación humana."
tags: [demo, copilot-studio, agentes, multiagente, power-automate, rfp, checkpoint-humano]
related: [charla-19-de-responder-a-actuar, agentes-multiples, copilot-studio]
charla: "Charla 19"
estado: "✅ Ejecutada"
timestamp: "2026-09-02"
---

# Demo — El Analista de RFP: equipo de agentes con checkpoint humano (Charla 19)

**Charla:** [[charla-19-de-responder-a-actuar]]
**Herramienta:** Copilot Studio (orquestador + 3 agentes hijo) + Power Automate + Excel Online
**Caso:** pliego ficticio de una academia de baile ("Compás")
**Duración:** 20-25 min

---

## Objetivo de la demo

Mostrar que un equipo pequeño de agentes especialistas, coordinados solo por lenguaje natural, puede leer un documento denso, cazar sus trampas y proponer un entregable — pero sin cerrar nada sin que un humano lo confirme primero.

---

## Preparación previa

- Agente orquestador "Analista de RFP" publicado, con los tres agentes hijo (Extractor de requisitos, Detector de riesgos, Estimador de tareas) configurados con `Finalización → No responder`
- Flujo "Requisitos a Excel" conectado como herramienta del orquestador y publicado
- `Entregable-RFP.xlsx` con la tabla `TablaRequisitos` ya creada en OneDrive
- Pliego PDF de la academia de baile "Compás" preparado con las trampas escondidas (ver tabla abajo)

---

## Paso a paso

### Paso 1 — Presentar el equipo (3 min)

Mostrar en pantalla, sin ejecutar nada todavía, los cuatro agentes y explicar la analogía de la asesoría: el orquestador no analiza, reparte y junta.

### Paso 2 — Lanzar el análisis (8 min)

Adjuntar el PDF del pliego en el panel de Test y escribir:

```
Analízame este pliego.
```

**Resultado esperado:** el orquestador delega en los tres especialistas en orden y devuelve un resumen único con requisitos (obligatorios/deseables), riesgos/huecos, y estimación.

Narrar en voz alta, a medida que aparecen en el resumen, las cuatro trampas que el equipo debe cazar:

| Trampa escondida | Qué debe detectar el agente |
|---|---|
| Fecha de decisión anterior a la de entrega de propuestas | Contradicción |
| Segunda sede colada en "fuera del proyecto" pero necesaria | Requisito rescatado de la letra pequeña |
| Presupuesto "limitado" sin cifra | Hueco de información |
| Sin personal técnico, pero "alguien mantendrá el sistema" | Riesgo / contradicción |

### Paso 3 — El checkpoint humano (3 min)

**Momento clave de la demo.** El agente termina el análisis y pregunta explícitamente: *"¿quieres corregir, añadir o quitar algo antes de que lo genere?"*. Pausar aquí y remarcar: no es una limitación, es diseño.

### Paso 4 — Confirmar y generar el Excel (5 min)

```
Sí, genéralo.
```

Cambiar a la ventana de `Entregable-RFP.xlsx` y abrirlo de verdad (no fiarse solo del mensaje de "hecho") para mostrar las filas escritas en vivo.

---

## Prompts de referencia

```
Analízame este pliego.
```

```
Sí, genéralo.
```

---

## Plan B

Si el flujo de Power Automate falla al escribir en Excel: tener una captura o un Excel ya generado de un ensayo previo listo para mostrar, y narrar el paso en vez de re-ejecutar en directo.

---

## Checklist pre-demo

- [ ] Ensayo completo realizado, incluida la publicación del agente tras cualquier cambio
- [ ] `Entregable-RFP.xlsx` limpio (sin filas de ensayos anteriores) antes de empezar
- [ ] Pliego PDF (no Markdown) cargado y verificado
- [ ] Conexión a internet verificada
