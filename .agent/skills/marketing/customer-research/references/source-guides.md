# Investigación de Clientes — Guías de Fuentes

Playbooks detallados, fuente por fuente, para reunir inteligencia de clientes en los puntos de encuentro digitales.

---

## Investigación en Reddit

### Encontrar los Subreddits Correctos

Empieza identificando dónde pasa el tiempo tu ICP, no dónde se habla de tu producto.

**Métodos de descubrimiento:**
- Busca `site:reddit.com "[puesto] tools"` o `site:reddit.com "[categoría del problema] software"`
- Usa [herramientas de búsqueda de subreddits](https://www.reddit.com/subreddits/search) con palabras clave del espacio del problema
- Mira qué subreddits aparecen en resultados de Google al buscar los problemas de tu ICP
- Revisa qué subreddits mencionan los clientes de tus competidores en las reseñas

**Subreddits de alto valor comunes por categoría:**
- SaaS B2B: r/sales, r/marketing, r/entrepreneur, r/startups, r/smallbusiness
- Herramientas de desarrollo: r/programming, r/devops, r/webdev, r/cscareerquestions
- Analítica/datos: r/analytics, r/dataengineering, r/BusinessIntelligence
- Marketing: r/PPC, r/SEO, r/emailmarketing, r/content_marketing
- RRHH/reclutamiento: r/recruiting, r/humanresources, r/jobs
- Finanzas/operaciones: r/accounting, r/financialplanning, r/projectmanagement

### Operadores de Búsqueda

```
site:reddit.com/r/[subreddit] "[palabra clave]"
site:reddit.com "[problema]" "recommend" OR "suggestion" OR "alternative"
site:reddit.com "[nombre del competidor]" "vs" OR "alternative" OR "switched"
```

### Qué Buscar

**Tipos de posts de alta señal:**
- "¿Qué herramientas usan para X?" → revela alternativas y vocabulario
- "Frustrado con [competidor], busco alternativas" → revela dolor y disparadores de cambio
- "¿Cómo manejan X?" → revela flujo de trabajo y workarounds
- "¿Vale la pena [tu categoría]?" → revela objeciones y criterios de evaluación
- Hilos de quejas sobre competidores → revela brechas que podrías llenar

**Qué extraer:**
- El problema exacto descrito en el post
- Las soluciones más votadas (¿qué recomiendan realmente los que están en el día a día?)
- Quejas sobre soluciones existentes en los comentarios
- El lenguaje usado — anota palabras y frases específicas
- Patrones de upvotes — consenso vs. controversia

### Herramientas
- Búsqueda nativa de Reddit (limitada pero rápida)
- Google: `site:reddit.com [consulta]` (mejores resultados)
- Pullpush.io — busca posts archivados de Reddit (bueno para hilos antiguos)

---

## Minería de G2 y Sitios de Reseñas

### Reseñas de Tu Propio Producto

Léelas en este orden para obtener la máxima señal:

1. **Reseñas de 3 estrellas** — son las más honestas. El cliente lo apreció lo suficiente como para quedarse, pero sintió que algo faltaba.
2. **Reseñas de 1 estrella** — entiende los modos de falla. Separa los problemas de producto de los problemas de soporte/onboarding.
3. **Reseñas de 5 estrellas** — extrae el lenguaje de "lo que aman". Son tus puntos de prueba.
4. **Reseñas de 4 estrellas** — suelen contener "lo único que desearía…" escondido entre elogios.

**Qué extraer:**
- Para qué dicen que lo usan (el job to be done)
- Qué dicen que es lo más difícil o frustrante
- Con qué lo comparan ("viniendo de [X]", "mejor que [Y]")
- Señales de industria y rol en los perfiles de quienes reseñan

### Reseñas de Competidores en G2

Las reseñas de 4 estrellas de competidores son oro — clientes a quienes les gusta el producto pero aun así tienen quejas.

**Estructura de G2 a explotar:**
- "¿Qué es lo que más te gusta?" → sus fortalezas (tu inteligencia para el battlecard)
- "¿Qué te disgusta?" → sus debilidades (tus oportunidades)
- "¿Qué problemas estás resolviendo?" → el job to be done

**Capterra** tiene una estructura similar. **Trustpilot** se inclina hacia B2C. Las reseñas de **AppSumo** son útiles para SaaS de PyME/prosumer.

### Plantilla de Minería de Reseñas

Para las reseñas de 4 estrellas de cada competidor, extrae:

| Categoría | Notas |
|----------|-------|
| Job to be done | ¿Por qué usan el producto? |
| Elogio principal | ¿Qué aman (y que podría ser difícil de igualar para ti)? |
| Queja principal | ¿Qué los frustra? |
| Contexto de cambio | ¿Mencionaron haber cambiado desde otra solución? |
| Necesidad insatisfecha | "Ojalá pudiera…" o "Sería mejor si…" |

---

## Indie Hackers y Product Hunt

### Indie Hackers

Señal fuerte para el ICP de fundadores/builders/PyME.

**Dónde buscar:**
- Posts de "Ask IH": preguntas sobre problemas que resuelve tu producto
- Posts de hitos (milestones): cuando los fundadores describen su stack, revelan preferencias de herramientas y dolor
- Hilos de comentarios en lanzamientos de productos de tu categoría

**Búsqueda:** `site:indiehackers.com "[problema]"` o usa la búsqueda nativa de IH.

### Product Hunt

Las **pestañas de discusión** en productos competidores son una mina de oro de investigación:

- Preguntas hechas = preocupaciones previas a la compra = objeciones
- Comentarios = reacciones de early adopters = indicadores adelantados de recepción
- Colecciones de "Alternativas a X" revelan el panorama competitivo tal como lo ven los usuarios

---

## Hacker News

Señal fuerte para el ICP técnico/desarrollador. Se inclina hacia builders y escépticos.

**Búsquedas de alto valor:**
- `site:news.ycombinator.com "[competidor o categoría]"`
- Hilos de "Ask HN: best tools for X"
- Posts de "Show HN" de competidores — lee los comentarios escépticos

**Qué es diferente en HN:**
- Los usuarios son más propensos a criticar la arquitectura subyacente y el modelo de negocio
- Opiniones fuertes sobre modelos de precios (especialmente cualquier cosa basada en suscripción)
- Objeciones de primeros principios que quizás no escuches en otro lado

---

## Investigación en LinkedIn

### Posts y Comentarios

Busca posts de profesionales describiendo sus flujos de trabajo:
- "[Rol] en [tamaño de empresa]" + palabra clave del problema
- Historias de "Antes usábamos [método viejo] pero ahora [método nuevo]"
- Los posts que piden recomendaciones de herramientas reciben comentarios de compradores activos

### Ofertas de Empleo

Una oferta de empleo es la admisión de una empresa de que tiene un punto de dolor.

**Qué buscar:**
- ¿Qué herramientas aparecen como "deseable" vs. "requerido"? (revela el stack y herramientas adyacentes)
- ¿Qué métricas y resultados se mencionan en la descripción del rol?
- ¿En qué pasa la mayor parte del tiempo el rol? (revela el job to be done)

**Búsqueda:** `site:linkedin.com/jobs "[título del rol]" "[herramienta o categoría relevante]"`

---

## Comentarios de YouTube

### Encontrar Videos de Alta Señal

- Videos tutoriales sobre problemas que resuelve tu producto
- Videos de "Mejores herramientas para X en [año]"
- Demos de productos competidores y walkthroughs

**Qué buscar en los comentarios:**
- "¿Esto funciona para [caso de uso específico]?" → casos límite y necesidades insatisfechas
- "Probé esto pero…" → puntos de falla
- "¿Y [competidor]?" → evaluación activa
- Marcas de tiempo con preguntas → puntos de confusión en el flujo de trabajo

---

## Investigación en Twitter / X

### Operadores de Búsqueda

```
"[competidor]" -filter:replies min_faves:10
"[palabra clave del problema]" "anyone know" OR "recommend" OR "alternative"
"[categoría] is broken" OR "frustrated with [categoría]"
```

### Qué Encontrar

- Quejas en tiempo real sobre competidores
- Profesionales discutiendo su stack
- Influencers/líderes de opinión a los que sigue tu ICP (útil para distribución)

---

## Investigación en Blogs y Foros

### Contenido de Comparación

Google: `"[competidor 1] vs [competidor 2]"` o `"mejor software de [categoría] [año]"`

Lee los comentarios de estos posts — las personas que encuentran contenido de comparación están evaluando activamente. Sus comentarios son preguntas que tu proceso de ventas debería responder.

### Comunidades de Nicho

- **Comunidades de Slack**: Muchas industrias tienen grupos de Slack públicos o semi-públicos. Busca "comunidad de Slack de [industria]".
- **Servidores de Discord**: En crecimiento para comunidades de desarrolladores y creadores.
- **Grupos de Facebook**: Siguen siendo fuertes para PyME, e-commerce, agencias, y el ICP de coaches/consultores.
- **Comunidades de Circle/Mighty Networks**: Revisa si hay comunidades de pago en el espacio de tu ICP.

---

## Investigación B2C y de Apps de Consumo

La investigación B2C requiere fuentes distintas a las del SaaS B2B. Los compradores de consumo no se reúnen en LinkedIn ni en G2 — dejan rastros en app stores, redes sociales y comunidades construidas alrededor de la actividad que sirve tu producto.

### Reseñas en App Stores (iOS App Store / Google Play)

Una de las fuentes más ricas y sin filtro para productos móviles/de consumo.

**Léelas en este orden:**
1. **Reseñas de 1-2 estrellas** — modos de falla, expectativas insatisfechas, picos de frustración
2. **Reseñas de 3 estrellas** — trade-offs honestos y feedback de "está bien pero…"
3. **Reseñas de 5 estrellas** — qué aman en sus propias palabras (puntos de prueba y posicionamiento)

**Qué extraer:**
- Para qué job contrataron la app ("Uso esto para…")
- El momento en que dejó de funcionarles
- Con qué lo compararon o desde qué se cambiaron
- Lenguaje emocional — "Me encanta cómo…", "Me frustra tanto que…"

**Tip de búsqueda:** Ordena por "Más reciente" para obtener señal fresca, luego por "Más crítico" para temas de dolor.

### Reseñas de Amazon (para productos físicos o software con presencia en Amazon)

El mismo orden de prioridad que en app stores: primero las reseñas de 3 estrellas.

**Análogo de G2 para SaaS de consumo**: Trustpilot, Sitejabber, y agregadores de reseñas específicos de producto.

### Comunidades de Consumo en Reddit

El Reddit B2C es muy vertical — ve al subreddit de hobbies/estilo de vida, no a los generales.

**Ejemplos por tipo de producto:**
- Apps de fitness: r/running, r/loseit, r/fitness, r/MyFitnessPal
- Finanzas personales: r/personalfinance, r/financialindependence, r/ynab
- Productividad/notas: r/productivity, r/Notion, r/ObsidianMD
- Viajes: r/travel, r/solotravel, r/digitalnomad
- Crianza: r/Parenting, r/beyondthebump, r/daddit

**Patrón de búsqueda:** `site:reddit.com/r/[comunidad] "[nombre de la app O problema]"`

### Comentarios de TikTok e Instagram

Alta señal para productos de consumo con atractivo visual/de estilo de vida.

**Cómo encontrar señal:**
- Busca en TikTok "reseña de [nombre del producto]" o "vale la pena [producto]"
- Mira los 5-10 videos principales; lee TODOS los comentarios — no solo los más gustados
- En Instagram, revisa los posts etiquetados de usuarios reales (no posts de marca)

**Qué extraer:**
- Preguntas en los comentarios = necesidades insatisfechas o posicionamiento poco claro
- "¿Esto funciona para…?" = jobs para los que quieren contratarlo
- Comentarios de "Me cambié de X" = disparadores de cambio
- Quejas sobre precio, funciones faltantes, o promesas incumplidas

### Comentarios de YouTube (Consumo)

Mismo enfoque que en B2B pero con tipos de video diferentes:

- "Reseña honesta de la app X" o "la app X después de 6 meses"
- Videos comparativos de "Mejores apps de [categoría] [año]"
- Videos de unboxing o "configuración" para hardware/productos físicos

Los comentarios en videos de reseñas son especialmente valiosos — son personas activamente en fase de consideración.

### Plataformas de Comunidades de Consumo

- **Grupos de Facebook**: Siguen siendo dominantes en muchos verticales de consumo (crianza, fitness, servicios locales, hobbies)
- **Servidores de Discord**: En crecimiento para gaming, herramientas para creadores, productividad, cripto, comunidades de estilo de vida
- **Nextdoor**: Útil para negocios de servicios locales
- **Quora**: Preguntas extensas revelan ansiedad de decisión y criterios de evaluación

---

## SparkToro (Inteligencia de Audiencia)

SparkToro es una herramienta de investigación de audiencia conductual. En lugar de minar posts y comentarios individuales, agrega datos de clickstream, búsqueda y redes sociales para mostrar qué hace tu audiencia a escala — qué lee, ve, escucha, sigue y busca.

### Cuándo Usar SparkToro vs. Investigación Manual

- **SparkToro primero** cuando necesitas entender dónde pasa el tiempo tu ICP, qué contenido consume y a qué influencers sigue — responde estas preguntas en segundos con datos agregados
- **Investigación manual primero** (Reddit, G2, comunidades) cuando necesitas lenguaje en bruto, citas exactas, contexto emocional y el "por qué" detrás del comportamiento
- **Mejor combinados**: Usa SparkToro para identificar qué podcasts, subreddits y sitios web importan, y luego mina esas fuentes manualmente para obtener lenguaje de voz del cliente

### Consultas Clave para Ejecutar

**Por competidor:**
- "Personas que siguen a @competidor" — revela afinidades de audiencia compartidas
- "Personas que visitan competidor.com" — muestra qué más consumen

**Por descripción de audiencia:**
- "Personas que hablan frecuentemente de [tema]" — encuentra comportamientos de audiencia
- "Personas cuya bio contiene [puesto]" — perfila un segmento basado en rol

**Por tu propia audiencia:**
- "Personas que visitan tudominio.com" — entiende tu audiencia real
- Compara contra perfiles de audiencia de competidores para encontrar brechas

### Qué Extraer

| Tipo de Dato | Qué Te Dice | Para Qué Usarlo |
|-----------|------------------|-------------|
| Sitios web más visitados | Dónde lee tu audiencia | Alianzas de contenido, objetivos de guest posting |
| Podcasts principales | Qué escuchan | Guest en podcasts, decisiones de patrocinio |
| Canales de YouTube principales | Qué miran | Estrategia de contenido en video, ubicaciones de anuncios |
| Subreddits principales | Dónde discuten | Participación en comunidades, segmentación de anuncios en Reddit |
| Palabras clave de búsqueda | Qué buscan en Google | Planeación de SEO y de temas de contenido |
| Temas de prompts de IA | Qué le preguntan a herramientas de IA | Oportunidades de contenido emergentes |
| Cuentas sociales seguidas | Quién los influencia | Alianzas con influencers, co-marketing |
| Demografía | Quiénes son | Construcción de personas, segmentación de anuncios |

### Ponderación de Fuentes

Los datos de SparkToro están agregados y anonimizados — muestran patrones, no opiniones individuales. Trátalos como:
- **Alta confianza** para datos conductuales (qué visitan, siguen, buscan)
- **Confianza media** para datos demográficos (autorreportados, pueden estar incompletos)
- **No un sustituto** de la investigación cualitativa (no captura lenguaje, emociones, ni el "por qué")

### Limitaciones

- Plan gratuito: 5 reportes/mes, resultados superficiales (top 5-10)
- Sin API pública — toda la investigación se hace por interfaz web
- Se inclina hacia inglés y hacia EE. UU.
- Muestra qué hacen las audiencias, no por qué — combínalo con fuentes cualitativas

Ver [tools/integrations/sparktoro.md](../../tools/integrations/sparktoro.md) para detalles completos de la herramienta y precios.

---

## Organizar Tu Investigación

Usa un sistema de etiquetado simple en todas las fuentes:

| Etiqueta | Significado |
|-----|---------|
| `#dolor` | Un problema o frustración |
| `#disparador` | Un evento que provocó la búsqueda |
| `#resultado` | Cómo se ve el éxito |
| `#lenguaje` | Frases exactas que vale la pena usar en el copy |
| `#alternativa` | Otra solución que consideraron o usan |
| `#objeción` | Razón para dudar o no comprar |
| `#competidor` | Cualquier cosa sobre un producto competidor |

Mantén un documento continuo con columnas: Fuente | Fecha | Cita | Etiquetas | Notas

Después de 20-30 entradas, surgirán patrones. Busca citas que aparezcan en múltiples fuentes no relacionadas — esos son tus insights de mayor confianza.

---

## Confiabilidad de Fuentes y Puntuación de Confianza

No todas las fuentes tienen el mismo peso. Usa esta guía al asignar etiquetas de confianza.

### Ponderación de Fuentes

| Fuente | Fuerza de la Señal | Sesgo a Considerar |
|--------|----------------|--------------|
| Entrevistas a clientes (sin que se pregunte) | Muy alta | Muestra pequeña; sesgo de selección hacia clientes comprometidos |
| Entrevistas de ganancia/pérdida (win/loss) | Alta | Solo memoria reciente; racionalización común |
| Reseñas de app store / G2 | Alta | Se inclina hacia opiniones fuertes (amor u odio) |
| Reddit / posts de comunidades | Media-alta | Se inclina hacia lo técnico, lo escéptico, minorías vocales |
| Tickets de soporte | Media | Se inclina hacia problemas; la mayoría silenciosa no está representada |
| Encuesta (abierta) | Media | Condicionada por el enfoque de la pregunta |
| Encuesta (opción múltiple) | Baja-media | Artefactos de las opciones que proporcionaste |
| Comentarios textuales de NPS | Media | Correlaciona con el puntaje; provocado por el momento de la encuesta |
| Comentarios de YouTube/TikTok | Media | Se inclina hacia espectadores comprometidos; performance social |
| Datos de audiencia de SparkToro | Media-alta | Datos conductuales agregados; fuerte para el "qué" pero no para el "por qué" |
| Ofertas de empleo | Baja-media | Aspiracional, no necesariamente refleja el dolor actual |

### Etiquetas de Confianza en la Práctica

Al presentar insights, lidera con la confianza:

```
[CONFIANZA ALTA] Los clientes se sienten abrumados por los reportes manuales — aparece en 12 de 20
entrevistas, 4 hilos de Reddit, y es la queja #1 en las reseñas de 3 estrellas de G2. Consistente
entre PyME y mercado medio.

[CONFIANZA MEDIA] Los clientes nos comparan más con hojas de cálculo que con competidores directos —
mencionado en 6 entrevistas y 3 hilos de Reddit, pero aún no visto en datos de reseñas.

[CONFIANZA BAJA] Los compradores empresariales podrían tener preocupaciones de procurement — mencionado
por 2 entrevistados de empresas de 500+. Necesita más señal antes de actuar sobre esto.
```

### Ventana de Vigencia

- **Usar como fuente principal**: Datos de los últimos 12 meses
- **Usar con precaución**: 12-24 meses (el producto y el mercado pueden haber cambiado)
- **Usar solo como contexto de referencia**: 2+ años de antigüedad

Cuando un tema aparece de forma consistente entre datos antiguos y nuevos, esa es una señal duradera que vale la pena atender.
