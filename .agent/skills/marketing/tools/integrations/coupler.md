# Coupler.io

Plataforma de integración de datos que conecta fuentes de datos de marketing, ventas, analítica y e-commerce con destinos como hojas de cálculo, herramientas de BI y data warehouses con programación automatizada.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Importers, Runs, Sources, Destinations |
| MCP | ✓ | [Claude connector](https://claude.com/connectors/coupler-io) |
| CLI | ✓ | [coupler.js](../clis/coupler.js) |
| SDK | - | Solo REST API |

## Autenticación

- **Tipo**: API Key
- **Header**: `Authorization: Bearer {api_key}`
- **Obtener clave**: Settings > API en https://app.coupler.io

## Operaciones Comunes del Agente

### Listar Importers

```bash
GET https://api.coupler.io/v1/importers
```

### Obtener Detalles de un Importer

```bash
GET https://api.coupler.io/v1/importers/{id}
```

### Activar una Ejecución de Importer

```bash
POST https://api.coupler.io/v1/importers/{id}/run
```

### Crear un Importer

```bash
POST https://api.coupler.io/v1/importers

{
  "source_type": "google_analytics",
  "destination_type": "google_sheets",
  "name": "GA4 to Sheets Daily"
}
```

### Eliminar un Importer

```bash
DELETE https://api.coupler.io/v1/importers/{id}
```

### Listar Ejecuciones de un Importer

```bash
GET https://api.coupler.io/v1/importers/{id}/runs
```

### Obtener Detalles de una Ejecución

```bash
GET https://api.coupler.io/v1/runs/{id}
```

### Listar Fuentes Disponibles

```bash
GET https://api.coupler.io/v1/sources
```

### Listar Destinos Disponibles

```bash
GET https://api.coupler.io/v1/destinations
```

## Métricas Clave

### Datos de Importer
- `id` - ID del importer
- `name` - Nombre del importer
- `source_type` - Tipo de conector de origen
- `destination_type` - Tipo de conector de destino
- `schedule` - Programación de automatización
- `status` - Estado actual
- `last_run_at` - Timestamp de la última ejecución

### Datos de Ejecución
- `id` - ID de la ejecución
- `importer_id` - Importer padre
- `status` - Estado de la ejecución (pending, running, completed, failed)
- `started_at` - Timestamp de inicio
- `finished_at` - Timestamp de finalización
- `rows_imported` - Número de filas procesadas
- `error` - Mensaje de error si falló

## Parámetros

### Creación de Importer
- `source_type` - Conector de origen (p. ej., google_analytics, google_ads, facebook_ads, hubspot, shopify, stripe, airtable)
- `destination_type` - Conector de destino (p. ej., google_sheets, bigquery, snowflake, postgresql)
- `name` - Nombre del importer
- `schedule` - Programación de automatización (p. ej., hourly, daily, weekly)

### Fuentes Compatibles
- **Analytics**: Google Analytics, Adobe Analytics
- **Ads**: Google Ads, Facebook Ads, LinkedIn Ads, TikTok Ads
- **CRM**: HubSpot, Salesforce, Pipedrive
- **E-commerce**: Shopify, Stripe, WooCommerce
- **Otros**: Airtable, Google Sheets, BigQuery, MySQL, PostgreSQL

### Destinos Compatibles
- **Hojas de cálculo**: Google Sheets, Excel Online
- **Herramientas de BI**: Looker Studio, Power BI, Tableau
- **Data Warehouses**: BigQuery, Snowflake, Redshift
- **Bases de datos**: PostgreSQL, MySQL

## Cuándo Usar

- Automatizar pipelines de datos de marketing desde plataformas de anuncios y analítica
- Consolidar datos de campañas multicanal en un único destino
- Programar sincronizaciones de datos recurrentes desde CRM a hojas de cálculo o herramientas de BI
- Construir dashboards de marketing con datos actualizados de múltiples fuentes
- Exportar datos de e-commerce para informes y análisis
- Conectar fuentes de datos sin escribir código ETL personalizado

## Límites de Tasa

- Los límites de tasa varían según el plan
- Standard: acceso a la API disponible en planes Professional y superiores
- La frecuencia de ejecución del importer depende del nivel del plan

## Skills Relacionadas

- analytics-tracking
- paid-ads
- revops
