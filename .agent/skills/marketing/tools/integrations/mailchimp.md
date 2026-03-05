# Mailchimp

Plataforma de email marketing para campañas, automatización y gestión de audiencias.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Marketing API para campañas, audiencias y automatización |
| MCP | ✓ | Disponible a través del servidor MCP de Mailchimp |
| CLI | - | No disponible |
| SDK | ✓ | SDKs oficiales para múltiples lenguajes |

## Autenticación

- **Tipo**: API Key u OAuth 2.0
- **Header**: `Authorization: Bearer {api_key}` o `Authorization: apikey {api_key}`
- **URL Base**: `https://{dc}.api.mailchimp.com/3.0/` (dc = datacenter de la API key)

## Operaciones Comunes del Agente

### Listar audiencias (listas)

```bash
GET https://{dc}.api.mailchimp.com/3.0/lists
```

### Obtener miembros de una audiencia

```bash
GET https://{dc}.api.mailchimp.com/3.0/lists/{list_id}/members?count=100
```

### Agregar suscriptor

```bash
POST https://{dc}.api.mailchimp.com/3.0/lists/{list_id}/members

{
  "email_address": "user@example.com",
  "status": "subscribed",
  "merge_fields": {
    "FNAME": "John",
    "LNAME": "Doe"
  }
}
```

### Actualizar suscriptor

```bash
PATCH https://{dc}.api.mailchimp.com/3.0/lists/{list_id}/members/{subscriber_hash}

{
  "merge_fields": {
    "FNAME": "Jane"
  },
  "tags": ["customer", "premium"]
}
```

### Obtener campañas

```bash
GET https://{dc}.api.mailchimp.com/3.0/campaigns?count=20
```

### Obtener reporte de campaña

```bash
GET https://{dc}.api.mailchimp.com/3.0/reports/{campaign_id}
```

### Crear campaña

```bash
POST https://{dc}.api.mailchimp.com/3.0/campaigns

{
  "type": "regular",
  "recipients": {
    "list_id": "{list_id}"
  },
  "settings": {
    "subject_line": "Your Subject",
    "from_name": "Your Name",
    "reply_to": "reply@example.com"
  }
}
```

### Enviar campaña

```bash
POST https://{dc}.api.mailchimp.com/3.0/campaigns/{campaign_id}/actions/send
```

### Listar automatizaciones

```bash
GET https://{dc}.api.mailchimp.com/3.0/automations
```

## Métricas Clave

### Campos del Reporte de Campaña
- `emails_sent` - Total enviados
- `opens` - Cantidad de aperturas
- `unique_opens` - Aperturas únicas
- `open_rate` - Tasa de apertura
- `clicks` - Cantidad de clics
- `click_rate` - Tasa de clics
- `unsubscribes` - Cantidad de bajas
- `bounces` - Cantidad de rebotes

### Hash de Suscriptor

Calcular el hash del suscriptor para actualizaciones:
```javascript
const hash = md5(email.toLowerCase());
```

## Estados de Suscriptor

- `subscribed` - Suscriptor activo
- `unsubscribed` - Dado de baja
- `cleaned` - Rebote duro
- `pending` - Pendiente de confirmación
- `transactional` - Solo transaccional

## Cuándo Usar

- Gestionar listas de correo y suscriptores
- Crear y enviar campañas de email
- Configurar automatización de email
- Analizar el rendimiento de campañas
- Segmentar audiencias
- Pruebas A/B de emails

## Límites de Uso

- 10 conexiones simultáneas
- 10 solicitudes por segundo
- Endpoints batch para operaciones masivas

## Skills Relacionados

- email-sequence
- analytics-tracking
- referral-program
