---
type: Concepto
title: "Decisión: Sin modo oscuro en RCA"
description: "Por qué no implementamos dark mode en el proyecto RCA — el sistema de diseño Artisanal Ether no lo contempla y el cliente no lo ha solicitado."
tags: [rca, diseño, dark-mode, artisanal-ether, decision]
related: [decisiones-arquitectura, contexto-proyecto]
timestamp: "2026-07-07"
---

# Decisión: Sin modo oscuro en RCA

---

## La decisión

**No implementamos modo oscuro en el proyecto RCA.** La aplicación funciona exclusivamente con el tema claro definido en el sistema de diseño Artisanal Ether.

---

## Por qué

**El sistema de diseño Artisanal Ether está definido únicamente en tonos cálidos.** La paleta de colores, las superficies y los contrastes están diseñados para un modo claro con tonos tierra y ámbar. No existe una variante oscura del sistema, y crearla implicaría rediseñar desde cero la identidad visual.

**El cliente no lo ha pedido.** No hay requisito funcional ni expectativa del cliente respecto a dark mode. Implementarlo de forma proactiva consumiría tiempo de desarrollo sin aportar valor al entregable.

**La coherencia visual es prioritaria.** Artisanal Ether transmite calidez artesanal — ese concepto se pierde con fondos oscuros. Forzar una adaptación oscura degradaría la experiencia de marca.

---

## Lo que NO se debe hacer

- No añadir `prefers-color-scheme` media queries.
- No crear variables CSS con prefijo `--dark-*`.
- No instalar librerías de theming (ej. `@angular/material` theming dual) para este propósito.
- No usar colores fuera de los tokens definidos en Artisanal Ether.

---

## Cuándo reconsiderar

Si el cliente solicita explícitamente modo oscuro, o si Artisanal Ether publica una variante dark oficial. En ese caso, la implementación debería partir de tokens de diseño actualizados, no de una inversión de colores ad-hoc.
