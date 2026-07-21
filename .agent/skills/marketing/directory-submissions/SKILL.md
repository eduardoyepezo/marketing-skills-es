---
name: directory-submissions
description: Cuando el usuario quiere enviar su producto a directorios de startups, SaaS, IA, agentes, MCP, no-code o reseñas para conseguir backlinks, mejorar el Domain Rating (DR) y ganar visibilidad. También usar cuando el usuario menciona "envíos a directorios," "enviar a directorios," "backlinks de directorios," "listar mi producto," "enviar a Product Hunt," "BetaList," "TAAFT," "Futurepedia," "listado en G2," "listado en Capterra," "AlternativeTo," "SaaSHub," "directorios de IA," "registro MCP," "directorio de agentes," "backlinks dofollow," "directorios de lanzamiento," o "tracker de directorios." Usar siempre que alguien esté planeando la capa de directorios de un lanzamiento de producto o una campaña continua de backlinks. Para el momento de lanzamiento más amplio, ver launch-strategy. Para páginas de SEO programático que deben recibir estos backlinks, ver programmatic-seo. Para optimización de citas de IA, ver ai-seo.
metadata:
  version: 2.0.0
---

# Envíos a Directorios

Eres un experto en distribución basada en directorios para productos de software. Tu objetivo es ayudar al usuario a construir una base de backlinks + descubrimiento que se acumule con el tiempo, enviando el producto a los directorios correctos, en el orden correcto, con el posicionamiento correcto — y asegurarte de que esa base realmente genere leads en lugar de backlinks vanidosos.

## Antes de Empezar

**Revisar el contexto de marketing del producto primero:**
Si existe `.agents/product-marketing.md` (o `.claude/product-marketing.md`, o el nombre de archivo heredado `product-marketing-context.md`, en configuraciones más antiguas), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información que no esté ya cubierta o que sea específica de esta tarea.

---

## Filosofía Central

Los envíos a directorios son la **capa de base** de la distribución — nunca la estrategia completa. Hacen bien tres cosas:

1. **Pasan backlinks dofollow** desde sitios con alto Domain Rating hacia tus páginas de marketing. Esto eleva tu DR, lo que hace que todo tu sitio sea más fácil de posicionar para keywords competitivas.
2. **Crean superficie de descubrimiento** — las personas que navegan directorios de IA/SaaS son compradores en el mercado, no tráfico aleatorio.
3. **Logran que te citen los motores de IA** — ChatGPT, Claude, Perplexity y Google AI Overviews recurren mucho a directorios de alto DR al responder consultas del tipo "¿cuál es el mejor [categoría]?". El tráfico referido por IA convierte **6–27× más** que el tráfico de búsqueda tradicional.

Pero los directorios por sí solos no generarán leads significativos. Existen para pasar equity de enlaces hacia las páginas que SÍ generan leads — galerías de plantillas, páginas de comparación, páginas de alternativas, posts de blog. **Construye primero las páginas de destino, luego envía a los directorios para que el equity de enlaces tenga dónde aterrizar de forma útil.**

El catálogo completo de directorios vive en `references/directory-list.md`. La biblioteca de variantes de posicionamiento vive en `references/positioning-variations.md`. La plantilla del tracker de envíos vive en `references/submission-tracker-template.csv`.

---

## Las Tres Reglas Duras

### Regla 1: Base antes que envío
Nunca envíes a un directorio hasta que la landing page a la que enlazará esté en vivo, indexada y tenga:
- Un único `<h1>` y jerarquía de encabezados secuencial — las páginas con jerarquía limpia tienen **2.8× más tasa de citación por IA**, y el 87% de las páginas citadas por ChatGPT usan un único H1.
- Una página de precios real (incluso "gratis mientras estamos en beta" cuenta — la mayoría de los directorios Tier 1 la exigen).
- Política de privacidad + términos.
- Assets de logo en PNG + SVG + cuadrado 1024×1024 + favicon.
- 5–8 screenshots reales del producto a 1920×1080 (no mockups de marketing).
- Un video demo de 60–90 segundos — los productos con video en Product Hunt reciben **2.7× más upvotes**.
- Schema markup de FAQ (los motores de IA valoran mucho el JSON-LD de `FAQPage` para la extracción de respuestas).
- Datos estructurados: `Organization`, `Product`, `SoftwareApplication`.

### Regla 2: Páginas de destino antes que directorios
Los directorios son la *fuente* del equity de enlaces. Necesitas *destinos* que puedan convertir el tráfico resultante. Destinos mínimos antes de enviar a cualquier directorio:
- 3–5 páginas de alternativas a competidores (`/alternatives/[competidor]`) apuntando a keywords tipo "alternativa a [competidor]". Las páginas de comparación/alternativas convierten al **5–15%** frente a 0.5–2% del contenido genérico.
- 3–5 páginas de caso de uso (`/for/[audiencia]` o `/use-cases/[caso-de-uso]`).
- Galería de plantillas con 20+ entradas (si aplica — este fue el mayor motor de crecimiento SEO de Typeform, generando 30K registros orgánicos no de marca y $3M/año en LTV).
- 1 post de blog "lo mejor de" que tú mismo escribas sobre tu propia categoría, incluyendo cobertura honesta de los competidores.

### Regla 3: El posicionamiento varía según el tipo de directorio
Nunca copies y pegues la misma descripción en todos lados. Los motores de IA penalizan el contenido duplicado, y cada audiencia de directorio responde a un enfoque distinto. Ver `references/positioning-variations.md` para la biblioteca completa de variantes. Versión corta:

| Superficie | Lidera con | Por qué |
|---|---|---|
| Directorios de startups | **Resultado** | La audiencia son otros founders. Les importa qué hace. |
| Directorios SaaS | **Framing de alternativa** | La gente busca "alternativa a [competidor]" — encuéntralos ahí. |
| Directorios de IA | **Arquitectura AI-first** | Las audiencias de TAAFT/Futurepedia quieren explícitamente herramientas de IA. |
| Directorios de agentes/MCP | **Ángulo agente/MCP** | Nicho pero de alta intención. Un foso real. |
| Directorios no-code | **Facilidad + poder** | La audiencia valora la velocidad de construcción sobre la profundidad. |
| Directorios de desarrolladores | **Profundidad técnica** | Las audiencias dev premian la sustancia técnica. |
| Sitios de reseñas B2B | **ROI + caso de uso** | Los compradores quieren resultados y casos de estudio. |

---

## Flujo de Trabajo

### Paso 1: Evaluación de preparación (Fase 0)

Hazle al usuario estas 9 preguntas. Si alguna es "no", no está listo — ayúdalo a construir primero la pieza faltante.

1. ¿El producto es públicamente accesible (sin muro de contraseña)?
2. ¿Existe una página de precios (aunque sea "gratis mientras estamos en beta")?
3. ¿La política de privacidad + términos están en vivo?
4. ¿Assets de logo en PNG + SVG + cuadrado + favicon?
5. ¿5–8 screenshots reales + video demo de 60–90s?
6. ¿Landing pages listas para GEO (H1 único, jerarquía secuencial, schema de FAQ, datos estructurados)?
7. ¿Al menos 3 páginas de alternativas y 3 páginas de caso de uso en vivo e indexadas?
8. ¿Galería de plantillas o lead magnet (si aplica a la categoría)?
9. ¿Al menos 20 usuarios beta/tempranos que podrían dejar una reseña en G2?

Un "no" en cualquiera de 1–7 es un bloqueo duro. Un "no" en 8–9 es un bloqueo blando: puedes lanzar pero perderás el valor Tier 2 de reseñas y el efecto compuesto estilo Typeform.

### Paso 2: Elegir los tiers

Catálogo completo en `references/directory-list.md`. Resumen:

| Tier | Cuándo | Ejemplos | Cantidad típica |
|---|---|---|---|
| **Tier 1 — Lanzamiento insignia** | Solo semana de lanzamiento | Product Hunt (ancla), BetaList, HN Show HN, Fazier, DevHunt | ~15 |
| **Tier 2 — Startup/SaaS** | Semana 1 + continuo | AlternativeTo, SaaSHub, G2, Capterra, F6S, SourceForge, Slashdot | ~50 |
| **Tier 3 — Directorios de IA** | Semana 1–3 | TAAFT, Futurepedia, Toolify, Future Tools, aitools.inc, AIStage | ~40 |
| **Tier 4 — Registros de agentes/MCP** | Semana 1–3 (si es MCP) | Glama, APITracker, LF MCP Registry, AI Agents List | ~10 |
| **Tier 5 — Directorios no-code** | Semana 1–3 (si es no-code) | NoCodeFinder, No Code MBA, We Are No Code, MakerPad | ~8 |
| **Tier 6 — Listicles "lo mejor de"** | Outreach continuo | Outreach en frío a posts de blog con DR 40+ | ~10 inclusiones |
| **Tier 7 — Marketplaces de integraciones** | Cuando las integraciones salen | Zapier, HubSpot, Slack, Airtable, Notion | ~5 |
| **Tier 8 — Plataformas de perfil y contenido** | Continuo | GitHub, WordPress.com, Substack, Dev.to, SlideShare, Behance | ~50 |
| **Tier 9 — Directorios de negocios locales** | Continuo (si aplica) | Manta, Hotfrog, Locanto, MerchantCircle | ~20 |
| **Tier 10 — Foros y comunidades** | Continuo (participar primero) | SitePoint, GrowthHackers, Warrior Forum, Designer News | ~13 |
| **Tier 11 — Sitios de comunicados de prensa y artículos** | Lanzamiento + hitos | PRLog, PR.com, EzineArticles, Feedspot | ~25 |
| **Tier 12 — Bookmarking social** | Continuo | Scoop.it, Diigo, Pearltrees | ~5 |
| **Tier 13 — Directorios verticales de nicho** | Cuando el vertical encaja | Justia (legal), Porch (hogar), LandBook (diseño), etc. | ~20 |

**Regla de triaje:** Solo enviar donde el producto encaje genuinamente. Forzar un listado en la categoría equivocada quema la ventaja de ser el primer envío y provoca el rechazo de los moderadores.

### Paso 3: Preparar variaciones de assets

Para cada tier, prepara una variante de descripción distinta (extraída de `references/positioning-variations.md`):
- **Tagline** de menos de 10 palabras
- **Descripción corta** de 60 caracteres
- **Descripción larga** de 150 palabras
- **5–8 tags de categoría**
- Assets de **logo**
- **Screenshots** + URL del video demo
- **Historia del founder** (2–3 oraciones)

**Crítico:** No copies y pegues la misma descripción larga en cada directorio. Varía la oración de apertura, el énfasis de funciones y el framing de audiencia por tier. Los motores de IA hacen referencias cruzadas y penalizan el contenido duplicado.

### Paso 4: Envío por lotes

Configura la hoja de cálculo del tracker (`references/submission-tracker-template.csv`). Trabaja de izquierda a derecha a través de ella. 2–3 horas por lote es realista.

Por cada envío:
1. Copia la variante de posicionamiento apropiada para el tier.
2. Llena el formulario.
3. Sube los assets.
4. Envía.
5. Registra: fecha, URL, estado, notas del moderador.
6. Una vez en vivo, verifica que el backlink exista y sea dofollow: `curl -sIL https://directory.com/your-listing | grep -i rel=`. Si está ausente, el enlace es dofollow.

---

## Análisis Profundo de Product Hunt (El Evento Ancla)

Product Hunt es el envío individual de mayor apalancamiento pero también el más fácil de desperdiciar. El algoritmo de PH 2026 pondera más la **calidad de los comentarios** que la cantidad de upvotes — un post con 50 upvotes + 30 comentarios genuinos supera a uno con 200 upvotes + 5 comentarios. **El 80% de los lanzamientos fallidos** fallan porque lanzaron sin una audiencia cálida O porque pidieron upvotes en lugar de feedback.

### Cronograma de preparación de 3 semanas

- **Día -21 a -14:** Calienta la cuenta de hunter. Da upvote + comenta con reflexión en 3 lanzamientos/día. Sigue a 100+ makers activos. Construye historial para que tu cuenta parezca real ante el algoritmo.
- **Día -14:** Crea la página "Upcoming" en PH. Dirige tráfico hacia ella para captar suscriptores de "avisar en el lanzamiento".
- **Día -10:** (Opcional) reserva un hunter. No pagues en efectivo — intercambia una función, un shoutout, o una intro. Un hunter conocido suma ~15% al momentum del primer día pero no es obligatorio.
- **Día -7:** Redacta los assets del día de lanzamiento: imágenes de galería (1270×760), tagline, descripción de 260 caracteres, primer comentario tuyo, primer comentario de un cliente.
- **Día -3:** Calentamiento de la lista de email. "Lanzamos el martes. Esto es lo que puedes esperar. Responde si quieres un aviso."
- **Día -1:** Chequeo final — el producto funciona en incógnito, el video se reproduce automáticamente, el CTA lleva al registro, la vista previa del listado en PH se ve bien.

### Ejecución del día de lanzamiento

- **Lanza a las 12:01 AM hora del Pacífico.** Solo martes, miércoles o jueves — los lanzamientos de fin de semana obtienen 60–70% menos tráfico. El inicio a las 12:01 AM PT maximiza tu ventana de 24 horas.
- **Las primeras 2 horas lo son todo.** Necesitas 50+ apoyos en las primeras 2 horas para activar la distribución algorítmica.
- **Publica el primer comentario tú mismo** con la historia: por qué lo construiste, qué es diferente, qué probar primero.
- **Responde a cada comentario** en menos de 30 minutos. PH mide la capacidad de respuesta del maker.
- **Comparte el enlace en:** hilo de Twitter/X, post largo de LinkedIn, comunidades personales de Slack/Discord, tu lista de email, Indie Hackers, cada power user por DM.
- **Nunca pidas upvotes.** Pide **feedback**. "Me encantaría tu opinión honesta sobre el posicionamiento" convierte 3× mejor que "¡apóyanos!" y no activa los filtros anti-manipulación del algoritmo.
- **No envíes mensajes a desconocidos.** La comunidad marca esto y los moderadores ocultarán tu post.

### Post-lanzamiento

- Escribe un post de blog de recapitulación del lanzamiento con números + aprendizajes. Honesto, no jactancioso. Publícalo el día 2.
- Cross-postea la recapitulación en Indie Hackers y r/SaaS (donde la promoción está permitida).
- Solo envía a Show HN si tienes un ángulo *técnico* que compartir (arquitectura, DSL, enfoque novedoso). Un post genérico de "lanzamos un SaaS" se marcará hasta morir.

---

## Manual de Reseñas (G2 / Capterra / TrustRadius)

Los listados de G2 y Capterra (ahora propiedad de G2 desde febrero de 2026) son **inútiles sin reseñas**. 10 reseñas es el umbral mágico para aparecer en el Grid. Ejecuta el protocolo 10-en-30 durante el mes de lanzamiento.

### El protocolo 10-en-30

1. **Día 1 post-lanzamiento:** Identifica a 20 usuarios que hayan completado una acción significativa con el producto.
2. **Envía a cada uno un email personal** con una URL de reseña directa (reduce la fricción en ~70%). Sin formularios, sin landing pages — enlace directo.
3. **Ofrece un agradecimiento modesto.** G2 y TrustRadius permiten explícitamente incentivos pequeños como una tarjeta de regalo de Amazon de $25.
4. **Haz un solo seguimiento** después de 5 días. No hagas seguimiento dos veces — se vuelve molesto y daña la relación.
5. **Objetivo:** 50% de conversión → 10 reseñas de 20 solicitudes.

### Fechas límite críticas

- **Reportes de verano de G2:** cierre ~28 de abril. Planea las campañas de reseñas para llegar antes de esto.
- **Reportes de otoño de G2:** cierre ~28 de julio.
- Perder una fecha límite significa esperar 3 meses hasta la siguiente actualización del grid.

### Badges y planes pagados

- El badge **"Users Love Us"** sigue siendo gratis: requiere 20 reseñas con promedio de 4.0+.
- Los badges **Grid, Momentum, Index y Award** requieren un plan pagado de G2 ($2,999+/año a partir del verano de 2025).
- **No gastes en G2 pagado el primer año.** El listado gratuito + el badge Users Love Us es suficiente.

### Multiplataforma

- TrustRadius sigue una mecánica similar pero con menor volumen.
- Capterra sincroniza automáticamente desde Gartner Digital Markets en algunas categorías — puede poblarse sin acción directa.

---

## Estrategia de Páginas de Destino (Adónde Apuntan los Backlinks)

Los directorios son inútiles si los backlinks aterrizan en una homepage genérica. Construye estas páginas de destino *antes* de enviar a los directorios:

### 1. Páginas de alternativas (mayor ROI)

Las páginas de alternativas a competidores convierten al **5–15%**, llegando a menudo al 15–30% para consultas de fondo de embudo. Una página por cada competidor principal:

- `/alternatives/[competidor-1]`
- `/alternatives/[competidor-2]`
- `/alternatives/[competidor-3]`
- `/alternatives/[competidor-4]`

Cada página necesita: tabla honesta de comparación de funciones, "cuándo elegir X sobre nosotros", "cuándo elegirnos a nosotros sobre X", comparación de precios, 3–5 ejemplos de caso de uso, FAQ sólido con schema.

**Crítico:** Sé honesto. Los motores de IA hacen referencias cruzadas de las afirmaciones de funciones de los competidores y degradan las páginas que mienten.

### 2. Páginas de caso de uso / ICP

Cada ICP recibe una landing page dedicada:
- `/for/[audiencia]` — coaches, agencias, ecommerce, SaaS, consultores, etc.
- `/use-cases/[caso-de-uso]` — calificación de leads, onboarding, recomendaciones de producto, etc.

### 3. Galería de plantillas / assets (si aplica)

La biblioteca de plantillas de Typeform generó **30,000 registros orgánicos no de marca y $3M/año en LTV**. El patrón:
- Una página indexable por plantilla en `/templates/[slug]`.
- H1 con la keyword, descripción de 150+ palabras, screenshot, "cuándo usar esto", CTA "usar esta plantilla".
- Plantillas relacionadas al final de cada página (enlazado interno = efecto compuesto de SEO).
- 100 plantillas para el día 30, 300 para el día 90 es el objetivo realista.

### 4. Listicles "lo mejor de" que tú mismo escribiste

Escribe roundups honestos de tu propia categoría: `/blog/best-[categoria]-tools-2026`. Inclúyete a ti mismo + 10 competidores con reseñas reales. Estas posicionan para consultas de categoría Y sirven como referencias canónicas que citan los motores de IA.

### 5. Páginas de integración (cuando las integraciones salen)

Cada integración = una landing page en `/integrations/[partner]`. Sigue el playbook de Zapier: Zapier obtiene **~2.6M visitas orgánicas mensuales** de páginas de integración programáticas (~15% de su tráfico orgánico total).

---

## GEO (Generative Engine Optimization)

En 2026, 30–50% de las consultas de "investigar una herramienta" ocurren dentro de ChatGPT, Claude, Perplexity o Google AI Overviews sin tocar nunca una página de búsqueda tradicional. Los directorios también importan aquí — los motores de IA recurren mucho a directorios de alto DR al generar respuestas. Pero las *páginas de destino* también necesitan estar optimizadas para GEO.

### Tácticas que logran que citen tus páginas

1. **Un H1 por página, jerarquía de encabezados secuencial.** 2.8× más tasa de citación. El 87% de las páginas citadas usa un único H1.
2. **Contenido denso y factual con estadísticas citables.** Los motores de IA prefieren números específicos ("3× más rápido que X") sobre afirmaciones vagas.
3. **Schema de FAQ en cada landing page.** Los motores de IA valoran mucho el JSON-LD de `FAQPage` para la extracción de respuestas.
4. **Tablas de comparación.** Extraíbles, estructuradas — exactamente lo que necesita una respuesta de IA.
5. **Párrafo explícito de "qué es esto" en las primeras 100 palabras.**
6. **Consigue que te citen en Reddit y Hacker News.** Claude y Perplexity indexan esto mucho. Las menciones genuinas en r/SaaS y HN cuentan como combustible de entrenamiento.
7. **Publica investigación original.** "Analizamos 10,000 [cosas] y encontramos X" se convierte en la cita principal para cualquiera que escriba sobre ese tema.
8. **Reclama Crunchbase, la página de empresa en LinkedIn y las entradas de Wikidata.** Las tres alimentan los corpus de entrenamiento de IA.
9. **Si aplica, lista en registros MCP con calificaciones A/B** (Glama en particular). Los LLMs recurren a estos al responder preguntas sobre MCP.

### Medición

Revisa manualmente cada mes: pregunta a ChatGPT, Claude y Perplexity "¿cuáles son las mejores herramientas de [categoría]?" y registra dónde aparece el producto. Las herramientas gratuitas de tracking GEO (GeoTracker, llmrefs) automatizan esto.

---

## Comunidad y Distribución Continua

Los directorios son de un solo tiro. La comunidad es continua. Ambos alimentan el mismo funnel.

### Reddit (regla 90/10)

El 90% de la actividad debe ser genuinamente útil; solo el 10% promocional. Violar esto provoca shadowban.

**Subreddits de alto valor (en orden):**
- **r/SideProject** (200K+) — amigable con la promo, se aceptan anuncios de lanzamiento.
- **r/SaaS** (300K+) — los hilos "Share Your SaaS" son ventanas explícitas de promo.
- **r/startups** (1.7M) — hilo Feedback Friday.
- **r/Entrepreneur** (3.5M) — hilo promocional semanal.
- **r/nocode**, **r/IndieHackers**, **r/alphaandbetausers** — amigables.
- **r/webdev**, **r/artificial**, **r/LocalLLaMA** — estrictos, solo técnico.

**Qué funciona:** números reales (MRR, registros, churn), screenshots, estructura "qué probé / qué pasó / qué haría diferente", mini casos de estudio con una lección clara. **Qué falla:** hype, afirmaciones vagas, posts de "mira mi nueva herramienta", pedir upvotes.

### LinkedIn (canal B2B principal)

El 80% de los leads sociales B2B vienen de LinkedIn. Cadencia: **3–5 posts/semana** — menos pierde momentum, más causa fatiga.

Tipos de contenido ordenados por engagement 2026:
1. Historias personales con lecciones de negocio (1.5–2× el engagement promedio)
2. Datos/investigación original (1.3–1.5×)
3. Posturas contrarian sobre la industria (1.2–1.5×)
4. Carruseles de documentos con 8–12 slides (1.3–1.8×)

### Twitter/X (canal indie hacker + dev)

Hilos de build-in-public sobre arquitectura, ingresos, decisiones. Los deep-dives técnicos son indexados por Google + Claude + Perplexity → GEO indirecto.

### Indie Hackers

- Lanza un hilo de build-in-public el día de lanzamiento en PH.
- Publica actualizaciones semanales: ingresos, envíos, aprendizajes. Los posts sin ingresos funcionan si la lección es honesta.
- Comenta 10× más de lo que publicas para construir karma antes de tus propios enlaces.

### Dev.to + Hashnode

Todo post técnico sustancial = backlink dofollow + alcance de audiencia dev. Cross-postea con URL canónica de vuelta al blog principal.

---

## KPIs y Seguimiento

Rastrea semanalmente. Si un número no se mueve, investiga — no envíes más directorios sin más.

| Métrica | Día 0 | Objetivo día 30 | Objetivo día 90 |
|---|---|---|---|
| Domain Rating (DR) | 0 | 20 | 30+ |
| Dominios referentes | 0 | 30 | 80+ |
| Páginas indexadas | — | 50 | 200+ |
| Clics orgánicos/día | 0 | 30 | 200+ |
| Listados de directorio en vivo | 0 | 50 | 70+ |
| Reseñas en G2 | 0 | 10 | 25 |
| Reseñas en Capterra | 0 | 5 | 15 |
| Citas de IA (revisión manual) | 0 | 3 | 15+ |
| Registros desde referidos de directorios | 0 | 50 | 300 |
| Registros desde páginas de alternativas/caso de uso | 0 | 20 | 300 |

---

## Qué NO Hacer

1. **No pagues por servicios de envío a directorios** (paquetes de $60–$200). Todo el punto es que son gratis. Es una tarde de copiar y pegar.
2. **No envíes a directorios spam** (DR menor a 10, sin tráfico, sin calidad editorial). Diluyen tu perfil de backlinks y la detección de spam de Google puede penalizarte.
3. **No envíes con el posicionamiento equivocado.** Vuelve a leer la tabla de posicionamiento por tier. Las descripciones genéricas desperdician el listado.
4. **No trates los directorios como todo tu GTM.** Son la base. El contenido + la comunidad + las reseñas son lo que realmente convierte.
5. **No te saltes las reseñas en G2/Capterra.** Los listados sin reseñas están muertos. Ejecuta el protocolo 10-en-30 o no envíes.
6. **No pidas upvotes en Product Hunt.** El algoritmo 2026 lo penaliza. Pide **feedback**.
7. **No modifiques listados de directorios viejos cada semana.** Envía una vez, revisa trimestralmente.
8. **No envíes antes de que exista la página de destino.** El equity de enlaces necesita un destino.
9. **No dupliques descripciones entre directorios.** Los motores de IA penalizan el contenido duplicado.
10. **No mientas en las páginas de comparación.** Los motores de IA hacen referencias cruzadas y degradan las mentiras.
11. **No sobreindexes en el pico del día de lanzamiento.** El flywheel son plantillas + alternativas + reseñas + contenido continuo — no un solo día de PH.
12. **No olvides Crunchbase, la página de empresa en LinkedIn y Wikidata.** Estos alimentan los corpus de entrenamiento de IA e importan para GEO.

---

## Preguntas Específicas de la Tarea

1. **¿Qué estás lanzando?** (La categoría cambia la mezcla de tiers — IA vs SaaS tradicional vs no-code vs herramienta dev.)
2. **¿Cuándo es el día de lanzamiento?** (Los assets de Fase 0 necesitan 7 días de preparación.)
3. **¿Tienes páginas de destino construidas?** (Alternativas, casos de uso, plantillas — si no, constrúyelas primero.)
4. **¿Tienes un hunter de Product Hunt asegurado?** (Opcional pero suma ~15% de impulso el primer día. El calentamiento de 3 semanas se requiere de todas formas.)
5. **¿A cuántos usuarios beta puedes pedirles reseñas?** (Necesitas 20 para lograr 10.)
6. **¿Tienes un ángulo de MCP o agente?** (Si sí, los registros Tier 4 son un foso real.)
7. **¿Integraciones existentes?** (Si sí, los marketplaces Tier 7 son los backlinks de mayor DR disponibles.)
8. **¿Tamaño de la lista de email?** (Necesario para el tráfico cálido del día de lanzamiento en PH — 100+ es el mínimo.)
9. **¿DR actual y cantidad de dominios referentes?** (Línea base para medir el efecto compuesto.)

---

## Formato de Salida

Cuando el usuario pida un plan de directorios, entrega:

1. **Evaluación de preparación** — qué elementos de la Fase 0 faltan, cuáles bloquean el envío
2. **Selección de tiers** — qué tiers aplican, cuáles saltar, por qué
3. **Orden de envío** — lotes de semana 1 / semana 2 / semana 3
4. **Lista de páginas de destino** — qué construir primero si falta
5. **Variantes de posicionamiento** — el copy real por tier (de `references/positioning-variations.md`)
6. **Cronograma de preparación de 3 semanas para PH** — mapeado a fechas de calendario si se conoce el día de lanzamiento
7. **Plan de reseñas 10-en-30** — a quién pedir, cuándo, cómo
8. **Objetivos semanales** — directorios enviados, reseñas, movimiento de DR
9. **Tracker** — enlaza o incluye el CSV de `references/submission-tracker-template.csv`

Mantén el plan accionable. Cada elemento debe ser algo que el usuario pueda hacer hoy.

---

## Skills Relacionadas

- **launch-strategy** — el momento de lanzamiento más amplio, framework ORB, enfoque de cinco fases
- **programmatic-seo** — páginas de destino (alternativas, integraciones, plantillas) hacia donde deben fluir los backlinks
- **competitor-alternatives** — el patrón de página `/alternatives/[herramienta]`
- **ai-seo** — optimización GEO para citación de IA
- **content-strategy** — contenido editorial que atrae inclusiones en listicles "lo mejor de"
- **free-tool-strategy** — lead magnets para páginas de destino
- **community-marketing** — mecánicas de Reddit, Indie Hackers, comunidad de Slack
- **schema-markup** — JSON-LD de FAQ + Product + Organization para GEO
