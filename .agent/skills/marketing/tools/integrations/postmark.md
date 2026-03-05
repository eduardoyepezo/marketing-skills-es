# Postmark

Servicio de entrega de correo electrónico transaccional con entrega rápida, plantillas, gestión de rebotes y análisis detallados.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API para envío de correos, templates, bounces, stats |
| MCP | - | No disponible |
| CLI | ✓ | [postmark.js](../clis/postmark.js) |
| SDK | ✓ | Node.js, Ruby, Python, PHP, Java, .NET, Go |

## Autenticación

- **Tipo**: Server Token (o Account Token para operaciones a nivel de cuenta)
- **Encabezado**: `X-Postmark-Server-Token: {server_token}` (nivel de servidor)
- **Encabezado**: `X-Postmark-Account-Token: {account_token}` (nivel de cuenta)
- **Obtener clave**: Pestaña API Tokens en https://account.postmarkapp.com/servers
- **Nota**: Los tokens de servidor son por servidor; los tokens de cuenta aplican a todos los servidores

## Operaciones Comunes del Agente

### Enviar un correo electrónico individual

```bash
POST https://api.postmarkapp.com/email

{
  "From": "sender@example.com",
  "To": "recipient@example.com",
  "Subject": "Welcome!",
  "HtmlBody": "<html><body><p>Hello!</p></body></html>",
  "TextBody": "Hello!",
  "MessageStream": "outbound",
  "TrackOpens": true,
  "TrackLinks": "HtmlAndText"
}
```

### Enviar con plantilla

```bash
POST https://api.postmarkapp.com/email/withTemplate

{
  "From": "sender@example.com",
  "To": "recipient@example.com",
  "TemplateId": 12345,
  "TemplateModel": {
    "name": "Jane",
    "action_url": "https://example.com/verify"
  },
  "MessageStream": "outbound"
}
```

### Enviar correos en lote

```bash
POST https://api.postmarkapp.com/email/batch

[
  {
    "From": "sender@example.com",
    "To": "user1@example.com",
    "Subject": "Notification",
    "TextBody": "Hello user 1"
  },
  {
    "From": "sender@example.com",
    "To": "user2@example.com",
    "Subject": "Notification",
    "TextBody": "Hello user 2"
  }
]
```

### Listar plantillas

```bash
GET https://api.postmarkapp.com/templates?Count=100&Offset=0
```

### Obtener plantilla

```bash
GET https://api.postmarkapp.com/templates/{templateIdOrAlias}
```

### Crear plantilla

```bash
POST https://api.postmarkapp.com/templates

{
  "Name": "Welcome Email",
  "Alias": "welcome",
  "Subject": "Welcome {{name}}!",
  "HtmlBody": "<html><body><p>Hello {{name}}</p></body></html>",
  "TextBody": "Hello {{name}}"
}
```

### Obtener estadísticas de entrega

```bash
GET https://api.postmarkapp.com/deliverystats
```

### Listar rebotes

```bash
GET https://api.postmarkapp.com/bounces?count=50&offset=0&type=HardBounce
```

### Activar rebote (reactivar destinatario)

```bash
PUT https://api.postmarkapp.com/bounces/{bounceId}/activate
```

### Buscar mensajes salientes

```bash
GET https://api.postmarkapp.com/messages/outbound?count=50&offset=0&recipient=user@example.com
```

### Obtener resumen de estadísticas salientes

```bash
GET https://api.postmarkapp.com/stats/outbound?fromdate=2025-01-01&todate=2025-01-31
```

### Obtener estadísticas de aperturas

```bash
GET https://api.postmarkapp.com/stats/outbound/opens?fromdate=2025-01-01&todate=2025-01-31
```

### Obtener estadísticas de clics

```bash
GET https://api.postmarkapp.com/stats/outbound/clicks?fromdate=2025-01-01&todate=2025-01-31
```

### Obtener información del servidor

```bash
GET https://api.postmarkapp.com/server
```

### Listar supresiones

```bash
GET https://api.postmarkapp.com/message-streams/outbound/suppressions/dump
```

### Crear supresión

```bash
POST https://api.postmarkapp.com/message-streams/outbound/suppressions

{
  "Suppressions": [
    { "EmailAddress": "user@example.com" }
  ]
}
```

## Patrón de API

Postmark usa endpoints REST simples con nombres de campo en PascalCase en los cuerpos de solicitud/respuesta. La autenticación se realiza mediante encabezados personalizados en lugar de Authorization. La paginación usa los parámetros `Count` y `Offset`. El envío de correos es síncrono con confirmación de entrega inmediata.

## Métricas Clave

### Métricas de Entrega
- `Sent` - Total de correos enviados
- `Bounced` - Cantidad de rebotes por tipo (hard, soft, transient)
- `SpamComplaints` - Cantidad de quejas de spam
- `Opens` - Cantidad de aperturas y aperturas únicas
- `Clicks` - Cantidad de clics y clics únicos

### Tipos de Rebote
- `HardBounce` - Fallo de entrega permanente
- `SoftBounce` - Fallo de entrega temporal
- `Transient` - Problema temporal (reintentar)
- `SpamNotification` - Marcado como spam

### Campos de Mensaje
- `MessageID` - Identificador único del mensaje
- `SubmittedAt` - Marca de tiempo de envío
- `Status` - Estado de entrega
- `Recipients` - Lista de destinatarios

## Parámetros

### Parámetros de Correo Electrónico
- `From` - Dirección del remitente (debe estar verificada)
- `To` - Destinatario (separados por comas para múltiples)
- `Subject` - Asunto del correo
- `HtmlBody` / `TextBody` - Contenido del correo
- `MessageStream` - outbound (transaccional) o broadcast
- `TrackOpens` - Habilitar rastreo de aperturas (booleano)
- `TrackLinks` - None, HtmlAndText, HtmlOnly, TextOnly
- `Tag` - Etiqueta personalizada para categorización

### Parámetros de Estadísticas
- `fromdate` - Fecha de inicio (YYYY-MM-DD)
- `todate` - Fecha de fin (YYYY-MM-DD)
- `tag` - Filtrar por etiqueta

## Cuándo Usar

- Correos transaccionales (restablecimiento de contraseña, confirmaciones de pedidos, notificaciones)
- Envío de correos basado en plantillas con variables dinámicas
- Monitoreo de la entregabilidad del correo y tasas de rebote
- Rastreo de la participación por correo electrónico (aperturas, clics)
- Gestión de supresiones y rebotes de correo
- Entrega de correo de alta confiabilidad con rendimiento rápido

## Límites de Tasa

- 500 mensajes por solicitud en lote
- Máximo 10 MB por mensaje individual (incluyendo adjuntos)
- Máximo 50 MB por solicitud en lote
- Los límites de tasa de la API varían según el plan

## Skills Relevantes

- email-sequence
- transactional-email
- email-deliverability
- onboarding-email
