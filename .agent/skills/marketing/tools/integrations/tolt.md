# Tolt

Gestión de programas de afiliados para SaaS, con integración de Stripe y Paddle.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | REST API para afiliados, referidos y pagos |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | - | Fragmento de JavaScript para seguimiento |

## Autenticación

- **Tipo**: API Key
- **Encabezado**: `Authorization: Bearer {api_key}`
- **Obtener clave**: Settings > API en el panel de Tolt

## Operaciones Comunes del Agente

### Listar afiliados

```bash
GET https://api.tolt.io/v1/affiliates
```

### Obtener afiliado

```bash
GET https://api.tolt.io/v1/affiliates/{affiliate_id}
```

### Crear afiliado

```bash
POST https://api.tolt.io/v1/affiliates

{
  "email": "affiliate@example.com",
  "name": "John Doe"
}
```

### Listar referidos

```bash
GET https://api.tolt.io/v1/referrals?affiliate_id={affiliate_id}
```

### Obtener referido por cliente

```bash
GET https://api.tolt.io/v1/referrals?customer_id={stripe_customer_id}
```

### Listar comisiones

```bash
GET https://api.tolt.io/v1/commissions?affiliate_id={affiliate_id}
```

### Obtener historial de pagos

```bash
GET https://api.tolt.io/v1/payouts?affiliate_id={affiliate_id}
```

### Actualizar afiliado

```bash
PATCH https://api.tolt.io/v1/affiliates/{affiliate_id}

{
  "commission_rate": 30,
  "payout_method": "paypal",
  "paypal_email": "affiliate@paypal.com"
}
```

## Seguimiento con JavaScript

### Instalar fragmento

```html
<script src="https://cdn.tolt.io/tolt.js" data-tolt="YOUR_PUBLIC_KEY"></script>
```

### Registrar alta

```javascript
window.tolt.signup(stripeCustomerId);
```

### Identificar cliente existente

```javascript
window.tolt.identify(stripeCustomerId);
```

## Eventos Webhook

| Evento | Cuándo |
|--------|--------|
| `affiliate.created` | Nuevo afiliado registrado |
| `affiliate.approved` | Afiliado aprobado |
| `referral.created` | Nuevo referido registrado |
| `referral.converted` | Referido convertido en cliente |
| `commission.created` | Comisión ganada |
| `payout.completed` | Pago enviado |

## Características Clave

- **Nativo de Stripe** - Seguimiento automático de comisiones
- **Soporte de Paddle** - Funciona con facturación de Paddle
- **Panel de afiliados** - Portal con marca blanca
- **Automatización de pagos** - Pagos por PayPal y Wise
- **Niveles de comisión personalizados** - Tasas diferentes por afiliado

## Objetos Clave

- **Affiliate** - Socio en tu programa
- **Referral** - Conversión rastreada
- **Commission** - Pago ganado por el afiliado
- **Payout** - Pago procesado al afiliado
- **Program** - Configuración de la campaña

## Cuándo Usar

- Configurar programas de afiliados para SaaS
- Gestionar relaciones con afiliados
- Rastrear referidos basados en Stripe o Paddle
- Procesar pagos a afiliados
- Construir paneles de afiliados

## Límites de Tasa

- 100 solicitudes por minuto
- Límites más altos en planes enterprise

## Habilidades Relacionadas

- referral-program
- pricing-strategy
