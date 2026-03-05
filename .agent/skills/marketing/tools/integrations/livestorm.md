# Livestorm

Plataforma de participación por video para webinars, eventos virtuales y reuniones en línea con analíticas integradas e integraciones.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Eventos, Sesiones, Personas, Grabaciones, Webhooks |
| MCP | - | No disponible |
| CLI | ✓ | [livestorm.js](../clis/livestorm.js) |
| SDK | - | REST API con formato JSON:API |

## Autenticación

- **Tipo**: API Token
- **Header**: `Authorization: {API_TOKEN}` (sin prefijo)
- **Content-Type**: `application/vnd.api+json` (JSON:API)
- **Scopes**: Identity, Events, Admin, Webhooks
- **Obtener token**: Account Settings > Integrations > Public API
- **Documentación**: https://developers.livestorm.co/

## Operaciones Comunes del Agente

### Ping (verificar autenticación)

```bash
GET https://api.livestorm.co/v1/ping

Headers:
  Authorization: {API_TOKEN}
  Accept: application/vnd.api+json
```

### Listar eventos

```bash
GET https://api.livestorm.co/v1/events?page[number]=1&page[size]=25

Headers:
  Authorization: {API_TOKEN}
  Accept: application/vnd.api+json
```

### Crear un evento

```bash
POST https://api.livestorm.co/v1/events

Headers:
  Authorization: {API_TOKEN}
  Content-Type: application/vnd.api+json

{
  "data": {
    "type": "events",
    "attributes": {
      "title": "Product Demo Webinar",
      "slug": "product-demo-webinar",
      "estimated_duration": 60
    }
  }
}
```

### Obtener detalles de un evento

```bash
GET https://api.livestorm.co/v1/events/{event_id}

Headers:
  Authorization: {API_TOKEN}
  Accept: application/vnd.api+json
```

### Actualizar un evento

```bash
PATCH https://api.livestorm.co/v1/events/{event_id}

Headers:
  Authorization: {API_TOKEN}
  Content-Type: application/vnd.api+json

{
  "data": {
    "type": "events",
    "id": "{event_id}",
    "attributes": {
      "title": "Updated Webinar Title"
    }
  }
}
```

### Listar sesiones

```bash
GET https://api.livestorm.co/v1/sessions?page[number]=1&page[size]=25

Headers:
  Authorization: {API_TOKEN}
  Accept: application/vnd.api+json
```

### Crear una sesión para un evento

```bash
POST https://api.livestorm.co/v1/events/{event_id}/sessions

Headers:
  Authorization: {API_TOKEN}
  Content-Type: application/vnd.api+json

{
  "data": {
    "type": "sessions",
    "attributes": {
      "estimated_started_at": "2025-06-15T14:00:00.000Z",
      "timezone": "America/New_York"
    }
  }
}
```

### Registrar a alguien en una sesión

```bash
POST https://api.livestorm.co/v1/sessions/{session_id}/people

Headers:
  Authorization: {API_TOKEN}
  Content-Type: application/vnd.api+json

{
  "data": {
    "type": "people",
    "attributes": {
      "fields": {
        "email": "attendee@example.com",
        "first_name": "Jane",
        "last_name": "Doe"
      }
    }
  }
}
```

### Listar participantes de una sesión

```bash
GET https://api.livestorm.co/v1/sessions/{session_id}/people?page[number]=1&page[size]=25

Headers:
  Authorization: {API_TOKEN}
  Accept: application/vnd.api+json
```

### Eliminar un registrante de una sesión

```bash
DELETE https://api.livestorm.co/v1/sessions/{session_id}/people?filter[email]=attendee@example.com

Headers:
  Authorization: {API_TOKEN}
```

### Listar mensajes del chat de una sesión

```bash
GET https://api.livestorm.co/v1/sessions/{session_id}/chat-messages

Headers:
  Authorization: {API_TOKEN}
  Accept: application/vnd.api+json
```

### Listar preguntas de una sesión

```bash
GET https://api.livestorm.co/v1/sessions/{session_id}/questions

Headers:
  Authorization: {API_TOKEN}
  Accept: application/vnd.api+json
```

### Obtener grabaciones de una sesión

```bash
GET https://api.livestorm.co/v1/sessions/{session_id}/recordings

Headers:
  Authorization: {API_TOKEN}
  Accept: application/vnd.api+json
```

### Listar todas las personas

```bash
GET https://api.livestorm.co/v1/people?page[number]=1&page[size]=25

Headers:
  Authorization: {API_TOKEN}
  Accept: application/vnd.api+json
```

### Crear un webhook

```bash
POST https://api.livestorm.co/v1/webhooks

Headers:
  Authorization: {API_TOKEN}
  Content-Type: application/vnd.api+json

{
  "data": {
    "type": "webhooks",
    "attributes": {
      "target_url": "https://example.com/webhook",
      "event_name": "attendance"
    }
  }
}
```

## Patrón de API

Livestorm sigue la especificación JSON:API:
- Todas las respuestas usan la estructura `data`, `attributes`, `relationships`
- Paginación: parámetros de consulta `page[number]` y `page[size]`
- Filtrado: parámetros de consulta `filter[field]=value`
- Los eventos contienen múltiples sesiones; las sesiones contienen personas
- Marcas de tiempo ISO 8601 en todo momento

## Métricas Clave

### Métricas de Evento
- `title` - Título del evento
- `slug` - Identificador amigable para URL
- `estimated_duration` - Duración en minutos
- `registration_page_enabled` - Estado de la página de registro
- `everyone_can_speak` - Si todos los asistentes pueden hablar

### Métricas de Sesión
- `status` - Estado de la sesión (upcoming, live, past)
- `estimated_started_at` - Hora de inicio programada
- `started_at` - Hora de inicio real
- `ended_at` - Hora de finalización real
- `timezone` - Zona horaria de la sesión
- `attendees_count` - Número de asistentes
- `registrants_count` - Número de registrados

### Métricas de Personas
- `email` - Correo electrónico de contacto
- `first_name` / `last_name` - Nombre del contacto
- `registrant_detail` - Metadatos de registro
- `attendance_rate` - Porcentaje de asistencia
- `attended_at` - Marca de tiempo de ingreso
- `left_at` - Marca de tiempo de salida

## Parámetros

### Paginación
- `page[number]` - Número de página (por defecto: 1)
- `page[size]` - Elementos por página (por defecto: 25)

### Atributos de Evento
- `title` - Título del evento (requerido para crear)
- `slug` - Slug de URL
- `description` - Descripción del evento
- `estimated_duration` - Duración en minutos

### Atributos de Sesión
- `estimated_started_at` - Hora de inicio en ISO 8601
- `timezone` - Cadena de zona horaria IANA

### Campos de Registro
- `email` - Correo electrónico del registrante (requerido)
- `first_name` - Nombre
- `last_name` - Apellido

### Eventos de Webhook
- `attendance` - Se activa al asistir a una sesión
- `registration` - Se activa al registrarse
- `unregistration` - Se activa al cancelar el registro

## Cuándo Usar

- Alojar demostraciones de producto y webinars de marketing
- Registro automatizado de webinars y gestión de asistentes
- Seguimiento del compromiso y tasas de asistencia a webinars
- Recuperar grabaciones de sesiones para reutilización de contenido
- Crear páginas de registro personalizadas con registro vía API
- Sincronizar datos de webinar con CRM y automatización de marketing
- Monitorear preguntas y chat de sesiones para seguimiento posterior

## Límites de Uso

- **10,000 llamadas a la API por período de 30 días** (a nivel de organización)
- Los límites de uso se comparten entre todos los tokens de API de la organización
- Planificar en consecuencia para operaciones de alto volumen
- Usar webhooks en lugar de polling para conservar la cuota

## Skills Relacionados

- webinar-marketing
- event-marketing
- lead-generation
- content-strategy
- lifecycle-marketing
- customer-engagement
