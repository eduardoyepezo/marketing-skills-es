# Meta Ads (Facebook/Instagram)

Plataforma de publicidad para Facebook, Instagram, Messenger y Audience Network.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Marketing API para campañas, audiencias y reportes |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | ✓ | SDKs oficiales para Python, PHP, Node.js |

## Autenticación

- **Tipo**: OAuth 2.0 Access Token
- **Header**: Access token como parámetro de consulta
- **Configuración**: Crear app en Meta Business Suite, generar token de System User

## Operaciones Comunes del Agente

### Obtener cuentas publicitarias

```bash
GET https://graph.facebook.com/v18.0/me/adaccounts?access_token={access_token}&fields=id,name,account_status
```

### Obtener campañas

```bash
GET https://graph.facebook.com/v18.0/act_{ad_account_id}/campaigns?access_token={access_token}&fields=id,name,status,objective,daily_budget
```

### Obtener insights de campaña

```bash
GET https://graph.facebook.com/v18.0/{campaign_id}/insights?access_token={access_token}&fields=impressions,clicks,spend,actions,cost_per_action_type&date_preset=last_30d
```

### Obtener conjuntos de anuncios

```bash
GET https://graph.facebook.com/v18.0/act_{ad_account_id}/adsets?access_token={access_token}&fields=id,name,status,targeting,daily_budget,bid_amount
```

### Obtener anuncios

```bash
GET https://graph.facebook.com/v18.0/{ad_set_id}/ads?access_token={access_token}&fields=id,name,status,creative
```

### Crear campaña

```bash
POST https://graph.facebook.com/v18.0/act_{ad_account_id}/campaigns

access_token={access_token}
&name=Campaign Name
&objective=CONVERSIONS
&status=PAUSED
&special_ad_categories=[]
```

### Actualizar estado de campaña

```bash
POST https://graph.facebook.com/v18.0/{campaign_id}

access_token={access_token}
&status=ACTIVE
```

### Obtener audiencias personalizadas

```bash
GET https://graph.facebook.com/v18.0/act_{ad_account_id}/customaudiences?access_token={access_token}&fields=id,name,approximate_count
```

### Crear audiencia lookalike

```bash
POST https://graph.facebook.com/v18.0/act_{ad_account_id}/customaudiences

access_token={access_token}
&name=Lookalike - Top Customers
&subtype=LOOKALIKE
&origin_audience_id={source_audience_id}
&lookalike_spec={"type":"similarity","country":"US"}
```

## Métricas Clave

| Métrica | Descripción |
|--------|-------------|
| `impressions` | Impresiones del anuncio |
| `clicks` | Total de clics |
| `spend` | Monto gastado |
| `reach` | Personas únicas alcanzadas |
| `frequency` | Promedio de impresiones por persona |
| `cpm` | Costo por 1000 impresiones |
| `cpc` | Costo por clic |
| `actions` | Array de conversiones |
| `cost_per_action_type` | CPA por acción |

## Objetivos de Campaña

- `AWARENESS` - Reconocimiento de marca
- `TRAFFIC` - Tráfico al sitio web
- `ENGAGEMENT` - Interacción con publicaciones
- `LEADS` - Generación de leads
- `APP_PROMOTION` - Instalaciones de app
- `SALES` - Conversiones/ventas de catálogo

## Opciones de Segmentación

```json
{
  "geo_locations": {
    "countries": ["US"],
    "cities": [{"key": "2420379"}]
  },
  "age_min": 25,
  "age_max": 45,
  "genders": [1, 2],
  "interests": [{"id": "6003139266461", "name": "Marketing"}],
  "behaviors": [{"id": "6002714895372"}]
}
```

## Cuándo Usar

- Crear y gestionar anuncios en Facebook e Instagram
- Segmentación de audiencias y lookalikes
- Análisis del rendimiento de campañas
- Configuración de retargeting

## Límites de Uso

- 200 llamadas/hora por cuenta publicitaria
- 60 llamadas/hora para la marketing API
- Usar solicitudes batch para mayor eficiencia

## Skills Relacionados

- paid-ads
- analytics-tracking
- page-cro
