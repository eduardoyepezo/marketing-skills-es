# Demio

Plataforma de webinars para alojar webinars en vivo, automatizados y bajo demanda con registro integrado y seguimiento de asistentes.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Events, Registration, Participants, Sessions |
| MCP | - | No disponible |
| CLI | ✓ | [demio.js](../clis/demio.js) |
| SDK | ✓ | PHP (oficial), Ruby (comunidad) |

## Autenticación

- **Tipo**: API Key + API Secret
- **Headers**: `Api-Key: {key}` y `Api-Secret: {secret}`
- **Obtener credenciales**: Configuración de cuenta > API (se requiere acceso de propietario)
- **Documentación**: https://publicdemioapi.docs.apiary.io/

## Operaciones Comunes del Agente

### Ping (verificación de estado)

```bash
GET https://my.demio.com/api/v1/ping

Headers:
  Api-Key: {API_KEY}
  Api-Secret: {API_SECRET}
```

### Listar todos los eventos

```bash
GET https://my.demio.com/api/v1/events

Headers:
  Api-Key: {API_KEY}
  Api-Secret: {API_SECRET}
```

### Listar eventos por tipo

```bash
GET https://my.demio.com/api/v1/events?type=upcoming

Headers:
  Api-Key: {API_KEY}
  Api-Secret: {API_SECRET}
```

### Obtener un evento específico

```bash
GET https://my.demio.com/api/v1/event/{event_id}

Headers:
  Api-Key: {API_KEY}
  Api-Secret: {API_SECRET}
```

### Obtener detalles de fecha de un evento

```bash
GET https://my.demio.com/api/v1/event/{event_id}/date/{date_id}

Headers:
  Api-Key: {API_KEY}
  Api-Secret: {API_SECRET}
```

### Registrar asistente para un evento

```bash
POST https://my.demio.com/api/v1/event/register

Headers:
  Api-Key: {API_KEY}
  Api-Secret: {API_SECRET}
  Content-Type: application/json

{
  "id": 12345,
  "name": "Jane Doe",
  "email": "jane@example.com"
}
```

### Registrar asistente para una fecha específica

```bash
POST https://my.demio.com/api/v1/event/register

Headers:
  Api-Key: {API_KEY}
  Api-Secret: {API_SECRET}
  Content-Type: application/json

{
  "id": 12345,
  "date_id": 67890,
  "name": "Jane Doe",
  "email": "jane@example.com"
}
```

### Obtener participantes para una fecha de evento

```bash
GET https://my.demio.com/api/v1/date/{date_id}/participants

Headers:
  Api-Key: {API_KEY}
  Api-Secret: {API_SECRET}
```

## Patrón de API

Demio utiliza una API REST sencilla:
- Todas las solicitudes requieren los headers `Api-Key` y `Api-Secret`
- Las respuestas son objetos JSON
- El registro devuelve una URL `join_link` para el asistente
- Los eventos tienen múltiples "fechas" (sesiones), cada una con un `date_id` único

## Métricas Clave

### Métricas de Eventos
- `id` - ID del evento
- `name` - Nombre del evento
- `date_id` - Identificador de sesión/fecha
- `status` - Estado del evento (upcoming, past, active)
- `type` - Tipo de evento (live, automated, on-demand)
- `registration_url` - URL de la página de registro pública

### Métricas de Participantes
- `name` - Nombre del participante
- `email` - Correo electrónico del participante
- `status` - Estado de asistencia (registered, attended, missed)
- `attended_minutes` - Duración de la asistencia
- `join_link` - URL de acceso única para el participante

## Parámetros

### Filtros de Lista de Eventos
- `type` - Filtrar por tipo de evento: `upcoming`, `past`, `all`

### Campos de Registro
- `id` - ID del evento (requerido)
- `name` - Nombre del registrante (requerido)
- `email` - Correo electrónico del registrante (requerido)
- `date_id` - ID de fecha de sesión específica (opcional)
- `ref_url` - URL de referencia para seguimiento (opcional)

### Campos Personalizados
- Los campos personalizados se admiten mediante su UID (no el nombre de visualización)
- Consulta la configuración de tu evento para los UIDs de campos personalizados disponibles

## Cuándo Usar

- Automatizar el registro a webinars desde páginas de destino o formularios
- Sincronizar datos de asistentes a webinars con el CRM
- Crear flujos de registro personalizados para webinars
- Seguimiento de asistencia y participación en webinars
- Activar secuencias de seguimiento según el estado de asistencia
- Gestionar múltiples sesiones de webinar de forma programática

## Límites de Velocidad

- **180 solicitudes por minuto** (3 por segundo)
- **Prueba gratuita**: 100 llamadas API por día
- **Planes de pago**: 5.000 llamadas API por día (se reinician a las 00:00 UTC)
- Contacta a Demio para solicitar límites diarios más altos
- Superar los límites devuelve una respuesta de error

## Skills Relacionadas

- webinar-marketing
- lead-generation
- event-marketing
- content-strategy
- lifecycle-marketing
