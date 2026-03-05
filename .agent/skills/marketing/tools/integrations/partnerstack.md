# PartnerStack

Plataforma de gestión de programas de socios y afiliados para empresas SaaS con seguimiento de acuerdos, recompensas y asociaciones multinivel.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Vendor API v2 para partnerships, deals, customers, transactions |
| MCP | - | No disponible |
| CLI | ✓ | [partnerstack.js](../clis/partnerstack.js) |
| SDK | - | Sin SDK oficial; REST API con Basic Auth |

## Autenticación

- **Tipo**: Basic Auth (Vendor API)
- **Encabezado**: `Authorization: Basic {base64(public_key:secret_key)}`
- **Obtener credenciales**: Panel de proveedor > Settings > Integrations > PartnerStack API Keys
- **Nota**: Claves API separadas para prueba y producción. Las transacciones de prueba solo se pueden agregar a clientes creados con claves de prueba.

## Operaciones Comunes del Agente

### Listar asociaciones

```bash
GET https://api.partnerstack.com/api/v2/partnerships?limit=25

Authorization: Basic {base64(public_key:secret_key)}
```

### Crear una asociación

```bash
POST https://api.partnerstack.com/api/v2/partnerships

{
  "email": "partner@example.com",
  "group_key": "affiliates",
  "first_name": "Jane",
  "last_name": "Smith"
}
```

### Listar clientes

```bash
GET https://api.partnerstack.com/api/v2/customers?limit=25
```

### Crear un cliente (atribuir a un socio)

```bash
POST https://api.partnerstack.com/api/v2/customers

{
  "email": "customer@example.com",
  "partner_key": "prtnr_abc123",
  "name": "John Doe"
}
```

### Registrar una transacción

```bash
POST https://api.partnerstack.com/api/v2/transactions

{
  "customer_key": "cust_abc123",
  "amount": 9900,
  "currency": "USD",
  "product_key": "pro_plan"
}
```

### Listar acuerdos

```bash
GET https://api.partnerstack.com/api/v2/deals?limit=25
```

### Crear un acuerdo

```bash
POST https://api.partnerstack.com/api/v2/deals

{
  "partner_key": "prtnr_abc123",
  "name": "Enterprise Opportunity",
  "amount": 50000,
  "stage": "qualified"
}
```

### Registrar una acción (recompensas basadas en eventos)

```bash
POST https://api.partnerstack.com/api/v2/actions

{
  "customer_key": "cust_abc123",
  "key": "signup_completed",
  "value": 1
}
```

### Crear una recompensa

```bash
POST https://api.partnerstack.com/api/v2/rewards

{
  "partner_key": "prtnr_abc123",
  "amount": 5000,
  "description": "Bonus for Q1 performance"
}
```

### Listar leads

```bash
GET https://api.partnerstack.com/api/v2/leads?limit=25
```

### Crear un lead

```bash
POST https://api.partnerstack.com/api/v2/leads

{
  "partner_key": "prtnr_abc123",
  "email": "lead@company.com",
  "name": "Potential Customer",
  "company": "Acme Corp"
}
```

### Listar grupos de socios

```bash
GET https://api.partnerstack.com/api/v2/groups
```

### Gestionar webhooks

```bash
POST https://api.partnerstack.com/api/v2/webhooks

{
  "target": "https://example.com/webhooks/partnerstack",
  "events": ["deal.created", "transaction.created", "customer.created"]
}
```

## Patrón de API

PartnerStack usa paginación basada en cursor. Las respuestas de lista incluyen `has_more` y claves de elementos para los parámetros `starting_after` / `ending_before`.

Todas las respuestas siguen el formato:
```json
{
  "data": { ... },
  "message": "...",
  "status": "2xx"
}
```

## Métricas Clave

### Métricas de Asociaciones
- `partner_key` - Identificador único del socio
- `group` - Nivel/grupo del socio
- `status` - active, pending, archived
- `created_at` - Fecha de inicio de la asociación

### Métricas de Transacciones
- `amount` - Valor de la transacción en centavos
- `currency` - Código de moneda
- `product_key` - Producto asociado
- `customer_key` - Cliente asociado

### Métricas de Acuerdos
- `amount` - Valor del acuerdo
- `stage` - Etapa del pipeline del acuerdo
- `status` - open, won, lost

### Métricas de Recompensas
- `amount` - Importe de la recompensa en centavos
- `status` - pending, approved, paid

## Parámetros

### Parámetros de Paginación
- `limit` - Elementos por página (1-250, predeterminado: 10)
- `starting_after` - Cursor para la página siguiente (clave de elemento)
- `ending_before` - Cursor para la página anterior (clave de elemento)
- `order_by` - Campo de ordenamiento, prefija con `-` para orden descendente

### Filtros Comunes
- `include_archived` - Incluir registros archivados
- `has_sub_id` - Filtrar por presencia de sub ID

## Cuándo Usar

- Gestionar programas de afiliados y referidos para SaaS
- Rastrear ingresos e imputaciones generadas por socios
- Automatizar la incorporación de socios y las recompensas
- Registro de acuerdos y seguimiento del pipeline
- Programas de asociación multinivel (afiliados, revendedores, agencias)
- Activadores de recompensas basados en eventos (registros, actualizaciones, etc.)

## Límites de Tasa

- No documentados explícitamente
- Usa tasas de solicitud razonables; implementa backoff exponencial en respuestas 429

## Skills Relevantes

- referral-program
- affiliate-marketing
- partner-enablement
- saas-metrics
- launch-sequence
