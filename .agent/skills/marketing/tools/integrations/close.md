# Close

CRM de ventas para PYMEs con llamadas, correo electrónico y gestión de pipeline integrados, diseñado para equipos de ventas de alta velocidad.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Leads, Contacts, Opportunities, Activities, Tasks |
| MCP | - | No disponible |
| CLI | ✓ | [close.js](../clis/close.js) |
| SDK | - | Solo REST API |

## Autenticación

- **Tipo**: Basic Auth
- **Header**: `Authorization: Basic {base64(api_key + ':')}`
- **Obtener clave**: Settings > API Keys en https://app.close.com

## Operaciones Comunes del Agente

### Listar Leads

```bash
GET https://api.close.com/api/v1/lead/

Authorization: Basic {base64(api_key + ':')}
```

### Buscar Leads

```bash
GET https://api.close.com/api/v1/lead/?query=company_name

Authorization: Basic {base64(api_key + ':')}
```

### Crear Lead

```bash
POST https://api.close.com/api/v1/lead/

{
  "name": "Acme Corp",
  "url": "https://acme.com",
  "description": "Enterprise prospect"
}
```

### Obtener Contacto

```bash
GET https://api.close.com/api/v1/contact/{contact_id}/

Authorization: Basic {base64(api_key + ':')}
```

### Crear Contacto

```bash
POST https://api.close.com/api/v1/contact/

{
  "lead_id": "lead_xxx",
  "name": "Jane Smith",
  "emails": [{ "email": "jane@acme.com", "type": "office" }],
  "phones": [{ "phone": "+15551234567", "type": "office" }]
}
```

### Crear Oportunidad

```bash
POST https://api.close.com/api/v1/opportunity/

{
  "lead_id": "lead_xxx",
  "value": 50000,
  "status_type": "active"
}
```

### Listar Actividades

```bash
GET https://api.close.com/api/v1/activity/?lead_id=lead_xxx

Authorization: Basic {base64(api_key + ':')}
```

### Crear Tarea

```bash
POST https://api.close.com/api/v1/task/

{
  "lead_id": "lead_xxx",
  "text": "Follow up on demo request",
  "_type": "lead",
  "date": "2026-03-10"
}
```

## Métricas Clave

### Datos de Lead
- `id` - ID del lead
- `display_name` - Nombre del lead
- `url` - URL del sitio web
- `description` - Descripción del lead
- `status_id` - Estado del pipeline
- `contacts` - Contactos asociados
- `opportunities` - Oportunidades asociadas
- `tasks` - Tareas asociadas

### Datos de Contacto
- `id` - ID del contacto
- `lead_id` - Lead padre
- `name` - Nombre completo
- `title` - Cargo
- `emails` - Array de direcciones de correo electrónico
- `phones` - Array de números de teléfono

### Datos de Oportunidad
- `id` - ID de la oportunidad
- `lead_id` - Lead padre
- `value` - Valor en centavos
- `status_type` - active, won o lost
- `confidence` - Probabilidad de cierre (0-100)
- `date_won` - Fecha de cierre

### Datos de Tarea
- `id` - ID de la tarea
- `lead_id` - Lead padre
- `text` - Descripción de la tarea
- `assigned_to` - ID del usuario asignado
- `date` - Fecha de vencimiento
- `is_complete` - Estado de completitud

## Parámetros

### Leads
- `query` - Cadena de búsqueda
- `_skip` - Número de resultados a omitir (paginación)
- `_limit` - Máximo de resultados a devolver (predeterminado: 100)
- `_fields` - Campos a devolver separados por comas

### Contactos
- `lead_id` - Filtrar por lead padre
- `_skip` - Desplazamiento de paginación
- `_limit` - Máximo de resultados

### Oportunidades
- `lead_id` - Filtrar por lead padre
- `status` - Filtrar por tipo de estado (active, won, lost)
- `_skip` - Desplazamiento de paginación
- `_limit` - Máximo de resultados

### Actividades
- `lead_id` - Filtrar por lead
- `_type__type` - Filtrar por tipo (Email, Call, Note, SMS, Meeting)
- `date_created__gt` - Después de la fecha
- `date_created__lt` - Antes de la fecha

### Tareas
- `assigned_to` - Filtrar por ID de usuario
- `is_complete` - Filtrar por completitud (true/false)
- `lead_id` - Filtrar por lead
- `_type` - Tipo de tarea (lead)

## Cuándo Usar

- Gestionar pipelines de ventas para PYMEs con prospección intensiva
- Rastrear actividades de ventas (llamadas, correos, reuniones) por lead
- Crear y gestionar tareas para seguimientos de ventas
- Seguimiento de oportunidades y pronóstico de ingresos
- Construir flujos de trabajo de prospección automatizados
- Reportes de rendimiento del equipo de ventas

## Límites de Tasa

- Los límites de tasa dependen del plan de la organización
- Standard: ~100 solicitudes/minuto
- Las respuestas incluyen los headers `ratelimit-limit` y `ratelimit-remaining`
- Las respuestas 429 incluyen el header `Retry-After`

## Skills Relacionadas

- revops
- sales-enablement
- cold-email
