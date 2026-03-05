# Beehiiv

Plataforma de newsletters con gestión de suscriptores, publicación de posts, automatizaciones y programas de referidos.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API v2 para publicaciones, suscripciones, posts, segmentos |
| MCP | - | No disponible |
| CLI | ✓ | [beehiiv.js](../clis/beehiiv.js) |
| SDK | - | Sin SDK oficial; especificación OpenAPI disponible para generación de código |

## Autenticación

- **Tipo**: Bearer Token
- **Header**: `Authorization: Bearer {api_key}`
- **Obtener clave**: Settings > API en Workspace Settings en https://app.beehiiv.com
- **Nota**: La API key solo se muestra una vez al crearla; cópiala y guárdala de inmediato

## Operaciones Comunes del Agente

### Listar publicaciones

```bash
GET https://api.beehiiv.com/v2/publications
```

### Obtener detalles de publicación

```bash
GET https://api.beehiiv.com/v2/publications/{publicationId}
```

### Listar suscripciones

```bash
GET https://api.beehiiv.com/v2/publications/{publicationId}/subscriptions?limit=10&status=active

# Filtrar por email
GET https://api.beehiiv.com/v2/publications/{publicationId}/subscriptions?email=user@example.com
```

### Crear suscripción

```bash
POST https://api.beehiiv.com/v2/publications/{publicationId}/subscriptions

{
  "email": "user@example.com",
  "reactivate_existing": false,
  "send_welcome_email": true,
  "utm_source": "api",
  "tier": "free"
}
```

### Actualizar suscripción

```bash
PUT https://api.beehiiv.com/v2/publications/{publicationId}/subscriptions/{subscriptionId}

{
  "tier": "premium"
}
```

### Eliminar suscripción

```bash
DELETE https://api.beehiiv.com/v2/publications/{publicationId}/subscriptions/{subscriptionId}
```

### Listar posts

```bash
GET https://api.beehiiv.com/v2/publications/{publicationId}/posts?limit=10&status=confirmed
```

### Crear post (solo Enterprise)

```bash
POST https://api.beehiiv.com/v2/publications/{publicationId}/posts

{
  "title": "Weekly Update",
  "subtitle": "What happened this week",
  "content": "<p>Hello subscribers...</p>",
  "status": "draft"
}
```

### Listar segmentos

```bash
GET https://api.beehiiv.com/v2/publications/{publicationId}/segments
```

### Listar automatizaciones

```bash
GET https://api.beehiiv.com/v2/publications/{publicationId}/automations
```

### Obtener programa de referidos

```bash
GET https://api.beehiiv.com/v2/publications/{publicationId}/referral_program
```

## Patrón de API

Todos los endpoints están vinculados a una publicación. El ID de publicación es un parámetro de ruta requerido para la mayoría de las operaciones. Las respuestas usan paginación basada en cursor con un parámetro `cursor` para obtener páginas siguientes.

## Métricas Clave

### Campos de Suscripción
- `status` - validating, invalid, pending, active, inactive
- `tier` - free o premium
- `created` - Marca de tiempo de creación de la suscripción
- `utm_source`, `utm_medium`, `utm_campaign` - Seguimiento de adquisición
- `referral_code` - Código de referido único del suscriptor

### Campos de Post
- `status` - draft, confirmed (programado), archived
- `publish_date` - Cuándo fue/será publicado el post
- `stats` - Tasa de apertura, tasa de clics, conteo de suscriptores (con expand)

## Parámetros

### Parámetros de Consulta Comunes
- `limit` - Resultados por página (1-100, predeterminado 10)
- `cursor` - Cursor para la siguiente página de resultados
- `expand[]` - Incluir datos adicionales: stats, custom_fields, referrals
- `status` - Filtrar por estado de suscripción/post
- `tier` - Filtrar por nivel de suscripción (free, premium)

## Cuándo Usar

- Gestionar suscriptores de newsletter de forma programática
- Sincronizar suscriptores desde formularios de registro externos o landing pages
- Construir integraciones de programas de referidos
- Automatizar flujos de trabajo de creación y publicación de posts
- Seguimiento del crecimiento y métricas de participación de suscriptores

## Límites de Velocidad

- Los límites de velocidad de la API aplican por API key
- Usar paginación basada en cursor para recuperación eficiente de datos
- Las operaciones por lotes no están disponibles; iterar con solicitudes individuales

## Skills Relevantes

- email-sequence
- newsletter-growth
- referral-program
- content-strategy
