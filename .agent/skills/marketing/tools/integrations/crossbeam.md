# Crossbeam

Plataforma de ecosistema de partners (ahora parte de Reveal) para compartir datos de cuentas con partners e identificar oportunidades de co-venta, clientes en común y pipeline originado por partners.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Partners, Populations, Overlaps, Reports, Threads |
| MCP | ✓ | [Claude connector](https://claude.com/connectors/crossbeam) |
| CLI | ✓ | [crossbeam.js](../clis/crossbeam.js) |
| SDK | - | Solo REST API |

## Autenticación

- **Tipo**: API Key
- **Header**: `Authorization: Bearer {api_key}`
- **Obtener clave**: Settings > API en https://app.crossbeam.com

## Operaciones Comunes del Agente

### Listar Partners

```bash
GET https://api.crossbeam.com/v1/partners
Authorization: Bearer {api_key}
```

### Obtener Detalles de un Partner

```bash
GET https://api.crossbeam.com/v1/partners/{id}
Authorization: Bearer {api_key}
```

### Listar Populations

```bash
GET https://api.crossbeam.com/v1/populations
Authorization: Bearer {api_key}
```

### Listar Overlaps

```bash
GET https://api.crossbeam.com/v1/overlaps?partner_id={partner_id}&population_id={population_id}
Authorization: Bearer {api_key}
```

### Obtener Detalles de un Overlap

```bash
GET https://api.crossbeam.com/v1/overlaps/{id}
Authorization: Bearer {api_key}
```

### Buscar Cuentas

```bash
GET https://api.crossbeam.com/v1/accounts/search?domain={domain}
Authorization: Bearer {api_key}
```

### Listar Reports

```bash
GET https://api.crossbeam.com/v1/reports
Authorization: Bearer {api_key}
```

### Listar Hilos de Colaboración

```bash
GET https://api.crossbeam.com/v1/threads
Authorization: Bearer {api_key}
```

## Métricas Clave

### Datos de Partner
- `id` - ID del partner
- `name` - Nombre de la empresa partner
- `status` - Estado de la asociación (active, pending, etc.)
- `created_at` - Fecha en que se estableció la asociación
- `populations_shared` - Número de populations compartidas

### Datos de Population
- `id` - ID de la population
- `name` - Nombre de la population (p. ej., "Customers", "Open Opportunities")
- `record_count` - Número de registros en la population
- `partner_visibility` - Lo que los partners pueden ver

### Datos de Overlap
- `id` - ID del overlap
- `partner_id` - Partner involucrado
- `population_id` - Population coincidente
- `account_name` - Nombre de la cuenta en común
- `overlap_type` - Tipo de overlap (customer, prospect, etc.)
- `match_confidence` - Puntuación de confianza de coincidencia

### Datos de Report
- `id` - ID del report
- `name` - Nombre del report
- `type` - Tipo de report
- `created_at` - Fecha de creación
- `results` - Datos de resultados del report

## Parámetros

### Lista de Overlaps
- `partner_id` - Filtrar por partner específico
- `population_id` - Filtrar por population específica

### Búsqueda de Cuentas
- `domain` - Dominio de la empresa a buscar

## Cuándo Usar

- Identificar oportunidades de co-venta con partners de canal
- Encontrar clientes y prospectos en común a través de los ecosistemas de partners
- Construir pipeline originado por partners mediante la coincidencia de cuentas
- Rastrear la influencia de partners en los negocios
- Crear informes de mapeo de cuentas para reuniones con partners
- Priorizar con qué partners interactuar basándose en los datos de overlap

## Límites de Tasa

- Los límites de tasa varían según el plan
- Standard: 100 solicitudes/minuto
- Paginación disponible en los endpoints de listado

## Skills Relacionadas

- revops
- sales-enablement
- referral-program
- competitor-alternatives
