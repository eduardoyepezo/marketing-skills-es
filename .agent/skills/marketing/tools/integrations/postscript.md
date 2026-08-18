# Postscript

Plataforma de SMS/MMS marketing enfocada en Shopify — suscriptores, flows automatizados, campañas y checkout con opt-in compatible con TCPA. Uno de los dos jugadores dominantes de SMS marketing en e-commerce (junto a Attentive).

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API — mensajes, suscriptores, eventos |
| MCP | - | No hay servidor MCP oficial |
| CLI | - | No disponible en este repo |
| SDK | ✓ | JavaScript SDK para el lado del cliente (popups, checkbox de opt-in en checkout) |

## Autenticación

- **Tipo**: API Token
- **Encabezado**: `Authorization: Bearer {API_TOKEN}` (nivel tienda) o `X-Postscript-Shop-Token` (solo para partners que gestionan múltiples tiendas)
- **Obtener token**: Configuración de la tienda > API en el dashboard de Postscript

## Operaciones Comunes del Agente

### Enviar un mensaje

```bash
POST https://api.postscript.io/api/v2/message_requests

{
  "phone": "15555555555",
  "body": "Tu código de descuento: WELCOME10",
  "category": "promotional"
}
```

`category` puede ser `promotional` (default), `transactional` o `conversational` — afecta cómo se filtra en reportes y cuotas de envío. `media_url` convierte el mensaje en MMS. `scheduled_at` (ISO 8601) programa el envío.

### Agregar un suscriptor

Vía el JavaScript SDK del lado del cliente (popup, checkbox de checkout) o directamente por API para suscriptores recolectados en otro lado (ej. importar una lista existente).

## Documentación para Agentes de IA

Postscript publica un índice completo en Markdown pensado para agentes: [developers.postscript.io/llms.txt](https://developers.postscript.io/llms.txt).

## Cuándo Usar

- SMS marketing para tiendas Shopify — flows de abandono de carrito, bienvenida, post-compra, y campañas
- Cuando el cliente ya usa Postscript y necesitas automatizar el envío de campañas o consultar métricas
- Checkout con opt-in de SMS compatible con TCPA sin construirlo desde cero

## Límites de Tasa

- No publicados de forma fija — varían según plan y volumen de la cuenta; la API responde con detalles de estado por solicitud (HTTP 202 en envíos aceptados)

## Skills Relevantes

- sms
- email-sequence
- churn-prevention
