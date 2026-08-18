# Attentive

Plataforma de SMS/MMS marketing de nivel empresarial — mensajes transaccionales, campañas, journeys automatizados y gestión de suscripción. El otro jugador dominante de SMS marketing en e-commerce junto a Postscript, con más presencia en marcas de mayor volumen.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API completa — mensajes, suscripciones, atributos de suscriptor, eventos |
| MCP | - | No hay servidor MCP oficial |
| CLI | - | No disponible en este repo |
| SDK | - | Solo REST API — sin SDKs oficiales publicados |

## Autenticación

- **Aplicaciones privadas**: `Authorization: Bearer {API_KEY}`
- **Aplicaciones públicas**: OAuth 2.0 con flujo de código de autorización (token de acceso sin expiración)
- **Verificar credenciales**: endpoint `/me` confirma si el token es válido
- **Obtener clave**: dashboard de Attentive, sección de integraciones/API

## Operaciones Comunes del Agente

### Enviar un mensaje transaccional

```bash
POST https://api.attentivemobile.com/1/messages
Content-Type: application/json

{
  "to": "5555555555",
  "body": "Tu pedido de XYZ fue confirmado por $49.99. Te avisamos cuando salga para entrega.",
  "type": "TRANSACTIONAL",
  "mediaUrl": "https://tusitio.com/imagen.png"
}
```

`type` debe ser exactamente `"TRANSACTIONAL"` (sensible a mayúsculas). Los mensajes solo se pueden enviar a suscriptores que ya dieron opt-in — Attentive no permite outbound frío.

## Cuándo Usar

- SMS marketing para marcas de e-commerce de mayor volumen, journeys automatizados complejos
- Mensajes transaccionales (confirmación de pedido, envío) que requieren mayor deliverabilidad que un SMS genérico
- Cuando el cliente ya usa Attentive y necesitas automatizar envíos o sincronizar atributos de suscriptor

## Límites de Tasa

- No publicados de forma fija — varían según plan de cuenta; revisar en la documentación específica del endpoint usado

## Skills Relevantes

- sms
- email-sequence
- churn-prevention
