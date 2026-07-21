# Fuentes de Datos de Prospección

Guía de selección de herramientas para prospección en las tres ramas.

---

## Selección de herramientas por objetivo

| Objetivo | Herramientas primarias | Notas |
|------|--------------|-------|
| **Construir lista firmográfica inicial (B2B / SaaS)** | Apollo, ZoomInfo, Clay | Apollo para amplitud, ZoomInfo para enterprise + intención, Clay para flujos personalizados |
| **Mapeo de tomadores de decisiones** | LinkedIn Sales Navigator (manual), Apollo, ZoomInfo | Sales Nav es el estándar de oro. Nunca hacer scraping masivo. |
| **Calificación de tech stack (SaaS)** | BuiltWith, Wappalyzer | BuiltWith tiene mayor cobertura + planes pagos para volumen; Wappalyzer es más liviano + gratis para uso pequeño |
| **Señales de financiamiento (SaaS)** | Crunchbase, Pitchbook | El nivel gratuito de Crunchbase es suficiente para señales tempranas; Pitchbook para datos de inversionistas más profundos |
| **Descubrimiento de patrones de email** | Hunter, Snov, Apollo | Adivinar patrones — seguido de verificación |
| **Verificación de entregabilidad de email** | Truelist, Hunter, NeverBounce, ZeroBounce | Siempre verificar antes de agregar a listas de outreach |
| **Identificación de visitantes (intención cálida)** | RB2B, Clearbit Reveal | Tráfico anónimo → identificación de empresa |
| **Datos de intención** | ZoomInfo Intent, 6sense, Bombora | Señales pre-calentadas; precios de mid-market en adelante |
| **Monitoreo de eventos disparadores** | Google Alerts, Feedly, alertas de LinkedIn Sales Nav | Las opciones gratuitas son suficientes para la mayoría de casos |
| **Descubrimiento de negocios locales** | Google Maps (manual), Yelp, páginas de Facebook | Asistido por navegador, no extraído masivamente |

---

## Apollo

**Úsalo para**: Datos firmográficos + de contacto B2B / SaaS en general. Mejor punto de partida si aún no tienes una lista.

**Fortalezas**:
- Base de datos grande (>200M contactos, >60M empresas)
- UI de filtrado sólida (industria, tamaño, tecnologías, señales)
- Buscador integrado de email + LinkedIn
- Planes de pago por uso y por niveles

**Ten cuidado con**:
- La frescura de los datos varía — reverificar antes de puntuar como "Hot"
- Precisión de email ~60–80% — siempre validar
- Aplican límites de exportación masiva

**Integración**: ver [apollo.md](../../../tools/integrations/apollo.md)

---

## Clay

**Úsalo para**: Enriquecimiento multi-fuente, búsquedas en cascada (waterfall), lógica de puntuación personalizada. Cuando la calidad de la lista importa más que el tamaño de la lista.

**Fortalezas**:
- Lógica de waterfall: probar Apollo primero → fallback a ZoomInfo → fallback a Clearbit
- Más de 100 integraciones con proveedores de datos
- Enriquecimiento impulsado por IA (extracción con LLM desde URLs)
- Columnas personalizadas + fórmulas de puntuación
- Servidor MCP nativo

**Ten cuidado con**:
- El precio por crédito puede dispararse en listas grandes
- Sobrecarga de complejidad — es fácil sobre-diseñar los flujos

**Integración**: ver [clay.md](../../../tools/integrations/clay.md)

---

## ZoomInfo

**Úsalo para**: B2B empresarial + datos de intención. Perfiles de comprador de mid-market en adelante.

**Fortalezas**:
- Profundidad firmográfica de nivel empresarial
- Señales de intención (empresas buscando temas relevantes a tu oferta)
- Lo mejor de su clase para ventas B2B >$50K ACV
- Servidor MCP nativo

**Ten cuidado con**:
- Costoso ($15K+/año como punto de entrada)
- Excesivo para prospección SMB
- Típicamente atado a contratos multi-año

**Integración**: ver [zoominfo.md](../../../tools/integrations/zoominfo.md)

---

## Clearbit

**Úsalo para**: Enriquecimiento de email → empresa, identificación de visitantes anónimos (Clearbit Reveal).

**Fortalezas**:
- Enriquecimiento de empresa sólido (industria, tamaño, financiamiento, tech stack)
- Búsqueda de email por dominio
- Reveal: identificar visitantes anónimos del sitio a nivel de empresa
- API-first

**Ten cuidado con**:
- Adquisición por HubSpot (2023) — ahora empaquetado en HubSpot Breeze Intelligence
- La API standalone sigue disponible pero el precio/acceso depende del nivel

**Integración**: ver [clearbit.md](../../../tools/integrations/clearbit.md)

---

## Hunter / Snov

**Úsalo para**: Descubrimiento de patrones de email + verificación liviana en listas pequeñas.

**Fortalezas de Hunter**:
- Descubrimiento de email basado en dominio
- Verificación de entregabilidad integrada
- Nivel gratuito razonable para uso ocasional

**Fortalezas de Snov**:
- Buscador de email + campañas drip (se superpone con herramientas de outreach)
- Verificación masiva
- Más barato que Hunter a escala

**Ten cuidado con**:
- Ambas son herramientas de adivinar patrones — la precisión depende de que el patrón de email de la empresa objetivo sea inferible
- Siempre pasar los resultados por un validador dedicado (Truelist o similar) antes del outreach

**Integraciones**: ver [hunter.md](../../../tools/integrations/hunter.md), [snov.md](../../../tools/integrations/snov.md)

---

## Truelist

**Úsalo para**: Validación de entregabilidad de email antes de agregar contactos a listas de outreach. Paso de seguridad crítico.

**Fortalezas**:
- Verificación síncrona de un solo email (`/api/v1/verify_inline`) + masiva asíncrona (`/api/v1/verify`)
- Devuelve `email_state` (ok / email_invalid / risky / unknown / accept_all) + `email_sub_state` (email_ok / is_disposable / is_role / unknown_error / failed_smtp_check) + sugerencias de corrección de errores tipográficos
- Detecta dominios catch-all, cuentas de rol, trampas de spam, proveedores desechables
- Servidor MCP oficial para flujos de trabajo dirigidos por agentes (Claude, Cursor, VS Code)
- SDKs oficiales en 7 lenguajes + integraciones de framework (Django, Laravel, Next.js, Rails, React, Svelte, Vue, WordPress)
- Integraciones nativas con Mailchimp, Klaviyo, HubSpot, Zapier, Make, n8n, Clay, Salesforce, y más
- Precio por email

**Por qué esto importa**: La reputación del cold email se hunde cuando las tasas de rebote superan el 2%. Validar antes de enviar no es negociable. Los datos de Apollo/ZoomInfo/Hunter suelen tener una precisión de 60–80% — Truelist atrapa el resto.

**Integración**: ver [truelist.md](../../../tools/integrations/truelist.md)

---

## LinkedIn Sales Navigator

**Úsalo para**: Descubrimiento manual de tomadores de decisiones. El estándar de oro para prospección B2B / SaaS pero solo cuando se usa como herramienta de investigación.

**Fortalezas**:
- Los datos de tomadores de decisiones más precisos de la industria
- Cambios de trabajo, posts, señales en tiempo real
- Listas de leads, alertas, búsquedas guardadas
- Créditos de InMail (canal separado del cold email)

**Reglas estrictas**:
- **Nunca hacer scraping masivo**. LinkedIn banea agresivamente a los scrapers. El riesgo de baneo de cuenta es real y permanente.
- Usa Sales Nav como interfaz de investigación — abre perfiles, lee, toma notas, captura datos clave manualmente.
- Apollo y otras herramientas afirman tener datos de LinkedIn vía partnerships / mirroring público — verifica la legitimidad de la fuente antes de asumir cumplimiento.

**Integración**: sin acceso MCP o API a nivel de consumidor. Solo investigación manual.

---

## BuiltWith / Wappalyzer

**Úsalo para**: Calificación de tech stack (rama SaaS).

**BuiltWith**:
- Más de 50K tecnologías rastreadas
- API + búsquedas masivas (pago)
- Datos históricos (cuándo cambió el stack)

**Wappalyzer**:
- Extensión de navegador gratuita; API pagada
- Cobertura más liviana que BuiltWith
- Más rápido para búsquedas puntuales

Verifica cruzadamente ambas para señales de tech stack de alta confianza.

---

## Crunchbase

**Úsalo para**: Señales de financiamiento (rama SaaS).

**Fortalezas**:
- El nivel gratuito muestra eventos de financiamiento recientes
- Pago (Pro / Enterprise) desbloquea alertas e historial profundo
- Acceso a API para usuarios pagos

**Ten cuidado con**:
- La cobertura es mejor para empresas respaldadas por VC; los bootstrapped y negocios pequeños están sub-representados
- Datos auto-reportados — verifica los montos de financiamiento de forma independiente

---

## GitHub (stargazers / forks / watchers)

**Úsalo para**: Prospección de intención de desarrollador. Especialmente poderoso para SaaS de herramientas para devs — los stargazers de repos de competidores o que definen la categoría son señal de intención de mercado.

**Fortalezas**:
- API pública, sin preocupaciones de scraping
- Alta calidad de señal (un repo con estrella = interés explícito)
- Los forks son una señal aún más fuerte (intención de modificar, no solo guardar)
- El CLI incluido `github-prospects.js` maneja paginación + enriquecimiento + salida CSV
- Gratis con límite de tasa de 5,000 req/hr autenticado

**Ten cuidado con**:
- Solo ~5–20% de los usuarios publican email — combinar con Apollo/Clay/Hunter para enriquecimiento
- Los repos muy populares (100K+ estrellas) son mayormente ruido; repos más pequeños y dirigidos (5K–25K) dan mejor densidad de señal
- La mayoría de los prospectos son individuos, no contactos de empresa directamente — hay que averiguar su empresa desde el campo `company` o LinkedIn

**Integración**: ver [github.md](../../../tools/integrations/github.md)

---

## Firecrawl / Browserbase (investigación de sitio único)

**Úsalo para**: Extraer contenido programáticamente del **sitio web propio de un prospecto** que ya encontraste vía discovery en plataformas como Google Maps, Yelp, o LinkedIn. No para hacer scraping de esas plataformas en sí.

### Firecrawl

- **Mejor para**: "Solo dame la página como markdown" — chequeos de estado de sitio web de Local SMB, extracción de página about/team de empresa B2B, extracción de campos estructurados
- **Fortalezas**: Bajo overhead, devuelve markdown limpio listo para LLM, maneja la mayoría de sitios renderizados con JS, tiene servidor MCP
- **API + MCP + SDKs**: Node, Python, Go, Rust

### Browserbase

- **Mejor para**: Cuando necesitas Chromium real — páginas pesadas en JS, diálogos de consentimiento de cookies, envío de formularios para llegar a una página de contacto, estado de sesión
- **Fortalezas**: Control total del navegador vía Playwright/Puppeteer; Stagehand ofrece extracción en lenguaje natural amigable con IA; grabaciones de sesión para debugging
- **API + MCP (Stagehand) + SDKs**: Node, Python

### Línea de cumplimiento crítica

Ambas herramientas técnicamente pueden apuntar a cualquier URL. La regla estricta:

- ✓ **OK**: extraer contenido del sitio web propio de un solo negocio (`joescoffeeshop.com`) que encontraste mediante discovery manual
- ✗ **NO OK**: apuntarlas a `google.com/maps`, resultados de búsqueda de LinkedIn, listados de Yelp, o cualquier plataforma cuyos ToS prohíban la extracción masiva

El discovery ocurre en plataformas (investigación manual asistida por navegador). La extracción ocurre en sitios de negocios públicos individuales.

**Integraciones**: ver [firecrawl.md](../../../tools/integrations/firecrawl.md), [browserbase.md](../../../tools/integrations/browserbase.md)

---

## RB2B / Clearbit Reveal

**Úsalo para**: Identificar visitantes anónimos del sitio como señales de intención cálida.

**Fortalezas**:
- Identificación de visitante → empresa basada en pixel
- Alta intención: llegaron a tu sitio, ya están en modo de investigación
- Alertas de Slack / email en visitas clave

**Ten cuidado con**:
- Consideraciones de privacidad/GDPR — verifica las divulgaciones de tu política de privacidad
- La identificación a nivel de persona genera más preocupaciones que a nivel de empresa

**Integración**: ver [rb2b.md](../../../tools/integrations/rb2b.md)

---

## Alternativas gratuitas / solo navegador

Cuando el usuario no tiene herramientas pagas, apóyate en:

- **Google Search** — búsquedas exactas de nombre de negocio + ciudad + rol
- **LinkedIn** (manual, sin scraping) — páginas de empresa, búsqueda de empleados
- **Nivel gratuito de Crunchbase** — eventos de financiamiento
- **Extensión de navegador Wappalyzer** — tech stack de un vistazo
- **Nivel gratuito de Hunter.io** — 25 búsquedas/mes
- **Google Maps** — para discovery de Local SMB
- **Sitios web de negocios + páginas About** — fuente primaria para cualquier afirmación
- **Sitios de noticias + comunicados de prensa** — monitoreo de eventos disparadores vía Google Alerts

Más lento que los flujos con herramientas, pero produce listas más pequeñas de alta calidad si el usuario está dispuesto a hacer el trabajo.

---

## Recomendaciones de secuenciación

Un flujo de prospección full-stack típico:

1. **Definir el ICP** desde el contexto de product-marketing (sin herramientas necesarias)
2. **Lista inicial** desde Apollo o ZoomInfo (filtro firmográfico)
3. **Enriquecer** con Clay (waterfall: tech stack, financiamiento, eventos disparadores)
4. **Mapeo de tomadores de decisiones** en LinkedIn Sales Nav (manual)
5. **Descubrimiento de patrones de email** con Hunter o el integrado de Apollo
6. **Validación de email** con Truelist antes de la lista final
7. **Entregar** a la skill de cold-email para el copy de outreach

Adapta esta secuencia según qué herramientas realmente tiene el usuario.
