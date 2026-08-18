# Twilio

Plataforma de comunicaciones en la nube — SMS, voz, WhatsApp y verificación. La infraestructura sobre la que corren muchas otras plataformas de SMS marketing (Postscript, Attentive y similares suelen usar Twilio o un proveedor equivalente por debajo).

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API completa — Messaging, Voice, Verify |
| MCP | - | No hay servidor MCP oficial |
| CLI | - | No disponible en este repo (Twilio tiene su propio CLI oficial, `twilio-cli`) |
| SDK | ✓ | SDKs oficiales para la mayoría de lenguajes (Node.js, Python, PHP, Ruby, Java, C#) |

## Autenticación

- **Tipo**: HTTP Basic Auth
- **Usuario**: API Key SID (recomendado para producción) o Account SID (para pruebas locales)
- **Contraseña**: API Key Secret o Auth Token
- **Obtener credenciales**: Twilio Console > Account > API keys & tokens

## Operaciones Comunes del Agente

### Enviar un SMS

```bash
POST https://api.twilio.com/2010-04-01/Accounts/{AccountSid}/Messages.json

# Body form-encoded:
To=+15558675309&From=+15017122661&Body=Tu pedido está en camino
```

### Consultar el estado de un mensaje

```bash
GET https://api.twilio.com/2010-04-01/Accounts/{AccountSid}/Messages/{MessageSid}.json
```

### Listar mensajes recientes

```bash
GET https://api.twilio.com/2010-04-01/Accounts/{AccountSid}/Messages.json?PageSize=20
```

## Notas de Región

Para residencia de datos en la UE, usa el subdominio de Dublín: `https://api.dublin.ie1.twilio.com/2010-04-01/...`

## Cuándo Usar

- Infraestructura de SMS transaccional (confirmaciones de pedido, OTPs, alertas) cuando no se necesita una capa de marketing/segmentación encima
- Cuando la agencia ya tiene un proveedor de SMS marketing (Postscript, Attentive) que corre sobre Twilio y necesitas depurar entregabilidad a bajo nivel
- Verificación de números telefónicos (Verify API) antes de agregar un suscriptor a una lista de SMS marketing

**No lo uses como reemplazo de una plataforma de SMS marketing** (Postscript, Attentive, Klaviyo) para una agencia — Twilio no trae gestión de opt-in/opt-out, segmentación ni cumplimiento TCPA integrados; eso hay que construirlo encima. Para SMS marketing con esas capacidades ya resueltas, ver [postscript.md](postscript.md) o [attentive.md](attentive.md).

## Límites de Tasa

- 1 mensaje/segundo por número de origen por defecto (aumenta con Messaging Service + short code o toll-free verificado)
- Límites de la API general: varían por cuenta y nivel de confianza

## Skills Relevantes

- sms
- email-sequence
