# AudienceTap

Plataforma de "text-to-buy" para e-commerce DTC — permite comprar directamente dentro de la conversación de SMS, sin links ni checkout separado. Se diferencia de Postscript/Attentive en que el mensaje mismo es el punto de venta, no solo el canal de aviso.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | - | **No publica una API REST pública para desarrolladores** |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | - | No disponible |

## Cómo Se Integra en la Práctica

AudienceTap prioriza integraciones sin código sobre una API abierta:

- **Shopify y Stripe** — conexión OAuth de un clic, sin configuración adicional
- **Klaviyo y Zapier** — vía API key que se pega directamente en el dashboard de AudienceTap (la clave es de la otra herramienta, no de AudienceTap)
- **Zapier como puente** — es la vía real para que un agente de IA dispare flujos de trabajo con AudienceTap: conectar por [zapier.md](zapier.md) en vez de intentar llamar una API que no existe

**No documentes ni intentes construir llamadas directas `api.audiencetap.com/...`** — no hay evidencia de que exista ese endpoint público. Si el cliente necesita automatización más allá de lo que Shopify/Stripe/Klaviyo/Zapier cubren, contacta soporte de AudienceTap para confirmar si hay acceso API bajo NDA o plan empresarial antes de prometerlo.

## Cuándo Usar

- Marcas DTC de e-commerce con volumen de SMS marketing maduro que quieren vender directamente en el hilo de texto (reduce fricción de checkout)
- Como capa adicional sobre Postscript/Attentive/Klaviyo, no como reemplazo — AudienceTap se integra con esas herramientas, no las sustituye

## Skills Relevantes

- sms
- churn-prevention
