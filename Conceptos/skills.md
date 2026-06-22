# Skills — El Arnés de Comportamiento

> _"El Skill no es lo que le pedís a la IA. Es lo que la IA ya sabe sobre cómo trabajáis antes de que le pidáis nada."_

---

## Qué es un Skill

Un Skill no es un prompt. No es algo que se escribe cada vez que se abre una conversación.

Un Skill es **contexto persistente**: una configuración que le dice a la IA quién es la empresa, cómo trabaja el equipo, qué tono usar, qué reglas seguir siempre, qué documentos son referencia.

---

## La diferencia clave

|Sin Skill|Con Skill|
|---|---|
|Cada conversación empieza desde cero|Cada conversación arranca ya con el contexto cargado|
|El usuario tiene que explicar el contexto|El contexto está siempre disponible|
|Respuestas inconsistentes entre personas del equipo|Respuestas consistentes para todos|

---

## En la metáfora del arnés

Si el `spec.md` son las instrucciones para una **carrera concreta**, el Skill es el **entrenamiento del caballo**: lo que sabe hacer siempre, antes de que le des ninguna instrucción.

---

## Cómo se implementa en Claude

En Claude, los Skills se implementan a través de **Projects** (`claude.ai`):

1. Se crean instrucciones persistentes (system prompt del proyecto)
2. Se adjuntan documentos de referencia (procedimientos, guías de estilo, estructuras de datos)
3. Se define el comportamiento esperado

A partir de ahí, cada conversación dentro del proyecto arranca con ese contexto ya cargado, para cualquier persona del equipo que lo use.

---

## Ejemplo práctico — Equipo de siniestros

Un Skill configurado para el equipo de siniestros sabría:

- Cómo se estructura una póliza en la empresa
- Los procedimientos internos de tramitación
- El tono adecuado para comunicaciones con clientes
- Los criterios de escalado según tipo de siniestro

Cualquier persona del equipo obtendría respuestas consistentes sin tener que explicar nada.

---

## Relación con otras piezas

- **[[sdd]]** — El SDD define qué construir en un proyecto concreto; el Skill define cómo comportarse siempre
- **[[mcp]]** — Los MCPs son el paso siguiente: permiten que la IA actúe fuera de la conversación
- **[[arnes-completo]]** — El Skill es la segunda pieza del arnés

---

## Dónde aparece en la serie

|Charla|Rol de los Skills|
|---|---|
|7|Introducción del concepto — Bloque 2|
|Futuras|Aplicación en contextos específicos del sector|