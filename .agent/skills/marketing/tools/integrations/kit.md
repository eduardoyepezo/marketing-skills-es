# Kit (anteriormente ConvertKit)

Plataforma de email marketing para creadores y negocios de newsletters.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API para suscriptores, formularios, secuencias |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | ✓ | Disponibles gems de JavaScript y Ruby |

## Autenticación

- **Tipo**: API Key o API Secret
- **Parámetro**: `api_key={key}` o `api_secret={secret}` en query/body
- **Obtener clave**: Configuración > Avanzado en el panel de Kit

## Operaciones Comunes del Agente

### Listar suscriptores

```bash
GET https://api.convertkit.com/v3/subscribers?api_secret={api_secret}&page=1

```

### Obtener suscriptor

```bash
GET https://api.convertkit.com/v3/subscribers/{subscriber_id}?api_secret={api_secret}
```

### Agregar suscriptor a un formulario

```bash
POST https://api.convertkit.com/v3/forms/{form_id}/subscribe

{
  "api_key": "{api_key}",
  "email": "user@example.com",
  "first_name": "John",
  "fields": {
    "company": "Example Inc"
  }
}
```

### Agregar suscriptor a una secuencia

```bash
POST https://api.convertkit.com/v3/sequences/{sequence_id}/subscribe

{
  "api_key": "{api_key}",
  "email": "user@example.com"
}
```

### Etiquetar suscriptor

```bash
POST https://api.convertkit.com/v3/tags/{tag_id}/subscribe

{
  "api_key": "{api_key}",
  "email": "user@example.com"
}
```

### Eliminar etiqueta de un suscriptor

```bash
DELETE https://api.convertkit.com/v3/subscribers/{subscriber_id}/tags/{tag_id}?api_secret={api_secret}
```

### Actualizar suscriptor

```bash
PUT https://api.convertkit.com/v3/subscribers/{subscriber_id}

{
  "api_secret": "{api_secret}",
  "first_name": "Jane",
  "fields": {
    "plan": "pro"
  }
}
```

### Dar de baja

```bash
PUT https://api.convertkit.com/v3/unsubscribe

{
  "api_secret": "{api_secret}",
  "email": "user@example.com"
}
```

### Listar formularios

```bash
GET https://api.convertkit.com/v3/forms?api_key={api_key}
```

### Listar secuencias

```bash
GET https://api.convertkit.com/v3/sequences?api_key={api_key}
```

### Listar etiquetas

```bash
GET https://api.convertkit.com/v3/tags?api_key={api_key}
```

### Crear broadcast

```bash
POST https://api.convertkit.com/v3/broadcasts

{
  "api_secret": "{api_secret}",
  "subject": "Newsletter Subject",
  "content": "<p>Email content here</p>",
  "email_layout_template": "default"
}
```

## Conceptos Clave

- **Subscribers** - Contactos de correo electrónico
- **Forms** - Formularios de suscripción
- **Sequences** - Series de correos automatizadas
- **Tags** - Etiquetas de suscriptores
- **Broadcasts** - Envíos únicos
- **Custom Fields** - Atributos de suscriptores

## Estados de Suscriptor

- `active` - Puede recibir correos
- `unsubscribed` - Se dio de baja
- `bounced` - Correo rebotado
- `complained` - Marcó como spam
- `inactive` - Suscriptor inactivo

## Cuándo Usar

- Negocios de creadores y newsletters
- Automatización de correo simple
- Construcción de listas basada en formularios
- Etiquetado y segmentación
- Secuencias de correo para cursos

## Límites de Velocidad

- 120 solicitudes por minuto
- Endpoints de batch disponibles

## Skills Relevantes

- email-sequence
- content-strategy
