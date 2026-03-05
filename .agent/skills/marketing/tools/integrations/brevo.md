# Brevo

Plataforma de marketing todo en uno (anteriormente Sendinblue) para email, SMS y WhatsApp con contactos, campañas y mensajería transaccional.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API v3 para contactos, campañas, email/SMS transaccional |
| MCP | - | No disponible |
| CLI | ✓ | [brevo.js](../clis/brevo.js) |
| SDK | ✓ | Node.js, Python, PHP, Ruby, Java, C#, Go |

## Autenticación

- **Tipo**: API Key
- **Header**: `api-key: {api_key}`
- **Obtener clave**: Configuración SMTP y API en https://app.brevo.com/settings/keys/api
- **Nota**: La API key solo se muestra una vez al crearla; guárdala de forma segura. Anteriormente usaba la Base URL `api.sendinblue.com`.

## Operaciones Comunes del Agente

### Obtener información de cuenta

```bash
GET https://api.brevo.com/v3/account
```

### Listar contactos

```bash
GET https://api.brevo.com/v3/contacts?limit=50&offset=0
```

### Obtener contacto por email

```bash
GET https://api.brevo.com/v3/contacts/user@example.com
```

### Crear contacto

```bash
POST https://api.brevo.com/v3/contacts

{
  "email": "user@example.com",
  "attributes": {
    "FIRSTNAME": "Jane",
    "LASTNAME": "Doe"
  },
  "listIds": [1, 2]
}
```

### Actualizar contacto

```bash
PUT https://api.brevo.com/v3/contacts/user@example.com

{
  "attributes": {
    "FIRSTNAME": "Updated"
  },
  "listIds": [3]
}
```

### Eliminar contacto

```bash
DELETE https://api.brevo.com/v3/contacts/user@example.com
```

### Importar contactos

```bash
POST https://api.brevo.com/v3/contacts/import

{
  "jsonBody": [
    { "email": "user1@example.com" },
    { "email": "user2@example.com" }
  ],
  "listIds": [1]
}
```

### Listar listas de contactos

```bash
GET https://api.brevo.com/v3/contacts/lists?limit=50&offset=0
```

### Crear lista

```bash
POST https://api.brevo.com/v3/contacts/lists

{
  "name": "Newsletter Subscribers",
  "folderId": 1
}
```

### Agregar contactos a una lista

```bash
POST https://api.brevo.com/v3/contacts/lists/{listId}/contacts/add

{
  "emails": ["user1@example.com", "user2@example.com"]
}
```

### Eliminar contactos de una lista

```bash
POST https://api.brevo.com/v3/contacts/lists/{listId}/contacts/remove

{
  "emails": ["user1@example.com"]
}
```

### Enviar email transaccional

```bash
POST https://api.brevo.com/v3/smtp/email

{
  "sender": {
    "name": "My App",
    "email": "noreply@example.com"
  },
  "to": [
    { "email": "user@example.com", "name": "Jane Doe" }
  ],
  "subject": "Order Confirmation",
  "htmlContent": "<html><body><p>Your order is confirmed.</p></body></html>"
}
```

### Listar campañas de email

```bash
GET https://api.brevo.com/v3/emailCampaigns?limit=50&offset=0&type=classic&status=sent
```

### Crear campaña de email

```bash
POST https://api.brevo.com/v3/emailCampaigns

{
  "name": "January Newsletter",
  "subject": "Monthly Update",
  "sender": { "name": "My Brand", "email": "news@example.com" },
  "htmlContent": "<html><body><p>Newsletter content</p></body></html>",
  "recipients": { "listIds": [1, 2] }
}
```

### Enviar campaña de inmediato

```bash
POST https://api.brevo.com/v3/emailCampaigns/{campaignId}/sendNow
```

### Enviar email de prueba para una campaña

```bash
POST https://api.brevo.com/v3/emailCampaigns/{campaignId}/sendTest

{
  "emailTo": ["test@example.com"]
}
```

### Enviar SMS transaccional

```bash
POST https://api.brevo.com/v3/transactionalSMS/sms

{
  "sender": "MyApp",
  "recipient": "+15551234567",
  "content": "Your verification code is 123456",
  "type": "transactional"
}
```

### Listar campañas de SMS

```bash
GET https://api.brevo.com/v3/smsCampaigns?limit=50&offset=0
```

### Listar remitentes

```bash
GET https://api.brevo.com/v3/senders
```

## Patrón de API

Brevo usa REST estándar con paginación basada en offset (parámetros `limit` y `offset`). Los atributos de contacto usan nombres de campo en mayúsculas (FIRSTNAME, LASTNAME). Las listas están anidadas bajo la ruta del recurso de contactos. El email transaccional usa el endpoint `/smtp/email` a pesar de ser basado en REST.

## Métricas Clave

### Campos de Contacto
- `email` - Dirección de email
- `attributes` - Atributos personalizados (FIRSTNAME, LASTNAME, SMS, etc.)
- `listIds` - IDs de listas asociadas
- `emailBlacklisted` - Estado de exclusión de email
- `smsBlacklisted` - Estado de exclusión de SMS
- `statistics` - Estadísticas de participación (con expand)

### Métricas de Campaña
- `sent` - Total de envíos
- `delivered` - Entregas exitosas
- `openRate` - Porcentaje de apertura
- `clickRate` - Porcentaje de clics
- `unsubscribed` - Cantidad de cancelaciones de suscripción
- `hardBounces`, `softBounces` - Conteos de rebotes

### Respuesta de Email Transaccional
- `messageId` - Identificador único del mensaje para seguimiento

## Parámetros

### Parámetros de Contacto
- `email` - Dirección de email del contacto
- `attributes` - Objeto clave-valor de atributos personalizados
- `listIds` - Array de IDs de listas a las que suscribirse
- `unlinkListIds` - Array de IDs de listas de las que desuscribirse

### Parámetros de Campaña
- `name` - Nombre de la campaña
- `subject` - Línea de asunto del email
- `sender` - Objeto con `name` y `email`
- `htmlContent` / `textContent` - Cuerpo del email
- `recipients` - Objeto con array `listIds`
- `type` - classic o trigger

## Cuándo Usar

- Marketing multicanal (email + SMS + WhatsApp)
- Envío de email transaccional con seguimiento
- Gestión de contactos y listas segmentadas
- Creación y programación de campañas de email
- Notificaciones y marketing por SMS
- Automatización de marketing todo en uno a precio accesible

## Límites de Velocidad

- Los límites de velocidad de la API dependen del plan (nivel gratuito: envíos limitados por día)
- Email transaccional: varía según el plan
- Importación de contactos: procesamiento por lotes con estado asíncrono
- Los headers de límite de velocidad se devuelven con las respuestas

## Skills Relevantes

- email-sequence
- sms-marketing
- transactional-email
- lifecycle-marketing
- contact-management
