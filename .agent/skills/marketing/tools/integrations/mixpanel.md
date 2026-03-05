# Mixpanel

Plataforma de analíticas de producto para rastrear el comportamiento y la retención de usuarios.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Ingestion API, Query API, Data Export |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | ✓ | JavaScript, iOS, Android, Python, etc. |

## Autenticación

- **Ingestion**: Token de proyecto (público)
- **Query API**: Service Account (username:secret como Basic auth)
- **Export**: API Secret

## Operaciones Comunes del Agente

### Rastrear evento (Ingestion API)

```bash
POST https://api.mixpanel.com/track

{
  "event": "signup_completed",
  "properties": {
    "token": "{project_token}",
    "distinct_id": "user_123",
    "plan": "pro",
    "time": 1705312800
  }
}
```

### Establecer perfil de usuario

```bash
POST https://api.mixpanel.com/engage

{
  "$token": "{project_token}",
  "$distinct_id": "user_123",
  "$set": {
    "$email": "user@example.com",
    "$name": "John Doe",
    "plan": "pro"
  }
}
```

### Consultar eventos (Query API)

```bash
POST https://mixpanel.com/api/2.0/insights

{
  "project_id": {project_id},
  "bookmark_id": null,
  "params": {
    "events": [{"event": "signup_completed"}],
    "time_range": {
      "from_date": "2024-01-01",
      "to_date": "2024-01-31"
    }
  }
}
```

### Obtener datos de embudo

```bash
GET https://mixpanel.com/api/2.0/funnels?funnel_id={funnel_id}&from_date=2024-01-01&to_date=2024-01-31
```

### Exportar eventos en bruto

```bash
GET https://data.mixpanel.com/api/2.0/export?from_date=2024-01-01&to_date=2024-01-01
```

### Obtener datos de retención

```bash
GET https://mixpanel.com/api/2.0/retention?from_date=2024-01-01&to_date=2024-01-31&retention_type=birth&born_event=signup_completed
```

## JavaScript SDK

```javascript
// Inicializar
mixpanel.init('YOUR_TOKEN');

// Identificar usuario
mixpanel.identify('user_123');

// Establecer propiedades de usuario
mixpanel.people.set({
  '$email': 'user@example.com',
  'plan': 'pro'
});

// Rastrear evento
mixpanel.track('Feature Used', {
  'feature_name': 'export'
});
```

## Conceptos Clave

- **Events** - Acciones del usuario (signup, purchase, etc.)
- **Properties** - Atributos de los eventos
- **User Profiles** - Datos persistentes del usuario
- **Cohorts** - Segmentos de usuarios guardados
- **Funnels** - Secuencias de conversión
- **Retention** - Patrones de regreso del usuario

## Cuándo Usar

- Rastrear eventos de uso del producto
- Analizar embudos de conversión
- Medir la adopción de funcionalidades
- Análisis de retención
- Segmentación de usuarios

## Límites de Uso

- Ingestion: Sin límite estricto (se recomienda batch)
- Query API: Varía según el plan

## Skills Relacionados

- analytics-tracking
- ab-test-setup
- onboarding-cro
