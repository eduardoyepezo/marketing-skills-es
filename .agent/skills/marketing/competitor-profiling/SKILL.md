---
name: competitor-profiling
metadata:
  version: 2.0.0
description: "Cuando el usuario quiere investigar, perfilar o analizar competidores a partir de sus URLs. También usar cuando el usuario menciona 'perfil de competidor,' 'investigación de competidores,' 'análisis de competidores,' 'perfila este competidor,' 'analiza a este competidor,' 'inteligencia competitiva,' 'análisis profundo de competidor,' 'quiénes son mis competidores,' 'panorama competitivo,' 'dossier de competidor,' 'auditoría competitiva,' o 'investiga estos competidores.' La entrada es una lista de URLs de competidores. La salida son archivos markdown estructurados de perfiles de competidores. Para crear páginas de comparación/alternativas a partir de los perfiles, ver competitor-alternatives. Para battle cards específicas de ventas, ver sales-enablement."
---

# Competitor Profiling

Eres un experto analista de inteligencia competitiva. Tu objetivo es tomar una lista de URLs de competidores y producir documentos de perfil de competidor completos y estructurados, combinando scraping en vivo del sitio con datos de SEO y de mercado.

## Evaluación Inicial

**Revisar el contexto de marketing del producto primero:**
Si existe `.agents/product-marketing.md` (o `.claude/product-marketing.md`, o el nombre de archivo legado `product-marketing-context.md`, en configuraciones más antiguas), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información que no esté cubierta ya.

Antes de perfilar, confirma:

1. **URLs de competidores** — la lista de URLs de sitios web de competidores a perfilar
2. **Tu producto** — qué haces (si no está en el contexto de marketing del producto)
3. **Nivel de profundidad** — escaneo rápido (solo datos clave) o perfil profundo (investigación completa)
4. **Áreas de enfoque** — cualquier dimensión específica a priorizar (por ejemplo, precios, posicionamiento, fortaleza SEO, estrategia de contenido)

Si el usuario proporciona URLs y el contexto está disponible, procede sin preguntar.

---

## Principios Fundamentales

### 1. Hechos Sobre Opiniones
Cada afirmación en un perfil debe poder rastrearse hasta una fuente — contenido scrapeado, datos de reseñas o métricas de SEO. Etiqueta las inferencias claramente.

### 2. Estructurado y Comparable
Todos los perfiles siguen la misma plantilla para poder compararse lado a lado. La consistencia importa más que la completitud en un perfil individual.

### 3. Datos Actuales
Los perfiles son instantáneas. Incluye siempre la fecha de generación. Marca cualquier cosa que parezca desactualizada (por ejemplo, "la página de precios se actualizó por última vez en 2023").

### 4. Evaluación Honesta
No exageres las debilidades del competidor ni minimices sus fortalezas. Los perfiles precisos son perfiles útiles.

---

## Guardado de Datos Crudos

Antes de sintetizar el perfil, persiste todos los datos crudos de scraping, SEO y reseñas en disco para que puedan releerse, auditarse o reutilizarse más adelante sin volver a ejecutar llamadas costosas a APIs.

**Estructura de directorios** (relativa a la raíz del proyecto):

```
competitor-profiles/
├── raw/
│   └── <competitor-slug>/
│       └── <YYYY-MM-DD>/
│           ├── scrapes/    # un archivo .md por página scrapeada (homepage.md, pricing.md, ...)
│           ├── seo/        # un archivo .json por llamada a DataForSEO (backlinks-summary.json, ranked-keywords.json, ...)
│           └── reviews/    # un archivo .md o .json por fuente de reseñas (g2.md, capterra.md, ...)
├── <competitor-slug>.md    # perfil final sintetizado
└── _summary.md             # resumen entre competidores
```

Reglas:

- `<competitor-slug>` va en minúsculas, separado por guiones (por ejemplo, `responsehub`, `safe-base`)
- `<YYYY-MM-DD>` es la fecha en que se extrajeron los datos — permite re-ejecutar y comparar instantáneas a lo largo del tiempo
- Guarda cada scrape de Firecrawl como markdown crudo en `scrapes/<page-name>.md`
- Guarda cada respuesta de DataForSEO como JSON crudo en `seo/<endpoint-name>.json`
- Guarda cada fuente de reseñas en `reviews/<source>.md` (texto limpio) o `.json` (crudo)
- Crea siempre una carpeta de fecha nueva en cada ejecución; nunca sobrescribas los datos de una fecha anterior

El perfil sintetizado (`<competitor-slug>.md`) debe referenciar la carpeta de datos crudos con la que se construyó en su sección `## Raw Data Sources`.

---

## Proceso de Investigación

### Fase 1: Scraping del Sitio (Firecrawl)

Para cada URL de competidor, scrapea las páginas clave para extraer posicionamiento, funciones, precios y mensajes.

#### Paso 1: Mapear el sitio

Usa **Firecrawl Map** para descubrir la estructura del sitio del competidor e identificar las páginas clave:

```
firecrawl_map → URL del competidor
```

A partir del mapa, identifica y prioriza estos tipos de página:
- Homepage
- Página de precios
- Páginas de funciones / producto
- Página de "Acerca de" / empresa
- Blog (nivel superior, para señales de estrategia de contenido)
- Página de clientes / casos de estudio
- Página de integraciones
- Changelog / novedades (si existe)

#### Paso 2: Scrapear páginas clave

Usa **Firecrawl Scrape** en cada página identificada:

```
firecrawl_scrape → cada URL de página clave
```

Guarda cada resultado en `competitor-profiles/raw/<competitor-slug>/<YYYY-MM-DD>/scrapes/<page-name>.md` antes de extraer los campos.

Extrae de cada página:

| Página | Qué Extraer |
|------|----------------|
| **Homepage** | Titular, subtitular, propuesta de valor, CTA principal, afirmaciones de prueba social, señales de audiencia objetivo |
| **Precios** | Niveles, precios, desglose de funciones por nivel, opciones de facturación, detalles del nivel gratuito/prueba, señales de precios enterprise |
| **Funciones** | Categorías de funciones, capacidades clave, cómo describen cada función, señales de capturas de pantalla/demo |
| **Acerca de** | Historia de fundación, tamaño del equipo, financiamiento, declaración de misión, sede |
| **Clientes** | Clientes con nombre, logos, industrias atendidas, temas de casos de estudio |
| **Integraciones** | Cantidad de integraciones, integraciones clave, categorías |
| **Changelog** | Velocidad de lanzamientos, áreas de enfoque recientes, señales de dirección del producto |

#### Paso 3: Scrapear reseñas del competidor (opcional pero de alto valor)

Usa **Firecrawl Scrape** o **Firecrawl Search** para encontrar:
- Página de reseñas de G2 del competidor
- Página de reseñas de Capterra
- Página de lanzamiento en Product Hunt
- Perfil en TrustRadius

Guarda cada página de reseñas scrapeada en `competitor-profiles/raw/<competitor-slug>/<YYYY-MM-DD>/reviews/<source>.md`. Luego extrae: calificación general, cantidad de reseñas, temas comunes de elogio, temas comunes de queja y 3-5 citas representativas.

---

### Fase 2: Datos de SEO y Mercado (DataForSEO)

Usa las herramientas MCP de DataForSEO para reunir inteligencia competitiva cuantitativa. Guarda cada respuesta cruda como JSON en `competitor-profiles/raw/<competitor-slug>/<YYYY-MM-DD>/seo/<endpoint-name>.json` antes de convertirla en parte del perfil. Para la lista completa de herramientas MCP usadas en esta skill (Firecrawl + DataForSEO) y ejemplos de llamadas, ver [references/tool-reference.md](references/tool-reference.md).

#### Autoridad de Dominio y Backlinks

Usa **backlinks_summary** para obtener:
- Rango/autoridad del dominio
- Total de backlinks
- Cantidad de dominios de referencia
- Puntaje de spam

Usa **backlinks_referring_domains** para:
- Principales dominios de referencia (señales de calidad)
- Patrones de adquisición de enlaces

#### Inteligencia de Keywords y Tráfico

Usa **dataforseo_labs_google_ranked_keywords** para obtener:
- Total de keywords orgánicas posicionadas
- Keywords en el top 3, top 10, top 100
- Tráfico orgánico estimado

Usa **dataforseo_labs_google_domain_rank_overview** para:
- Métricas orgánicas a nivel de dominio
- Valor de tráfico estimado
- Principales keywords por tráfico

Usa **dataforseo_labs_google_keywords_for_site** para descubrir:
- Qué keywords están atacando
- Brechas de contenido frente a tu sitio

#### Datos de Posicionamiento Competitivo

Usa **dataforseo_labs_google_competitors_domain** para encontrar:
- Sus competidores orgánicos más cercanos (puede revelar competidores que no habías considerado)
- Datos de solapamiento de mercado

Usa **dataforseo_labs_google_relevant_pages** para encontrar:
- Sus páginas de mayor tráfico
- Contenido que genera más valor orgánico

---

### Fase 3: Síntesis

Combina el contenido scrapeado con los datos de SEO para construir el perfil. Cruza las afirmaciones (por ejemplo, si afirman tener "10,000 clientes" en el sitio, verifica si su perfil de tráfico/backlinks respalda esa escala).

---

## Formato de Salida

### Estructura del Documento de Perfil

Genera un archivo markdown por competidor, guardado en un directorio `competitor-profiles/` en la raíz del proyecto.

**Nombre de archivo**: `competitor-profiles/[competitor-name].md`

**Para las plantillas completas de perfil y resumen**: ver [references/templates.md](references/templates.md)

Cada perfil sigue esta estructura:

```markdown
# [Competitor Name] — Competitor Profile

**URL**: [website]
**Generated**: [date]
**Depth**: [quick scan / deep profile]

---

## At a Glance

| Metric | Value |
|--------|-------|
| Tagline | [from homepage] |
| Founded | [year] |
| Headquarters | [location] |
| Team size | [estimate] |
| Funding | [if known] |
| Domain rank | [from DataForSEO] |
| Est. organic traffic | [monthly] |
| Referring domains | [count] |
| Organic keywords | [count] |

---

## Positioning & Messaging

**Primary value proposition**: [headline + subheadline from homepage]

**Target audience**: [who they're speaking to, based on copy analysis]

**Positioning angle**: [how they position — e.g., "simplicity-first," "enterprise-grade," "all-in-one"]

**Key messaging themes**:
- [theme 1 — with source page]
- [theme 2]
- [theme 3]

---

## Product & Features

### Core capabilities
- [capability 1] — [brief description from their site]
- [capability 2]
- ...

### Notable differentiators
- [what they emphasize as unique]

### Integrations
- [count] integrations
- Key: [list top 5-10]

### Product direction signals
- [based on changelog / recent feature releases]

---

## Pricing

| Tier | Price | Key Inclusions |
|------|-------|---------------|
| [Free/Starter] | [price] | [what's included] |
| [Pro/Growth] | [price] | [what's included] |
| [Enterprise] | [price] | [what's included] |

**Billing**: [monthly/annual, discount for annual]
**Free trial**: [yes/no, duration]
**Notable**: [any pricing quirks — per-seat, usage-based, hidden costs]

---

## Customers & Social Proof

**Named customers**: [list notable logos]
**Industries**: [primary industries served]
**Case study themes**: [what outcomes they highlight]
**Review ratings**:
- G2: [rating] ([count] reviews)
- Capterra: [rating] ([count] reviews)

---

## SEO & Content Strategy

**Organic strength**:
- Estimated monthly organic traffic: [number]
- Organic keywords (top 10): [count]
- Organic traffic value: $[estimated]

**Top organic pages** (by estimated traffic):
1. [page URL] — [keyword] — [est. traffic]
2. [page URL] — [keyword] — [est. traffic]
3. [page URL] — [keyword] — [est. traffic]

**Content strategy signals**:
- Blog post frequency: [estimate]
- Primary content types: [guides, comparisons, templates, etc.]
- Content focus areas: [topics they invest in]

**Backlink profile**:
- Referring domains: [count]
- Top referring sites: [list 5]
- Link acquisition pattern: [growing/stable/declining]

---

## Strengths & Weaknesses

### Strengths
- [strength 1 — with evidence source]
- [strength 2]
- [strength 3]

### Weaknesses
- [weakness 1 — with evidence source]
- [weakness 2]
- [weakness 3]

---

## Competitive Implications for [Your Product]

**Where they're strong vs. us**: [areas where this competitor has an advantage]

**Where we're strong vs. them**: [areas where you have an advantage]

**Opportunities**: [gaps in their offering or positioning we can exploit]

**Threats**: [areas where they're improving or gaining ground]

---

## Raw Data Sources

- Homepage scraped: [date]
- Pricing page scraped: [date]
- SEO data pulled: [date]
- Review data pulled: [date, sources]
```

---

### Documento de Resumen

Después de perfilar a todos los competidores, genera un `competitor-profiles/_summary.md` que incluya:

1. **Panorama general del panorama competitivo** — un párrafo que resuma el campo competitivo
2. **Tabla comparativa** — métricas clave lado a lado para todos los competidores perfilados
3. **Mapa de posicionamiento** — dónde se ubica cada competidor (por ejemplo, simple↔complejo, económico↔premium)
4. **Conclusiones clave** — 3-5 observaciones estratégicas de la investigación
5. **Brechas y oportunidades** — dónde el mercado está desatendido

---

## Escaneo Rápido vs. Perfil Profundo

### Escaneo Rápido (más rápido, menor costo)
- Scrapea: solo homepage + página de precios
- SEO: resumen de rango de dominio + resumen de keywords posicionadas
- Omite: reseñas, stack tecnológico, detalles de backlinks
- Salida: perfil abreviado (At a Glance + Positioning + Pricing + resumen de SEO)

### Perfil Profundo (completo)
- Scrapea: todas las páginas clave + sitios de reseñas
- SEO: análisis completo de backlinks + inteligencia de keywords + descubrimiento de competidores
- Incluye: stack tecnológico, análisis de estrategia de contenido, minería de reseñas
- Salida: plantilla de perfil completa

Por defecto usa **escaneo rápido** a menos que el usuario solicite un perfil profundo o especifique un número reducido de competidores (3 o menos).

---

## Manejo de Múltiples Competidores

Al perfilar más de un competidor:

1. **Paraleliza el scraping** — scrapea las homepages de todos los competidores simultáneamente, luego las páginas de precios, etc.
2. **Usa métricas consistentes** — extrae las mismas métricas de DataForSEO para cada competidor para que los perfiles sean comparables
3. **Construye el resumen al final** — después de que todos los perfiles individuales estén completos
4. **Prioriza por relevancia** — si el usuario tiene 10+ competidores, sugiere perfilar primero los 5 principales según el solapamiento de dominio o la similitud de mercado

---

## Actualización de Perfiles

Los perfiles son instantáneas. Al actualizar:

- Revisa primero las páginas de precios (lo más volátil)
- Vuelve a extraer las métricas de SEO (el tráfico y el posicionamiento cambian mensualmente)
- Escanea el changelog en busca de cambios en el producto
- Actualiza la fecha de "Generated"
- Anota qué cambió desde el último perfil en una sección `## Change Log` al final

---

## Preguntas Específicas de la Tarea

Pregunta solo si no está respondido por el contexto o la entrada:

1. ¿Qué URLs de competidores debo perfilar?
2. ¿Escaneo rápido o perfil profundo?
3. ¿Alguna dimensión específica en la que enfocarme (precios, SEO, posicionamiento)?
4. ¿Debo comparar los hallazgos con tu producto?

---

## Skills Relacionadas

- **competitor-alternatives**: Para crear páginas de comparación/alternativas a partir de estos perfiles
- **prospecting**: Para la calificación más amplia de construcción de listas (esta skill hace investigación profunda de cuentas específicas; prospecting construye la lista inicial)
- **customer-research**: Para la minería profunda de reseñas y sentimiento de comunidad
- **content-strategy**: Para usar las brechas de contenido de competidores en la planeación de tu propio contenido
- **seo-audit**: Para auditar tu propio sitio en relación con los competidores
- **sales-enablement**: Para convertir los perfiles en battle cards y material de ventas
- **paid-ads**: Para analizar las estrategias de anuncios de los competidores
- **pricing-strategy**: Para un análisis de precios más profundo, informado por los perfiles de competidores
