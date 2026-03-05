# PostHog

Análisis de productos de código abierto con repetición de sesiones y banderas de características.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Capture API, Query API, Feature Flags API |
| MCP | - | No disponible |
| CLI | ✓ | CLI `posthog` para desarrollo local |
| SDK | ✓ | JavaScript, Python, Ruby, Go, etc. |

## Autenticación

- **Tipo**: API Key (Personal o de Proyecto)
- **Encabezado**: `Authorization: Bearer {api_key}`
- **Para capture**: Project API Key en el payload

## Operaciones Comunes del Agente

### Capturar evento

```bash
POST https://app.posthog.com/capture/

{
  "api_key": "{project_api_key}",
  "event": "signup_completed",
  "distinct_id": "user_123",
  "properties": {
    "plan": "pro",
    "$current_url": "https://example.com/signup"
  }
}
```

### Eventos en lote

```bash
POST https://app.posthog.com/batch/

{
  "api_key": "{project_api_key}",
  "batch": [
    {"event": "pageview", "distinct_id": "user_1"},
    {"event": "signup", "distinct_id": "user_2"}
  ]
}
```

### Obtener persona por distinct_id

```bash
GET https://app.posthog.com/api/projects/{project_id}/persons/?distinct_id=user_123

Authorization: Bearer {api_key}
```

### Consultar eventos (HogQL)

```bash
POST https://app.posthog.com/api/projects/{project_id}/query/

{
  "query": {
    "kind": "HogQLQuery",
    "query": "SELECT event, count() FROM events WHERE timestamp > now() - interval 7 day GROUP BY event ORDER BY count() DESC LIMIT 10"
  }
}
```

### Obtener valor de bandera de característica

```bash
POST https://app.posthog.com/decide?v=3

{
  "api_key": "{project_api_key}",
  "distinct_id": "user_123"
}
```

### Obtener insights

```bash
GET https://app.posthog.com/api/projects/{project_id}/insights/

Authorization: Bearer {api_key}
```

### Obtener grabaciones de sesión

```bash
GET https://app.posthog.com/api/projects/{project_id}/session_recordings/

Authorization: Bearer {api_key}
```

## SDK de JavaScript

```javascript
// Inicializar
posthog.init('PROJECT_API_KEY', {
  api_host: 'https://app.posthog.com'
});

// Identificar usuario
posthog.identify('user_123', {
  email: 'user@example.com',
  plan: 'pro'
});

// Rastrear evento
posthog.capture('signup_completed', {
  method: 'email'
});

// Verificar bandera de característica
if (posthog.isFeatureEnabled('new-pricing')) {
  // Mostrar nuevo precio
}
```

## Características Clave

- **Rastreo de eventos** - Análisis de producto
- **Repetición de sesiones** - Ver sesiones de usuario
- **Banderas de características** - Controlar el despliegue de funciones
- **Pruebas A/B** - Experimentos integrados
- **HogQL** - Lenguaje de consulta similar a SQL
- **Auto-alojable** - Ejecutar en tu propia infraestructura

## Cuándo Usar

- Análisis de producto con enfoque en privacidad
- Repetición de sesiones para obtener información de UX
- Gestión de banderas de características
- Necesidades de análisis auto-alojado
- Requisitos de código abierto

## Límites de Tasa

- Cloud: 10.000 eventos/segundo
- Auto-alojado: Ilimitado

## Skills Relevantes

- analytics-tracking
- ab-test-setup
- onboarding-cro
