# Ejemplos de Schema Markup

Ejemplos completos de JSON-LD para tipos de schema comunes.

## Contenidos
- Organization
- WebSite (con SearchAction)
- Article / BlogPosting
- Product
- SoftwareApplication
- FAQPage
- HowTo
- BreadcrumbList
- LocalBusiness
- Event
- Múltiples Tipos de Schema
- Ejemplo de Implementación (Next.js)

## Organization

Para la página de inicio o página "Acerca de" de una empresa/marca.

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Empresa Ejemplo",
  "url": "https://ejemplo.com",
  "logo": "https://ejemplo.com/logo.png",
  "sameAs": [
    "https://twitter.com/ejemplo",
    "https://linkedin.com/company/ejemplo",
    "https://facebook.com/ejemplo"
  ],
  "contactPoint": {
    "@type": "ContactPoint",
    "telephone": "+1-555-555-5555",
    "contactType": "customer service"
  }
}
```

---

## WebSite (con SearchAction)

Para la página de inicio, habilita el cuadro de búsqueda de sitelinks.

```json
{
  "@context": "https://schema.org",
  "@type": "WebSite",
  "name": "Ejemplo",
  "url": "https://ejemplo.com",
  "potentialAction": {
    "@type": "SearchAction",
    "target": {
      "@type": "EntryPoint",
      "urlTemplate": "https://ejemplo.com/buscar?q={search_term_string}"
    },
    "query-input": "required name=search_term_string"
  }
}
```

---

## Article / BlogPosting

Para publicaciones de blog y artículos de noticias.

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "Cómo Implementar Schema Markup",
  "image": "https://ejemplo.com/imagen.jpg",
  "datePublished": "2024-01-15T08:00:00+00:00",
  "dateModified": "2024-01-20T10:00:00+00:00",
  "author": {
    "@type": "Person",
    "name": "Juan García",
    "url": "https://ejemplo.com/autores/juan"
  },
  "publisher": {
    "@type": "Organization",
    "name": "Empresa Ejemplo",
    "logo": {
      "@type": "ImageObject",
      "url": "https://ejemplo.com/logo.png"
    }
  },
  "description": "Una guía completa para implementar schema markup...",
  "mainEntityOfPage": {
    "@type": "WebPage",
    "@id": "https://ejemplo.com/guia-schema"
  }
}
```

---

## Product

Para páginas de productos (e-commerce o SaaS).

```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Widget Premium",
  "image": "https://ejemplo.com/widget.jpg",
  "description": "Nuestro widget más vendido para profesionales",
  "sku": "WIDGET-001",
  "brand": {
    "@type": "Brand",
    "name": "Empresa Ejemplo"
  },
  "offers": {
    "@type": "Offer",
    "url": "https://ejemplo.com/productos/widget",
    "priceCurrency": "USD",
    "price": "99.99",
    "availability": "https://schema.org/InStock",
    "priceValidUntil": "2024-12-31"
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.8",
    "reviewCount": "127"
  }
}
```

---

## SoftwareApplication

Para páginas de productos SaaS y páginas de destino de aplicaciones.

```json
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "Aplicación Ejemplo",
  "applicationCategory": "BusinessApplication",
  "operatingSystem": "Web, iOS, Android",
  "offers": {
    "@type": "Offer",
    "price": "0",
    "priceCurrency": "USD"
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.6",
    "ratingCount": "1250"
  }
}
```

---

## FAQPage

Para páginas con preguntas frecuentes.

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "¿Qué es el schema markup?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "El schema markup es un vocabulario de datos estructurados que ayuda a los motores de búsqueda a entender tu contenido..."
      }
    },
    {
      "@type": "Question",
      "name": "¿Cómo implemento el schema?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "El enfoque recomendado es usar el formato JSON-LD, colocando el script en el head de tu página..."
      }
    }
  ]
}
```

---

## HowTo

Para contenido instructivo y tutoriales.

```json
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "Cómo Agregar Schema Markup a Tu Sitio Web",
  "description": "Una guía paso a paso para implementar schema JSON-LD",
  "totalTime": "PT15M",
  "step": [
    {
      "@type": "HowToStep",
      "name": "Elige tu tipo de schema",
      "text": "Identifica el tipo de schema apropiado para el contenido de tu página...",
      "url": "https://ejemplo.com/guia#paso1"
    },
    {
      "@type": "HowToStep",
      "name": "Escribe el JSON-LD",
      "text": "Crea el markup JSON-LD siguiendo las especificaciones de schema.org...",
      "url": "https://ejemplo.com/guia#paso2"
    },
    {
      "@type": "HowToStep",
      "name": "Agrégalo a tu página",
      "text": "Inserta la etiqueta script en la sección head de tu página...",
      "url": "https://ejemplo.com/guia#paso3"
    }
  ]
}
```

---

## BreadcrumbList

Para cualquier página con navegación de migas de pan.

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Inicio",
      "item": "https://ejemplo.com"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "Blog",
      "item": "https://ejemplo.com/blog"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "Guía de SEO",
      "item": "https://ejemplo.com/blog/guia-seo"
    }
  ]
}
```

---

## LocalBusiness

Para páginas de ubicación de negocios locales.

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "Cafetería Ejemplo",
  "image": "https://ejemplo.com/tienda.jpg",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "Calle Principal 123",
    "addressLocality": "Ciudad de México",
    "addressRegion": "CDMX",
    "postalCode": "06600",
    "addressCountry": "MX"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "19.4326",
    "longitude": "-99.1332"
  },
  "telephone": "+52-55-5555-5555",
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"],
      "opens": "08:00",
      "closes": "18:00"
    }
  ],
  "priceRange": "$$"
}
```

---

## Event

Para páginas de eventos, webinars, conferencias.

```json
{
  "@context": "https://schema.org",
  "@type": "Event",
  "name": "Conferencia Anual de Marketing",
  "startDate": "2024-06-15T09:00:00-07:00",
  "endDate": "2024-06-15T17:00:00-07:00",
  "eventAttendanceMode": "https://schema.org/OnlineEventAttendanceMode",
  "eventStatus": "https://schema.org/EventScheduled",
  "location": {
    "@type": "VirtualLocation",
    "url": "https://ejemplo.com/conferencia"
  },
  "image": "https://ejemplo.com/conferencia.jpg",
  "description": "Únete a nuestra conferencia anual de marketing...",
  "offers": {
    "@type": "Offer",
    "url": "https://ejemplo.com/conferencia/entradas",
    "price": "199",
    "priceCurrency": "USD",
    "availability": "https://schema.org/InStock",
    "validFrom": "2024-01-01"
  },
  "performer": {
    "@type": "Organization",
    "name": "Empresa Ejemplo"
  },
  "organizer": {
    "@type": "Organization",
    "name": "Empresa Ejemplo",
    "url": "https://ejemplo.com"
  }
}
```

---

## Múltiples Tipos de Schema

Combinar múltiples tipos de schema usando @graph.

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Organization",
      "@id": "https://ejemplo.com/#organization",
      "name": "Empresa Ejemplo",
      "url": "https://ejemplo.com"
    },
    {
      "@type": "WebSite",
      "@id": "https://ejemplo.com/#website",
      "url": "https://ejemplo.com",
      "name": "Ejemplo",
      "publisher": {
        "@id": "https://ejemplo.com/#organization"
      }
    },
    {
      "@type": "BreadcrumbList",
      "itemListElement": [...]
    }
  ]
}
```

---

## Ejemplo de Implementación (Next.js)

```jsx
export default function ProductPage({ product }) {
  const schema = {
    "@context": "https://schema.org",
    "@type": "Product",
    name: product.name,
    // ... otras propiedades
  };

  return (
    <>
      <Head>
        <script
          type="application/ld+json"
          dangerouslySetInnerHTML={{ __html: JSON.stringify(schema) }}
        />
      </Head>
      {/* Contenido de la página */}
    </>
  );
}
```
