# Calendly

API de plataforma de programación y reservas para gestionar tipos de eventos, eventos programados, invitados y disponibilidad.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API v2 - tipos de eventos, eventos programados, invitados, disponibilidad |
| MCP | - | No disponible |
| CLI | ✓ | [calendly.js](../clis/calendly.js) |
| SDK | ✓ | Sin SDK oficial; bibliotecas de la comunidad disponibles |

## Autenticación

- **Tipo**: Bearer Token (Personal Access Token u OAuth 2.0)
- **Header**: `Authorization: Bearer {token}`
- **Obtener clave**: https://calendly.com/integrations/api_webhooks (Personal Access Token)

## Operaciones Comunes del Agente

### Obtener el usuario actual

```bash
GET https://api.calendly.com/users/me
```

### Listar tipos de eventos

```bash
GET https://api.calendly.com/event_types?user={user_uri}
```

### Listar eventos programados

```bash
GET https://api.calendly.com/scheduled_events?user={user_uri}&min_start_time=2024-01-01T00:00:00Z&max_start_time=2024-12-31T23:59:59Z&status=active
```

### Obtener un evento programado

```bash
GET https://api.calendly.com/scheduled_events/{event_uuid}
```

### Listar invitados de un evento

```bash
GET https://api.calendly.com/scheduled_events/{event_uuid}/invitees
```

### Cancelar un evento programado

```bash
POST https://api.calendly.com/scheduled_events/{event_uuid}/cancellation

{
  "reason": "Cancellation reason"
}
```

### Obtener horarios disponibles

```bash
GET https://api.calendly.com/event_type_available_times?event_type={event_type_uri}&start_time=2024-01-20T00:00:00Z&end_time=2024-01-27T00:00:00Z
```

### Obtener horarios ocupados del usuario

```bash
GET https://api.calendly.com/user_busy_times?user={user_uri}&start_time=2024-01-20T00:00:00Z&end_time=2024-01-27T00:00:00Z
```

### Listar miembros de la organización

```bash
GET https://api.calendly.com/organization_memberships?organization={organization_uri}
```

### Crear suscripción a webhook

```bash
POST https://api.calendly.com/webhook_subscriptions

{
  "url": "https://example.com/webhook",
  "events": ["invitee.created", "invitee.canceled"],
  "organization": "{organization_uri}",
  "scope": "organization"
}
```

### Listar suscripciones a webhooks

```bash
GET https://api.calendly.com/webhook_subscriptions?organization={organization_uri}&scope=organization
```

### Eliminar suscripción a webhook

```bash
DELETE https://api.calendly.com/webhook_subscriptions/{webhook_uuid}
```

## Métricas Clave

### Datos de Evento Programado
- `uri` - URI único del evento
- `name` - Nombre del tipo de evento
- `status` - Estado del evento (active, canceled)
- `start_time` / `end_time` - Horario del evento
- `event_type` - URI del tipo de evento
- `location` - Detalles de la ubicación de la reunión
- `invitees_counter` - Conteo de invitados (active, limit, total)

### Datos de Invitado
- `name` - Nombre completo del invitado
- `email` - Correo electrónico del invitado
- `status` - active o canceled
- `questions_and_answers` - Respuestas a preguntas personalizadas
- `tracking` - Parámetros UTM
- `created_at` / `updated_at` - Timestamps

## Parámetros

### Listar Eventos Programados
- `user` - URI del usuario (requerido)
- `min_start_time` / `max_start_time` - Filtro de rango de fechas (ISO 8601)
- `status` - Filtrar por estado (active, canceled)
- `count` - Número de resultados (predeterminado 20, máximo 100)
- `page_token` - Token de paginación
- `sort` - Orden de clasificación (start_time:asc o start_time:desc)

### Listar Tipos de Eventos
- `user` - URI del usuario
- `organization` - URI de la organización
- `active` - Filtrar activos/inactivos
- `count` - Resultados por página
- `sort` - Orden de clasificación

## Cuándo Usar

- Recuperar datos de reuniones programadas para sincronización con CRM
- Monitorear la actividad de reservas y las tasas de conversión
- Automatizar flujos de seguimiento tras las reuniones
- Verificar disponibilidad antes de sugerir horarios de reunión
- Rastrear cancelaciones de reuniones y ausencias
- Construir interfaces de reserva personalizadas

## Límites de Tasa

- No documentados oficialmente; implementar lógica de reintento con retroceso exponencial
- Usar tasas de solicitud conservadoras (evitar ráfagas)
- Monitorear respuestas HTTP 429

## Skills Relacionadas

- lead-generation
- sales-automation
- customer-onboarding
- appointment-scheduling
