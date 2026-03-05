# Versiones de Marketing Skills

Versiones actuales de todas las skills. Los agentes pueden comparar con las versiones locales para verificar actualizaciones.

| Skill | Versión | Última Actualización |
|-------|---------|----------------------|
| ab-test-setup | 1.1.0 | 2026-02-27 |
| ad-creative | 1.1.0 | 2026-02-27 |
| ai-seo | 1.1.0 | 2026-02-27 |
| analytics-tracking | 1.1.0 | 2026-02-27 |
| churn-prevention | 1.1.0 | 2026-02-27 |
| cold-email | 1.1.0 | 2026-02-27 |
| competitor-alternatives | 1.1.0 | 2026-02-27 |
| content-strategy | 1.1.0 | 2026-02-27 |
| copy-editing | 1.1.0 | 2026-02-27 |
| copywriting | 1.1.0 | 2026-02-27 |
| email-sequence | 1.1.0 | 2026-02-27 |
| form-cro | 1.1.0 | 2026-02-27 |
| free-tool-strategy | 1.1.0 | 2026-02-27 |
| launch-strategy | 1.1.0 | 2026-02-27 |
| marketing-ideas | 1.1.0 | 2026-02-27 |
| marketing-psychology | 1.1.0 | 2026-02-27 |
| onboarding-cro | 1.1.0 | 2026-02-27 |
| page-cro | 1.1.0 | 2026-02-27 |
| paid-ads | 1.1.0 | 2026-02-27 |
| paywall-upgrade-cro | 1.1.0 | 2026-02-27 |
| popup-cro | 1.1.0 | 2026-02-27 |
| pricing-strategy | 1.1.0 | 2026-02-27 |
| product-marketing-context | 1.1.0 | 2026-02-27 |
| programmatic-seo | 1.1.0 | 2026-02-27 |
| referral-program | 1.1.0 | 2026-02-27 |
| revops | 1.1.0 | 2026-02-27 |
| sales-enablement | 1.1.0 | 2026-02-27 |
| schema-markup | 1.1.0 | 2026-02-27 |
| seo-audit | 1.1.0 | 2026-02-27 |
| signup-flow-cro | 1.1.0 | 2026-02-27 |
| site-architecture | 1.1.0 | 2026-02-27 |
| social-content | 1.1.0 | 2026-02-27 |

## Cambios Recientes

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
