# Supermetrics

Canal de datos de marketing que conecta más de 200 plataformas de marketing. Extrae datos de plataformas publicitarias, analítica, redes sociales, SEO, email y más en una única interfaz de consulta.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | Consulta cualquier fuente de datos conectada, gestión de cuentas |
| MCP | ✓ | [Conector de Claude](https://claude.com/connectors/supermetrics) |
| CLI | ✓ | [supermetrics.js](../clis/supermetrics.js) |
| SDK | - | Solo REST API |

## Autenticación

- **Tipo**: API Key
- **Parámetro de consulta**: `api_key={api_key}` o **Encabezado**: `x-api-key: {api_key}`
- **Obtener clave**: Supermetrics Hub > Configuración de API en https://hub.supermetrics.com

## Operaciones Comunes del Agente

### Consultar una fuente de datos

```bash
POST https://api.supermetrics.com/enterprise/v2/query/data/json

{
  "ds_id": "GA4",
  "ds_accounts": "123456789",
  "date_range_type": "last_28_days",
  "fields": [
    { "name": "sessions" },
    { "name": "pageviews" },
    { "name": "date" }
  ]
}
```

### Consultar con filtros

```bash
POST https://api.supermetrics.com/enterprise/v2/query/data/json

{
  "ds_id": "AW",
  "ds_accounts": "123-456-7890",
  "date_range_type": "last_month",
  "fields": [
    { "name": "campaign_name" },
    { "name": "clicks" },
    { "name": "impressions" },
    { "name": "cost" }
  ],
  "max_rows": 100
}
```

### Listar fuentes de datos disponibles

```bash
GET https://api.supermetrics.com/enterprise/v2/datasources
```

### Listar cuentas conectadas

```bash
GET https://api.supermetrics.com/enterprise/v2/datasources/accounts?ds_id=GA4
```

### Listar equipos

```bash
GET https://api.supermetrics.com/enterprise/v2/teams
```

### Listar usuarios

```bash
GET https://api.supermetrics.com/enterprise/v2/users
```

## Métricas Clave

### IDs de fuentes de datos
- `GA4` - Google Analytics 4
- `GA4_PAID` - Google Analytics (de pago)
- `AW` - Google Ads
- `FB` - Facebook Ads
- `LI` - LinkedIn Ads
- `TW_ADS` - Twitter Ads
- `IG_IA` - Instagram
- `FB_IA` - Facebook Pages
- `GSC` - Google Search Console
- `SE` - Semrush
- `MC` - Mailchimp
- `HubSpot` - HubSpot

### Valores de rango de fechas
- `last_28_days` - Últimos 28 días
- `last_month` - Mes calendario anterior
- `this_month` - Mes actual hasta la fecha
- `custom` - Rango personalizado (requiere `start_date` y `end_date`)

## Parámetros

### Consulta
- `ds_id` - Identificador de fuente de datos (requerido)
- `ds_accounts` - ID de cuenta para la fuente de datos (requerido)
- `date_range_type` - Preajuste de rango de fechas o "custom" (requerido)
- `fields` - Array de objetos de campo con propiedad `name` (requerido)
- `filter` - Expresión de filtro para acotar resultados
- `max_rows` - Número máximo de filas a devolver
- `start_date` - Fecha de inicio para rango personalizado (YYYY-MM-DD)
- `end_date` - Fecha de fin para rango personalizado (YYYY-MM-DD)

### Campos comunes por fuente
- **GA4**: `sessions`, `pageviews`, `users`, `bounce_rate`, `date`, `source`, `medium`, `page_path`
- **Google Ads**: `campaign_name`, `clicks`, `impressions`, `cost`, `conversions`, `ctr`, `cpc`
- **Facebook Ads**: `campaign_name`, `impressions`, `clicks`, `spend`, `reach`, `cpm`, `cpc`
- **LinkedIn Ads**: `campaign_name`, `impressions`, `clicks`, `cost`, `conversions`
- **GSC**: `query`, `clicks`, `impressions`, `ctr`, `position`, `page`

## Cuándo Usar

- Extraer datos de marketing multiplataforma en un único informe
- Comparar rendimiento entre plataformas publicitarias (Google, Meta, LinkedIn, TikTok)
- Agregar datos de analítica de múltiples fuentes
- Automatizar flujos de trabajo de informes de marketing
- Construir paneles unificados entre canales de marketing
- Extraer datos de SEO junto con métricas de medios de pago

## Límites de Tasa

- Los límites de tasa varían según el plan
- API Enterprise: típicamente 100 solicitudes/minuto
- Los resultados de consultas pueden estar paginados para conjuntos de datos grandes
- Recomendado: usar `max_rows` para controlar el tamaño de la respuesta

## Habilidades Relacionadas

- analytics-tracking
- paid-ads
- seo-audit
- content-strategy
- social-content
