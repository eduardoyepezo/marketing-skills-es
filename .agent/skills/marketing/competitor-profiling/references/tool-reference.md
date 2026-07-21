# Referencia de Herramientas MCP para Competitor Profiling

Referencia rápida de las herramientas MCP de Firecrawl y DataForSEO usadas en el perfilado de competidores.

## Contenido
- Herramientas Firecrawl (scraping de sitios)
- Herramientas DataForSEO (datos de SEO y mercado)
- Orden de Ejecución Recomendado
- Manejo de Errores

---

## Herramientas Firecrawl

### firecrawl_map
**Propósito**: Descubrir todas las URLs del sitio de un competidor para identificar las páginas clave.
**Cuándo usarla**: Primer paso para cada competidor — antes de scrapear páginas individuales.
**Salida clave**: Lista de URLs con sus tipos/rutas de página.
**Tip**: Busca rutas que contengan `/pricing`, `/features`, `/about`, `/customers`, `/integrations`, `/blog`, `/changelog`.

### firecrawl_scrape
**Propósito**: Extraer el contenido de una sola página como markdown limpio.
**Cuándo usarla**: Después de mapear, scrapea cada página clave individualmente.
**Salida clave**: Contenido de la página en formato markdown — titulares, texto del cuerpo, datos estructurados.
**Tip**: Scrapea primero la homepage — revela posicionamiento, audiencia y prueba social en un solo paso.

### firecrawl_search
**Propósito**: Buscar en la web contenido específico sobre un competidor.
**Cuándo usarla**: Para encontrar páginas de reseñas, cobertura de prensa o menciones del competidor que no están en su propio sitio.
**Ejemplos de consultas**:
- `"[Competitor Name]" site:g2.com`
- `"[Competitor Name]" review`
- `"[Competitor Name]" funding OR raised`

### firecrawl_crawl
**Propósito**: Rastrear múltiples páginas de un sitio en una sola operación.
**Cuándo usarla**: En perfiles profundos donde quieras analizar muchas páginas (por ejemplo, todas las páginas de funciones, todos los posts de blog). Más costoso — úsalo con criterio.
**Tip**: Define límites de páginas para evitar rastrear el sitio completo. Apunta a patrones de URL específicos.

### firecrawl_extract
**Propósito**: Extraer datos estructurados de una página usando un esquema.
**Cuándo usarla**: Cuando necesitas puntos de datos específicos en un formato consistente (por ejemplo, detalles de niveles de precios, listas de funciones).
**Tip**: Define un esquema claro de lo que quieres extraer — es más confiable que analizar markdown crudo.

---

## Herramientas MCP de DataForSEO

### Inteligencia a Nivel de Dominio

#### backlinks_summary
**Propósito**: Obtener la autoridad del dominio, total de backlinks, dominios de referencia, puntaje de spam.
**Entrada**: Dominio objetivo (por ejemplo, `competitor.com`)
**Métricas clave**: `domain_rank`, `total_backlinks`, `referring_domains`, `backlinks_spam_score`

#### backlinks_referring_domains
**Propósito**: Listar los principales dominios de referencia — muestra de dónde proviene su valor de enlaces.
**Entrada**: Dominio objetivo + límite
**Métricas clave**: Por dominio: `rank`, `backlinks`, nombre de `domain`

#### dataforseo_labs_google_domain_rank_overview
**Propósito**: Resumen de búsqueda orgánica — tráfico, keywords, valor del tráfico.
**Entrada**: Dominio objetivo
**Métricas clave**: `organic_count` (keywords), `organic_traffic` (estimado mensual), `organic_cost` (valor del tráfico en $)

#### dataforseo_labs_google_ranked_keywords
**Propósito**: Qué keywords posiciona un dominio, con sus posiciones.
**Entrada**: Dominio objetivo
**Métricas clave**: Por keyword: `keyword`, `position`, `search_volume`, `url` (página que posiciona)
**Tip**: Ordena por tráfico para encontrar sus keywords de mayor valor.

#### dataforseo_labs_google_keywords_for_site
**Propósito**: Keywords relevantes para un dominio — más amplio que las keywords posicionadas, incluye oportunidades.
**Entrada**: Dominio objetivo
**Métricas clave**: `keyword`, `search_volume`, `competition`, `cpc`

### Análisis Competitivo

#### dataforseo_labs_google_competitors_domain
**Propósito**: Encontrar los competidores orgánicos más cercanos de un dominio por solapamiento de keywords.
**Entrada**: Dominio objetivo
**Métricas clave**: `domain`, `avg_position`, `intersections` (keywords compartidas), `full_domain_rank`
**Tip**: Puede revelar competidores que el usuario no había considerado.

#### dataforseo_labs_google_domain_intersection
**Propósito**: Encontrar keywords donde dos dominios posicionan ambos — muestra competencia directa.
**Entrada**: Dos dominios objetivo
**Métricas clave**: `keyword`, posición para cada dominio, `search_volume`
**Tip**: Úsala para comparar el dominio del usuario contra cada competidor.

#### dataforseo_labs_google_relevant_pages
**Propósito**: Encontrar las páginas más importantes de un dominio por tráfico orgánico.
**Entrada**: Dominio objetivo
**Métricas clave**: `page`, `metrics` (tráfico, keywords por página)
**Tip**: Revela su estrategia de contenido — qué páginas generan más valor.

### Detección de Tecnología

#### domain_analytics_technologies_domain_technologies
**Propósito**: Detectar el stack tecnológico que usa un dominio.
**Entrada**: Dominio objetivo
**Métricas clave**: Tecnologías agrupadas por categoría (CMS, analítica, marketing, pagos, etc.)

### Análisis Profundo de Backlinks

#### backlinks_backlinks
**Propósito**: Listar backlinks individuales hacia un dominio.
**Entrada**: Dominio objetivo + límite
**Métricas clave**: `url_from`, `url_to`, `anchor`, `domain_from_rank`, `is_new`

#### backlinks_bulk_ranks
**Propósito**: Comparar el rango de dominio de varios dominios a la vez.
**Entrada**: Array de dominios objetivo
**Métricas clave**: `domain_rank` por dominio
**Tip**: Úsala para la tabla comparativa de resumen.

---

## Orden de Ejecución Recomendado

### Escaneo Rápido (por competidor)

```
1. firecrawl_map → obtener URLs del sitio
2. En paralelo:
   a. firecrawl_scrape → homepage
   b. firecrawl_scrape → página de precios
   c. dataforseo_labs_google_domain_rank_overview → métricas orgánicas
   d. backlinks_summary → autoridad del dominio
3. Sintetizar en un perfil abreviado
```

### Perfil Profundo (por competidor)

```
1. firecrawl_map → obtener URLs del sitio
2. En paralelo (lote 1 — scraping):
   a. firecrawl_scrape → homepage
   b. firecrawl_scrape → página de precios
   c. firecrawl_scrape → página(s) de funciones
   d. firecrawl_scrape → página "Acerca de"
   e. firecrawl_scrape → página de clientes/casos de estudio
   f. firecrawl_scrape → página de integraciones
3. En paralelo (lote 2 — datos de SEO):
   a. dataforseo_labs_google_domain_rank_overview
   b. dataforseo_labs_google_ranked_keywords
   c. backlinks_summary
   d. backlinks_referring_domains
   e. dataforseo_labs_google_relevant_pages
   f. dataforseo_labs_google_competitors_domain
4. En paralelo (lote 3 — extras opcionales):
   a. domain_analytics_technologies_domain_technologies
   b. firecrawl_search → reseñas de G2/Capterra
   c. dataforseo_labs_google_domain_intersection (vs. el dominio del usuario)
5. Sintetizar en el perfil completo
```

### Multi-Competidor (3+ competidores)

```
1. Mapear todos los sitios de competidores en paralelo
2. Scrapear todas las homepages en paralelo, luego las páginas de precios en paralelo
3. Extraer domain_rank_overview para todos en paralelo
4. Extraer backlinks_bulk_ranks para todos a la vez
5. Construir los perfiles en secuencia (la síntesis requiere enfoque)
6. Construir la tabla de resumen al final
```

---

## Manejo de Errores

| Problema | Acción |
|-------|--------|
| El scrape de Firecrawl regresa vacío/bloqueado | Intenta con `firecrawl_browser_create` para sitios con mucho JS |
| Página de precios no encontrada en el mapa | Busca `/pricing`, `/plans`, `/packages` — algunos sitios usan rutas distintas |
| DataForSEO no regresa datos para el dominio | El dominio puede ser demasiado nuevo o pequeño — anota "datos insuficientes" en el perfil |
| Se alcanzan los límites de tasa | Espacía las solicitudes; prioriza primero los datos de mayor valor |
| Scraping de página de reseñas bloqueado | Usa `firecrawl_search` para encontrar fuentes de reseñas en caché o alternativas |
