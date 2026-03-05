# ZoomInfo

Base de datos de contactos B2B y plataforma de datos de intención con más de 100 millones de contactos empresariales e inteligencia de empresas para equipos de ventas y marketing.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | Búsqueda de contactos, búsqueda de empresas, enriquecimiento, datos de intención, Scoops |
| MCP | ✓ | [Conector de Claude](https://claude.com/connectors/zoominfo) |
| CLI | ✓ | [zoominfo.js](../clis/zoominfo.js) |
| SDK | - | Solo REST API |

## Autenticación

- **Tipo**: JWT Token (Bearer)
- **Flujo**: POST `/authenticate` con username + password, recibe token JWT
- **Encabezado**: `Authorization: Bearer {jwt_token}`
- **Variables de entorno**: `ZOOMINFO_USERNAME` + `ZOOMINFO_PRIVATE_KEY` o `ZOOMINFO_ACCESS_TOKEN`
- **Obtener credenciales**: Contactar a ventas de ZoomInfo o portal de administración en https://app.zoominfo.com

## Operaciones Comunes del Agente

### Autenticar

```bash
POST https://api.zoominfo.com/authenticate

{
  "username": "user@company.com",
  "password": "private-key-here"
}
```

### Búsqueda de contactos

```bash
POST https://api.zoominfo.com/search/contact

{
  "jobTitle": ["VP Marketing"],
  "companyName": ["Acme Corp"],
  "managementLevel": ["VP"],
  "rpp": 25,
  "page": 1
}
```

### Enriquecimiento de contactos

```bash
POST https://api.zoominfo.com/enrich/contact

{
  "matchEmail": ["jane@acme.com"]
}
```

### Búsqueda de empresas

```bash
POST https://api.zoominfo.com/search/company

{
  "companyName": ["Acme"],
  "industry": ["Software"],
  "employeeCountMin": 50,
  "revenueMin": 10000000,
  "rpp": 25,
  "page": 1
}
```

### Enriquecimiento de empresas

```bash
POST https://api.zoominfo.com/enrich/company

{
  "matchCompanyWebsite": ["acme.com"]
}
```

### Consulta de datos de intención

```bash
POST https://api.zoominfo.com/lookup/intent

{
  "topicId": ["marketing-automation"],
  "companyId": ["123456"]
}
```

### Consulta de Scoops

```bash
POST https://api.zoominfo.com/lookup/scoops

{
  "companyId": ["123456"],
  "rpp": 25,
  "page": 1
}
```

## Métricas Clave

### Datos de contactos
- `firstName`, `lastName` - Nombre
- `jobTitle` - Cargo
- `email` - Correo electrónico verificado
- `phone` - Teléfono directo
- `linkedinUrl` - Perfil de LinkedIn
- `companyName` - Nombre de la empresa
- `managementLevel` - Nivel de antigüedad
- `department` - Departamento

### Datos de empresas
- `companyName` - Nombre de la empresa
- `website` - URL del sitio web
- `employeeCount` - Número de empleados
- `industry` - Industria
- `revenue` - Ingresos anuales
- `techStack` - Tecnologías utilizadas
- `fundingAmount` - Financiación total
- `companyCity`, `companyState`, `companyCountry` - Ubicación

### Datos de intención
- `topicName` - Tema de intención
- `signalScore` - Fuerza de la señal
- `audienceStrength` - Nivel de engagement de la audiencia
- `firstSeenDate`, `lastSeenDate` - Marco temporal de la señal

## Parámetros

### Búsqueda de contactos
- `jobTitle` - Array de cargos
- `companyName` - Array de nombres de empresas
- `managementLevel` - Array: C-Level, VP, Director, Manager, Staff
- `department` - Array: Marketing, Sales, Engineering, Finance, etc.
- `personLocationCity` - Array de ciudades
- `personLocationState` - Array de estados/provincias
- `personLocationCountry` - Array de países
- `rpp` - Resultados por página (predeterminado: 25, máximo: 100)
- `page` - Número de página (predeterminado: 1)

### Enriquecimiento de contactos
- `matchEmail` - Array de direcciones de correo electrónico
- `personId` - Array de IDs de persona de ZoomInfo
- `matchFirstName` + `matchLastName` + `matchCompanyName` - Búsqueda alternativa

### Búsqueda de empresas
- `companyName` - Array de nombres de empresas
- `industry` - Array de industrias
- `employeeCountMin` / `employeeCountMax` - Rango de número de empleados
- `revenueMin` / `revenueMax` - Rango de ingresos
- `companyLocationCity` - Array de ciudades
- `rpp` - Resultados por página
- `page` - Número de página

### Enriquecimiento de empresas
- `matchCompanyWebsite` - Array de dominios
- `companyId` - Array de IDs de empresa de ZoomInfo

### Datos de intención
- `topicId` - Array de IDs de temas de intención
- `companyId` - Array de IDs de empresas

## Cuándo Usar

- Identificar cuentas en el mercado con señales de intención
- Construir listas de contactos segmentadas por cargo, antigüedad y empresa
- Enriquecer leads con datos de contacto verificados e información firmográfica
- Encontrar tomadores de decisiones en cuentas objetivo para ABM
- Rastrear noticias de empresas y cambios de liderazgo mediante Scoops
- Priorizar el alcance basándose en señales de intención del comprador

## Límites de Tasa

- Los límites de tasa varían según el plan y el endpoint
- Estándar: ~200 solicitudes/minuto
- Endpoints masivos: se recomiendan solicitudes en lotes
- Los tokens de autenticación expiran tras ~12 horas

## Habilidades Relacionadas

- cold-email
- revops
- sales-enablement
- competitor-alternatives
