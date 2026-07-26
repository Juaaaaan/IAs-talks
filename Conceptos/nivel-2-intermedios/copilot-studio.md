---
type: Concepto
title: "Copilot Studio"
description: "Plataforma de Microsoft para crear agentes de IA sin código dentro del ecosistema corporativo, con conocimiento propio vía SharePoint y despliegue en Teams"
tags: [copilot-studio, microsoft, agentes, teams, sharepoint, no-code]
related: [agente-ia, rag, embeddings, metricas-ia]
charla: "Charla 13"
estado: "✅ Publicado"
timestamp: "2026-07-22"
---

# Copilot Studio

> _"La diferencia entre un LLM genérico y un agente de Copilot Studio es la misma que entre un becario recién llegado y alguien que lleva tres años en la empresa y conoce todos los procesos."_

---

## Qué es

Copilot Studio es la plataforma de Microsoft para crear [[agente-ia|agentes de IA]] dentro del ecosistema corporativo. Es la respuesta a la pregunta: ¿cómo construyo algo inteligente que sepa cosas de mi empresa sin que ningún dato salga fuera?

Tres ideas clave:

- **No necesita código.** Interfaz visual, pasos secuenciales: nombre del agente, instrucciones de comportamiento, documentos de conocimiento, canal de despliegue. Cualquier persona — RRHH, comercial, operaciones, soporte — puede construir un agente.
- **El conocimiento es de la empresa y se queda en la empresa.** Los documentos conectados no salen de la organización. El agente accede a ellos vía SharePoint con las mismas credenciales corporativas de siempre.
- **Vive donde ya se trabaja.** El agente se despliega en Teams, en un canal dedicado. No hay una app nueva que aprender.

---

## LLM genérico vs agente de Copilot Studio

| LLM genérico (ChatGPT, Copilot 365 sin configurar) | Agente de Copilot Studio |
|---|---|
| Responde con conocimiento general del mundo | Responde con el conocimiento específico que le conectas |
| No sabe cuántos empleados sois ni vuestros procesos internos | Puede responder preguntas sobre vuestro handbook, procesos, políticas |
| Útil para redactar, explicar, resumir, traducir | Útil para preguntas que solo existen dentro de la empresa |

---

## Cómo se construye un agente (pasos de referencia)

1. **Abrir Copilot Studio** — interfaz principal en `make.preview.microsoft.com`
2. **Crear el agente y configurar instrucciones** — texto en lenguaje natural: para qué sirve, cómo debe comportarse, qué hacer cuando no tiene información
3. **Conectar el conocimiento** — sección Knowledge, documentos vía URL de SharePoint (el entorno LITE no permite subir ficheros directamente); por debajo ocurre el proceso de [[rag]] y [[embeddings]]
4. **Desplegar en Teams** — se crea un canal dedicado; cualquier persona con acceso puede hablar con el agente sin instalar nada

> ⚠️ Nota técnica: en el entorno LITE, el panel de test interno no tiene credenciales corporativas, así que no puede acceder al conocimiento vía SharePoint. La forma correcta de probar el agente es desde Teams, autenticado.

---

## Medir si el agente funciona

Copilot Studio incluye un dashboard de analytics con tres métricas base — ver **[[metricas-ia]]** para el detalle:

- **Engagement rate** — ¿le hicieron al menos una pregunta los que lo abrieron?
- **Resolution rate** — ¿se resolvió el problema sin escalar?
- **Deflection rate** — ¿cuántas solicitudes atendió sin intervención humana?

También permite definir métricas personalizadas en lenguaje natural (p. ej. "¿el usuario expresó satisfacción al final de la conversación?").

---

## Relación con otras piezas

- **[[agente-ia]]** — Lo que se construye en la plataforma
- **[[rag]]** y **[[embeddings]]** — Cómo el agente accede al conocimiento conectado
- **[[metricas-ia]]** — Cómo se mide si el agente está funcionando de verdad

---

## Dónde aparece en la serie

| Charla | Rol de Copilot Studio |
| ------ | --------------- |
| 13 | Introducción + demo en vivo: construcción del "Agente de bienvenida" con el handbook corporativo, despliegue en Teams, dashboard de analytics |
