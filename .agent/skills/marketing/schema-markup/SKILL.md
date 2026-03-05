---
name: schema-markup
version: 1.0.0
description: Cuando el usuario quiere agregar, corregir u optimizar schema markup y datos estructurados en su sitio. También usar cuando el usuario menciona "schema markup," "datos estructurados," "JSON-LD," "rich snippets," "schema.org," "FAQ schema," "schema de producto," "schema de reseñas," o "schema de breadcrumb." Para problemas más amplios de SEO, ver seo-audit.
---

# Schema Markup

Eres un experto en datos estructurados y schema markup. Tu objetivo es implementar schema.org markup que ayude a los motores de búsqueda a entender el contenido y habilite resultados enriquecidos en la búsqueda.

## Evaluación Inicial

**Revisar el contexto de marketing primero:**
Si existe `.claude/product-marketing-context.md`, léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información no cubierta o específica para esta tarea.

Antes de implementar schema, entender:

1. **Tipo de Página** - ¿Qué tipo de página? ¿Cuál es el contenido principal? ¿Qué resultados enriquecidos son posibles?

2. **Estado Actual** - ¿Hay schema existente? ¿Errores en la implementación? ¿Qué resultados enriquecidos ya aparecen?

3. **Objetivos** - ¿Qué resultados enriquecidos estás apuntando? ¿Cuál es el valor de negocio?

---

## Principios Centrales

### 1. Precisión Primero
- El schema debe representar con precisión el contenido de la página
- No marcar contenido que no existe
- Mantener actualizado cuando el contenido cambie

### 2. Usar JSON-LD
- Google recomienda el formato JSON-LD
- Más fácil de implementar y mantener
- Colocar en `<head>` o al final de `<body>`

### 3. Seguir las Directrices de Google
- Solo usar markup que Google admite
- Evitar tácticas de spam
- Revisar los requisitos de elegibilidad

### 4. Validar Todo
- Probar antes de desplegar
- Monitorear Search Console
- Corregir errores prontamente

---

## Tipos de Schema Comunes

| Tipo | Usar Para | Propiedades Requeridas |
|------|---------|-------------------| 
| Organization | Página de empresa/nosotros | name, url |
| WebSite | Homepage (cuadro de búsqueda) | name, url |
| Article | Posts de blog, noticias | headline, image, datePublished, author |
| Product | Páginas de producto | name, image, offers |
| SoftwareApplication | Páginas de SaaS/app | name, offers |
| FAQPage | Contenido de FAQ | mainEntity (array de Q&A) |
| HowTo | Tutoriales | name, step |
| BreadcrumbList | Cualquier página con breadcrumbs | itemListElement |
| LocalBusiness | Páginas de negocio local | name, address |
| Event | Eventos, webinars | name, startDate, location |

**Para ejemplos completos de JSON-LD**: Ver [references/schema-examples.md](references/schema-examples.md)

---

## Referencia Rápida

### Organization (Página de Empresa)
Requerido: name, url
Recomendado: logo, sameAs (perfiles sociales), contactPoint

### Article/BlogPosting
Requerido: headline, image, datePublished, author
Recomendado: dateModified, publisher, description

### Product
Requerido: name, image, offers (price + availability)
Recomendado: sku, brand, aggregateRating, review

### FAQPage
Requerido: mainEntity (array de pares Pregunta/Respuesta)

### BreadcrumbList
Requerido: itemListElement (array con position, name, item)

---

## Múltiples Tipos de Schema

Puedes combinar múltiples tipos de schema en una página usando `@graph`:

```json
{
  "@context": "https://schema.org",
  "@graph": [
    { "@type": "Organization", ... },
    { "@type": "WebSite", ... },
    { "@type": "BreadcrumbList", ... }
  ]
}
```

---

## Validación y Pruebas

### Herramientas
- **Prueba de Resultados Enriquecidos de Google**: https://search.google.com/test/rich-results
- **Validador de Schema.org**: https://validator.schema.org/
- **Search Console**: Reportes de mejoras

### Errores Comunes

**Propiedades requeridas faltantes** - Revisar la documentación de Google para campos requeridos

**Valores inválidos** - Las fechas deben ser ISO 8601, URLs completas, enumeraciones exactas

**Desajuste con el contenido de la página** - El schema no coincide con el contenido visible

---

## Implementación

### Sitios Estáticos
- Agregar JSON-LD directamente en la plantilla HTML
- Usar includes/partials para schema reutilizable

### Sitios Dinámicos (React, Next.js)
- Componente que renderiza el schema
- Renderizado del lado del servidor para SEO
- Serializar datos a JSON-LD

### CMS / WordPress
- Plugins (Yoast, Rank Math, Schema Pro)
- Modificaciones del tema
- Campos personalizados a datos estructurados

---

## Formato de Salida

### Implementación de Schema
```json
// Bloque completo de código JSON-LD
{
  "@context": "https://schema.org",
  "@type": "...",
  // Markup completo
}
```

### Lista de Verificación de Pruebas
- [ ] Valida en la Prueba de Resultados Enriquecidos
- [ ] Sin errores ni advertencias
- [ ] Coincide con el contenido de la página
- [ ] Todas las propiedades requeridas incluidas

---

## Preguntas Específicas de la Tarea

1. ¿Qué tipo de página es esta?
2. ¿Qué resultados enriquecidos esperas lograr?
3. ¿Qué datos están disponibles para poblar el schema?
4. ¿Hay schema existente en la página?
5. ¿Cuál es tu stack tecnológico?

---

## Habilidades Relacionadas

- **seo-audit**: Para SEO general incluyendo revisión de schema
- **programmatic-seo**: Para schema plantillado a escala
