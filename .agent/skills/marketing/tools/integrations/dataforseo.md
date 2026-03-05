# DataForSEO

API de datos SEO integral para resultados SERP, investigación de palabras clave, backlinks y análisis on-page.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | SERP, Keywords Data, Backlinks, On-Page, Labs |
| MCP | - | No disponible |
| CLI | ✓ | [dataforseo.js](../clis/dataforseo.js) |
| SDK | ✓ | Python, TypeScript, PHP, Java, C# |

## Autenticación

- **Tipo**: Basic Auth
- **Header**: `Authorization: Basic {base64(login:password)}`
- **Obtener credenciales**: Pestaña API Access en https://app.dataforseo.com/api-access
- **Nota**: La contraseña de API se genera automáticamente y es diferente a la contraseña de la cuenta

## Operaciones Comunes del Agente

### SERP - Google orgánico (live)

```bash
POST https://api.dataforseo.com/v3/serp/google/organic/live/regular

[{
  "keyword": "marketing automation",
  "location_name": "United States",
  "language_name": "English"
}]
```

### Keywords - Volumen de búsqueda (live)

```bash
POST https://api.dataforseo.com/v3/keywords_data/google_ads/search_volume/live

[{
  "keywords": ["email marketing", "marketing automation", "crm software"],
  "location_code": 2840,
  "language_code": "en"
}]
```

### Keywords - Palabras clave por sitio (live)

```bash
POST https://api.dataforseo.com/v3/keywords_data/google_ads/keywords_for_site/live

[{
  "target": "example.com",
  "location_code": 2840,
  "language_code": "en"
}]
```

### Backlinks - Resumen

```bash
POST https://api.dataforseo.com/v3/backlinks/summary/live

[{
  "target": "example.com",
  "internal_list_limit": 10,
  "backlinks_status_type": "live"
}]
```

### Backlinks - Lista

```bash
POST https://api.dataforseo.com/v3/backlinks/backlinks/live

[{
  "target": "example.com",
  "mode": "as_is",
  "limit": 100,
  "backlinks_status_type": "live"
}]
```

### Backlinks - Dominios de referencia

```bash
POST https://api.dataforseo.com/v3/backlinks/referring_domains/live

[{
  "target": "example.com",
  "limit": 100
}]
```

### Backlinks - Índice (estadísticas de la base de datos)

```bash
GET https://api.dataforseo.com/v3/backlinks/index
```

### On-Page - Auditoría instantánea de páginas

```bash
POST https://api.dataforseo.com/v3/on_page/instant_pages

[{
  "url": "https://example.com/page",
  "enable_javascript": true
}]
```

### SERP - Lista de ubicaciones

```bash
GET https://api.dataforseo.com/v3/serp/google/locations
```

### SERP - Lista de idiomas

```bash
GET https://api.dataforseo.com/v3/serp/google/languages
```

## Patrón de API

DataForSEO utiliza dos métodos para la mayoría de los endpoints:
- **Live** (`/live`) - Síncrono, resultados en la misma respuesta
- **Basado en tareas** (`/task_post` + `/task_get/$id`) - Asíncrono para solicitudes de gran volumen

Los cuerpos de las solicitudes son siempre arrays JSON (incluso para solicitudes individuales).

## Métricas Clave

### Métricas de Palabras Clave
- `search_volume` - Volumen de búsqueda mensual
- `competition` - Nivel de competencia (0-1)
- `cpc` - Costo por clic
- `monthly_searches` - Array de desglose mensual

### Métricas de Backlinks
- `total_backlinks` - Total de backlinks
- `referring_domains` - Dominios de referencia únicos
- `domain_rank` - Puntuación de autoridad de dominio
- `backlinks_spam_score` - Puntuación de spam

## Cuándo Usar

- Seguimiento programático de SERP a escala
- Investigación de palabras clave con datos de volumen de búsqueda
- Análisis y monitoreo de backlinks
- Auditorías SEO on-page
- Análisis de competidores

## Límites de Velocidad

- Headers de límite de velocidad: `X-RateLimit-Limit`, `X-RateLimit-Remaining`
- API de Backlinks: 2000 solicitudes/minuto, 30 simultáneas
- Varía según el endpoint y el plan

## Skills Relacionadas

- seo-audit
- programmatic-seo
- content-strategy
- competitor-alternatives
