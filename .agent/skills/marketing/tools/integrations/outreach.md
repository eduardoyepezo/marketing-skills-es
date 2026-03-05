# Outreach

Plataforma de participación de ventas para gestionar prospectos, secuencias y campañas de salida a escala.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Prospects, Sequences, Mailings, Accounts, Tasks |
| MCP | ✓ | [Conector de Claude](https://claude.com/connectors/outreach) |
| CLI | ✓ | [outreach.js](../clis/outreach.js) |
| SDK | - | Solo REST API (formato JSON:API) |

## Autenticación

- **Tipo**: OAuth2 Bearer Token
- **Encabezado**: `Authorization: Bearer {access_token}`
- **Content-Type**: `application/vnd.api+json`
- **Obtener token**: Settings > API en https://app.outreach.io o mediante el flujo OAuth2

## Operaciones Comunes del Agente

### Listar Prospectos

```bash
curl -s https://api.outreach.io/api/v2/prospects \
  -H "Authorization: Bearer $OUTREACH_ACCESS_TOKEN" \
  -H "Content-Type: application/vnd.api+json"
```

### Obtener un Prospecto

```bash
curl -s https://api.outreach.io/api/v2/prospects/42 \
  -H "Authorization: Bearer $OUTREACH_ACCESS_TOKEN" \
  -H "Content-Type: application/vnd.api+json"
```

### Crear un Prospecto

```bash
curl -s -X POST https://api.outreach.io/api/v2/prospects \
  -H "Authorization: Bearer $OUTREACH_ACCESS_TOKEN" \
  -H "Content-Type: application/vnd.api+json" \
  -d '{
    "data": {
      "type": "prospect",
      "attributes": {
        "emails": ["jane@example.com"],
        "firstName": "Jane",
        "lastName": "Doe"
      }
    }
  }'
```

### Listar Secuencias

```bash
curl -s https://api.outreach.io/api/v2/sequences \
  -H "Authorization: Bearer $OUTREACH_ACCESS_TOKEN" \
  -H "Content-Type: application/vnd.api+json"
```

### Agregar Prospecto a una Secuencia

```bash
curl -s -X POST https://api.outreach.io/api/v2/sequenceStates \
  -H "Authorization: Bearer $OUTREACH_ACCESS_TOKEN" \
  -H "Content-Type: application/vnd.api+json" \
  -d '{
    "data": {
      "type": "sequenceState",
      "relationships": {
        "prospect": { "data": { "type": "prospect", "id": 42 } },
        "sequence": { "data": { "type": "sequence", "id": 7 } }
      }
    }
  }'
```

### Listar Mailings de una Secuencia

```bash
curl -s "https://api.outreach.io/api/v2/mailings?filter[sequence][id]=7" \
  -H "Authorization: Bearer $OUTREACH_ACCESS_TOKEN" \
  -H "Content-Type: application/vnd.api+json"
```

### Listar Cuentas

```bash
curl -s https://api.outreach.io/api/v2/accounts \
  -H "Authorization: Bearer $OUTREACH_ACCESS_TOKEN" \
  -H "Content-Type: application/vnd.api+json"
```

### Listar Tareas

```bash
curl -s "https://api.outreach.io/api/v2/tasks?filter[status]=incomplete" \
  -H "Authorization: Bearer $OUTREACH_ACCESS_TOKEN" \
  -H "Content-Type: application/vnd.api+json"
```

## Métricas Clave

### Datos del Prospecto
- `firstName`, `lastName` - Nombre
- `emails` - Direcciones de correo electrónico
- `title` - Cargo laboral
- `company` - Nombre de la empresa
- `tags` - Etiquetas del prospecto
- `engagedAt` - Marca de tiempo del último compromiso

### Datos de la Secuencia
- `name` - Nombre de la secuencia
- `enabled` - Si la secuencia está activa
- `sequenceType` - Tipo (p. ej., interval, date-based)
- `stepCount` - Número de pasos
- `openCount`, `clickCount`, `replyCount` - Métricas de participación

### Datos de Mailing
- `mailingType` - Tipo de mailing
- `state` - Estado de entrega
- `openCount`, `clickCount` - Participación
- `deliveredAt`, `openedAt`, `clickedAt` - Marcas de tiempo

## Parámetros

### Prospectos
- `page[number]` - Número de página (predeterminado: 1)
- `page[size]` - Resultados por página (predeterminado: 25, máximo: 1000)
- `filter[emails]` - Filtrar por correo electrónico
- `filter[firstName]` - Filtrar por nombre
- `filter[lastName]` - Filtrar por apellido
- `sort` - Campo de ordenamiento (p. ej., `createdAt`, `-updatedAt`)

### Secuencias
- `filter[name]` - Filtrar por nombre de secuencia
- `filter[enabled]` - Filtrar por estado activo

### Mailings
- `filter[sequence][id]` - Filtrar por ID de secuencia
- `filter[prospect][id]` - Filtrar por ID de prospecto

### Tareas
- `filter[status]` - Filtrar por estado (p. ej., `incomplete`, `complete`)
- `filter[taskType]` - Filtrar por tipo (p. ej., `call`, `email`, `action_item`)

## Cuándo Usar

- Gestionar secuencias y cadencias de ventas salientes
- Agregar prospectos a secuencias de correo electrónico automatizadas
- Rastrear la participación de prospectos en múltiples puntos de contacto
- Gestionar tareas de ventas y seguimientos
- Coordinar campañas de contacto multicanal
- Monitorear el rendimiento de las secuencias y las tasas de respuesta

## Límites de Tasa

- 10.000 solicitudes por hora por usuario
- Límite de ráfaga: 100 solicitudes por 10 segundos
- Encabezados de límite de tasa devueltos: `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset`
- Respuestas 429 cuando se superan los límites

## Skills Relevantes

- cold-email
- revops
- sales-enablement
- email-sequence
