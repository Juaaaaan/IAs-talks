---
type: guion
title: "Charla 20 — La otra correa del arnés: el ejecutor abierto"
description: "Charla de teoría (sin demo en directo) sobre la capa del ejecutor del arnés: ejecutor cerrado (Claude Code) vs abierto (OpenCode). Mensaje de criterio y gobernanza, no de adopción."
tags: [charla, guion, opencode, ejecutor, arnes, gobernanza, open-source]
related:
  - "[[guion-charla-16]]"
  - "[[guion-charla-19]]"
  - "[[opencode]]"
  - "[[claude-code]]"
  - "[[openspec]]"
  - "[[el-arnes]]"
charla: 20
estado: borrador
timestamp: 2026-09-14
---

# Guión Charla 20 — La otra correa del arnés: el ejecutor abierto

### 16 de septiembre de 2026

> Charla de teoría / modelos mentales. Sin demo en directo. El objetivo no es que nadie se instale nada, sino que todos entiendan una decisión que su empresa ya está tomando: **quién controla la IA que usamos y dónde viven nuestros datos.**

---

## Estructura de tiempos

| Bloque | Contenido | Tiempo |
|--------|-----------|--------|
| 1. Apertura | Callback a la 16 + mapa del arnés | 4 min |
| 2. Las dos correas | Especificar ≠ ejecutar | 4 min |
| 3. El ejecutor cerrado | Claude Code: potente pero atado | 4 min |
| 4. El giro | El ejecutor también puede ser abierto: OpenCode | 7 min |
| 5. ¿Y a mí qué? | Por qué aparece en soluciones internas | 7 min |
| 6. Escenario concreto | Una casa como la nuestra | 5 min |
| 7. Visual guiado | *(pendiente de decidir — placeholder)* | 6 min |
| 8. Equilibrio | Abierto vs cerrado: las 3 preguntas | 5 min |
| 9. Cierre | Pregunta para todos + círculo con la 19 + puente | 4 min |

**Total ≈ 46 min** (preguntas aparte).

---

## Bloque 1 — Apertura + mapa del arnés — 4 min

Abrir **en frío** con el gancho honesto (afirmativo: la herramienta ya está entrando en la empresa) y girar al tema. Después, 60 seg de mapa del arnés (dónde estamos, qué correa toca hoy).

**Gancho honesto (apertura en frío):**

> *"Empiezo con un dato que quizá os sorprenda: la herramienta de la que os voy a hablar hoy ya está entrando en la empresa. Hay compañeros aquí, ahora mismo, usándola. Yo también puedo instalarla en el portátil de trabajo y usarla — lo he comprobado."*
>
> *"O sea, esto no es teoría ni futurismo: ya ha cruzado la puerta. Y cuando una herramienta de IA entra en casa, hay dos preguntas que conviene hacerse desde el primer día — y son el tema de hoy: quién controla esa IA, y dónde viven nuestros datos."*

**Puente al arnés:**

> *"Llevamos toda la serie montando un arnés para la IA: documentos que le dicen qué construir, comportamiento persistente, acceso a nuestras herramientas, memoria. Riendas, para que el caballo no se desboque."*
>
> *"En la Charla 16 vimos una de esas correas de cerca: la de especificar — el spec a mano frente a herramientas como OpenSpec, decir bien QUÉ queremos antes de que la IA toque nada. Y para ejecutar ese trabajo, usamos Claude Code."*
>
> *"Hoy miramos el otro extremo del arnés. No el QUÉ, sino el QUIÉN lo ejecuta. Y una pregunta muy sencilla:"*

**Frase que debe quedar:**
> *"En la 16 especificamos y dejamos que Claude Code lo ejecutara. Hoy: ¿y si el ejecutor no te atara a nadie?"*

---

## Bloque 2 — Las dos correas del arnés — 4 min

Separar dos piezas que se suelen mezclar.

> *"Cuando hablamos de que 'la IA programa', juntamos dos cosas que en realidad son distintas."*
>
> *"Una es **especificar**: decidir y describir qué queremos. Eso ya lo vimos. Es la correa del QUÉ."*
>
> *"La otra es **ejecutar**: el agente que de verdad lee el código, lo entiende y hace los cambios. Ese es el ejecutor. La correa del QUIÉN lo hace."*
>
> *"Hoy va toda de la segunda correa. Y lo interesante no es tanto qué hace el ejecutor, sino de quién depende."*

En pantalla (esquema simple):

```
QUÉ (especificar)    →   OpenSpec, Kiro, Spec Kit   ← visto en la 16
QUIÉN ejecuta        →   Claude Code / OpenCode      ← hoy
```

**Frase que debe quedar:**
> *"Especificar y ejecutar no son lo mismo. Son dos correas distintas."*

---

## Bloque 3 — El ejecutor cerrado: Claude Code — 4 min

Explicar qué hace un ejecutor, en cristiano, y sembrar la tensión. Sin atacar a Claude Code: es un trade-off, no un defecto.

> *"Un ejecutor como Claude Code es una maravilla. Le das una tarea, mira todo el proyecto, razona y hace los cambios él solo. Es de lo mejor que hay."*
>
> *"Pero fijaos en tres cosas, sin juzgarlas todavía. Uno: funciona con un único proveedor, el suyo. Dos: es cerrado, no puedes ver por dentro cómo está hecho. Y tres: para trabajar, vuestro código y vuestro contexto salen a un servidor de un tercero."*
>
> *"No estoy diciendo que eso sea malo. Para muchísimos casos es perfecto y no querrías otra cosa. Solo quiero que veáis que ahí hay una decisión tomada — y que la ha tomado el proveedor, no vosotros."*

**Guiño a lo que ya usáis (ancla de familiaridad):**

> *"Y esto no os pilla tan lejos como parece. Pensad en el Copilot de Office — el de Word, Teams, Excel — que muchos usáis a diario. Está en este mismo lado, el cerrado: vuestros datos pasan por Microsoft y no hay caja que podáis abrir ni traer a casa."*
>
> *"Y tiene un primo, GitHub Copilot, el de programar: ese sí es un ejecutor como Claude Code. Os dejo con un detalle simpático — GitHub Copilot incluso os deja elegir el modelo, Claude, GPT o Gemini. Suena a libertad, ¿verdad? Pero ojo: sigue siendo una caja cerrada y alojada fuera."*

**Reseñable:**
> *"Elegir el motor dentro de la caja no es lo mismo que controlar la caja."*

**Frase que debe quedar:**
> *"No es que sea malo. Es que decides tú, o decide el proveedor por ti."*

---

## Bloque 4 — El giro: el ejecutor también puede ser abierto (OpenCode) — 7 min

Presentar OpenCode por las propiedades que importan, no como catálogo de features.

> *"Ahora imaginad el mismo tipo de herramienta — un agente que ejecuta, que lee vuestro código y hace los cambios — pero construido al revés en tres cosas. Se llama OpenCode."*

Ir una a una, despacio:

> *"**Uno: es abierto.** El código está a la vista, cualquiera lo puede auditar. No es una caja negra."*
>
> *"**Dos: no te casa con ningún proveedor.** Le enchufas el motor que quieras — el de una empresa, el de otra, o incluso un modelo que corra en vuestra propia máquina o en un servidor interno. Tú eliges el motor, no la herramienta por ti."*
>
> *"**Tres: los datos no tienen por qué salir de casa.** Si el motor es interno o local, vuestro código nunca viaja a un tercero. Puede funcionar hasta en entornos aislados, sin internet."*

> *"Y no es un experimento de garaje: es una de las herramientas de su tipo más usadas del mundo. Vive en la terminal, pero también tiene app de escritorio y extensión para el editor, así que no es solo para gente muy técnica."*

**Reseñable — pausa aquí:**
> *"El mismo trabajo que hace el ejecutor cerrado. Pero el motor lo eliges tú, y tus datos se quedan en casa."*

> ⚠️ *Antes del miércoles: verificar cifras que quiera citar (nº de proveedores soportados, popularidad). Para la charla basta con "decenas de proveedores, incluso modelos locales" — no colgarse de un número exacto.*

---

## Bloque 5 — ¿Y a mí qué? Por qué aparece en soluciones internas — 7 min

El corazón accesible de la charla. Traducir a negocio. **Ojo al reencuadre: el trabajo de la audiencia NO es adoptarlo — es entender la decisión.**

> *"Vale, Juan, muy bonito, pero yo no voy a abrir una terminal en mi vida. ¿Por qué me cuentas esto?"*
>
> *"Porque esta decisión — ejecutor abierto o cerrado — se está tomando en empresas como la nuestra ahora mismo. Y afecta a todos, toquéis código o no."*

Tres razones por las que una empresa elige lo abierto:

> *"**Uno: no quedar atrapada.** Ni a un proveedor ni a su precio. Si mañana suben la tarifa o cambian las reglas, con una herramienta abierta cambias de motor y sigues. Con una cerrada, estás donde te pongan."*
>
> *"**Dos: gobernar los datos.** Esto lo hemos hablado mucho: RGPD, información sensible, datos de clientes. Con un ejecutor que corre contra modelos internos, esa información no sale de casa. Para un banco o una aseguradora, eso no es un capricho: es la diferencia entre poder usarlo o no."*
>
> *"**Tres: correr contra lo suyo.** Muchas casas ya tienen sus propios modelos o acuerdos. Una herramienta abierta se enchufa a eso; una cerrada te obliga a lo suyo."*

> *"Por eso lo veis aparecer en soluciones internas. No porque sea 'más chulo', sino porque deja el control del lado de la empresa."*

**Frase que debe quedar:**
> *"La factura y los datos dejan de ser rehenes."*

---

## Bloque 6 — Escenario concreto — 5 min

Aterrizar en un caso cercano y genérico. **Sin nombrar ninguna solución interna real.**

> *"Pongámoslo con un caso que os suena. Una aseguradora. Tiene datos de pólizas, de clientes, historiales. Quiere que sus desarrolladores usen IA para ir más rápido — pero no puede permitir que ese código y esos datos salgan a un servidor de fuera. Legal no lo firma. Y con razón."*
>
> *"Con un ejecutor cerrado, la conversación se acaba ahí: 'no podemos, los datos salen'. Con un ejecutor abierto conectado a un modelo interno, la conversación cambia: 'sí podemos, y no sale nada de casa'."*
>
> *"Misma necesidad, mismo trabajo. Lo único que cambia es quién controla el motor. Y eso lo cambia todo."*

**Frase que debe quedar:**
> *"Esto no es teoría de garaje: ya está pasando en casas como la nuestra."*

> ⚠️ *Si el Bloque 7 (visual) se queda corto de tiempo o de contenido, este escenario puede estirarse 1-2 min con un segundo ejemplo (p. ej. sanidad / datos de pacientes).*

---

## Bloque 7 — Visual guiado — 6 min

> 🚧 **PLACEHOLDER — pendiente de decisión de Juan.**
>
> Este bloque está diseñado para **sobrevivir con cero herramienta en directo** (Juan prefiere teoría y no estar pendiente de una demo frágil en vivo). No depende de nada montado.
>
> Opciones sobre la mesa (elegir una cuando Juan lo decida):
> - **A —** Recorrido por la web `opencode.ai` + un par de capturas de la interfaz (terminal/escritorio) mientras se comenta. Cero riesgo, cero instalación.
> - **B —** Walkthrough de OpenCode ya montado en tu equipo (instalación confirmada: ya la usan compañeros): enseñar cómo se elige el proveedor y el modo Plan/Build. Pausa larga en el momento *"elijo el motor"* — ese es el reseñable.
> - **C —** Enseñarlo desde tu propio trasteo previo (capturas / grabación), sin depender de que arranque nada en vivo.
>
> **Reseñable objetivo del bloque, sea cual sea la opción:** el instante en que se elige el proveedor/modelo. Ahí es donde la audiencia *ve* de qué hemos estado hablando.
>
> *Cuando decidas A/B/C, relleno este bloque con el paso a paso y las frases.*

---

## Bloque 8 — Equilibrio: abierto vs cerrado — 5 min

Evitar la guerra santa. Dar un modelo mental de decisión que aplica **aunque nadie del público vaya a elegir nunca** — porque enseña a hacer las preguntas correctas.

> *"No os vayáis con la idea de que abierto es bueno y cerrado es malo. No va de eso. Cada uno tiene su momento."*
>
> *"Cerrado: menos fricción, soporte, todo integrado, funciona de fábrica. Abierto: control, gobernanza, y flexibilidad — pero requiere manos y decisiones."*

En pantalla — **las tres preguntas que tu empresa debería hacerse:**

```
1. ¿Qué necesito gobernar? (datos, cumplimiento, auditoría)
2. ¿Cuántas manos tengo? (equipo para montar y mantener)
3. ¿Qué datos toca? (públicos, internos, sensibles)
```

> *"Aunque nunca vayáis a instalar nada, si sabéis estas tres preguntas, entendéis la decisión que alguien está tomando por vosotros. Y podéis pedir cuentas."*

**Frase que debe quedar:**
> *"La pregunta no es cuál es mejor, sino qué necesitas gobernar."*

---

## Bloque 9 — Cierre + puente — 4 min

Recolocar en el arnés, dejar la pregunta que se lleva **todo el mundo**, cerrar el círculo con la 19 y presentar OpenCode como algo que ya asoma en la empresa.

> *"Recolocad esto en el arnés: hoy cerramos la correa del ejecutor. Y os la lleváis con una pregunta, no con una herramienta:"*

**Frase — dejar fija en pantalla:**
> *"¿Quién controla la IA que usa mi empresa, y dónde viven mis datos?"*

**Cerrar el círculo con la Charla 19:**

> *"Y dejad que cierre el círculo. ¿Os acordáis de la 19? Montamos un equipo de agentes que analizaba pliegos: un jefe, tres especialistas, hasta escribía en un Excel. Una maravilla. Pero miradlo hoy con otros ojos: lo montamos entero dentro de una caja cerrada. Plataforma, modelo, datos… todo en casa de otro."*
>
> *"Para empezar y para probar, perfecto. Pero cuando esto va en serio —llevar un agente al día a día, con vuestros permisos, vuestros datos, vuestras reglas— la forma de construir y de ejecutar cambia. Y se mueve justo hacia lo de hoy: herramientas donde el motor y los datos son vuestros."*

**El puente (por qué ahora — enlaza con la apertura):**

> *"Y os enlazo con lo del principio. ¿Os acordáis de que os dije que ya hay compañeros usándola? Por eso os la traigo: no por curiosidad, sino porque ya está aquí. Quiero que la conozcáis, aunque no la toquéis, por si os llega la oportunidad de trabajar con ella. Mejor que os pille sabiendo lo que es."*
>
> *"Y quién sabe: igual la semana que viene, con más tiempo, dejamos de hablar y montamos algo de verdad."*

**Frase final:**
> *"Hoy no os lleváis una herramienta. Os lleváis el criterio para entender la que viene."*

---

## Checklist antes del miércoles

### Cuanto antes
- [ ] (Instalación: confirmado que se puede — ya la usan compañeros.) Si vas con el Bloque 7 opción B, tenerla montada y probada antes del miércoles
- [ ] Decidir Bloque 7: opción A (web), B (montado) o C (trasteo previo)

### Lunes / Martes
- [ ] Verificar cifras a citar de OpenCode (proveedores, popularidad) — o dejarlo en "decenas / de las más usadas"
- [ ] Preparar el esquema visual de las dos correas (Bloque 2)
- [ ] Preparar el esquema de las 3 preguntas (Bloque 8)
- [ ] Rellenar el Bloque 7 según la opción elegida
- [ ] Ensayo cronometrado (vigilar que la teoría no se estire de más)

### El día de la charla
- [ ] Esquemas (dos correas / 3 preguntas) listos para proyectar
- [ ] Material del Bloque 7 abierto y listo (según opción)
- [ ] Frase final preparada para dejar fija en pantalla

---

## Decisiones abiertas (para cerrar contigo)

1. **Bloque 7 (visual):** A / B / C — me dices y lo relleno.
2. **Gancho honesto de apertura:** ✅ cerrado — apertura en frío afirmativa: la herramienta ya está entrando en la empresa, hay compañeros usándola y tú también puedes usarla.
3. **Puente final:** ✅ cerrado — cierre en círculo con la Charla 19 (caja cerrada) + OpenCode como herramienta que ya asoma en la empresa ("conocedla por si nos toca") + tease de "montamos algo la semana que viene".
