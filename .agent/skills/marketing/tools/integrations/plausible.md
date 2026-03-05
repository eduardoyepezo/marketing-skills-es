# Plausible Analytics

Plataforma de análisis web de código abierto centrada en la privacidad, con una API sencilla para consultas de estadísticas sin cookies ni recopilación de datos personales.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Stats v2 Query, Sites Provisioning, Goals, Shared Links |
| MCP | - | No disponible |
| CLI | ✓ | [plausible.js](../clis/plausible.js) |
| SDK | - | Solo REST API |

## Autenticación

- **Tipo**: Bearer Token
- **Encabezado**: `Authorization: Bearer {api_key}`
- **Obtener clave**: https://plausible.io/settings > API Keys
- **Nota**: La API de sitios requiere el plan Enterprise

## Operaciones Comunes del Agente

### Consulta de Estadísticas (v2)

```bash
POST https://plausible.io/api/v2/query

{
  "site_id": "example.com",
  "metrics": ["visitors", "pageviews", "bounce_rate", "visit_duration"],
  "date_range": "30d"
}
```

### Páginas Principales

```bash
POST https://plausible.io/api/v2/query

{
  "site_id": "example.com",
  "metrics": ["visitors", "pageviews"],
  "date_range": "30d",
  "dimensions": ["event:page"]
}
```

### Fuentes de Tráfico

```bash
POST https://plausible.io/api/v2/query

{
  "site_id": "example.com",
  "metrics": ["visitors", "bounce_rate"],
  "date_range": "30d",
  "dimensions": ["visit:source"]
}
```

### Serie Temporal

```bash
POST https://plausible.io/api/v2/query

{
  "site_id": "example.com",
  "metrics": ["visitors", "pageviews"],
  "date_range": "30d",
  "dimensions": ["time:day"]
}
```

### Desglose por País

```bash
POST https://plausible.io/api/v2/query

{
  "site_id": "example.com",
  "metrics": ["visitors", "percentage"],
  "date_range": "30d",
  "dimensions": ["visit:country"]
}
```

### Consulta Filtrada (página específica)

```bash
POST https://plausible.io/api/v2/query

{
  "site_id": "example.com",
  "metrics": ["visitors", "pageviews", "bounce_rate"],
  "date_range": "30d",
  "filters": [["is", "event:page", ["/pricing"]]]
}
```

### Visitantes en Tiempo Real (v1)

```bash
GET https://plausible.io/api/v1/stats/realtime/visitors?site_id=example.com
```

### Listar Sitios

```bash
GET https://plausible.io/api/v1/sites
```

## Métricas Clave

### Métricas Disponibles
- `visitors` - Visitantes únicos
- `visits` - Total de visitas (sesiones)
- `pageviews` - Total de páginas vistas
- `views_per_visit` - Páginas por sesión
- `bounce_rate` - Porcentaje de tasa de rebote
- `visit_duration` - Duración promedio de la sesión (segundos)
- `events` - Total de eventos
- `conversion_rate` - Tasa de conversión de objetivos
- `time_on_page` - Tiempo promedio en la página
- `scroll_depth` - Profundidad de desplazamiento promedio
- `percentage` - Participación del total

### Dimensiones Disponibles
- `event:page` - Ruta de página
- `event:goal` - Nombre del objetivo
- `visit:source` - Fuente de tráfico
- `visit:referrer` - URL de referencia
- `visit:channel` - Canal de tráfico
- `visit:utm_source`, `visit:utm_medium`, `visit:utm_campaign` - Parámetros UTM
- `visit:device` - Tipo de dispositivo
- `visit:browser` - Nombre del navegador
- `visit:os` - Sistema operativo
- `visit:country`, `visit:region`, `visit:city` - Ubicación
- `visit:entry_page`, `visit:exit_page` - Páginas de entrada/salida
- `time`, `time:day`, `time:week`, `time:month` - Períodos de tiempo

## Parámetros

### Consulta de Estadísticas (v2)
- `site_id` (obligatorio) - Dominio registrado en Plausible
- `metrics` (obligatorio) - Array de métricas a devolver
- `date_range` (obligatorio) - Período de tiempo: "day", "7d", "30d", "month", "6mo", "12mo", "year", o personalizado ["2024-01-01", "2024-01-31"]
- `dimensions` - Array de dimensiones para agrupar
- `filters` - Array de condiciones de filtro: `[operator, dimension, values]`
- `order_by` - Array de especificaciones de ordenamiento: `[[metric, "desc"]]`
- `pagination` - `{ "limit": 100, "offset": 0 }`

### Operadores de Filtro
- `is` / `is_not` - Coincidencia exacta
- `contains` / `contains_not` - Coincidencia de subcadena
- `matches` / `matches_not` - Coincidencia con comodín

## Cuándo Usar

- Análisis web con prioridad en la privacidad sin cookies
- Análisis de tráfico simple y ligero
- Seguimiento del rendimiento de campañas UTM
- Seguimiento de objetivos y conversiones
- Desglose geográfico y por dispositivo
- Alternativa de análisis compatible con GDPR/CCPA a GA4

## Límites de Tasa

- 600 solicitudes/hora por clave API
- Todas las solicitudes deben realizarse por HTTPS

## Skills Relevantes

- analytics-tracking
- content-strategy
- programmatic-seo
- page-cro
- utm-tracking
