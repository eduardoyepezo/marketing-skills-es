# Apollo.io

Plataforma de prospección B2B y enriquecimiento de datos con más de 210 millones de contactos y 35 millones de empresas para inteligencia de ventas.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | People Search, Company Search, Enrichment, Sequences |
| MCP | - | No disponible |
| CLI | ✓ | [apollo.js](../clis/apollo.js) |
| SDK | - | Solo REST API |

## Autenticación

- **Tipo**: API Key
- **Header**: `x-api-key: {api_key}` o `Authorization: Bearer {token}`
- **Obtener clave**: Settings > Integrations > API en https://app.apollo.io

## Operaciones Comunes del Agente

### Búsqueda de personas

```bash
POST https://api.apollo.io/api/v1/mixed_people/api_search

{
  "person_titles": ["Sales Manager"],
  "person_locations": ["United States"],
  "organization_num_employees_ranges": ["1,100"],
  "page": 1
}
```

### Enriquecimiento de persona

```bash
POST https://api.apollo.io/api/v1/people/match

{
  "first_name": "Tim",
  "last_name": "Zheng",
  "domain": "apollo.io"
}
```

### Enriquecimiento masivo de personas

```bash
POST https://api.apollo.io/api/v1/people/bulk_match

{
  "details": [
    { "email": "tim@apollo.io" },
    { "first_name": "Jane", "last_name": "Doe", "domain": "example.com" }
  ]
}
```

### Búsqueda de organizaciones

```bash
POST https://api.apollo.io/api/v1/mixed_companies/search

{
  "organization_locations": ["United States"],
  "organization_num_employees_ranges": ["1,100"],
  "page": 1
}
```

### Enriquecimiento de organización

```bash
POST https://api.apollo.io/api/v1/organizations/enrich

{
  "domain": "apollo.io"
}
```

## Métricas Clave

### Datos de Persona
- `first_name`, `last_name` - Nombre
- `title` - Cargo
- `email` - Email verificado
- `linkedin_url` - Perfil de LinkedIn
- `organization` - Detalles de la empresa
- `seniority` - Nivel de antigüedad
- `departments` - Lista de departamentos

### Datos de Organización
- `name` - Nombre de la empresa
- `website_url` - Sitio web
- `estimated_num_employees` - Número de empleados
- `industry` - Industria
- `annual_revenue` - Ingresos anuales
- `technologies` - Stack tecnológico
- `funding_total` - Financiamiento total

## Parámetros

### Búsqueda de Personas
- `person_titles` - Array de cargos
- `person_locations` - Array de ubicaciones
- `person_seniorities` - Array: owner, founder, c_suite, partner, vp, head, director, manager, senior, entry
- `organization_num_employees_ranges` - Array de rangos (p. ej., "1,100")
- `organization_ids` - Filtrar por IDs de organización en Apollo
- `page` - Número de página (predeterminado: 1)
- `per_page` - Resultados por página (predeterminado: 25, máximo: 100)

### Enriquecimiento de Persona
- `email` - Dirección de email
- `first_name` + `last_name` + `domain` - Búsqueda alternativa
- `linkedin_url` - URL de LinkedIn
- `reveal_personal_emails` - Incluir emails personales
- `reveal_phone_number` - Incluir números de teléfono

### Búsqueda de Organizaciones
- `organization_locations` - Array de ubicaciones
- `organization_num_employees_ranges` - Rangos de cantidad de empleados
- `organization_ids` - IDs de organización específicos
- `page` - Número de página

## Cuándo Usar

- Construir listas de prospectos segmentadas por rol, antigüedad y tamaño de empresa
- Enriquecer leads con información de contacto verificada
- Encontrar tomadores de decisiones en cuentas objetivo
- Investigación de empresas y análisis firmográfico
- Segmentación de campañas ABM
- Inteligencia de ventas y prospección saliente

## Límites de Velocidad

- Los límites de velocidad varían según el plan
- Estándar: 100 solicitudes/minuto para la mayoría de los endpoints
- Enriquecimiento masivo: hasta 10 personas por solicitud
- Búsqueda: máximo 50,000 registros (100 por página, 500 páginas)

## Skills Relevantes

- abm-strategy
- lead-enrichment
- lead-scoring
- cold-email
- competitor-alternatives
