---
type: Concepto
title: "IA local — El modelo en tus propios equipos"
description: "Ejecutar un modelo en tu ordenador o en servidores bajo tu control en lugar de usar un servicio externo. Da más control sobre los datos, a cambio de asumir hardware, mantenimiento y seguridad."
tags: [ia-local, on-premise, privacidad, soberania, modelos-abiertos]
related: [modelos-abiertos-vs-cerrados, federated-ai, modelos-pequenos-slm, cuantizacion, privacidad-y-anonimizacion]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# IA local

> _"Los datos no tienen por qué salir de casa, pero la casa la cuidas tú."_

---

## Qué es

La **IA local** consiste en ejecutar el modelo en un **equipo propio** o en infraestructura bajo tu control. Requiere un modelo cuyos pesos puedas obtener y cuya licencia permita el uso que quieres darle.

> [[federated-ai]] trata la estrategia general de no depender de un proveedor. Esta nota se centra en **ejecutar en local**.

---

## Ventajas y costes

| A favor | En contra |
|---|---|
| Más control sobre dónde se procesan los datos | Necesitas hardware adecuado |
| Puede funcionar sin conexión | Lo mantienes y actualizas tú |
| Sin pago por petición a un proveedor | No es gratis: equipos, energía y personas |
| Control sobre la versión del modelo | Los modelos que caben pueden rendir menos |

---

## Local no es automáticamente seguro

- La **aplicación** que ejecuta el modelo puede conectarse a internet o usar servicios en la nube: compruébalo
- Los **registros** y documentos locales también hay que protegerlos
- Descarga modelos y programas solo de **fuentes de confianza**
- En el trabajo, instalar algo por tu cuenta sin aprobación también es [[shadow-ai]]

---

## Relación con otras piezas

- **[[modelos-abiertos-vs-cerrados]]** — Qué modelos se pueden descargar
- **[[modelos-pequenos-slm]]** — Los más asequibles de ejecutar
- **[[cuantizacion]]** — Ayuda a que quepan en menos memoria
- **[[privacidad-y-anonimizacion]]** — Las obligaciones sobre los datos siguen existiendo
