# Segment

Plataforma de datos de clientes para recopilar, enrutar y activar datos de usuarios.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Tracking API, Profile API, Config API |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | ✓ | analytics.js, iOS, Android, librerías de servidor |

## Autenticación

- **Seguimiento**: Write Key (por fuente)
- **API**: Access Token (OAuth 2.0)
- **Header**: `Authorization: Bearer {access_token}`

## Operaciones Comunes del Agente

### Registrar evento

```bash
POST https://api.segment.io/v1/track

Authorization: Basic {base64(write_key:)}

{
  "userId": "user_123",
  "event": "signup_completed",
  "properties": {
    "plan": "pro",
    "method": "email"
  }
}
```

### Identificar usuario

```bash
POST https://api.segment.io/v1/identify

Authorization: Basic {base64(write_key:)}

{
  "userId": "user_123",
  "traits": {
    "email": "user@example.com",
    "name": "John Doe",
    "plan": "pro"
  }
}
```

### Registrar vista de página

```bash
POST https://api.segment.io/v1/page

Authorization: Basic {base64(write_key:)}

{
  "userId": "user_123",
  "name": "Pricing",
  "properties": {
    "title": "Pricing - Example",
    "url": "https://example.com/pricing"
  }
}
```

### Eventos en lote

```bash
POST https://api.segment.io/v1/batch

Authorization: Basic {base64(write_key:)}

{
  "batch": [
    {"type": "identify", "userId": "user_1", "traits": {"plan": "free"}},
    {"type": "track", "userId": "user_1", "event": "signup"}
  ]
}
```

### Obtener perfil de usuario (Profile API)

```bash
GET https://profiles.segment.com/v1/spaces/{space_id}/collections/users/profiles/user_id:{user_id}/traits

Authorization: Basic {base64(access_token:)}
```

### Obtener eventos de usuario

```bash
GET https://profiles.segment.com/v1/spaces/{space_id}/collections/users/profiles/user_id:{user_id}/events

Authorization: Basic {base64(access_token:)}
```

## SDK de JavaScript

```javascript
// Inicializar
analytics.load('WRITE_KEY');

// Identificar usuario
analytics.identify('user_123', {
  email: 'user@example.com',
  plan: 'pro'
});

// Registrar evento
analytics.track('Feature Used', {
  feature_name: 'export'
});

// Vista de página
analytics.page('Pricing');
```

## Conceptos Clave

- **Sources** - De dónde provienen los datos (sitio web, aplicación, servidor)
- **Destinations** - A dónde van los datos (análisis, CRM, anuncios)
- **Tracking Plan** - Esquema para eventos y propiedades
- **Protocols** - Gobernanza y validación de datos
- **Personas** - Perfiles unificados de usuarios
- **Audiences** - Segmentos de usuarios calculados

## Destinos Comunes

- Análisis: GA4, Mixpanel, Amplitude
- CRM: HubSpot, Salesforce
- Correo electrónico: Customer.io, Mailchimp
- Anuncios: Google Ads, Meta
- Almacén de datos: BigQuery, Snowflake

## Cuándo Usar

- Centralizar el seguimiento de eventos
- Enrutar datos a múltiples herramientas
- Mantener un seguimiento consistente
- Construir perfiles unificados de usuarios
- Sincronizar audiencias entre plataformas

## Límites de Velocidad

- 500 solicitudes/segundo por fuente
- Lotes de hasta 500KB o 32KB por evento

## Habilidades Relevantes

- analytics-tracking
- email-sequence
- paid-ads
