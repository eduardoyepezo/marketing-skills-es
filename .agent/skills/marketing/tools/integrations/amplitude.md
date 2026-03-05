# Amplitude

Plataforma de analítica de producto para comportamiento de usuarios, retención y experimentación.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | HTTP API para eventos, User Profile API, Export API |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | ✓ | JavaScript, iOS, Android, Python, etc. |

## Autenticación

- **HTTP API**: API Key (pública para eventos)
- **Export/Dashboard API**: API Key + Secret Key

## Operaciones Comunes del Agente

### Registrar evento

```bash
POST https://api2.amplitude.com/2/httpapi

{
  "api_key": "{api_key}",
  "events": [{
    "user_id": "user_123",
    "event_type": "signup_completed",
    "event_properties": {
      "plan": "pro"
    },
    "user_properties": {
      "email": "user@example.com"
    }
  }]
}
```

### Eventos en lote

```bash
POST https://api2.amplitude.com/batch

{
  "api_key": "{api_key}",
  "events": [
    {"user_id": "user_1", "event_type": "pageview"},
    {"user_id": "user_2", "event_type": "signup"}
  ]
}
```

### Obtener actividad de usuario

```bash
GET https://amplitude.com/api/2/useractivity?user={user_id}

Authorization: Basic {base64(api_key:secret_key)}
```

### Exportar eventos

```bash
GET https://amplitude.com/api/2/export?start=20240101T00&end=20240131T23

Authorization: Basic {base64(api_key:secret_key)}
```

### Obtener datos de retención

```bash
GET https://amplitude.com/api/2/retention?e={"event_type":"signup_completed"}&start=20240101&end=20240131

Authorization: Basic {base64(api_key:secret_key)}
```

### Consulta con SQL (Snowflake)

Para clientes de Amplitude con acceso SQL:
```sql
SELECT event_type, COUNT(*) as count
FROM events
WHERE event_time > '2024-01-01'
GROUP BY event_type
```

## JavaScript SDK

```javascript
// Inicializar
amplitude.init('API_KEY');

// Identificar usuario
amplitude.setUserId('user_123');

// Establecer propiedades de usuario
const identify = new amplitude.Identify();
identify.set('plan', 'pro');
amplitude.identify(identify);

// Registrar evento
amplitude.track('Feature Used', {
  feature_name: 'export'
});
```

## Conceptos Clave

- **Events** - Acciones de usuario con propiedades
- **User Properties** - Atributos persistentes del usuario
- **Cohorts** - Segmentos de comportamiento
- **Funnels** - Análisis de conversión en múltiples pasos
- **Retention** - Patrones de retorno de usuarios
- **Journeys** - Análisis del recorrido del usuario

## Cuándo Usar

- Seguimiento de analítica de producto
- Análisis de embudos de usuario
- Análisis de cohortes y retención
- Experimentación y pruebas A/B
- Mapeo del recorrido del usuario

## Límites de Velocidad

- HTTP API: 1000 eventos/segundo
- Export API: 360 solicitudes/hora

## Skills Relevantes

- analytics-tracking
- ab-test-setup
- onboarding-cro
