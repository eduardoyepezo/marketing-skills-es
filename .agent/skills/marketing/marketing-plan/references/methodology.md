# Metodología — Cómo se Elabora un Plan de Marketing

El flujo de trabajo de tres fases que produce un plan de marketing integral. SKILL.md es la capa de orquestación; esto es el detalle operativo.

## Fase 1 — INIT (investigación e intake)

**Meta:** Entrar a la Fase 2 con suficiente contexto para redactar cada sección sin adivinar.

### Paso 1.1 — Configurar la carpeta del plan

Estructura canónica de archivos para todo plan:

```
~/marketing-plans/{client-slug}/
├── materials/         # Archivos provistos por el cliente (decks, salida de auditoría, doc de voz de marca, etc.)
├── research.md        # Escrito en la Fase 1 (INIT)
├── progress.md        # Máquina de estados — ver Paso 1.1.1 para el esquema
├── sections/
│   ├── 01.md          # Resumen ejecutivo (escrito al final, ordenado primero)
│   ├── 02.md          # Marco estratégico
│   ├── ...
│   └── 13.md          # Medición, RACI, decisiones abiertas, apéndice
└── final_plan.md      # Entregable compilado (salida de la Fase 3)
```

### Paso 1.1.1 — Esquema de estado de `progress.md`

Todo plan rastrea un único archivo `progress.md` en la raíz del plan. Es la fuente de verdad para la reanudación. Esquema:

```markdown
# {Cliente} — Progreso del Plan de Marketing

phase: init | review | finalize | finalized
current_section: <número, solo relevante durante la fase de review>
plan_version: v1
last_updated: AAAA-MM-DD HH:MM

## Secciones completadas
- [ ] 2. Marco estratégico
- [ ] 3. Estado actual
- [ ] 4. Adquisición
- [ ] 5. Activación
- [ ] 6. Retención
- [ ] 7. Referidos
- [ ] 8. Ingresos
- [ ] 9. Roadmap a 90 días
- [ ] 10. Perspectiva a 12 meses
- [ ] 11. Stack de operaciones de marketing
- [ ] 12. Banco táctico de ideas
- [ ] 13. Medición, RACI, decisiones abiertas, apéndice
- [ ] 1. Resumen ejecutivo (sintetizado al final)

## Artefactos aprobados
sections/02.md, sections/03.md, ... (listar a medida que se escriben)

## Notas
<cualquier decisión abierta, bloqueador, o contexto fuera de banda que no esté en research.md>
```

### Paso 1.1.2 — Árbol de decisión de reanudación

En cada invocación, revisa el estado en este orden:

1. **No existe la carpeta `{client-slug}/`** → plan nuevo. Crea la carpeta + `materials/` + `sections/` vacío. Comienza INIT (Paso 1.2).
2. **La carpeta existe, no hay `research.md`** → INIT fue interrumpido. Reanuda desde el Paso 1.2.
3. **Existe `research.md`, no hay `progress.md`** → INIT terminado, REVIEW no ha empezado. Crea `progress.md`, comienza REVIEW desde la Sección 2.
4. **Existe `progress.md`, `phase: review`** → REVIEW en progreso. Reanuda desde `current_section` (o la primera casilla sin marcar).
5. **Existe `progress.md`, `phase: finalize`** → FINALIZE fue interrumpido. Vuelve a correr la Fase 3.
6. **Existe `progress.md`, `phase: finalized`** → el plan está terminado. **No sobrescribir silenciosamente.** Pregunta al usuario: *"Este plan está finalizado (v{N}). ¿Quieres (a) revisarlo como v{N+1}, (b) empezar un plan nuevo en una carpeta nueva, o (c) reabrir una sección específica?"*

Actualiza `phase` y `last_updated` cada vez que cambie el estado.

### Paso 1.2 — Leer el material existente

Si `materials/` tiene archivos, léelos todos. Materiales comunes:
- Pitch deck / deck de inversionistas
- Documento de posicionamiento / documento de voz de marca
- Investigación de clientes / documento de ICP
- Captura de métricas de App Store / analítica
- Inventario de emails de lifecycle
- Salida de auditoría previa (cualquier evaluación de estado actual puntuada que el equipo haya corrido)
- Investigación de SEO (`seo/plan.md`, `seo/keyword-shortlist.md`)
- Transcripción de la llamada de kickoff
- Notas asíncronas / de Slack del founder

Lee todo. Captura hechos clave en `research.md` a medida que avanzas.

### Paso 1.3 — Extraer datos en vivo donde estén conectados

Si hay MCPs/APIs conectados para este cliente, extrae:

- **Ahrefs** → domain rating, keywords orgánicas, backlinks, páginas top, dominios de referencia (según la skill `/seo-audit`)
- **GA4 MCP** → tráfico por canal, eventos de conversión, curvas de retención
- **Stripe MCP** → MRR, ARR, churn, mezcla de planes, LTV blended por cohorte
- **App Store Connect** (manual o `dev-browser`) → funnel instalación → trial → pago; retención de cohorte
- **Customer.io MCP** → inventario de flujos, tasas de envío / apertura / clic / desuscripción
- **Shopify** → conversión de página de producto, AOV, tasa de recompra
- **GitHub MCP** → inventario de repos, fechas del último commit, qué está desactualizado
- **Notion** → directorio de conocimiento interno si está expuesto

No le pidas al usuario que copie/pegue datos que se pueden extraer directamente.

### Paso 1.4 — Realizar el intake estructurado

Para cada brecha en el material, pregúntale al usuario. El intake mínimo cubre diez temas:

#### Intake 1 — Visión general del cliente
- ¿Qué hace la empresa, en una oración (palabras del founder)?
- ¿Cuál es el producto primario?
- ¿Qué otros productos / SKUs / niveles existen?
- ¿El producto está en vivo, beta, o pre-lanzamiento?
- Si está en beta: ¿throttling? ¿timeline de GA?

#### Intake 2 — ICP
- ¿Para quién eres, en una oración?
- ¿Qué dicen que quieren?
- ¿Qué quieren realmente?
- ¿Cuál es su problema declarado? ¿Su problema real?
- Demografía / firmografía: ¿quién encaja exactamente con el ICP?

#### Intake 3 — Estado del funnel hoy
- ¿Cuáles son los números actuales del funnel? (signups, activaciones, pago, retención)
- ¿Cuál es la *forma* del funnel — está cuellado en el tope, en el medio, o en el fondo?
- ¿Cuál es la mayor fuga?

#### Intake 4 — Estado de financiamiento
- ¿Ronda actual (pre-seed / seed / Series A / etc.)?
- ¿Total levantado hasta la fecha?
- ¿Burn / runway actual?
- ¿Ronda activa? ¿Cierra cuándo?
- ¿Inversionistas notables?
- ¿Permiso para mencionar el engagement de fCMO en pitches?

#### Intake 5 — Equipo
- ¿Founders y qué posee cada uno (producto, marketing, ventas, etc.)?
- ¿Otros roles en el equipo y su superficie de marketing?
- ¿Advisors que tocan marketing?
- ¿Agencias / contratistas / fraccionales?
- ¿Dónde están las brechas obvias?
- Para el owner actual de marketing del equipo (si existe): ¿la forma es π-shaped (dos skill sets profundos), T-shaped (uno profundo, amplio), o solo táctico? Ver `team-and-agency-model.md` para el marco que informa el RACI de la Sección 11 y la recomendación de primera contratación en la Sección 9.

#### Intake 6 — Presupuesto
- ¿Gasto mensual actual de marketing, desglosado: adquisición pagada, herramientas, retainers, headcount?
- ¿A qué nivel de presupuesto mapea (ver `funding-stage-unlocks.md`)?
- ¿Qué presupuesto se desbloquea cuando cierre la siguiente ronda?
- CAC blended si se conoce (incluyendo salarios, costos de contenido, herramientas, retainers — no solo el gasto en anuncios pagados). Si se desconoce, márcalo como la principal decisión abierta de la Sección 13 — cada proyección de ingresos depende de él.
- ARPC, tasa de retención anual (o tasa de churn), para que las matemáticas de presupuesto en `budget-planning.md` puedan aplicarse a la Sección 8 (Ingresos) y la Sección 10 (Perspectiva a 12 meses).

#### Intake 7 — Canales actualmente activos
- Adquisición: SEO orgánico, búsqueda pagada, paid social, contenido, social, partnerships, eventos, PR, ambassadors, etc. — para cada uno, estado (vivo / pausado / nunca probado)
- Activación: estado del onboarding, flujo de signup, paywall, experiencia de primera sesión, listado en app store
- Retención: estado del email de lifecycle, upsells in-app, cohorte de churn
- Referidos: existencia de programa, atribución, interés inbound
- Ingresos: estructura de pricing, mezcla de planes, experimentos recientes

#### Intake 8 — Ya hecho
¿Qué trabajo pasado debería reconocer este plan?
- Lanzamientos mayores y fechas
- Momentos de PR y quién los cubrió
- Pilares / hubs / piezas cornerstone de contenido
- Partnerships
- Premios / certificaciones
- Clientes / usuarios notables (si son usuarios de consumo nombrados)
- Advisors / fraccionales pasados

#### Intake 9 — En curso y estancado
- ¿Qué está borrado pero no publicado? ¿Por qué?
- ¿Qué ha estado "casi listo" por meses?
- ¿Qué está bloqueando cada uno?
- ¿Qué está roto o activamente dañino?

#### Intake 10 — Postura estratégica
- Lo más importante que arreglar este trimestre (lectura del founder)
- Lo más importante que ignorar este trimestre (lectura del founder)
- Qué preguntan más los inversionistas / el board
- Cualquier restricción no visible en otro lado (legal, relacionada con partnerships, relacionada con marca)

### Paso 1.5 — Puntuar el estado actual contra la rúbrica

Usa la rúbrica de 17 secciones en `references/current-state-rubric.md` como tu lente de puntuación. Dos modos:

- **A partir de material rico.** Cuando el equipo ha compartido decks, auditorías de contenido previas, un documento de voz de marca existente, trabajo de posicionamiento reciente, o una transcripción de llamada de kickoff — puntúa a partir de eso. Marca "puntuado a partir de material" en el encabezado de la sección.
- **A partir de una auditoría puntuada por separado.** Si el equipo ya tiene una evaluación de estado actual puntuada (en cualquier formato), incorpora esos números directamente. No repitas el trabajo.

De cualquier forma, la salida es la tabla puntuada de 17 filas que se convierte en la Sección 3 del plan, seguida de una "interpretación de forma" de 2 a 4 oraciones señalando dónde se agrupan las fortalezas y las brechas.

### Paso 1.6 — Escribir research.md

Compila todo en `research.md` con esta estructura:

```markdown
# {Cliente} — Registro de Investigación del Plan de Marketing

**Fecha:** AAAA-MM-DD
**Autor:** (nombre del fCMO / planificador)

## Panorama de la empresa
- Descripción en una oración
- Etapa (pre-seed / seed / Series A / etc.)
- Estado del producto (beta / GA)

## ICP
- ICP primario
- Problema declarado vs. real
- Demografía / firmografía

## Estado del funnel hoy
- Números actuales
- Forma del funnel
- Mayor fuga

## Financiamiento
- Total levantado
- Estado de la ronda actual
- Runway

## Equipo
- Founders y propiedad
- Superficie de marketing por persona
- Brechas

## Presupuesto de marketing actual
- $/mes total
- Desglose
- Mapeo de nivel

## Canales actualmente activos
[Por etapa AARRR]

## Ya hecho (reconocer en el plan)
[Lista]

## En curso y estancado
[Lista con bloqueadores]

## Postura estratégica
- Prioridad principal del founder
- De-priorización principal del founder
- Puntos de presión de inversionistas
- Restricciones

## Puntajes de la rúbrica de estado actual
[Puntajes de las 17 secciones usando `references/current-state-rubric.md`. Si existe una auditoría previa puntuada, pega esos puntajes. De lo contrario marca "puntuado a partir de material".]

## Material leído
[Lista de archivos en materials/ + cuándo se leyeron]
```

Guarda. Pasa a la Fase 2.

---

## Fase 2 — REVIEW (redacción sección por sección)

**Meta:** Recorrer las 13 secciones de la plantilla del plan (`references/plan-template.md`), redactando cada una, obteniendo confirmación del usuario, guardando a medida que avanzas.

### Paso 2.1 — Inicializar progress.md

Usa el esquema definido en el Paso 1.1.1 arriba. Fija `phase: review`, `current_section: 2`, `plan_version: v1`, y sella `last_updated`.

### Paso 2.2 — Recorre cada sección en este orden: 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, luego 1

La Sección 1 (Resumen Ejecutivo) se redacta **al final** porque depende de las conclusiones de todas las demás secciones. Recorre las Secciones 2 → 13 en orden numérico, luego sintetiza la Sección 1 a partir de las otras. El `final_plan.md` compilado final siempre se presenta en el orden canónico 1 → 13.

Para cada sección, usa la plantilla en `references/plan-template.md` para redactar. Luego en el chat:

1. Presenta el borrador (o los puntos clave — secciones cortas en línea, secciones largas como bosquejo de bullets primero)
2. Pregunta: *"¿Apruebas, ajustas, o expandes?"*
3. Itera hasta que el usuario confirme
4. Guarda el texto confirmado en `sections/01.md` ... `sections/13.md` (un archivo por sección, con ceros a la izquierda para el orden). Este es el artefacto canónico persistido — la recuperación depende de él.
5. Marca la casilla en `progress.md`
6. Pasa a la siguiente sección

### Paso 2.3 — Guía específica por sección

**Sección 1 (Resumen ejecutivo)** se sintetiza a partir de las Secciones 2–13 después de que todas estén aprobadas. Redáctala al final; preséntala primero en el documento de salida.

**Sección 3 (Estado actual)** usa la rúbrica embebida de 17 secciones en `references/current-state-rubric.md`. Si existe una auditoría previa puntuada, pega esos puntajes. Si no, puntúa a partir del material disponible.

**Secciones 4–8 (AARRR)** cada una sigue la misma estructura interna: estado actual, el plan (movidas numeradas), movidas a 90 días, perspectiva a 12 meses, skills + herramientas. No te saltes la subsección de skills + herramientas — es lo que hace al plan operativamente honesto.

**Sección 11 (Stack de operaciones de marketing)** es auto-generable a partir de `references/ops-stack-mapping.md` más las movidas específicas nombradas en las Secciones 4–8.

**Sección 12 (Banco de ideas)** es auto-generable a partir de `references/idea-cross-reference.md` más filtros específicos del cliente (omitir ideas que entren en conflicto con la voz de marca; el estado de las movidas cambia según el timing de la etapa de financiamiento).

**Sección 13** vive al final. Las decisiones abiertas deben ordenarse por impacto. El apéndice debe referenciar solo archivos a los que el equipo pueda acceder (advertir sobre rutas locales de la máquina).

### Paso 2.4 — Consistencia de voz de marca

Si el cliente tiene reglas de voz de marca documentadas (capturadas en research.md / Sección 2), cada sección debe respetarlas. Restricciones de voz comunes:
- Reglas de vocabulario (listas SÍ / NO)
- Reglas de CTA (p. ej., "nunca presionar")
- Encuadre iniciático vs. explicativo
- Tono (p. ej., autoritativo-pero-accesible, íntimo-pero-profesional)

Si el borrador de una sección viola la voz de marca, rehazlo antes de mostrárselo al usuario.

---

## Fase 3 — FINALIZE (compilar + verificar + publicar)

**Meta:** Producir `final_plan.md` y opcionalmente publicar en un repo compartido.

### Paso 3.1 — Compilar

Fija `phase: finalize` en `progress.md` antes de empezar. Concatena `sections/01.md` a `sections/13.md` en `final_plan.md` (orden canónico 1 → 13, sin importar el orden de redacción). Agrega:
- Encabezado de título con fecha y marcador de versión "v1"
- Frontmatter "Preparado por / Para / Fecha / Estado"
- Anclas de sección que funcionen al pegarse en Notion

### Paso 3.2 — Pasada de verificación

Antes de imprimir:

- **Verificación de referencias cruzadas** — cada número de marketing-ideas (p. ej., "idea #17") coincide con la idea real en `references/idea-cross-reference.md`. Cada mención de skill relacionada existe en el repo `marketingskills` o está documentada como dependencia externa (ver la nota sobre skills de otros marketplaces en ops-stack-mapping).
- **Verificación de MCP/API** — cada herramienta mencionada en la Sección 11 realmente existe en el stack del usuario (según el intake de research.md) O está marcada como "futura / aún no conectada."
- **Verificación de rutas** — no hay rutas específicas de la máquina (`/Users/...`, `/home/...`) en la salida. Reemplázalas con referencias descriptivas.
- **Verificación de voz** — lectura final contra las reglas de voz de marca. Marca y corrige violaciones.
- **Verificación de decisiones abiertas** — cada "TBD" o pregunta sin responder del intake está listada en las decisiones abiertas de la Sección 13, no escondida en el cuerpo.
- **Verificación de reconocimiento** — cada elemento de "ya hecho" en research.md se reconoce en algún lugar del plan.

### Paso 3.3 — Imprimir

Envía `final_plan.md` a la carpeta del plan. Imprime un resumen en el chat:

> *"Plan de Marketing v1 guardado en `~/marketing-plans/{client-slug}/final_plan.md`. ~X,XXX palabras a través de 13 secciones. Listo para pegar en Notion o compartir con el equipo."*

### Paso 3.4 — Publicar (opcional)

Pregúntale al usuario:
> *"¿Quieres que publique esto en un repo compartido de GitHub para que el equipo tenga acceso? Si es así, ¿cuál es el repo y ruta destino (p. ej., `{client-org}/{client-context}/marketing/plan.md`)?"*

Si sí:
- Clona (o asume clonado) el repo destino
- Crea una rama feature o publica directo a main según la preferencia del usuario
- Copia `final_plan.md` a la ruta destino
- Ajusta el apéndice para usar rutas relativas al repo (no rutas de la máquina)
- Commit + push
- Confirma con la URL del commit

Si no: déjalo local. Listo.

### Paso 3.5 — Marcar como finalizado

Fija `phase: finalized` en `progress.md` y sella `last_updated`. Este es el estado terminal y evita que futuras invocaciones de `/marketing-plan` sobrescriban silenciosamente el plan (ver Paso 1.1.2 caso 6).

---

## Reanudando un plan

La reanudación se rige enteramente por el árbol de decisión en el Paso 1.1.2 de arriba — siempre revisa el estado en ese orden en cada invocación.

Si el usuario dice *"empezar de nuevo"* → pregunta si quiere borrar la carpeta existente o moverla a `archive/` primero; no sobrescribas silenciosamente.
Si el usuario dice *"rehacer la Sección X"* → desmarca esa casilla en `progress.md`, borra `sections/0X.md`, y redacta de nuevo.

## Modos de falla a vigilar

- **Saltarse el intake.** Un plan escrito sin un intake apropiado es genérico y no sobrevivirá el contacto con el founder. Siempre haz el intake completo de diez temas a menos que el usuario lo exima explícitamente.
- **Fingir que existen datos.** Si no puedes confirmar un número (MRR actual, tasa de retención, etc.), no adivines. Márcalo `[TBD — confirmar con el equipo]` en el plan y agrégalo a las decisiones abiertas.
- **Ignorar la voz de marca.** Si el cliente tiene una voz fuerte (la mayoría la tiene), cada sección debe respetarla. Lee las reglas de voz antes de redactar cualquier texto adyacente a copy.
- **Rellenar el banco de ideas.** La Sección 12 es integral solo si incluye la lista de omitidos con razones. No rellenes con ideas que claramente no encajan solo para llegar a las 139.
- **Pasar por alto métricas incómodas.** Si el churn es alto o la activación es baja, nómbralo en Estado Actual. Los founders leen más allá del maquillaje.
- **Olvidar la lógica de etapa de financiamiento.** Si el cliente está en medio de una ronda, el plan debe explicar qué cambia cuando cierre. Saltarse esto convierte un plan en una lista de deseos.
