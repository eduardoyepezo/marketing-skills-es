# Zapier

Plataforma de automatización de flujos de trabajo que conecta aplicaciones sin necesidad de código.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | REST API para Zaps, tareas y webhooks |
| MCP | ✓ | Disponible mediante el servidor MCP de Zapier |
| CLI | - | No disponible |
| SDK | - | Solo API y webhooks |

## Autenticación

- **Tipo**: API Key
- **Encabezado**: `X-API-Key: {api_key}`
- **Obtener clave**: Settings > API en la cuenta de Zapier

## Operaciones Comunes del Agente

### Listar Zaps

```bash
GET https://api.zapier.com/v1/zaps
```

### Obtener detalles de un Zap

```bash
GET https://api.zapier.com/v1/zaps/{zap_id}
```

### Activar/desactivar Zap

```bash
POST https://api.zapier.com/v1/zaps/{zap_id}/on
POST https://api.zapier.com/v1/zaps/{zap_id}/off
```

### Obtener historial de tareas

```bash
GET https://api.zapier.com/v1/zaps/{zap_id}/tasks
```

### Obtener información del perfil

```bash
GET https://api.zapier.com/v1/profiles/me
```

## Webhooks (Disparadores)

### Catch Hook (recibir datos)

Crear un disparador "Webhooks by Zapier" para recibir datos:

```bash
POST https://hooks.zapier.com/hooks/catch/{webhook_id}/

{
  "event": "user.created",
  "user_id": "123",
  "email": "user@example.com"
}
```

### Enviar datos a Zapier

Lo más común: disparar un Zap desde tu aplicación:

```bash
POST https://hooks.zapier.com/hooks/catch/{account_id}/{hook_id}/

{
  "name": "John Doe",
  "email": "john@example.com",
  "plan": "pro"
}
```

## Automatizaciones de Marketing Comunes

### Captura de leads al CRM
```
Typeform → Zapier → HubSpot
```

### Notificaciones de nuevos clientes
```
Stripe (new customer) → Zapier → Slack
```

### Disparadores de secuencias de email
```
Form submission → Zapier → Customer.io
```

### Automatización de prueba social
```
New review → Zapier → Twitter/Slack
```

### Seguimiento de referidos
```
New referral → Zapier → Spreadsheet + Slack
```

## Estructura del payload del webhook

Al enviar a Zapier, estructura los datos como JSON plano:

```json
{
  "customer_name": "John Doe",
  "customer_email": "john@example.com",
  "plan_name": "Pro",
  "plan_price": 99,
  "signup_date": "2024-01-15"
}
```

## Conceptos Clave

- **Zap** - Flujo de trabajo automatizado
- **Trigger** - Evento que inicia un Zap
- **Action** - Tarea ejecutada por el Zap
- **Task** - Ejecución de una acción individual
- **Filter** - Lógica condicional
- **Path** - Lógica de ramificación

## Cuándo Usar

- Conectar herramientas de marketing sin código
- Automatizar el enrutamiento de leads
- Sincronizar datos entre plataformas
- Disparar notificaciones
- Construir flujos de trabajo de marketing

## Límites de Tasa

- 100 solicitudes por minuto
- Límites de tareas según el nivel del plan

## Habilidades Relacionadas

- email-sequence
- analytics-tracking
- referral-program
