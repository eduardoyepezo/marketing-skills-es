# Google Search Console

Herramienta gratuita para monitorear el rendimiento de búsqueda de sitios web e indexación.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Search Analytics API, URL Inspection API |
| MCP | - | No disponible |
| CLI | - | Usar gcloud o scripts de API |
| SDK | ✓ | Bibliotecas cliente de Google API |

## Autenticación

- **Tipo**: OAuth 2.0 o Service Account
- **Scopes**: `https://www.googleapis.com/auth/webmasters.readonly`
- **Configuración**: Crear credenciales en Google Cloud Console

## Operaciones Comunes del Agente

### Obtener analytics de búsqueda

```bash
POST https://searchconsole.googleapis.com/webmasters/v3/sites/{site_url}/searchAnalytics/query

{
  "startDate": "2024-01-01",
  "endDate": "2024-01-31",
  "dimensions": ["query"],
  "rowLimit": 100
}
```

### Obtener rendimiento por página

```bash
POST https://searchconsole.googleapis.com/webmasters/v3/sites/{site_url}/searchAnalytics/query

{
  "startDate": "2024-01-01",
  "endDate": "2024-01-31",
  "dimensions": ["page"],
  "rowLimit": 50
}
```

### Obtener rendimiento por país

```bash
POST https://searchconsole.googleapis.com/webmasters/v3/sites/{site_url}/searchAnalytics/query

{
  "startDate": "2024-01-01",
  "endDate": "2024-01-31",
  "dimensions": ["country", "query"],
  "rowLimit": 100
}
```

### Inspeccionar URL

```bash
POST https://searchconsole.googleapis.com/v1/urlInspection/index:inspect

{
  "inspectionUrl": "https://example.com/page",
  "siteUrl": "https://example.com/"
}
```

### Listar sitemaps

```bash
GET https://searchconsole.googleapis.com/webmasters/v3/sites/{site_url}/sitemaps

Authorization: Bearer {access_token}
```

### Enviar sitemap

```bash
PUT https://searchconsole.googleapis.com/webmasters/v3/sites/{site_url}/sitemaps/{sitemap_url}

Authorization: Bearer {access_token}
```

### Solicitar indexación

```bash
POST https://indexing.googleapis.com/v3/urlNotifications:publish

{
  "url": "https://example.com/new-page",
  "type": "URL_UPDATED"
}
```

## Dimensiones

- `query` - Consulta de búsqueda
- `page` - URL de la página
- `country` - Código de país
- `device` - Tipo de dispositivo (MOBILE, DESKTOP, TABLET)
- `date` - Fecha
- `searchAppearance` - Tipo de resultado de búsqueda

## Métricas

- `clicks` - Clics desde la búsqueda
- `impressions` - Impresiones en búsqueda
- `ctr` - Tasa de clics
- `position` - Posición promedio

## Filtros

```json
{
  "dimensionFilterGroups": [{
    "filters": [{
      "dimension": "query",
      "operator": "contains",
      "expression": "keyword"
    }]
  }]
}
```

## Cuándo Usar

- Analizar el rendimiento en búsqueda
- Encontrar oportunidades de palabras clave
- Monitorear el estado de indexación
- Enviar nuevas páginas para indexación
- Identificar problemas de rastreo
- Seguimiento de cambios de posición

## Límites de Velocidad

- 200 consultas por minuto
- 1.200 solicitudes por minuto

## Skills Relacionadas

- seo-audit
- programmatic-seo
- analytics-tracking
