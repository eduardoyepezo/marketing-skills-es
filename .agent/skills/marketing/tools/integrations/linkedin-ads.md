# LinkedIn Ads

Plataforma de publicidad B2B con segmentación profesional.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Marketing API para campañas, audiencias y analíticas |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | - | Solo API (librerías de la comunidad disponibles) |

## Autenticación

- **Tipo**: OAuth 2.0
- **Header**: `Authorization: Bearer {access_token}`
- **Scopes**: `r_ads`, `r_ads_reporting`, `rw_ads`

## Operaciones Comunes del Agente

### Obtener cuentas publicitarias

```bash
GET https://api.linkedin.com/v2/adAccountsV2?q=search

Authorization: Bearer {access_token}
```

### Obtener campañas

```bash
GET https://api.linkedin.com/v2/adCampaignsV2?q=search&search.account.values[0]=urn:li:sponsoredAccount:{account_id}

Authorization: Bearer {access_token}
```

### Obtener analíticas de campaña

```bash
GET https://api.linkedin.com/v2/adAnalyticsV2?q=analytics&pivot=CAMPAIGN&dateRange.start.year=2024&dateRange.start.month=1&dateRange.start.day=1&dateRange.end.year=2024&dateRange.end.month=1&dateRange.end.day=31&campaigns=urn:li:sponsoredCampaign:{campaign_id}&fields=impressions,clicks,costInLocalCurrency,conversions

Authorization: Bearer {access_token}
```

### Crear campaña

```bash
POST https://api.linkedin.com/v2/adCampaignsV2

Authorization: Bearer {access_token}

{
  "account": "urn:li:sponsoredAccount:{account_id}",
  "name": "Campaign Name",
  "type": "SPONSORED_UPDATES",
  "costType": "CPC",
  "unitCost": {
    "amount": "5.00",
    "currencyCode": "USD"
  },
  "dailyBudget": {
    "amount": "100.00",
    "currencyCode": "USD"
  },
  "status": "PAUSED"
}
```

### Actualizar estado de campaña

```bash
POST https://api.linkedin.com/v2/adCampaignsV2/{campaign_id}

Authorization: Bearer {access_token}

{
  "patch": {
    "$set": {
      "status": "ACTIVE"
    }
  }
}
```

### Obtener creatividades

```bash
GET https://api.linkedin.com/v2/adCreativesV2?q=search&search.campaign.values[0]=urn:li:sponsoredCampaign:{campaign_id}

Authorization: Bearer {access_token}
```

### Obtener conteos de audiencia

```bash
POST https://api.linkedin.com/v2/audienceCountsV2

{
  "audienceCriteria": {
    "include": {
      "and": [{
        "or": {
          "urn:li:adTargetingFacet:titles": ["urn:li:title:123"]
        }
      }]
    }
  }
}
```

## Métricas Clave

| Métrica | Descripción |
|--------|-------------|
| `impressions` | Impresiones del anuncio |
| `clicks` | Total de clics |
| `costInLocalCurrency` | Gasto |
| `conversions` | Cantidad de conversiones |
| `leadGenerationMailContactInfoShares` | Envíos de formularios de leads |

## Tipos de Campaña

- `SPONSORED_UPDATES` - Contenido patrocinado
- `TEXT_AD` - Anuncios de texto
- `SPONSORED_INMAILS` - Anuncios de mensaje
- `DYNAMIC` - Anuncios dinámicos

## Opciones de Segmentación

### Por Cargo
- Títulos de trabajo
- Funciones laborales
- Niveles de antigüedad
- Años de experiencia

### Por Empresa
- Nombres de empresas
- Industrias
- Tamaño de empresa
- Seguidores de empresa

### Profesional
- Habilidades
- Grupos
- Instituciones educativas
- Títulos académicos

## Cuándo Usar

- Publicidad B2B
- Segmentación por cargo
- Marketing basado en cuentas
- Campañas de generación de leads

## Límites de Uso

- 100 solicitudes/día (básico)
- 10,000 solicitudes/día (Marketing Developer Platform)

## Skills Relacionados

- paid-ads
- analytics-tracking
