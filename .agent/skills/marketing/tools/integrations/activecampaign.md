# ActiveCampaign

Plataforma de automatización de email marketing con CRM, contactos, pipeline de negocios, etiquetas, automatizaciones y gestión de campañas.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API v3 para contactos, negocios, automatizaciones, campañas, etiquetas |
| MCP | - | No disponible |
| CLI | ✓ | [activecampaign.js](../clis/activecampaign.js) |
| SDK | ✓ | Python, PHP, Node.js, Ruby |

## Autenticación

- **Tipo**: API Token
- **Header**: `Api-Token: {api_token}`
- **Base URL**: `https://{yourAccountName}.api-us1.com/api/3`
- **Obtener clave**: Settings > pestaña Developer en tu cuenta de ActiveCampaign
- **Nota**: Cada usuario tiene una API key única. La Base URL es específica por cuenta (se encuentra en Settings > Developer).

## Operaciones Comunes del Agente

### Obtener usuario actual

```bash
GET https://{account}.api-us1.com/api/3/users/me
```

### Listar contactos

```bash
GET https://{account}.api-us1.com/api/3/contacts?limit=20&offset=0

# Buscar por email
GET https://{account}.api-us1.com/api/3/contacts?email=user@example.com

# Buscar por nombre
GET https://{account}.api-us1.com/api/3/contacts?search=Jane
```

### Crear contacto

```bash
POST https://{account}.api-us1.com/api/3/contacts

{
  "contact": {
    "email": "user@example.com",
    "firstName": "Jane",
    "lastName": "Doe",
    "phone": "+15551234567"
  }
}
```

### Actualizar contacto

```bash
PUT https://{account}.api-us1.com/api/3/contacts/{contactId}

{
  "contact": {
    "firstName": "Updated",
    "lastName": "Name"
  }
}
```

### Sincronizar contacto (crear o actualizar)

```bash
POST https://{account}.api-us1.com/api/3/contact/sync

{
  "contact": {
    "email": "user@example.com",
    "firstName": "Jane",
    "lastName": "Doe"
  }
}
```

### Eliminar contacto

```bash
DELETE https://{account}.api-us1.com/api/3/contacts/{contactId}
```

### Listar todas las listas

```bash
GET https://{account}.api-us1.com/api/3/lists?limit=20&offset=0
```

### Crear lista

```bash
POST https://{account}.api-us1.com/api/3/lists

{
  "list": {
    "name": "Newsletter",
    "stringid": "newsletter",
    "sender_url": "https://example.com",
    "sender_reminder": "You signed up for our newsletter."
  }
}
```

### Suscribir contacto a una lista

```bash
POST https://{account}.api-us1.com/api/3/contactLists

{
  "contactList": {
    "list": "1",
    "contact": "1",
    "status": 1
  }
}
```

### Desuscribir contacto de una lista

```bash
POST https://{account}.api-us1.com/api/3/contactLists

{
  "contactList": {
    "list": "1",
    "contact": "1",
    "status": 2
  }
}
```

### Listar campañas

```bash
GET https://{account}.api-us1.com/api/3/campaigns?limit=20&offset=0
```

### Listar negocios

```bash
GET https://{account}.api-us1.com/api/3/deals?limit=20&offset=0

# Filtrar por etapa del pipeline
GET https://{account}.api-us1.com/api/3/deals?filters[stage]=1
```

### Crear negocio

```bash
POST https://{account}.api-us1.com/api/3/deals

{
  "deal": {
    "title": "New Enterprise Deal",
    "value": 50000,
    "currency": "usd",
    "group": "1",
    "stage": "1",
    "owner": "1",
    "contact": "1"
  }
}
```

### Actualizar negocio

```bash
PUT https://{account}.api-us1.com/api/3/deals/{dealId}

{
  "deal": {
    "stage": "2",
    "value": 75000
  }
}
```

### Listar automatizaciones

```bash
GET https://{account}.api-us1.com/api/3/automations?limit=20&offset=0
```

### Agregar contacto a una automatización

```bash
POST https://{account}.api-us1.com/api/3/contactAutomations

{
  "contactAutomation": {
    "contact": "1",
    "automation": "1"
  }
}
```

### Listar etiquetas

```bash
GET https://{account}.api-us1.com/api/3/tags?limit=20&offset=0
```

### Crear etiqueta

```bash
POST https://{account}.api-us1.com/api/3/tags

{
  "tag": {
    "tag": "VIP Customer",
    "tagType": "contact"
  }
}
```

### Agregar etiqueta a un contacto

```bash
POST https://{account}.api-us1.com/api/3/contactTags

{
  "contactTag": {
    "contact": "1",
    "tag": "1"
  }
}
```

### Listar pipelines (grupos de negocios)

```bash
GET https://{account}.api-us1.com/api/3/dealGroups?limit=20&offset=0
```

### Listar webhooks

```bash
GET https://{account}.api-us1.com/api/3/webhooks?limit=20&offset=0
```

### Crear webhook

```bash
POST https://{account}.api-us1.com/api/3/webhooks

{
  "webhook": {
    "name": "Contact Updated",
    "url": "https://example.com/webhook",
    "events": ["subscribe", "unsubscribe"],
    "sources": ["public", "admin", "api", "system"]
  }
}
```

## Patrón de API

ActiveCampaign usa REST con encapsulamiento de recursos (p. ej., `{ "contact": {...} }`). Las respuestas incluyen el objeto del recurso junto con metadatos. Los recursos relacionados se gestionan mediante endpoints de unión (p. ej., `/contactLists`, `/contactTags`, `/contactAutomations`). La Base URL es específica por cuenta. La paginación usa los parámetros `limit` y `offset`.

## Métricas Clave

### Campos de Contacto
- `email` - Dirección de email
- `firstName`, `lastName` - Campos de nombre
- `phone` - Número de teléfono
- `cdate` - Fecha de creación
- `udate` - Fecha de última actualización
- `deals` - Cantidad de negocios relacionados

### Campos de Negocio
- `title` - Nombre del negocio
- `value` - Valor del negocio en centavos
- `currency` - Código de moneda
- `stage` - ID de la etapa del pipeline
- `group` - ID del pipeline (grupo de negocios)
- `owner` - ID del usuario asignado
- `status` - 0 (abierto), 1 (ganado), 2 (perdido)

### Métricas de Campaña
- `sends` - Total de envíos
- `opens` - Cantidad de aperturas
- `clicks` - Cantidad de clics
- `uniqueopens` - Aperturas únicas
- `uniquelinks` - Clics únicos

## Parámetros

### Estado de Lista de Contacto
- `1` - Suscrito (activo)
- `2` - Desuscrito

### Estado de Negocio
- `0` - Abierto
- `1` - Ganado
- `2` - Perdido

### Tipos de Etiqueta
- `contact` - Etiquetas de contacto
- `deal` - Etiquetas de negocio

### Parámetros de Consulta Comunes
- `limit` - Resultados por página (predeterminado 20)
- `offset` - Omitir N resultados
- `search` - Búsqueda de texto
- `email` - Filtrar contactos por email
- `filters[stage]` - Filtrar negocios por etapa
- `filters[owner]` - Filtrar negocios por propietario

## Cuándo Usar

- Automatización de marketing con flujos de trabajo condicionales complejos
- CRM con gestión de pipeline de negocios
- Gestión de contactos con etiquetado y segmentación
- Creación y seguimiento de campañas de email
- Activar automatizaciones basadas en eventos externos
- Seguimiento del pipeline de ventas B2B integrado con marketing

## Límites de Velocidad

- 5 solicitudes por segundo por cuenta
- El límite de velocidad aplica a todos los usuarios de API en la misma cuenta
- Las respuestas 429 incluyen el header `Retry-After`

## Skills Relevantes

- email-sequence
- lifecycle-marketing
- crm-integration
- sales-pipeline
- marketing-automation
