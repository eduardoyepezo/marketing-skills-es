# Google Analytics 4 (GA4)

Plataforma de analítica web para rastrear el comportamiento de usuarios, conversiones y rendimiento de marketing.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Data API para reportes, Admin API para configuración |
| MCP | ✓ | Disponible mediante el servidor MCP de Google Analytics |
| CLI | - | Usar gcloud para algunas operaciones |
| SDK | ✓ | gtag.js, Google Analytics SDK para móvil |

## Autenticación

- **Tipo**: OAuth 2.0 o Service Account
- **Scopes**: `https://www.googleapis.com/auth/analytics.readonly` (lectura), `https://www.googleapis.com/auth/analytics.edit` (escritura)
- **Configuración**: Crear credenciales en Google Cloud Console

## Operaciones Comunes del Agente

### Ejecutar un reporte (Data API)

```bash
POST https://analyticsdata.googleapis.com/v1beta/properties/{property_id}:runReport

{
  "dateRanges": [{"startDate": "30daysAgo", "endDate": "today"}],
  "dimensions": [{"name": "sessionSource"}],
  "metrics": [{"name": "sessions"}, {"name": "conversions"}]
}
```

### Obtener datos en tiempo real

```bash
POST https://analyticsdata.googleapis.com/v1beta/properties/{property_id}:runRealtimeReport

{
  "dimensions": [{"name": "country"}],
  "metrics": [{"name": "activeUsers"}]
}
```

### Listar eventos de conversión

```bash
GET https://analyticsadmin.googleapis.com/v1beta/properties/{property_id}/conversionEvents
```

### Crear un evento de conversión

```bash
POST https://analyticsadmin.googleapis.com/v1beta/properties/{property_id}/conversionEvents

{
  "eventName": "purchase"
}
```

## Seguimiento del Lado del Cliente

### Enviar evento personalizado (gtag.js)

```javascript
gtag('event', 'signup_completed', {
  'method': 'email',
  'plan': 'free'
});
```

### Enviar evento mediante Measurement Protocol

```bash
POST https://www.google-analytics.com/mp/collect?measurement_id={measurement_id}&api_secret={api_secret}

{
  "client_id": "client_123",
  "events": [{
    "name": "purchase",
    "params": {
      "value": 99.99,
      "currency": "USD"
    }
  }]
}
```

## Dimensiones y Métricas Clave

### Dimensiones Comunes
- `sessionSource` - Fuente de tráfico
- `sessionMedium` - Medio de tráfico
- `sessionCampaignName` - Nombre de campaña
- `landingPage` - Página de entrada
- `deviceCategory` - Tipo de dispositivo
- `country` - País del usuario

### Métricas Comunes
- `sessions` - Total de sesiones
- `activeUsers` - Usuarios activos
- `newUsers` - Nuevos usuarios
- `conversions` - Eventos de conversión
- `engagementRate` - Tasa de sesiones comprometidas
- `averageSessionDuration` - Duración de la sesión

## Cuándo Usar

- Rastrear el tráfico del sitio web y el comportamiento de los usuarios
- Medir el rendimiento de campañas de marketing
- Configurar el seguimiento de conversiones
- Analizar los recorridos de los usuarios y embudos
- Modelado de atribución

## Límites de Velocidad

- Data API: 10 solicitudes por segundo por propiedad
- Admin API: Varía según el endpoint
- Measurement Protocol: 1M hits/día para el nivel gratuito

## Skills Relacionadas

- analytics-tracking
- ab-test-setup
- seo-audit
- page-cro
