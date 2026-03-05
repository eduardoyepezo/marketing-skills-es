# Clearbit (HubSpot Breeze Intelligence)

API de enriquecimiento de datos de empresas y personas para convertir leads con más de 100 atributos firmográficos y tecnográficos.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Person, Company, Combined Enrichment, Reveal, Name to Domain, Prospector |
| MCP | - | No disponible |
| CLI | ✓ | [clearbit.js](../clis/clearbit.js) |
| SDK | ✓ | Node, Ruby, Python, PHP |

## Autenticación

- **Tipo**: Bearer Token (o Basic Auth con API key como nombre de usuario)
- **Header**: `Authorization: Bearer {api_key}`
- **Obtener clave**: https://dashboard.clearbit.com/api

## Operaciones Comunes del Agente

### Enriquecimiento de Persona (por correo electrónico)

```bash
GET https://person.clearbit.com/v2/people/find?email=alex@clearbit.com
```

Devuelve más de 100 atributos: nombre, cargo, empresa, ubicación, perfiles sociales, historial laboral.

### Enriquecimiento de Empresa (por dominio)

```bash
GET https://company.clearbit.com/v2/companies/find?domain=clearbit.com
```

Devuelve datos firmográficos: industria, tamaño, ingresos, stack tecnológico, ubicación, financiamiento.

### Enriquecimiento Combinado (persona + empresa)

```bash
GET https://person.clearbit.com/v2/combined/find?email=alex@clearbit.com
```

Devuelve datos de persona y empresa en una sola solicitud.

### Reveal (IP a empresa)

```bash
GET https://reveal.clearbit.com/v1/companies/find?ip=104.132.0.0
```

Identifica la empresa detrás de un visitante del sitio web mediante su dirección IP.

### Name to Domain

```bash
GET https://company.clearbit.com/v1/domains/find?name=Clearbit
```

Convierte el nombre de una empresa en su dominio.

### Prospector (encontrar empleados)

```bash
GET https://prospector.clearbit.com/v1/people/search?domain=clearbit.com&role=sales&seniority=executive
```

Encuentra empleados de una empresa filtrados por rol, antigüedad y cargo.

## Patrón de API

Clearbit usa subdominios separados por API:
- `person.clearbit.com` - Datos de persona
- `company.clearbit.com` - Datos de empresa, Name to Domain
- `person-stream.clearbit.com` - Consulta de persona en streaming (bloqueante, hasta 60s)
- `company-stream.clearbit.com` - Consulta de empresa en streaming (bloqueante, hasta 60s)
- `reveal.clearbit.com` - IP a empresa
- `prospector.clearbit.com` - Búsqueda de empleados

Los endpoints estándar devuelven `202 Accepted` si los datos están siendo procesados (usar webhooks). Los endpoints de streaming bloquean hasta que los datos están listos.

## Métricas Clave

### Atributos de Persona
- `name.fullName` - Nombre completo
- `title` - Cargo
- `role` - Rol laboral (sales, engineering, etc.)
- `seniority` - Nivel de antigüedad
- `employment.name` - Nombre de la empresa
- `linkedin.handle` - Perfil de LinkedIn

### Atributos de Empresa
- `name` - Nombre de la empresa
- `domain` - Dominio del sitio web
- `category.industry` - Industria
- `metrics.employees` - Número de empleados
- `metrics.estimatedAnnualRevenue` - Rango de ingresos
- `tech` - Array del stack tecnológico
- `metrics.raised` - Total de financiamiento obtenido

## Parámetros

### Enriquecimiento de Persona
- `email` (requerido) - Dirección de correo electrónico a consultar
- `webhook_url` - URL para resultados asincrónicos
- `subscribe` - Suscribirse a cambios futuros

### Enriquecimiento de Empresa
- `domain` (requerido) - Dominio de la empresa a consultar
- `webhook_url` - URL para resultados asincrónicos

### Prospector
- `domain` (requerido) - Dominio de la empresa
- `role` - Filtro de rol laboral (sales, engineering, marketing, etc.)
- `seniority` - Filtro de antigüedad (executive, director, manager, etc.)
- `title` - Filtro de cargo exacto
- `page` - Número de página (predeterminado: 1)
- `page_size` - Resultados por página (predeterminado: 5, máximo: 20)

## Cuándo Usar

- Calificación y puntuación de leads basada en datos firmográficos
- Enriquecer contactos del CRM con datos de empresa y persona
- Desanonimizar visitantes del sitio web con Reveal
- Construir listas de prospectos con Prospector
- Personalizar marketing basado en atributos de la empresa
- Enrutar leads según tamaño de empresa, industria o stack tecnológico

## Límites de Tasa

- Enrichment: 600 solicitudes/minuto
- Prospector: 100 solicitudes/minuto
- Reveal: 600 solicitudes/minuto
- Las respuestas incluyen los headers `X-RateLimit-Limit` y `X-RateLimit-Remaining`

## Skills Relacionadas

- lead-scoring
- personalization
- abm-strategy
- lead-enrichment
- competitor-alternatives
