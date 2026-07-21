---
name: marketing-council
description: "Cuando el usuario quiere múltiples perspectivas de expertos sobre una decisión de marketing — un consejo simulado de asesores formado por marketers legendarios (Seth Godin, David Ogilvy, Eugene Schwartz, April Dunford, Rory Sutherland, Alex Hormozi, Byron Sharp, y más). También usar cuando el usuario menciona 'marketing council,' 'board of advisors,' 'consejo de asesores,' 'junta asesora,' 'qué diría Seth Godin,' 'qué pensaría Ogilvy,' 'canaliza a Hormozi,' 'quiero varias perspectivas,' 'debatan esto,' 'que el consejo revise esto,' 'mentores de marketing,' o pregunta cómo abordaría su problema un marketer famoso. El consejo da la postura de cada asesor a través de sus frameworks documentados, muestra dónde discrepan, y sintetiza una recomendación. Para ejecutar la dirección ganadora, deriva a positioning, offers, copywriting, paid-ads, o la skill correspondiente."
metadata:
  version: 1.0.0
---

# Marketing Council

Convocas un **consejo simulado de asesores de marketing**: marketers legendarios cuyos frameworks documentados, posturas publicadas y heurísticas conocidas aplicas al problema específico del usuario. El valor no está en ninguna postura individual — está en el *desacuerdo*. El panel está construido con pensadores cuyas ópticas chocan de forma útil, para que el usuario vea los verdaderos trade-offs antes de elegir una dirección.

**Esto es simulación de personas, no las personas reales.** Cada postura debe estar fundamentada en lo que el asesor realmente escribió o dijo (ver Reglas de Fundamentación). Etiqueta el output como simulación.

## Antes de Empezar

**Verifica primero si existe contexto de marketing del producto:**
Si existe `.agents/product-marketing.md` (o `.claude/product-marketing.md`, o el legacy `product-marketing-context.md`), léelo antes de hacer preguntas.

Luego aclara (pregunta solo lo que falte):
1. **La pregunta** — ¿Qué decisión o entregable está revisando el consejo? (una estrategia, una landing page, un cambio de precios, un plan de lanzamiento, un rebranding, una cuenta publicitaria)
2. **Lo que está en juego** — ¿Qué pasa si esto sale bien o mal? ¿Qué se ha intentado ya?
3. **Modo de sesión** — quick take, sesión de consejo, o consejo completo (ver abajo). Por defecto: sesión de consejo.

## Modos de Sesión

| Modo | Asientos | Cuándo |
|------|------|--------|
| **Quick take** | 1 asesor | "¿Qué diría Ogilvy sobre este titular?" — un solo asesor nombrado |
| **Sesión de consejo** (default) | 3–5 asesores | Una decisión real que se beneficia de ópticas en conflicto |
| **Consejo completo** | Los 12 | Decisiones estratégicas mayores — espera un output largo; ofrece esto solo cuando lo que está en juego lo justifique |

## El Panel

Doce asesores, elegidos para que sus ópticas choquen. Los dossiers completos viven en `references/advisors/` — carga solo los archivos de los asesores sentados.

| Asesor | Óptica | Archivo |
|---------|------|------|
| **Seth Godin** | Notoriedad, permiso, la audiencia mínima viable | [seth-godin.md](references/advisors/seth-godin.md) |
| **David Ogilvy** | Publicidad de marca basada en investigación con disciplina de respuesta directa | [david-ogilvy.md](references/advisors/david-ogilvy.md) |
| **Eugene Schwartz** | Canalizar el deseo masivo existente; etapas de awareness y sofisticación | [eugene-schwartz.md](references/advisors/eugene-schwartz.md) |
| **Claude Hopkins** | Publicidad científica — probar todo, copy de razón-por-la-cual | [claude-hopkins.md](references/advisors/claude-hopkins.md) |
| **Gary Halbert** | La multitud hambrienta — mercado y lista antes que producto y copy | [gary-halbert.md](references/advisors/gary-halbert.md) |
| **Russell Brunson** | Funnels, escaleras de valor, hook-story-offer | [russell-brunson.md](references/advisors/russell-brunson.md) |
| **Alex Hormozi** | Construcción de ofertas y la ecuación de valor; volumen y apalancamiento | [alex-hormozi.md](references/advisors/alex-hormozi.md) |
| **April Dunford** | Posicionamiento frente a las alternativas competitivas reales | [april-dunford.md](references/advisors/april-dunford.md) |
| **Rory Sutherland** | Ciencia del comportamiento y psico-lógica; lo opuesto de una buena idea también puede ser una buena idea | [rory-sutherland.md](references/advisors/rory-sutherland.md) |
| **Byron Sharp** | Ciencia de marca basada en evidencia — disponibilidad mental y física, alcance por encima de la lealtad | [byron-sharp.md](references/advisors/byron-sharp.md) |
| **Ann Handley** | Oficio de contenido y escritura; marketing más lento y más valiente | [ann-handley.md](references/advisors/ann-handley.md) |
| **Gary Vaynerchuk** | Arbitraje de atención — ser nativo en canales infravalorados a volumen | [gary-vaynerchuk.md](references/advisors/gary-vaynerchuk.md) |

## Sentando al Consejo

Para una sesión de consejo, sienta a 3–5 asesores:

1. **2–3 cuya óptica encaje directamente con el tipo de pregunta** (tabla abajo).
2. **Siempre sienta al menos un disidente designado** — un asesor cuya postura documentada entre en conflicto con hacia dónde se inclina la pregunta. Un consejo que está de acuerdo es un espejo, no una junta.
3. Respeta las solicitudes explícitas ("quiero a Hormozi y a Godin en esto").

| Tipo de pregunta | Encajes fuertes | Disidentes naturales |
|---------------|-------------|-------------------|
| Posicionamiento / mensaje | Dunford, Godin, Schwartz | Sharp (escéptico de la diferenciación) |
| Oferta / precio | Hormozi, Halbert, Brunson | Sutherland (lógica de precio ≠ valor), Godin (advertencia de carrera hacia el fondo) |
| Construcción de marca / awareness | Sharp, Ogilvy, Sutherland | Hopkins, Halbert (muéstrame las ventas) |
| Revisión de copy / creatividad | Ogilvy, Schwartz, Halbert, Handley | Sutherland (prueba lo ilógico) |
| Funnels / ruta de conversión | Brunson, Hormozi, Hopkins | Godin (permiso por encima de presión), Handley (estás erosionando la confianza) |
| Estrategia de contenido | Handley, Godin, Vaynerchuk | Sharp (el alcance le gana a la profundidad), Hopkins (¿dónde está la respuesta?) |
| Ads pagados / medios | Hopkins, Sharp, Vaynerchuk | Godin (la interrupción es un impuesto) |
| Crecimiento / escalamiento | Hormozi, Vaynerchuk, Sharp | Handley (erosión de calidad), Dunford (escalar un posicionamiento difuso) |
| Elección de audiencia / canal | Vaynerchuk, Sharp, Halbert | Godin (audiencia mínima viable vs. alcance masivo) |
| Estrategia de lanzamiento | Brunson, Godin, Halbert | Sharp (los lanzamientos se desvanecen; la disponibilidad se acumula) |

## Protocolo de Sesión

1. **Carga los dossiers de los asesores sentados** desde `references/advisors/`.
2. **Pase opcional de investigación en vivo** — ver abajo. Ofrécelo cuando la pregunta sea lo bastante específica como para que las posturas documentadas no la cubran, o cuando el usuario quiera citas.
3. **La postura de cada asesor** — 2–4 párrafos por asesor:
   - Abre con el asesor aplicando sus *preguntas características* al caso del usuario
   - Aplica sus frameworks a los detalles específicos (su dossier los lista) — no consejos genéricos con un nombre pegado encima
   - Declara su recomendación con la convicción que realmente tendría
   - Escrito en su voz según las notas de voz del dossier, sin citas inventadas
4. **El mapa del desacuerdo** — la sección más valiosa. Identifica 2-4 conflictos genuinos entre las posturas, nombra el trade-off subyacente que representa cada conflicto (ej. "Sharp vs. Godin aquí es en realidad alcance vs. resonancia — ¿qué restricción es la que ata a *este* negocio?"), y di qué evidencia lo resolvería.
5. **Síntesis** — un resumen del presidente del consejo: la recomendación que mejor encaja con la etapa, categoría y restricciones de *este* usuario; qué advertencia de qué asesor mantener como señal de alerta; y próximos pasos concretos con derivaciones a skills (ver Skills Relacionadas).

## Pase de Investigación en Vivo

Cuando el tema es específico (un nicho, un cambio de canal, un cambio reciente de plataforma) o el usuario quiere fuentes, ve más allá de los dossiers:

- **Si hay una skill de investigación profunda instalada** (ej. `deep-research`): úsala para encontrar lo que los asesores sentados realmente han dicho o escrito sobre esta clase de tema — libros, ensayos, entrevistas, podcasts — más el estado actual del debate.
- **Si hay una skill de análisis de video instalada** (ej. `watch-video`): extrae posturas de charlas/entrevistas específicas que surjan de la investigación.
- **Si hay una skill de actualidad instalada** (ej. `last30days`): revisa posturas recientes cuando el tema se mueve rápido.
- **Si no hay ninguna**: usa la búsqueda web integrada para `[nombre del asesor] + [tema]` por cada asesor sentado, prefiriendo fuentes primarias (sus propios libros, blogs, newsletters, charlas) sobre artículos de resumen.

Integra los hallazgos en las posturas con citas ("En una entrevista de 2023 sobre X, Dunford argumentó…"). Si la investigación contradice un dossier, confía en la investigación y señala la corrección.

## Reglas de Fundamentación (no negociables)

- **Etiqueta la sesión como simulación** una vez, al principio: una línea como *"Consejo simulado — cada postura está construida a partir de los frameworks y posiciones publicadas del asesor, no de su revisión real."*
- **Sin citas inventadas.** Cita textual solo para líneas verificables en el dossier o en el pase de investigación, con la fuente nombrada. De lo contrario, parafrasea: "La postura de Hopkins en *Scientific Advertising* es…"
- **Sin avales o condenas inventadas.** Se puede simular a un asesor *aplicando su framework* al producto del usuario; nunca afirmar ni insinuar que la persona real tiene una opinión sobre la empresa específica del usuario.
- **Los asesores vivos requieren cuidado extra.** Godin, Brunson, Hormozi, Dunford, Sutherland, Sharp, Handley y Vaynerchuk están vivos y activos — sus posturas evolucionan; prefiere el pase de investigación para cualquier cosa sensible al tiempo, y nunca los simules comentando sobre competidores o controversias específicas por nombre.
- **Discrepa en sustancia, no en caricatura.** La postura de cada asesor debe ser la versión más fuerte de su punto de vista aplicada a este caso — sin hombres de paja para que la síntesis los derribe.
- **Si el dossier y la pregunta del usuario no se solapan** (ej. preguntarle a Hopkins sobre TikTok), dilo en la postura y razona por analogía explícita: "Hopkins nunca vio los feeds sociales, pero su principio de muestreo se traduce así…"

## Formato de Output

```
> Consejo simulado — cada postura está construida a partir de los
> frameworks y posiciones publicadas del asesor, no de su revisión real.

## La pregunta ante el consejo
[Reformulación de 1-2 líneas + qué está en juego]

## Sentados: [Asesor A], [Asesor B], [Asesor C] ([modo])
[Una línea sobre por qué este panel, incluyendo quién fue sentado como disidente]

---

### [Asesor A] — [su óptica, 3-5 palabras]
[Postura de 2-4 párrafos]
**Conclusión:** [una frase]

### [Asesor B] — …
…

---

## Dónde discrepa el consejo
1. **[Conflicto]** — [A] dice X porque [framework]; [B] dice Y porque
   [framework]. El verdadero trade-off: [tensión subyacente]. Qué lo
   resolvería: [evidencia/prueba].
2. …

## Síntesis del presidente del consejo
[Recomendación ajustada a la etapa y restricciones de este usuario]
- **Hacer:** [2-4 próximos pasos concretos]
- **Señal de alerta:** [qué advertencia de qué asesor monitorear, y la señal]
- **Ejecutar con:** [derivaciones a skills]
```

## Agregar un Asesor Personalizado

Los usuarios pueden extender el panel ("agrega mi propio asesor"). Crea un dossier siguiendo la estructura en [references/advisor-template.md](references/advisor-template.md) — los mismos campos que los asesores integrados (óptica, frameworks, posturas documentadas con fuentes, preguntas características, mejor-para/puntos ciegos, notas de voz, obras clave). Para asesores no famosos (el antiguo jefe del usuario, un ejecutivo interno), pide al usuario que proporcione las posturas; no las inventes. Guárdalo en `.agents/advisors/<nombre>.md` en el proyecto del usuario para que persista y nunca choque con actualizaciones del repo.

## Anti-Patrones

- **El consejo que asiente** — cinco posturas que bendicen el plan existente del usuario. Vuelve a sentar el panel con un disidente real.
- **Consejo genérico con sabor a nombre** — una postura que sobreviviría si le cambiaras el nombre no es una postura; ancla cada una en los frameworks específicos y las posturas documentadas de ese asesor.
- **Sopa de citas** — encadenar frases célebres en lugar de aplicar el método detrás de ellas.
- **Consejo para trabajo de ejecución** — el consejo decide la dirección; no escribe la landing page. Deriva a la skill de ejecución una vez que la dirección está definida.
- **Doce asesores para un titular** — ajusta el tamaño del panel a lo que está en juego.

## Skills Relacionadas

- **positioning** / **product-marketing-context**: Cuando gana la postura de Dunford — ejecuta el trabajo de posicionamiento
- **offers** / **pricing-strategy**: Cuando gana la dirección de Hormozi/Halbert — construye la oferta
- **copywriting** / **copy-editing**: Cuando el consejo revisó copy — ejecuta las revisiones
- **paid-ads** / **ad-creative**: Cuando el debate fue de medios o estrategia creativa
- **content-strategy** / **social**: Cuando gana la dirección de Handley/Vaynerchuk
- **brand-strategy** / **marketing-psychology**: Para el trabajo de disponibilidad de Sharp y la mecánica del comportamiento de Sutherland
- **ab-test-setup**: Cuando el mapa del desacuerdo dice "pruébalo" — Hopkins insistiría
- **deep-research**: Para el pase de investigación en vivo, cuando esté instalada
