# Resend

Servicio de correo electrónico transaccional orientado a desarrolladores con una API moderna.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API sencilla para envío de correos |
| MCP | ✓ | Disponible mediante el servidor MCP de Resend |
| CLI | - | No disponible |
| SDK | ✓ | SDKs oficiales para Node.js, Python, Go, etc. |

## Autenticación

- **Tipo**: API Key
- **Encabezado**: `Authorization: Bearer {api_key}`
- **Obtener clave**: Sección API Keys en el panel de Resend

## Operaciones Comunes del Agente

### Enviar correo electrónico

```bash
POST https://api.resend.com/emails

{
  "from": "hello@example.com",
  "to": ["user@example.com"],
  "subject": "Welcome!",
  "html": "<h1>Welcome to our app!</h1>"
}
```

### Enviar con plantilla React

```bash
POST https://api.resend.com/emails

{
  "from": "hello@example.com",
  "to": ["user@example.com"],
  "subject": "Welcome!",
  "react": "WelcomeEmail",
  "props": {
    "name": "John"
  }
}
```

### Obtener estado de un correo

```bash
GET https://api.resend.com/emails/{email_id}
```

### Listar correos

```bash
GET https://api.resend.com/emails
```

### Enviar correos en lote

```bash
POST https://api.resend.com/emails/batch

[
  {
    "from": "hello@example.com",
    "to": ["user1@example.com"],
    "subject": "Welcome User 1"
  },
  {
    "from": "hello@example.com",
    "to": ["user2@example.com"],
    "subject": "Welcome User 2"
  }
]
```

### Listar dominios

```bash
GET https://api.resend.com/domains
```

### Verificar dominio

```bash
POST https://api.resend.com/domains/{domain_id}/verify
```

## SDK de Node.js

### Instalación

```bash
npm install resend
```

### Uso

```typescript
import { Resend } from 'resend';

const resend = new Resend('re_xxx');

await resend.emails.send({
  from: 'hello@example.com',
  to: 'user@example.com',
  subject: 'Welcome!',
  html: '<h1>Welcome!</h1>'
});
```

### Con React Email

```typescript
import { WelcomeEmail } from './emails/welcome';

await resend.emails.send({
  from: 'hello@example.com',
  to: 'user@example.com',
  subject: 'Welcome!',
  react: WelcomeEmail({ name: 'John' })
});
```

## Estados de Correo

- `queued` - Correo en cola para entrega
- `sent` - Correo enviado al servidor del destinatario
- `delivered` - Correo entregado
- `opened` - Correo abierto (si el rastreo está habilitado)
- `clicked` - Enlace clicado (si el rastreo está habilitado)
- `bounced` - Correo rebotado
- `complained` - Marcado como spam

## Eventos de Webhook

| Evento | Cuándo |
|-------|------|
| `email.sent` | Correo enviado |
| `email.delivered` | Correo entregado |
| `email.opened` | Correo abierto |
| `email.clicked` | Enlace clicado |
| `email.bounced` | Correo rebotado |
| `email.complained` | Queja de spam |

## Cuándo Usar

- Envío de correos transaccionales
- Correos de bienvenida, restablecimiento de contraseña
- Correos de recibo y notificación
- Integración de correo electrónico orientada a desarrolladores
- Plantillas de correo basadas en React

## Límites de Tasa

- Gratuito: 100 correos/día, 3.000/mes
- Pro: 100 correos/segundo
- Límites superiores en planes de escala

## Skills Relevantes

- email-sequence
- onboarding-cro
