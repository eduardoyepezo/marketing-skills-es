# Hotjar

Plataforma de análisis de comportamiento con mapas de calor, grabaciones de sesiones y encuestas para comprender la experiencia del usuario.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Surveys, Responses, Sites, Heatmaps, Recordings |
| MCP | - | No disponible |
| CLI | ✓ | [hotjar.js](../clis/hotjar.js) |
| SDK | ✓ | Fragmento de seguimiento JavaScript, Identify API, Events API |

## Autenticación

- **Tipo**: OAuth 2.0 Client Credentials
- **Endpoint del token**: `POST https://api.hotjar.io/v1/oauth/token`
- **Header**: `Authorization: Bearer {access_token}`
- **Obtener credenciales**: Panel de Hotjar > Integrations > API
- **Expiración del token**: 3600 segundos (1 hora)

### Solicitud de Token

```bash
POST https://api.hotjar.io/v1/oauth/token
Content-Type: application/x-www-form-urlencoded

grant_type=client_credentials&client_id={client_id}&client_secret={client_secret}
```

### Respuesta del Token

```json
{
  "access_token": "<token>",
  "token_type": "Bearer",
  "expires_in": 3600
}
```

## Operaciones Comunes del Agente

### Listar Sitios

```bash
GET https://api.hotjar.io/v1/sites

Authorization: Bearer {access_token}
```

### Listar Encuestas

```bash
GET https://api.hotjar.io/v1/sites/{site_id}/surveys

Authorization: Bearer {access_token}
```

### Obtener Respuestas de Encuesta

```bash
GET https://api.hotjar.io/v1/sites/{site_id}/surveys/{survey_id}/responses?limit=100

Authorization: Bearer {access_token}
```

Admite paginación basada en cursor con los parámetros `cursor` y `limit`.

### Listar Mapas de Calor

```bash
GET https://api.hotjar.io/v1/sites/{site_id}/heatmaps

Authorization: Bearer {access_token}
```

### Listar Grabaciones

```bash
GET https://api.hotjar.io/v1/sites/{site_id}/recordings

Authorization: Bearer {access_token}
```

### Listar Formularios

```bash
GET https://api.hotjar.io/v1/sites/{site_id}/forms

Authorization: Bearer {access_token}
```

## Métricas Clave

### Datos de Respuestas de Encuesta
- `response_id` - Identificador único de respuesta
- `answers` - Array de pares pregunta/respuesta
- `created_at` - Marca de tiempo de la respuesta
- `device_type` - Desktop, mobile, tablet

### Datos de Mapas de Calor
- `url` - URL de la página
- `click_count` - Total de clics registrados
- `visitors` - Visitantes únicos
- `created_at` - Fecha de creación del mapa de calor

### Datos de Grabaciones
- `recording_id` - ID único de la grabación
- `duration` - Duración de la sesión
- `pages_visited` - Páginas en la sesión
- `device` - Información del dispositivo

## Parámetros

### Respuestas de Encuesta
- `limit` - Resultados por página (por defecto: 100)
- `cursor` - Cursor de paginación de la respuesta anterior
- `sort` - Orden de clasificación (por defecto: created_at desc)

### Grabaciones
- `limit` - Resultados por página
- `cursor` - Cursor de paginación
- `date_from` - Filtro de fecha de inicio
- `date_to` - Filtro de fecha de fin

## Cuándo Usar

- Analizar patrones de comportamiento de usuarios en páginas de destino
- Recopilar retroalimentación cualitativa mediante encuestas en el sitio
- Identificar problemas de UX a través de grabaciones de sesiones
- Comprender la profundidad de desplazamiento y el engagement mediante mapas de calor
- Validar hipótesis de CRO con datos de comportamiento del usuario
- Análisis de abandono de formularios

## Límites de Velocidad

- 3000 solicitudes/minuto (50 por segundo)
- Límite de velocidad por dirección IP de origen
- Paginación basada en cursor para conjuntos de resultados grandes

## Skills Relacionadas

- page-cro
- ab-test-setup
- analytics-tracking
- ux-audit
- landing-page
