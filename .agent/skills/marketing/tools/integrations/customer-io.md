# Customer.io

Plataforma de mensajería basada en comportamiento para correo electrónico, push, SMS y mensajes in-app.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Track API, App API, Journeys API |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | ✓ | JavaScript, iOS, Android, Ruby, Python |

## Autenticación

- **Track API**: Site ID + API Key (Basic auth)
- **App API**: Bearer token
- **Header**: `Authorization: Basic {base64(site_id:api_key)}`

## Operaciones Comunes del Agente

### Identificar cliente

```bash
PUT https://track.customer.io/api/v1/customers/{customer_id}

Authorization: Basic {base64(site_id:api_key)}

{
  "email": "user@example.com",
  "created_at": 1705312800,
  "first_name": "John",
  "plan": "pro"
}
```

### Rastrear evento

```bash
POST https://track.customer.io/api/v1/customers/{customer_id}/events

Authorization: Basic {base64(site_id:api_key)}

{
  "name": "purchase",
  "data": {
    "product": "Pro Plan",
    "amount": 99
  }
}
```

### Rastrear evento anónimo

```bash
POST https://track.customer.io/api/v1/events

Authorization: Basic {base64(site_id:api_key)}

{
  "name": "page_viewed",
  "data": {
    "page": "/pricing"
  },
  "anonymous_id": "anon_123"
}
```

### Eliminar cliente

```bash
DELETE https://track.customer.io/api/v1/customers/{customer_id}

Authorization: Basic {base64(site_id:api_key)}
```

### Obtener cliente (App API)

```bash
GET https://api.customer.io/v1/customers/{customer_id}/attributes

Authorization: Bearer {app_api_key}
```

### Listar campañas

```bash
GET https://api.customer.io/v1/campaigns

Authorization: Bearer {app_api_key}
```

### Obtener métricas de campaña

```bash
GET https://api.customer.io/v1/campaigns/{campaign_id}/metrics

Authorization: Bearer {app_api_key}
```

### Activar broadcast

```bash
POST https://api.customer.io/v1/campaigns/{campaign_id}/triggers

Authorization: Bearer {app_api_key}

{
  "emails": ["user@example.com"],
  "data": {
    "coupon_code": "SAVE20"
  }
}
```

### Enviar correo electrónico transaccional

```bash
POST https://api.customer.io/v1/send/email

Authorization: Bearer {app_api_key}

{
  "transactional_message_id": "1",
  "to": "user@example.com",
  "identifiers": {
    "id": "user_123"
  },
  "message_data": {
    "order_id": "ORD-456"
  }
}
```

## JavaScript SDK

```javascript
// Inicializar
_cio.identify({
  id: 'user_123',
  email: 'user@example.com',
  created_at: 1705312800,
  plan: 'pro'
});

// Rastrear evento
_cio.track('purchase', {
  product: 'Pro Plan',
  amount: 99
});

// Rastrear vista de página
_cio.page();
```

## Conceptos Clave

- **People** - Clientes y leads
- **Segments** - Grupos dinámicos basados en atributos/comportamiento
- **Campaigns** - Secuencias de mensajes automatizadas
- **Broadcasts** - Envíos únicos
- **Transactional** - Mensajes activados por eventos

## Tipos de Atributos

- Estándar: `email`, `created_at`, `unsubscribed`
- Personalizados: Cualquier clave que definas
- Calculados: Agregaciones a partir de eventos

## Cuándo Usar

- Automatización de correo electrónico basada en comportamiento
- Mensajería multicanal (correo electrónico, push, SMS)
- Secuencias de onboarding
- Campañas de reactivación
- Mensajes transaccionales

## Límites de Tasa

- Track API: 100 solicitudes/segundo
- App API: 10 solicitudes/segundo

## Skills Relacionadas

- email-sequence
- onboarding-cro
- analytics-tracking
