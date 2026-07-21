# Versiones de Marketing Skills

Versiones actuales de todas las skills. Los agentes pueden comparar con las versiones locales para verificar actualizaciones.

| Skill | Versión | Última Actualización |
|-------|---------|----------------------|
| ab-test-setup | 1.0.0 | 2026-02-27 |
| ad-creative | 2.8.0 | 2026-07-21 |
| ai-seo | 1.1.0 | 2026-02-27 |
| analytics-tracking | 1.0.0 | 2026-02-27 |
| aso | 2.0.0 | 2026-07-21 |
| churn-prevention | 1.1.0 | 2026-02-27 |
| co-marketing | 2.0.0 | 2026-07-21 |
| cold-email | 1.1.0 | 2026-02-27 |
| community-marketing | 2.0.0 | 2026-07-21 |
| competitor-alternatives | 1.0.0 | 2026-02-27 |
| competitor-profiling | 2.0.0 | 2026-07-21 |
| content-plan-html | 1.0.0 | 2026-02-27 |
| content-strategy | 1.0.0 | 2026-02-27 |
| copy-editing | 1.0.0 | 2026-02-27 |
| copywriting | 1.0.0 | 2026-02-27 |
| customer-research | 2.0.1 | 2026-07-21 |
| directory-submissions | 2.0.0 | 2026-07-21 |
| email-sequence | 1.0.0 | 2026-02-27 |
| form-cro | 1.0.0 | 2026-02-27 |
| free-tool-strategy | 1.0.0 | 2026-02-27 |
| image | 2.0.1 | 2026-07-21 |
| launch-strategy | 1.0.0 | 2026-02-27 |
| lead-magnets | 2.0.0 | 2026-07-21 |
| marketing-council | 1.0.0 | 2026-07-21 |
| marketing-ideas | 1.0.0 | 2026-02-27 |
| marketing-loops | 1.2.0 | 2026-07-21 |
| marketing-plan | 1.1.0 | 2026-07-21 |
| marketing-psychology | 1.0.0 | 2026-02-27 |
| offers | 1.0.0 | 2026-07-21 |
| onboarding-cro | 1.0.0 | 2026-02-27 |
| page-cro | 1.0.0 | 2026-02-27 |
| paid-ads | 1.0.0 | 2026-02-27 |
| paywall-upgrade-cro | 1.0.0 | 2026-02-27 |
| popup-cro | 1.0.0 | 2026-02-27 |
| pricing-strategy | 1.0.0 | 2026-02-27 |
| product-marketing-context | 1.0.0 | 2026-02-27 |
| programmatic-seo | 1.0.0 | 2026-02-27 |
| prospecting | 1.1.0 | 2026-07-21 |
| public-relations | 1.0.0 | 2026-07-21 |
| referral-program | 1.0.0 | 2026-02-27 |
| revops | 1.1.0 | 2026-02-27 |
| sales-enablement | 1.1.0 | 2026-02-27 |
| schema-markup | 1.0.0 | 2026-02-27 |
| seo-audit | 1.0.0 | 2026-02-27 |
| signup-flow-cro | 1.0.0 | 2026-02-27 |
| site-architecture | 1.1.0 | 2026-02-27 |
| sms | 1.0.0 | 2026-07-21 |
| social | 2.2.0 | 2026-07-21 |
| social-content-plan | 1.0.0 | 2026-02-27 |
| video | 2.1.0 | 2026-07-21 |

## Cambios Recientes

### 2026-07-21 (Tier 3 — sincronización completa)
- Se agregaron las últimas 10 skills del repo de Corey Haines, completando el set de 47: `aso` (2.0.0), `co-marketing` (2.0.0), `community-marketing` (2.0.0), `competitor-profiling` (2.0.0), `directory-submissions` (2.0.0), `lead-magnets` (2.0.0), `marketing-council` (1.0.0, incluye 12 dossiers de asesores simulados), `prospecting` (1.1.0), `public-relations` (1.0.0), `sms` (1.0.0)
- `public-relations` no tiene carpeta `evals/` — tampoco la tiene en el repo original
- `prospecting/references/compliance.md` y `sms/references/compliance.md` contienen reglas legales (CAN-SPAM, GDPR, CASL, TCPA, A2P 10DLC) traducidas con precisión exacta, verificadas contra el original
- `directory-submissions/references/submission-tracker-template.csv`: solo encabezados traducidos, datos de directorios intactos
- Este repo ahora tiene el catálogo completo de las 47 skills de Corey Haines (más 3 propias de agencia: `content-plan-html`, `social-content-plan`), todas traducidas al español — 50 skills en total
- Nota: al regenerar esta tabla completa se corrigió un desfase pre-existente entre las 24 skills originales y esta tabla — algunas mostraban `1.1.0` aquí pero `1.0.0` en su `SKILL.md` real; la tabla ahora refleja el número real de cada archivo

### 2026-07-21 (Tier 2)
- Se agregaron las skills `customer-research` (2.0.1), `offers` (1.0.0), `marketing-loops` (1.2.0) y `marketing-plan` (1.1.0), traducidas desde el repo de Corey Haines
- `marketing-plan` no tenía campo de versión en el original en inglés — se le agregó `1.1.0` (el número que sí aparece en el VERSIONS.md upstream) para mantener consistencia con el resto de este repo
- `offers` no tiene carpeta `evals/` — tampoco la tiene en el repo original
- Verificadas ~150 referencias cruzadas entre skills en `marketing-plan` contra el mapeo de nombres locales; sin nombres rotos
- Confirmado que las menciones a `typefully`, `copycraft`, `marketing-website-design`, `diagram-maker`, `website-copy` en `marketing-plan` son referencias intencionales a herramientas de otros marketplaces de Claude Code, no errores

### 2026-07-21 (Tier 1)
- Se agregaron las skills `video` (2.1.0) e `image` (2.0.1), traducidas desde el repo de Corey Haines — generación de video e imágenes con IA para producción creativa
- `social-content` renombrada a `social` y retraducida completa (1.1.0 → 2.2.0): agrega social listening, triage de engagement, frameworks de carrusel, ingeniería inversa de videos virales
- `ad-creative` retraducida completa (1.1.0 → 2.8.0): página de revisión de creativos en HTML, loop de estrategia creativa, formatos de video reveal nativos de iOS (iMessage, ChatGPT, Apple Notes, AirDrop)
- Se agregaron las guías de herramientas `heygen.md` y `hyperframes.md` (video con IA) al registro de herramientas
- Se corrigieron referencias cruzadas rotas a `social-content` en `video`, `cold-email`, `content-strategy`, `social-content-plan` y `tools/integrations/supermetrics.md`
- Se corrigieron rutas rotas en la tabla de skills de README.md (apuntaban a `skills/` en vez de `.agent/skills/marketing/`)
- Se agregaron `content-plan-html` y `social-content-plan` (skills propias, no del repo de Corey) al manifiesto de instalación — nunca se habían registrado

### 2026-02-27
- Migración de la ruta de contexto de `.claude/` a `.agents/` para compatibilidad agnóstica al agente
- Todas las skills ahora verifican `.agents/product-marketing-context.md` primero, con `.claude/` como alternativa para configuraciones más antiguas
- Rutas de instalación actualizadas en README para referenciar `.agents/skills/`
- Todas las 32 skills actualizadas de 1.0.0 → 1.1.0

### 2026-02-22
- Se agregó la skill `revops` para operaciones de ingresos, ciclo de vida de leads, puntuación, enrutamiento, gestión de pipeline y automatización de CRM
- Se agregó la skill `sales-enablement` para decks de ventas, one-pagers, manejo de objeciones, scripts de demo y playbooks de ventas

### 2026-02-21
- Se agregó la skill `site-architecture` para planificación de estructura de sitio web, jerarquía de páginas, diseño de navegación, estructura de URLs y estrategia de enlaces internos

### 2026-02-18
- Se agregó la skill `ai-seo` para optimización de búsqueda con IA (AEO, GEO, LLMO, AI Overviews)
- Se movieron los patrones de contenido AEO/GEO de las referencias de `seo-audit` a la skill `ai-seo`
- Se agregó la skill `churn-prevention` para flujos de cancelación, ofertas de retención, dunning y recuperación de pagos

### 2026-02-17
- Se agregó la skill `ad-creative` para generación masiva de creativos publicitarios e iteración basada en rendimiento
- Se agregaron 51 herramientas CLI sin dependencias para plataformas de marketing (`tools/clis/`)
- Se agregaron 31 nuevas guías de integración (`tools/integrations/`)
- Se agregaron 4 CLIs de prospección por email: hunter, snov, lemlist, instantly
- Fortalecimiento de seguridad: autenticación por encabezado para meta-ads, codificación de URL, validación de entrada
- Todos los CLIs revisados mediante auditoría independiente de codex (autenticación, seguridad, manejo de errores, consistencia)

### 2026-01-27
- Se agregó el seguimiento de versiones inicial
- Se agregó el registro de herramientas con 29 guías de integración
