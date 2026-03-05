# Typeform

API de la plataforma de formularios y encuestas para crear typeforms, recuperar respuestas, gestionar webhooks, temas, imágenes y espacios de trabajo.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | APIs de creación, respuestas y webhooks |
| MCP | - | No disponible |
| CLI | ✓ | [typeform.js](../clis/typeform.js) |
| SDK | ✓ | JavaScript (@typeform/js-api-client), Embed SDK |

## Autenticación

- **Tipo**: Bearer Token (Token de acceso personal u OAuth 2.0)
- **Encabezado**: `Authorization: Bearer {token}`
- **Obtener clave**: https://admin.typeform.com/account#/section/tokens

## Operaciones Comunes del Agente

### Listar formularios

```bash
GET https://api.typeform.com/forms
```

### Obtener un formulario

```bash
GET https://api.typeform.com/forms/{form_id}
```

### Crear un formulario

```bash
POST https://api.typeform.com/forms

{
  "title": "Customer Feedback Survey",
  "fields": [
    {
      "type": "short_text",
      "title": "What is your name?"
    },
    {
      "type": "rating",
      "title": "How would you rate our service?",
      "properties": {
        "steps": 5
      }
    }
  ]
}
```

### Actualizar un formulario

```bash
PUT https://api.typeform.com/forms/{form_id}

{
  "title": "Updated Survey Title"
}
```

### Eliminar un formulario

```bash
DELETE https://api.typeform.com/forms/{form_id}
```

### Recuperar respuestas

```bash
GET https://api.typeform.com/forms/{form_id}/responses?page_size=25&since=2024-01-01T00:00:00Z
```

### Eliminar respuestas

```bash
DELETE https://api.typeform.com/forms/{form_id}/responses?included_response_ids={id1},{id2}
```

### Listar webhooks

```bash
GET https://api.typeform.com/forms/{form_id}/webhooks
```

### Crear o actualizar webhook

```bash
PUT https://api.typeform.com/forms/{form_id}/webhooks/{tag}

{
  "url": "https://example.com/webhook",
  "enabled": true
}
```

### Eliminar webhook

```bash
DELETE https://api.typeform.com/forms/{form_id}/webhooks/{tag}
```

### Listar temas

```bash
GET https://api.typeform.com/themes
```

### Listar imágenes

```bash
GET https://api.typeform.com/images
```

### Listar espacios de trabajo

```bash
GET https://api.typeform.com/workspaces
```

### Obtener un espacio de trabajo

```bash
GET https://api.typeform.com/workspaces/{workspace_id}
```

## Métricas Clave

### Datos de respuesta
- `response_id` - Identificador único de la respuesta
- `landed_at` / `submitted_at` - Marcas de tiempo
- `answers` - Array de respuestas a campos
- `variables` - Variables calculadas
- `hidden` - Valores de campos ocultos
- `calculated` - Cálculos de puntuación

### Datos del formulario
- `id` - ID del formulario (desde la URL)
- `title` - Título del formulario
- `fields` - Array de campos del formulario
- `logic` - Saltos de lógica
- `settings` - Configuración del formulario (notificaciones, meta, etc.)
- `_links` - URLs de visualización y respuestas

## Parámetros

### Recuperar respuestas
- `page_size` - Resultados por página (predeterminado 25, máximo 1000)
- `since` / `until` - Filtro de rango de fechas (ISO 8601 o marca de tiempo Unix)
- `after` / `before` - Tokens de paginación
- `response_type` - Filtro: started, partial, completed (predeterminado: completed)
- `query` - Búsqueda de texto dentro de las respuestas
- `fields` - Mostrar solo campos específicos en las respuestas
- `sort` - Orden de clasificación: `{fieldID},{asc|desc}`
- `included_response_ids` / `excluded_response_ids` - Filtrar respuestas específicas
- `answered_fields` - Solo respuestas que contienen los campos indicados

### Listar formularios
- `page` - Número de página
- `page_size` - Resultados por página (predeterminado 10, máximo 200)
- `workspace_id` - Filtrar por espacio de trabajo
- `search` - Buscar por título del formulario

## Cuándo Usar

- Recopilar información de leads y datos de encuestas
- Construir experiencias de formularios personalizadas de forma programática
- Automatizar la creación de encuestas para campañas
- Analizar datos de respuestas de formularios a escala
- Configurar webhooks de respuesta en tiempo real
- Gestionar temas y marca de formularios

## Límites de Tasa

- **APIs de creación y respuestas**: 2 solicitudes por segundo por cuenta
- **Webhooks y Embed**: Sin límites de tasa (basado en push)
- Monitorizar respuestas HTTP 429

## Habilidades Relacionadas

- lead-generation
- customer-research
- page-cro
- signup-flow-cro
- customer-feedback
