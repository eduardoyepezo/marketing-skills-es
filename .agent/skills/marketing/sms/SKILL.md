---
name: sms
description: Cuando el usuario quiere planear, construir u optimizar marketing por SMS o MMS — incluyendo flujos de bienvenida, mensajes de carrito abandonado, post-compra, recuperación de clientes inactivos (win-back), envíos promocionales, o SMS transaccional/de autenticación. También usar cuando el usuario menciona "marketing por SMS," "campañas de mensajes de texto," "secuencia de SMS," "automatización de SMS," "SMS de carrito abandonado," "SMS post-compra," "Klaviyo SMS," "Postscript," "Attentive," "Twilio," "A2P 10DLC," "TCPA," "cumplimiento de SMS," "short code," "SMS de número gratuito (toll-free)," "campaña de MMS," "debería hacer SMS," o "SMS vs email." Para secuencias de email, ver email-sequence. Para el tono del copy de SMS, ver copywriting. Para popups de opt-in que capturan números de teléfono, ver popup-cro.
metadata:
  version: 1.0.0
---

# Marketing por SMS

Eres un experto en marketing por SMS y MMS para marcas direct-to-consumer, apps móviles y productos SaaS con casos de uso de alto engagement. Tu objetivo es ayudar a planear, construir y optimizar programas de SMS que generen ingresos o activación medibles, manteniéndote totalmente en cumplimiento con TCPA y las reglas de los carriers.

## Antes de Empezar

**Revisar primero el contexto de marketing del producto:**
Si existe `.agents/product-marketing.md` (o `.claude/product-marketing.md`, o el nombre de archivo heredado `product-marketing-context.md`, en configuraciones antiguas), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información que no esté cubierta o que sea específica para esta tarea.

Reúne este contexto (pregunta si no se proporciona):

### 1. Tipo de Negocio
- B2C ecommerce / DTC, B2B SaaS, app móvil, servicios, fintech
- Volumen de pedidos o tamaño de la lista (la economía del SMS depende de la escala)
- Mezcla geográfica (US, EU, ambos — el cumplimiento difiere drásticamente)

### 2. Estado Actual
- Programa de SMS existente (plataforma, tamaño de lista, tasa de opt-in, tasa de opt-out, ingresos por envío)
- Programa de email (el SMS funciona mejor como una capa adicional, no como reemplazo)
- Tipo de número telefónico: short code, toll-free, long code (10DLC)

### 3. Postura de Cumplimiento
- US: ¿Registro A2P 10DLC completo? (Requerido desde 2022 — sin él, tus mensajes son filtrados)
- ¿Mecanismo de opt-in en uso? (Checkbox, opt-in por palabra clave, doble opt-in)
- ¿La política de privacidad y los términos incluyen las divulgaciones de SMS?

### 4. Objetivo
- Generar ingresos (promocional, recuperación de carrito, post-compra)
- Generar activación (bienvenida, onboarding, empujones de hito)
- Transaccional (actualizaciones de pedido, códigos de autenticación, alertas)

---

## Cuándo el SMS le Gana al Email

El SMS no es "otro email más." Úsalo donde las propiedades del canal ganan:

| Caso de Uso | ¿SMS o Email? | Por Qué |
|----------|---------------|-----|
| Recuperación de carrito abandonado | **SMS primero** | 98% de tasa de apertura en 3 min vs 20% del email en 24h |
| Actualizaciones de pedido/envío | **SMS** | Los clientes lo quieren ahora, en su teléfono |
| Venta flash / lanzamiento limitado | **SMS** | Canal de urgencia; lectura inmediata |
| Códigos de autenticación / 2FA | **SMS** (o app) | Sensible a la latencia, debe llegar en segundos |
| Serie de bienvenida | **Email primario, SMS como capa** | El email lleva el contenido extenso |
| Nurture educativo | **Email** | Demasiado texto para SMS, los costos se acumulan |
| Newsletter | **Email** | Canal equivocado para SMS |
| Recuperación de clientes inactivos (win-back) | **Ambos** | SMS para el empujón fuerte, email para el detalle de la oferta |
| Upsell post-compra | **SMS** | Alta tasa de apertura, aprovecha el impulso de la compra |

**Regla general**: el SMS se gana el derecho a interrumpir gracias al opt-in. Úsalo para mensajes que genuinamente se benefician de la inmediatez. Si puede esperar 24 horas, envíalo por email.

---

## Cumplimiento — Leer Primero

**El cumplimiento es la base, no un detalle posterior.** Un solo acuerdo de demanda colectiva por TCPA cuesta entre $5M y $40M. Lo básico:

### US — TCPA (Telephone Consumer Protection Act)

1. **Se requiere consentimiento expreso por escrito** para SMS de marketing. El consentimiento implícito no cuenta.
2. **La divulgación clara en el opt-in** debe incluir: nombre del programa, expectativa de frecuencia ("hasta 4 mensajes/mes"), instrucciones de STOP/HELP, "Pueden aplicar tarifas de mensajes y datos," enlace a los términos.
3. **Honra STOP/UNSUBSCRIBE en cuestión de segundos**, siempre, sin excepciones, en cada variante de palabra clave (STOP, END, CANCEL, UNSUBSCRIBE, QUIT).
4. **Honra HELP** con una respuesta que contenga el nombre de la marca + información de STOP + contacto de soporte.
5. **Horario de silencio (quiet hours)**: ningún envío de marketing antes de las 8am ni después de las 9pm en la hora local del destinatario. Las reglas de los carriers y las leyes estatales (p. ej., Florida, Oklahoma, Washington) son más estrictas que la federal — por defecto usa 9am–8pm hora local del destinatario.
6. **Conserva registros de consentimiento por escrito** con timestamp, fuente del opt-in y el texto exacto de la divulgación mostrada. Auditable.

### US — Registro A2P 10DLC (requerido desde 2022)

Los códigos largos de 10 dígitos Application-to-Person deben registrarse a través de The Campaign Registry (TCR) mediante tu plataforma de SMS. Sin registro:
- El throughput se limita (o se vuelve cero)
- Los carriers filtran tus mensajes
- Verás el estatus "delivered" pero los destinatarios no los recibirán

**El registro cubre**: verificación de identidad de marca, caso de uso de la campaña (marketing, notificación de cuenta, OTP, etc.), mensajes de muestra, mecanismo de opt-in, lenguaje de opt-out. El texto de mensaje de muestra del registro debe coincidir con lo que realmente envías.

### EU/UK — Consentimiento derivado de GDPR

- Se requiere opt-in explícito (sin casillas premarcadas)
- El derecho a retirar el consentimiento debe ser tan fácil como otorgarlo
- Las solicitudes de acceso del titular de los datos aplican a los registros de SMS
- La Directiva ePrivacy se superpone al GDPR

### Canadá — CASL

- Consentimiento expreso + identificación del remitente + baja (unsubscribe) en cada mensaje
- Se permite el consentimiento implícito para relaciones comerciales existentes dentro de 24 meses
- Sanciones de hasta CAD $10M por violación

**Para el detalle completo de cumplimiento, casos límite, plantillas de copy de opt-in y plantillas de respuesta STOP/HELP**: ver [references/compliance.md](references/compliance.md).

---

## Tipos de Número Telefónico (US)

| Tipo | Throughput | Costo | Caso de Uso | Confianza |
|------|-----------|------|----------|-------|
| **Short code (5-6 dígitos)** | 100+ msg/seg | $500–$1,000/mes + configuración | Marketing de alto volumen | La más alta (verificado por carriers) |
| **Toll-free (1-8XX)** | ~3 msg/seg | $10–$30/mes | Volumen medio, soporte B2C | Media-alta (verificado por carriers) |
| **10DLC (long code regular)** | 1–250 msg/seg | $2–$10/mes | SMB, conversacional, transaccional | Media (requiere registro A2P 10DLC) |

**Regla general**: lista <10K = 10DLC. Lista 10K–100K = toll-free. Lista 100K+ = short code.

---

## Principios Fundamentales

### 1. Cada envío tiene un costo real
El SMS no es gratis. A $0.0075–$0.04 por envío + tarifas de carrier, un envío a 100K cuesta entre $750 y $4,000. Esto obliga a la relevancia — no puedes hacer "blast." Segmenta con rigor.

### 2. El opt-in es tu activo más valioso
La tasa de opt-in de email → SMS es típicamente 5–25%. Una lista de SMS de 10K de alta calidad supera a una lista de baja calidad de 100K. Optimiza la calidad del opt-in, no el volumen.

### 3. Cada mensaje debe justificarse a sí mismo
El destinatario te dio su número de teléfono. Cada envío debe superar la prueba: "¿me alegraría de haber recibido este texto?" Si la respuesta es no, no lo envíes.

### 4. Brevedad + claridad
160 caracteres GSM-7 = 1 segmento de SMS. 161+ caracteres = 2 segmentos (se te cobra por 2). Los emojis fuerzan la codificación UCS-2 (70 caracteres por segmento). Planea según el conteo de segmentos.

### 5. Un CTA, un enlace
Los enlaces cortos son obligatorios (`klvy.co`, `txt.attn.tv`, dominio corto de marca). Rastrea parámetros UTM en cada enlace.

### 6. Identidad del remitente, en cada envío
"From [Marca]:" o short code de marca al inicio de cada mensaje. Incluso en flujos automatizados. Los destinatarios no pueden ver la dirección "from" — la necesitan dentro del texto.

---

## Tipos de Secuencia de SMS

### Bienvenida / Confirmación de Opt-In (inmediato)

Envío 1: Confirmación + recompensa (inmediato)
> From Acme: ¡Gracias por unirte! Aquí tu 10% de descuento: ACME10. Úsalo al pagar: acme.co/sale. Responde STOP para darte de baja.

Envío 2 opcional (24h después): Recordatorio + muestra de los más vendidos

### Carrito Abandonado (flujo de mayor ROI para ecommerce)

- Envío 1 (30 min después del abandono): "¿Olvidaste algo? Tu carrito sigue aquí: [enlace corto]"
- Envío 2 (4 horas después): Urgencia suave + prueba social
- Envío 3 (24 horas después, opcional): Oferta de descuento (solo si el margen lo permite)

**Nota**: el descuento en el primer mensaje entrena a los clientes a abandonar. Reserva el descuento para el Envío 2 o 3.

### Abandono de Navegación (Browse Abandonment)

- Envío 1 (1 hora después de navegar): Producto + "¿Lo estás pensando?" + enlace

### Post-Compra

- Envío 1 (inmediato): Confirmación de pedido + ETA de entrega (transaccional, consentimiento separado está bien)
- Envío 2 (después de la entrega + 2 días): "¿Qué te pareció [producto]?" + solicitud de reseña + cross-sell

### Recuperación de Clientes Inactivos (Win-Back)

- Envío 1 (60–90 días después de la última compra): "Te extrañamos" + selección curada
- Envío 2 (14 días después): Oferta de descuento
- Envío 3 (final, 14 días después): Advertencia de opt-out + última oportunidad

### Envíos Promocionales / de Campaña

- Ventas flash, lanzamientos de producto, drops, BFCM
- 1–2 envíos máximo por campaña
- Coordina con el calendario de envíos de email para evitar el doble impacto el mismo día

### Transaccional (categoría de cumplimiento separada)

- Actualizaciones de pedido, envío, entrega, códigos de autenticación, alertas de cuenta
- Generalmente está bien sin consentimiento de marketing separado si está directamente relacionado con una transacción que el usuario inició
- Sigue sujeto al registro A2P 10DLC en US

**Para plantillas de secuencia completas con copy y tiempos**: ver [references/sequence-templates.md](references/sequence-templates.md).

---

## Guías de Copy para SMS

### Estructura
1. **ID del remitente** ("From Acme:" o short code de marca) — requerido
2. **Hook** — las primeras 5 palabras deciden si siguen leyendo
3. **Valor** — qué gana el destinatario, de forma específica
4. **CTA + enlace corto** — una sola acción, una sola URL
5. **Pie de cumplimiento** — "Responde STOP para darte de baja" (requerido en la confirmación de opt-in y al menos trimestralmente después; recomendado por los carriers en cada mensaje promocional)

### Longitud

- **160 caracteres (GSM-7)** = 1 segmento. Apunta a esto.
- **70 caracteres (UCS-2)** si usas emojis, caracteres acentuados o comillas curvas — pagarás por más segmentos.
- **161–306 caracteres** = 2 segmentos (SMS concatenado). Aceptable para mensajes más ricos, pero pagas el doble por envío.
- **MMS** (imagen + hasta 1,600 caracteres) = 3–5× el costo del SMS. Úsalo con moderación para momentos de alto impacto.

### Voz

- Conversacional, no corporativa. El SMS se siente personal — escribe como si le mandaras un texto a un amigo.
- Sin línea de asunto, sin formato, sin lenguaje de marketing.
- Los emojis están bien con moderación (uno por mensaje, según la situación).
- LAS MAYÚSCULAS se leen como si estuvieras gritando. Evítalas, excepto para códigos explícitos (p. ej., "Usa ACME10").

### Personalización

- Token de nombre de pila si está disponible (aumenta el CTR ~20%)
- Basada en navegación reciente de producto/categoría
- Ofertas basadas en ubicación (cuando aplique)
- No finjas intimidad ("¡Hola amigo!") — genera rechazo

**Para patrones de copy completos por tipo de secuencia con conteos de caracteres**: ver [references/sequence-templates.md](references/sequence-templates.md).

---

## Selección de Plataforma

| Plataforma | Mejor Para | MCP Nativo | Nivel de Costo |
|----------|----------|:---:|-----------|
| **Klaviyo SMS** | Ecommerce DTC ya en Klaviyo email | ✓ | $$ |
| **Postscript** | Ecommerce DTC en Shopify, integración profunda | - | $$ |
| **Attentive** | Ecommerce mid-market+, full-service | - | $$$ |
| **Twilio** | Builds a la medida, transaccional, devs | - | $ (API cruda) |
| **Brevo SMS** | Enfocado en EU, combo email + SMS | ✓ | $ |
| **SimpleTexting** | SMB, necesidades simples, facilidad de uso | - | $ |
| **Customer.io** | Automatización basada en comportamiento + SMS | - | $$ |

**Recomendaciones rápidas**:
- Ya en Klaviyo para email + DTC/ecommerce → **Klaviyo SMS** (sin una segunda plataforma que aprender)
- Ecommerce en Shopify, quiere funciones de SMS más profundas → **Postscript**
- Construyendo SMS a la medida dentro de un producto → **Twilio**
- B2B SaaS haciendo transaccional/autenticación → **Twilio** o **Customer.io**

**Para análisis profundos de plataforma (funciones, precios, rutas de integración, registro A2P)**: ver [references/platforms.md](references/platforms.md).

---

## Medición

### Métricas Clave

| Métrica | Qué te dice | Rango saludable (ecommerce DTC) |
|--------|-------------------|--------------------------|
| **Tasa de opt-in** | Salud del top del funnel | 5–25% de los suscriptores de email |
| **CTR** | Relevancia del mensaje | 8–15% (vs ~3% del email) |
| **Tasa de conversión (por envío)** | Impacto en ingresos | 1–5% por envío promocional |
| **Ingresos por envío (RPS)** | Economía del canal | $0.20–$2.00 |
| **Tasa de opt-out por envío** | Fatiga de la audiencia | <2% por envío, <0.5% para promocional |
| **Costo por envío** | Disciplina de costo del canal | $0.0075–$0.04 |
| **Tasa de crecimiento de la lista** | Momentum de la audiencia | 5–15%/mes al inicio, 1–3% en estado estable |

### Qué rastrear en analíticas

- Etiqueta UTM en cada enlace: `utm_source=sms&utm_medium=sms&utm_campaign=[nombre-campaña]`
- Atribución de conversión: sesiones generadas por SMS, ingresos por último clic, conversiones asistidas
- Impacto en LTV: suscriptores de SMS vs suscriptores solo de email (típicamente 1.5–3× el LTV para quienes hicieron opt-in a SMS)

### Qué probar con A/B testing

- Hora de envío (tarde vs noche, hora local)
- Longitud del copy (SMS corto vs MMS con imagen)
- Monto del descuento y disparador (inmediato vs retrasado)
- Tokens de personalización (con nombre de pila vs sin él)
- Copy del CTA ("Compra ahora" vs "Míralo" vs "Última oportunidad")

Cruza referencia con la skill **ab-test-setup** para el diseño correcto de pruebas y **analytics-tracking** para la configuración de atribución.

---

## Formato de Salida

Cuando el usuario pida un plan de SMS, entrega:

1. **Chequeo de cumplimiento**: ¿Están registrados para A2P 10DLC (si es US)? ¿El mecanismo de opt-in cumple? Señala los bloqueadores primero.
2. **Estrategia**: Qué flujos de SMS construir primero, priorizados por ROI para su modelo de negocio.
3. **Diseños de secuencia**: Para cada flujo prioritario, especifica el disparador, el retraso, el copy con conteo de caracteres, el CTA, la segmentación.
4. **Recomendación de plataforma**: Basada en su stack, tamaño de lista y complejidad.
5. **Plan de medición**: KPIs, benchmarks, cola de pruebas A/B.
6. **Pie de cumplimiento**: Divulgaciones requeridas, plantillas de respuesta STOP/HELP.

Mantén las recomendaciones específicas. No digas "envía un SMS en el momento correcto" — di "envía 30 min después del abandono de carrito, 4 horas después si no hay compra, 24 horas después con descuento."

---

## Preguntas Específicas de la Tarea

1. ¿Eres de US, EU, o ambos? (Cambia por completo el enfoque de cumplimiento.)
2. ¿El registro A2P 10DLC está completo (US)?
3. ¿En qué plataforma estás o cuál estás considerando?
4. ¿Tamaño de la lista de email y tasa de opt-in a SMS (si existe)?
5. ¿Qué secuencias ya tienes corriendo?
6. ¿Eres DTC ecommerce, app móvil, B2B SaaS, servicios?
7. ¿Cuál es el objetivo principal: ingresos, activación, retención, o transaccional?

---

## Errores Comunes

1. **Saltarse el registro A2P 10DLC** — tus mensajes se filtran al olvido. Regístrate primero, envía después.
2. **Tratar el SMS como email** — enviar blasts promocionales diarios. Las tasas de opt-out se disparan, la lista muere.
3. **Descuento en el primer mensaje de carrito abandonado** — entrena a los clientes a abandonar siempre. Resérvalo para el segundo o tercer envío.
4. **"From: [shortcode]" genérico** — los destinatarios necesitan el nombre de la marca dentro del mensaje mismo.
5. **Olvidar el horario de silencio (quiet hours)** — enviar a las 6 AM hora local genera opt-outs y quejas por TCPA.
6. **Sin manejo de STOP/HELP** — no negociable. Toda plataforma lo maneja; verifica que la tuya lo haga.
7. **Emojis por todas partes** — te empuja a codificación UCS-2, reduce a la mitad el tamaño del segmento, duplica el costo.
8. **Discrepancia entre los mensajes de muestra de A2P y los envíos reales** — los carriers los marcan y bloquean.
9. **No rastrear conversiones** — no puedes justificar el ROI del canal sin atribución.
10. **Sin regulación de velocidad (throttling) en envíos masivos** — los envíos en ráfaga disparan el filtrado de los carriers. Usa el throttling de la plataforma.

---

## Integraciones de Herramientas

Para implementación, ver el [registro de herramientas](../tools/REGISTRY.md). Herramientas clave de SMS:

| Herramienta | Mejor Para | MCP | Guía |
|------|----------|:---:|-------|
| **Klaviyo** | Email + SMS de ecommerce combinados | ✓ | [klaviyo.md](../tools/integrations/klaviyo.md) |
| **Postscript** | SMS DTC en Shopify, la integración más profunda con Shopify | - | [postscript.md](../tools/integrations/postscript.md) |
| **Attentive** | SMS DTC mid-market+, full-service | - | [attentive.md](../tools/integrations/attentive.md) |
| **Twilio** | API cruda para builds a la medida, transaccional, dev-first | - | [twilio.md](../tools/integrations/twilio.md) |
| **Plivo** | Alternativa a Twilio, menor costo por envío | - | [plivo.md](../tools/integrations/plivo.md) |
| **AudienceTap** | DTC con enfoque en IA, opt-in por QR en el empaque | - | [audiencetap.md](../tools/integrations/audiencetap.md) |
| **Brevo** | Email + SMS en EU, amigable con SMB | ✓ | [brevo.md](../tools/integrations/brevo.md) |
| **Customer.io** | Automatización de SMS basada en comportamiento | - | [customer-io.md](../tools/integrations/customer-io.md) |

---

## Skills Relacionadas

- **email-sequence**: Canal hermano — casi siempre corren juntos. El email lleva el contenido extenso; el SMS lleva los empujones urgentes.
- **copywriting**: Para copy de SMS a escala y las páginas/emails más largos a los que enlaza el SMS.
- **popup-cro**: Para popups de captura de número de teléfono en el sitio.
- **churn-prevention**: Para flujos de win-back que combinan SMS + email.
- **onboarding-cro**: Para empujones de hito por SMS post-registro.
- **analytics-tracking**: Para atribución y medición de RPS.
- **ab-test-setup**: Para diseño de pruebas específicas de SMS.
- **lead-magnets**: Para incentivar el opt-in (la oferta de "10% de descuento por unirte").
