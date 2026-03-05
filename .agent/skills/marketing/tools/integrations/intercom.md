# Intercom

API de plataforma de mensajería y soporte al cliente para gestionar contactos, conversaciones, mensajes, empresas, artículos y etiquetas.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API v2.11+ - contactos, conversaciones, mensajes, empresas, artículos, etiquetas |
| MCP | - | No disponible |
| CLI | ✓ | [intercom.js](../clis/intercom.js) |
| SDK | ✓ | Node.js, Ruby, Python, PHP, Go |

## Autenticación

- **Tipo**: Bearer Token (Access Token u OAuth 2.0)
- **Encabezado**: `Authorization: Bearer {token}`
- **Encabezado de versión**: `Intercom-Version: 2.11`
- **Obtener clave**: Developer Hub en https://app.intercom.com/a/apps/_/developer-hub

## Operaciones Comunes del Agente

### Listar contactos

```bash
GET https://api.intercom.io/contacts
```

### Obtener un contacto

```bash
GET https://api.intercom.io/contacts/{id}
```

### Crear un contacto

```bash
POST https://api.intercom.io/contacts

{
  "role": "user",
  "email": "user@example.com",
  "name": "Jane Doe",
  "custom_attributes": {
    "plan": "pro"
  }
}
```

### Actualizar un contacto

```bash
PUT https://api.intercom.io/contacts/{id}

{
  "name": "Jane Smith",
  "custom_attributes": {
    "plan": "enterprise"
  }
}
```

### Buscar contactos

```bash
POST https://api.intercom.io/contacts/search

{
  "query": {
    "field": "email",
    "operator": "=",
    "value": "user@example.com"
  }
}
```

### Eliminar un contacto

```bash
DELETE https://api.intercom.io/contacts/{id}
```

### Listar conversaciones

```bash
GET https://api.intercom.io/conversations
```

### Obtener una conversación

```bash
GET https://api.intercom.io/conversations/{id}
```

### Buscar conversaciones

```bash
POST https://api.intercom.io/conversations/search

{
  "query": {
    "field": "open",
    "operator": "=",
    "value": true
  }
}
```

### Responder a una conversación

```bash
POST https://api.intercom.io/conversations/{id}/reply

{
  "message_type": "comment",
  "type": "admin",
  "admin_id": "{admin_id}",
  "body": "Thanks for reaching out!"
}
```

### Crear un mensaje

```bash
POST https://api.intercom.io/messages

{
  "message_type": "inapp",
  "body": "Welcome to our platform!",
  "from": {
    "type": "admin",
    "id": "{admin_id}"
  },
  "to": {
    "type": "user",
    "id": "{user_id}"
  }
}
```

### Listar empresas

```bash
GET https://api.intercom.io/companies
```

### Crear o actualizar una empresa

```bash
POST https://api.intercom.io/companies

{
  "company_id": "company_123",
  "name": "Acme Corp",
  "plan": "enterprise",
  "custom_attributes": {
    "industry": "Technology"
  }
}
```

### Listar etiquetas

```bash
GET https://api.intercom.io/tags
```

### Crear una etiqueta

```bash
POST https://api.intercom.io/tags

{
  "name": "VIP Customer"
}
```

### Etiquetar un contacto

```bash
POST https://api.intercom.io/contacts/{contact_id}/tags

{
  "id": "{tag_id}"
}
```

### Listar artículos

```bash
GET https://api.intercom.io/articles
```

### Crear un artículo

```bash
POST https://api.intercom.io/articles

{
  "title": "Getting Started Guide",
  "body": "<p>Welcome to our platform...</p>",
  "author_id": "{admin_id}",
  "state": "published"
}
```

### Listar administradores

```bash
GET https://api.intercom.io/admins
```

### Enviar eventos

```bash
POST https://api.intercom.io/events

{
  "event_name": "purchased-item",
  "created_at": 1706140800,
  "user_id": "user_123",
  "metadata": {
    "item_name": "Pro Plan",
    "price": 99.00
  }
}
```

## Métricas Clave

### Datos de Contacto
- `id` - Identificador único del contacto
- `role` - user o lead
- `email` - Correo del contacto
- `name` - Nombre del contacto
- `created_at` / `updated_at` - Marcas de tiempo
- `last_seen_at` - Última actividad
- `custom_attributes` - Campos de datos personalizados
- `tags` - Etiquetas aplicadas
- `companies` - Empresas asociadas

### Datos de Conversación
- `id` - Identificador de la conversación
- `state` - open, closed, snoozed
- `open` - Estado abierto booleano
- `read` - Estado de lectura
- `priority` - Nivel de prioridad
- `statistics` - Tiempos de respuesta y conteos
- `conversation_parts` - Historial de mensajes

## Parámetros

### Listar Contactos
- `per_page` - Resultados por página (predeterminado 50, máximo 150)
- `starting_after` - Cursor de paginación

### Listar Conversaciones
- `per_page` - Resultados por página (predeterminado 20, máximo 150)
- `starting_after` - Cursor de paginación

### Búsqueda (Contactos y Conversaciones)
- `query.field` - Campo a buscar
- `query.operator` - Operador de comparación (=, !=, >, <, ~, IN, NIN)
- `query.value` - Valor de búsqueda
- `pagination.per_page` - Resultados por página
- `pagination.starting_after` - Cursor para la siguiente página
- `sort.field` / `sort.order` - Configuración de orden

## Cuándo Usar

- Gestionar registros y segmentos de contactos de clientes
- Automatizar la mensajería y el onboarding de clientes
- Monitorear y responder a conversaciones de soporte
- Rastrear eventos y comportamiento de clientes
- Crear flujos de trabajo de soporte personalizados
- Sincronizar datos de clientes entre plataformas

## Límites de Velocidad

- **Predeterminado**: 10,000 llamadas API por minuto por aplicación
- **Por espacio de trabajo**: 25,000 llamadas API por minuto
- Distribuidas en ventanas de 10 segundos (se restablece cada 10 segundos)
- Encabezados: `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset`
- Se devuelve HTTP 429 cuando se supera el límite

## Skills Relevantes

- customer-onboarding
- customer-retention
- lead-generation
- customer-support
- in-app-messaging
