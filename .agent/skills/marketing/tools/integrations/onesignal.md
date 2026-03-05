# OneSignal

Plataforma de notificaciones push, email, SMS y mensajería in-app para la participación de clientes a escala.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Notifications, Users, Segments, Templates, Apps |
| MCP | - | No disponible |
| CLI | ✓ | [onesignal.js](../clis/onesignal.js) |
| SDK | ✓ | JavaScript, Node.js, Python, Java, PHP, Ruby, Go, .NET |

## Autenticación

- **Tipo**: REST API Key (Basic Auth)
- **Header**: `Authorization: Basic {REST_API_KEY}`
- **App ID**: Requerido como `app_id` en el cuerpo de las solicitudes
- **Obtener credenciales**: Dashboard > Settings > Keys & IDs
- **Seguridad**: HTTPS requerido, TLS 1.2+ en el puerto 443

## Operaciones Comunes del Agente

### Enviar notificación push a un segmento

```bash
POST https://api.onesignal.com/api/v1/notifications

Headers:
  Authorization: Basic {REST_API_KEY}
  Content-Type: application/json

{
  "app_id": "YOUR_APP_ID",
  "included_segments": ["Subscribed Users"],
  "headings": { "en": "New Feature!" },
  "contents": { "en": "Check out our latest update." },
  "url": "https://example.com/feature"
}
```

### Enviar notificación a usuarios específicos

```bash
POST https://api.onesignal.com/api/v1/notifications

Headers:
  Authorization: Basic {REST_API_KEY}
  Content-Type: application/json

{
  "app_id": "YOUR_APP_ID",
  "include_aliases": { "external_id": ["user-123", "user-456"] },
  "target_channel": "push",
  "contents": { "en": "You have a new message." }
}
```

### Programar una notificación

```bash
POST https://api.onesignal.com/api/v1/notifications

Headers:
  Authorization: Basic {REST_API_KEY}
  Content-Type: application/json

{
  "app_id": "YOUR_APP_ID",
  "included_segments": ["Subscribed Users"],
  "contents": { "en": "Scheduled notification" },
  "send_after": "2025-12-01 12:00:00 GMT-0500"
}
```

### Listar notificaciones

```bash
GET https://api.onesignal.com/api/v1/notifications?app_id={APP_ID}&limit=50&offset=0

Headers:
  Authorization: Basic {REST_API_KEY}
```

### Ver una notificación

```bash
GET https://api.onesignal.com/api/v1/notifications/{notification_id}?app_id={APP_ID}

Headers:
  Authorization: Basic {REST_API_KEY}
```

### Cancelar una notificación programada

```bash
DELETE https://api.onesignal.com/api/v1/notifications/{notification_id}?app_id={APP_ID}

Headers:
  Authorization: Basic {REST_API_KEY}
```

### Listar segmentos

```bash
GET https://api.onesignal.com/api/v1/apps/{APP_ID}/segments

Headers:
  Authorization: Basic {REST_API_KEY}
```

### Crear un segmento

```bash
POST https://api.onesignal.com/api/v1/apps/{APP_ID}/segments

Headers:
  Authorization: Basic {REST_API_KEY}
  Content-Type: application/json

{
  "name": "Active Users",
  "filters": [
    { "field": "session_count", "relation": ">", "value": "5" }
  ]
}
```

### Obtener usuario por external ID

```bash
GET https://api.onesignal.com/api/v1/apps/{APP_ID}/users/by/external_id/{external_id}

Headers:
  Authorization: Basic {REST_API_KEY}
```

### Crear un usuario

```bash
POST https://api.onesignal.com/api/v1/apps/{APP_ID}/users

Headers:
  Authorization: Basic {REST_API_KEY}
  Content-Type: application/json

{
  "identity": { "external_id": "user-789" },
  "subscriptions": [
    { "type": "Email", "token": "user@example.com" }
  ],
  "tags": { "plan": "pro", "signup_source": "organic" }
}
```

### Listar plantillas

```bash
GET https://api.onesignal.com/api/v1/templates?app_id={APP_ID}

Headers:
  Authorization: Basic {REST_API_KEY}
```

## Métricas Clave

### Métricas de Notificación
- `successful` - Número de entregas exitosas
- `failed` - Número de entregas fallidas
- `converted` - Usuarios que hicieron clic o convirtieron
- `remaining` - Notificaciones aún en cola
- `errored` - Cantidad de errores
- `opened` - Cantidad de aperturas de notificación

### Métricas de Usuario
- `session_count` - Total de sesiones del usuario
- `last_active` - Marca de tiempo de última actividad
- `tags` - Metadatos personalizados clave-valor
- `subscriptions` - Canales de suscripción activos

## Parámetros

### Parámetros de Notificación
- `app_id` - ID de la aplicación (requerido)
- `included_segments` - Array de segmentos objetivo
- `excluded_segments` - Array de segmentos excluidos
- `include_aliases` - Apuntar a usuarios específicos por alias
- `target_channel` - Canal: `push`, `email`, `sms`
- `contents` - Contenido del mensaje por código de idioma
- `headings` - Título de la notificación por código de idioma
- `url` - URL de destino al hacer clic
- `data` - Payload de datos personalizados clave-valor
- `send_after` - Hora de envío programada (cadena UTC)
- `ttl` - Tiempo de vida en segundos

### Campos de Filtro de Segmento
- `session_count` - Número de sesiones
- `first_session` - Fecha de la primera sesión
- `last_session` - Fecha de la última sesión
- `tag` - Valor de etiqueta personalizada
- `language` - Idioma del usuario
- `app_version` - Versión de la app
- `country` - Código de país del usuario

## Cuándo Usar

- Enviar notificaciones push para actualizaciones del producto
- Notificaciones activadas por comportamiento del usuario
- Mensajería multicanal (push + email + SMS)
- Campañas de reenganche para usuarios inactivos
- Segmentar usuarios para mensajería dirigida
- Pruebas A/B del contenido de notificaciones
- Programar campañas promocionales

## Límites de Uso

- **Plan Gratuito**: 150 solicitudes de notificación/segundo por app
- **Plan de Pago**: 6,000 solicitudes de notificación/segundo por app
- **Operaciones de User/Subscription**: 1,000 solicitudes/segundo por app
- **Límite de ráfaga**: No más de 10 veces el total de suscriptores en 15 minutos
- **Respuesta 429**: Incluye header `RetryAfter` con los segundos de espera

## Skills Relacionados

- push-notifications
- customer-engagement
- retention-campaign
- re-engagement
- lifecycle-marketing
