# Klaviyo

Plataforma de email y SMS marketing para e-commerce con perfiles, flows, campañas, segmentos y seguimiento de eventos.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API con especificación JSON:API, versionada por revisión |
| MCP | - | No disponible |
| CLI | ✓ | [klaviyo.js](../clis/klaviyo.js) |
| SDK | ✓ | Python, Node.js, Ruby, PHP, Java, C# |

## Autenticación

- **Tipo**: Clave API privada
- **Encabezado**: `Authorization: Klaviyo-API-Key {private_api_key}`
- **Encabezado de revisión**: `revision: 2024-10-15` (requerido en todas las solicitudes)
- **Obtener clave**: Configuración de cuenta > API Keys en https://www.klaviyo.com/settings/account/api-keys
- **Nota**: Las claves privadas tienen el prefijo `pk_`; las claves públicas (ID de sitio de 6 caracteres) son solo para uso del lado del cliente

## Operaciones Comunes del Agente

### Listar perfiles

```bash
GET https://a.klaviyo.com/api/profiles/?page[size]=20

# Filtrar por correo
GET https://a.klaviyo.com/api/profiles/?filter=equals(email,"user@example.com")
```

### Crear perfil

```bash
POST https://a.klaviyo.com/api/profiles/

{
  "data": {
    "type": "profile",
    "attributes": {
      "email": "user@example.com",
      "first_name": "Jane",
      "last_name": "Doe",
      "phone_number": "+15551234567"
    }
  }
}
```

### Actualizar perfil

```bash
PATCH https://a.klaviyo.com/api/profiles/{profileId}/

{
  "data": {
    "type": "profile",
    "id": "{profileId}",
    "attributes": {
      "first_name": "Updated Name"
    }
  }
}
```

### Listar todas las listas

```bash
GET https://a.klaviyo.com/api/lists/
```

### Crear lista

```bash
POST https://a.klaviyo.com/api/lists/

{
  "data": {
    "type": "list",
    "attributes": {
      "name": "Newsletter Subscribers"
    }
  }
}
```

### Agregar perfiles a una lista

```bash
POST https://a.klaviyo.com/api/lists/{listId}/relationships/profiles/

{
  "data": [
    { "type": "profile", "id": "{profileId1}" },
    { "type": "profile", "id": "{profileId2}" }
  ]
}
```

### Registrar evento

```bash
POST https://a.klaviyo.com/api/events/

{
  "data": {
    "type": "event",
    "attributes": {
      "metric": {
        "data": {
          "type": "metric",
          "attributes": { "name": "Placed Order" }
        }
      },
      "profile": {
        "data": {
          "type": "profile",
          "attributes": { "email": "user@example.com" }
        }
      },
      "properties": {
        "value": 99.99,
        "items": ["Product A"]
      },
      "time": "2025-01-15T10:00:00Z"
    }
  }
}
```

### Listar campañas

```bash
GET https://a.klaviyo.com/api/campaigns/?filter=equals(messages.channel,"email")
```

### Listar flows

```bash
GET https://a.klaviyo.com/api/flows/
```

### Actualizar estado de un flow

```bash
PATCH https://a.klaviyo.com/api/flows/{flowId}/

{
  "data": {
    "type": "flow",
    "id": "{flowId}",
    "attributes": {
      "status": "live"
    }
  }
}
```

### Listar métricas

```bash
GET https://a.klaviyo.com/api/metrics/
```

### Listar segmentos

```bash
GET https://a.klaviyo.com/api/segments/
```

## Patrón de API

Klaviyo utiliza la especificación JSON:API. Todos los cuerpos de solicitud/respuesta usan el formato `{ "data": { "type": "...", "attributes": {...} } }`. Las relaciones se gestionan mediante sub-endpoints `/relationships/`. El encabezado `revision` es obligatorio en cada solicitud y determina la versión del comportamiento de la API.

## Métricas Clave

### Campos de Perfil
- `email` - Dirección de correo electrónico
- `phone_number` - Teléfono para SMS
- `first_name`, `last_name` - Campos de nombre
- `properties` - Objeto de propiedades personalizadas
- `subscriptions` - Estado de suscripción de correo/SMS

### Campos de Evento
- `metric` - Nombre de la métrica/evento
- `properties` - Propiedades personalizadas del evento
- `time` - Marca de tiempo del evento
- `value` - Valor monetario (para seguimiento de ingresos)

### Métricas de Campaña/Flow
- `send_count` - Número de envíos
- `open_rate` - Porcentaje de apertura
- `click_rate` - Porcentaje de clics
- `revenue` - Ingresos atribuidos

## Parámetros

### Parámetros de Consulta Comunes
- `page[size]` - Resultados por página (predeterminado 20, máximo 100)
- `page[cursor]` - Cursor para paginación
- `filter` - Expresiones de filtro (ej., `equals(email,"user@example.com")`)
- `sort` - Campo de ordenamiento (prefijo `-` para descendente)
- `include` - Incluir recursos relacionados
- `fields[resource]` - Conjuntos de campos escasos

## Cuándo Usar

- Automatización de email/SMS marketing para e-commerce
- Sincronización de perfiles de clientes desde sistemas externos
- Seguimiento de eventos de compra y comportamiento de clientes
- Gestión de flows de correo y campañas drip
- Segmentación de audiencias para campañas dirigidas
- Reportes sobre rendimiento de campañas y flows

## Límites de Velocidad

- Estado estable: 75 solicitudes/segundo para la mayoría de endpoints
- Ráfaga: hasta 700 solicitudes en 1 minuto
- Encabezados de límite de velocidad: `RateLimit-Limit`, `RateLimit-Remaining`, `RateLimit-Reset`
- Límites más bajos en algunos endpoints de escritura (perfiles, eventos)

## Skills Relevantes

- email-sequence
- ecommerce-email
- lifecycle-marketing
- customer-segmentation
