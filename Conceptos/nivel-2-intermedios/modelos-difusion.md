---
type: Concepto
title: "Modelos de difusión — Del ruido a la imagen"
description: "Familia de modelos generativos que aprende a revertir un proceso de añadir ruido. Es una técnica muy usada para generar imágenes, y también se aplica a vídeo y audio."
tags: [difusion, diffusion, imagen, video, generativa, modelos]
related: [ia-generativa, multimodal, transformer-atencion, deepfakes-y-etiquetado]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Modelos de difusión

> _"Aprende a limpiar ruido hasta que, paso a paso, aparece algo nuevo."_

---

## Qué es

Durante el entrenamiento, se **añade ruido** a los datos de forma gradual y el modelo aprende a **revertir** ese proceso. Para generar, parte de ruido y lo va refinando. En los generadores de imagen, una **descripción en texto** suele guiar el resultado.

---

## La idea en un esquema

```
Aprender:  imagen → un poco de ruido → más ruido → ruido
Generar:   ruido  → menos ruido      → …         → imagen nueva
              ↑
        guiado por tu descripción
```

Es una simplificación: muchos sistemas trabajan sobre una representación comprimida, no directamente sobre los píxeles. Y no todos los generadores de imagen usan difusión.

---

## Para pedir mejores imágenes

- Sujeto, entorno, encuadre, estilo e iluminación
- Para qué se va a usar y en qué formato
- Iterar cambiando **pocas cosas cada vez**

## Cosas a revisar

- Texto dentro de la imagen, manos, detalles y coherencia
- Derechos de uso y política de la empresa
- Si puede confundirse con algo real (ver [[deepfakes-y-etiquetado]])

---

## Relación con otras piezas

- **[[ia-generativa]]** — La categoría general
- **[[multimodal]]** — Sistemas que combinan texto, imagen y audio
- **[[transformer-atencion]]** — Algunos modelos de difusión usan transformers
- **[[deepfakes-y-etiquetado]]** — Riesgos y transparencia

---

## Referencias

- [Denoising Diffusion Probabilistic Models (Ho et al., 2020)](https://arxiv.org/abs/2006.11239)
