# Zapier

Plataforma de automatización de flujos de trabajo que conecta aplicaciones sin necesidad de código.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | Partner API para Zaps/tareas (requiere integración pública aprobada) + Webhooks (sin aprobación) |
| MCP | ✓ | Servidor MCP oficial hospedado — recomendado para agentes de IA, ver abajo |
| CLI | - | No disponible |
| SDK | - | Solo API y webhooks |

## Servidor MCP (recomendado para agentes de IA)

Es la forma más simple de que un agente actúe sobre Zapier — sin necesidad de aprobar una integración pública. Zapier expone más de 9,000 apps como herramientas MCP.

- **URL del servidor**: `https://mcp.zapier.com/api/v1/connect`
- **Autenticación**: OAuth — el cliente (Claude Code, Claude Desktop) te dirige al flujo de login de Zapier y Zapier configura el servidor automáticamente
- **Documentación oficial**: [docs.zapier.com/mcp](https://docs.zapier.com/mcp/home)

## Autenticación de la API (caso avanzado, no la ruta por defecto)

Gestionar Zaps directamente por API (listar, activar/desactivar, ver tareas) **no** es tan simple como generar una API key en Settings — requiere crear una **integración pública en la Partner API** con OAuth y pasar un proceso de revisión de Zapier (toma aproximadamente una semana). No recomiendes esta ruta a una agencia que solo quiere conectar el sistema — usa el servidor MCP de arriba, o webhooks (abajo), que no requieren aprobación.

### Listar Zaps (Partner API, requiere integración aprobada)

```bash
GET https://api.zapier.com/v2/zaps
Authorization: Bearer {oauth_token}
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
