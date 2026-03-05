# Plantillas por Tipo de Sitio

Plantillas completas de jerarquía de páginas con árboles ASCII, mapas de URLs y recomendaciones de navegación para los tipos de sitio más comunes.

---

## Sitio de Marketing SaaS

### Jerarquía de Páginas

```
Homepage (/)
├── Features (/features)
│   ├── Feature A (/features/feature-a)
│   ├── Feature B (/features/feature-b)
│   └── Feature C (/features/feature-c)
├── Pricing (/pricing)
├── Customers (/customers)
│   ├── Case Study 1 (/customers/company-name)
│   └── Case Study 2 (/customers/company-name-2)
├── Resources (/resources)
│   ├── Blog (/blog)
│   │   └── [Posts] (/blog/post-slug)
│   ├── Templates (/resources/templates)
│   │   └── [Template] (/resources/templates/template-slug)
│   └── Guides (/resources/guides)
│       └── [Guide] (/resources/guides/guide-slug)
├── Integrations (/integrations)
│   └── [Integration] (/integrations/integration-name)
├── Docs (/docs)
│   ├── Getting Started (/docs/getting-started)
│   ├── Guides (/docs/guides)
│   └── API Reference (/docs/api)
├── About (/about)
│   ├── Careers (/about/careers)
│   └── Contact (/contact)
├── Compare (/compare)
│   └── [Competitor] (/compare/competitor-name)
├── Privacy (/privacy)
└── Terms (/terms)
```

### Mapa de URLs

| Página | URL | Ubicación en Nav | Prioridad |
|------|-----|-------------|----------|
| Homepage | `/` | Cabecera (logo) | Crítica |
| Features | `/features` | Cabecera | Alta |
| Páginas de función | `/features/{slug}` | Dropdown cabecera | Media |
| Pricing | `/pricing` | Cabecera | Crítica |
| Customers | `/customers` | Cabecera | Media |
| Casos de estudio | `/customers/{slug}` | Dropdown Customers | Media |
| Blog | `/blog` | Cabecera (Resources) | Alta |
| Posts de blog | `/blog/{slug}` | — | Media |
| Integrations | `/integrations` | Cabecera | Media |
| Docs | `/docs` | Cabecera | Media |
| Compare | `/compare/{slug}` | Pie de página | Alta (SEO) |
| About | `/about` | Pie de página | Baja |
| CTA Pricing | `/pricing` | Cabecera (botón CTA) | Crítica |

### Navegación

**Cabecera (6 items + CTA)**: Features | Pricing | Customers | Resources | Integrations | Docs | [Get Started]

**Columnas del pie de página**:
- Product: Features, Pricing, Integrations, Changelog, Security
- Resources: Blog, Templates, Guides, Case Studies
- Company: About, Careers, Contact, Press
- Legal: Privacy, Terms, Security

---

## Sitio de Contenido / Blog

### Jerarquía de Páginas

```
Homepage (/)
├── Blog (/blog)
│   ├── [Category: Topic A] (/blog/category/topic-a)
│   ├── [Category: Topic B] (/blog/category/topic-b)
│   ├── [Category: Topic C] (/blog/category/topic-c)
│   └── [Posts] (/blog/post-slug)
├── Newsletter (/newsletter)
├── Resources (/resources)
│   ├── Guides (/resources/guides)
│   │   └── [Guide] (/resources/guides/guide-slug)
│   └── Tools (/resources/tools)
│       └── [Tool] (/resources/tools/tool-slug)
├── About (/about)
├── Contact (/contact)
├── Privacy (/privacy)
└── Terms (/terms)
```

### Mapa de URLs

| Página | URL | Ubicación en Nav | Prioridad |
|------|-----|-------------|----------|
| Homepage | `/` | Cabecera (logo) | Crítica |
| Índice de blog | `/blog` | Cabecera | Alta |
| Categorías | `/blog/category/{slug}` | Dropdown cabecera | Media |
| Posts | `/blog/{slug}` | — | Media |
| Newsletter | `/newsletter` | Cabecera (CTA) | Alta |
| Guides | `/resources/guides` | Cabecera | Media |
| About | `/about` | Cabecera | Baja |

### Navegación

**Cabecera (4 items + CTA)**: Blog | Resources | About | Contact | [Subscribe]

**Barra lateral** (en el blog): Categories, Popular Posts, Newsletter signup

---

## E-Commerce

### Jerarquía de Páginas

```
Homepage (/)
├── Shop (/shop)
│   ├── Category A (/shop/category-a)
│   │   ├── Subcategory (/shop/category-a/subcategory)
│   │   │   └── [Product] (/shop/category-a/subcategory/product-slug)
│   │   └── [Product] (/shop/category-a/product-slug)
│   ├── Category B (/shop/category-b)
│   │   └── [Product] (/shop/category-b/product-slug)
│   └── Category C (/shop/category-c)
│       └── [Product] (/shop/category-c/product-slug)
├── Collections (/collections)
│   └── [Collection] (/collections/collection-slug)
├── Sale (/sale)
├── Blog (/blog)
│   └── [Posts] (/blog/post-slug)
├── About (/about)
│   └── Our Story (/about/our-story)
├── Help (/help)
│   ├── FAQ (/help/faq)
│   ├── Shipping (/help/shipping)
│   ├── Returns (/help/returns)
│   └── Contact (/contact)
├── Cart (/cart)
├── Account (/account)
├── Privacy (/privacy)
└── Terms (/terms)
```

### Mapa de URLs

| Página | URL | Ubicación en Nav | Prioridad |
|------|-----|-------------|----------|
| Homepage | `/` | Cabecera (logo) | Crítica |
| Shop | `/shop` | Cabecera | Crítica |
| Categorías | `/shop/{category}` | Mega menú cabecera | Alta |
| Productos | `/shop/{category}/{product}` | — | Alta |
| Collections | `/collections/{slug}` | Cabecera | Media |
| Sale | `/sale` | Cabecera (destacado) | Alta |
| Cart | `/cart` | Cabecera (ícono) | Crítica |
| Account | `/account` | Cabecera (ícono) | Media |

### Navegación

**Cabecera (5 items + carrito/cuenta)**: Shop (mega menú) | Collections | Sale | Blog | Help | [Ícono Cart] [Ícono Account]

**Mega menú bajo Shop**: Columnas de categorías con productos/imágenes destacados

---

## Sitio de Documentación

### Jerarquía de Páginas

```
Docs Home (/docs)
├── Getting Started (/docs/getting-started)
│   ├── Installation (/docs/getting-started/installation)
│   ├── Quick Start (/docs/getting-started/quick-start)
│   └── Configuration (/docs/getting-started/configuration)
├── Guides (/docs/guides)
│   ├── Guide A (/docs/guides/guide-a)
│   ├── Guide B (/docs/guides/guide-b)
│   └── Guide C (/docs/guides/guide-c)
├── API Reference (/docs/api)
│   ├── Authentication (/docs/api/authentication)
│   ├── Endpoints (/docs/api/endpoints)
│   └── Webhooks (/docs/api/webhooks)
├── Examples (/docs/examples)
│   └── [Example] (/docs/examples/example-slug)
├── Changelog (/docs/changelog)
└── FAQ (/docs/faq)
```

### Mapa de URLs

| Página | URL | Ubicación en Nav | Prioridad |
|------|-----|-------------|----------|
| Docs home | `/docs` | Cabecera | Alta |
| Getting Started | `/docs/getting-started` | Barra lateral (arriba) | Crítica |
| Guides | `/docs/guides` | Barra lateral | Alta |
| API Reference | `/docs/api` | Barra lateral | Alta |
| Changelog | `/docs/changelog` | Barra lateral (abajo) | Baja |

### Navegación

**Cabecera**: Docs | API | Blog | Community | GitHub | [Dashboard]

**Barra lateral** (persistente, izquierda): Getting Started, Guides, API Reference, Examples, Changelog — con subsecciones expandibles

**En la página**: Navegación Anterior/Siguiente al final de cada página de doc

---

## SaaS + Contenido Híbrido

### Jerarquía de Páginas

```
Homepage (/)
├── Product (/product)
│   ├── Feature A (/product/feature-a)
│   ├── Feature B (/product/feature-b)
│   └── Feature C (/product/feature-c)
├── Solutions (/solutions)
│   ├── By Use Case (/solutions/use-case-slug)
│   └── By Industry (/solutions/industry-slug)
├── Pricing (/pricing)
├── Blog (/blog)
│   ├── [Category] (/blog/category/slug)
│   └── [Posts] (/blog/post-slug)
├── Resources (/resources)
│   ├── Guides (/resources/guides)
│   ├── Templates (/resources/templates)
│   ├── Webinars (/resources/webinars)
│   └── Case Studies (/resources/case-studies)
├── Docs (/docs)
│   ├── Getting Started (/docs/getting-started)
│   └── API (/docs/api)
├── Integrations (/integrations)
│   └── [Integration] (/integrations/slug)
├── Compare (/compare)
│   └── [Competitor] (/compare/competitor-slug)
├── About (/about)
│   ├── Careers (/about/careers)
│   └── Contact (/contact)
├── Privacy (/privacy)
└── Terms (/terms)
```

### Navegación

**Cabecera (7 items + CTA)**: Product | Solutions | Pricing | Resources | Blog | Docs | Integrations | [Start Free Trial]

Usar mega menús para Product (lista de funciones), Solutions (casos de uso + industrias) y Resources (blog, guides, templates, webinars, case studies).

---

## Negocio Pequeño / Local

### Jerarquía de Páginas

```
Homepage (/)
├── Services (/services)
│   ├── Service A (/services/service-a)
│   ├── Service B (/services/service-b)
│   └── Service C (/services/service-c)
├── About (/about)
├── Testimonials (/testimonials)
├── Blog (/blog)
│   └── [Posts] (/blog/post-slug)
├── Contact (/contact)
├── Privacy (/privacy)
└── Terms (/terms)
```

### Mapa de URLs

| Página | URL | Ubicación en Nav | Prioridad |
|------|-----|-------------|----------|
| Homepage | `/` | Cabecera (logo) | Crítica |
| Services | `/services` | Cabecera | Alta |
| Páginas de servicio | `/services/{slug}` | Dropdown cabecera | Alta |
| About | `/about` | Cabecera | Media |
| Testimonials | `/testimonials` | Cabecera | Media |
| Blog | `/blog` | Cabecera | Media |
| Contact | `/contact` | Cabecera (CTA) | Alta |

### Navegación

**Cabecera (5 items + CTA)**: Services | About | Testimonials | Blog | [Contact Us]

Mantenerlo simple. Los sitios de negocios pequeños deben ser planos (máximo 1-2 niveles). Cada página debe ser accesible desde la cabecera.
