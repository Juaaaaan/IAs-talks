---
type: Concepto
title: "Búsqueda semántica — Buscar por significado"
description: "Búsqueda que intenta encontrar contenido por su significado y no solo por coincidencia de palabras. Normalmente usa embeddings, y a menudo se combina con la búsqueda por términos exactos."
tags: [busqueda-semantica, busqueda-hibrida, embeddings, retrieval, rag]
related: [embeddings, rag, base-de-datos-vectorial, reranking, chunking]
estado: "📝 Borrador"
timestamp: "2026-11-27"
---

# Búsqueda semántica

> _"Buscas 'baja por nacimiento' y encuentra el documento que dice 'permiso parental'."_

---

## Qué es

La **búsqueda semántica** intenta encontrar lo que **quieres decir**, aunque el documento use otras palabras. Normalmente compara los [[embeddings]] de la consulta con los del contenido.

> [[embeddings]] explica la **representación numérica**. Esta nota explica **el buscador** que la aprovecha.

---

## Tres formas de buscar

| Tipo | Fuerte en | Flojo en |
|---|---|---|
| **Por palabras** | Códigos, referencias, nombres exactos | Sinónimos y reformulaciones |
| **Semántica** | Preguntas en lenguaje natural | Identificadores exactos |
| **Híbrida** | Combina ambas | Más piezas que ajustar |

---

## Ejemplo práctico

Para encontrar la póliza *"AB-2291"* conviene la búsqueda exacta. Para *"¿qué pasa si se me inunda la cocina?"* ayuda la semántica.

---

## Ojo

- "Parecido" **no significa correcto** ni vigente
- Siempre puede devolver **algo**, aunque no haya ninguna respuesta buena
- Los **permisos** deben respetarse: nadie debe encontrar por significado lo que no puede abrir

---

## Relación con otras piezas

- **[[embeddings]]** — La base técnica habitual
- **[[base-de-datos-vectorial]]** — Dónde se guardan y consultan los vectores
- **[[chunking]]** — Cómo se trocean los documentos antes de indexarlos
- **[[reranking]]** — Reordenar los resultados
- **[[rag]]** — Usa lo encontrado para generar una respuesta
