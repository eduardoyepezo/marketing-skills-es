# Paddle

Plataforma de facturación y pagos para SaaS con cumplimiento fiscal integrado, que actúa como comerciante de registro para ventas globales.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API para products, prices, subscriptions, transactions |
| MCP | - | No disponible |
| CLI | ✓ | [paddle.js](../clis/paddle.js) |
| SDK | ✓ | Node.js, Python, PHP, Go |

## Autenticación

- **Tipo**: Bearer Token
- **Encabezado**: `Authorization: Bearer {api_key}`
- **Obtener clave**: Panel de Paddle > Developer Tools > Authentication
- **URL de producción**: `https://api.paddle.com`
- **URL de sandbox**: `https://sandbox-api.paddle.com`
- **Nota**: La versión se especifica mediante encabezado, no por ruta. Establece la variable de entorno `PADDLE_SANDBOX=true` para el sandbox.

## Operaciones Comunes del Agente

### Listar productos

```bash
GET https://api.paddle.com/products
```

### Crear un producto

```bash
POST https://api.paddle.com/products

{
  "name": "Pro Plan",
  "tax_category": "standard",
  "description": "Professional tier subscription"
}
```

### Crear un precio para un producto

```bash
POST https://api.paddle.com/prices

{
  "product_id": "pro_01abc...",
  "description": "Monthly Pro",
  "unit_price": {
    "amount": "2999",
    "currency_code": "USD"
  },
  "billing_cycle": {
    "interval": "month",
    "frequency": 1
  }
}
```

### Listar clientes

```bash
GET https://api.paddle.com/customers
```

### Crear un cliente

```bash
POST https://api.paddle.com/customers

{
  "email": "customer@example.com",
  "name": "Jane Smith"
}
```

### Listar suscripciones

```bash
GET https://api.paddle.com/subscriptions?status=active
```

### Obtener detalles de una suscripción

```bash
GET https://api.paddle.com/subscriptions/{subscription_id}
```

### Cancelar una suscripción

```bash
POST https://api.paddle.com/subscriptions/{subscription_id}/cancel

{
  "effective_from": "next_billing_period"
}
```

### Pausar una suscripción

```bash
POST https://api.paddle.com/subscriptions/{subscription_id}/pause
```

### Listar transacciones

```bash
GET https://api.paddle.com/transactions
```

### Crear un descuento

```bash
POST https://api.paddle.com/discounts

{
  "amount": "20",
  "type": "percentage",
  "description": "20% off first month",
  "code": "WELCOME20"
}
```

### Crear un ajuste de reembolso

```bash
POST https://api.paddle.com/adjustments

{
  "transaction_id": "txn_01abc...",
  "action": "refund",
  "reason": "Customer requested refund",
  "items": [{"item_id": "txnitm_01abc...", "type": "full"}]
}
```

### Listar eventos

```bash
GET https://api.paddle.com/events
```

### Listar tipos de eventos

```bash
GET https://api.paddle.com/event-types
```

## Métricas Clave

### Métricas de Transacciones
- `totals.total` - Importe total cobrado
- `totals.tax` - Importe de impuestos
- `totals.subtotal` - Importe antes de impuestos
- `totals.discount` - Descuento aplicado
- `currency_code` - Moneda de la transacción

### Métricas de Suscripciones
- `status` - active, canceled, paused, past_due, trialing
- `current_billing_period` - Inicio/fin del período actual
- `next_billed_at` - Próxima fecha de facturación
- `scheduled_change` - Cambios pendientes (cancelación, cambio de plan)

### Métricas de Producto/Precio
- `unit_price.amount` - Precio en la denominación más baja
- `billing_cycle` - Intervalo y frecuencia
- `trial_period` - Duración de la prueba si está configurada

## Parámetros

### Filtrado de Listas
- `status` - Filtrar por estado (p. ej., active, archived)
- `after` - Cursor para paginación
- `per_page` - Resultados por página (predeterminado: 50)
- `order_by` - Campo y dirección de ordenamiento

### Opciones de Cancelación de Suscripción
- `effective_from` - `immediately` o `next_billing_period`

### Ciclo de Facturación de Precio
- `interval` - `day`, `week`, `month`, `year`
- `frequency` - Número de intervalos entre facturaciones

### Categorías Fiscales
- `standard` - Tasa impositiva estándar
- `digital-goods` - Tasa impositiva para bienes digitales
- `saas` - Tasa impositiva específica para SaaS

## Cuándo Usar

- Gestionar la facturación de suscripciones SaaS con cumplimiento fiscal
- Crear productos y niveles de precios
- Procesar reembolsos y ajustes
- Gestionar el ciclo de vida de suscripciones (crear, pausar, cancelar, reanudar)
- Manejo de impuestos globales como comerciante de registro
- Gestión de descuentos y cupones para promociones

## Límites de Tasa

- 100 solicitudes por minuto
- Aplica a todos los endpoints
- HTTP 429 devuelto cuando se supera el límite

## Skills Relevantes

- pricing-page
- saas-metrics
- churn-reduction
- launch-sequence
- monetization-strategy
