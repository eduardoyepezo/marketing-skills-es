# TikTok Ads

Plataforma publicitaria para la audiencia de videos cortos de TikTok.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | Marketing API para campañas, audiencias e informes |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | ✓ | SDK de Python disponible |

## Autenticación

- **Tipo**: Access Token
- **Encabezado**: `Access-Token: {access_token}`
- **Configuración**: Crear aplicación en TikTok for Business, obtener access token

## Operaciones Comunes del Agente

### Obtener información del anunciante

```bash
GET https://business-api.tiktok.com/open_api/v1.3/advertiser/info/?advertiser_ids=["{advertiser_id}"]

Access-Token: {access_token}
```

### Obtener campañas

```bash
GET https://business-api.tiktok.com/open_api/v1.3/campaign/get/?advertiser_id={advertiser_id}&page=1&page_size=20

Access-Token: {access_token}
```

### Obtener informe de campaña

```bash
POST https://business-api.tiktok.com/open_api/v1.3/report/integrated/get/

Access-Token: {access_token}

{
  "advertiser_id": "{advertiser_id}",
  "report_type": "BASIC",
  "dimensions": ["campaign_id"],
  "metrics": ["spend", "impressions", "clicks", "conversion"],
  "data_level": "AUCTION_CAMPAIGN",
  "start_date": "2024-01-01",
  "end_date": "2024-01-31"
}
```

### Crear campaña

```bash
POST https://business-api.tiktok.com/open_api/v1.3/campaign/create/

Access-Token: {access_token}

{
  "advertiser_id": "{advertiser_id}",
  "campaign_name": "Campaign Name",
  "objective_type": "CONVERSIONS",
  "budget_mode": "BUDGET_MODE_DAY",
  "budget": 100
}
```

### Actualizar estado de campaña

```bash
POST https://business-api.tiktok.com/open_api/v1.3/campaign/status/update/

Access-Token: {access_token}

{
  "advertiser_id": "{advertiser_id}",
  "campaign_ids": ["{campaign_id}"],
  "opt_status": "ENABLE"
}
```

### Obtener grupos de anuncios

```bash
GET https://business-api.tiktok.com/open_api/v1.3/adgroup/get/?advertiser_id={advertiser_id}&campaign_ids=["{campaign_id}"]

Access-Token: {access_token}
```

### Obtener audiencias

```bash
GET https://business-api.tiktok.com/open_api/v1.3/dmp/custom_audience/list/?advertiser_id={advertiser_id}

Access-Token: {access_token}
```

## Métricas Clave

| Métrica | Descripción |
|---------|-------------|
| `spend` | Monto gastado |
| `impressions` | Impresiones del anuncio |
| `clicks` | Clics |
| `ctr` | Tasa de clics |
| `cpc` | Costo por clic |
| `cpm` | Costo por 1000 impresiones |
| `conversion` | Conversiones |
| `cost_per_conversion` | CPA |
| `video_play_actions` | Reproducciones del video |
| `video_watched_6s` | Vistas de 6 segundos |

## Objetivos de Campaña

- `REACH` - Reconocimiento de marca
- `TRAFFIC` - Tráfico al sitio web
- `VIDEO_VIEWS` - Reproducciones de video
- `LEAD_GENERATION` - Formularios de leads
- `CONVERSIONS` - Conversiones en el sitio web
- `APP_PROMOTION` - Instalaciones de aplicaciones

## Opciones de Segmentación

### Datos demográficos
- Rangos de edad
- Género
- Idiomas
- Ubicaciones

### Intereses y comportamiento
- Categorías de interés
- Interacciones con videos
- Interacciones con creadores
- Interacciones con hashtags

### Audiencias personalizadas
- Carga de archivos de clientes
- Visitantes del sitio web (pixel)
- Actividad en la aplicación
- Audiencias de engagement

## Cuándo Usar

- Llegar a demografías más jóvenes (18-34)
- Publicidad con enfoque en video
- Campañas virales/creativas
- Promoción de aplicaciones

## Límites de Tasa

- 10 solicitudes/segundo
- 100,000 solicitudes/día

## Habilidades Relacionadas

- paid-ads
- analytics-tracking
