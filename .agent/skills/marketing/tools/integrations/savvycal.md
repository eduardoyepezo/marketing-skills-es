# SavvyCal

API de plataforma de programación para gestionar enlaces de agendamiento, eventos, franjas horarias disponibles y webhooks.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API v1 - enlaces de agendamiento, eventos, webhooks |
| MCP | - | No disponible |
| CLI | ✓ | [savvycal.js](../clis/savvycal.js) |
| SDK | - | Sin SDK oficial |

## Autenticación

- **Tipo**: Bearer Token (Token de Acceso Personal u OAuth 2.0)
- **Header**: `Authorization: Bearer {token}`
- **Obtener clave**: Developer Settings en el panel de SavvyCal (crear un Token de Acceso Personal)

## Operaciones Comunes del Agente

### Obtener usuario actual

```bash
GET https://api.savvycal.com/v1/me
```

### Listar enlaces de agendamiento

```bash
GET https://api.savvycal.com/v1/scheduling-links
```

### Obtener un enlace de agendamiento

```bash
GET https://api.savvycal.com/v1/scheduling-links/{id}
```

### Crear un enlace de agendamiento

```bash
POST https://api.savvycal.com/v1/scheduling-links

{
  "name": "30 Minute Meeting",
  "slug": "30min",
  "duration_minutes": 30
}
```

### Actualizar un enlace de agendamiento

```bash
PATCH https://api.savvycal.com/v1/scheduling-links/{id}

{
  "name": "Updated Meeting Name"
}
```

### Eliminar un enlace de agendamiento

```bash
DELETE https://api.savvycal.com/v1/scheduling-links/{id}
```

### Duplicar un enlace de agendamiento

```bash
POST https://api.savvycal.com/v1/scheduling-links/{id}/duplicate
```

### Cambiar estado del enlace (activo/deshabilitado)

```bash
POST https://api.savvycal.com/v1/scheduling-links/{id}/toggle
```

### Obtener franjas horarias disponibles

```bash
GET https://api.savvycal.com/v1/scheduling-links/{id}/slots
```

### Listar eventos

```bash
GET https://api.savvycal.com/v1/events
```

### Obtener un evento

```bash
GET https://api.savvycal.com/v1/events/{id}
```

### Crear un evento

```bash
POST https://api.savvycal.com/v1/events

{
  "scheduling_link_id": "{link_id}",
  "start_at": "2024-01-20T10:00:00Z",
  "name": "John Doe",
  "email": "john@example.com"
}
```

### Cancelar un evento

```bash
POST https://api.savvycal.com/v1/events/{id}/cancel
```

### Listar webhooks

```bash
GET https://api.savvycal.com/v1/webhooks
```

### Crear un webhook

```bash
POST https://api.savvycal.com/v1/webhooks

{
  "url": "https://example.com/webhook",
  "events": ["event.created", "event.canceled"]
}
```

## Métricas Clave

### Datos del Enlace de Agendamiento
- `id` - Identificador único del enlace
- `name` - Nombre para mostrar
- `slug` - Slug de la URL
- `duration_minutes` - Duración de la reunión
- `state` - Activo o deshabilitado
- `url` - URL completa de agendamiento

### Datos del Evento
- `id` - Identificador único del evento
- `name` - Nombre del invitado
- `email` - Correo electrónico del invitado
- `start_at` / `end_at` - Hora de inicio y fin del evento
- `status` - Estado del evento
- `scheduling_link` - Enlace de agendamiento asociado

## Parámetros

### Listar Eventos
- `before` / `after` - Cursores de paginación
- `limit` - Resultados por página (predeterminado 20, máximo 100)

### Listar Enlaces de Agendamiento
- `before` / `after` - Cursores de paginación
- `limit` - Resultados por página

## Cuándo Usar

- Gestionar enlaces de agendamiento mediante programación
- Recuperar eventos reservados para sincronización con CRM o análisis
- Verificar franjas horarias disponibles para interfaces de reserva personalizadas
- Automatizar la creación de enlaces de agendamiento para campañas
- Monitorear la actividad de reservas mediante webhooks

## Límites de Velocidad

- No documentado oficialmente
- Implementar lógica de reintento con retroceso exponencial
- Monitorear respuestas HTTP 429

## Habilidades Relevantes

- lead-generation
- sales-automation
- appointment-scheduling
- customer-onboarding
