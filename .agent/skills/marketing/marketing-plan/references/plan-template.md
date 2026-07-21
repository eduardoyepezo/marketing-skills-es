# Plantilla del Plan — La Estructura de 13 Secciones

La plantilla canónica para todo plan de marketing generado por esta skill. Cada sección tiene un propósito, una estructura, y prompts en línea sobre qué redactar.

El plan de Quietude (ver `references/example-quietude.md`) es la implementación de referencia canónica.

---

## Bloque de título

```markdown
# {Cliente} — Plan de Marketing v1

**Preparado por:** {Nombre del Autor / fCMO}
**Para:** {Founders / equipo de liderazgo}
**Fecha:** AAAA-MM-DD
**Estado:** Borrador v1 — para revisión del equipo
```

---

## Sección 1 — Resumen ejecutivo

**Propósito:** Levantar-y-compartir. Un founder debe poder pegar esto en una actualización al board o un email a inversionistas sin editarlo.

**Longitud:** 400–700 palabras. Ajustado.

**Estructura:**
1. **Marco de una oración.** ¿Para qué optimiza este plan? No "más ingresos" — algo específico para este cliente en esta etapa.
2. **Tres grandes apuestas, ordenadas por apalancamiento.** Cada una es un párrafo. Apuesta = una tesis de alta convicción sobre dónde debe enfocar el equipo capital y atención.
3. **Cómo se ve doce meses, de forma plausible.** Lista de bullets. El estado de resultado plausible al final del horizonte del plan. Legible para inversionistas.
4. **Prioridades a 90 días.** Lista numerada. Las seis (más o menos) movidas que se publican en el primer trimestre.

**Notas de voz:**
- Coincide con la voz del cliente
- Directo, legible para el founder, sin lenguaje de marketing
- Usa nombres y números (canales específicos, métricas específicas) — no abstracciones
- Los tradeoffs se nombran explícitamente cuando importan

---

## Sección 2 — Marco estratégico

**Propósito:** Destilar el posicionamiento, el ICP, la lógica del modelo de negocio, y la voz de marca en una sola página que cualquier miembro del equipo o nueva contratación pueda leer para orientarse.

**Longitud:** 800–1500 palabras.

**Estructura:**

### Qué es {Empresa}, en una oración
Extraído del documento de posicionamiento / seed deck / lenguaje del founder.

### La categoría que estamos reclamando
¿La empresa está creando una nueva categoría, redefiniendo una existente, o compitiendo en una categoría definida? Nómbrala. Declara el marco que define la categoría en 2–3 oraciones. Referencia la fuente (palabras del founder, documento de ICP, etc.).

### Para quién somos (ICP, destilado)
Demografía / firmografía + problema declarado vs. problema real + qué están comprando realmente. Ajustado, 4–6 bullets.

### La lógica del modelo de negocio
¿Cómo gana dinero la empresa? ¿Cuál es la teoría de unit economics de adquisición de clientes? ¿Cuál es la tesis del canal de composición (si existe)? Extraído del seed deck / modelo financiero / narrativa del founder.

### Voz de marca (el no-negociable)
Si el cliente tiene reglas de voz documentadas, lístalas. Vocabulario SÍ / NO. Reglas de CTA. Tono. Método central (iniciático, explicativo, narrativo, etc.). Cada otra sección del plan debe respetarlas.

**Notas de voz:**
- Esta sección es la más "extraída de material existente" — no inventes el posicionamiento. Expón lo que ya existe.
- Si el posicionamiento no es claro o se contradice entre materiales, márcalo en las decisiones abiertas de la Sección 13.

---

## Sección 3 — Estado actual

**Propósito:** Anclar el plan en la realidad. ¿Cuál es el equipo, el presupuesto, el trabajo en curso, y el trabajo estancado *hoy*?

**Longitud:** 1000–2000 palabras.

**Estructura:**

### Composición del equipo (superficie de marketing)
Tabla de cada persona con superficie de marketing:

| Persona | Rol | Superficie de marketing |
|---|---|---|

Sé honesto sobre las brechas. Si no hay todavía una contratación dedicada de marketing, nombra cuándo se vuelve necesaria y qué rol (ver `references/team-and-agency-model.md` — la primera contratación debe ser un estratega π-shaped titulado Manager o Lead, no VP/CMO).

### Presupuesto de marketing (actual)
- Adquisición pagada: $X/mes
- Stack de herramientas: lista con costo estimado
- Retainers / fCMO: lista
- Headcount: lista
- CAC blended: $X (debe incluir salarios, costos de contenido, herramientas, retainers — no solo el gasto pagado; ver `references/budget-planning.md` para el cálculo)
- Gasto actual como % del ARR: X% (comparar contra el rango 5–40%)

Declara a qué nivel de etapa de financiamiento mapea (ver `references/funding-stage-unlocks.md`). Implicación: qué debe producir el plan a 90 días *sin* palancas que requieran presupuesto futuro.

### Fase del crecimiento SaaS
Nombra la fase actual: $0–10K ARR / $10K–100K / $100K–1M / $1M–$10M / $10M+. Cada fase tiene su propia restricción vinculante y patrón de crecimiento dominante (ver `references/growth-patterns.md`). La Sección 10 secuencia la movida hacia la siguiente fase.

### Qué ya está hecho (reconocer, luego construir encima)
Tabla:

| Activo | Estado | Apalancamiento de marketing |
|---|---|---|

Aquí es donde se reconocen los lanzamientos pasados, momentos de PR, pilares de contenido, certificaciones, usuarios notables. **Crítico**: no escribas un plan que ignore trabajo del que el equipo está orgulloso.

### Qué está en curso (borrado pero no publicado)
Tabla:

| Elemento | Estado | Bloqueador |
|---|---|---|

Sé honesto sobre los bloqueadores. Donde el bloqueador sea "no hay tiempo" o "no hay decisión", eso va a las decisiones abiertas de la Sección 13.

### Qué está estancado (y necesita desatorarse este trimestre)
Tabla:

| Problema | Costo de la inacción | Acción |
|---|---|---|

Las cosas estancadas son los lugares con más apalancamiento positivo para enfocar las primeras semanas del plan a 90 días.

### Captura de la rúbrica de auditoría
Captura puntuada de 17 secciones usando la rúbrica embebida de estado actual. Ver `references/current-state-rubric.md` para la rúbrica completa y las guías de puntuación.

Si existe una auditoría previa puntuada, pega esos puntajes. De lo contrario puntúa a partir del material disponible y anota "puntuado a partir de material" bajo el encabezado.

| # | Sección | Puntaje | Nota |
|---|---|---|---|
| 1 | Posicionamiento | 0–5 | |
| 2 | Investigación de clientes | 0–5 | |
| ... | ... | ... | ... |
| 17 | Internacionalización | 0–5 | |

**Total: X / 85 (Y%).** Anota la *forma* de fortaleza y debilidad — esa forma es la brecha que cierra el resto del plan.

**Notas de voz:**
- Honesto > pulido. Si las métricas del cliente son malas, nómbralas. Los founders leen más allá del maquillaje.

---

## Sección 4 — Adquisición

**Propósito:** Responder "¿cómo se vuelven conscientes de nosotros los desconocidos?" Mapea cada canal: estado actual, movidas planeadas, omitidos (con razón).

**Longitud:** 1000–1800 palabras.

**Estructura:**

### Estado actual
Breve. Qué está funcionando hoy, qué no, qué muestran los datos sobre la mezcla de canales.

### El plan
"Movidas" numeradas. Cada movida es un párrafo (3–6 oraciones) describiendo el canal, la tesis, y el trabajo específico. Movidas comunes:

- **Movida 1 — SEO (y contenido)** — Referencia el plan de SEO si existe (`seo/plan.md`). De lo contrario: investigación de keywords, estructura de pilar/spoke, cadencia de contenido.
- **Movida 2 — Optimización de App Store / Play Store** (para apps de consumo) — Reescritura del listado, pruebas de capturas de pantalla, targeting de keywords ASO.
- **Movida 3 — Canales liderados por el founder** — LinkedIn para B2B/SaaS, Twitter/X para tech, Instagram para consumo. Cadencia, temas, owners.
- **Movida 4 — Amplificación de PR** — ¿Cuál es el ancla de credibilidad? Cómo amplificarla.
- **Movida 5 — Eventos (si aplica)** — Eventos en vivo, conferencias, webinars. Rol de Adquisición vs. activación.
- **Movida 6 — Superficie de hardware / comercio (si aplica)** — Storefront de Shopify, Amazon, retail.
- **Movida 7 — Soporte de ventas B2B** — Casos de estudio, páginas de partners, contenido específico por vertical.
- **Movida 8 — Capa pagada (cuando se desbloquea presupuesto)** — Apple Search Ads, Meta, LinkedIn, Google. Retenida hasta la etapa de financiamiento especificada.

### Movidas de adquisición a 90 días
Desglose semana por semana de los envíos del primer trimestre.

### Perspectiva de adquisición a 12 meses
Estado de resultado trimestre por trimestre (Q1 / Q2 / Q3 / Q4).

### Skills + herramientas
- **Skills:** lista las skills relevantes del repo de marketing-skills (`seo-audit`, `ai-seo`, `paid-ads`, `social`, `competitor-alternatives`, etc.)
- **MCPs / APIs:** lista las conexiones (API de Ahrefs, GA4 MCP, Typefully MCP, Stripe MCP para matemáticas de LTV, etc.)

---

## Sección 5 — Activación

**Propósito:** Responder "una vez que alguien nos prueba, ¿tiene una experiencia que convierte?"

**Longitud:** 800–1500 palabras.

**Estructura:** Igual que Adquisición (Estado actual / El plan / 90 días / 12 meses / Skills + herramientas).

**Movidas comunes:**
- Correcciones de base (signup roto, gates de onboarding rotos, etc.)
- Pruebas / reconstrucción de onboarding (a menudo la movida más apalancada en esta etapa)
- Reescritura del listado de App Store (cruza referencia con Adquisición)
- Orden de envío del Lifecycle Flow (cuándo enviar emails de onboarding vs. retener hasta que se estabilice el producto)
- Revisión de paywall + pricing (a menudo Activación × Ingresos)

### Skills + herramientas
`onboarding-cro`, `signup-flow-cro`, `paywall-upgrade-cro`, `copywriting`, `marketing-website-design`, `ab-test-setup`, etc.

---

## Sección 6 — Retención

**Propósito:** Responder "una vez que alguien convierte, ¿se queda y profundiza?"

**Longitud:** 800–1500 palabras.

**Estructura:** Igual que arriba.

**Movidas comunes:**
- Flujos de email de lifecycle (post-compra, usuario inactivo, win-back)
- Centros de suscripción / preferencias
- Reconciliación de churn (a menudo las definiciones de métrica no coinciden entre superficies)
- Rutas de activación hardware → software (para negocios híbridos)
- Pruebas de default de plan anual (cruza referencia con Ingresos)

### Skills + herramientas
`email-sequence`, `churn-prevention`, `copywriting`, `paywall-upgrade-cro`, etc.

---

## Sección 7 — Referidos

**Propósito:** Responder "¿los usuarios retenidos traen más usuarios, y a qué costo?"

**Longitud:** 500–1200 palabras.

**Estructura:** Igual que arriba.

**Movidas comunes:**
- Lanzamiento de programa de ambassador / afiliado (si existe interés inbound, lidera con él)
- Momentos de compartir-después-del-valor integrados en el producto
- Amplificación del founder (el founder como referente cero)
- Red de expertos / Guides / hosts certificados a largo plazo
- Flujos de regalo (para consumo / hardware)

### Skills + herramientas
`referral-program`, `social`, `email-sequence` (para lifecycle de ambassador), `copywriting`, etc.

---

## Sección 8 — Ingresos

**Propósito:** Responder "¿qué cobramos, quién paga, y cómo compone?"

**Longitud:** 500–1200 palabras.

**Estructura:** Igual que arriba.

**Movidas comunes:**
- Auditoría de pricing (¿qué se cobra realmente hoy vs. lo listado?)
- Pruebas de default de plan anual
- Formalización del bundling hardware → software (para negocios híbridos)
- Optimización de la página de storefront / comercio
- Casos de estudio B2B + material de ventas
- Pools de valor a largo plazo (licenciamiento de datos, expansión enterprise) — marcados, no ejecutados en el plan de 12 meses

### Unit economics
Tabla requerida:

| Métrica | Valor | Nota |
|---|---|---|
| ARPC (ingreso mensual promedio por cliente) | $X | Extraído de Stripe / facturación |
| CAC blended | $X | Incluye todos los costos de marketing, no solo el pago |
| Tasa de retención anual | X% | 1 − churn anual |
| LTV (aproximado) | $X | ARPC × 12 / churn anual |
| LTV / CAC | X | Benchmark de salud: > 3 |

Estos alimentan las matemáticas de presupuesto en la Sección 10. Si alguno de estos es desconocido, márcalo en la Sección 13 como la principal decisión abierta.

### Skills + herramientas
`pricing-strategy`, `paywall-upgrade-cro`, `sales-enablement`, `revops`, `ab-test-setup`, etc.

---

## Sección 9 — Roadmap a 90 días

**Propósito:** La capa de ejecución táctica. Cada movida se publica dentro de una semana nombrada, con un owner.

**Longitud:** Tablas, no prosa. Debe caber en una página impresa si es posible.

**Estructura:** Cuatro sprints de 2–3 semanas:

### Semanas 1–2 — Desbloquear
Cambios de mayor confianza y menor costo. Quitar cosas que están rotas.

| Movida | Etapa | Owner |
|---|---|---|

### Semanas 3–4 — Fundación
Trabajo pilar/fundacional. Consolidación de dominio. Primer contenido. Primeros flujos publicándose. Primeras pruebas en vivo.

### Semanas 5–8 — Velocidad
Comienza el trabajo de composición. Cadencia de contenido. Pruebas repetidas. Escalamiento de canal.

### Semanas 9–12 — Composición
Movidas de segundo orden. Tácticas en capas. Preparación de la revisión a 90 días.

---

## Sección 10 — Perspectiva a 12 meses

**Propósito:** Hitos trimestrales con desbloqueos de capacidad por etapa de financiamiento nombrados explícitamente, anclados contra un patrón de crecimiento defendible.

**Longitud:** Cuatro subsecciones, una por trimestre. ~250–400 palabras cada una. Más un párrafo corto de encuadre al inicio nombrando el método de presupuesto y el patrón de crecimiento.

### Encuadre (inicio de la Sección 10)

Declara explícitamente:
- **Método de presupuesto usado.** Método 1 (Basado en Ingresos 5–40% del ARR) o Método 2 (Fórmula Basada en la Meta). Ver `references/budget-planning.md`. Muestra las matemáticas.
- **Presupuesto anual total** + el buffer experimental (+10–20%).
- **Meta resultante de ARR de fin de año.** Forecast honesto, no una garantía — ver la verificación de realidad del forecasting en `references/measurement-framework.md`.
- **Patrón de crecimiento esperado.** Lineal ($X de MRR predecible agregado por mes), función escalonada (meseta entre saltos deliberados), o curvas en S en capas. Para Series A+ respaldado por VC, ancla contra 3-3-2-2-2 y muestra si el plan la iguala o elige explícitamente una trayectoria diferente. Ver `references/growth-patterns.md`.

### Estructura (por trimestre)

#### Q{N} — Meses {X}–{Y}

**Estado de financiamiento:** {nivel} según `funding-stage-unlocks.md`

**Enfoque:** Tema de enfoque en una oración para el trimestre.

**Resultados al final de Q{N}:**
- Lista de resultados con bullets (5–8 elementos)

**Metas de KPI:** 3–5 metas numéricas específicas.

**Posición en la curva en S de Canal/Producto/Mercado:** Qué curvas están creciendo, cuáles se están estancando, cuál es la siguiente que se está preparando para este trimestre (ver `growth-patterns.md` — principio de superposición).

---

## Sección 11 — Stack de operaciones de marketing

**Propósito:** El diferenciador fCMO. Muestra cómo un equipo pequeño + herramientas agénticas ejecuta el plan sin contratar en cada canal.

**Longitud:** Tablas + explicación breve.

**Estructura:**

### La tesis
1–2 párrafos explicando el principio: equipo pequeño + librería de marketing-skills + integraciones MCP = salida de un equipo más grande.

### Skills mapeadas a etapas AARRR

| Etapa | Skills primarias | Skills de apoyo |
|---|---|---|
| Adquisición | (lista) | (lista) |
| Activación | (lista) | (lista) |
| Retención | (lista) | (lista) |
| Referidos | (lista) | (lista) |
| Ingresos | (lista) | (lista) |
| Transversal | (lista) | (lista) |

### MCPs / APIs mapeadas a etapas

| Etapa | Conexiones existentes | Capa de herramientas del fCMO |
|---|---|---|

### Un ejemplo concreto
Elige un momento operativo que pruebe la tesis del stack (p. ej., "El MCP de Customer.io permitió al founder no técnico redactar un flujo en vivo en la llamada de kickoff"). Ancla la afirmación abstracta en un evento específico.

### Desbloqueos de capacidad por etapa de financiamiento

| Etapa | Headcount | Herramientas | Canales activos |
|---|---|---|---|
| (actual) | (lista) | (lista) | (lista) |
| (siguiente ronda) | (delta) | (delta) | (delta) |
| ... | ... | ... | ... |

### Modelo de equipo y agencia (RACI)

Aplica el principio de `references/team-and-agency-model.md`: estrategia interna, ejecución a menudo externalizada.

| Función | Owned por (rol estratégico interno) | Ejecutado por (IC / contratista / agencia) |
|---|---|---|
| Growth marketing (motor de demanda) | | |
| Product marketing (motor de historia) | | |
| Content marketing (motor de confianza) | | |

Si al equipo le falta un owner estratégico para alguna de estas funciones, la primera movida a 90 días (Sección 9) debe ser la contratación — título Manager o Lead, π-shaped si es posible, no VP/CMO.

Si la capacidad de ejecución es la brecha, nombra al contratista o a la agencia especializada pequeña en la celda correcta en lugar del IC existente del equipo.

Extrae de `references/funding-stage-unlocks.md`.

---

## Sección 12 — Banco táctico de ideas

**Propósito:** Cruzar las 139 ideas de la skill `marketing-ideas` contra etapas AARRR, con estado específico del cliente.

**Longitud:** Larga — las tablas pueden fácilmente sumar 150+ filas.

**Estructura:**

### Párrafo de introducción
Explica la referencia cruzada: las Secciones 4–8 prescriben lo que *se está haciendo*. Esta sección mapea lo que *es posible*.

### Leyenda de estado

- **Ahora (Q1)** — ya está en el plan a 90 días
- **Q2** — capa post-fundación
- **Q3+** — expansión post-cierre-de-seed o post-GA
- **Q4+** — juego largo
- **Omitir / fuera de marca** — incompatible con la voz de marca o el modelo de negocio

### 12.1 Ideas de Adquisición

Por estado (Ahora / Q2 / Q3+ / Q4+ / Omitir), tablas de ideas de marketing relevantes por número.

| # | Idea | Nota del cliente |
|---|---|---|

### 12.2 Ideas de Activación
### 12.3 Ideas de Retención
### 12.4 Ideas de Referidos
### 12.5 Ideas de Ingresos
### 12.6 Ideas transversales / de fundación de marca

### Resumen del banco de ideas
- Conteos por etapa AARRR
- Conteos omitidos, con justificación
- Qué cubre el plan como % de la superficie táctica disponible
- Qué demuestra esto sobre la etapa del cliente

Usa `references/idea-cross-reference.md` como el mapeo fuente de verdad. Aplica filtros específicos del cliente durante la redacción (las reglas de voz de marca descartan algunas; la etapa de financiamiento cambia el timing de otras).

---

## Sección 13 — Medición, RACI, decisiones abiertas, apéndice

**Propósito:** Cierre operativo. Define cómo se mide el plan, quién posee qué, qué sigue siendo TBD, y dónde encontrar los documentos más profundos.

**Estructura:**

### Medición — las métricas que importan

**Métrica norte (propuesta):** Una métrica que capture la tesis del modelo de negocio. Para Quietude era LTV-blended-a-CAC-blended; para un B2B SaaS podría ser NRR × NPS; para un marketplace, take-rate × usuarios transaccionando mensualmente. Hazla específica a la empresa.

**Indicadores líderes por etapa AARRR:** Tabla:

| Etapa | Indicadores líderes |
|---|---|
| Adquisición | ... |
| Activación | ... |
| Retención | ... |
| Referidos | ... |
| Ingresos | ... |

**Cadencia de revisión:**
- Semanal: quién sincroniza con quién, sobre qué
- Mensual: quién revisa qué
- Trimestral: disparador de recalibración del plan

### RACI

| Dominio | Responsable | Aprobador | Consultado | Informado |
|---|---|---|---|---|

Dominios comunes: plan estratégico, voz de marca, implementación de app/producto, lifecycle, contenido de SEO, App Store, social liderado por el founder, eventos, ambassadors, ventas B2B, pricing, narrativa de inversionistas, futuras contrataciones.

### Decisiones abiertas que bloquean el plan

Ordenadas por impacto. Cada una es: nombre + impacto + qué está bloqueado.

1. (mayor impacto) ...
2. ...
8. (menor impacto) ...

### Apéndice — enlaces de profundización

**Publicado en este repo / compartido con el equipo:** {rutas relativas a documentos en el repo compartido}

**Contexto estratégico escrito por el founder** (base de conocimiento interna): {nombres de documentos a los que el equipo tiene acceso fuera del repo del plan}

**Borradores de trabajo del fCMO** (aún no publicados): {nombres + cómo acceder desde el autor}

---

## Línea de cierre

```markdown
*{Cliente} Plan de Marketing v1. Preparado por {Autor}, {Fecha}. Para revisión y discusión del equipo.*
```

---

## Heurísticas por sección para "¿está terminada esta sección?"

- **Sección 1** — Un lector no-Quietude podría entender la tesis de crecimiento de la empresa solo a partir de esto.
- **Sección 2** — Las reglas de voz de marca son lo suficientemente explícitas como para que cualquier copywriter nuevo pueda seguirlas.
- **Sección 3** — Todos los elementos "en curso" tienen un owner y un bloqueador nombrados.
- **Secciones 4–8** — Cada movida nombra una skill (`alguna-skill`) y una herramienta (Customer.io MCP / Stripe MCP / Ahrefs / etc.).
- **Sección 9** — Cada fila tiene un owner.
- **Sección 10** — Cada trimestre nombra explícitamente la etapa de financiamiento.
- **Sección 11** — Al menos un ejemplo operativo concreto prueba la tesis del stack.
- **Sección 12** — La lista de omitidos tiene justificación, no solo ausencia.
- **Sección 13** — La métrica norte es específica de esta empresa (no un genérico "crecimiento de ARR").
