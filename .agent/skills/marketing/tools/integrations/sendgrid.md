# SendGrid

Plataforma de entrega de correo electrónico para correos transaccionales y de marketing.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Mail Send API, Marketing API |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | ✓ | Librerías oficiales para la mayoría de lenguajes |

## Autenticación

- **Tipo**: API Key
- **Header**: `Authorization: Bearer {api_key}`
- **Obtener clave**: Settings > API Keys en el panel de SendGrid

## Operaciones Comunes del Agente

### Enviar correo electrónico

```bash
POST https://api.sendgrid.com/v3/mail/send

Authorization: Bearer {api_key}

{
  "personalizations": [{
    "to": [{"email": "user@example.com"}]
  }],
  "from": {"email": "hello@example.com"},
  "subject": "Welcome!",
  "content": [{
    "type": "text/html",
    "value": "<h1>Welcome!</h1>"
  }]
}
```

### Enviar con plantilla

```bash
POST https://api.sendgrid.com/v3/mail/send

{
  "personalizations": [{
    "to": [{"email": "user@example.com"}],
    "dynamic_template_data": {
      "name": "John",
      "order_id": "12345"
    }
  }],
  "from": {"email": "hello@example.com"},
  "template_id": "d-xxx"
}
```

### Agregar contacto a una lista

```bash
PUT https://api.sendgrid.com/v3/marketing/contacts

{
  "list_ids": ["list-id"],
  "contacts": [{
    "email": "user@example.com",
    "first_name": "John",
    "last_name": "Doe"
  }]
}
```

### Buscar contactos

```bash
POST https://api.sendgrid.com/v3/marketing/contacts/search

{
  "query": "email LIKE 'user@%'"
}
```

### Obtener estadísticas de correo electrónico

```bash
GET https://api.sendgrid.com/v3/stats?start_date=2024-01-01&end_date=2024-01-31

Authorization: Bearer {api_key}
```

### Obtener rebotes

```bash
GET https://api.sendgrid.com/v3/suppression/bounces

Authorization: Bearer {api_key}
```

### Obtener reportes de spam

```bash
GET https://api.sendgrid.com/v3/suppression/spam_reports

Authorization: Bearer {api_key}
```

### Validar correo electrónico

```bash
POST https://api.sendgrid.com/v3/validations/email

{
  "email": "user@example.com"
}
```

## Eventos de Webhook

| Evento | Descripción |
|-------|-------------|
| `processed` | Correo aceptado |
| `delivered` | Correo entregado |
| `open` | Correo abierto |
| `click` | Enlace clicado |
| `bounce` | Rebote duro/suave |
| `dropped` | Correo descartado |
| `spamreport` | Marcado como spam |
| `unsubscribe` | Suscripción cancelada |

## SDK de Node.js

```javascript
const sgMail = require('@sendgrid/mail');
sgMail.setApiKey('SG.xxx');

await sgMail.send({
  to: 'user@example.com',
  from: 'hello@example.com',
  subject: 'Welcome!',
  html: '<h1>Welcome!</h1>'
});
```

## Cuándo Usar

- Correo electrónico transaccional a escala
- Campañas de correo electrónico de marketing
- Validación de correo electrónico
- Gestión de entregabilidad

## Límites de Velocidad

- Gratuito: 100 correos/día
- De pago: Varía según el plan (hasta millones/mes)

## Habilidades Relevantes

- email-sequence
- analytics-tracking
