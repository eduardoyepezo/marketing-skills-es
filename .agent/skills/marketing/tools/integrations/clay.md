# Clay

Plataforma de enriquecimiento de datos y automatización outbound para construir listas de prospectos con enriquecimiento en cascada a través de más de 75 proveedores de datos.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Tables, People Enrichment, Company Enrichment |
| MCP | ✓ | [Claude connector](https://claude.com/connectors/clay) |
| CLI | ✓ | [clay.js](../clis/clay.js) |
| SDK | - | Solo REST API |

## Autenticación

- **Tipo**: API Key (Bearer token)
- **Header**: `Authorization: Bearer {api_key}`
- **Obtener clave**: Settings > API en https://app.clay.com

## Operaciones Comunes del Agente

### Listar Tables

```bash
GET https://api.clay.com/v3/tables

Authorization: Bearer {api_key}
```

### Obtener Detalles de una Table

```bash
GET https://api.clay.com/v3/tables/{table_id}

Authorization: Bearer {api_key}
```

### Obtener Filas de una Table

```bash
GET https://api.clay.com/v3/tables/{table_id}/rows?page=1&per_page=25

Authorization: Bearer {api_key}
```

### Agregar Fila a una Table

```bash
POST https://api.clay.com/v3/tables/{table_id}/rows

{
  "first_name": "Jane",
  "last_name": "Doe",
  "company": "Acme Inc",
  "email": "jane@acme.com"
}
```

### Enriquecimiento de Personas

```bash
POST https://api.clay.com/v3/people/enrich

{
  "email": "jane@acme.com"
}
```

### Enriquecimiento de Empresas

```bash
POST https://api.clay.com/v3/companies/enrich

{
  "domain": "acme.com"
}
```

## Métricas Clave

### Datos de Persona
- `first_name`, `last_name` - Nombre
- `email` - Dirección de correo electrónico
- `title` - Cargo
- `linkedin_url` - Perfil de LinkedIn
- `company` - Nombre de la empresa
- `location` - Ubicación
- `seniority` - Nivel de antigüedad

### Datos de Empresa
- `name` - Nombre de la empresa
- `domain` - Dominio del sitio web
- `industry` - Industria
- `employee_count` - Número de empleados
- `revenue` - Ingresos estimados
- `location` - Ubicación de la sede
- `technologies` - Stack tecnológico
- `description` - Descripción de la empresa

### Datos de Table
- `id` - ID de la table
- `name` - Nombre de la table
- `row_count` - Número de filas
- `columns` - Definiciones de columnas
- `created_at` - Timestamp de creación
- `updated_at` - Timestamp de última actualización

## Parámetros

### Tables
- `page` - Número de página (predeterminado: 1)
- `per_page` - Resultados por página (predeterminado: 25)

### Enriquecimiento de Personas
- `email` - Dirección de correo electrónico
- `linkedin_url` - URL del perfil de LinkedIn
- `first_name` + `last_name` - Búsqueda por nombre

### Enriquecimiento de Empresas
- `domain` - Dominio de la empresa (p. ej., "acme.com")

### Agregar Fila
- Los campos son dinámicos y coinciden con las definiciones de columnas de la table
- Pasar datos como pares clave-valor que coincidan con los nombres de las columnas

## Cuándo Usar

- Construir listas de prospectos enriquecidas con enriquecimiento en cascada a través de múltiples proveedores
- Enriquecer leads con datos de personas y empresas de más de 75 fuentes
- Automatizar flujos de trabajo outbound con datos enriquecidos
- Encontrar información de contacto verificada (correos, teléfonos, perfiles sociales)
- Investigación de empresas y análisis firmográfico
- Activar flujos de trabajo de enriquecimiento mediante webhooks
- Sincronizar datos enriquecidos de vuelta al CRM o herramientas outbound

## Límites de Tasa

- Los límites de tasa varían según el plan
- Standard: 100 solicitudes/minuto
- Los planes Enterprise tienen límites más altos
- Los créditos de enriquecimiento consumidos por consulta varían según el proveedor de datos
- Los endpoints de webhook aceptan datos de forma continua

## Skills Relacionadas

- cold-email
- revops
- sales-enablement
- competitor-alternatives
