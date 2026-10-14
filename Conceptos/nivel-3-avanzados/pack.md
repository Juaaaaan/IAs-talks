---
type: Concepto
title: "Pack — Módulo instalable de capacidades"
description: "Subconjunto modular e instalable de agentes, skills, workflows u otros activos de AI SDLC Foundation que puede distribuirse de forma independiente sin exigir un paquete monolítico."
tags: [ai-sdlc-foundation, pack, modularidad, distribucion, skills, workflows]
related: [ai-sdlc-foundation, apm, agent, knowledge, skill-foundation, workflow]
estado: "📋 Planificado"
timestamp: "2026-09-15"
---

# Pack — Módulo instalable de capacidades

> _"No todo tiene que viajar junto: un buen sistema también sabe distribuir subconjuntos útiles."_

---

## Qué es

En AI SDLC Foundation, **Pack** es un módulo instalable que agrupa un subconjunto de capacidades relacionadas para poder distribuirlas y activarlas de forma independiente. Puede contener agentes, [[skill-foundation]], [[workflow]]s, plantillas o configuraciones complementarias, siempre que tenga una frontera funcional clara. La idea central es modularizar el sistema para que cada equipo instale lo que necesita y no un bloque indivisible.

---

## Papel en AI SDLC Foundation

Pack es la unidad operativa que conecta el diseño reusable de Foundation con su distribución real. Un [[apm]] puede instalarlo, un agente puede descubrir sus activos en runtime y un equipo puede versionarlo de forma separada del resto del catálogo. Esto hace más fácil compartir capacidades entre dominios, por ejemplo documentación, seguridad o soporte de arquitectura, sin copiar manualmente los mismos activos en cada proyecto.

---

## Cómo funciona

El pack define qué activos se empaquetan juntos, qué dependencias conceptuales tienen y cómo deben ponerse a disposición del entorno destino. Después se distribuye e instala como módulo independiente dentro del ecosistema. Su límite importante es estructural: un pack no necesita contener todas las clases de activo posibles, y de hecho conviene que reutilice piezas compartidas antes que duplicarlas solo para ser autosuficiente.

---

## Ejemplos prácticos

### Ejemplo 1 — Pack de seguridad

Un equipo publica un pack con skills de revisión de secretos, plantillas de threat modeling y workflows para endurecimiento de cambios sensibles. Otros repositorios lo instalan sin tener que adoptar todo el catálogo de Foundation.

### Ejemplo 2 — Pack de documentación

Otro pack reúne un agente de documentación, varias skills editoriales y plantillas para ADR o guías técnicas. El área de producto lo instala porque necesita esa capacidad, aunque no requiera los activos de seguridad o de análisis operativo.

---

## Matices y confusiones habituales

- **Cuidado:** Un pack no tiene por qué incluir todos los tipos de activo de Foundation; basta con que encapsule un conjunto útil y coherente.
- **Cuidado:** Duplicar activos compartidos dentro de varios packs complica versiones, mantenimiento y trazabilidad.
- **Importante:** Si la frontera del pack es demasiado difusa, termina convirtiéndose en un contenedor genérico que pierde su valor modular.

---

## Relación con otras piezas

- **[[ai-sdlc-foundation]]** — Muestra cómo los packs materializan la modularidad del sistema.
- **[[apm]]** — Suele encargarse de instalar, actualizar o distribuir estos módulos.
- **[[agent]]** — Puede ser uno de los activos incluidos o un consumidor de lo que el pack pone disponible.
- **[[knowledge|Knowledge]]** — Los packs pueden distribuir skills que encapsulan este conocimiento
- **[[skill-foundation]]** — Es un ejemplo habitual de activo empaquetado dentro de un pack.
- **[[workflow]]** — Puede viajar junto a skills y agentes cuando la capacidad requiere una orquestación completa.
