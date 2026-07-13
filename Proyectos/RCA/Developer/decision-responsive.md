---
type: Concepto
title: "Decisión: Implementar responsive en RCA"
description: "El sistema de diseño Artisanal Ether solo define versión desktop. El cliente requiere visualización en tablet y mobile. Se implementa responsive con estrategia desktop-first y breakpoints estándar."
tags: [rca, diseño, responsive, artisanal-ether, decision, tailwind, breakpoints]
related: [decisiones-arquitectura, contexto-proyecto, decision-no-dark-mode]
timestamp: "2026-07-08"
---

# Decisión: Implementar responsive en RCA

---

## La decisión

**Implementamos diseño responsive en el proyecto RCA.** La aplicación debe visualizarse correctamente en desktop, tablet (768px) y mobile (375px), utilizando una estrategia desktop-first.

---

## Por qué

**El cliente lo ha solicitado explícitamente.** En reunión del 8 de julio de 2026, el cliente requirió que la web sea accesible desde tablet y dispositivo móvil.

**El sistema de diseño Artisanal Ether solo define versión desktop.** No existen maquetas para tablet ni mobile. Esto significa que las adaptaciones responsive serán decisiones de desarrollo — no hay un diseño de referencia por debajo de desktop.

**El tráfico esperado lo justifica.** Una tienda online de joyería artesanal recibe un porcentaje significativo de tráfico móvil. Sin responsive, se pierde conversión directa.

---

## Estrategia: desktop-first

**La dirección es de arriba hacia abajo:** los estilos base corresponden al diseño desktop de Artisanal Ether (que ya existe y está implementado), y se añaden media queries descendentes para adaptar a tablet y mobile.

Esto implica en Tailwind v4:
- Los estilos sin prefijo representan la versión desktop (base del sistema de diseño).
- Se usan breakpoints descendentes con `max-*` o se definen breakpoints custom en `@theme {}`.

---

## Breakpoints definidos

| Breakpoint | Ancho | Dispositivo |
|---|---|---|
| Desktop | ≥ 1024px | Pantalla completa |
| Tablet | 768px – 1023px | iPad, tablets Android |
| Mobile | < 768px | Smartphones (ref: 375px) |

---

## Reglas de implementación

- **Respetar la identidad visual.** La paleta, tipografías y tokens de Artisanal Ether no cambian — solo cambia la disposición y el espaciado.
- **Layouts que colapsan, no que se redesignan.** Grids pasan de multi-columna a columna única. Navegación se convierte en hamburger menu. Los componentes no cambian de apariencia, solo de distribución.
- **Imágenes adaptativas.** Usar `srcset` / `NgOptimizedImage` para servir resoluciones apropiadas por pantalla.
- **Decisiones de adaptación se documentan aquí.** Como no hay maquetas de referencia, cada decisión de layout responsive que no sea obvia debe registrarse en este fichero.

---

## Lo que NO se debe hacer

- No crear un diseño mobile completamente diferente al desktop — la marca debe ser coherente.
- No usar `display: none` extensivamente para ocultar secciones enteras en mobile. Si algo no cabe, se reorganiza.
- No añadir librerías CSS adicionales para el responsive. Tailwind v4 es suficiente.
- No implementar responsive "pixel perfect" sin maquetas — el objetivo es usabilidad, no precisión de diseño.

---

## Cuándo reconsiderar

Si el equipo de diseño de Artisanal Ether publica maquetas específicas para tablet y mobile, se deben revisar las adaptaciones implementadas y ajustar a las maquetas oficiales. En ese caso, la estrategia podría pivotar de desktop-first a design-token-first si los breakpoints del sistema de diseño difieren de los estándar.
