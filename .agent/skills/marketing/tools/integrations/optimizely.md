# Optimizely

Plataforma de pruebas A/B y experimentación con una REST API para gestionar proyectos, experimentos, campañas y resultados.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Projects, Experiments, Campaigns, Audiences, Results |
| MCP | - | No disponible |
| CLI | ✓ | [optimizely.js](../clis/optimizely.js) |
| SDK | ✓ | JavaScript, Python, Ruby, Java, Go, C#, PHP, React, Swift, Android |

## Autenticación

- **Tipo**: Bearer Token (Personal Access Token u OAuth 2.0)
- **Header**: `Authorization: Bearer {personal_token}`
- **Obtener token**: https://app.optimizely.com/v2/profile/api > Generate New Token

## Operaciones Comunes del Agente

### Listar Proyectos

```bash
GET https://api.optimizely.com/v2/projects
```

### Obtener Proyecto

```bash
GET https://api.optimizely.com/v2/projects/{project_id}
```

### Listar Experimentos

```bash
GET https://api.optimizely.com/v2/experiments?project_id={project_id}
```

### Obtener Experimento

```bash
GET https://api.optimizely.com/v2/experiments/{experiment_id}
```

### Obtener Resultados del Experimento

```bash
GET https://api.optimizely.com/v2/experiments/{experiment_id}/results
```

### Crear Experimento

```bash
POST https://api.optimizely.com/v2/experiments

{
  "project_id": 12345,
  "name": "Homepage CTA Test",
  "type": "a/b",
  "variations": [
    { "name": "Control", "weight": 5000 },
    { "name": "Variation 1", "weight": 5000 }
  ],
  "metrics": [{ "event_id": 67890 }],
  "status": "not_started"
}
```

### Actualizar Experimento

```bash
PATCH https://api.optimizely.com/v2/experiments/{experiment_id}

{
  "status": "running"
}
```

### Listar Campañas

```bash
GET https://api.optimizely.com/v2/campaigns?project_id={project_id}
```

### Obtener Resultados de Campaña

```bash
GET https://api.optimizely.com/v2/campaigns/{campaign_id}/results
```

### Listar Audiencias

```bash
GET https://api.optimizely.com/v2/audiences?project_id={project_id}
```

### Listar Eventos

```bash
GET https://api.optimizely.com/v2/events?project_id={project_id}
```

### Listar Páginas

```bash
GET https://api.optimizely.com/v2/pages?project_id={project_id}
```

## Métricas Clave

### Resultados del Experimento
- `variation_id` - Identificador de la variación
- `variation_name` - Nombre de visualización de la variación
- `visitors` - Visitantes únicos por variación
- `conversions` - Cantidad de conversiones
- `conversion_rate` - Tasa como decimal
- `improvement` - Mejora porcentual respecto al control
- `statistical_significance` - Nivel de confianza
- `is_baseline` - Si es el control

### Propiedades del Experimento
- `name` - Nombre del experimento
- `status` - not_started, running, paused, archived
- `type` - a/b, multivariate, personalization
- `traffic_allocation` - Porcentaje de tráfico (0-10000 = 0-100%)
- `variations` - Array de variaciones con pesos

## Parámetros

### Listar Experimentos
- `project_id` (requerido) - Proyecto del que se listan los experimentos
- `page` - Número de página
- `per_page` - Resultados por página (por defecto: 25)
- `status` - Filtrar por estado

### Obtener Resultados
- `start_time` - Hora de inicio de los resultados (ISO 8601)
- `end_time` - Hora de fin de los resultados (ISO 8601)

### Crear Experimento
- `project_id` (requerido) - Proyecto padre
- `name` (requerido) - Nombre del experimento
- `type` - Tipo de experimento (por defecto: a/b)
- `variations` (requerido) - Array de variaciones con nombre y peso
- `metrics` - Array de configuraciones de métricas/eventos
- `audience_conditions` - Condiciones de segmentación
- `traffic_allocation` - Porcentaje de tráfico (0-10000)

## Cuándo Usar

- Ejecutar pruebas A/B en páginas web y funcionalidades
- Gestionar programas de experimentación a escala
- Extraer resultados de experimentos para análisis
- Automatizar la creación y el monitoreo de experimentos
- Gestión de feature flags
- Campañas de personalización

## Límites de Uso

- 50 solicitudes/segundo por token personal
- Paginación mediante parámetros `page` y `per_page`
- Especificación OpenAPI disponible en https://api.optimizely.com/v2/swagger.json

## Skills Relacionados

- ab-test-setup
- page-cro
- landing-page
- personalization
- analytics-tracking
