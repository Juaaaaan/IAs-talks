---
type: Concepto
title: "Privacidad y anonimización — Qué datos pueden entrar en una IA"
description: "Antes de pegar información en una herramienta de IA hay que saber si está permitida. Anonimizar no es solo borrar el nombre: si se puede volver a identificar a la persona, sigue siendo un dato personal."
tags: [privacidad, anonimizacion, seudonimizacion, rgpd, datos, seguridad, fundamentos]
related: [shadow-ai, ai-governance, ia-local, synthetic-data, trifecta-letal]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Privacidad y anonimización

> _"Quitar el nombre no siempre quita a la persona."_

---

## Dos términos que se confunden

| | Anonimización | Seudonimización |
|---|---|---|
| **Qué hace** | Impide identificar a la persona con medios razonables | Sustituye identificadores, pero se puede relacionar de nuevo usando información adicional |
| **¿Sigue siendo dato personal según el RGPD?** | No, si es efectiva | **Sí** |
| **Ejemplo** | Estadísticas agregadas que no permiten aislar a nadie | Cambiar el nombre por "Cliente 4821" guardando la tabla de equivalencias |

---

## La trampa de los datos indirectos

Un texto sin nombre puede identificar a alguien si combina puesto, localidad, fechas y un suceso poco común.

---

## Antes de pegar algo, pregúntate

1. **¿La herramienta está aprobada** por la empresa para este tipo de dato?
2. **¿Hay datos personales, de clientes o confidenciales?**
3. **¿Son necesarios** para la tarea? Si no, no los incluyas
4. **¿Puedo usar datos ficticios** o describir la estructura sin el contenido real?
5. **En caso de duda**, consulta a quien lleve protección de datos

---

## Ejemplo práctico

Para pedir ayuda con una fórmula no hace falta subir el Excel real: basta con describir las columnas y poner tres filas inventadas.

> Esta nota es orientativa y no es asesoramiento legal. Manda la política de tu empresa.

---

## Relación con otras piezas

- **[[shadow-ai]]** — El riesgo de usar herramientas no aprobadas
- **[[ai-governance]]** — Las reglas de la organización
- **[[ia-local]]** — Ejecutar el modelo en tu propia infraestructura
- **[[synthetic-data]]** — Datos artificiales como alternativa, con sus propias precauciones

---

## Referencias

- [RGPD — Reglamento (UE) 2016/679](https://eur-lex.europa.eu/eli/reg/2016/679/oj) (artículo 4.5 y considerando 26)
