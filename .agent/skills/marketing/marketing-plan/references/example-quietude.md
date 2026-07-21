# Ejemplo — Plan de Marketing de Quietude v1

**Este es el ejemplo de referencia canónico para la skill `/marketing-plan`.** Está basado en un engagement real de fCMO para una plataforma híbrida de bienestar hardware-y-software. **Los nombres, dominios, y detalles identificables han sido cambiados** — el cliente se llama "Quietude" aquí, y los miembros del equipo han sido renombrados (Alex / Sam / Casey / Devon). Los números del funnel, el presupuesto, y las lecciones estructurales preservan la forma del engagement original para que el ejemplo conserve su valor didáctico.

Usa esto como la referencia de "cómo se ve lo bueno" al redactar un plan nuevo. La estructura, el tono, la profundidad, y la especificidad operativa son la barra a superar.

**Arquetipo de Quietude:** Híbrido hardware + software con capa de credibilidad deep-tech / clínica. Ver `references/client-types.md` para patrones de arquetipo.

**Contexto de etapa de financiamiento:** Pre-cierre-de-seed (en medio de un levantamiento de $3M de seed). Tier 1 según `references/funding-stage-unlocks.md`. $0 de presupuesto pagado; solo orgánico + lifecycle + ambassador.

**Qué fue fuerte de este plan:**
- El marco estratégico (Sección 2) se apoyó en el propio encuadre del founder de meditación-vs-regulación como el pilar de contenido
- El estado actual (Sección 3) incluyó la rúbrica de auditoría de 17 secciones puntuada contra material existente (no se corrió una auditoría formal)
- El roadmap a 90 días (Sección 9) tuvo movidas asignadas a un owner, no solo acciones
- El stack de operaciones (Sección 11) incluyó un punto de prueba operativo concreto (MCP de Customer.io usado en vivo por el founder no técnico en la llamada de kickoff)
- El banco táctico de ideas (Sección 12) cruzó las 139 marketing-ideas con AARRR + estado específico de Quietude, incluyendo 23 omisiones explícitas con justificación

---

# Quietude — Plan de Marketing v1

**Preparado por:** Casey Reed (fCMO)
**Para:** Alex, Sam, y el equipo de Quietude
**Fecha:** 2026-05-27
**Estado:** Borrador v1 — para revisión del equipo

## 1. Resumen ejecutivo

Quietude ha construido algo raro: un producto clínicamente validado, coherente en su marca, liderado por el founder, en una categoría que aún no tiene nombre. La oportunidad en los próximos doce meses no es inventar un motor de marketing desde cero — es **convertir la gravedad orgánica existente en un funnel medible y repetible**, luego agregar la adquisición pagada encima de ese funnel una vez que cierre la ronda de seed.

**Tres grandes apuestas, ordenadas por apalancamiento:**

1. **Arreglar la fuga antes de echar más agua.** La forma del funnel Día 1 → Día 35 (1.34% → 5.46%) nos dice que el producto convierte dado tiempo y contacto. Lo que le falta es un momento de primera sesión que funcione (el gate de audífonos está matando la conversión) y una capa de lifecycle para entregar el contacto. Estas dos piezas — reconstrucción del onboarding y flujos de Customer.io publicados — son el desbloqueo para todo lo demás.
2. **Componer los moats que Quietude ya tiene.** Estudio clínico peer-reviewed, PR de influencer de longevidad, 15K participantes de eventos en vivo, la voz del founder de Alex — estos son generadores de enlaces, pilares de contenido, y anclas de credibilidad que la mayoría de las marcas de bienestar matarían por tener. Están subaprovechados. El SEO, el contenido, y la optimización de App Store los traducen en superficie de búsqueda y descubrimiento.
3. **Construir el sistema operativo founder-y-fCMO que permite a un equipo de 4 personas hacer marketing como uno de 20.** Esto es lo que hace que el plan sea realmente ejecutable al tamaño de equipo y ritmo de quema de Quietude — las herramientas agénticas encima de Customer.io, Shopify, App Store, Stripe, GitHub, y la librería de marketing skills significan que publicamos sin contratar.

**Cómo se ve doce meses, de forma plausible:**

- La app pasa de beta a GA. El onboarding convierte con un lift significativo sobre la línea base de hoy.
- 4 pilares de contenido SEO sembrados, con el Pilar 1 (Regulación del Sistema Nervioso) y el Pilar 2 (Sueño + Antifaz) posicionando en keywords Tier-1.
- Lifecycle completo vivo en Customer.io: onboarding, reenganche de usuarios inactivos, post-compra de hardware, opt-ins del centro de suscripción.
- Programa de ambassador vivo con 15–25 hosts activos. Primer piloto de certificación de Quietude Guides corrido.
- La cuña del antifaz vendiéndose a escala vía Shopify con una ruta limpia de activación hardware → app. CAC blended medido y rastreado.
- Adquisición pagada disparando post-cierre-de-seed a un presupuesto inicial de prueba de $5–10K/mes, escalando a $20–50K/mes si la unit economics se valida.
- La narrativa de Series A se escribe sola: evidencia clínica + lift de activación + composición de lifecycle + primeros casos de referencia de instalación B2B.

**Las prioridades a 90 días** (que el resto de este documento operacionaliza):

1. Matar el gate de audífonos. Publicar la corrección de base esta semana.
2. Correr la prueba de onboarding de tres variantes. Encontrar el ganador de activación.
3. Publicar los Flows 6 (post-compra del antifaz) y 4 (usuario inactivo) de Customer.io — retener el Flow 2 (onboarding) hasta que la UI de la app se estabilice.
4. Reescribir el listado de App Store en la voz de marca de Quietude. El activo no-sitio de mayor apalancamiento en este momento.
5. Sentar la fundación de SEO: consolidar a `quietude.app`, publicar el hub del Pilar 1 + 3 spokes, publicar la landing page del estudio peer-reviewed de psicofisiología.
6. Lanzar el programa de ambassador con los ~5 inbound que están esperando.

Todo lo demás compone encima de esos seis.

---

## 2. Marco estratégico

Esta sección destila el posicionamiento, el ICP, y la voz de marca en lo que el equipo necesita tener en mente al ejecutar. El detalle completo vive en `marketing-os.md`, `icp.md`, y `sound-philosophy.md`.

### Qué es Quietude, en una oración

Una plataforma de inteligencia del sistema nervioso — audio espacial clínicamente validado + compañero de reflexión de IA (Mira) + hardware + instalaciones en venues + red de practicantes. *"Empezamos con sonido. Nos expandimos a todos los sentidos. Terminamos con ciudades."*

### La categoría que estamos reclamando (y defendiendo)

Quietude no encaja en la categoría de apps de meditación, la categoría de audio de enfoque, ni la categoría de sleep tech. La marca hace un reclamo más fuerte: **regulación del sistema nervioso bottom-up a través de audio espacial**, con evidencia clínica como prueba y credibilidad somática como defensa.

El marco que define la categoría, según Alex (2026-05-19): **La meditación es top-down. Quietude es bottom-up.** La meditación usa la mente para comandar el cuerpo — kung fu mental que le falla precisamente a las personas más propensas a necesitar ayuda, porque la corteza prefrontal está desconectada cuando hay estrés. Quietude entra por el tallo cerebral, antes de la mente pensante. El cuerpo responde antes de tener que intentarlo. (Tratamiento completo del pilar de contenido en `meditation-vs-regulation.md`.)

Este es el mensaje estratégico más importante. Pertenece al copy de App Store, onboarding, email de lifecycle, contenido SEO, talking points de ambassador, y el seed deck.

### Para quién somos (ICP D2C, destilado)

Profesionales sobreestimulados y de alto rendimiento, 25–45, urbanos (Bay Area, NYC, Londres, Berlín, Austin). Trabajadores tech, founders, creadores, académicos, diseñadores, consultores. A menudo neurodivergentes (TDAH, HSP, superdotados). Compradores sofisticados de bienestar — ya invertidos fuertemente en su vida interior.

**Su problema declarado:** *"No puedo apagar mi cerebro. He probado apps de meditación. No funcionan."*

**Su problema real:** Sobreestimulación, no falta de motivación. Su don (pensar rápido) se convirtió en una maldición. Necesitan permiso para dejar de optimizar — incluyendo su descanso.

**Qué están comprando realmente:** la *sensación* de estabilidad, indulgencia sensorial, rituales hermosos, efectividad sin esfuerzo, un atajo lujoso hacia el genio al que no pueden acceder en medio del caos.

### La lógica del modelo de negocio (según el seed deck)

**El B2B siembra el mercado. El D2C cosecha.** Una instalación en un venue pone a Quietude frente a ~20K personas/año a un costo de ~$17K → 5% convierte a suscripciones → ~$430K/año por venue. Seis canales de composición (referidos, Guides, contenido, hosting en casa, PR, comunidad) hacen que el CAC se aproxime a cero para el Año 3. Año 5: 75% de las nuevas suscripciones vienen de canales de costo casi cero.

**El alcance del fCMO según el kickoff: liderado por D2C.** Alex posee las ventas B2B a través de eventos/red/credibilidad del founder. El apalancamiento del fCMO está en el lado D2C de app/hardware. Este plan refleja esa división — el B2B se reconoce como el motor de cosecha pero no se trata como superficie de trabajo primaria.

### Voz de marca (el no-negociable)

Según el Marketing OS:
- **Tono.** Autoritativo pero accesible. Íntimo pero profesional. Revolucionario pero fundamentado. La autoridad viene de la experiencia vivida, no de la explicación.
- **Habla desde el cuerpo, no desde la mente.** Cada oración restaura la seguridad y orientación somática. El lenguaje abre espacio en lugar de cerrar significado.
- **Vocabulario SÍ:** Vivacidad, vida interior, sistema nervioso, sonido espacial, resonancia, seguridad somática, claridad encarnada, ritmo natural, orientación, iniciación, decir la verdad.
- **Vocabulario NO:** Zen, chill, vibes, "alta vibración," bypass espiritual, clichés de meditación, lenguaje didáctico/explicativo, "déjame explicarte por qué esto funciona."
- **Método central: Reflexión Iniciática.** El propósito de la escritura no es explicar o convencer — es cambiar el estado interno del lector. El resultado debe ser *"algo en mí se movió,"* no *"entiendo este concepto."*
- **Regla de CTA:** Nunca presionar. "No recordamos. Invitamos."

Esta regla restringe cada pieza de copy en cada etapa AARRR. En caso de duda: reescribir desde el cuerpo.

---

## 3. Estado actual

Esto es de dónde partimos — equipo, presupuesto, qué ya está en movimiento, qué está estancado, puntuado contra la rúbrica de 17 secciones de la Auditoría de Marketing CF.

### Composición del equipo (superficie de marketing)

| Persona | Rol | Superficie de marketing |
|---|---|---|
| **Alex** | Co-founder, CEO | Posee: LinkedIn personal, eventos en vivo, ventas B2B, narrativa del founder, relaciones con inversionistas, autoría de la voz de marca |
| **Sam** | Co-founder, CXO | Posee: credibilidad clínica/somática, custodia de la voz de marca, ángulo somático en la revisión de copy, red de practicantes |
| **Devon** | Lead Dev | Posee: build de producto/UI, instrumentación, conexión de eventos de Customer.io, despliegue de App Store |
| **Ed Dorsey** | Advisor de Diseño | Cadencia de asesoría (ex-Apple/Airbnb/Strava) |
| **Emily Babich** | Estrategia Creativa | Cadencia de asesoría |
| **Matt Mikkelsen** | Grabación de Campo | Librería de audio, no marketing |
| **Casey Reed** | fCMO | Estrategia, lifecycle, SEO, pruebas de onboarding, contenido, programa de ambassador, stack de operaciones |

**No hay todavía una contratación dedicada de marketing.** La primera contratación probablemente sea post-cierre-de-seed (candidata para Q3 2026): un manager de lifecycle + content marketing que posea Customer.io, la producción de contenido SEO, y las operaciones de ambassador día a día.

### Presupuesto de marketing (actual)

- **Adquisición pagada:** $0. Confirmado por Alex, 2026-05-20: *"UA de D2C hasta ahora: Mis posts personales de LinkedIn, eventos en vivo de Quietude, boca a boca orgánico, y descubrimiento orgánico en app store."* No hay capa pagada.
- **Stack de herramientas:** Suscripción de Customer.io, Shopify (storefront del antifaz), App Store Connect, GA4 (o pendiente), Stripe, Notion, Dub.co (atribución de ambassador). Estimado ~$500–1,500/mes combinado.
- **Retainer de fCMO:** Engagement de Casey Reed.
- **PR:** Sin PR pagado. Tracción orgánica de influencer de longevidad, angels de tech de consumo + red de laboratorios de modelos fundacionales.

**Implicación:** El plan a 90 días debe producir ganancias sin activar ninguna palanca pagada. Todo en las próximas 12 semanas es orgánico, de lifecycle, o a nivel de producto. El pago es un desbloqueo de Q2–Q3.

### Qué ya está hecho (reconocer, luego construir encima)

| Activo | Estado | Apalancamiento de marketing |
|---|---|---|
| Estudio peer-reviewed de psicofisiología (2025) | Publicado | Ancla de autoridad clínica. El activo más submercadeado que posee Quietude. |
| Endorsement del antifaz por influencer de longevidad | Vivo, generando ventas en Shopify | Gancho de prensa. Subutilizado para prueba social en landing pages. |
| Inversión de angels de tech de consumo + laboratorio de modelos fundacionales | Cerrado | Oportunidad de PR de inversionistas. Piezas de Substack/Medium tipo "Por qué invertí." |
| 15K+ participantes de eventos en vivo a lo largo de una década | Real | Potencial de lista de email, pool de ambassadors, banco de testimonios, referencia B2B. |
| Antifaz Quietude (5K en inventario) | Vendiéndose | El producto cuña. Ruta de activación hardware → app. |
| 38% de retención a 12 meses (vs. promedio de categoría de 20%) | Real | Métrica destacada. Pertenece en todas partes. |
| Integración de Customer.io + Shopify | Conectada | La infraestructura de lifecycle existe. Los flujos solo necesitan publicarse. |
| 4 repos de GitHub para contexto + producto | Configurados | `quietude-context` (cerebro compartido), `quietude-promo`, `quietude-app` (app), `mira` (IA), `quietude-api` |
| Documento de Sound Philosophy de Alex | Documento de trabajo | Position paper enlazable una vez pulido y publicado. |
| ~5 ambassadors inbound esperando | Inbound | Programa de referidos listo para lanzar — sin necesidad de generación de demanda para v1. |
| Instalación B2B de Aurora (~€250K, deadline de julio) | En curso | Primer venue insignia. Caso de referencia una vez instalado. |
| Directorio de Conocimiento de Notion | Vivo | Contexto interno. |
| MCP de Customer.io (integración con Claude) | Validado en el kickoff | El equipo no técnico puede publicar flujos de forma independiente. |

### Qué está en curso (borrado pero no publicado)

| Elemento | Estado | Bloqueador |
|---|---|---|
| Flow 2 — Onboarding de la App (8 emails / 14 días) | Borrador | UI de la app en flujo; el copy referencia pantallas que podrían cambiar |
| Flow 4 — Reenganche de Usuario Inactivo (5 emails / 38 días) | Borrador | Ninguno — listo para publicar |
| Flow 6 — Post-Compra del Antifaz | Borrador | Ninguno — listo para publicar |
| Reconstrucción del onboarding (plan de prueba de 3 variantes) | Documento de estrategia listo | Alcance de ingeniería + remoción del gate de audífonos |
| Plan de SEO a 90 días + investigación de keywords | Listo | Esperando decisión de consolidación de dominio + inicio de producción de contenido |

### Qué está estancado (y necesita desatorarse este trimestre)

| Problema | Costo de la inacción | Acción |
|---|---|---|
| Gate duro de audífonos en el onboarding | Caída de conversión confirmada post-lanzamiento | Matarlo esta semana (corrección de base) |
| 4 dominios sin consolidar (quietude.app, quietude.space, quietude.audio, quietude.center) | Fragmentación de autoridad SEO, confusión de emails transaccionales | Consolidar a `quietude.app` según los datos de SEO |
| Copy del listado de App Store fuera de la voz de marca | La superficie de mayor tráfico de Quietude; experiencia fuera de marca para usuarios que llegan | Reescribir en voz (Pilar 1) |
| La consolidación de dominio requiere plan de 301s + migración del remitente de email | Riesgo de pérdida de tráfico si se maneja mal | Planificar en semanas 1–2, ejecutar en semanas 3–4 |
| El repo `quietude-promo` no se ha publicado desde marzo de 2026 | El sitio de marketing está desactualizado | Confirmar si está vivo; reescribir o reemplazar |
| 29% de churn mensual de App Store vs. reclamo de retención de 38% a 12 meses | Discordancia en la definición de la métrica confundiendo al equipo | Reconciliar con Devon + datos de Customer.io |
| Alcance de la reflexión post-sesión de Mira desconocido | Bloquea la Variante B y la Variante C de las pruebas de onboarding | Resolver con Devon |

### Captura de la rúbrica de auditoría (17 secciones)

Puntuada de 0 a 5 a partir del material, usando la rúbrica embebida en `references/current-state-rubric.md`. Marcada "puntuada a partir de material" en lugar de "auditoría formal" — Alex puede cuestionar cualquier puntaje donde tenga mejores datos.

| # | Sección | Puntaje | Nota |
|---|---|---|---|
| 1 | Posicionamiento | **4** | Reclamo de categoría claro, original. El marco bottom-up es la pieza más fuerte. Necesita articulación externa más amplia. |
| 2 | Investigación de clientes | **4** | Investigación profunda liderada por el founder, una década de participantes en vivo. Podría capturarse más sistemáticamente. |
| 3 | Homepage | **2** | `quietude-promo` no se ha publicado desde marzo. Voz fuera de marca en algunos lugares. |
| 4 | Páginas de ventas / producto | **2** | La página del antifaz existe en Shopify pero no está optimizada para SEO ni narrativa de ventas. No hay landing page de producto-app en la voz de marca. |
| 5 | Páginas de conversión | **2** | `/partner` existe en `quietude.app`. No hay `/science`, `/eye-mask`, `/ambassadors`, `/guides` vivas. |
| 6 | Comparación con competidores | **1** | No existe nada. Gran oportunidad de SEO + ventas (poseer los SERPs "Quietude vs. Calm/Headspace/Brain.fm/Endel"). |
| 7 | Recursos / contenido | **1** | Sound Philosophy aún no es público. El estudio peer-reviewed de psicofisiología aún no tiene página dedicada. Sin blog. |
| 8 | Onboarding | **2** | El gate de audífonos está matando la conversión. Proyecto de retener-y-arreglar este trimestre. |
| 9 | Lifecycle de email | **1** | Los tres flujos están borrados, ninguno vivo. Orden de publicación fijado. |
| 10 | Material de ventas | **3** | El seed deck es sólido (de cara a inversionistas). El material de ventas B2B está más liderado por el founder que por activos. |
| 11 | Mensajería | **5** | Alex + Sam han creado la voz de marca más distintiva en la categoría de bienestar. Esto es un moat. |
| 12 | Pricing | **3** | $30/mes la app, $45 el antifaz, $7,500 los speakers, $50–200K B2B. No se ha puesto a prueba para lift de conversión D2C. |
| 13 | CRO | **2** | La tasa de conversión de App Store es rastreable pero sin historial A/B. El gate de audífonos es la primera remoción de prueba obvia. |
| 14 | GTM / lanzamientos | **2** | App en beta con throttling. Los lanzamientos mayores (antifaz, Mira público) no han tenido GTM estructurado. |
| 15 | Ads | **0** | Sin capa pagada. Refleja la estrategia orgánica actual — no una debilidad, pero el desbloqueo de presupuesto hará que esto se mueva. |
| 16 | SEO | **1** | Estado actual: 7 visitas orgánicas/mes. El plan existe; la ejecución aún no ha empezado. |
| 17 | Internacionalización | **1** | Sede en Finlandia + ICP global, pero copy solo en EN y centrado en US. Aplazar hasta Q4+. |

**Total: 36 / 85 (42%).** La forma importa más que el puntaje: alto en Posicionamiento + Mensajería + Investigación de clientes, bajo en Páginas de conversión + Lifecycle de email + SEO + Recursos + Ads. Esa es la brecha que este plan cierra.

---

## 4. Adquisición

> *"¿Cómo se vuelven conscientes de Quietude los desconocidos?"*

### Estado actual

100% orgánico. Cuatro canales reales: LinkedIn personal de Alex, eventos en vivo de Quietude, boca a boca orgánico, descubrimiento orgánico en App Store. Más el impulso pasivo de PR del endorsement de influencer de longevidad + el estudio clínico.

Esto son buenas noticias, no malas. Cada dólar de ingreso ganado hasta la fecha se ha ganado sin adquisición pagada. La barra a superar no es alta; el upside encima de una base orgánica es significativo.

### El plan

**Canal 1 — SEO (inversión primaria a 90 días).**
El plan completo a 90 días vive en `seo/plan.md`. Resumen: consolidar a `quietude.app`, apuntar a tres clusters asimétricos (regulación del sistema nervioso KD 14–32, antifaz de dormir con peso/blackout KD 6–30, WELL + club social de bienestar B2B KD 5–34), publicar 4 pilares de contenido. Meta a 90 días: 500–1,500 visitas orgánicas/mes, 80+ keywords posicionadas. Meta a 12 meses: 10,000/mes, 1,000+ keywords.

**Canal 2 — Optimización de App Store (el activo no-sitio de mayor apalancamiento).**
El listado de App Store es actualmente la URL de Quietude más visitada por el algoritmo de Apple. Arreglar el copy tiene más apalancamiento este trimestre que arreglar el sitio de marketing. Reescribir en la voz de marca. Agregar el marco meditación-vs-regulación. Liderar con el ancla clínica. Probar variaciones de capturas de pantalla.

**Canal 3 — LinkedIn de Alex (productizar el canal).**
Hoy es publicación ad hoc del founder. La siguiente movida es estructurarlo: una cadencia de 2–3x/semana, categorías de post que mapean a los pilares de contenido (sistema nervioso, ciencia del sonido, viaje del founder, evidencia clínica, detrás de cámaras), enlaces rastreables vía Dub, funnel de seguidor → suscriptor de email → instalación de app medido. Esta es la voz de Alex — el canal solo funciona si él es quien escribe. La programación con fCMO + Typefully hace la cadencia sostenible.

**Canal 4 — Amplificación de PR.**
La tracción del influencer de longevidad es real pero subutilizada en superficies propias. Agregar una página `/notable-users` o `/in-the-press`. Presentar el estudio peer-reviewed de psicofisiología a 5 medios (prensa de bienestar: Well+Good, MindBodyGreen; tech-adyacente: Wired con el gancho del influencer de longevidad; mainstream: Outside, Forbes Wellness). Respuestas a HARO/Help-A-B2B-Writer citando los datos de Quietude. Momentos de PR de inversionistas (piezas de Substack "Por qué invertí en Quietude" de los angels de tech de consumo — impulsar para que estos incluyan backlinks).

**Canal 5 — Instrumentación de evento-a-app.**
Los eventos en vivo son la exposición ICP de mayor conversión que tiene Quietude (15K+ participantes, una década de confianza). No están instrumentados. Agregar: código QR por evento → instalación de app + captura de email, lifecycle post-evento (¿Customer.io Flow 7?), tracking de ROI de evento. Meta: convertir un evento de un momento de conversión de una noche a un funnel de 30 días.

**Canal 6 — Cuña del antifaz (producto de entrada de consumo).**
5K antifaces en inventario. El storefront de Shopify existe pero no está optimizado. Mejoras: optimizar la página de producto para SEO (apuntar a "antifaz de dormir con peso," "antifaz blackout," "antifaz de seda"), agregar reseñas vía Judge.me (según decisión del kickoff), política de devolución de 30 días (expectativa del mercado US, según kickoff), construir el listicle ("Quietude vs. Manta vs. Nodpod vs. Lumon"). Considerar el listado en Amazon como una jugada de distribución v2.

**Canal 7 — Instalaciones B2B en venues (mantenido lean según el kickoff).**
Alex posee esto. Marketing apoya con: casos de estudio después de cada instalación, reescritura de la página `/partner` en voz (ya existe en quietude.app), contenido del Pilar 4 ("La Función de Sonido que Falta en WELL"), enlaces recíprocos de venues partner integrados en los contratos.

**Canal 8 — Capa pagada (desbloqueada post-cierre-de-seed).**
Retenida hasta que aterrice el financiamiento de seed. Presupuesto de prueba inicial: $5–10K/mes dividido entre Apple Search Ads (mayor intención para App Store), Meta (Instagram + Facebook para el antifaz), LinkedIn (compradores de venues B2B). No activar hasta que: (a) se publique la corrección de base del onboarding, (b) el Flow 6 esté vivo, (c) al menos una landing page de Pilar esté en voz. El pago amplifica lo que ya funciona — el pago prematuro amplifica lo que está roto.

### Movidas de adquisición a 90 días

- Semanas 1–2: Decisión de consolidación de dominio + plan de 301s. Primera pasada de la reescritura del listado de App Store.
- Semanas 3–4: 301s de dominio ejecutados. Migración de GSC. Hub del Pilar 1 de SEO borrado.
- Semanas 5–8: Hub del Pilar 1 + 3 spokes publicados. Hub del Pilar 2 (Antifaz) + listicle publicados. Cadencia de LinkedIn de Alex operacionalizada vía Typefully. El estudio peer-reviewed de psicofisiología aterriza en una página `/science` dedicada.
- Semanas 9–12: Cornerstone del Pilar 4 (WELL/B2B) publicado. Sound Philosophy se hace público en `/research/sound-philosophy`. Primer impulso de PR: presentar el estudio + el gancho del influencer de longevidad a 5 medios.

### Perspectiva de adquisición a 12 meses

- Q1 (Meses 1–3): Fundación. Pilares de SEO sembrados. Reescritura de App Store publicada. Cadencia de LinkedIn estable. Impulso de PR lanzado.
- Q2 (Meses 4–6, post-cierre-de-seed): Piloto de adquisición pagada a $5–10K/mes. Composición de SEO — el Pilar 1 posicionando. Primer caso de referencia de instalación B2B vivo.
- Q3 (Meses 7–9): El pago escala a $20–30K/mes si la unit economics se sostiene. Los cuatro pilares produciendo. La app llega a GA — nuevo momento GTM.
- Q4 (Meses 10–12): Canales de composición vivos. 50+ piezas de contenido de pilares. Primer piloto del programa Quietude Guides creando SEO local + prensa ganada.

### Skills + herramientas

- **Skills:** `seo-audit`, `ai-seo`, `programmatic-seo`, `schema-markup`, `content-strategy`, `competitor-alternatives`, `launch-strategy`, `paid-ads`, `ad-creative`, `social`, `typefully`, `analytics-tracking`, `copywriting`, `marketing-website-design`, `free-tool-strategy`
- **MCPs / APIs:** API de Ahrefs, API de DataForSEO, Typefully MCP (programación de LinkedIn), GA4 MCP (cuando esté conectado), GitHub MCP (trabajo en el repo `quietude-promo`), Notion (directorio de conocimiento), Stripe MCP (matemáticas de LTV / CAC pagado), `agent-browser` (redacción y pruebas de LinkedIn), `defuddle` (investigación)

---

## 5. Activación

> *"Una vez que alguien prueba Quietude, ¿tiene una experiencia que convierte?"*

### Estado actual

Día 1 → pago: **1.34%**. Día 7 → pago: **3.73%**. Día 35 → pago: **5.46%**. *La forma del funnel es la señal.* El lift de ~4× a lo largo de 35 días significa que el producto convierte dado tiempo y contacto — ambos socavados por el onboarding actual y aún no provistos por la capa de lifecycle.

Advertencias: la app está en beta con throttling. Las métricas son ruidosas. No optimizar contra absolutos; optimizar contra la *forma* del funnel y la *comparación de cohortes*.

### El plan

**Movida 1 — Matar el gate duro de audífonos (corrección de base, esta semana).**
Caída de conversión confirmada después de que se publicó el gate. La corrección no es mejor copy en el gate — es eliminar el gate. Reemplazar con detección pasiva de audífonos + un nudge suave de una línea. Cambio sin arrepentimiento. Razonamiento completo en `onboarding-recommendation.md`.

**Movida 2 — Correr la prueba de onboarding de tres variantes.**
Tres variantes, cada una una expresión pura de una creencia sobre qué impulsa la activación en este ICP:
- **Variante 1 — Confianza Primero.** Promesa audaz + ancla clínica + muro de testimonios + mecanismo de 1 línea. Prueba si el ICP saturado necesita encuadre antes de invertir.
- **Variante 2 — Ser Visto Primero.** Diagnóstico multi-paso → resumen "te vemos" generado por IA → sesión personalizada. Prueba si ser nombrado con precisión es el evento de conversión.
- **Variante 3 — Sentir Primero.** El audio empieza al abrir la app. ~15 palabras en pantalla. La sesión ES el onboarding. Prueba si el producto puede sostenerlo en frío.

Secuencia de prueba (secuencial, ~7 semanas hasta un ganador): línea base de la corrección de base → V3 vs. línea base → ganadora vs. V1 → ganadora vs. V2. Sistema completo en `onboarding-recommendation.md`.

**Movida 3 — Reescritura del listado de App Store.**
El activo no-sitio de mayor apalancamiento. Reescribir en voz de marca. Liderar con meditación-vs-regulación. Variaciones de capturas de pantalla para probar. Esto también es una movida de Adquisición (descubrimiento orgánico) pero vive aquí porque es el umbral hacia el trial.

**Movida 4 — Flow 2 de Customer.io (retenido hasta que la UI esté estable).**
La secuencia de 8 emails / 14 días de onboarding está borrada y en marca. Se retiene la publicación porque los emails referencian pantallas in-app que cambiarán durante la reconstrucción del onboarding. Una vez que una variante ganadora de onboarding se publique, el Flow 2 recibe una actualización de copy contra la UI final y se publica.

**Movida 5 — Revisión de paywall + pricing (cruza con Ingresos).**
¿Cuál es la estructura actual del trial? ¿Duración, disparador del paywall, pricing de introducción? Cuando la forma del funnel es "lift a lo largo de 35 días," extender el trial podría convertir mejor que gatear agresivamente antes. A auditar en Q1.

### Movidas de activación a 90 días

- Semana 1: Gate de audífonos eliminado. Línea base establecida.
- Semanas 2–3: Variante 3 (Sentir Primero) prototipada, instrumentada, publicada a una cohorte de prueba.
- Semanas 4–5: Lectura de Variante 3 vs. línea base. Decidir publicar/iterar. Comenzar la construcción de la Variante 1.
- Semanas 6–7: Variante 1 (Confianza Primero) en vivo.
- Semanas 8–9: Lectura de V1 vs. ganadora. Comenzar la construcción de la Variante 2.
- Semanas 10–11: Variante 2 (Ser Visto Primero) en vivo.
- Semana 12: Lectura final. Variante ganadora programada para publicación permanente. Flow 2 desbloqueado.

### Perspectiva de activación a 12 meses

- Q1: Variante ganadora identificada y publicada.
- Q2: El Flow 2 se publica. Comienzan las pruebas A/B de paywall.
- Q3: Lanzamiento GA — onboarding re-validado a mayor tráfico. La segmentación de cohorte por fuente de adquisición (Shopify/antifaz vs. directo vs. ambassador vs. pagado) empieza a impulsar bifurcaciones de variante.
- Q4: El onboarding ya no es el cuello de botella. El enfoque se mueve a la transición Activación → Retención (sesiones 2–7).

### Skills + herramientas

- **Skills:** `onboarding-cro`, `signup-flow-cro`, `page-cro`, `paywall-upgrade-cro`, `popup-cro`, `copywriting`, `copy-editing`, `copycraft`, `marketing-website-design`, `ab-test-setup`, `marketing-psychology`
- **MCPs / APIs:** App Store Connect (manual + `dev-browser` para automatización de capturas), GitHub MCP (repo de app `quietude-app` para código de onboarding), Figma / Pencil MCP (para diseño de pantallas de onboarding), Customer.io MCP (para cualquier coordinación in-app/email), GA4 MCP (eventos de activación)

---

## 6. Retención

> *"Una vez que alguien convierte, ¿se queda — y profundiza?"*

### Estado actual

**Métrica destacada (según el seed deck): 38% de retención a 12 meses** — casi el doble del promedio de la categoría (~20%). Esta es la señal de retención más fuerte del deck y una de las afirmaciones más submercadeadas que posee Quietude.

**Captura de App Store, 2026-05-16:** 145 pagados, 42 con churn (~29% de churn mensual). Discordancia de definición con el reclamo del 38%. A reconciliar. Posiblemente: el 38% es retención de cohorte anual (personas que pagaron el mes 1 y siguen pagando el mes 12), el 29% es churn bruto mensual (personas que pagaron este mes y no pagaron el siguiente). Ambos pueden ser ciertos. Hay que aclarar qué métrica se reporta externamente y cuál es la señal real de salud del producto.

### El plan

**Movida 1 — Publicar el Flow 6 primero (Post-Compra del Antifaz).**
Según la decisión del kickoff y el documento onboarding-recommendation: este es el flujo listo para publicar. Anclado en hardware, no referencia pantallas in-app, puede publicarse hoy. Conecta la ruta de activación hardware → app (los compradores del antifaz deberían recibir un trial gratuito de 6 meses de Premium — formalizar esto como parte del flujo).

**Movida 2 — Publicar el Flow 4 segundo (Reenganche de Usuario Inactivo).**
Cinco emails a lo largo de 38 días. El lenguaje es universal — no depende del estado de la UI de la app. Publicar después de que el Flow 6 esté vivo.

**Movida 3 — Retener el Flow 2 (Onboarding).**
Ocho emails a lo largo de 14 días. Se retiene hasta que la UI de la app se estabilice post-reconstrucción-de-onboarding. No publicar copy que necesitará reescribirse en 8 semanas.

**Movida 4 — Centro de suscripción de Customer.io con temas de opt-in.**
Según la decisión del kickoff. Temas: eventos, actualizaciones de la app, somática y sistema nervioso, promociones del antifaz. Los usuarios se auto-segmentan. Mejora la entregabilidad (tasas de queja más bajas) y le da al lifecycle una superficie de segmentación más rica.

**Movida 5 — Reflexión post-sesión de Mira (cuando se defina el alcance).**
La movida de retención más poderosa a mediano plazo. Después de una sesión, Mira pregunta *"¿Qué notaste?"* Chips preestablecidos opcionales + texto libre. Dos beneficios: (a) le da a Mira priors para personalización desde la sesión 2+, (b) las respuestas de reflexión se convierten en una mina de oro de contenido + segmentación para el equipo. Pregunta de alcance para Devon — ¿Mira actualmente soporta esto, o es un build nuevo?

**Movida 6 — Flujo de activación hardware → app.**
La ruta de comprador-del-antifaz-se-convierte-en-suscriptor-Premium está insinuada en el seed deck (CAC blended vía hardware) pero no es visible en el dashboard de App Store. Auditar el flujo existente: ¿una compra en Shopify del antifaz realmente entrega un código Premium gratuito? ¿Cómo se canjea? ¿Cuál es la tasa de conversión? Esto es fundacional para la tesis de "cuña B2C."

**Movida 7 — Reconciliar la métrica de retención.**
¿Cuál es la definición real de "38% de retención a 12 meses"? ¿Cohorte? ¿Tipo de plan (mensual vs. anual)? Sobrevive esto incluso si la respuesta es incómoda — el equipo y los inversionistas necesitan estar hablando de la misma métrica.

**Movida 8 — Plan anual como default (cruza con Ingresos).**
Patrón de la industria: hacer que el default sea anual reduce la ansiedad de churn y mejora el LTV. A probar en Q2.

### Movidas de retención a 90 días

- Semanas 1–2: El Flow 6 (post-compra del antifaz) se publica. Se abordan correcciones de la revisión del kickoff (salto de línea del enlace del estudio, footer de CAN-SPAM, firma de burbuja con la cara del founder, reseñas de Judge.me).
- Semanas 3–4: El Flow 4 (reenganche de usuario inactivo) se publica.
- Semanas 5–6: El centro de suscripción de Customer.io se construye y se publica.
- Semanas 7–8: El flujo de activación hardware → app se audita y se documenta. Se arreglan las fugas.
- Semanas 9–10: Reconciliación de la métrica de retención (con Devon).
- Semanas 11–12: Campaña de win-back para la cohorte con churn — probar copy de reactivación.

### Perspectiva de retención a 12 meses

- Q1: Flows 6 + 4 disparando. Centro de suscripción vivo.
- Q2: El Flow 2 se publica (post-reconstrucción-de-onboarding). Reflexión post-sesión de Mira en producción. Default de plan anual probado.
- Q3: Lanzamiento GA — métricas de retención re-establecidas a mayor volumen. Flujos de lifecycle basados en cohorte (antifaz vs. instalación directa de la app).
- Q4: Lifecycle completo compuesto. La retención ya no es una de las tres preocupaciones principales — el enfoque se mueve a Referidos e Ingresos.

### Skills + herramientas

- **Skills:** `email-sequence`, `churn-prevention`, `copywriting`, `copy-editing`, `paywall-upgrade-cro`, `ab-test-setup`
- **MCPs / APIs:** **MCP de Customer.io** (validado en el kickoff — el equipo no técnico puede publicar flujos), Shopify (compradores del antifaz como fuente de eventos), Stripe MCP (estado de suscripción, extracciones de cohorte de churn), GA4 MCP (eventos de sesión, curvas de retención)

---

## 7. Referidos

> *"¿Los usuarios retenidos traen más usuarios — y a qué costo?"*

### Estado actual

~5 ambassadors inbound esperando (según el kickoff). Dub.co configurado. Aún no hay un programa formal. El boca a boca ocurre naturalmente según el desglose de UA de Alex.

Este es uno de los indicadores líderes más fuertes en el negocio: 5 personas no afiliadas han levantado la mano pidiendo llevar Quietude a su red *antes de que exista ningún programa*. Esa señal no aparece en apps con product-market fit más débil.

### El plan

**Movida 1 — Lanzar el programa de ambassador con los 5 inbound.**
Tier 1 del programa. Landing pages por ambassador (p. ej., `quietude.app/with/sarah`). Dub.co rastrea la atribución. Estructura de comisión por determinar (según el kickoff, $/suscripción o rev-share TBD). Lanzamiento suave con los 5 — tratar como cohorte piloto, recolectar feedback, refinar antes de abrir aplicaciones.

**Movida 2 — Construir el momento de compartir-después-del-cambio.**
La reflexión post-sesión de Mira (ver Retención) es el momento natural para exponer un prompt de compartir. Después de que un usuario reporte un cambio sentido, ofrecer: *"¿Quieres compartir Quietude con alguien que lo necesite?"* Una sola línea, nunca insistente. El mecanismo de boca a boca más poderoso: flujo de regalar-un-mes donde el destinatario recibe una introducción con descuento o gratis.

**Movida 3 — Amplificación del founder (Alex + Sam como ambassador-cero).**
Alex mencionando el engagement de fCMO en pitches de fundraising (permiso otorgado). Menciones recíprocas en contenido del lado del fCMO. La red clínica de Sam → pool de ambassadors de practicantes.

**Movida 4 — Piloto de certificación de Quietude Guides (largo plazo, Q3+).**
El programa Guides es la composición de referidos de Fase 2 (según el seed deck). 500–1,000 Guides a través de 50+ ciudades para el Año 3–5. Primer piloto de certificación: 3–5 hosts que corren sesiones en vivo, obtienen un rev-share + co-marketing. Construye SEO local + prensa ganada + flywheel de ambassador-de-ambassadors. Retener hasta que el pago + lifecycle estén disparando — Guides es un build de múltiples trimestres.

**Movida 5 — Flujo de regalo del antifaz.**
El referido de hardware es raro y poderoso. *"Envíale a un amigo un antifaz Quietude. Recibe el antifaz + 3 meses gratis de Premium. Tú recibes un crédito hacia tu próxima cosa."* Las ventanas pico de temporada de regalos/vacaciones son la prueba.

### Movidas de referidos a 90 días

- Semanas 1–4: Programa de ambassador definido en alcance, estructura de comisión decidida, plantilla de landing page por ambassador construida, 5 inbound incorporados.
- Semanas 5–8: Primeras ventas impulsadas por ambassador rastreadas vía Dub. Flujo de atribución y pago validado.
- Semanas 9–12: Se abren aplicaciones para los siguientes 10–15 ambassadors. Comienza la definición de alcance de Quietude Guides.

### Perspectiva de referidos a 12 meses

- Q1: Programa de ambassador vivo con 5–10 activos.
- Q2: 15–25 ambassadors activos. Momento de compartir-después-del-cambio en producción (post-reflexión de Mira).
- Q3: Piloto de certificación de Guides lanzado (3–5 hosts). Flujo de regalo del antifaz vivo para el pico de vacaciones.
- Q4: 50+ ambassadors + 5–10 Guides. Referidos impulsando 15–25% de las nuevas suscripciones D2C.

### Skills + herramientas

- **Skills:** `referral-program`, `social`, `copywriting`, `marketing-website-design` (landing pages por ambassador)
- **MCPs / APIs:** Dub.co (atribución — ya en el stack), Stripe MCP (contabilidad de comisiones + pagos), GitHub MCP (despliegue de landing pages en `quietude-promo` o un repo nuevo `quietude-ambassadors`), Customer.io MCP (lifecycle de ambassador: onboarding, resumen mensual de desempeño, notificación de pago)

---

## 8. Ingresos

> *"¿Qué cobramos, quién paga, y cómo compone eso?"*

### Estado actual

| Producto | Precio | Señal de volumen |
|---|---|---|
| App Quietude + Mira | ~$30/mes | 145 suscripciones pagadas (captura de App Store 2026-05-16) |
| Antifaz Quietude | ~$45 | 5K en inventario, ventas impulsadas por PR del influencer de longevidad |
| Audio Quietude (speakers) | ~$7,500 | Nicho, liderado por el founder |
| Espacios Quietude (instalación B2B) | $50–200K | Insignia de Aurora en curso (~€250K), pipeline de 4 venues |
| Experiencias Quietude (eventos) | Varía | 15K+ participantes históricos |
| Guides Quietude | Rev share | Aún no operativo |

**Ingreso a la fecha: ~$500K sobre ~$250K levantados.** Eficiente en capital. Hardware + B2B + suscripciones de app contribuyendo todos.

**MRR (captura de App Store): $592.** Con throttling de beta, no en estado estable. Las matemáticas implícitas de ~$4/suscripción/mes contra el precio listado de $30/mes sugieren fuerte adopción de plan anual (lo que comprime el ingreso mensual pero mejora el LTV) o descuentos promocionales significativos — a reconciliar con Alex.

### El plan

**Movida 1 — Auditoría de pricing.**
¿Qué se está cobrando realmente hoy? ¿Precio listado, mezcla de planes común, pricing de introducción, ofertas de recuperación de churn? Las matemáticas implícitas de $4/suscripción/mes no cuentan una historia limpia — se necesita la verdad de fondo antes de recomendar cambios.

**Movida 2 — Plan anual como default (prueba).**
Patrón de la industria, cruza referencia con Retención. A probar en Q2.

**Movida 3 — Bundling hardware → app formalizado.**
Según el encuadre de negocio-de-eventos-partner en el seed deck: el CAC blended vía hardware → suscripción de app es la jugada. Hoy, ¿un comprador del antifaz recibe qué, exactamente? ¿Premium gratis? ¿Código de trial? Auditar + formalizar. El antifaz es la cuña; la app es el LTV.

**Movida 4 — Optimización del storefront de Shopify del antifaz.**
La página actual tiene un rendimiento menor a su potencial. Agregar: targeting de SEO ("antifaz de dormir con peso," "antifaz blackout"), reseñas de Judge.me (decisión del kickoff), política de devolución de 30 días (decisión del kickoff), flujo de upsell hacia la app Premium.

**Movida 5 — Considerar un listado en Amazon para el antifaz.**
Amazon se lleva margen pero es su propio motor de descubrimiento. Probar como distribución v2 si el volumen de Shopify lo valida.

**Movida 6 — Casos de estudio B2B + material de ventas.**
Alex posee las ventas B2B pero marketing apoya con: casos de estudio post-instalación (Aurora como el insignia), reescritura de la página `/partner` en voz, contenido SEO del Pilar 4. Cada instalación B2B es un multiplicador de ~$430K/año recurrente + caso de referencia.

**Movida 7 — Licenciamiento de datos (largo plazo, marcar para el stack de operaciones).**
Según el pool de valor Y10–15 del seed deck: $100–160M/año. No es ingreso inmediato. Pertenece a la agenda estratégica a 24 meses. Marcado aquí para no perderlo de vista.

### Movidas de ingresos a 90 días

- Semanas 1–2: Auditoría de pricing. Reconciliar el MRR implícito vs. el listado.
- Semanas 3–4: Flujo de activación hardware → app auditado (también movida de Retención 6).
- Semanas 5–8: Reescritura de la página de Shopify del antifaz + optimización SEO + Judge.me + política de devolución. Caso de estudio de Aurora preparado para post-instalación.
- Semanas 9–12: Prueba de default de plan anual definida en alcance.

### Perspectiva de ingresos a 12 meses

- Q1: Cierra la auditoría de pricing. Activación hardware → app formalizada.
- Q2: Prueba de default de plan anual en vivo. El Shopify del antifaz produciendo lift medible.
- Q3: Casos de estudio de instalación B2B (1–2) publicados. Lanzamiento GA + consideración de nuevo nivel de pricing (¿un plan de nivel superior con más Mira?).
- Q4: Pricing optimizado vía resultados de pruebas. CAC blended hardware → app rastreado y reportado. Primeros números sobre la tesis de licenciamiento de datos (aún muy temprano).

### Skills + herramientas

- **Skills:** `pricing-strategy`, `paywall-upgrade-cro`, `sales-enablement`, `revops`, `ab-test-setup`, `copywriting`
- **MCPs / APIs:** Stripe MCP (pruebas de pricing, analítica de suscripción, cohorte de churn, matemáticas de CAC blended), Customer.io MCP (lifecycle relacionado con paywall), Shopify (transacciones del antifaz), GA4 MCP (eventos de ingresos), Notion (directorio de conocimiento comercial)

---

## 9. Roadmap a 90 días

Capa de ejecución táctica. Cada elemento está etiquetado con AARRR para que la prioridad sea visible.

### Semanas 1–2 — Desbloquear

| Movida | Etapa | Owner |
|---|---|---|
| Matar el gate duro de audífonos | Activación | Casey + Devon |
| Decisión de consolidación de dominio documentada | Adquisición | Casey + Alex |
| Plan de 301s borrado (página por página) | Adquisición | Casey |
| Reescritura del listado de App Store — primera pasada | Activación + Adquisición | Casey + Alex + Sam (revisión de voz) |
| El Flow 6 (post-compra del antifaz) se publica | Retención | Casey + MCP de Customer.io |
| Documento de definición de alcance del programa de ambassador | Referidos | Casey |
| Auditoría de pricing iniciada | Ingresos | Casey + Alex |

### Semanas 3–4 — Fundación

| Movida | Etapa | Owner |
|---|---|---|
| 301s de consolidación de dominio ejecutados | Adquisición | Devon + Casey |
| GSC + GA4 configurados en `quietude.app` | Adquisición | Casey |
| Hub del Pilar 1 de SEO borrado (Regulación del Sistema Nervioso) | Adquisición | Casey |
| Hub `/science` construido con el estudio peer-reviewed de psicofisiología | Adquisición + marca | Casey + Sam |
| Variante 3 (Sentir Primero) de onboarding prototipada + probada | Activación | Casey + Devon |
| El Flow 4 (usuario inactivo) se publica | Retención | Casey |
| Programa de ambassador: 5 inbound incorporados | Referidos | Casey |
| Flujo de activación hardware → app auditado | Retención + Ingresos | Casey + Devon |
| Reescritura del listado de App Store — final + publicado | Activación + Adquisición | Alex + Sam + Casey |

### Semanas 5–8 — Velocidad

| Movida | Etapa | Owner |
|---|---|---|
| Hub del Pilar 1 + 3 spokes publicados | Adquisición | Casey |
| Hub del Pilar 2 (Antifaz) + listicle publicados | Adquisición | Casey |
| Cadencia de LinkedIn de Alex operacionalizada (Typefully) | Adquisición | Alex + Casey |
| Primer impulso de PR: estudio + gancho del influencer de longevidad a 5 medios | Adquisición | Casey + Alex |
| Lectura de Variante 3; publicar o iterar | Activación | Casey |
| Variante 1 (Confianza Primero) prototipada + probada | Activación | Casey + Devon |
| Centro de suscripción de Customer.io construido | Retención | Casey |
| Reescritura del storefront de Shopify del antifaz (SEO + reseñas + devolución) | Adquisición + Ingresos | Casey + Alex |
| Primera atribución de ambassador verificada vía Dub | Referidos | Casey |

### Semanas 9–12 — Composición

| Movida | Etapa | Owner |
|---|---|---|
| Cornerstone del Pilar 4 (WELL/B2B) publicado | Adquisición | Casey |
| 3 spokes más del Pilar 1 publicados | Adquisición | Casey |
| Sound Philosophy publicado en `/research/sound-philosophy` | Adquisición + marca | Alex + Casey |
| Lectura de Variante 1; comienza la construcción de la Variante 2 (Mira-dependiente) | Activación | Casey + Devon |
| Campaña de win-back para la cohorte con churn | Retención | Casey |
| Prueba de default de plan anual definida en alcance | Ingresos | Casey + Alex |
| Se abren aplicaciones de ambassador para los siguientes 10–15 | Referidos | Casey |
| Revisión a 90 días + recalibración del plan de Q2 | Transversal | Casey + Alex |

---

## 10. Perspectiva a 12 meses

Hitos trimestrales con desbloqueos de capacidad por etapa de financiamiento nombrados explícitamente.

### Q1 — Meses 1–3 (jun–ago 2026)

**Estado de financiamiento:** Pre-cierre-de-seed. Presupuesto pagado = $0. Solo fCMO + liderado por el founder + costos de herramientas.

**Enfoque:** Fundación. Tapar las fugas. Sentar el terreno de SEO. Poner el lifecycle a disparar.

**Resultados al final de Q1:**
- El gate de audífonos desaparece; ganadora de onboarding identificada
- Los cuatro pilares de SEO sembrados (hub + primeros spokes)
- Flows de lifecycle 4 + 6 vivos
- Listado de App Store en voz de marca
- 5 ambassadors activos
- Auditoría de pricing cerrada
- Dominio consolidado

**Metas de KPI:** Lift de Día 1 → pago del onboarding de 25–50%. Tráfico orgánico 500–1,500/mes. Tasa de conversión de App Store +20%.

### Q2 — Meses 4–6 (sep–nov 2026)

**Estado de financiamiento:** Cierre de seed (meta ~Q3 2026). Primer desbloqueo de presupuesto pagado: prueba de $5–10K/mes.

**Enfoque:** Validar el pago. Escalar la ganadora de onboarding. Agregar el Flow 2.

**Resultados al final de Q2:**
- Adquisición pagada disparando en Apple Search Ads + Meta
- Ganadora de onboarding publicada permanentemente
- Flow 2 (emails de onboarding) publicado
- Reflexión post-sesión de Mira en producción
- 15–25 ambassadors activos
- Primer caso de referencia de instalación B2B (Aurora) publicado
- Default de plan anual probado

**Metas de KPI:** CAC pagado blended < $50. Tráfico orgánico 1,500–3,500/mes. Curvas de retención mejorando visiblemente.

### Q3 — Meses 7–9 (dic 2026–feb 2027)

**Estado de financiamiento:** Deployment de seed. El pago escala a $20–50K/mes si la unit economics se sostiene. Primera contratación de marketing (manager de lifecycle + contenido).

**Enfoque:** Escalar + diversificar. GA de la app. Los casos de referencia B2B componen.

**Resultados al final de Q3:**
- Lanzamiento GA de la app con un nuevo momento GTM (PR + refresh de creatividad de anuncios + ciclo de contenido del Pilar 3 de ciencia del audio espacial)
- Primer piloto de certificación de Quietude Guides (3–5 hosts)
- Los cuatro pilares produciendo contenido semanal
- Flujo de regalo del antifaz vivo para el pico de vacaciones
- Nueva contratación de marketing incorporada

**Metas de KPI:** CAC blended pagado + orgánico estabilizándose. Conversión de GA de la app +50% sobre la línea base de beta. El piloto de Guides valida el modelo de rev-share + co-marketing.

### Q4 — Meses 10–12 (mar–may 2027)

**Estado de financiamiento:** Pre-Series-A. El escalamiento pagado continúa. El pitch de Series A está en movimiento.

**Enfoque:** Componer. Posicionarse para Series A.

**Resultados al final de Q4:**
- Los canales de composición (orgánico + ambassador + Guides + lifecycle) produciendo 50%+ de las nuevas suscripciones
- 50+ ambassadors, 5–10 Guides
- 4 pilares de SEO + 30+ piezas de contenido vivas
- El pago escalando a $50–150K/mes si se validó
- Narrativa de Series A: evidencia clínica + lift de activación + composición de lifecycle + pipeline de casos de referencia B2B

**Metas de KPI:** Trayectoria de run-rate de ARR D2C clara. LTV/CAC blended > 3. Narrativa del founder + datos + casos de referencia listos para Series A.

---

## 11. Stack de operaciones de marketing

Esto es lo que hace que el plan sea ejecutable al tamaño de equipo de Quietude. Un equipo founder de 4 personas + fCMO + herramientas agénticas puede publicar la salida de una organización de marketing tradicional de 15 a 20 personas — porque la librería de marketing skills y las integraciones MCP hacen la orquestación.

### La tesis

Cada movida en el desglose AARRR de arriba mapea a (a) una o más marketing skills que operacionalizan el trabajo, y (b) una o más integraciones MCP/API que le permiten ejecutarse sin headcount dedicado por canal.

El trabajo del fCMO es:
1. Definir la estrategia y la secuenciación (este documento)
2. Correr las skills contra el contexto correcto en el momento correcto
3. Mantener el contexto compartido (`quietude-context`) y las herramientas para que Alex + Sam + futuras contrataciones puedan conectarse
4. Delegar trabajo operativo a humanos (o futuras contrataciones) solo donde el costo de la ejecución agéntica > el costo de la ejecución humana

### Skills mapeadas a etapas AARRR

| Etapa | Skills primarias | Skills de apoyo |
|---|---|---|
| **Adquisición** | `seo-audit`, `ai-seo`, `programmatic-seo`, `schema-markup`, `content-strategy`, `competitor-alternatives`, `paid-ads`, `ad-creative`, `social`, `typefully` | `launch-strategy`, `free-tool-strategy`, `analytics-tracking`, `cold-email`, `copywriting`, `marketing-website-design` |
| **Activación** | `onboarding-cro`, `signup-flow-cro`, `paywall-upgrade-cro`, `page-cro`, `copywriting`, `copy-editing`, `copycraft` | `marketing-website-design`, `ab-test-setup`, `marketing-psychology`, `popup-cro` |
| **Retención** | `email-sequence`, `churn-prevention` | `copywriting`, `copy-editing`, `ab-test-setup`, `paywall-upgrade-cro` |
| **Referidos** | `referral-program`, `social` | `copywriting`, `marketing-website-design`, `email-sequence` |
| **Ingresos** | `pricing-strategy`, `paywall-upgrade-cro`, `sales-enablement`, `revops` | `ab-test-setup`, `copywriting` |
| **Transversal** (marca, inteligencia) | `product-marketing-context`, `customer-research`, `marketing-psychology` | `marketing-ideas`, `diagram-maker` |

### MCPs / APIs mapeadas a etapas

| Etapa | Conexiones existentes en Quietude | Capa de herramientas (stack de fCMO de Casey) |
|---|---|---|
| **Adquisición** | App Store Connect (manual), Shopify, GA4 (en progreso), Notion | API de Ahrefs, API de DataForSEO, Typefully MCP, GitHub MCP (`quietude-promo`), `agent-browser`, `defuddle` |
| **Activación** | App Store Connect, Customer.io, Shopify | App Store Connect (vía `dev-browser` para automatización de capturas), Figma / Pencil MCP, GitHub MCP (repo de app `quietude-app`), Stripe MCP |
| **Retención** | **Customer.io (con MCP de Claude — validado en el kickoff)**, Stripe, Shopify | MCP de Customer.io, Stripe MCP, GA4 MCP |
| **Referidos** | Dub.co, Stripe | Dub.co, Stripe MCP, GitHub MCP (landing pages por ambassador), MCP de Customer.io |
| **Ingresos** | Stripe, Shopify, Customer.io | Stripe MCP, Shopify, GA4 MCP, Notion |
| **Transversal** | Notion, GitHub (`quietude-context`) | Notion, GitHub MCP, `defuddle`, `obsidian-cli` (para las notas de trabajo de Casey) |

### El desbloqueo del MCP de Customer.io (ejemplo concreto)

Según la llamada de kickoff: *"Construido en vivo en la llamada — flujo de carrito abandonado borrado usando el MCP de Claude de Customer.io. Se validó que el equipo no técnico puede usar el patrón de skill de forma independiente."*

Esta es la prueba operativa de que el stack funciona. Alex, quien no es desarrollador, redactó un flujo de lifecycle funcional con Claude + el MCP de Customer.io en tiempo real en una llamada de kickoff. El mismo patrón aplica a: publicación del Flow 4 (reenganche de usuario inactivo), construcción del centro de suscripción, campaña de win-back, flujo de regalo del antifaz, lifecycle de ambassador. El rol del fCMO se convierte en orquestación + QA de voz de marca, no en escribir cada email a mano.

### Desbloqueos de capacidad por etapa de financiamiento

| Etapa | Headcount | Herramientas | Canales activos |
|---|---|---|---|
| **Pre-cierre-de-seed (ahora)** | fCMO + equipo founder | Todas las herramientas actuales + librería de marketing skills de Casey + capa MCP | Solo orgánico (SEO, contenido, App Store, LinkedIn, eventos, boca a boca, ambassador) |
| **Cierre de seed (~Q3 2026)** | + primera contratación de marketing (lifecycle/contenido) para fin de Q3 | + cuentas de anuncios pagados (Apple Search Ads, Meta, LinkedIn) | + piloto de adquisición pagada $5–10K/mes |
| **Deployment de seed (Q3–Q4 2026)** | + diseñador (potencialmente fraccional) | + expansión de analítica (Mixpanel o Amplitude si se necesita) | + escalamiento pagado $20–50K/mes, + piloto de certificación de Guides |
| **Series A (2027)** | + lead de performance marketing + lead de contenido | + gasto dedicado en herramientas (~$2–5K/mes de software) | + escalamiento pagado $50–150K/mes, + internacional, + expansión vertical B2B |

La librería de marketing skills escala estas etapas. Cada canal agregado no requiere un aumento de headcount 1:1 porque cada skill codifica el flujo de trabajo.

---

## 12. Banco táctico de ideas — referencia cruzada de 139 ideas

La skill `marketing-ideas` cataloga 139 tácticas de marketing probadas. Las Secciones 4–8 (AARRR) prescriben lo que estamos *haciendo*. Esta sección mapea el universo completo de lo que es *posible* — cada idea cruzada con la etapa AARRR a la que sirve principalmente, con aplicabilidad y timing para Quietude.

Este es el menú exhaustivo. El plan de arriba es el camino curado. Cuando pasemos a Q2 / Q3 / Series A y se desbloquee nueva capacidad, este es el inventario del que extraemos.

**Leyenda de estado:**

- **Ahora (Q1)** — ya está en el plan a 90 días O puede correr en paralelo sin nueva capacidad
- **Q2** — post-corrección-de-base, post-fundación; capas del segundo trimestre
- **Q3+** — post-cierre-de-seed, post-GA; movidas de expansión
- **Q4+** — juego largo / movidas de gran inversión
- **Omitir / fuera de marca** — incompatible con la voz de marca, el modelo de negocio, o la categoría de producto de Quietude

### 12.1 Ideas de Adquisición (88 mapeadas)

**Ahora (Q1):**

| # | Idea | Nota de Quietude |
|---|---|---|
| 1 | Ranking Fácil de Keywords | El cluster Tier-1 del plan de SEO (sistema nervioso, antifaz de dormir, B2B) apunta directamente a esto |
| 2 | Auditoría de SEO | Correr `/seo-audit quietude.app` trimestralmente; publicar hallazgos como contenido |
| 5 | Repropósito de Contenido | Sound Philosophy → ensayos → posts de LinkedIn → newsletter → loop de podcast |
| 6 | Contenido de Datos Propietarios | El estudio peer-reviewed de psicofisiología ahora; dataset anonimizado de HRV/sueño de Quietude después |
| 7 | Enlazado Interno | Integrado en la estructura pilar/spoke del plan de SEO |
| 10 | SEO Parásito | El LinkedIn de Alex ya hace esto; considerar espejo a Substack |
| 12 | Jiu-Jitsu de Marketing | Meditación-vs-Regulación ES esto — voltear la suposición de "la meditación funciona" en su contra |
| 36 | Marketing en Quora | Responder preguntas de "por qué la meditación no funciona para mí" + HRV + somática |
| 37 | Investigación de Keywords en Reddit | Minar r/somatic, r/CPTSD, r/HSP, r/ADHD por lenguaje del ICP (alimenta el Lenguaje del Cliente #139) |
| 39 | Audiencia de LinkedIn | El canal de Alex productizado — tope de funnel D2C primario hoy |
| 59 | Citas en Artículos | HARO / Help-A-B2B-Writer para Alex + Sam — victorias de prensa fáciles |
| 70 | Charlas en Conferencias | Alex: WELL Conference, eventos de diseño biofílico, Mindful Leadership Summit |
| 74 | Cobertura de Prensa | Presentar el estudio peer-reviewed + el gancho del influencer de longevidad a 5 medios en Q1 |
| 109 | Demos Públicos | Los eventos en vivo de Quietude SON esto; instrumentar la conversión en-persona → app |
| 114 | Marketing Moneyball | Ya se está practicando — keywords SEO asimétricas, canales subvalorados |
| 133 | Marketing a Inversionistas | El levantamiento de Alex — aprovechar el backchannel de angels para PR + intros |

**Q2:**

| # | Idea | Nota de Quietude |
|---|---|---|
| 3 | Marketing de Glosario | Glosario de sonido + sistema nervioso — "qué es polivagal," "qué es HRV," "qué es escucha somática" |
| 8 | Actualización de Contenido | Revisitar el Pilar 1 trimestralmente con nuevos datos y actualizaciones de intención de búsqueda |
| 11 | Páginas de Comparación con Competidores | Quietude vs. Calm / Headspace / Brain.fm / Endel / Wavepaths — SERPs de alta intención |
| 13 | Investigación de Anuncios Competitivos | SpyFu + Facebook Ad Library antes de lanzar pago |
| 17 | Marketing con Quiz | "¿Cuál es tu perfil de sistema nervioso?" — genera semilla de personalización + captura de leads |
| 25 | Anuncios de Facebook | Creatividad del antifaz + contenido somático + retargeting de asistentes a eventos |
| 26 | Anuncios de Instagram | Producto visual + anuncios nativos de Reels (especialmente el antifaz) |
| 28 | Anuncios de LinkedIn | Compradores de venues B2B + ICP adyacente a inversionistas |
| 31 | Anuncios de Google | Apple Search Ads primero (intención de App Store); Google para el antifaz + B2B |
| 38 | Marketing en Reddit | Participación auténtica en r/somatic, r/HSP, r/ADHD después de que exista base de contenido |
| 40 | Audiencia de Instagram | Creadores de antifaz + somáticos; nativo de Reels |
| 44 | Marketing con Comentarios | Comentarios reflexivos en Huberman / el negocio-de-eventos-partner / Tim Ferriss / creadores de bienestar |
| 49 | Newsletters Mensuales | Ya sea con marca Quietude o sincronizado con la newsletter de Substack de Sam |
| 54 | Descubrimiento de Afiliados vía Backlinks | Encontrar quién enlaza a Calm/Headspace/Brain.fm — proponerles el programa de afiliados de Quietude |
| 58 | Intercambios de Newsletter | El negocio-de-eventos-partner, Substacks de bienestar de founders, red de inversionistas de Alex |
| 64 | Patrocinio de Comunidad | Newsletters somáticos, Substacks de bienestar, comunidades de founders |
| 65 | Webinars en Vivo | Alex + Sam presentando "Sonido + el Sistema Nervioso" |
| 101 | Entrevistas de Industria | Alex + Sam entrevistan expertos de la categoría (se convierte en la semilla del podcast de Quietude) |
| 102 | Capturas de Pantalla Sociales | Respuestas de reflexión de Mira (anonimizadas, consentidas) — oro de prueba social |
| 108 | Changelogs | Changelog público en `quietude.app/changes` — señal de momentum de producto |
| 115 | Curación como Marketing | Función curada "grabaciones de campo del año"; directorio de Espacios Quietude |
| 135 | Soporte como Marketing | Exponer momentos de soporte al cliente / reflexión de Mira como contenido |
| 138 | Tours de Podcast | Alex en Huberman, el negocio-de-eventos-partner, Tim Ferriss, Rich Roll, Rangan Chatterjee |

**Q3+:**

| # | Idea | Nota de Quietude |
|---|---|---|
| 4 | SEO Programático | Páginas de ciudad de Quietude Guides una vez que el programa Guides escale |
| 9 | SEO de Base de Conocimiento | Cuando los docs de ayuda escalen lo suficiente para tener cobertura problema-solución |
| 14 | Proyectos Paralelos | Eventualmente una herramienta gratuita adyacente a Quietude que viva fuera de la app |
| 15 | Ingeniería como Marketing | Guía de interpretación de HRV; autoevaluación del sistema nervioso; directorio de buscador de baño de sonido |
| 18 | Marketing con Calculadora | Calculadora de latencia del sueño; índice de sobreestimulación |
| 20 | Microsites | Para momentos GTM específicos (p. ej., lanzamiento GA de Mira) |
| 23 | Publicidad en Podcast | Huberman, Tim Ferriss, Rich Roll, el negocio-de-eventos-partner — leído por el host es lo más relevante |
| 24 | Anuncios de Pre-targeting | Audiencias cálidas vía contenido antes de respuesta directa |
| 29 | Anuncios de Reddit | r/HSP, r/ADHD, r/somatic — alta densidad de ICP, baja saturación de anunciantes |
| 30 | Anuncios de Quora | Rico en intención para consultas de "por qué la meditación no funciona" |
| 32 | Anuncios de YouTube | Pre-roll en videos de Huberman / Lex Fridman / creadores de bienestar |
| 33 | Retargeting Cross-Platform | Capa estándar una vez que el pago esté disparando |
| 35 | Marketing de Comunidad | Comunidad de Espacios Quietude (Discord/Circle); organizar drop-ins mensuales |
| 42 | Video Corto | TikTok / Reels — educación somática + UGC del antifaz |
| 55 | Whitelisting de Influencers | Correr anuncios a través de cuentas de ambassador / Guide para autenticidad |
| 57 | Redes de Expertos | El programa Quietude Guides ES esto — hosts certificados que pueden hacer marketing |
| 60 | Compartir de Pixel | Estándar una vez que el pago esté disparando |
| 61 | Canales de Slack Compartidos | Slacks de venues partner (Aurora, Lumen, Stillwater) |
| 63 | Marketing de Integraciones | Apple Health (datos de HRV), Oura, Whoop — co-marketing |
| 66 | Cumbres Virtuales | Quietude participa o organiza |
| 68 | Meetups Locales | Ciudades con alta densidad de ICP (SF, NYC, LA, Austin) |
| 69 | Patrocinio de Meetups | Patrocinar meetups de bienestar / biohacking |
| 72 | Patrocinio de Conferencias | Conferencias de la industria una vez que se desbloquee presupuesto |
| 75 | PR de Fundraising | Momento de "Quietude levanta $3M" cuando cierre el seed |
| 78 | Lanzamiento en Product Hunt | Momento de lanzamiento público de Mira |
| 79 | Referidos de Acceso Anticipado | Lista de acceso anticipado del GA de la app (cruza referencia con Referidos) |
| 81 | Pricing de Acceso Anticipado | GA de la app — nivel de acceso anticipado asegurado para la primera cohorte |
| 82 | Alternativas a Product Hunt | BetaList, Launching Next, AlternativeTo en el GA |
| 97 | Playlists como Marketing | Quietude cura playlists de Spotify para escucha somática |
| 98 | Marketing de Plantillas | PDFs gratuitos de protocolo "reset del sistema nervioso" |
| 100 | Videos Promocionales | Films de marca de alta calidad — Ed Dorsey asesora, Matt Mikkelsen graba el audio de campo |
| 103 | Cursos Online | Curso de Sound Philosophy de Alex; curso de metodología somática de Sam |
| 107 | Podcasts | Podcast de Quietude — formato de entrevista con expertos de la categoría y clientes |
| 111 | Retos como Marketing | "Reset del sistema nervioso de 21 días" — con buen gusto, sin tono fitness-bro |
| 113 | Controversia como Marketing | Meditación-vs-Regulación ES controversia leve — inclinarse con cuidado |
| 126 | Reseñas en YouTube | Proponer Quietude a YouTubers de bienestar — nivel de creador fan de Huberman |
| 127 | Canal de YouTube | Detrás de cámaras del diseño de sonido; demos de sesiones de Sam |
| 129 | Sitios de Reseñas | Reseñas de App Store gestionadas activamente; Trustpilot para el Shopify del antifaz |
| 130 | Audio en Vivo | Twitter Spaces / LinkedIn Audio con Alex sobre sonido y cuerpo |
| 134 | Certificaciones | La certificación de Quietude Guides ES esto — piloto Q3+ |

**Q4+ / juego largo:**

| # | Idea | Nota de Quietude |
|---|---|---|
| 56 | Programas de Revendedores | Plataformas de bienestar corporativo (Modern Health, Lyra) como revendedores |
| 67 | Roadshows | Experiencias Quietude ES esto — pop-ups de antifaz + sesión de escucha en 3 ciudades |
| 71 | Conferencias | "Sonido + el Cuerpo" organizado por Quietude — momento de largo plazo que define la categoría |
| 76 | Documentales | La historia de Alex es de calidad documental — juego largo |
| 77 | Promociones de Black Friday | Bundle de antifaz + Premium para las fiestas |
| 80 | Promociones de Año Nuevo | Campaña de reset del sistema nervioso de Año Nuevo |
| 84 | Sorteos | Sorteo de antifaz con partner de marca (nivel Wellness Mama) |
| 85 | Sorteos de Vacaciones | Sorteo de Quietude + partner de retiro (quietude.center podría ser el venue) |
| 87 | Marketing "Powered By" | Insignia "Sistema de sonido por Quietude" en instalaciones B2B de venues |
| 104 | Marketing de Libro | Sound Philosophy como libro — ancla de posicionamiento a largo plazo |
| 105 | Reportes Anuales | "Estado del Sistema Nervioso" — datos de Quietude + comentario de la industria |
| 106 | Resúmenes de Fin de Año | "Tu año del sistema nervioso" — equivalente al Wrapped de Spotify |
| 110 | Premios como Marketing | Quietude funda un premio para diseño acústico biofílico innovador |
| 116 | Grants como Marketing | Suscripciones gratuitas de Quietude para terapeutas, trabajadores sociales, primeros respondientes |
| 119 | Publicidad OOH | Vallas en SF / NYC si se desbloquea presupuesto de Series A |
| 120 | Stunts de Marketing | Una instalación de sonido pública podría funcionar — encaja con la marca |
| 121 | Marketing de Guerrilla | Instalación de sonido en el metro / aeropuerto — interesante pero requiere cuidado |
| 131 | Expansión Internacional | Sede en Finlandia + ICP global — Q4 o post-Series-A |

**Omitir / fuera de marca para Quietude:**

| # | Idea | Por qué omitir |
|---|---|---|
| 16 | Importadores como Marketing | No hay datos de competidor para importar (bienestar de consumo, no SaaS) |
| 19 | Extensiones de Chrome | Fuera de plataforma (producto mobile-first) |
| 21 | Escáneres | No hay ajuste de producto obvio |
| 22 | APIs Públicas | No es negocio central |
| 27 | Anuncios de Twitter | Prioridad menor a menos que crezca la presencia de Alex en X |
| 34 | Anuncios de Click-to-Messenger | Fuera de marca (sin patrón de ventas impulsado por DM) |
| 41 | Audiencia de X | Depende del ancho de banda de Alex — postergar a menos que él quiera |
| 43 | Grupos de Engagement | Fuera de marca |
| 73 | Adquisiciones de Medios | Demasiado intensivo en capital en esta etapa |
| 83 | Sorteos en Twitter | Voz fuera de marca |
| 86 | Ofertas de por Vida | Conflicto de marca — presiona la voz de "sin presión" y daña las matemáticas de LTV |
| 88 | Migraciones Gratuitas | No hay datos de competidor que migrar |
| 89 | Recompra de Contratos | No es relevante para suscripciones D2C |
| 99 | Marketing de Novela Gráfica | Fuera de marca |
| 112 | Marketing de Reality TV | Fuera de marca |
| 117 | Competencias de Producto | No es un producto para desarrolladores |
| 118 | Marketing de Cameo | Fuera de marca |
| 122 | Marketing con Humor | La voz de marca es seria; el humor se sentiría fuera de lugar |
| 123 | Open Source como Marketing | Librería de audio propietaria |
| 125 | Marketplaces de Apps | No es relevante para una app nativa de consumo (sin patrón de app-de-app) |
| 128 | Plataformas de Fuente | G2 / Capterra son enfocados en B2B; D2C usa reseñas de App Store |
| 132 | Localización de Precio | Q4+ — vinculado a la expansión internacional |
| 136 | Relaciones con Desarrolladores | No es un producto de desarrolladores |

### 12.2 Ideas de Activación (7 mapeadas)

| # | Idea | Estado | Nota de Quietude |
|---|---|---|---|
| 124 | Optimización de App Store | Ahora | Prioridad Q1 — reescritura del listado en voz (también Adquisición) |
| 90 | Registro en Un Clic | Ahora | OAuth (Apple, Google) para el signup de la app — lift de activación estándar |
| 51 | Emails de Onboarding | Q2 | Flow 2 — retenido hasta que la UI se estabilice post-reconstrucción-de-onboarding |
| 96 | Optimización de Onboarding | Q1-Q2 | La prueba de 3 variantes ES esto — trabajo primario de activación |
| 47 | Email de Bienvenida del Founder | Q2 | Bienvenida personal de Alex o Sam temprano en el Flow 2 |
| 48 | Captura Dinámica de Email | Q2 | Captura inteligente en `quietude.app` — intención de salida + profundidad de scroll |
| 95 | Configuración Concierge | Q3+ | Onboarding de alto contacto para clientes B2B de venues + suscriptores de alto valor |

### 12.3 Ideas de Retención (8 mapeadas)

| # | Idea | Estado | Nota de Quietude |
|---|---|---|---|
| 46 | Emails de Reactivación | Ahora | El Flow 4 se publica en las semanas 3–4 — exactamente esto |
| 52 | Emails de Win-back | Q1 (semana 11-12) | Campaña independiente encima del Flow 4 |
| 53 | Reactivación de Trial | Q2 | Campaña de recuperación de trial expirado una vez que el paywall esté disparando |
| 45 | Marketing de Email de Error | Q2 | Cuando algo realmente sale mal, enviar un "oops" — impulsa el engagement |
| 50 | Colocación en Inbox | Q1 | Estrategia de silo de subdominio (`mail.quietude.app` / `commerce.quietude.app`) aborda esto |
| 91 | Upsells In-App | Q2 | Puntos de upsell de Premium dentro de la app (también Ingresos) |
| 94 | Flujos de Offboarding | Q2 | Optimizar el flujo de cancelación para retener o aprender — alimenta la inteligencia de churn |
| 135 | Soporte como Marketing | Q2 | Las historias de soporte al cliente se exponen como contenido (también Adquisición) |

### 12.4 Ideas de Referidos (5 mapeadas)

| # | Idea | Estado | Nota de Quietude |
|---|---|---|---|
| 62 | Programa de Afiliados | Ahora | El programa de ambassador v1 es exactamente esto — lanzado con los 5 inbound |
| 137 | Referidos de Dos Lados | Q2 | Recompensar tanto al referidor como al referido — momento de compartir-después-del-cambio + flujo de regalo |
| 92 | Referidos de Newsletter | Q3 | Si lanzamos una newsletter, mecánica de referido estilo Sparkloop |
| 93 | Loops Virales | Q3 | Mecánicas de compartir integradas post-reflexión de Mira |
| 79 | Referidos de Acceso Anticipado | Q3 | Referidos de la lista de acceso anticipado del GA de la app (cruza referencia con Adquisición) |

### 12.5 Ideas de Ingresos (3 mapeadas — la mayoría de las ideas sirven al tope de funnel)

| # | Idea | Estado | Nota de Quietude |
|---|---|---|---|
| 91 | Upsells In-App | Q2 | Prompts de actualización a Premium; cross-sell del antifaz desde la app (también Retención) |
| 132 | Localización de Precio | Q4+ | Ajustar el pricing para el poder adquisitivo local una vez internacional |
| 86 | Ofertas de por Vida | Omitir | Conflicto de marca — ver la lista de omitidos de Adquisición |

### 12.6 Ideas transversales / de fundación de marca

| # | Idea | Estado | Nota de Quietude |
|---|---|---|---|
| 139 | Lenguaje del Cliente | Ahora | Las respuestas de reflexión de Mira + el lenguaje de las 7 Ds = la fuente de verdad para el lenguaje del cliente en todo el copy |
| 114 | Marketing Moneyball | Continuo | Encontrar canales subvalorados en cada etapa — metodología, no una sola táctica |

### Resumen del banco de ideas

- **88 ideas aplicables a Adquisición** (la etapa dominante en la etapa actual de Quietude — tiene sentido, el producto de Quietude convierte bien; el cuello de botella es el tope del funnel)
- **7 ideas a Activación, 8 a Retención** (más pequeñas porque estas etapas son sobre profundidad, no amplitud — ejecutar bien las pocas correctas en lugar de correr un menú amplio de tácticas)
- **5 ideas a Referidos** (impulsado por programa, no por táctica)
- **3 ideas a Ingresos** (la mayor parte del trabajo de ingresos es estrategia de pricing, no trucos tácticos)
- **2 transversales**
- **23 ideas omitidas por ajuste de marca / modelo de negocio** — el posicionamiento de categoría de Quietude restringe lo disponible

**Lo que esto demuestra:** el plan es aproximadamente el 30% de la superficie táctica disponible, no el 100%. Eso es apropiado en esta etapa y presupuesto. A medida que se desbloquea capacidad a través de Q2 → Q3 → Series A, la referencia cruzada se convierte en el inventario del que extraemos para escalar la actividad sin perder coherencia estratégica.

---

## 13. Medición, RACI, decisiones abiertas, apéndice

### Medición — las métricas que importan

**Métrica norte (propuesta):**
**Ratio LTV-blended-a-CAC-blended por usuario adquirido**, donde:
- El LTV blended combina el ingreso de suscripción de la app + el ingreso de hardware (antifaz + speakers) + cualquier cross-sell, por cohorte
- El CAC blended combina el gasto pagado + el costo de producción de contenido + las comisiones de ambassador + el gasto en herramientas de lifecycle, por cohorte

Esto captura el modelo de negocio: la cuña del antifaz no es gratis si cuesta $X fabricarla, y la suscripción de la app no es cara de adquirir si un momento de PR estilo Bryan-Johnson se está pagando solo.

Si se prefiere una métrica única para el enfoque a nivel de equipo, recurre a: **nuevos suscriptores D2C mensuales de canales no pagados.** Esto aísla los canales de composición de los que depende la estrategia de largo plazo.

**Indicadores líderes por etapa AARRR:**

| Etapa | Indicadores líderes |
|---|---|
| Adquisición | Visitas orgánicas/mes (total + por pilar), tasa de visita-a-instalación de App Store, engagement del LinkedIn de Alex → suscriptores de email, tasa de conversión de evento a app, visitas atribuidas a ambassador |
| Activación | Conversión Día 1 / Día 7 / Día 35 → pago, tasa de completación de sesión de onboarding, completación de reflexión de Mira en la primera sesión |
| Retención | Retención 30 / 60 / 90 días, churn mensual, tasa de reactivación del Flow 4, tasa de activación hardware → app |
| Referidos | Nuevas suscripciones atribuidas a ambassador (Dub), tasa de compartir-después-del-cambio, referidos del piloto de Guides (cuando esté vivo) |
| Ingresos | MRR blended, ARPU, % de adopción de plan anual, LTV por cohorte, tasa de attach del antifaz |

**Cadencia de revisión:**
- **Semanal:** Sync de 30 min fCMO ↔ Alex. Scoreboard AARRR + los envíos de esta semana.
- **Mensual:** Revisión completa de métricas (sync extendido, con Sam incluido). Comparar contra las metas trimestrales de KPI.
- **Trimestral:** Recalibración del plan. Qué funciona, qué no, qué movidas de etapa de financiamiento estamos activando.

### RACI

| Dominio | Responsable | Aprobador | Consultado | Informado |
|---|---|---|---|---|
| Plan estratégico (este documento) | Casey | Alex | Sam, Emily | Equipo |
| Voz de marca | Alex + Sam | Alex + Sam | Casey | Equipo |
| Implementación de app + onboarding | Devon | Alex | Casey | Equipo |
| Flujos de lifecycle (Customer.io) | Casey | Alex | Sam (QA de copy) | Equipo |
| Contenido SEO | Casey | Casey | Sam, Alex | Equipo |
| Copy de App Store | Casey | Alex | Sam | Equipo |
| Cadencia de LinkedIn de Alex | Alex | Alex | Casey (orquestación) | Equipo |
| Eventos | Alex + Sam | Alex | Casey (solo instrumentación) | Equipo |
| Programa de ambassador | Casey | Casey | Alex | Equipo |
| Ventas B2B | Alex | Alex | Casey (casos de estudio) | Equipo |
| Pricing | Alex | Alex | Casey | Sam |
| Narrativa de inversionistas | Alex | Alex | Casey, Sam | Equipo |
| Programa Quietude Guides (Q3+) | TBD (probablemente futura contratación) | Alex + Sam | Casey | Equipo |
| Futura contratación de marketing (Q3) | Casey | Alex | Sam | Equipo |

### Decisiones abiertas que bloquean el plan

Las de mayor bloqueo, ordenadas por impacto:

1. **Dominio canónico.** Los datos de SEO + este plan recomiendan `quietude.app`. Necesita aprobación ejecutiva + plan de ejecución de 301s. *Bloquea: consolidación de dominio, fundación de SEO, migración del remitente de email.*
2. **Definición de la métrica de retención.** Reconciliar el reclamo de 38% de retención a 12 meses vs. 29% de churn mensual de App Store. *Bloquea: dashboards limpios, coherencia de narrativa de inversionistas, lecturas de pruebas de lifecycle.*
3. **Alcance de la reflexión post-sesión de Mira.** ¿Mira actualmente soporta esto, o es un build nuevo? *Bloquea: Variantes 1 y 2 de Onboarding (que dependen del momento de reflexión de Mira), movidas de composición de retención.*
4. **Timeline de estabilidad de la UI de la app.** ¿Cuándo permite la eliminación-del-gate-de-audífonos + la reconstrucción-del-onboarding que el Flow 2 se publique sin riesgo de reproceso? *Bloquea: Flow 2, lifecycle completo, timing de la adquisición pagada.*
5. **Timeline del lanzamiento GA.** ¿Cuándo se convierte la beta con throttling en GA? *Bloquea: escala de adquisición pagada, planificación GTM de Q3.*
6. **Verdad de fondo de la estructura de pricing.** ¿Qué se cobra realmente hoy? *Bloquea: conclusiones de la auditoría de pricing, prueba de default de plan anual, matemáticas de LTV blended.*
7. **Alcance de la primera contratación de marketing.** ¿Owner de lifecycle + contenido, o algo más? ¿Cuándo se escribe la descripción del puesto? *Bloquea: plan de capacidad de Q3, sucesión del trabajo operativo del fCMO.*
8. **Estructura de comisión de ambassador.** ¿$/suscripción, rev-share, híbrido? *Bloquea: lanzamiento del programa de ambassador, dashboards de atribución.*

### Apéndice — enlaces de profundización

**Publicado al equipo vía el repo de GitHub `Quietude-Inc/quietude-context`:**
- `marketing/seo/plan.md` — Plan completo de SEO a 90 días + investigación de keywords
- `marketing/seo/keyword-shortlist.md` — Shortlist de keywords Tier 1
- `marketing/seo/raw/` — Extracciones de API de Ahrefs + DataForSEO
- `marketing/onboarding-recommendation.md` — Plan de prueba de onboarding de tres variantes

**Contexto estratégico escrito por el founder** (en la base de conocimiento interna de Quietude):
- Seed deck — Narrativa de inversionistas
- Sound Philosophy — Documento de trabajo técnico/filosófico de Alex
- Marketing OS — Voz de marca, ritmo de contenido, sistema visual
- Documento de ICP — Perfil de audiencia D2C
- Nota de Meditación-vs-Regulación (2026-05-19) — Pilar de contenido central
- Transcripción de la llamada de kickoff (2026-05-18) — Decisiones + preguntas abiertas
- Captura del copy de App Store + análisis de brecha de voz
- Captura de métricas de App Store (2026-05-16)
- Inventario de flujos de lifecycle de Customer.io

---

*Plan de Marketing v1. Preparado por Casey Reed (fCMO), 2026-05-27. Para revisión y discusión del equipo.*
