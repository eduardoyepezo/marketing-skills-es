# Google Ads

Plataforma de publicidad de pago por clic para campañas de búsqueda, display y video.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Google Ads API para gestión de campañas |
| MCP | ✓ | Disponible mediante el servidor MCP de Google Ads |
| CLI | - | Usar gcloud o scripts de API |
| SDK | ✓ | Bibliotecas cliente para múltiples lenguajes |

## Autenticación

- **Tipo**: OAuth 2.0
- **Scopes**: `https://www.googleapis.com/auth/adwords`
- **Configuración**: Crear credenciales en Google Cloud Console, vincular con la cuenta de Google Ads
- **Headers**: `developer-token`, `login-customer-id` (para MCC)

## Operaciones Comunes del Agente

### Obtener información de la cuenta

```bash
POST https://googleads.googleapis.com/v14/customers/{customer_id}/googleAds:searchStream

{
  "query": "SELECT customer.id, customer.descriptive_name FROM customer"
}
```

### Listar campañas

```bash
POST https://googleads.googleapis.com/v14/customers/{customer_id}/googleAds:searchStream

{
  "query": "SELECT campaign.id, campaign.name, campaign.status, campaign_budget.amount_micros FROM campaign ORDER BY campaign.id"
}
```

### Obtener rendimiento de campaña

```bash
POST https://googleads.googleapis.com/v14/customers/{customer_id}/googleAds:searchStream

{
  "query": "SELECT campaign.name, metrics.impressions, metrics.clicks, metrics.cost_micros, metrics.conversions FROM campaign WHERE segments.date DURING LAST_30_DAYS"
}
```

### Obtener rendimiento de grupo de anuncios

```bash
POST https://googleads.googleapis.com/v14/customers/{customer_id}/googleAds:searchStream

{
  "query": "SELECT ad_group.name, metrics.impressions, metrics.clicks, metrics.conversions FROM ad_group WHERE segments.date DURING LAST_7_DAYS"
}
```

### Obtener rendimiento de palabras clave

```bash
POST https://googleads.googleapis.com/v14/customers/{customer_id}/googleAds:searchStream

{
  "query": "SELECT ad_group_criterion.keyword.text, metrics.impressions, metrics.clicks, metrics.average_cpc FROM keyword_view WHERE segments.date DURING LAST_30_DAYS ORDER BY metrics.clicks DESC LIMIT 50"
}
```

### Pausar campaña

```bash
POST https://googleads.googleapis.com/v14/customers/{customer_id}/campaigns:mutate

{
  "operations": [{
    "update": {
      "resourceName": "customers/{customer_id}/campaigns/{campaign_id}",
      "status": "PAUSED"
    },
    "updateMask": "status"
  }]
}
```

### Actualizar presupuesto

```bash
POST https://googleads.googleapis.com/v14/customers/{customer_id}/campaignBudgets:mutate

{
  "operations": [{
    "update": {
      "resourceName": "customers/{customer_id}/campaignBudgets/{budget_id}",
      "amountMicros": "50000000"
    },
    "updateMask": "amountMicros"
  }]
}
```

## Métricas Clave

| Métrica | Descripción |
|--------|-------------|
| `metrics.impressions` | Impresiones del anuncio |
| `metrics.clicks` | Clics |
| `metrics.cost_micros` | Costo en micros (dividir entre 1M) |
| `metrics.conversions` | Conversiones |
| `metrics.conversions_value` | Valor de conversión |
| `metrics.average_cpc` | Costo promedio por clic |
| `metrics.ctr` | Tasa de clics |
| `metrics.conversion_rate` | Tasa de conversión |

## Tipos de Campaña

- `SEARCH` - Anuncios de texto en la red de búsqueda
- `DISPLAY` - Red de display
- `SHOPPING` - Anuncios de compras de productos
- `VIDEO` - Anuncios de video en YouTube
- `PERFORMANCE_MAX` - Optimizado por IA en todos los canales
- `DEMAND_GEN` - Discovery/Demand Gen

## GAQL (Google Ads Query Language)

```sql
SELECT
  campaign.name,
  metrics.clicks,
  metrics.conversions
FROM campaign
WHERE
  campaign.status = 'ENABLED'
  AND segments.date DURING LAST_30_DAYS
ORDER BY metrics.conversions DESC
LIMIT 10
```

## Cuándo Usar

- Gestionar campañas de publicidad en búsqueda
- Analizar el rendimiento de campañas
- Ajustar presupuestos y pujas
- Investigación y gestión de palabras clave
- Análisis del seguimiento de conversiones

## Límites de Velocidad

- 15.000 operaciones por día (básico)
- Límites más altos con niveles de developer token

## Skills Relacionadas

- paid-ads
- analytics-tracking
- page-cro
