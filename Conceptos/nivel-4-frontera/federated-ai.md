---
type: Concepto
title: "Federated & Decentralized AI — IA sin depender de un solo proveedor"
description: "Modelos y arquitecturas que reducen la dependencia de un único proveedor de IA: modelos locales, edge AI, multi-cloud, open-source. Soberanía tecnológica sobre la IA."
tags: [federado, descentralizado, local, edge, open-source, soberania, privacidad]
related: [model-routing, ai-governance, caching-cost, reasoning-models]
estado: "✅ Publicado"
timestamp: "2026-07-13"
---

# Federated & Decentralized AI — IA sin depender de un solo proveedor

> _"Si toda tu IA depende de una API, toda tu IA depende de una factura."_

---

## Qué es

**Federated/Decentralized AI** engloba las estrategias para usar IA sin depender exclusivamente de un proveedor centralizado (OpenAI, Anthropic, Google).

Incluye modelos locales, edge computing, estrategias multi-cloud y modelos open-source.

---

## Por qué importa

| Riesgo de dependencia | Solución descentralizada |
|---|---|
| El proveedor cambia precios | Modelos alternativos / locales |
| Caída del servicio | Fallback a otro proveedor |
| Datos confidenciales en la nube | Modelo local que no sale de tu red |
| Regulación (EU AI Act) exige control | Ejecución on-premise |
| Latencia de red | Edge AI (procesamiento local) |

---

## Estrategias

### 1. Modelos open-source
```
Llama (Meta), Mistral, Qwen, Gemma
→ Descargables, ejecutables en tu infra, sin API fees
```

### 2. Ejecución local
```
Ollama, LM Studio, vLLM
→ Ejecutas el modelo en tu máquina o servidor
→ Los datos nunca salen de tu red
```

### 3. Multi-provider
```
Router que elige entre OpenAI, Anthropic, Google, local
→ Si uno falla, usa otro
→ Optimiza coste/calidad por proveedor
```

### 4. Edge AI
```
Modelos pequeños que corren en dispositivos:
Móvil, laptop, IoT, navegador
→ Sin internet, sin latencia de red
```

### 5. Federated Learning
```
El modelo se entrena en datos distribuidos
→ Los datos nunca salen de cada organización
→ Solo se comparten los pesos/gradientes
```

---

## Tradeoffs

| Aspecto | Centralizado (API) | Descentralizado (local) |
|---|---|---|
| Calidad | Mejor (modelos más grandes) | Buena (modelos más pequeños) |
| Coste | Por token | Hardware fijo |
| Privacidad | Datos van al proveedor | Datos se quedan en tu red |
| Mantenimiento | Cero | Gestión de infra |
| Latencia | Red + inferencia | Solo inferencia |
| Escalabilidad | Infinita | Limitada por tu hardware |

---

## Para la empresa

La estrategia ideal suele ser **híbrida**:
- Tareas sensibles → modelo local
- Tareas complejas → API del mejor modelo
- Tareas rutinarias → modelo open-source barato
- Contingencia → multi-provider con fallback

---

## Relación con otras piezas

- **[[model-routing]]** — El routing decide cuándo usar local vs cloud
- **[[ai-governance]]** — La gobernanza define qué datos pueden ir a la nube
- **[[caching-cost]]** — Los modelos locales eliminan costes por token
- **[[reasoning-models]]** — Los reasoning models locales (DeepSeek R1) son una revolución

---

## Referencias

- [Ollama](https://ollama.com/)
- [Meta Llama](https://llama.meta.com/)
- [vLLM](https://vllm.ai/)
- Concepto en glosario: [[glosario-ia-nivel-1]] §26
