# Referencia de Cumplimiento de SMS

Referencia integral de cumplimiento para marketing por SMS en las principales jurisdicciones, plantillas de copy de opt-in y plantillas de respuesta STOP/HELP.

> Esta es orientación operativa, no asesoría legal. Para programas de alto volumen (50K+ suscriptores) o cualquier programa con ingresos no triviales, haz revisar tu configuración de cumplimiento por un abogado con experiencia en TCPA.

---

## Estados Unidos — TCPA

### Qué es

La Telephone Consumer Protection Act (1991, enmendada) regula las llamadas y textos de marketing. La FCC la hace cumplir; los demandantes privados demandan bajo esta ley. Daños estatutarios: $500–$1,500 **por mensaje**. Las demandas colectivas fácilmente alcanzan 7 u 8 cifras.

### Niveles de consentimiento

| Tipo | Qué cubre | Cómo capturarlo |
|------|---------------|----------------|
| **Consentimiento expreso por escrito** | SMS de marketing (ventas, promociones, ofertas) | Checkbox + lenguaje de divulgación claro, capturado electrónicamente con timestamp |
| **Consentimiento expreso (no escrito)** | Informativo/transaccional (entrega, alertas de cuenta) | Número de teléfono proporcionado durante la transacción con conocimiento de que se usará para enviar textos |
| **Relación comercial establecida** | NO es suficiente para SMS de marketing | No aplica |

### Requisitos del consentimiento expreso por escrito

El flujo de opt-in debe capturar todo lo siguiente:

1. El destinatario aceptó recibir SMS de marketing de tu marca
2. El destinatario entiende que el consentimiento no es una condición de compra
3. La divulgación mostró la expectativa de frecuencia, el aviso de tarifas de mensajes y datos, las instrucciones de STOP/HELP, el enlace a los términos
4. El acuerdo quedó registrado electrónicamente con timestamp

### Plantilla de divulgación de opt-in (conforme)

```
Al registrarte por texto, aceptas recibir mensajes de texto de marketing
recurrentes automatizados y personalizados (p. ej., recordatorios de carrito)
de [Marca] al número celular usado al registrarte. El consentimiento no es
una condición de ninguna compra. Responde HELP para ayuda y STOP para
cancelar. La frecuencia de mensajes varía. Pueden aplicar tarifas de
mensajes y datos. Consulta [Términos](enlace) y [Privacidad](enlace).
```

Coloca esto **directamente adyacente** al campo del número de teléfono y al botón de envío. No lo escondas en un pie de página.

### Horario de silencio (quiet hours)

- **Federal**: 8am–9pm en la zona horaria local del destinatario
- **Estados más estrictos**: Florida (8am–8pm), Oklahoma (8am–8pm), Washington (8am–8pm)
- **Recomendado por los carriers**: 9am–8pm hora local del destinatario
- **Valor por defecto práctico**: 9am–8pm hora local del destinatario, por seguridad

La zona horaria se determina por el código de área, pero los códigos de área mienten (la gente se muda). Las plataformas principales (Klaviyo, Postscript, Attentive) manejan esto automáticamente; verifica que la tuya también lo haga.

### Manejo de STOP/HELP

**Variantes de STOP que debes honrar**: STOP, END, CANCEL, UNSUBSCRIBE, QUIT, STOPALL, OPTOUT

**Respuesta a STOP** (después de recibir STOP):
```
Has sido dado de baja de las alertas de [Marca]. No se te enviarán más mensajes. Responde HELP para ayuda.
```

**Variantes de HELP**: HELP, INFO

**Respuesta a HELP**:
```
Alertas de [Marca]: para ayuda, visita [URL] o escribe a [support@brand.com]. Pueden aplicar tarifas de mensajes y datos. Responde STOP para cancelar.
```

**Reglas críticas**:
- Honra STOP **en cuestión de segundos**, siempre, en cada variante de palabra clave
- No exijas al destinatario iniciar sesión o visitar un sitio web para darse de baja
- Se permite una sola confirmación de STOP; no envíes mensajes adicionales después
- Las respuestas de HELP no cuentan como mensajes de marketing y no están sujetas al horario de silencio

### Lenguaje de pie de página conforme a TCPA por tipo de secuencia

- **Confirmación de opt-in**: "Responde HELP para ayuda, STOP para cancelar. Pueden aplicar tarifas de mensajes y datos." — requerido
- **Promocional recurrente**: "Responde STOP para darte de baja" — requerido como mínimo trimestralmente; recomendado por los carriers en cada envío
- **Transaccional**: No requerido por TCPA pero los carriers lo esperan; inclúyelo por seguridad

---

## Estados Unidos — A2P 10DLC

### Qué es

El registro Application-to-Person 10-Digit Long Code, gestionado por The Campaign Registry (TCR). Requerido para negocios que envían SMS a través de números 10DLC (long codes regulares) desde 2022. Los carriers (T-Mobile, AT&T, Verizon) hacen cumplir esto; el tráfico no registrado se limita o se bloquea.

### Componentes del registro

1. **Registro de marca**
   - Nombre de la entidad legal, EIN, tipo de negocio
   - Se asigna un trust score (Standard o Verified)
   - Mayor confianza = mejor throughput, menores tarifas

2. **Registro de campaña** (uno por caso de uso)
   - Caso de uso: Marketing, Account Notification, Customer Care, Public Service, Higher Education, Polling and Voting, 2FA, Delivery Notification, etc.
   - Texto de mensaje de muestra (debe coincidir con lo que realmente envías)
   - Descripción y captura de pantalla del flujo de opt-in
   - Lenguaje de opt-out
   - Lenguaje del mensaje de ayuda
   - Estimación de volumen

3. **Asignación de número telefónico** a las campañas

### Niveles de throughput (varía según carrier y trust score)

| Trust score + caso de uso | Throughput |
|------------------------|-----------|
| Marca verificada, marketing | 75–100+ msg/seg |
| Marca standard, marketing | 4–10 msg/seg |
| No registrado | 0.1 msg/seg o bloqueado |

### Rechazos comunes

- El texto del mensaje de muestra no coincide con los envíos reales
- La captura de pantalla del flujo de opt-in no muestra el lenguaje de divulgación requerido
- Contenido "SHAFT" (Sex, Hate, Alcohol, Firearms, Tobacco) sin un caso de uso explícito
- Descripciones de campaña genéricas o vagas

**Tiempo de proceso**: 1–7 días hábiles. Planifica esto en tus cronogramas de lanzamiento.

---

## EU / UK — GDPR + Directiva ePrivacy

### Requisitos de consentimiento

- **Opt-in explícito**: acción afirmativa clara (sin casillas premarcadas)
- **Específico**: el opt-in debe ser para SMS de marketing específicamente, separado de los términos de servicio genéricos
- **Informado**: el titular de los datos debe saber quién los procesa y por qué
- **Libremente otorgado**: no puede estar condicionado al acceso al servicio

### Disposiciones obligatorias

- Identidad del remitente en cada mensaje
- Opt-out fácil en cada mensaje
- Derecho de acceso a los datos (DSARs)
- Derecho al borrado
- Registros de consentimiento conservados durante la duración del procesamiento + el plazo de prescripción

### Exposición a sanciones

Multas de GDPR de hasta €20M o 4% de los ingresos globales, lo que sea mayor.

---

## Canadá — CASL

### Consentimiento

- **Consentimiento expreso**: opt-in explícito (mismo estándar que el consentimiento expreso por escrito de TCPA en US)
- **Consentimiento implícito**: relación comercial existente dentro de 24 meses — uso limitado, expira

### Cada mensaje debe incluir

- Identificación del remitente (nombre legal + cualquier nombre operativo)
- Dirección postal
- Contacto de teléfono, email o sitio web
- Mecanismo de baja que funcione dentro de 10 días hábiles

### Exposición a sanciones

Hasta CAD $10M por violación. Aplicado por la CRTC.

---

## Australia — Spam Act 2003

- Consentimiento expreso o inferido (el inferido tiene aplicación limitada)
- Se requiere ID del remitente
- Se requiere baja funcional
- Aplicado por la ACMA

---

## Programas multi-jurisdiccionales

Si envías a través de US + EU + Canadá simultáneamente:

- Por defecto, aplica el estándar **más estricto** entre todas las jurisdicciones (consentimiento expreso por escrito de TCPA en US + opt-in explícito de GDPR)
- Rastrea la jurisdicción del consentimiento por suscriptor
- Por defecto, el horario de silencio debe ser 9am–8pm hora local del destinatario
- Incluye todos los identificadores requeridos en cada mensaje

---

## Checklist de cumplimiento listo para auditoría

- [ ] Registro A2P 10DLC completo (US, si aplica)
- [ ] El flujo de opt-in incluye todas las divulgaciones requeridas, adyacente al campo de teléfono
- [ ] El texto de divulgación coincide con los mensajes de muestra registrados en A2P
- [ ] El evento de opt-in captura: timestamp, IP, URL de la página, texto exacto de la divulgación mostrada
- [ ] Las palabras clave STOP/HELP se honran en todas sus variantes
- [ ] El horario de silencio se aplica a nivel de plataforma (hora local del destinatario)
- [ ] La política de privacidad incluye una sección de SMS
- [ ] Los términos de servicio incluyen los términos de SMS
- [ ] Los registros de consentimiento se conservan según la ley aplicable (típicamente 4+ años en US, más en EU)
- [ ] Existe un proceso para manejar DSARs (EU) y revocación de consentimiento
- [ ] Identidad del remitente en cada mensaje
- [ ] Pie de cumplimiento en cada mensaje promocional (recomendado) o como mínimo trimestralmente (requerido)
- [ ] Se prueba STOP/HELP desde un número de teléfono real trimestralmente para verificar que siga funcionando
