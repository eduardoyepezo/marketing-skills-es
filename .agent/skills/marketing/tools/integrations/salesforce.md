# Salesforce

Plataforma CRM empresarial para ventas, servicio al cliente y marketing.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API, SOAP API, Bulk API |
| MCP | - | No disponible |
| CLI | ✓ | Salesforce CLI (`sf`) |
| SDK | ✓ | JSforce, simple-salesforce, etc. |

## Autenticación

- **Tipo**: OAuth 2.0 (Web Server Flow o JWT Bearer)
- **Header**: `Authorization: Bearer {access_token}`
- **URL de instancia**: Usar instance_url de la respuesta de autenticación

## Operaciones Comunes del Agente

### Consultar registros (SOQL)

```bash
GET https://{instance}.salesforce.com/services/data/v59.0/query?q=SELECT+Id,Name,Email+FROM+Contact+LIMIT+10

Authorization: Bearer {access_token}
```

### Obtener registro por ID

```bash
GET https://{instance}.salesforce.com/services/data/v59.0/sobjects/Contact/{record_id}

Authorization: Bearer {access_token}
```

### Crear registro

```bash
POST https://{instance}.salesforce.com/services/data/v59.0/sobjects/Contact

{
  "FirstName": "John",
  "LastName": "Doe",
  "Email": "john@example.com",
  "AccountId": "{account_id}"
}
```

### Actualizar registro

```bash
PATCH https://{instance}.salesforce.com/services/data/v59.0/sobjects/Contact/{record_id}

{
  "Title": "Senior Developer"
}
```

### Buscar registros (SOSL)

```bash
GET https://{instance}.salesforce.com/services/data/v59.0/search?q=FIND+{searchTerm}+IN+ALL+FIELDS+RETURNING+Contact(Id,Name,Email)

Authorization: Bearer {access_token}
```

### Obtener oportunidades

```bash
GET https://{instance}.salesforce.com/services/data/v59.0/query?q=SELECT+Id,Name,Amount,StageName,CloseDate+FROM+Opportunity+WHERE+IsClosed=false

Authorization: Bearer {access_token}
```

### Describir objeto

```bash
GET https://{instance}.salesforce.com/services/data/v59.0/sobjects/Contact/describe

Authorization: Bearer {access_token}
```

## Comandos CLI

```bash
# Autenticar
sf org login web

# Consultar registros
sf data query --query "SELECT Id, Name FROM Account LIMIT 10"

# Crear registro
sf data create record --sobject Account --values "Name='New Account'"

# Desplegar metadatos
sf project deploy start

# Ejecutar Apex
sf apex run --file script.apex
```

## Ejemplos SOQL

```sql
-- Obtener contactos con cuentas
SELECT Id, Name, Email, Account.Name
FROM Contact
WHERE Account.Industry = 'Technology'

-- Obtener oportunidades por etapa
SELECT StageName, COUNT(Id)
FROM Opportunity
GROUP BY StageName

-- Obtener leads recientes
SELECT Id, Name, Company, Status
FROM Lead
WHERE CreatedDate = LAST_N_DAYS:30
ORDER BY CreatedDate DESC
```

## Objetos Clave

- **Lead** - Cliente potencial
- **Contact** - Persona en una cuenta
- **Account** - Empresa u organización
- **Opportunity** - Negociación de ventas
- **Case** - Ticket de soporte
- **Campaign** - Campaña de marketing

## Cuándo Usar

- Operaciones de CRM empresarial
- Procesos de ventas complejos
- Relaciones entre múltiples objetos
- Gestión de objetos personalizados
- Seguimiento de campañas de marketing

## Límites de Velocidad

- 15,000 llamadas a la API por 24 horas (Enterprise)
- Límites más altos disponibles

## Habilidades Relevantes

- email-sequence
- analytics-tracking
- paid-ads
