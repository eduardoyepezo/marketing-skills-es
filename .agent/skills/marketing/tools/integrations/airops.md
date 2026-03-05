# AirOps

Plataforma de contenido con IA para crear contenido que triunfe en la búsqueda de IA. Construye y ejecuta flujos de trabajo con IA (flows) para generación de contenido SEO, enriquecimiento de datos y automatización.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Flows, Workflows, Runs |
| MCP | - | No disponible |
| CLI | ✓ | [airops.js](../clis/airops.js) |
| SDK | - | Solo REST API |

## Autenticación

- **Tipo**: API Key + Workspace ID
- **Header**: `Authorization: Bearer {api_key}`
- **Variables de entorno**: `AIROPS_API_KEY`, `AIROPS_WORKSPACE_ID`
- **Obtener clave**: Settings > API Keys en https://app.airops.com

## Operaciones Comunes del Agente

### Listar Flows

```bash
GET https://api.airops.com/public_api/v1/workspaces/{workspace_id}/flows
```

### Obtener detalles de un Flow

```bash
GET https://api.airops.com/public_api/v1/workspaces/{workspace_id}/flows/{flow_id}
```

### Ejecutar un Flow

```bash
POST https://api.airops.com/public_api/v1/workspaces/{workspace_id}/flows/{flow_id}/execute

{
  "inputs": {
    "keyword": "best project management tools",
    "target_audience": "startup founders"
  }
}
```

### Listar Runs de un Flow

```bash
GET https://api.airops.com/public_api/v1/workspaces/{workspace_id}/flows/{flow_id}/runs
```

### Obtener estado de un Run

```bash
GET https://api.airops.com/public_api/v1/workspaces/{workspace_id}/runs/{run_id}
```

### Listar Workflows

```bash
GET https://api.airops.com/public_api/v1/workspaces/{workspace_id}/workflows
```

### Ejecutar un Workflow

```bash
POST https://api.airops.com/public_api/v1/workspaces/{workspace_id}/workflows/{workflow_id}/execute

{
  "inputs": {
    "topic": "email marketing best practices",
    "content_type": "blog_post"
  }
}
```

## Métricas Clave

### Datos de Flow
- `id` - Identificador del flow
- `name` - Nombre del flow
- `description` - Descripción del flow
- `status` - Estado activo/inactivo
- `created_at` - Marca de tiempo de creación
- `updated_at` - Marca de tiempo de última modificación

### Datos de Run
- `id` - Identificador del run
- `flow_id` - ID del flow padre
- `status` - pending, running, completed, failed
- `inputs` - Parámetros de entrada utilizados
- `outputs` - Resultados generados
- `started_at` - Hora de inicio del run
- `completed_at` - Hora de finalización del run

## Parámetros

### Ejecución de Flow
- `inputs` - Objeto JSON de pares clave-valor que coinciden con las entradas esperadas del flow
- Las claves de entrada varían por flow (p. ej., `keyword`, `topic`, `url`, `target_audience`)

### Ejecución de Workflow
- `inputs` - Objeto JSON de pares clave-valor que coinciden con las entradas esperadas del workflow

## Cuándo Usar

- Generación masiva de contenido para SEO a escala
- Creación de artículos optimizados para SEO con flujos de trabajo de IA
- Pipelines de enriquecimiento de datos para listas de marketing
- Automatización de investigación de palabras clave
- Optimización y reescritura de contenido
- Generación programática de páginas SEO
- Briefs y esquemas de contenido impulsados por IA

## Límites de Velocidad

- Los límites de velocidad varían según el plan
- Los límites de ejecución concurrente dependen del nivel del workspace
- Consultar el panel de AirOps para uso y límites actuales

## Skills Relevantes

- ai-seo
- content-strategy
- programmatic-seo
- copywriting
