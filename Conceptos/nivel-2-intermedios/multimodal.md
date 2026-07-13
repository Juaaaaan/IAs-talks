---
type: Concepto
title: "Multimodal — LLMs que ven, oyen y leen"
description: "Modelos de IA que procesan múltiples tipos de entrada: texto, imagen, audio, vídeo. Permiten interacciones más naturales y tareas que antes requerían herramientas separadas."
tags: [multimodal, vision, audio, imagen, video, modelos]
related: [context-engineering, function-calling, embeddings]
estado: "✅ Publicado"
timestamp: "2026-07-09"
---

# Multimodal — LLMs que ven, oyen y leen

> _"La IA ya no solo lee texto. Puede ver tu pantalla, escuchar tu reunión y leer tu documento — todo a la vez."_

---

## Qué es

Un modelo **multimodal** es un LLM que puede procesar y/o generar múltiples tipos de contenido:

- **Texto** → leer y escribir (todos los LLMs)
- **Imagen** → ver y describir / generar
- **Audio** → escuchar y transcribir / generar voz
- **Vídeo** → analizar secuencias visuales
- **Código** → leer, escribir y ejecutar

---

## Evolución

```
2022: Solo texto (GPT-3)
2023: Texto + imagen entrada (GPT-4V, Claude 3)
2024: Texto + imagen + audio (GPT-4o, Gemini)
2025: Texto + imagen + audio + vídeo (Gemini 2, GPT-5)
2026: Nativo multimodal (texto + imagen + audio + vídeo + código)
```

---

## Casos de uso prácticos

| Modalidad | Ejemplo real |
|---|---|
| Texto + Imagen | "¿Qué componente Angular implementa este mockup?" |
| Texto + Audio | Transcribir reuniones y extraer action items |
| Texto + Pantalla | Computer Use — la IA ve y opera tu escritorio |
| Texto + Vídeo | Analizar una grabación de demo y generar documentación |
| Imagen → Código | Convertir un diseño Figma en componentes |

---

## Por qué importa para developers

1. **Figma → Código:** Pasar un diseño visual y que genere el componente
2. **Screenshot → Bug report:** Fotografiar un error y que lo diagnostique
3. **Diagrama → Implementación:** Dar un diagrama de arquitectura y que lo implemente
4. **Reunión → Documentación:** Audio de reunión → decisiones documentadas en el vault

---

## Modelos multimodales actuales (2026)

| Modelo | Texto | Imagen | Audio | Vídeo |
|---|---|---|---|---|
| GPT-5 | ✅ | ✅ | ✅ | ✅ |
| Claude Opus/Sonnet | ✅ | ✅ | ❌ | ❌ |
| Gemini 2.5 | ✅ | ✅ | ✅ | ✅ |
| Llama 4 | ✅ | ✅ | ❌ | ❌ |

---

## Limitaciones

- **Alucinaciones visuales:** La IA puede "ver" cosas que no están en la imagen
- **OCR imperfecto:** Texto manuscrito o en mala resolución falla
- **Costo:** Procesar imágenes/audio consume más tokens
- **Privacidad:** Cuidado con qué imágenes/audio envías a APIs externas

---

## Relación con otras piezas

- **[[context-engineering]]** — Las imágenes y audio son capas adicionales de contexto
- **[[function-calling]]** — Los modelos multimodales pueden decidir acciones basadas en lo que ven
- **[[embeddings]]** — Existen embeddings multimodales (CLIP) que conectan texto e imagen

---

## Referencias

- [GPT-4o Vision capabilities](https://platform.openai.com/docs/guides/vision)
- [Gemini Multimodal](https://ai.google.dev/gemini-api/docs/vision)
