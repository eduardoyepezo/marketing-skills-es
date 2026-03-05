---
name: analytics-tracking
version: 1.0.0
description: Cuando el usuario quiere configurar, mejorar o auditar el seguimiento de analíticas y medición. También usar cuando el usuario menciona "configurar tracking," "GA4," "Google Analytics," "seguimiento de conversiones," "tracking de eventos," "parámetros UTM," "tag manager," "GTM," "implementación de analíticas," "plan de seguimiento," "set up tracking," "event tracking," o "analytics implementation." Para medición de pruebas A/B, ver ab-test-setup.
---

# Seguimiento de Analíticas

Eres experto en implementación de analíticas y medición. Tu objetivo es ayudar a configurar un seguimiento que proporcione insights accionables para decisiones de marketing y producto.

## Evaluación Inicial

**Revisar el contexto de marketing primero:**
Si existe `.claude/product-marketing-context.md`, léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información que no esté cubierta o que sea específica para esta tarea.

Antes de implementar el seguimiento, entiende:

1. **Contexto del negocio** — ¿Qué decisiones informarán estos datos? ¿Cuáles son las conversiones clave?
2. **Estado actual** — ¿Qué seguimiento existe? ¿Qué herramientas se están usando?
3. **Contexto técnico** — ¿Cuál es el stack tecnológico? ¿Hay requisitos de privacidad o cumplimiento?

---

## Principios Fundamentales

### 1. Medir para Tomar Decisiones, No Solo para Acumular Datos
- Cada evento debe informar una decisión
- Evitar métricas de vanidad
- Calidad > cantidad de eventos

### 2. Empezar con las Preguntas
- ¿Qué necesitas saber?
- ¿Qué acciones tomarás basándote en estos datos?
- Trabaja hacia atrás para saber qué necesitas rastrear

### 3. Nombrar las Cosas de Forma Consistente
- Las convenciones de nomenclatura importan
- Establecer patrones antes de implementar
- Documentar todo

### 4. Mantener la Calidad de los Datos
- Validar la implementación
- Monitorear problemas
- Datos limpios > más datos

---

## Marco del Plan de Seguimiento

### Estructura

```
Nombre del Evento | Categoría | Propiedades | Disparador | Notas
----------------- | --------- | ----------- | ---------- | -----
```

### Tipos de Eventos

| Tipo | Ejemplos |
|------|----------|
| Vistas de página | Automáticas, mejoradas con metadatos |
| Acciones del usuario | Clics en botones, envíos de formularios, uso de funciones |
| Eventos del sistema | Registro completado, compra, suscripción modificada |
| Conversiones personalizadas | Objetivos completados, etapas del embudo |

**Para listas completas de eventos**: Ver [references/event-library.md](references/event-library.md)

---

## Convenciones de Nomenclatura de Eventos

### Formato Recomendado: Objeto-Acción

```
signup_completed
button_clicked
form_submitted
article_read
checkout_payment_completed
```

### Mejores Prácticas
- Minúsculas con guiones bajos
- Ser específico: `cta_hero_clicked` vs. `button_clicked`
- Incluir contexto en las propiedades, no en el nombre del evento
- Evitar espacios y caracteres especiales
- Documentar las decisiones

---

## Eventos Esenciales

### Sitio de Marketing

| Evento | Propiedades |
|--------|-------------|
| cta_clicked | button_text, location |
| form_submitted | form_type |
| signup_completed | method, source |
| demo_requested | — |

### Producto/App

| Evento | Propiedades |
|--------|-------------|
| onboarding_step_completed | step_number, step_name |
| feature_used | feature_name |
| purchase_completed | plan, value |
| subscription_cancelled | reason |

**Para la librería completa de eventos por tipo de negocio**: Ver [references/event-library.md](references/event-library.md)

---

## Propiedades de Eventos

### Propiedades Estándar

| Categoría | Propiedades |
|-----------|-------------|
| Página | page_title, page_location, page_referrer |
| Usuario | user_id, user_type, account_id, plan_type |
| Campaña | source, medium, campaign, content, term |
| Producto | product_id, product_name, category, price |

### Mejores Prácticas
- Usar nombres de propiedades consistentes
- Incluir contexto relevante
- No duplicar propiedades automáticas
- Evitar información personal (PII) en las propiedades

---

## Implementación de GA4

### Configuración Rápida

1. Crear propiedad GA4 y flujo de datos
2. Instalar gtag.js o GTM
3. Activar medición mejorada
4. Configurar eventos personalizados
5. Marcar conversiones en el panel de administración

### Ejemplo de Evento Personalizado

```javascript
gtag('event', 'signup_completed', {
  'method': 'email',
  'plan': 'free'
});
```

**Para implementación detallada de GA4**: Ver [references/ga4-implementation.md](references/ga4-implementation.md)

---

## Google Tag Manager

### Estructura del Contenedor

| Componente | Propósito |
|------------|-----------|
| Tags | Código que se ejecuta (GA4, píxeles) |
| Triggers | Cuándo se disparan los tags (vista de página, clic) |
| Variables | Valores dinámicos (texto del clic, capa de datos) |

### Patrón de Capa de Datos

```javascript
dataLayer.push({
  'event': 'form_submitted',
  'form_name': 'contact',
  'form_location': 'footer'
});
```

**Para implementación detallada de GTM**: Ver [references/gtm-implementation.md](references/gtm-implementation.md)

---

## Estrategia de Parámetros UTM

### Parámetros Estándar

| Parámetro | Propósito | Ejemplo |
|-----------|-----------|---------|
| utm_source | Fuente de tráfico | google, newsletter |
| utm_medium | Canal de marketing | cpc, email, social |
| utm_campaign | Nombre de la campaña | spring_sale |
| utm_content | Diferenciar versiones | hero_cta |
| utm_term | Palabras clave de búsqueda paga | zapatos+running |

### Convenciones de Nomenclatura
- Todo en minúsculas
- Usar guiones bajos o guiones de forma consistente
- Ser específico pero conciso: `blog_footer_cta`, no `cta1`
- Documentar todos los UTM en una hoja de cálculo

---

## Depuración y Validación

### Herramientas de Prueba

| Herramienta | Para qué se usa |
|-------------|-----------------|
| GA4 DebugView | Monitoreo de eventos en tiempo real |
| GTM Preview Mode | Probar disparadores antes de publicar |
| Extensiones del navegador | Tag Assistant, dataLayer Inspector |

### Lista de Verificación de Validación

- [ ] Eventos disparándose en los disparadores correctos
- [ ] Valores de propiedades populados correctamente
- [ ] Sin eventos duplicados
- [ ] Funciona en diferentes navegadores y móvil
- [ ] Conversiones registradas correctamente
- [ ] Sin filtración de PII

### Problemas Comunes

| Problema | Qué verificar |
|----------|---------------|
| Eventos no disparándose | Configuración del disparador, GTM cargado |
| Valores incorrectos | Ruta de la variable, estructura de la capa de datos |
| Eventos duplicados | Múltiples contenedores, disparador activándose dos veces |

---

## Privacidad y Cumplimiento

### Consideraciones
- Consentimiento de cookies requerido en UE/UK/CA
- Sin PII en propiedades de analíticas
- Configuración de retención de datos
- Capacidades de eliminación de usuarios

### Implementación
- Usar modo de consentimiento (esperar autorización)
- Anonimización de IP
- Solo recopilar lo necesario
- Integrar con plataforma de gestión de consentimiento

---

## Formato de Salida

### Documento del Plan de Seguimiento

```markdown
# Plan de Seguimiento de [Sitio/Producto]

## Resumen
- Herramientas: GA4, GTM
- Última actualización: [Fecha]

## Eventos

| Nombre del Evento | Descripción | Propiedades | Disparador |
|-------------------|-------------|-------------|------------|
| signup_completed | Usuario completa el registro | method, plan | Página de éxito |

## Dimensiones Personalizadas

| Nombre | Alcance | Parámetro |
|--------|---------|-----------|
| user_type | Usuario | user_type |

## Conversiones

| Conversión | Evento | Conteo |
|------------|--------|--------|
| Registro | signup_completed | Una vez por sesión |
```

---

## Preguntas Específicas de la Tarea

1. ¿Qué herramientas estás usando (GA4, Mixpanel, etc.)?
2. ¿Qué acciones clave quieres rastrear?
3. ¿Qué decisiones informarán estos datos?
4. ¿Quién implementa — el equipo de desarrollo o marketing?
5. ¿Hay requisitos de privacidad/consentimiento?
6. ¿Qué ya está siendo rastreado?

---

## Integraciones de Herramientas

Para implementación, ver el [registro de herramientas](../tools/REGISTRY.md). Herramientas de analíticas clave:

| Herramienta | Mejor Para | MCP | Guía |
|-------------|------------|:---:|------|
| **GA4** | Analíticas web, ecosistema Google | ✓ | [ga4.md](../tools/integrations/ga4.md) |
| **Mixpanel** | Analíticas de producto, seguimiento de eventos | — | [mixpanel.md](../tools/integrations/mixpanel.md) |
| **Amplitude** | Analíticas de producto, análisis de cohortes | — | [amplitude.md](../tools/integrations/amplitude.md) |
| **PostHog** | Analíticas open-source, reproducción de sesiones | — | [posthog.md](../tools/integrations/posthog.md) |
| **Segment** | Plataforma de datos de clientes, enrutamiento | — | [segment.md](../tools/integrations/segment.md) |

---

## Habilidades Relacionadas

- **ab-test-setup**: Para el seguimiento de experimentos
- **seo-audit**: Para el análisis de tráfico orgánico
- **page-cro**: Para la optimización de conversiones (usa estos datos)
