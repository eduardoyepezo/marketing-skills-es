# Trustpilot

Plataforma de gestión de reseñas de negocios para recopilar, gestionar y mostrar opiniones de clientes.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | Business Units, Reseñas, Invitaciones, Etiquetas |
| MCP | - | No disponible |
| CLI | ✓ | [trustpilot.js](../clis/trustpilot.js) |
| SDK | ✓ | Node.js (oficial), wrappers de la comunidad |

## Autenticación

- **Tipo**: API Key (endpoints públicos) + OAuth 2.0 (endpoints privados)
- **Encabezado público**: `apikey: {YOUR_API_KEY}`
- **Encabezado privado**: `Authorization: Bearer {access_token}`
- **Concesión OAuth**: Client Credentials (`Basic base64(API_KEY:API_SECRET)`)
- **Duración del token**: Los access tokens expiran tras 100 horas, los refresh tokens tras 30 días
- **Obtener credenciales**: https://businessapp.b2b.trustpilot.com/ > Integrations > API

## Operaciones Comunes del Agente

### Buscar una unidad de negocio

```bash
GET https://api.trustpilot.com/v1/business-units/search?query=example.com&limit=10

Headers:
  apikey: {API_KEY}
```

### Obtener detalles de una unidad de negocio

```bash
GET https://api.trustpilot.com/v1/business-units/{businessUnitId}

Headers:
  apikey: {API_KEY}
```

### Obtener información del perfil del negocio

```bash
GET https://api.trustpilot.com/v1/business-units/{businessUnitId}/profileinfo

Headers:
  apikey: {API_KEY}
```

### Listar reseñas públicas

```bash
GET https://api.trustpilot.com/v1/business-units/{businessUnitId}/reviews?perPage=20&orderBy=createdat.desc

Headers:
  apikey: {API_KEY}
```

### Listar reseñas privadas (con datos del cliente)

```bash
GET https://api.trustpilot.com/v1/private/business-units/{businessUnitId}/reviews?perPage=20

Headers:
  Authorization: Bearer {access_token}
```

### Responder a una reseña

```bash
POST https://api.trustpilot.com/v1/private/reviews/{reviewId}/reply

Headers:
  Authorization: Bearer {access_token}

{
  "message": "Thank you for your feedback!"
}
```

### Enviar invitación por correo electrónico

```bash
POST https://api.trustpilot.com/v1/private/business-units/{businessUnitId}/email-invitations

Headers:
  Authorization: Bearer {access_token}

{
  "consumerEmail": "customer@example.com",
  "consumerName": "Jane Doe",
  "referenceNumber": "order-123",
  "redirectUri": "https://example.com/thanks"
}
```

### Generar enlace de invitación a reseña

```bash
POST https://api.trustpilot.com/v1/private/business-units/{businessUnitId}/invitation-links

Headers:
  Authorization: Bearer {access_token}

{
  "email": "customer@example.com",
  "name": "Jane Doe",
  "referenceId": "order-123",
  "redirectUri": "https://example.com/thanks"
}
```

### Listar plantillas de invitación

```bash
GET https://api.trustpilot.com/v1/private/business-units/{businessUnitId}/templates

Headers:
  Authorization: Bearer {access_token}
```

### Añadir etiquetas a una reseña

```bash
PUT https://api.trustpilot.com/v1/private/reviews/{reviewId}/tags

Headers:
  Authorization: Bearer {access_token}

{
  "tags": [{ "group": "sentiment", "value": "positive" }]
}
```

## Métricas Clave

### Métricas de la unidad de negocio
- `numberOfReviews` - Número total de reseñas
- `trustScore` - Puntuación de confianza general (1-5)
- `stars` - Calificación de estrellas mostrada
- `status` - Estado de reclamación (claimed, unclaimed)

### Métricas de reseñas
- `stars` - Calificación de estrellas de la reseña individual (1-5)
- `language` - Código de idioma de la reseña
- `createdAt` - Marca de tiempo de creación de la reseña
- `isVerified` - Si la reseña está verificada
- `status` - Estado de la reseña (active, reported, flagged)

## Parámetros

### Filtros de reseñas
- `stars` - Filtrar por calificación de estrellas (1-5)
- `language` - Filtrar por código de idioma (p. ej., `en`)
- `orderBy` - Orden de clasificación (`createdat.desc`, `createdat.asc`, `stars.desc`, `stars.asc`)
- `perPage` - Resultados por página (máximo 100)

### Parámetros de invitación
- `consumerEmail` - Correo del destinatario (requerido)
- `consumerName` - Nombre del destinatario (requerido)
- `referenceNumber` - Referencia del pedido o transacción
- `templateId` - ID de plantilla de correo electrónico
- `redirectUri` - URL de redirección tras enviar la reseña
- `senderEmail` - Correo del remitente personalizado
- `replyTo` - Dirección de respuesta personalizada

## Cuándo Usar

- Recopilar y gestionar reseñas de clientes a escala
- Automatizar flujos de invitación a reseñas tras la compra
- Monitorizar la reputación de marca y el sentimiento de las reseñas
- Responder a comentarios de clientes de forma programática
- Mostrar TrustScore y reseñas en páginas de marketing
- Etiquetar y categorizar reseñas para análisis

## Límites de Tasa

- Recomendado: no más de 833 llamadas cada 5 minutos (10K/hora)
- Limitado a más de 1 solicitud por segundo
- Encabezados de límite de tasa devueltos en las respuestas
- Usar webhooks en lugar de polling siempre que sea posible

## Habilidades Relacionadas

- reputation-management
- customer-feedback
- review-generation
- social-proof
- post-purchase-flow
