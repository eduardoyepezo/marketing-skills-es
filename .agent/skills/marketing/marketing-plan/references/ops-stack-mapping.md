# Stack de Operaciones de Marketing — Skills + MCPs por Etapa AARRR

Este documento mapea cada marketing-skill y cada integración MCP/API relevante a la(s) etapa(s) AARRR a la(s) que sirve principalmente. Es la fuente para la Sección 11 de todo plan.

> **Nota sobre el alcance.** Las skills de abajo viven en este repo de marketing skills. Algunas referencias apuntan a herramientas opcionales de marketplaces adyacentes de Claude Code (p. ej., `vercel:agent-browser`, `compound-engineering:diagram-maker`) — sustitúyelas por equivalentes si no están instaladas. Cuando un plan referencia una skill o herramienta que no está disponible, recurre a la táctica subyacente y márcalo en las decisiones abiertas de la Sección 13.

## La tesis

Un equipo pequeño + fCMO + herramientas agénticas = la salida de una organización de marketing tradicional de 15 a 20 personas. Las skills + MCPs codifican flujos de trabajo que antes requerían headcount dedicado por canal.

La Sección 11 del plan hace esta tesis explícita al:
1. Mapear skills a etapas para que el founder vea qué skills ejecutan qué trabajo
2. Mapear MCPs/APIs a etapas para que el founder vea la capa de herramientas
3. Nombrar un ejemplo operativo concreto que pruebe que el stack funciona
4. Mostrar desbloqueos de capacidad por etapa de financiamiento (pre-seed → seed → Series A)

## Skills de marketing mapeadas a AARRR

### Skills de Adquisición

| Skill | Qué hace | Uso primario en Adquisición |
|---|---|---|
| `seo-audit` | Audita el sitio en busca de SEO técnico y on-page | Chequeos trimestrales de salud del sitio |
| `ai-seo` | Optimiza contenido para motores de búsqueda de IA / citación por LLM | Estrategia de contenido a prueba de futuro |
| `programmatic-seo` | Construye páginas de SEO impulsadas por plantillas a escala | Sistemas de páginas de ubicación, comparación, integración |
| `schema-markup` | Agrega datos estructurados | Rich snippets, elegibilidad para citación de IA |
| `content-strategy` | Planifica temas, pilares, cadencia de contenido | Fijar el calendario editorial |
| `competitor-alternatives` | Construye páginas vs. y páginas de alternativas | Capturar SERPs de alta intención contra competidores |
| `paid-ads` | Planifica y estructura campañas pagadas | Apple Search Ads, Meta, Google, LinkedIn |
| `ad-creative` | Genera variaciones y creatividades de anuncio | Iterar creatividad de anuncios entre plataformas |
| `social` | Planifica y escribe contenido de redes sociales | LinkedIn, Twitter/X, Instagram, TikTok |
| `typefully` | Programa/publica tweets, hilos, contenido de LinkedIn | Operaciones de cadencia para canales liderados por el founder |
| `cold-email` | Escribe outreach B2B en frío + secuencias | Outbound para B2B SaaS / negocios híbridos |
| `analytics-tracking` | Configura tracking, GA4, eventos de conversión | Instrumentación del funnel |
| `free-tool-strategy` | Planifica herramientas gratuitas de engineering-as-marketing | Construir herramientas que generen enlaces + leads |
| `marketing-website-design` | Diseña sitios de marketing con intención | Diseño de páginas pilar/landing |
| `launch-strategy` | Planifica y ejecuta lanzamientos (Product Hunt, GA, lanzamientos de función) | Momentos GTM — estrategia + ejecución táctica |

### Skills de Activación

| Skill | Qué hace | Uso primario en Activación |
|---|---|---|
| `onboarding-cro` | Optimiza flujos de onboarding de usuarios | Reconstrucción de onboarding, pruebas de tasa de activación |
| `signup-flow-cro` | Optimiza signup/registro | Reducir fricción en el tope de la activación |
| `page-cro` | Optimiza cualquier página o formulario de marketing | Pruebas de conversión en páginas, formularios, landing pages |
| `paywall-upgrade-cro` | Optimiza paywalls y pantallas de actualización | Conversión trial → pago (también Ingresos) |
| `popup-cro` | Optimiza popups, modales, slide-ins | Captura de leads + prompts de activación |
| `copywriting` | Escribe copy de marketing | Pantallas de onboarding, copy de paywall, CTAs |
| `copy-editing` | Edita y mejora copy existente | Pasada de voz / claridad antes de publicar |
| `copycraft` | Overlay de variación de copy en tiempo real | Iteración de copy en vivo durante reviews |
| `website-copy` | Escribe el copy completo del sitio web (etapa-8 del proceso CF) | Producción integral de copy del sitio |
| `ab-test-setup` | Planifica pruebas A/B | Estructura para pruebas de variantes de onboarding |
| `marketing-psychology` | Aplica ciencia del comportamiento al copy y al CRO | Principios de persuasión en momentos de activación |

### Skills de Retención

| Skill | Qué hace | Uso primario en Retención |
|---|---|---|
| `email-sequence` | Diseña secuencias de email | Construcción de flujos en Customer.io / Mailchimp / Resend |
| `churn-prevention` | Construye flujos de cancelación, ofertas de retención, win-back | Reducir churn, recuperar pagos fallidos |
| `copywriting` / `copy-editing` | Producción de copy de email | Contenido de email de lifecycle |
| `paywall-upgrade-cro` | (cruza) — prompts de actualización en emails de retención | Upsell dentro del lifecycle |
| `ab-test-setup` | Prueba variantes de email | Pruebas de línea de asunto, CTA, timing |

### Skills de Referidos

| Skill | Qué hace | Uso primario en Referidos |
|---|---|---|
| `referral-program` | Planifica y lanza programas de referidos / afiliados / ambassador | Skill central para la Sección 7 |
| `social` | Crea contenido compartible para ambassadors | Talking points, plantillas de post |
| `copywriting` | Copy de email para ambassador / afiliados | Reclutamiento, onboarding, comunicación |
| `marketing-website-design` | Landing pages por ambassador | Superficie de atribución |
| `email-sequence` | Emails de lifecycle de ambassador | Onboarding, resumen mensual, notificaciones de pago |

### Skills de Ingresos

| Skill | Qué hace | Uso primario en Ingresos |
|---|---|---|
| `pricing-strategy` | Audita y optimiza el pricing | Estructura de niveles, defaults anuales, métricas de valor |
| `paywall-upgrade-cro` | Optimización de paywall | Conversión trial → pago, gratis → pago |
| `sales-enablement` | Construye decks de ventas, one-pagers, demos | Material de soporte de ventas B2B |
| `revops` | Operaciones de ingresos, ciclo de vida del lead | Traspaso de marketing a ventas |
| `ab-test-setup` | Experimentos de pricing | Probar default anual, pricing de introducción, consolidación de niveles |

### Skills transversales / de fundación de marca

| Skill | Qué hace | Uso primario |
|---|---|---|
| `product-marketing-context` | Configura el archivo de contexto `.agents/product-marketing.md` (posicionamiento, ICP, voz) | Fundacional — ejecutar primero; cada sección del plan lo referencia |
| `customer-research` | Realiza entrevistas de clientes + encuestas | Sección 2 + Sección 3 (Estado actual) |
| `marketing-psychology` | Aplica ciencia del comportamiento | Cruza con copy, CRO, paywalls |
| `marketing-ideas` | La librería de 139 ideas | Sección 12 del plan (Banco de ideas) |

## MCPs y APIs mapeadas a AARRR

### Herramientas de Adquisición

| Herramienta | Qué provee | Chequeo de conexión con el cliente |
|---|---|---|
| **API de Ahrefs** | Datos de SEO: investigación de keywords, backlinks, análisis de competidores | Requiere `AHREFS_API_KEY` en `.env` |
| **API de DataForSEO** | Datos SERP, volumen de keywords, análisis de SERP de competidores | Requiere API key |
| **GA4 MCP** | Tráfico por canal, eventos de conversión, curvas de retención | Conectado vía proyecto GCP + cuenta de servicio |
| **GitHub MCP** | Trabajo de repo: sitio de marketing (patrones `site-name-promo`), autoría de contenido | Auth estándar de CLI `gh` + servidor MCP |
| **Typefully MCP** | Publicación social (LinkedIn, X, Threads, Bluesky) | Cuenta de Typefully + API key |
| **Google Ads MCP** | Gestión de cuenta de anuncios, creación de campañas, extracción de performance | Conectado post-desbloqueo de presupuesto |
| **agent-browser** | Automatización de navegador (llenado de formularios, capturas, scraping) | Instalación CLI: `npm install -g agent-browser` |
| **dev-browser** | Automatización de navegador de propósito general | Instalación de servidor MCP |
| **defuddle** | Extracción limpia de markdown desde páginas web | Instalación CLI |
| **Notion** | Acceso al directorio de conocimiento interno | API key de Notion |
| **Stripe MCP** | Matemáticas de LTV, reconciliación de CAC pagado (cruza con Ingresos) | Cuenta de Stripe + key restringida |

### Herramientas de Activación

| Herramienta | Qué provee |
|---|---|
| **App Store Connect** | Tasa de conversión por variante de listado, funnel de instalación | Usualmente manual + `dev-browser` para capturas |
| **GitHub MCP** | Repo de app móvil para ediciones de código de onboarding |
| **Figma / Pencil MCP** | Diseño e iteración de pantallas de onboarding |
| **Customer.io MCP** | Coordinación de mensajería in-app + email de lifecycle |
| **Stripe MCP** | Estado de la suscripción para la lógica del paywall |
| **GA4 MCP** | Instrumentación de eventos de activación |

### Herramientas de Retención

| Herramienta | Qué provee |
|---|---|
| **Customer.io MCP** | La infraestructura de retención — construcción de flujos, segmentación, envío |
| **Shopify** | Eventos de comprador de hardware como disparadores de lifecycle |
| **Stripe MCP** | Estado de suscripción, cohortes de churn, cambios de plan |
| **GA4 MCP** | Eventos de sesión, curvas de retención |
| **Resend / Mailchimp / SendGrid** | Alternativas a Customer.io para diferentes stacks |

### Herramientas de Referidos

| Herramienta | Qué provee |
|---|---|
| **Dub.co** | Atribución de ambassador, enlaces cortos, tracking por ambassador |
| **Stripe MCP** | Contabilidad de comisiones + pagos vía Connect |
| **GitHub MCP** | Landing pages por ambassador |
| **Customer.io MCP** | Lifecycle de ambassador (reclutamiento → onboarding → resumen mensual → notificaciones de pago) |
| **Rewardful / Tolt / Mention Me** | Alternativas a Dub para gestión de afiliados |

### Herramientas de Ingresos

| Herramienta | Qué provee |
|---|---|
| **Stripe MCP** | Pruebas de pricing, analítica de suscripción, análisis de cohorte de churn, matemáticas de CAC blended |
| **Shopify** | Transacciones de hardware |
| **GA4 MCP** | Eventos de ingresos |
| **Customer.io MCP** | Lifecycle relacionado con paywall / pricing |
| **Notion** | Directorio de conocimiento comercial |

### Herramientas transversales

| Herramienta | Qué provee |
|---|---|
| **Notion** | Base de conocimiento compartida |
| **GitHub MCP** | Repo de contexto compartido (`{client-org}/{client-context}`) |
| **defuddle** | Extracción de investigación |
| **obsidian-cli** | Notas de trabajo para el fCMO |
| **Pencil MCP** | Archivos de diseño |
| **Figma MCP** | Archivos de diseño (si es Figma) |

## Desbloqueos de capacidad por etapa de financiamiento

La Sección 11 del plan debe incluir esta tabla (o equivalente), específica para las etapas de financiamiento actuales y proyectadas del cliente.

| Etapa | Headcount | Herramientas | Canales activos |
|---|---|---|---|
| **Pre-seed / bootstrapped** | fCMO + equipo founder | Todas las herramientas actuales + librería de marketing-skills + capa MCP | Solo orgánico (SEO, contenido, App Store, social liderado por el founder, eventos, boca a boca, ambassador) |
| **Cierre de seed** | + primera contratación de marketing (owner de lifecycle/contenido) | + cuentas de anuncios pagados (Apple Search Ads, Meta, LinkedIn) + skill `paid-ads` activada | + piloto de adquisición pagada ($5–15K/mes — ver `funding-stage-unlocks.md` para los niveles canónicos) |
| **Deployment de seed** | + diseñador (potencialmente fraccional) | + expansión de analítica (Mixpanel / Amplitude si se necesita) | + escalamiento pagado ($20–50K/mes) + primeros lanzamientos (PH, GA) |
| **Series A** | + lead de performance marketing + lead de contenido | + gasto dedicado en herramientas ($2–5K/mes de software) + presupuesto para patrocinio de eventos | + escalamiento pagado ($50–150K/mes) + consideración internacional + expansión vertical B2B |
| **Series B+** | Organización de marketing full-stack (10+ personas) | + partnerships de agencia + agencia de PR | + campañas de marca + adquisiciones + patrocinios a nivel de categoría |

## La prueba del ejemplo concreto

La Sección 11 del plan debe incluir al menos un ejemplo operativo concreto que pruebe la tesis del stack. El ejemplo debe ser:
- Un evento específico (no una afirmación abstracta)
- De la historia real de este cliente si es posible (lo más creíble)
- Vinculado a una persona no técnica ejecutando vía el stack (prueba que funciona sin ingeniería dedicada)

Ejemplos de engagements reales:
- *"En la llamada de kickoff, Alex redactó en vivo un flujo funcional de carrito abandonado en Customer.io, usando el MCP de Claude de Customer.io. Se validó que un founder no técnico puede publicar trabajo de lifecycle usando el patrón de skill de forma independiente."*
- *"En dos semanas, el equipo escaló de 0 a 14 keywords posicionadas usando `programmatic-seo` contra la API de Ahrefs + GitHub MCP — sin necesidad de una contratación dedicada de SEO."*
- *"La primera campaña de email generó una tasa de respuesta del 24% después de que la skill `cold-email` + GA4 MCP + Stripe MCP le dieran al equipo una lista objetivo verificada de usuarios con LTV alto pero sin actividad reciente."*

Si el cliente no tiene todavía un momento así en su historia, enmarca el ejemplo como la *primera movida* — "Aquí está la demostración que el equipo correrá en la semana uno para validar el stack:"

## Cuando el stack aún no aplica

Para clientes sin conexiones MCP configuradas, enmarca la Sección 11 de forma diferente:
- Lista las skills que SÍ aplican con las herramientas actuales
- Nombra qué MCPs desbloquearían qué secciones del plan
- Trata la configuración de MCP como una prioridad de Q1 junto con las correcciones de base

Un plan no puede reclamar la tesis del stack agéntico si el stack no está conectado. Sé honesto sobre el estado.
