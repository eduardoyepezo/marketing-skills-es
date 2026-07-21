# Marketing Skills para Agentes de IA

Una colección de skills de agentes de IA enfocadas en tareas de marketing. Creada para marketers técnicos y fundadores que quieren que sus agentes de codificación con IA los ayuden con optimización de conversiones, redacción publicitaria, SEO, analítica y growth engineering. Funciona con Claude Code, OpenAI Codex, Cursor, Windsurf y cualquier agente que soporte la [especificación Agent Skills](https://agentskills.io).

Creada por [Corey Haines](https://corey.co?ref=marketingskills). ¿Necesitas ayuda práctica? Visita [Conversion Factory](https://conversionfactory.co?ref=marketingskills) — la agencia de Corey para optimización de conversiones, landing pages y estrategia de crecimiento. ¿Quieres aprender más sobre marketing? Suscríbete a [Swipe Files](https://swipefiles.com?ref=marketingskills). ¿Quieres un agente de IA autónomo que use estas skills para ser tu CMO? Prueba [Magister](https://magistermarketing.com?ref=marketingskills).

¿Eres nuevo en la terminal y los agentes de codificación? Consulta la guía complementaria [Coding for Marketers](https://codingformarketers.com?ref=marketingskills).

**¡Las contribuciones son bienvenidas!** ¿Encontraste una forma de mejorar una skill o tienes una nueva para agregar? [Abre un PR](#contributing).

¿Tienes un problema o una pregunta? [Abre un issue](https://github.com/coreyhaines31/marketingskills/issues) — con gusto te ayudamos.

## ¿Qué son las Skills?

Las skills son archivos markdown que le dan a los agentes de IA conocimiento especializado y flujos de trabajo para tareas específicas. Cuando las agregas a tu proyecto, tu agente puede reconocer cuándo estás trabajando en una tarea de marketing y aplicar los marcos y las mejores prácticas correctas.

## Cómo Funcionan las Skills en Conjunto

Las skills se referencian entre sí y se basan en un contexto compartido. La skill `product-marketing-context` es la base — todas las demás skills la verifican primero para entender tu producto, audiencia y posicionamiento antes de hacer cualquier cosa.

```
                            ┌──────────────────────────────────────┐
                            │      product-marketing-context       │
                            │    (read by all other skills first)  │
                            └──────────────────┬───────────────────┘
                                               │
    ┌──────────────┬─────────────┬─────────────┼─────────────┬──────────────┬──────────────┐
    ▼              ▼             ▼             ▼             ▼              ▼              ▼
┌──────────┐ ┌──────────┐ ┌──────────┐ ┌────────────┐ ┌──────────┐ ┌─────────────┐ ┌───────────┐
│  SEO &   │ │   CRO    │ │Content & │ │  Paid &    │ │ Growth & │ │  Sales &    │ │ Strategy  │
│ Content  │ │          │ │   Copy   │ │Measurement │ │Retention │ │    GTM      │ │           │
├──────────┤ ├──────────┤ ├──────────┤ ├────────────┤ ├──────────┤ ├─────────────┤ ├───────────┤
│seo-audit │ │page-cro  │ │copywritng│ │paid-ads    │ │referral  │ │revops       │ │mktg-ideas │
│ai-seo    │ │signup-cro│ │copy-edit │ │ad-creative │ │free-tool │ │sales-enable │ │mktg-psych │
│site-arch │ │onboard   │ │cold-email│ │ab-test     │ │churn-    │ │launch       │ │           │
│programm  │ │form-cro  │ │email-seq │ │analytics   │ │ prevent  │ │pricing      │ │           │
│schema    │ │popup-cro │ │social    │ │            │ │          │ │competitor   │ │           │
│content   │ │paywall   │ │          │ │            │ │          │ │             │ │           │
└────┬─────┘ └────┬─────┘ └────┬─────┘ └─────┬──────┘ └────┬─────┘ └──────┬──────┘ └─────┬─────┘
     │            │            │              │             │              │              │
     └────────────┴─────┬──────┴──────────────┴─────────────┴──────────────┴──────────────┘
                        │
         Skills cross-reference each other:
           copywriting ↔ page-cro ↔ ab-test-setup
           revops ↔ sales-enablement ↔ cold-email
           seo-audit ↔ schema-markup ↔ ai-seo
```

Consulta la sección **Related Skills** de cada skill para ver el mapa de dependencias completo.

## Skills Disponibles

<!-- SKILLS:START -->
| Skill | Descripción |
|-------|-------------|
| [ab-test-setup](.agent/skills/marketing/ab-test-setup/) | Cuando el usuario quiere planear, diseñar o implementar una prueba A/B o experimento. También usar cuando el usuario menciona "prueba A/B... |
| [ad-creative](.agent/skills/marketing/ad-creative/) | Cuando el usuario quiere generar, iterar o escalar creatividades publicitarias — titulares, descripciones, texto principal o variaciones ... |
| [ai-seo](.agent/skills/marketing/ai-seo/) | Cuando el usuario quiere optimizar contenido para motores de búsqueda de IA, ser citado por LLMs, o aparecer en respuestas generadas por ... |
| [analytics-tracking](.agent/skills/marketing/analytics-tracking/) | Cuando el usuario quiere configurar, mejorar o auditar el seguimiento de analíticas y medición. También usar cuando el usuario menciona "... |
| [churn-prevention](.agent/skills/marketing/churn-prevention/) | Cuando el usuario quiere reducir la cancelación, construir flujos de cancelación, configurar ofertas de retención, recuperar pagos fallid... |
| [cold-email](.agent/skills/marketing/cold-email/) | Escribir correos de prospección B2B y secuencias de seguimiento que obtienen respuestas. Usar cuando el usuario quiere escribir correos d... |
| [competitor-alternatives](.agent/skills/marketing/competitor-alternatives/) | Cuando el usuario quiere crear páginas de comparación con competidores o páginas de alternativas para SEO y habilitación de ventas. Tambi... |
| [content-plan-html](.agent/skills/marketing/content-plan-html/) | Cuando el usuario quiere convertir un plan de contenido mensual en formato MD a un archivo HTML listo para imprimir como PDF. Usar cuando... |
| [content-strategy](.agent/skills/marketing/content-strategy/) | Cuando el usuario quiere planificar una estrategia de contenido, decidir qué contenido crear, o determinar qué temas cubrir. También usar... |
| [copy-editing](.agent/skills/marketing/copy-editing/) | Cuando el usuario quiere editar, revisar o mejorar copy de marketing existente. También usar cuando el usuario menciona 'edita este copy,... |
| [copywriting](.agent/skills/marketing/copywriting/) | Cuando el usuario quiere escribir, reescribir o mejorar copy de marketing para cualquier página — incluyendo homepage, landing pages, pág... |
| [customer-research](.agent/skills/marketing/customer-research/) | Cuando el usuario quiere realizar, analizar o sintetizar investigación de clientes. Usar cuando el usuario menciona "investigación de cli... |
| [email-sequence](.agent/skills/marketing/email-sequence/) | Cuando el usuario quiere crear u optimizar una secuencia de email, campaña drip, flujo de email automatizado o programa de email de ciclo... |
| [form-cro](.agent/skills/marketing/form-cro/) | Cuando el usuario quiere optimizar cualquier formulario que NO sea de registro/sign-up — incluyendo formularios de captura de leads, form... |
| [free-tool-strategy](.agent/skills/marketing/free-tool-strategy/) | Cuando el usuario quiere planificar, evaluar o construir una herramienta gratuita con fines de marketing — generación de leads, valor de ... |
| [image](.agent/skills/marketing/image/) | Cuando el usuario quiere crear, generar, editar u optimizar imágenes para marketing — imágenes hero de blog, gráficos para redes sociales... |
| [launch-strategy](.agent/skills/marketing/launch-strategy/) | Cuando el usuario quiere planificar un lanzamiento de producto, anuncio de función o estrategia de lanzamiento. También usar cuando el us... |
| [marketing-ideas](.agent/skills/marketing/marketing-ideas/) | Cuando el usuario necesita ideas de marketing, inspiración o estrategias para su producto SaaS o software. También usar cuando el usuario... |
| [marketing-loops](.agent/skills/marketing/marketing-loops/) | Cuando el usuario quiere configurar un flujo de trabajo de marketing recurrente y autoejecutable — un loop repetible que un agente de IA ... |
| [marketing-plan](.agent/skills/marketing/marketing-plan/) | Cuando el usuario necesita un plan de marketing integral para un cliente, una empresa que asesora, o su propio producto. También usar cua... |
| [marketing-psychology](.agent/skills/marketing/marketing-psychology/) | Cuando el usuario quiere aplicar principios psicológicos, modelos mentales o ciencia del comportamiento al marketing. También usar cuando... |
| [offers](.agent/skills/marketing/offers/) | Cuando el usuario quiere diseñar, construir o mejorar una oferta — lo que realmente vende — incluyendo enfoque de valor, apilamiento de b... |
| [onboarding-cro](.agent/skills/marketing/onboarding-cro/) | Cuando el usuario quiere optimizar el onboarding post-registro, la activación de usuarios, la experiencia de primer uso o el tiempo de ob... |
| [page-cro](.agent/skills/marketing/page-cro/) | Cuando el usuario quiere optimizar, mejorar o aumentar las conversiones en cualquier página de marketing — incluyendo homepage, landing p... |
| [paid-ads](.agent/skills/marketing/paid-ads/) | Cuando el usuario quiere ayuda con campañas de publicidad pagada en Google Ads, Meta (Facebook/Instagram), LinkedIn, Twitter/X u otras pl... |
| [paywall-upgrade-cro](.agent/skills/marketing/paywall-upgrade-cro/) | Cuando el usuario quiere crear u optimizar paywalls dentro de la app, pantallas de actualización, modales de upsell o puertas de funcione... |
| [popup-cro](.agent/skills/marketing/popup-cro/) | Cuando el usuario quiere crear u optimizar popups, modales, overlays, slide-ins o banners con fines de conversión. También usar cuando el... |
| [pricing-strategy](.agent/skills/marketing/pricing-strategy/) | Cuando el usuario quiere ayuda con decisiones de precios, empaquetado o estrategia de monetización. También usar cuando el usuario mencio... |
| [product-marketing-context](.agent/skills/marketing/product-marketing-context/) | Cuando el usuario quiere crear o actualizar su documento de contexto de marketing del producto. También usar cuando el usuario menciona '... |
| [programmatic-seo](.agent/skills/marketing/programmatic-seo/) | Cuando el usuario quiere crear páginas orientadas a SEO a escala usando plantillas y datos. También usar cuando el usuario menciona "SEO ... |
| [referral-program](.agent/skills/marketing/referral-program/) | Cuando el usuario quiere crear, optimizar o analizar un programa de referidos, programa de afiliados o estrategia de boca a boca. También... |
| [revops](.agent/skills/marketing/revops/) | Cuando el usuario quiere ayuda con operaciones de ingresos, gestión del ciclo de vida del lead, o procesos de traspaso de marketing a ven... |
| [sales-enablement](.agent/skills/marketing/sales-enablement/) | Cuando el usuario quiere crear material de ventas, pitch decks, one-pagers, documentos de manejo de objeciones o scripts de demo. También... |
| [schema-markup](.agent/skills/marketing/schema-markup/) | Cuando el usuario quiere agregar, corregir u optimizar schema markup y datos estructurados en su sitio. También usar cuando el usuario me... |
| [seo-audit](.agent/skills/marketing/seo-audit/) | Cuando el usuario quiere auditar, revisar o diagnosticar problemas de SEO en su sitio. También usar cuando el usuario menciona "auditoría... |
| [signup-flow-cro](.agent/skills/marketing/signup-flow-cro/) | Cuando el usuario quiere optimizar flujos de registro, creación de cuenta o activación de prueba. También usar cuando el usuario menciona... |
| [site-architecture](.agent/skills/marketing/site-architecture/) | Cuando el usuario quiere planificar, mapear o reestructurar la jerarquía de páginas, navegación, estructura de URLs o enlazado interno de... |
| [social](.agent/skills/marketing/social/) | Cuando el usuario quiere ayuda para crear, programar u optimizar contenido de redes sociales para LinkedIn, Twitter/X, Instagram, TikTok,... |
| [social-content-plan](.agent/skills/marketing/social-content-plan/) | Cuando el usuario quiere generar el contenido completo de redes sociales para todo un mes con el copy redactado y listo para publicar, no... |
| [video](.agent/skills/marketing/video/) | Cuando el usuario quiere crear, generar o producir contenido de video usando herramientas de IA o frameworks programáticos. También usar ... |
<!-- SKILLS:END -->

## Instalación

### Opción 1: Instalación por CLI (Recomendada)

Usa [npx skills](https://github.com/vercel-labs/skills) para instalar skills directamente:

```bash
# Instalar todas las skills
npx skills add coreyhaines31/marketingskills

# Instalar skills específicas
npx skills add coreyhaines31/marketingskills --skill page-cro copywriting

# Listar skills disponibles
npx skills add coreyhaines31/marketingskills --list
```

Esto instala automáticamente en tu directorio `.agents/skills/` (y crea symlinks en `.claude/skills/` para compatibilidad con Claude Code).

### Opción 2: Plugin de Claude Code

Instala mediante el sistema de plugins integrado de Claude Code:

```bash
# Agregar el marketplace
/plugin marketplace add coreyhaines31/marketingskills

# Instalar todas las marketing skills
/plugin install marketing-skills
```

### Opción 3: Clonar y Copiar

Clona el repositorio completo y copia la carpeta de skills:

```bash
git clone https://github.com/coreyhaines31/marketingskills.git
cp -r marketingskills/skills/* .agents/skills/
```

### Opción 4: Git Submodule

Agrega como submódulo para actualizaciones fáciles:

```bash
git submodule add https://github.com/coreyhaines31/marketingskills.git .agents/marketingskills
```

Luego referencia las skills desde `.agents/marketingskills/skills/`.

### Opción 5: Fork y Personalizar

1. Haz un fork de este repositorio
2. Personaliza las skills para tus necesidades específicas
3. Clona tu fork en tus proyectos

### Opción 6: SkillKit (Multi-Agente)

Usa [SkillKit](https://github.com/rohitg00/skillkit) para instalar skills en múltiples agentes de IA (Claude Code, Cursor, Copilot, etc.):

```bash
# Instalar todas las skills
npx skillkit install coreyhaines31/marketingskills

# Instalar skills específicas
npx skillkit install coreyhaines31/marketingskills --skill page-cro copywriting

# Listar skills disponibles
npx skillkit install coreyhaines31/marketingskills --list
```

## Actualización desde v1.0

Las skills ahora usan `.agents/` en lugar de `.claude/` para el archivo de contexto de marketing de producto. Mueve tu archivo de contexto existente:

```bash
mkdir -p .agents
mv .claude/product-marketing-context.md .agents/product-marketing-context.md
```

Las skills seguirán verificando `.claude/` como alternativa, por lo que nada se rompe si no lo haces.

## Uso

Una vez instaladas, simplemente pídele a tu agente que te ayude con tareas de marketing:

```
"Help me optimize this landing page for conversions"
→ Usa la skill page-cro

"Write homepage copy for my SaaS"
→ Usa la skill copywriting

"Set up GA4 tracking for signups"
→ Usa la skill analytics-tracking

"Create a 5-email welcome sequence"
→ Usa la skill email-sequence
```

También puedes invocar las skills directamente:

```
/page-cro
/email-sequence
/seo-audit
```

## Categorías de Skills

### Optimización de Conversiones
- `page-cro` - Cualquier página de marketing
- `signup-flow-cro` - Flujos de registro
- `onboarding-cro` - Activación post-registro
- `form-cro` - Formularios de captura de leads
- `popup-cro` - Modales y overlays
- `paywall-upgrade-cro` - Momentos de actualización dentro de la app

### Contenido y Copy
- `copywriting` - Copy para páginas de marketing
- `copy-editing` - Editar y pulir copy existente
- `cold-email` - Correos fríos B2B y secuencias de prospección
- `email-sequence` - Flujos de email automatizados
- `social` - Contenido para redes sociales, social listening
- `social-content-plan` - Plan de contenido mensual completo, listo para publicar
- `content-plan-html` - Plan de contenido MD → HTML listo para imprimir como PDF

### Producción Creativa con IA
- `video` - Generación y producción de video con IA (avatares, video programático)
- `image` - Generación y optimización de imágenes con IA para marketing

### SEO y Descubrimiento
- `seo-audit` - SEO técnico y on-page
- `ai-seo` - Optimización para búsqueda de IA (AEO, GEO, LLMO)
- `programmatic-seo` - Generación de páginas a escala
- `site-architecture` - Jerarquía de páginas, navegación, estructura de URLs
- `competitor-alternatives` - Páginas de comparación y alternativas
- `schema-markup` - Datos estructurados

### Publicidad Paga y Distribución
- `paid-ads` - Campañas de anuncios en Google, Meta, LinkedIn
- `ad-creative` - Generación e iteración masiva de creativos publicitarios
- `social` - Programación y estrategia de redes sociales

### Medición y Pruebas
- `analytics-tracking` - Configuración de seguimiento de eventos
- `ab-test-setup` - Diseño de experimentos

### Retención
- `churn-prevention` - Flujos de cancelación, ofertas de retención, dunning, recuperación de pagos

### Growth Engineering
- `free-tool-strategy` - Herramientas de marketing y calculadoras
- `referral-program` - Programas de referidos y afiliados

### Investigación y Planeación Estratégica
- `customer-research` - Investigación de clientes, personas, JTBD, minería de reseñas
- `marketing-plan` - Plan de marketing integral AARRR de 13 secciones
- `marketing-loops` - Workflows de marketing recurrentes y autoejecutables

### Estrategia y Monetización
- `marketing-ideas` - 140 ideas de marketing para SaaS
- `marketing-psychology` - Modelos mentales y psicología
- `launch-strategy` - Lanzamientos de productos y anuncios
- `pricing-strategy` - Precios, empaquetado y monetización
- `offers` - Diseño de ofertas, garantías, apilamiento de bonos (servicios y agencias)

### Ventas y RevOps
- `revops` - Ciclo de vida de leads, puntuación, enrutamiento, gestión de pipeline
- `sales-enablement` - Decks de ventas, one-pagers, documentos de objeciones, scripts de demo

## Contribuir

¿Encontraste una forma de mejorar una skill? ¿Tienes una nueva skill para sugerir? ¡Los PRs e issues son bienvenidos!

Consulta [CONTRIBUTING.md](CONTRIBUTING.md) para ver las pautas para agregar o mejorar skills.

## Licencia

[MIT](LICENSE) - Úsalas como quieras.
