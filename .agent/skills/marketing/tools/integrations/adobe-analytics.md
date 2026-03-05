# Adobe Analytics

Plataforma de analítica empresarial para medición y atribución multicanal.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Reporting API 2.0, Data Insertion API |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | ✓ | AppMeasurement.js, Mobile SDKs, Launch |

## Autenticación

- **Tipo**: OAuth 2.0 (Service Account JWT)
- **Configuración**: Crear integración en Adobe Developer Console
- **Header**: `Authorization: Bearer {access_token}`

## Operaciones Comunes del Agente

### Obtener información del report suite

```bash
GET https://analytics.adobe.io/api/{company_id}/reportsuites

Authorization: Bearer {access_token}
x-api-key: {client_id}
```

### Obtener dimensiones

```bash
GET https://analytics.adobe.io/api/{company_id}/dimensions?rsid={report_suite_id}

Authorization: Bearer {access_token}
x-api-key: {client_id}
```

### Obtener métricas

```bash
GET https://analytics.adobe.io/api/{company_id}/metrics?rsid={report_suite_id}

Authorization: Bearer {access_token}
x-api-key: {client_id}
```

### Ejecutar reporte

```bash
POST https://analytics.adobe.io/api/{company_id}/reports

{
  "rsid": "{report_suite_id}",
  "globalFilters": [{
    "type": "dateRange",
    "dateRange": "2024-01-01T00:00:00/2024-01-31T23:59:59"
  }],
  "metricContainer": {
    "metrics": [
      {"id": "metrics/visits"},
      {"id": "metrics/pageviews"},
      {"id": "metrics/orders"}
    ]
  },
  "dimension": "variables/evar1"
}
```

### Obtener segmentos

```bash
GET https://analytics.adobe.io/api/{company_id}/segments?rsid={report_suite_id}

Authorization: Bearer {access_token}
x-api-key: {client_id}
```

### Inserción de datos (lado del servidor)

```bash
POST https://{tracking_server}/b/ss/{report_suite_id}/0

<?xml version="1.0" encoding="UTF-8"?>
<request>
  <visitorID>user_123</visitorID>
  <events>event1</events>
  <eVar1>campaign_name</eVar1>
  <prop1>page_type</prop1>
</request>
```

## AppMeasurement.js

```javascript
// Inicializar
var s = s_gi('report_suite_id');
s.trackingServer = 'metrics.example.com';

// Establecer variables
s.pageName = 'Home Page';
s.channel = 'Marketing';
s.eVar1 = 'campaign_name';
s.events = 'event1';

// Registrar vista de página
s.t();

// Registrar enlace
s.tl(this, 'o', 'Button Click');
```

## Conceptos Clave

- **Report Suite** - Contenedor de datos
- **eVars** - Variables de conversión (persistentes)
- **props** - Variables de tráfico (a nivel de hit)
- **Events** - Métricas de éxito
- **Segments** - Filtros de usuario/visita
- **Calculated Metrics** - Métricas derivadas

## Dimensiones Comunes

- `variables/page` - Nombre de página
- `variables/evar1` - Variable de conversión personalizada
- `variables/prop1` - Variable de tráfico personalizada
- `variables/marketingchannel` - Canal de marketing
- `variables/referringdomain` - Dominio de referencia

## Métricas Comunes

- `metrics/visits` - Visitas
- `metrics/pageviews` - Vistas de página
- `metrics/uniquevisitors` - Visitantes únicos
- `metrics/orders` - Pedidos
- `metrics/revenue` - Ingresos

## Cuándo Usar

- Analítica a escala empresarial
- Atribución multicanal
- Integración con Adobe Experience Cloud
- Segmentación avanzada
- Exportaciones de data warehouse

## Límites de Velocidad

- 12 solicitudes/segundo por empresa
- 120 solicitudes/minuto

## Skills Relevantes

- analytics-tracking
- ab-test-setup
- paid-ads
