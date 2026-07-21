# Descubrimiento por Señal de Demanda (Encuentra a Tus Primeros Clientes)

Las otras tres ramas construyen una lista a partir de quién *encaja* (firmográficos, tecnográficos, proximidad). Esta rama construye una lista a partir de quién ya está mostrando el dolor — el motion de etapa temprana donde tienes un producto y una corazonada pero sin base de clientes todavía, y necesitas tus primeros diez conversaciones reales. No estás filtrando una base de datos; estás minando el discurso público reciente en busca de personas que describen exactamente el problema que resuelves, y luego vinculando cada prospecto a la evidencia.

Usa esta rama cuando el usuario esté en etapa pre-product-market-fit, lanzando algo nuevo, o buscando **design partners, beta users, o primeros clientes** en lugar de una lista de outbound escalada. Reutiliza las cinco fases compartidas y todas las barreras de cumplimiento en SKILL.md; lo que cambia es dónde buscas, cómo puntúas, y qué entregas.

Crédito del patrón: el marco aquí está re-expresado a partir de la skill open-source de Codex `first-customer-finder` (Kappaemme, MIT), extendida con nuestras herramientas de recencia en vivo.

## Qué hace diferente a esta rama

| | Ramas de construcción de lista (SaaS / B2B / SMB) | Descubrimiento por señal de demanda |
|---|---|---|
| Empieza desde | Un ICP firmográfico | Un problema descrito |
| Fuentes | Bases de datos de contactos (Apollo, ZoomInfo, Clay) | Discurso público (foros, reseñas, issues, posts) |
| Paso de contacto | Enriquecer + verificar entregabilidad de email | Ninguno — contáctalos donde ya publicaron |
| Gana en | Cobertura a escala | 10 matches fuertes respaldados por evidencia por encima de una lista larga |
| Salida | Una hoja de leads puntuada | Un reporte de evidencia + plan de outreach manual |

Un prospecto aquí sin un dolor, necesidad, o señal de timing citada es un fit especulativo — **no** pertenece a la shortlist primaria. La evidencia es el boleto de entrada.

## Paso 1 — Brief de producto (antes de cualquier búsqueda)

Define, con suficiente especificidad como para *rechazar* matches débiles:

- el producto y el resultado prometido
- el usuario primario y el comprador económico (a menudo diferentes)
- el trabajo urgente por hacer (job to be done)
- la alternativa o workaround actual que se está reemplazando
- el probable disparador de adopción (qué hace que ahora sea el momento)
- restricción de geografía / idioma
- descalificadores claros

No empieces la recolección amplia hasta que el brief esté afilado. Toma datos de `.agents/product-marketing.md` si existe.

## Paso 2 — Mina los cinco buckets de señales

Busca en varios ángulos, no una sola query repetida. Adapta el lenguaje a cómo realmente habla la audiencia (mina su vocabulario de contenido orgánico primero — ver la nota de lenguaje orgánico del hook-system de ad-creative para la misma idea).

1. **Demanda explícita** — "busco," "recomiéndenme una herramienta para," "alternativa a [X]," "existe algo que," "cómo manejan ustedes."
2. **Dolor** — "toma horas," "es súper manual," "odio que," "siempre se rompe," "la mayor frustración con," "por qué no existe."
3. **Workaround** — hojas de cálculo, copy-paste, una VA, una cadena de Zapier, un script, una plantilla, cualquier paso manual repetido que tu producto reemplazaría.
4. **Cambio (switching)** — cancelación, migración, "mudándose de [competidor]," una función faltante, una queja de precios, frustración con un competidor.
5. **Timing** — un lanzamiento público, una nueva contratación para la función relevante, expansión, un nuevo flujo de trabajo o regulación, un anuncio de integración — un evento *actual* que hace que el producto sea relevante ahora.

**Usa nuestra ventaja de recencia en vivo.** Una skill genérica depende de lo que arroje una búsqueda web; tú tienes algo mejor:
- **last30days** — señales de Reddit, Hacker News, X, YouTube, y web de los últimos 30 días. Esta es la herramienta de mayor valor para esta rama: la recencia *es* la señal de timing.
- **social-fetch** — trae el contenido completo de un post/hilo específico que encuentres, normalizado.
- **scraping** / **Firecrawl** / **Browserbase** — lee la página pública original (un hilo de foro, un issue de GitHub, una reseña), nunca califiques a partir de un fragmento de búsqueda solamente.
- **deep-research** — para un barrido multi-fuente con verificación adversarial cuando el wedge es amplio.
- **competitor-profiling** / **customer-research** — señales de cambio de competidor y minería de reseñas para el lenguaje del dolor.

## Paso 3 — Mezcla de fuentes (solo público)

Foros e hilos de comunidad pública · posts sociales públicos y respuestas · reseñas de producto y de marketplaces de apps · issues y solicitudes de funciones en GitHub · páginas públicas de empresas, ofertas de empleo, changelogs, anuncios de lanzamiento · posts "busco una herramienta" y directorios.

Evita grupos privados, comunidades con acceso restringido, data brokers, datasets filtrados, y cualquier fuente cuyos términos prohíban el acceso — las mismas barreras de cumplimiento que cualquier otra rama (ver SKILL.md), incluyendo la regla de no-rasgos-sensibles.

**Solo contexto profesional/de negocio.** Califica y contacta únicamente donde alguien esté publicando en una capacidad profesional o de negocio sobre un problema de trabajo (un fundador en un hilo de indie-hackers, un desarrollador en un issue de GitHub, un líder de operaciones en un subreddit de su rol). Excluye por completo los contextos de angustia personal — salud, dificultad financiera, adicción, duelo, o cualquier foro de apoyo al consumidor donde la gente está desahogando problemas personales, incluso si tu producto es tangencialmente relevante. Cuando el motion es genuinamente de consumidor (B2C), un post público de dolor no es por sí solo una base legal para el outreach en frío — contacta a las personas a través de las normas propias del canal (responde públicamente donde responder es lo esperado) y nunca envíes un DM a un extraño a partir de un post personal.

Cita mínimamente, parafrasea por defecto, y enlaza cada señal material de dolor o timing.

## Paso 4 — Puntúa por fit de demanda (no por fit de ICP)

Las ramas de construcción de lista puntúan Hot/Warm/Cold según el fit de ICP. Esta rama puntúa de 0–100 en **fit de demanda** — qué tan fuertemente la evidencia dice que este prospecto específico quiere esta cosa específica ahora. Puntúa cada dimensión de 0–5:

| Dimensión | Peso | Qué mide |
|---|---|---|
| **Fuerza del dolor** | 25% | Directitud, severidad, repetición, y costo del problema declarado |
| **Fit de producto** | 25% | Qué tan directamente tu producto resuelve el trabajo evidenciado |
| **Timing** | 20% | Frescura + presencia de un disparador actual |
| **Alcanzabilidad pública** | 15% | Existe un camino de contacto público/profesional natural y relevante |
| **Calidad de evidencia** | 15% | Especificidad, confiabilidad de la fuente, confianza de que la señal es realmente suya |

```
score = dolor/5*25 + fit/5*25 + timing/5*20 + alcanzabilidad/5*15 + evidencia/5*15
```

| Banda | Significado |
|---|---|
| **80–100** | Candidato fuerte a primer cliente |
| **65–79** | Prometedor — validar rápido |
| **50–64** | Plausible pero le falta una señal material |
| **Menos de 50** | No incluir en la shortlist primaria |

Una solicitud explícita antigua todavía puede contar — pero baja el puntaje de timing y etiqueta la fecha. Una empresa que solo coincide con la industria sin un disparador evidenciado *no* es un prospecto calificado aquí.

### Etapas del prospecto

- **Alta intención** — solicitando públicamente una solución o cambiando activamente
- **Consciente del problema** — describiendo claramente el dolor o un workaround costoso
- **Disparador presente** — un evento de negocio actual hace relevante al producto
- **Fit potencial** — coincide con el ICP, evidencia incompleta → mantener *fuera* de la shortlist primaria

### Registro de evidencia (por prospecto calificado)

Nombre mostrado (empresa/proyecto/profesional público) · título de fuente + URL · fecha de publicación visible o "fecha no disponible" · tipo de fuente · la señal concisa de dolor/timing · evidencia observada vs. inferencia (etiqueta cuál) · desglose del puntaje · advertencia de frescura cuando la señal esté vieja.

## Paso 5 — Redacta el outreach, nunca lo envíes

Recomienda el canal más natural *ya asociado a la fuente*, y solo donde responder sea parte normal de ese canal (responder en el hilo público, responder vía un perfil profesional público). No conviertas un post público en un DM privado que el autor no invitó, y nunca contactes a alguien a partir de un post de angustia personal. Redacta una apertura, de menos de ~90 palabras, con esta forma:

1. menciona el contexto público de forma natural
2. conéctalo con el problema exacto
3. explica el producto en una oración
4. haz una pregunta de baja fricción

Nunca reclames familiaridad que no tienes, nunca inventes detalles personales, y nunca envíes automáticamente: ningún mensaje, conexión, follow, comentario, envío de formulario, o registro de CRM a menos que el usuario autorice esa acción por separado. Esta es la postura manual/con puerta de marketing-loops.

## Paso 6 — Entrega el reporte de evidencia

Lidera con la evidencia más accionable, en este orden:

1. **Veredicto** — ¿tiene el producto señal alcanzable de cliente temprano, o todavía no? (Un honesto "todavía no, y aquí está por qué" es una respuesta válida.)
2. **ICP** — comprador, trabajo, disparador, descalificadores.
3. **Prospecto principal** — el candidato individual más fuerte respaldado por evidencia y por qué ahora.
4. **Shortlist de prospectos** — por prospecto: fuente, señal de dolor, puntaje de fit de demanda, etapa, por-qué-ahora, canal, apertura.
5. **Patrones repetidos** — dolores y disparadores que se repiten entre prospectos (esto es oro para tu posicionamiento y mensajería).
6. **Plan de outreach manual de siete días** — una secuencia de validación de bajo volumen (ej. contactar a los 3 principales con una pregunta basada en la fuente; compartir un mockup solo después de que confirmen el dolor; apuntar a tres conversaciones y un compromiso de design partner).
7. **Límites** — qué evidencia falta y qué debe confirmarse mediante conversaciones reales.

Para una versión HTML independiente y compartible de este reporte, el patrón generador JSON→HTML en [creative-review-page.md](../../ad-creative/references/creative-review-page.md) de ad-creative es el modelo (escapa cada valor; mantenlo autocontenido).

## Las reglas de honestidad (no negociables)

- Cada prospecto primario enlaza a al menos una señal pública real. Sin señal, sin shortlist.
- Etiqueta la salida como **"cliente potencial basado en señales públicas"** — nunca "interesado," "va a comprar," o "ha dado su consentimiento."
- Prefiere diez matches fuertes por encima de una lista larga y genérica. Haz visible la incertidumbre y la evidencia vieja.
- Personaliza a partir de la fuente citada, no de suposiciones inventadas.
- Trata la shortlist como una hipótesis de investigación por validar mediante conversaciones, no como una base de datos de clientes.
