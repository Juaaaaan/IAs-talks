---
type: Concepto
title: "AI Governance Frameworks — Gobernanza de IA en la empresa"
description: "Marcos normativos y de buenas prácticas para usar IA de forma responsable en la empresa: EU AI Act, ISO 42001, políticas internas, evaluación de riesgos."
tags: [gobernanza, regulacion, eu-ai-act, iso-42001, riesgos, compliance, etica]
related: [ai-act, alfabetizacion-ia, deepfakes-y-etiquetado, constitutional-ai, prompt-injection, eval-benchmarking]
estado: "✅ Publicado"
timestamp: "2026-11-27"
---

# AI Governance Frameworks — Gobernanza de IA en la empresa

> _"Usar IA sin gobernanza es como conducir sin normas de tráfico. Funciona hasta que no funciona."_

---

## Qué es

**AI Governance** es el conjunto de normas, controles, procesos y buenas prácticas para usar IA de forma segura, responsable y alineada con los objetivos de la empresa.

No es frenar la innovación — es ponerle guardarraíles para que no se descarrile.

---

## Marcos principales

### 1. EU AI Act (Reglamento europeo)
Reglamento (UE) 2024/1689, modificado en 2026 por el Reglamento (UE) 2026/1744. Regula la IA según el riesgo. De forma simplificada:

| Nivel | Ejemplo | Qué implica |
|---|---|---|
| **Riesgo inaceptable** | Puntuación social, inferir emociones en el trabajo (salvo motivos médicos o de seguridad) | Prohibido |
| **Alto riesgo** | Selección de personal, solvencia de personas, riesgo y precios en seguros de vida y salud | Requisitos estrictos para proveedores y responsables del despliegue, entre ellos supervisión humana |
| **Riesgo de transparencia** (o limitado) | Chatbots, deepfakes | Informar o marcar, según el caso |
| **Riesgo mínimo** | Filtros de spam | Sin obligaciones específicas para ese nivel |

Los modelos de IA de uso general tienen sus propias obligaciones, y la alfabetización en IA (art. 4) afecta a proveedores y responsables del despliegue de sistemas de IA.

**Se aplica por fases:** primeras prohibiciones y alfabetización desde febrero de 2025, modelos de uso general desde agosto de 2025, aplicación general y transparencia desde agosto de 2026, y alto riesgo en diciembre de 2027 (Anexo III) y agosto de 2028 (Anexo I). El detalle y los matices están en [[ai-act]].

---

### 2. ISO 42001
Estándar internacional para **sistemas de gestión de IA**:
- Evaluación de riesgos
- Documentación de decisiones
- Auditoría continua
- Formación del equipo

### 3. NIST AI Risk Management Framework
Marco del gobierno de EEUU para gestionar riesgos de IA. Complementario al EU AI Act.

---

## Gobernanza práctica en la empresa

| Área | Qué controlar |
|---|---|
| **Datos** | ¿Qué datos se envían al modelo? ¿Son confidenciales? |
| **Modelos** | ¿Qué modelos están aprobados? ¿Dónde se ejecutan? |
| **Acceso** | ¿Quién puede usar IA y para qué? |
| **Output** | ¿Se revisa lo que genera la IA antes de usarse? |
| **Auditoría** | ¿Se registra qué se le pidió a la IA y qué respondió? |
| **Formación** | ¿El equipo sabe usar IA de forma responsable? |

---

## Checklist mínimo para un equipo

- [ ] Política clara de qué se puede y qué no se puede enviar a modelos externos
- [ ] Lista de herramientas de IA aprobadas
- [ ] Proceso de revisión humana para outputs críticos
- [ ] Formación básica sobre riesgos (alucinaciones, prompt injection, confidencialidad)
- [ ] Registro de uso de IA en decisiones importantes

---

## Para esta serie

La gobernanza es el contexto en el que operan todas las herramientas de la serie:
- Las **instrucciones de Copilot** son gobernanza técnica a nivel de proyecto
- Los **guardrails** en el system prompt son gobernanza a nivel de modelo
- El **Wiki LLM** documenta decisiones — parte de la auditoría

---

## Relación con otras piezas

- **[[ai-act]]** — El reglamento europeo y su calendario
- **[[alfabetizacion-ia]]** — La obligación de apoyar la formación del personal
- **[[constitutional-ai]]** — La base técnica del alineamiento que la gobernanza supervisa
- **[[prompt-injection]]** — Un riesgo que la gobernanza debe contemplar
- **[[eval-benchmarking]]** — La evaluación es parte de la gobernanza continua

---

## Referencias

- [Reglamento (UE) 2024/1689 — texto consolidado a 27 de julio de 2026](https://eur-lex.europa.eu/eli/reg/2024/1689/2026-07-27/eng)
- [Reglamento (UE) 2026/1744 — modificación de 2026](https://eur-lex.europa.eu/eli/reg/2026/1744/oj/eng)
- [ISO 42001](https://www.iso.org/standard/81230.html)
- [NIST AI RMF](https://airc.nist.gov/AI_RMF_Playbook)
- Concepto en glosario: [[glosario-ia-nivel-1]] §25
