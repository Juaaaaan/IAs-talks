---
type: Concepto
title: "Modelos abiertos vs cerrados — Las dos familias del panorama IA"
description: "El panorama de modelos de 2026 se divide en dos familias: los cerrados o propietarios (OpenAI, Anthropic, Google, xAI), que usas vía API o app; y los abiertos u open-weight (DeepSeek, Qwen, Kimi, GLM, Mistral), cuyos pesos puedes descargar y ejecutar en tu propia máquina. La elección no es solo de capacidad o precio: en la empresa entra la residencia de datos."
tags: [modelos, abiertos, cerrados, open-weight, proveedores, coste, gobernanza, decision]
related: [model-routing, ai-governance, federated-ai, reasoning-models]
estado: "✅ Publicado"
timestamp: "2026-08-17"
---

# Modelos abiertos vs cerrados — Las dos familias del panorama IA

> _"No os aprendáis los nombres, que la semana que viene son otros. Aprendeos que hay dos familias — y que en la empresa, la elección la marca también dónde acaban tus datos."_

---

## Qué son

El panorama de modelos se organiza en **dos grandes familias**:

- **Cerrados (propietarios):** solo accesibles vía API o app del proveedor. No ves ni descargas el modelo; pagas por usarlo. Fiables, fáciles, pensados para empresa.
- **Abiertos (open-weight):** el proveedor publica los **pesos** del modelo, así que puedes descargarlo y **ejecutarlo en tu propia máquina o servidor**. Suelen ser más baratos vía API y permiten control total.

> Matiz: "open-weight" (pesos públicos) no es lo mismo que "open-source" estricto (también código y datos de entrenamiento). La mayoría de los "abiertos" son open-weight.

---

## Las dos familias (agosto 2026)

| | Cerrados | Abiertos (open-weight) |
|---|---|---|
| **Proveedores** | OpenAI (GPT), Anthropic (Claude), Google (Gemini), xAI (Grok) | DeepSeek, Qwen (Alibaba), Kimi (Moonshot), GLM (Z.ai), Mistral (EU) |
| **Acceso** | API / app de pago | Descargables + API |
| **Coste** | Mayor | Mucho menor (hasta 5-30× según carga) |
| **Control / privacidad** | Dependes del proveedor | Puedes ejecutarlo tú, sin que los datos salgan |
| **Facilidad / soporte** | Alto, enterprise-ready | Requiere más trabajo técnico |

> ⚠️ Nombres a agosto 2026. Cambian cada semana; las **familias y los criterios** no.

---

## El titular de 2026

Los modelos abiertos —muchos chinos— **han alcanzado a los grandes cerrados** en muchas tareas, a una fracción del precio. Esto ha sacudido el mercado: ya no hay solo dos o tres opciones serias, y el coste ha dejado de ser una barrera.

---

## El factor empresa: residencia de datos

Para una organización, "potente y barato" no basta. Muchas APIs de modelos chinos **corren desde China**, lo que plantea una cuestión de **dónde acaban los datos** que le envías. Para cargas reguladas, eso es un factor de decisión de primer orden.

**Regla de oro corporativa:** en el trabajo, usar solo lo aprobado internamente (habitualmente proveedores 🇺🇸/🇪🇺 con garantías de residencia y cumplimiento). La experimentación personal es otra cosa.

---

## Cuándo usar cada uno

- **Cerrado:** primera opción para la mayoría — fiabilidad, soporte, integración, cumplimiento.
- **Abierto:** cuando el coste a escala es crítico, cuando necesitas **ejecutarlo en tu propio entorno** por privacidad/soberanía, o cuando quieres no depender de un solo proveedor (ver [[federated-ai]]).

---

## Relación con otras piezas

- **[[model-routing]]** — Elegir familia y modelo por tarea es una decisión de routing
- **[[ai-governance]]** — La residencia de datos y el cumplimiento son el corazón de la gobernanza
- **[[federated-ai]]** — No depender de un único proveedor es una de las razones para mirar a los abiertos
- **[[reasoning-models]]** — Tanto cerrados como abiertos ofrecen ya variantes "que razonan"

---

## Referencias

- [Artificial Analysis — Intelligence Index](https://artificialanalysis.ai/)
