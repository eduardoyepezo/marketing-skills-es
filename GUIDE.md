# Marketing Skills — Guía de Uso

Una guía práctica para usar las 32 marketing skills en esta carpeta, cómo se conectan entre sí y cómo sacarles el máximo provecho con Claude Code o cualquier agente de IA.

---

## ¿Qué son las Skills?

Las skills son archivos markdown que le dan a tu agente de IA conocimiento especializado, flujos de trabajo y marcos para tareas específicas de marketing. Cuando están instaladas en tu proyecto, tu agente aplica automáticamente la skill correcta cuando detecta que estás trabajando en una tarea relevante — o puedes invocarlas directamente.

Cada skill vive en su propia carpeta y consiste en:

```
skill-name/
├── SKILL.md          # Instrucciones principales y flujos de trabajo (siempre cargado)
├── evals/
│   └── evals.json    # Casos de prueba para validar la calidad de la skill
└── references/       # Documentación detallada cargada bajo demanda
    ├── frameworks.md
    └── templates.md
```

`SKILL.md` es el archivo principal. Los archivos de `references/` son documentación de apoyo detallada que el agente carga cuando es necesario — manteniendo el archivo principal ligero sin perder profundidad.

---

## Empieza Aquí: Contexto de Marketing de Producto

**Antes de usar cualquier otra skill, configura tu contexto de marketing de producto.**

```
/product-marketing-context
```

Esta es la base que todas las demás skills leen primero. Captura el posicionamiento, audiencia, mensajería, panorama competitivo, lenguaje del cliente y voz de marca de tu producto — para que nunca tengas que repetirte entre tareas.

El documento se guarda en `.agents/product-marketing-context.md` (o `.claude/product-marketing-context.md` como alternativa).

### Qué captura

| Sección | Qué contiene |
|---|---|
| Descripción del Producto | Descripción en una línea, qué hace, categoría, modelo de negocio |
| Audiencia Objetivo | Tipo de empresa, tomadores de decisiones, casos de uso, JTBD |
| Personas | Por stakeholder: qué les importa, su desafío, tu valor |
| Problemas y Puntos de Dolor | Problema central, por qué fallan las alternativas, tensión emocional |
| Panorama Competitivo | Competidores directos, secundarios e indirectos |
| Diferenciación | Diferenciadores clave, cómo eres diferente, por qué importa |
| Objeciones y Anti-Personas | Objeciones de ventas + quién NO es el cliente ideal |
| Dinámicas de Cambio | Fuerzas de empuje, atracción, hábito y ansiedad |
| Lenguaje del Cliente | Frases textuales para usar y evitar |
| Voz de Marca | Tono, estilo, personalidad |
| Pruebas y Evidencias | Métricas, logos, fragmentos de testimonios |
| Objetivos | Objetivo principal, acción de conversión, métricas actuales |

### Cómo otras skills lo usan

Cada skill verifica si este archivo existe antes de hacer cualquier cosa. Si existe, el agente usa tu posicionamiento, audiencia y tono automáticamente — sin necesidad de re-explicar tu producto cada vez. Si falta, las skills pedirán contexto básico antes de continuar.

---

## Categorías de Skills

### Optimización de Conversiones (CRO)

Seis skills que cubren cada etapa del embudo de conversión:

| Skill | Úsala cuando... |
|---|---|
| `page-cro` | Quieres mejorar las conversiones en cualquier página de marketing (homepage, landing page, precios) |
| `signup-flow-cro` | Quieres optimizar el flujo de registro o activación de prueba |
| `onboarding-cro` | Quieres aumentar la activación y el tiempo hasta el valor después del registro |
| `form-cro` | Quieres mejorar formularios de captura de leads, contacto o solicitud de demo |
| `popup-cro` | Quieres crear u optimizar modales, overlays, slide-ins o banners |
| `paywall-upgrade-cro` | Quieres optimizar pantallas de actualización dentro de la app, paywalls o momentos de upsell |

**Cómo se conectan:** `page-cro` es la skill de uso general. Usa las otras para superficies de conversión específicas. Todas ellas hacen referencia cruzada a `ab-test-setup` cuando quieres validar cambios experimentalmente.

---

### Contenido y Copy

| Skill | Úsala cuando... |
|---|---|
| `copywriting` | Estás escribiendo o reescribiendo copy de marketing para cualquier página |
| `copy-editing` | Estás editando y puliendo copy existente |
| `cold-email` | Estás escribiendo correos fríos B2B y secuencias de seguimiento |
| `email-sequence` | Estás creando campañas de drip automatizadas y flujos de email de ciclo de vida |
| `social-content` | Estás creando y optimizando publicaciones sociales para LinkedIn, Twitter/X, Instagram |
| `content-strategy` | Estás planificando qué contenido crear y qué temas cubrir |
| `brainstorming` | Estás generando ideas amplias de marketing cuando no sabes por dónde empezar |

**Cómo se conectan:** `copywriting` ↔ `page-cro` — úsalas juntas al reconstruir una página. `cold-email` + `email-sequence` cubren el panorama completo de prospección y nurture. `content-strategy` alimenta a `copywriting` y `social-content` con dirección.

---

### SEO y Descubrimiento

| Skill | Úsala cuando... |
|---|---|
| `seo-audit` | Estás auditando o diagnosticando problemas de SEO en tu sitio |
| `ai-seo` | Estás optimizando para aparecer en respuestas generadas por IA (AEO, GEO, AI Overviews) |
| `programmatic-seo` | Estás creando páginas impulsadas por SEO a escala usando plantillas y datos |
| `site-architecture` | Estás planificando jerarquía de páginas, navegación, estructura de URLs, enlaces internos |
| `competitor-alternatives` | Estás creando páginas de comparación con competidores y páginas de "[producto] alternativas" |
| `schema-markup` | Estás agregando o corrigiendo datos estructurados y schema markup |

**Cómo se conectan:** Ejecuta `seo-audit` primero para diagnóstico. `site-architecture` establece la base estructural. `programmatic-seo` + `schema-markup` trabajan juntos para contenido escalado y legible por máquinas. `ai-seo` se ubica junto al SEO tradicional — diferente objetivo de optimización (LLMs vs. rastreadores de búsqueda). `competitor-alternatives` abarca tanto SEO como habilitación de ventas.

---

### Publicidad Paga y Distribución

| Skill | Úsala cuando... |
|---|---|
| `paid-ads` | Estás ejecutando campañas en Google, Meta, LinkedIn, TikTok o Twitter/X |
| `ad-creative` | Estás generando, iterando o escalando creativos publicitarios en volumen |
| `social-content` | Estás distribuyendo contenido orgánico a través de canales sociales |

**Cómo se conectan:** `paid-ads` y `ad-creative` están muy vinculadas — usa `paid-ads` para la estrategia y estructura de la campaña, `ad-creative` para generar los titulares, copy y variantes creativas reales. Ambas se nutren de los principios de `copywriting`.

---

### Medición y Pruebas

| Skill | Úsala cuando... |
|---|---|
| `analytics-tracking` | Estás configurando o auditando GA4, GTM, Mixpanel, Segment u otro seguimiento de eventos |
| `ab-test-setup` | Estás diseñando e implementando pruebas A/B o experimentos |

**Cómo se conectan:** `analytics-tracking` es un prerrequisito para `ab-test-setup` — necesitas un seguimiento de eventos adecuado antes de poder medir los resultados de las pruebas. Ambas skills son referenciadas por las skills de CRO al validar mejoras.

---

### Retención

| Skill | Úsala cuando... |
|---|---|
| `churn-prevention` | Estás creando flujos de cancelación, ofertas de retención, secuencias de dunning o recuperación de pagos |

**Cómo se conecta:** Conecta `email-sequence` (para correos de dunning y winback), `analytics-tracking` (para señales de deserción) y `pricing-strategy` (para el diseño de ofertas de retención).

---

### Growth Engineering

| Skill | Úsala cuando... |
|---|---|
| `referral-program` | Estás creando u optimizando un programa de referidos, afiliados o marketing de boca en boca |
| `free-tool-strategy` | Estás planificando o construyendo una herramienta gratuita para generación de leads, valor SEO o awareness de marca |

**Cómo se conectan:** `referral-program` + `revops` — los programas de referidos necesitan enrutamiento de leads y atribución. `free-tool-strategy` alimenta a `programmatic-seo` (las herramientas generan backlinks y rankings).

---

### Estrategia y Monetización

| Skill | Úsala cuando... |
|---|---|
| `marketing-ideas` | Necesitas una amplia gama de ideas de marketing para SaaS para elegir (más de 140 ideas indexadas) |
| `marketing-psychology` | Estás aplicando ciencia del comportamiento y principios psicológicos a cualquier trabajo de marketing |
| `launch-strategy` | Estás planificando el lanzamiento de un producto, anuncio de funcionalidad o release |
| `pricing-strategy` | Estás tomando decisiones de precios, empaquetado o monetización |
| `brand-identity` | Estás definiendo o refinando la voz de marca, identidad visual y design tokens |

**Cómo se conectan:** `marketing-psychology` informa a todas las demás skills — es una lente, no un flujo de trabajo. `launch-strategy` se nutre de `copywriting`, `paid-ads`, `email-sequence` y `social-content` como capas de ejecución. `pricing-strategy` se conecta con `paywall-upgrade-cro` y `churn-prevention`.

---

### Ventas y Operaciones de Ingresos

| Skill | Úsala cuando... |
|---|---|
| `revops` | Ciclo de vida de leads, puntuación de leads, reglas de enrutamiento, gestión de pipeline, automatización de CRM |
| `sales-enablement` | Estás creando pitch decks, one-pagers, documentos de manejo de objeciones y scripts de demo |

**Cómo se conectan:** `revops` + `cold-email` + `sales-enablement` forman el sistema completo de ventas B2B. `revops` maneja la mecánica del pipeline, `cold-email` genera pipeline, `sales-enablement` lo cierra.

---

## Cómo se Conectan las Skills — El Mapa de Dependencias

```
                    product-marketing-context
                    (todas las skills leen esto primero)
                            │
    ┌───────────────────────┼───────────────────────────┐
    │                       │                           │
    ▼                       ▼                           ▼
SEO Cluster           CRO Cluster               Content Cluster
─────────────         ──────────────            ─────────────────
seo-audit ──────────► page-cro ◄──────────────  copywriting
    │                    │                           │
ai-seo               signup-flow-cro             copy-editing
    │                    │                           │
site-architecture    onboarding-cro ◄─────────── email-sequence
    │                    │                           │
programmatic-seo     ab-test-setup ◄──────────── cold-email
    │                    │                           │
schema-markup        analytics-tracking          social-content
    │                    │
competitor-alternatives  │
                         │
            ┌────────────┴────────────┐
            │                         │
            ▼                         ▼
    Paid / Growth             Strategy / Sales
    ─────────────             ────────────────
    paid-ads                  revops
    ad-creative               sales-enablement
    referral-program          launch-strategy
    free-tool-strategy        pricing-strategy
    churn-prevention          marketing-psychology
```

**Patrones clave entre skills:**

- `copywriting` ↔ `page-cro` ↔ `ab-test-setup` — el ciclo de conversión central
- `seo-audit` → `site-architecture` → `programmatic-seo` + `schema-markup` — la secuencia de construcción SEO
- `revops` ↔ `cold-email` ↔ `sales-enablement` — el stack de ingresos B2B
- `analytics-tracking` → `ab-test-setup` → todas las skills de CRO — la medición lo habilita todo
- `launch-strategy` se nutre de copywriting, paid-ads, email-sequence, social-content

---

## Invocando Skills

Las skills se activan automáticamente cuando describes una tarea de marketing. También puedes llamarlas directamente:

```
/page-cro
/email-sequence
/seo-audit
/copywriting
/product-marketing-context
```

O describe lo que quieres:

```
"Ayúdame a optimizar esta landing page"              → page-cro
"Escribe una secuencia de bienvenida de 5 emails"    → email-sequence
"Configura el seguimiento de eventos GA4 para registros" → analytics-tracking
"Audita el SEO de mi sitio"                          → seo-audit
"Crea un programa de referidos para mi SaaS"         → referral-program
"Planifica el lanzamiento de nuestra nueva función"  → launch-strategy
"Escribe copy de anuncios para campañas de Google Search" → paid-ads + ad-creative
```

---

## Herramientas: Integraciones y CLIs

Junto con las skills, esta carpeta incluye **68 guías de integración de herramientas** y **62 herramientas CLI** para plataformas de marketing.

### Registro de Herramientas

Consulta `tools/REGISTRY.md` para el índice completo. Las herramientas están organizadas por categoría:

| Categoría | Herramientas |
|---|---|
| Analytics | GA4, Mixpanel, Amplitude, PostHog, Segment, Adobe Analytics, Plausible |
| SEO | Google Search Console, SEMrush, Ahrefs, DataForSEO, Keywords Everywhere |
| Email | Mailchimp, Customer.io, Resend, SendGrid, Kit, Klaviyo, Brevo, ActiveCampaign, Beehiiv |
| Email Outreach | Hunter, Snov, Lemlist, Instantly |
| Ads | Google Ads, Meta Ads, LinkedIn Ads, TikTok Ads |
| CRM | HubSpot, Salesforce, Close |
| Referral / Affiliate | Rewardful, Tolt, Mention Me, PartnerStack |
| Payments | Stripe, Paddle |
| Data Enrichment | Clearbit, Apollo, ZoomInfo, Clay |
| Data Aggregation | Supermetrics, Coupler |
| Automation | Zapier, Airops |
| Links | Dub.co |
| Otros | PostHog, Pendo, Hotjar, Optimizely, Intercom, Outreach, y más |

### Guías de Integración

Cada herramienta tiene una guía detallada en `tools/integrations/{tool}.md` que cubre:
- Autenticación y configuración
- Endpoints de API clave
- Operaciones comunes
- Casos de uso de ejemplo

### Herramientas CLI

Scripts de Node.js sin dependencias (Node 18+) para cada plataforma, en `tools/clis/{tool}.js`:

```bash
# Mostrar uso para cualquier herramienta
node tools/clis/ga4.js

# Vista previa de una solicitud sin enviarla
node tools/clis/ga4.js events list --dry-run

# Verificación de sintaxis
node --check tools/clis/ga4.js
```

### Mapeo de Herramientas → Skills

| Skill | Herramientas relevantes |
|---|---|
| `analytics-tracking` | ga4, mixpanel, segment, amplitude, posthog |
| `referral-program` | rewardful, tolt, dub-co, mention-me, partnerstack |
| `email-sequence` | customer-io, mailchimp, resend, klaviyo, kit |
| `paid-ads` | google-ads, meta-ads, linkedin-ads, tiktok-ads |
| `cold-email` | hunter, snov, lemlist, instantly |
| `revops` | hubspot, salesforce, close, clay, clearbit |
| `ab-test-setup` | optimizely, google-ads (experiments) |
| `churn-prevention` | stripe, paddle, customer-io |

---

## Flujos de Trabajo Recomendados

### Configuración de Nuevo Producto
1. `/product-marketing-context` — captura posicionamiento y audiencia una vez
2. `/brand-identity` — define voz, tono e identidad visual
3. `/site-architecture` — planifica la estructura de tu página antes de construir
4. `/copywriting` — escribe la homepage y las landing pages clave
5. `/seo-audit` — audita lo que está en su lugar e identifica brechas

### Lanzar una Nueva Funcionalidad
1. `/launch-strategy` — construye el plan de lanzamiento completo
2. `/copywriting` — escribe el copy del anuncio
3. `/email-sequence` — redacta los correos de anuncio y nurture
4. `/social-content` — crea publicaciones sociales de soporte
5. `/paid-ads` — configura cualquier amplificación paga

### Mejorar Conversiones
1. `/page-cro` — audita y mejora la página
2. `/copywriting` — reescribe si es necesario
3. `/ab-test-setup` — diseña experimentos para validar cambios
4. `/analytics-tracking` — asegúrate de poder medir resultados

### Construir una Base SEO
1. `/seo-audit` — encuentra los problemas existentes
2. `/site-architecture` — planifica la estructura
3. `/content-strategy` — decide qué crear
4. `/programmatic-seo` — escala páginas de alta intención
5. `/schema-markup` — agrega datos estructurados
6. `/ai-seo` — optimiza para búsqueda de IA junto al SEO tradicional

### Construir un Sistema de Ventas B2B
1. `/product-marketing-context` — afina el posicionamiento primero
2. `/revops` — configura el ciclo de vida de leads, puntuación y enrutamiento
3. `/cold-email` — escribe secuencias de prospección
4. `/sales-enablement` — construye pitch decks, one-pagers, documentos de objeciones
5. `/competitor-alternatives` — crea páginas de comparación para inbound

---

## Mantener las Skills Actualizadas

Las skills verifican actualizaciones automáticamente una vez por sesión. Para actualizar manualmente:

```bash
# Desde tu carpeta Skills Master
git pull

# O verifica qué hay de nuevo
cat VERSIONS.md
```

Versión actual: **1.1.0** (las 32 skills, actualizado el 2026-02-27)

---

## Referencia de Estructura de Archivos

```
Skills Master/
├── GUIDE.md                          # Este archivo
├── CLAUDE.md                         # Instrucciones para el agente
├── AGENTS.md                         # Pautas de especificación entre agentes
├── README.md                         # Resumen y opciones de instalación
├── VERSIONS.md                       # Historial de versiones por skill
├── CONTRIBUTING.md                   # Cómo agregar o mejorar skills
├── validate-skills.sh                # Script de validación
├── .claude-plugin/
│   └── marketplace.json              # Manifiesto del plugin de Claude Code
└── .agent/skills/marketing/
    ├── product-marketing-context/    # Skill base — configurar primero
    ├── page-cro/                     # CRO: cualquier página de marketing
    ├── signup-flow-cro/              # CRO: flujos de registro
    ├── onboarding-cro/               # CRO: activación post-registro
    ├── form-cro/                     # CRO: formularios de captura de leads
    ├── popup-cro/                    # CRO: modales y overlays
    ├── paywall-upgrade-cro/          # CRO: momentos de actualización dentro de la app
    ├── copywriting/                  # Copy: escribir páginas de marketing
    ├── copy-editing/                 # Copy: editar copy existente
    ├── cold-email/                   # Copy: secuencias de prospección B2B
    ├── email-sequence/               # Copy: flujos de email automatizados
    ├── social-content/               # Copy: contenido para redes sociales
    ├── content-strategy/             # Estrategia: qué crear
    ├── seo-audit/                    # SEO: diagnosticar problemas
    ├── ai-seo/                       # SEO: optimizar para búsqueda de IA
    ├── programmatic-seo/             # SEO: generación de páginas a escala
    ├── site-architecture/            # SEO: estructura y navegación
    ├── competitor-alternatives/      # SEO + ventas: páginas de comparación
    ├── schema-markup/                # SEO: datos estructurados
    ├── paid-ads/                     # Pago: estrategia de campaña
    ├── ad-creative/                  # Pago: generación de creativos
    ├── analytics-tracking/           # Medición: seguimiento de eventos
    ├── ab-test-setup/                # Medición: diseño de experimentos
    ├── churn-prevention/             # Retención: flujos de cancelación, dunning
    ├── referral-program/             # Crecimiento: referidos y afiliados
    ├── free-tool-strategy/           # Crecimiento: marketing con herramientas gratuitas
    ├── marketing-ideas/              # Estrategia: más de 140 ideas indexadas
    ├── marketing-psychology/         # Estrategia: lente de ciencia del comportamiento
    ├── launch-strategy/              # Estrategia: lanzamientos de productos
    ├── pricing-strategy/             # Estrategia: precios y empaquetado
    ├── brand-identity/               # Estrategia: voz e identidad
    ├── revops/                       # Ventas: operaciones de ingresos
    ├── sales-enablement/             # Ventas: pitch decks, objeciones
    └── tools/
        ├── REGISTRY.md               # Índice de herramientas
        ├── integrations/             # 68 guías de integración de API
        └── clis/                     # 62 herramientas CLI (Node.js)
```
