# Referencia de Cumplimiento de Prospección

Las restricciones legales y de ToS de plataforma que aplican a la construcción de listas de prospectos. Leer primero, en cada engagement.

> Guía operacional, no asesoría legal. Para programas de alto volumen o programas que tocan residentes de la UE/Reino Unido, valida tu configuración con un abogado de privacidad.

---

## Estados Unidos — CAN-SPAM (downstream)

CAN-SPAM regula el **envío** del cold email, no la construcción de la lista. Pero la construcción de la lista importa porque:

- Debes poder identificar la fuente de cada dirección de email que contactas (requerido si te lo cuestionan)
- Las reglas de la línea "from" y del contenido del email aplican en el momento del envío — pero no puedes mentir sobre cómo obtuviste el contacto
- Las solicitudes de opt-out deben honrarse dentro de 10 días hábiles y quedar registradas

**Específicamente para prospección**: captura y retén la URL fuente + fecha de cada contacto que agregues a una lista. CAN-SPAM no lo requiere explícitamente, pero defender tus prácticas de envío sí lo necesita.

---

## UE / Reino Unido — GDPR

El marco aplicable más estricto. Se activa cuando:

- Tu prospecto reside en la UE/Reino Unido
- Estás procesando datos personales (cualquier información identificable, incluyendo emails de negocio vinculados a una persona nombrada)

### Bases legales para outreach B2B en frío

Tienes tres opciones creíbles:

1. **Interés legítimo** (la más común para B2B). Requiere:
   - El contacto está en un rol de negocio con probabilidad de estar interesado en tu oferta
   - Los datos se recolectaron de una fuente pública, de contexto de negocio
   - Provees un opt-out claro
   - Puedes articular por escrito la prueba de interés legítimo

2. **Consentimiento** — típicamente no es viable para outreach en frío (no tienes consentimiento antes del primer contacto)

3. **Relación de cliente existente** — solo aplica a clientes actuales, no a prospectos

### Qué debes hacer

- Capturar **fuente + fecha + base legal** para cada contacto
- Honrar las solicitudes de acceso del titular de los datos (DSARs) — debes poder divulgar, corregir, o eliminar bajo solicitud
- Incluir un aviso de privacidad / opt-out en el primer outreach
- No almacenar datos personales más tiempo del necesario para el interés legítimo

### Qué descalifica una lista

- Datos de LinkedIn obtenidos por scraping masivo — violación explícita de ToS + riesgo de GDPR
- Direcciones de email compradas a un list broker sin procedencia de fuente
- Emails adivinados tipo "cualquiera @ este dominio" enviados sin verificación (multiplica el riesgo + los rebotes)

---

## Canadá — CASL

Más estricta que CAN-SPAM. El outreach B2B en frío requiere:

- **Consentimiento expreso** (opt-in explícito) — típicamente no está presente en la prospección en frío
- **O consentimiento implícito** — relación de negocio existente dentro de los últimos 24 meses, O dirección de negocio publicada públicamente en el sitio propio de la empresa con el propósito de recibir dichas comunicaciones

**Implicación práctica para prospectos canadienses**: apoyarse en la excepción de dirección públicamente publicada es la base de prospección en frío más defendible en Canadá. Debes incluir identificación del remitente, dirección postal, y un mecanismo de baja en cada mensaje.

---

## Términos de Servicio de Plataformas

### LinkedIn

- **Sales Navigator** como herramienta de investigación: está bien
- **Scraping de LinkedIn a cualquier escala**: violación explícita de ToS. Las cuentas baneadas son permanentes. No lo hagas.
- **Apollo, Clay, y ZoomInfo** afirman tener datos de superposición con LinkedIn a través de varios canales legítimos — verifica sus fuentes de datos antes de asumir cumplimiento
- **InMail y Solicitudes de Conexión**: gobernadas por las propias reglas de mensajería de LinkedIn, no por CAN-SPAM/GDPR (porque son internas de LinkedIn)

### Google Maps

- El ToS prohíbe la extracción masiva o convertir los datos de Maps en producto
- La investigación asistida por navegador como ayuda de discovery: aceptable
- Almacenar Place IDs o datos estructurados grandes de Maps en tu CRM: prohibición explícita de ToS
- Usa Maps para **encontrar** negocios locales, luego verifica cruzadamente desde el sitio propio del negocio para los datos que retienes

### Apollo / ZoomInfo / Clearbit

- Todos tienen su propio ToS que limita la reventa, el compartir downstream, y los casos de uso
- Lee tu contrato — típicamente puedes usar los datos para tu propio outreach pero no convertirlos en producto
- No compartas extractos públicamente (ej. en un leaderboard, en un reporte público)

### Crunchbase

- El nivel gratuito es de solo lectura para uso personal
- El nivel pago permite un uso más amplio dentro del alcance contractual
- El acceso a API requiere nivel Pro+ pago

---

## Anti-Patrones (No Hagas Esto)

1. **Scraping masivo de LinkedIn / Google Maps / Yelp**. La investigación asistida por navegador está bien; los scrapers automatizados apuntados a estas plataformas no lo están. **Firecrawl y Browserbase están bien para el sitio web propio de un prospecto individual** (la URL que encontraste mediante discovery manual) — no para las plataformas que alojan a los prospectos.
2. **Comprar listas de vendedores al azar** sin procedencia de fuente. Heredas su exposición legal.
3. **Adivinar emails y enviarlos sin verificar**. Las tasas de rebote sobre el 2% destruyen la reputación del remitente; legalmente, no puedes reclamar una base de "interés legítimo" para un email que fabricaste.
4. **Recolectar direcciones de email personales** (Gmail, Outlook personal, etc.) de perfiles públicos. Las direcciones personales elevan significativamente el riesgo de GDPR.
5. **Almacenar datos que no necesitas**. Minimiza la retención. No mantengas listas de prospectos para siempre — el derecho de eliminación de GDPR aplica.
6. **Saltarse la documentación de base legal**. Si te lo cuestionan, necesitas poder demostrar tu trabajo. Captura la URL fuente + fecha de recolección de cada contacto.
7. **Revender listas de prospectos**. Puede que no tengas el derecho de compartirlas downstream. Lee los contratos de tus proveedores de datos.
8. **Bypass de CAPTCHA / bypass de muro de login**. Incluso si es técnicamente posible, esto señala comportamiento de bot y viola prácticamente todos los ToS.

---

## Checklist Rápido de Auditoría

Antes de entregar una lista al usuario (o downstream a cold-email):

- [ ] Cada contacto tiene una URL fuente + fecha de recolección
- [ ] Ningún contacto proviene de datos de LinkedIn obtenidos por scraping
- [ ] No se retienen Place IDs de Google Maps ni datos estructurados grandes de Maps
- [ ] Base legal documentada (prueba de interés legítimo para B2B, o la alternativa relevante)
- [ ] Direcciones de email validadas (chequeo de entregabilidad antes del outreach)
- [ ] Direcciones personales (Gmail, etc.) marcadas o excluidas
- [ ] Los contratos del proveedor de la fuente permiten el caso de uso previsto
- [ ] Plan de retención documentado (cuándo eliminar)
- [ ] El primer outreach incluirá baja + aviso de privacidad (preocupación downstream para la skill de cold-email, pero menciónalo ahora)
