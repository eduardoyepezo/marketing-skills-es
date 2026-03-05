# Stripe

Procesamiento de pagos, suscripciones y facturación para negocios en internet.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | REST API completa |
| MCP | ✓ | Disponible mediante el servidor MCP de Stripe |
| CLI | ✓ | CLI `stripe` para pruebas y webhooks |
| SDK | ✓ | SDKs oficiales para la mayoría de lenguajes |

## Autenticación

- **Tipo**: API Key
- **Encabezado**: `Authorization: Bearer sk_live_xxx` o `sk_test_xxx`
- **Claves**: Clave secreta (servidor), clave publicable (cliente)

## Operaciones Comunes del Agente

### Listar clientes

```bash
GET https://api.stripe.com/v1/customers?limit=10
```

### Obtener cliente por correo electrónico

```bash
GET https://api.stripe.com/v1/customers?email=user@example.com
```

### Obtener suscripción

```bash
GET https://api.stripe.com/v1/subscriptions/{subscription_id}
```

### Listar suscripciones de un cliente

```bash
GET https://api.stripe.com/v1/subscriptions?customer={customer_id}
```

### Crear sesión de checkout

```bash
POST https://api.stripe.com/v1/checkout/sessions

customer={customer_id}
&line_items[0][price]={price_id}
&line_items[0][quantity]=1
&mode=subscription
&success_url=https://example.com/success
&cancel_url=https://example.com/cancel
```

### Crear sesión del portal de clientes

```bash
POST https://api.stripe.com/v1/billing_portal/sessions

customer={customer_id}
&return_url=https://example.com/account
```

### Listar facturas recientes

```bash
GET https://api.stripe.com/v1/invoices?customer={customer_id}&limit=10
```

### Obtener intención de pago

```bash
GET https://api.stripe.com/v1/payment_intents/{payment_intent_id}
```

## Eventos Webhook

Eventos clave a gestionar:

| Evento | Cuándo | Acción |
|--------|--------|--------|
| `checkout.session.completed` | Checkout exitoso | Aprovisionar acceso |
| `customer.subscription.created` | Nueva suscripción | Actualizar registro de usuario |
| `customer.subscription.updated` | Cambio de plan | Actualizar permisos |
| `customer.subscription.deleted` | Cancelación | Revocar acceso |
| `invoice.payment_failed` | Pago fallido | Notificar al usuario, reintentar |
| `invoice.paid` | Factura pagada | Confirmar pago |

### Verificar firma del webhook

```javascript
const event = stripe.webhooks.constructEvent(
  payload,
  sig,
  webhookSecret
);
```

## Comandos CLI

```bash
# Escuchar webhooks localmente
stripe listen --forward-to localhost:3000/webhooks

# Disparar eventos de prueba
stripe trigger checkout.session.completed

# Listar eventos recientes
stripe events list --limit 10

# Obtener recurso
stripe customers retrieve cus_xxx
```

## Objetos Clave

- **Customer** - Perfil de facturación del usuario
- **Subscription** - Facturación recurrente
- **Price** - Configuración de precios
- **Product** - Lo que vendes
- **Invoice** - Documento de facturación
- **PaymentIntent** - Pago único
- **Checkout Session** - Página de pago alojada

## Cuándo Usar

- Procesar pagos
- Gestionar suscripciones
- Crear flujos de checkout
- Gestionar portal de facturación
- Consultar datos de clientes
- Analítica de ingresos

## Límites de Tasa

- 100 solicitudes de lectura por segundo
- 100 solicitudes de escritura por segundo
- Límites más altos disponibles bajo petición

## Habilidades Relacionadas

- pricing-strategy
- referral-program (herramientas de afiliados integradas con Stripe)
- analytics-tracking (seguimiento de ingresos)
