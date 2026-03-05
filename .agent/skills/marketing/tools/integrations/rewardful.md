# Rewardful

Seguimiento de afiliados y referencias para negocios SaaS basados en Stripe.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API para afiliados, referencias, comisiones |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | - | Solo API, fragmento JavaScript para seguimiento |

## Autenticación

- **Tipo**: API Key
- **Header**: `Authorization: Bearer {api_secret}`
- **Obtener clave**: Settings > API en el panel de Rewardful

## Operaciones Comunes del Agente

### Listar afiliados

```bash
GET https://api.getrewardful.com/v1/affiliates
```

### Obtener afiliado por ID

```bash
GET https://api.getrewardful.com/v1/affiliates/{affiliate_id}
```

### Buscar afiliado por correo electrónico

```bash
GET https://api.getrewardful.com/v1/affiliates?email=affiliate@example.com
```

### Obtener referencia por cliente de Stripe

```bash
GET https://api.getrewardful.com/v1/referrals?stripe_customer_id={customer_id}
```

### Listar referencias de un afiliado

```bash
GET https://api.getrewardful.com/v1/referrals?affiliate_id={affiliate_id}
```

### Obtener detalles de comisión

```bash
GET https://api.getrewardful.com/v1/commissions/{commission_id}
```

### Listar comisiones

```bash
GET https://api.getrewardful.com/v1/commissions?affiliate_id={affiliate_id}
```

### Crear enlace de afiliado

```bash
POST https://api.getrewardful.com/v1/affiliates/{affiliate_id}/links

{
  "token": "custom-link-token",
  "url": "https://example.com/pricing"
}
```

### Actualizar afiliado

```bash
PUT https://api.getrewardful.com/v1/affiliates/{affiliate_id}

{
  "first_name": "John",
  "last_name": "Doe",
  "paypal_email": "john@example.com"
}
```

## Seguimiento JavaScript

### Instalar fragmento

```html
<script>
(function(w,r){w._rwq=r;w[r]=w[r]||function(){(w[r].q=w[r].q||[]).push(arguments)}})(window,'rewardful');
</script>
<script async src='https://r.wdfl.co/rw.js' data-rewardful='YOUR_API_KEY'></script>
```

### Registrar conversión manualmente

```javascript
rewardful('convert', { email: 'customer@example.com' });
```

## Eventos de Webhook

| Evento | Cuándo |
|-------|------|
| `affiliate.created` | Un nuevo afiliado se registra |
| `affiliate.approved` | Afiliado aprobado |
| `referral.created` | Nueva referencia rastreada |
| `referral.converted` | La referencia se convierte en cliente |
| `commission.created` | Comisión generada |
| `commission.paid` | Comisión pagada |

## Objetos Clave

- **Affiliate** - Socio que promociona tu producto
- **Referral** - Visita/cliente potencial rastreado proveniente de un afiliado
- **Commission** - Pago generado para el afiliado
- **Campaign** - Programa con condiciones específicas
- **Link** - URL de seguimiento para el afiliado

## Integración con Stripe

Rewardful automáticamente:
1. Rastrea la cookie de referencia cuando el usuario visita a través del enlace de afiliado
2. Asocia al cliente de Stripe con la referencia al momento del pago
3. Crea comisiones cuando se pagan las suscripciones
4. Gestiona comisiones recurrentes por suscripciones

## Cuándo Usar

- Configurar programas de afiliados/referencias para SaaS
- Rastrear la atribución de referencias desde pagos de Stripe
- Gestionar relaciones con afiliados
- Procesar pagos a afiliados
- Analizar el rendimiento del programa de referencias

## Límites de Velocidad

- 120 solicitudes por minuto
- Contactar soporte para límites más altos

## Habilidades Relevantes

- referral-program
- pricing-strategy
