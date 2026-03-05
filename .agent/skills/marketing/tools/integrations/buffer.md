# Buffer

Plataforma de programación, publicación y analítica de redes sociales para gestionar múltiples perfiles sociales.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API v1 para perfiles, actualizaciones y programación |
| MCP | - | No disponible |
| CLI | ✓ | [buffer.js](../clis/buffer.js) |
| SDK | - | Sin SDK oficial; la API heredada sigue siendo compatible |

## Autenticación

- **Tipo**: OAuth 2.0 Bearer Token
- **Header**: `Authorization: Bearer {access_token}`
- **Obtener clave**: Registra tu app en https://buffer.com/developers/apps y completa el flujo OAuth
- **Nota**: Buffer ya no acepta nuevos registros de apps de desarrollador; las apps existentes siguen funcionando. La nueva API pública está en desarrollo en https://buffer.com/developer-api

## Operaciones Comunes del Agente

### Obtener información del usuario

```bash
GET https://api.bufferapp.com/1/user.json

Authorization: Bearer {token}
```

### Listar perfiles conectados

```bash
GET https://api.bufferapp.com/1/profiles.json

Authorization: Bearer {token}
```

### Obtener programaciones de publicación de un perfil

```bash
GET https://api.bufferapp.com/1/profiles/{profile_id}/schedules.json
```

### Crear una publicación programada

```bash
POST https://api.bufferapp.com/1/updates/create.json
Content-Type: application/x-www-form-urlencoded

profile_ids[]={profile_id}&text=Your+post+content&scheduled_at=2026-03-01T10:00:00Z
```

### Obtener actualizaciones pendientes de un perfil

```bash
GET https://api.bufferapp.com/1/profiles/{profile_id}/updates/pending.json?count=25
```

### Obtener actualizaciones enviadas de un perfil

```bash
GET https://api.bufferapp.com/1/profiles/{profile_id}/updates/sent.json?count=25
```

### Publicar una actualización pendiente de inmediato

```bash
POST https://api.bufferapp.com/1/updates/{update_id}/share.json
```

### Eliminar una actualización

```bash
POST https://api.bufferapp.com/1/updates/{update_id}/destroy.json
```

### Reordenar la cola

```bash
POST https://api.bufferapp.com/1/profiles/{profile_id}/updates/reorder.json
Content-Type: application/x-www-form-urlencoded

order[]={update_id_1}&order[]={update_id_2}&order[]={update_id_3}
```

## Patrón de API

La API Buffer v1 usa extensiones `.json` en todos los endpoints. Las solicitudes POST usan el tipo de contenido `application/x-www-form-urlencoded`. Los parámetros de tipo array usan notación de corchetes (p. ej., `profile_ids[]`).

Las respuestas incluyen un booleano `success` para operaciones de mutación.

## Métricas Clave

### Métricas de Perfil
- `followers` - Número de seguidores del perfil conectado
- `service` - Nombre de la plataforma (twitter, facebook, instagram, linkedin, etc.)

### Métricas de Actualización (actualizaciones enviadas)
- `statistics.reach` - Alcance de la publicación
- `statistics.clicks` - Clics en enlaces
- `statistics.retweets` - Retweets/compartidos
- `statistics.favorites` - Me gusta/favoritos
- `statistics.mentions` - Menciones

## Parámetros

### Parámetros de Creación de Actualización
- `profile_ids[]` - Requerido. Array de IDs de perfiles donde publicar
- `text` - Requerido. Contenido de la publicación
- `scheduled_at` - Timestamp ISO 8601 para programación
- `now` - Establecer en `true` para publicar de inmediato
- `top` - Establecer en `true` para añadir al inicio de la cola
- `shorten` - Establecer en `true` para acortar enlaces automáticamente
- `media[photo]` - URL del archivo adjunto de foto
- `media[thumbnail]` - URL de la miniatura
- `media[link]` - URL del enlace adjunto

## Cuándo Usar

- Programar publicaciones en redes sociales en múltiples plataformas
- Gestionar colas de contenido en redes sociales
- Analizar el rendimiento de publicaciones en distintos canales
- Automatizar flujos de trabajo de publicación en redes sociales
- Coordinar la actividad del equipo en redes sociales

## Límites de Tasa

- 60 solicitudes autenticadas por usuario por minuto
- Superarlos devuelve HTTP 429
- Límites más altos disponibles contactando a hello@buffer.com

## Skills Relacionadas

- social-media-calendar
- content-repurposing
- social-proof
- launch-sequence
