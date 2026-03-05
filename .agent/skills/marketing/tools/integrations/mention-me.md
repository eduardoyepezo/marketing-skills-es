# Mention Me

Plataforma de marketing de referidos empresarial para la promoción de clientes.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API para referidos, clientes y recompensas |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | - | Widget de JavaScript para incrustar |

## Autenticación

- **Tipo**: API Key
- **Header**: `Authorization: Bearer {api_key}`
- **Entorno**: Claves separadas para sandbox y producción

## Operaciones Comunes del Agente

### Crear oferta de referido

```bash
POST https://api.mention-me.com/api/v2/referrer-offer

{
  "email": "customer@example.com",
  "firstname": "John",
  "lastname": "Doe",
  "order_number": "ORD-123",
  "order_total": 99.99,
  "order_currency": "USD"
}
```

### Obtener enlace de referido para un cliente

```bash
GET https://api.mention-me.com/api/v2/referrer/{customer_id}/share-links
```

### Registrar referee (cliente referido)

```bash
POST https://api.mention-me.com/api/v2/referee

{
  "email": "referred@example.com",
  "firstname": "Jane",
  "referrer_code": "JOHN123",
  "order_number": "ORD-456",
  "order_total": 149.99
}
```

### Obtener estado de referido

```bash
GET https://api.mention-me.com/api/v2/referral/{referral_id}
```

### Listar referidos de un cliente

```bash
GET https://api.mention-me.com/api/v2/referrer/{customer_id}/referrals
```

### Obtener saldo de recompensas

```bash
GET https://api.mention-me.com/api/v2/referrer/{customer_id}/rewards
```

### Canjear recompensa

```bash
POST https://api.mention-me.com/api/v2/referrer/{customer_id}/rewards/redeem

{
  "reward_id": "RWD-123",
  "order_number": "ORD-789"
}
```

## Widget de JavaScript

### Incrustar widget de referido

```html
<div id="mmWrapper"></div>
<script>
  window.MentionMe = window.MentionMe || [];
  MentionMe.push({
    type: 'offer',
    customer: {
      email: 'customer@example.com',
      firstname: 'John',
      order_number: 'ORD-123'
    }
  });
</script>
<script src="https://tag.mention-me.com/client/{partner_code}.js" async></script>
```

### Widget de compartir por nombre

```javascript
MentionMe.push({
  type: 'nameShare',
  customer: {
    email: 'customer@example.com'
  }
});
```

## Eventos de Webhook

| Evento | Cuándo |
|-------|------|
| `referral.created` | Nuevo referido registrado |
| `referral.converted` | El referido completó una compra |
| `reward.earned` | Recompensa desbloqueada |
| `reward.redeemed` | Recompensa utilizada |

## Características Clave

- **Pruebas A/B** - Marco de experimentación integrado
- **Prevención de fraude** - Detección automática de fraude
- **Multicanal** - Compartir mediante enlace, email y redes sociales
- **Compartir por nombre** - Referir por nombre, no por código
- **Segmentación** - Diferentes ofertas por segmento
- **Analíticas** - Reportes del programa de referidos

## Objetos Clave

- **Referrer** - Cliente que refiere
- **Referee** - Cliente que es referido
- **Referral** - Conexión entre referrer y referee
- **Offer** - Configuración del programa de referidos
- **Reward** - Incentivo ganado

## Cuándo Usar

- Programas de referidos empresariales
- Campañas de referidos en múltiples mercados
- Pruebas A/B de ofertas de referidos
- Seguimiento de referidos resistente al fraude
- Programas de compartir por nombre

## Límites de Uso

- 1000 solicitudes por minuto
- Contactar para límites más altos

## Skills Relacionados

- referral-program
- pricing-strategy
- analytics-tracking
