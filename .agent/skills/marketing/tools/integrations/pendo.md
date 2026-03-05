# Pendo

Plataforma de análisis de productos y guía dentro de la aplicación para rastrear el comportamiento de los usuarios, medir la adopción de funciones y entregar mensajes dirigidos dentro de la aplicación.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Features, Pages, Guides, Visitors, Accounts, Reports, Metadata |
| MCP | - | No disponible |
| CLI | ✓ | [pendo.js](../clis/pendo.js) |
| SDK | - | Solo REST API |

## Autenticación

- **Tipo**: Integration Key
- **Encabezado**: `x-pendo-integration-key: {key}`
- **Obtener clave**: Settings > Integrations en https://app.pendo.io

## Operaciones Comunes del Agente

### Listar Funciones

```bash
GET https://app.pendo.io/api/v1/feature
```

### Obtener Detalles de una Función

```bash
GET https://app.pendo.io/api/v1/feature/{featureId}
```

### Listar Páginas

```bash
GET https://app.pendo.io/api/v1/page
```

### Obtener Detalles de una Página

```bash
GET https://app.pendo.io/api/v1/page/{pageId}
```

### Listar Guías

```bash
GET https://app.pendo.io/api/v1/guide?state=public
```

### Obtener Detalles de una Guía

```bash
GET https://app.pendo.io/api/v1/guide/{guideId}
```

### Obtener Datos de un Visitante

```bash
GET https://app.pendo.io/api/v1/visitor/{visitorId}
```

### Buscar Visitantes

```bash
POST https://app.pendo.io/api/v1/aggregation

{
  "response": { "mimeType": "application/json" },
  "request": {
    "pipeline": [
      { "source": { "visitors": null } },
      { "filter": "lastVisitedAt > 1700000000000" }
    ]
  }
}
```

### Obtener Datos de una Cuenta

```bash
GET https://app.pendo.io/api/v1/account/{accountId}
```

### Buscar Cuentas

```bash
POST https://app.pendo.io/api/v1/aggregation

{
  "response": { "mimeType": "application/json" },
  "request": {
    "pipeline": [
      { "source": { "accounts": null } },
      { "filter": "metadata.auto.lastupdated > 1700000000000" }
    ]
  }
}
```

### Ejecutar un Informe de Embudo

```bash
POST https://app.pendo.io/api/v1/aggregation

{
  "response": { "mimeType": "application/json" },
  "request": {
    "pipeline": [
      { "source": { "visitors": null, "timeSeries": { "period": "dayRange", "first": 1700000000000, "last": 1700600000000 } } },
      { "identified": "visitorId" },
      { "filter": "pageId == \"page-id-1\"" },
      { "filter": "pageId == \"page-id-2\"" }
    ]
  }
}
```

### Listar Campos de Metadatos

```bash
GET https://app.pendo.io/api/v1/metadata/schema/visitor
GET https://app.pendo.io/api/v1/metadata/schema/account
GET https://app.pendo.io/api/v1/metadata/schema/parentAccount
```

## Métricas Clave

### Datos de Funciones
- `id` - ID de la función
- `name` - Nombre de la función
- `kind` - Tipo de función
- `elementPath` - Selector CSS del elemento rastreado
- `pageId` - ID de página asociada
- `numEvents` - Cantidad de eventos
- `numVisitors` - Cantidad de visitantes únicos

### Datos de Páginas
- `id` - ID de la página
- `name` - Nombre de la página
- `rules` - Reglas de coincidencia de URL
- `numEvents` - Cantidad de vistas de página
- `numVisitors` - Cantidad de visitantes únicos

### Datos de Guías
- `id` - ID de la guía
- `name` - Nombre de la guía
- `state` - Estado de la guía (draft, staged, public, disabled)
- `launchMethod` - Cómo se activa la guía
- `steps` - Definiciones de pasos de la guía
- `numSteps` - Número de pasos
- `numViews` - Total de vistas
- `numVisitors` - Visitantes únicos que vieron la guía

### Datos de Visitantes
- `visitorId` - Identificador único del visitante
- `lastVisitedAt` - Marca de tiempo de la última visita
- `firstVisit` - Marca de tiempo de la primera visita
- `numEvents` - Cantidad total de eventos
- `metadata` - Metadatos personalizados del visitante

### Datos de Cuentas
- `accountId` - Identificador único de la cuenta
- `lastVisitedAt` - Última visita de cualquier miembro de la cuenta
- `numVisitors` - Número de visitantes en la cuenta
- `metadata` - Metadatos personalizados de la cuenta

## Parámetros

### Filtrado de Guías
- `state` - Filtrar por estado: draft, staged, public, disabled

### Consultas de Agregación
- `source` - Fuente de datos: visitors, accounts, features, pages, guides
- `filter` - Filtrado basado en expresiones
- `sort` - Ordenar resultados
- `limit` - Máximo de resultados a devolver
- `timeSeries` - Rango de tiempo con period, first, last

### Tipos de Metadatos
- `visitor` - Esquema de metadatos de visitante
- `account` - Esquema de metadatos de cuenta
- `parentAccount` - Esquema de metadatos de cuenta principal

## Cuándo Usar

- Rastrear la adopción y los patrones de uso de funciones
- Crear y gestionar guías de incorporación dentro de la aplicación
- Analizar el comportamiento del usuario en páginas y funciones
- Segmentar usuarios por nivel de participación
- Ejecutar análisis de embudo en los recorridos de usuario
- Identificar cuentas en riesgo basándose en la disminución de uso
- Pruebas A/B de mensajes y tooltips dentro de la aplicación

## Límites de Tasa

- Los límites de tasa varían según el plan
- Estándar: 500 solicitudes por minuto
- Las consultas de agregación pueden tardar más para conjuntos de datos grandes
- Usar paginación para conjuntos de resultados grandes

## Skills Relevantes

- analytics-tracking
- onboarding-cro
- churn-prevention
- ab-test-setup
