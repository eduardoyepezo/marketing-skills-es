# Referencia de Plataformas de SMS

Análisis profundo de las principales plataformas de marketing por SMS — funciones, precios, soporte de A2P 10DLC y rutas de integración.

> Los precios son aproximados y cambian con regularidad. Siempre confirma en el sitio del proveedor antes de comprometerte.

---

## Klaviyo SMS

**Mejor para**: marcas de ecommerce DTC que ya usan Klaviyo para email.

### Funciones clave
- Integración nativa con el email y la segmentación de Klaviyo
- Perfil de suscriptor compartido entre email + SMS
- Registro A2P 10DLC integrado
- Constructor de flujos compartido con los flujos de email
- Soporte para SMS conversacional (bidireccional)

### Precios
- Incluido en los planes de Klaviyo, facturado por crédito de SMS
- US: ~$0.0075–$0.015 por SMS; MMS ~$0.04
- Nivel gratuito: 150 créditos de SMS/mes en los planes de email de nivel más bajo

### Rutas de integración
- Integración directa con Shopify, WooCommerce, BigCommerce, Magento
- API para plataformas personalizadas
- Servidor MCP disponible

### Cumplimiento
- Registro A2P 10DLC gestionado dentro de la plataforma
- Aprovisionamiento de toll-free y short code disponible (el short code agrega $1,000+/mes)
- Horario de silencio aplicado según la zona horaria del destinatario (configurable)

### A tener en cuenta
- La facturación combinada de email + SMS puede dispararse rápido en listas grandes
- Los costos de short code son overhead real; solo vale la pena para 100K+ suscriptores de SMS activos

---

## Postscript

**Mejor para**: marcas DTC nativas de Shopify que quieren herramientas específicas de SMS y soporte de onboarding.

### Funciones clave
- Integración profunda con Shopify (la más profunda de cualquier plataforma de SMS)
- Automatizaciones sólidas de carrito abandonado y abandono de navegación
- AI Reply (respuesta automática entrenada en la voz de la marca)
- SMS conversacional / agente en vivo
- Audiencias extraídas de los datos de clientes de Shopify

### Precios
- Planes escalonados: Starter (gratis, 1K mensajes/mes), Growth ($100+/mes), Professional, Enterprise
- El pago por envío se suma encima: ~$0.015 por SMS, ~$0.04 por MMS

### Rutas de integración
- Enfocado primero en Shopify; soporte limitado para plataformas que no son Shopify
- API + webhooks disponibles

### Cumplimiento
- A2P 10DLC gestionado dentro de la plataforma
- Herramientas sólidas de cumplimiento de opt-in (constructor de popups, opt-in por palabra clave)
- Horario de silencio aplicado

### A tener en cuenta
- Aumento pronunciado de costo pasado el nivel Starter
- Menos útil si no estás en Shopify

---

## Attentive

**Mejor para**: marcas DTC mid-market y enterprise que quieren SMS full-service.

### Funciones clave
- Full-service: CSM dedicado, soporte de copy, estrategia
- SMS conversacional a escala
- Venta concierge vía SMS
- Analíticas y atribución sólidas
- Resolución de identidad (emparejar visitantes anónimos del sitio con números de teléfono)

### Precios
- Contratos personalizados; típicamente $1K–$10K+/mes + tarifas por envío
- Contratos anuales estándar
- El precio rara vez tiene sentido para <50K suscriptores de SMS

### Rutas de integración
- Shopify, BigCommerce, Salesforce Commerce Cloud, personalizado
- API robusta

### Cumplimiento
- A2P 10DLC totalmente gestionado
- Herramientas de cumplimiento y soporte de auditoría de primer nivel
- Aprovisionamiento de short code incluido en la mayoría de los planes

### A tener en cuenta
- Los términos del contrato pueden atarte por 12+ meses
- Excesivo para marcas en etapa temprana

---

## Twilio

**Mejor para**: builds a la medida, SMS transaccional, B2B SaaS que integra SMS en sus productos, desarrolladores.

### Funciones clave
- API de SMS cruda
- Precios de pago por envío, sin tarifas de plataforma
- Cobertura global masiva (200+ países)
- Programmable Voice, WhatsApp Business, RCS disponibles en paralelo
- Studio (constructor visual de flujos) para automatización sin código

### Precios
- SMS 10DLC en US: $0.0079 por mensaje
- SMS toll-free en US: $0.0079 por mensaje
- SMS short code en US: $0.0079 por mensaje + arrendamiento de $1,000/mes
- MMS: ~$0.02
- Sobrecargos de carrier añadidos encima (~$0.005 por 10DLC en US)
- Registro A2P 10DLC: ~$15 marca + $10/mes por campaña

### Rutas de integración
- API-first (REST + SDKs en Node, Python, Ruby, Go, etc.)
- Sin integraciones nativas de ecommerce — las construyes tú

### Cumplimiento
- Registro A2P 10DLC dentro de la plataforma pero el trabajo lo haces tú
- TwilioSendGrid (producto separado) maneja el cumplimiento del lado del email
- El horario de silencio y el manejo de STOP/HELP deben ser implementados por ti

### A tener en cuenta
- Eres responsable del cumplimiento — sin asistencia guiada
- Sin segmentación nativa, dashboards de deliverability, ni interfaz de marketing
- Se combina mejor con Customer.io, Segment, o una capa de orquestación personalizada

---

## Brevo (antes Sendinblue)

**Mejor para**: marcas con base en EU, combo email + SMS, amigable con SMB.

### Funciones clave
- Email + SMS + WhatsApp combinados en una plataforma
- Con sede en EU, nativo de GDPR
- Nivel gratuito generoso para email; SMS de pago por envío
- Flujos de automatización de marketing
- CRM incluido

### Precios
- Nivel gratuito: 300 emails/día; SMS de pago por envío
- SMS en US: ~$0.015 por mensaje
- SMS en EU: varía según el país, ~€0.04–€0.07

### Rutas de integración
- Integraciones directas: Shopify, WooCommerce, WordPress, Magento
- API + Zapier
- Servidor MCP disponible

### Cumplimiento
- GDPR + ePrivacy integrados
- A2P 10DLC para US (menos pulido que las plataformas dedicadas de US)

### A tener en cuenta
- Las funciones de SMS de US van rezagadas respecto a Klaviyo/Postscript
- Mejor si eres EU-first o ya estás en Brevo para email

---

## SimpleTexting

**Mejor para**: SMB, negocios de servicios, campañas de blast simples, bajo volumen.

### Funciones clave
- Interfaz fácil de usar
- Opt-in por palabra clave para construcción de lista de base
- Landing pages integradas para opt-in
- Automatización simple

### Precios
- Los planes empiezan ~$30/mes por 500 créditos, escalando hacia arriba
- Solo SMS de US

### Rutas de integración
- Zapier, Make, nativo en algunas apps
- API disponible pero básica

### Cumplimiento
- A2P 10DLC gestionado
- Herramientas de TCPA

### A tener en cuenta
- Profundidad de automatización limitada frente a Klaviyo/Postscript
- Mejor para casos de uso de baja complejidad y bajo volumen (gimnasios, salones, bienes raíces)

---

## Plivo

**Mejor para**: builds de SMS a la medida donde el costo por envío importa; API estilo Twilio a un precio menor.

### Funciones clave
- Competidor directo de Twilio con una superficie similar
- Powerpack para envío masivo con remitente fijo (sticky sender) entre pools de números
- A2P 10DLC gestionado dentro de la plataforma
- WhatsApp, voz disponibles en paralelo al SMS
- SDKs para los lenguajes principales

### Precios
- SMS 10DLC en US: ~$0.0055/msg (típicamente 20–30% por debajo de Twilio)
- SMS short code en US: similar + arrendamiento mensual
- MMS: ~$0.02
- Alquiler de número telefónico: ~$0.80/mes local, ~$1/mes toll-free

### Rutas de integración
- API-first (REST + SDKs)
- Sin integraciones nativas de ecommerce — las construyes tú

### Cumplimiento
- A2P 10DLC gestionado dentro de la plataforma
- La plomería de cumplimiento (STOP/HELP, horario de silencio) es tu responsabilidad — mismo modelo que Twilio

### A tener en cuenta
- Ecosistema más pequeño que Twilio (menos productos accesorios, integraciones, recursos de comunidad)
- Herramientas de WhatsApp menos maduras

---

## AudienceTap

**Mejor para**: marcas DTC que quieren herramientas creativas con IA o opt-in por código QR en el empaque como canal de adquisición principal.

> Plataforma más nueva — verifica las capacidades actuales, precios y superficie de API antes de comprometerte.

### Funciones clave
- SMS + email en una plataforma (modelo combinado similar a Klaviyo)
- Generación creativa con IA (copy de SMS, líneas de asunto, variantes de imagen)
- Opt-in por código QR en el empaque: insertos en los pedidos enviados que impulsan el crecimiento de la lista de SMS
- Integraciones con Shopify, BigCommerce, comercio headless
- A2P 10DLC gestionado dentro de la plataforma
- Resolución de identidad y segmentación

### Precios
- Escalonado por cantidad de suscriptores + volumen de envío
- Precios por envío comparables a otras plataformas DTC de SMS

### Rutas de integración
- Acceso a API en niveles Growth+
- Integraciones directas de ecommerce
- Webhooks para eventos

### Cumplimiento
- A2P 10DLC gestionado dentro de la plataforma
- Herramientas de TCPA — verifica la profundidad a escala enterprise antes de comprometerte para listas grandes

### A tener en cuenta
- Entrante más nuevo — menos clientes de referencia, menos probado en batalla a alto volumen que los incumbentes
- Algunas funciones lanzadas recientemente — confirma qué está GA vs beta antes de depender de ellas

---

## Customer.io

**Mejor para**: B2B SaaS, automatización basada en comportamiento, orquestación multicanal (email + SMS + push).

### Funciones clave
- Dispara SMS a partir de eventos de producto (registro, hito, riesgo de churn)
- Segmentación de audiencia potente
- Constructor de workflows
- Sincronización de datos en tiempo real vía API/webhooks

### Precios
- Los planes empiezan ~$150/mes, escalando con la cantidad de perfiles
- SMS vía integración con Twilio o nativo (varía)

### Rutas de integración
- API-first
- Integraciones directas con Segment, Heap, Mixpanel, etc.

### Cumplimiento
- A2P 10DLC vía Twilio si se usa la integración nativa
- Gestión granular de suscripción/consentimiento

### A tener en cuenta
- Menos adaptado a ecommerce que Klaviyo/Postscript
- Mejor para SaaS product-led o apps con seguimiento de eventos profundo

---

## Tabla de selección rápida

| Stack / Objetivo | Recomendado | Por Qué |
|--------------|------------|-----|
| Ecommerce en Shopify, ya en Klaviyo | **Klaviyo SMS** | Una plataforma, un perfil de suscriptor |
| Ecommerce en Shopify, enfoque SMS-first | **Postscript** | La integración más profunda con Shopify + funciones específicas de SMS |
| Ecommerce mid-market, quiere soporte concierge | **Attentive** | Equipo full-service + herramientas |
| Plataforma personalizada, B2B SaaS, transaccional | **Twilio** | API-first, control total |
| Build personalizado, sensible al costo | **Plivo** | ~20–30% más barato que Twilio por envío |
| DTC que quiere IA creativa u opt-in por QR en el empaque | **AudienceTap** | Enfocado en IA; el opt-in por tarjeta insertada es único |
| SMB con base en EU | **Brevo** | Nativo de GDPR, precios amigables para EU |
| SMB de servicios locales, campañas simples | **SimpleTexting** | Interfaz fácil, poco overhead |
| SaaS product-led con seguimiento de eventos | **Customer.io** | Disparadores basados en comportamiento |

---

## A2P 10DLC: qué debería manejar tu plataforma

Elijas la que elijas, confirma que tu plataforma maneja:

- [ ] Registro de marca y campaña con TCR
- [ ] Texto de mensaje de muestra alineado con lo que realmente envías
- [ ] Documentación del flujo de opt-in enviada a los carriers
- [ ] Visibilidad del trust score (y una ruta para mejorarlo)
- [ ] Throughput apropiado para el tamaño de tu lista y la frecuencia de envío
- [ ] Manejo de palabras clave STOP/HELP
- [ ] Horario de silencio según la zona horaria del destinatario
- [ ] Gestión de lista de supresión
- [ ] Retención de registros de consentimiento con timestamps

Todas las plataformas principales mencionadas arriba manejan esto. Twilio hace el trabajo de más bajo nivel y traslada más responsabilidad a ti.
