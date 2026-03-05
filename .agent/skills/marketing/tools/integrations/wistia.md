# Wistia

Plataforma de alojamiento, gestión y analítica de video creada para especialistas en marketing con seguimiento detallado de engagement.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | Data API (v1/modern), Stats API, Upload API |
| MCP | - | No disponible |
| CLI | ✓ | [wistia.js](../clis/wistia.js) |
| SDK | ✓ | Ruby (oficial), wrappers de la comunidad para otros lenguajes |

## Autenticación

- **Tipo**: Bearer Token
- **Encabezado**: `Authorization: Bearer {api_token}`
- **Obtener clave**: Account Settings > pestaña API en https://account.wistia.com/account/api
- **Nota**: Solo los propietarios de cuenta pueden crear/gestionar tokens. Los tokens solo se pueden copiar cuando se crean por primera vez.

## Operaciones Comunes del Agente

### Listar todos los proyectos

```bash
GET https://api.wistia.com/v1/projects.json?page=1&per_page=25
```

### Crear un proyecto

```bash
POST https://api.wistia.com/v1/projects.json

{
  "name": "Marketing Videos Q1"
}
```

### Listar todos los medios

```bash
GET https://api.wistia.com/v1/medias.json?page=1&per_page=25
```

### Obtener detalles de un medio

```bash
GET https://api.wistia.com/v1/medias/{media_hashed_id}.json
```

### Obtener estadísticas de un medio

```bash
GET https://api.wistia.com/v1/medias/{media_hashed_id}/stats.json
```

### Obtener estadísticas generales de la cuenta

```bash
GET https://api.wistia.com/v1/stats/account.json
```

### Obtener datos de engagement del medio (mapa de calor)

```bash
GET https://api.wistia.com/v1/stats/medias/{media_id}/engagement.json
```

### Obtener estadísticas del medio por fecha

```bash
GET https://api.wistia.com/v1/stats/medias/{media_id}/by_date.json?start_date=2026-01-01&end_date=2026-01-31
```

### Listar visitantes

```bash
GET https://api.wistia.com/v1/stats/visitors.json?page=1&per_page=25
```

### Listar eventos de visualización

```bash
GET https://api.wistia.com/v1/stats/events.json?media_id={media_id}
```

### Actualizar metadatos de un medio

```bash
PUT https://api.wistia.com/v1/medias/{media_hashed_id}.json

{
  "name": "Updated Video Title",
  "description": "New description"
}
```

### Listar subtítulos de un video

```bash
GET https://api.wistia.com/v1/medias/{media_hashed_id}/captions.json
```

## Versiones de la API

Wistia cuenta con dos versiones de API:
- **v1** (`/v1/`) - Legacy, con soporte permanente, sin cambios incompatibles
- **modern** (`/modern/`) - Versión actual, versionado basado en fechas mediante el encabezado `X-Wistia-Api-Version`

El CLI utiliza v1 para máxima estabilidad.

## Métricas Clave

### Estadísticas de medios
- `plays` - Total de reproducciones de video
- `visitors` - Visitantes únicos
- `pageLoads` - Número de cargas de página
- `averagePercentWatched` - Porcentaje promedio visto
- `percentOfVisitorsClickingPlay` - Tasa de clics en reproducción

### Datos de engagement
- Datos de mapa de calor que muestran exactamente dónde los espectadores ven, revisan y abandonan
- Desglose de engagement por segundo

### Estadísticas de la cuenta
- `total_medias` - Total de videos
- `total_plays` - Reproducciones en toda la cuenta
- `total_hours_watched` - Total de horas de video vistas

## Parámetros

### Parámetros de lista de medios
- `page` - Número de página (predeterminado: 1)
- `per_page` - Resultados por página (predeterminado: 25, máximo: 100)
- `project_id` - Filtrar por proyecto
- `name` - Filtrar por nombre
- `type` - Filtrar por tipo (Video, Audio, Image, etc.)

### Parámetros de fecha para estadísticas
- `start_date` - Fecha de inicio (YYYY-MM-DD)
- `end_date` - Fecha de fin (YYYY-MM-DD)

## Cuándo Usar

- Alojar videos de marketing y producto con analítica
- Rastrear engagement de video y comportamiento del espectador
- Pruebas A/B de miniaturas de video y CTAs
- Incrustar videos con marca de reproductor personalizada
- Analizar qué partes de los videos generan engagement
- Generación de leads mediante puertas de correo electrónico en video

## Límites de Tasa

- 600 solicitudes por minuto por cuenta
- Al exceder se devuelve HTTP 429 con encabezado `Retry-After`
- El acceso a activos (descarga de archivos de medios) no cuenta para el límite
- Los datos de eventos solo devuelven registros de los últimos 2 años

## Habilidades Relacionadas

- video-marketing
- content-repurposing
- landing-page-optimization
- lead-generation
