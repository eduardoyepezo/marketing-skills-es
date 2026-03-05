# Ahrefs

Conjunto de herramientas SEO para análisis de backlinks, investigación de palabras clave y análisis competitivo.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API para Site Explorer, Keywords Explorer |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | - | Solo API |

## Autenticación

- **Tipo**: API Token
- **Header**: `Authorization: Bearer {api_token}`
- **Obtener token**: Account Settings > API en el panel de Ahrefs

## Operaciones Comunes del Agente

### Calificación de dominio

```bash
GET https://api.ahrefs.com/v3/site-explorer/domain-rating?target=example.com

Authorization: Bearer {api_token}
```

### Resumen de backlinks

```bash
GET https://api.ahrefs.com/v3/site-explorer/backlinks-stats?target=example.com&mode=domain

Authorization: Bearer {api_token}
```

### Dominios de referencia

```bash
GET https://api.ahrefs.com/v3/site-explorer/refdomains?target=example.com&mode=domain&limit=100

Authorization: Bearer {api_token}
```

### Lista de backlinks

```bash
GET https://api.ahrefs.com/v3/site-explorer/backlinks?target=example.com&mode=domain&limit=100

Authorization: Bearer {api_token}
```

### Palabras clave orgánicas

```bash
GET https://api.ahrefs.com/v3/site-explorer/organic-keywords?target=example.com&mode=domain&country=us&limit=100

Authorization: Bearer {api_token}
```

### Páginas principales

```bash
GET https://api.ahrefs.com/v3/site-explorer/top-pages?target=example.com&mode=domain&country=us&limit=50

Authorization: Bearer {api_token}
```

### Resumen de palabra clave

```bash
GET https://api.ahrefs.com/v3/keywords-explorer/overview?keywords=keyword1,keyword2&country=us

Authorization: Bearer {api_token}
```

### Sugerencias de palabras clave

```bash
GET https://api.ahrefs.com/v3/keywords-explorer/matching-terms?keyword=seed+keyword&country=us&limit=100

Authorization: Bearer {api_token}
```

### Resumen de SERP

```bash
GET https://api.ahrefs.com/v3/keywords-explorer/serp-overview?keyword=target+keyword&country=us

Authorization: Bearer {api_token}
```

## Métricas Clave

### Métricas de Dominio
- `domain_rating` - Domain Rating (DR)
- `ahrefs_rank` - Ahrefs Rank
- `referring_domains` - Cantidad de dominios de referencia
- `backlinks` - Total de backlinks
- `organic_traffic` - Tráfico orgánico estimado

### Métricas de Palabras Clave
- `volume` - Volumen de búsqueda mensual
- `keyword_difficulty` - Puntuación KD (0-100)
- `cpc` - Costo por clic
- `clicks` - Clics mensuales estimados
- `global_volume` - Volumen de búsqueda global

### Campos de Backlink
- `url_from` - URL de origen
- `url_to` - URL de destino
- `anchor` - Texto ancla
- `domain_rating_source` - DR de la fuente
- `first_seen` - Fecha de primer descubrimiento

## Modos

- `domain` - Dominio completo
- `subdomains` - Dominio + subdominios
- `prefix` - Prefijo de URL
- `exact` - URL exacta

## Cuándo Usar

- Análisis de backlinks
- Investigación para construcción de enlaces
- Investigación de palabras clave
- Análisis competitivo
- Análisis de brechas de contenido
- Auditorías de sitio

## Límites de Velocidad

- Varía según el plan
- 500-5000 filas por solicitud

## Skills Relevantes

- seo-audit
- content-strategy
- competitor-alternatives
