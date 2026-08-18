# Plivo

Plataforma de comunicaciones en la nube — SMS, MMS, WhatsApp y voz. Alternativa a Twilio, generalmente más económica por segmento, con la misma lógica de infraestructura por debajo de plataformas de SMS marketing.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API completa — Messaging, Voice, Lookup |
| MCP | - | No hay servidor MCP oficial |
| CLI | - | No disponible en este repo |
| SDK | ✓ | SDKs oficiales (Node.js, Python, PHP, Ruby, Java, C#, Go) |

## Autenticación

- **Tipo**: HTTP Basic Auth
- **Usuario**: Auth ID
- **Contraseña**: Auth Token
- **Obtener credenciales**: Plivo Console Dashboard

## Operaciones Comunes del Agente

### Enviar un SMS

```bash
POST https://api.plivo.com/v1/Account/{auth_id}/Message/
Content-Type: application/json

{
  "src": "+14155551234",
  "dst": "+14155559876",
  "text": "Tu pedido está en camino"
}
```

Los números deben estar en formato E.164 (`+` seguido del código de país, sin espacios).

### Consultar el estado de un mensaje

```bash
GET https://api.plivo.com/v1/Account/{auth_id}/Message/{message_uuid}/
```

### Listar mensajes recientes

```bash
GET https://api.plivo.com/v1/Account/{auth_id}/Message/?limit=20
```

## Cuándo Usar

- Infraestructura de SMS transaccional a menor costo por segmento que Twilio, cuando el volumen es alto y el margen importa
- Cuando la agencia ya tiene una cuenta Plivo por decisión de costos y necesita depurar entregabilidad
- Verificación de números y lookup de tipo de línea antes de agregar un suscriptor

**No lo uses como reemplazo de una plataforma de SMS marketing** para una agencia — igual que Twilio, no trae gestión de opt-in/opt-out ni cumplimiento TCPA integrados. Para eso, ver [postscript.md](postscript.md) o [attentive.md](attentive.md).

## Límites de Tasa

- Varían por tipo de número (long code, short code, toll-free) y nivel de cuenta — revisar en la consola de Plivo

## Skills Relevantes

- sms
- email-sequence
