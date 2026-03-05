# Patrones de Navegación

Patrones de navegación detallados para diferentes tipos de sitio y contextos.

---

## Navegación de Cabecera

### Cabecera Simple (4-6 items)

Mejor para: negocios pequeños, SaaS simple, portfolios.

```
[Logo]   Features   Pricing   Blog   About   [CTA Button]
```

Reglas:
- El logo siempre enlaza a la homepage
- El botón CTA va a la derecha, visualmente diferenciado (botón relleno, color contrastante)
- Items ordenados por prioridad (más visitados primero)
- La página activa recibe un indicador visual (subrayado, negrita, color)

### Cabecera con Mega Menú

Mejor para: SaaS con muchas funciones, e-commerce con categorías, sitios de contenido grandes.

```
[Logo]   Product ▾   Solutions ▾   Resources ▾   Pricing   Docs   [CTA]
```

Cuando se pasa el cursor/clic sobre "Product":

```
┌─────────────────────────────────────────────────┐
│  Features           Platform        Integrations │
│  ─────────          ─────────       ──────────── │
│  Analytics           Security       Slack         │
│  Automation          API            HubSpot       │
│  Reporting           Compliance     Salesforce    │
│  Dashboards                         Zapier        │
│                                                   │
│  [See all features →]                             │
└─────────────────────────────────────────────────┘
```

Reglas del mega menú:
- Máximo 2-4 columnas
- Agrupar items de forma lógica (por área de función, caso de uso o audiencia)
- Incluir un link "Ver todo" al final
- No anidar dropdowns dentro de mega menús
- Mostrar descripciones para items cuando las etiquetas solas no sean claras

### Navegación Dividida

Mejor para: apps con navegación tanto de marketing como de producto.

```
[Logo]   Features   Pricing   Blog        [Login]   [Sign Up]
├── Nav de marketing (izquierda) ───┘          └── Nav de auth (derecha) ──┤
```

El lado derecho gestiona las acciones de autenticación. El lado izquierdo gestiona la navegación entre páginas.

---

## Navegación de Pie de Página

### Pie de Página por Columnas (Estándar)

Mejor para: la mayoría de los sitios. Organiza los links en 3-5 columnas temáticas.

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│  Product          Resources        Company       Legal   │
│  ─────────        ──────────       ─────────     ─────   │
│  Features         Blog             About         Privacy │
│  Pricing          Guides           Careers       Terms   │
│  Integrations     Templates        Contact       GDPR    │
│  Changelog        Case Studies     Press                 │
│  Security         Webinars         Partners              │
│                                                          │
│  [Logo]  © 2026 Company Name                             │
│  Social: [Twitter] [LinkedIn] [GitHub]                   │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

### Pie de Página Minimalista

Mejor para: sitios simples, landing pages.

```
┌──────────────────────────────────────────────────────────┐
│  [Logo]                                                  │
│  © 2026 Company  ·  Privacy  ·  Terms  ·  Contact        │
└──────────────────────────────────────────────────────────┘
```

### Pie de Página Expandido

Mejor para: sitios que usan el pie de página para SEO (páginas de comparación, páginas de ubicación, links de recursos).

```
┌──────────────────────────────────────────────────────────┐
│  Product     Resources    Compare         Use Cases      │
│  Features    Blog         vs Competitor A  For Startups  │
│  Pricing     Guides       vs Competitor B  For Enterprise│
│  API         Templates    vs Competitor C  For Agencies  │
│                                                          │
│  Integrations             Popular Posts                  │
│  Slack       Zapier       How to Do X                    │
│  HubSpot     Salesforce   Guide to Y                     │
│                           Template: Z                    │
│                                                          │
│  [Logo]  © 2026  ·  Privacy  ·  Terms  ·  Security      │
└──────────────────────────────────────────────────────────┘
```

---

## Navegación de Barra Lateral

### Barra Lateral de Documentación

Barra lateral izquierda persistente con secciones colapsables.

```
Getting Started
  ├── Installation
  ├── Quick Start
  └── Configuration

Guides
  ├── Authentication
  ├── Data Models
  └── Deployment

API Reference
  ├── REST API
  │   ├── Users
  │   ├── Projects
  │   └── Webhooks
  └── GraphQL

Examples
  ├── Next.js
  ├── Rails
  └── Python

Changelog
```

Reglas:
- Página actual resaltada
- Secciones colapsables (expandidas por defecto para la sección activa)
- Búsqueda en la parte superior de la barra lateral
- Navegación "Anterior / Siguiente" en la parte inferior del área de contenido
- Fija al hacer scroll (no desaparece al bajar)

### Barra Lateral de Categorías del Blog

```
Categories
  ├── SEO (24)
  ├── CRO (18)
  ├── Content (15)
  ├── Paid Ads (12)
  └── Analytics (9)

Popular Posts
  ├── How to Improve SEO
  ├── Landing Page Guide
  └── Analytics Setup

Newsletter
  └── [Email signup form]
```

---

## Breadcrumbs

### Formato Estándar

```
Home > Features > Analytics
Home > Blog > SEO Category > How to Do Keyword Research
Home > Docs > API Reference > Authentication
```

Reglas:
- Separador: `>` o `/` (ser consistente)
- Cada segmento es un link excepto la página actual
- La página actual es texto plano (sin link)
- No incluir la página actual si el título ya es visible como H1

### Con Marcado Schema

```html
<nav aria-label="Breadcrumb">
  <ol itemscope itemtype="https://schema.org/BreadcrumbList">
    <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
      <a itemprop="item" href="/"><span itemprop="name">Home</span></a>
      <meta itemprop="position" content="1" />
    </li>
    <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
      <a itemprop="item" href="/features"><span itemprop="name">Features</span></a>
      <meta itemprop="position" content="2" />
    </li>
    <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
      <span itemprop="name">Analytics</span>
      <meta itemprop="position" content="3" />
    </li>
  </ol>
</nav>
```

O usar JSON-LD (recomendado):

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://example.com/" },
    { "@type": "ListItem", "position": 2, "name": "Features", "item": "https://example.com/features" },
    { "@type": "ListItem", "position": 3, "name": "Analytics" }
  ]
}
```

---

## Navegación Móvil

### Menú Hamburguesa

Estándar para móvil. Todos los items de nav se colapsan en un ícono de menú.

Reglas:
- Ícono hamburguesa (tres líneas) en la parte superior derecha o izquierda
- Panel a pantalla completa o deslizante
- Botón CTA visible sin abrir el menú (cabecera sticky)
- Búsqueda accesible desde el menú móvil
- Patrón acordeón para items anidados

### Barra de Pestañas Inferior

Mejor para: web apps, PWAs, productos mobile-first.

```
┌──────────────────────────────────────┐
│                                      │
│           [Page Content]             │
│                                      │
├──────────────────────────────────────┤
│  Home    Search    Create    Profile │
│   🏠       🔍        ➕       👤    │
└──────────────────────────────────────┘
```

Reglas:
- Máximo 3-5 items
- Íconos + etiquetas (no solo íconos)
- Estado activo claramente indicado
- La acción más importante al centro

---

## Anti-Patrones

### Cosas a Evitar

- **Demasiados items en la cabecera** (8+): causa parálisis de decisión, la nav se vuelve ilegible en pantallas más pequeñas
- **Dropdowns dentro de dropdowns**: menús desplegables anidados dentro de otros menús desplegables
- **Íconos misteriosos**: íconos sin etiquetas — los usuarios no saben qué significan
- **Nav primaria oculta**: enterrar páginas importantes en menús hamburguesa en escritorio
- **Nav inconsistente entre páginas**: la nav debe ser idéntica en todo el sitio (excepto app vs. marketing)
- **Sin consideración móvil**: nav de escritorio que no se traduce bien a móvil
- **Pie de página como vertedero de sitemap**: 50+ links en el pie sin organización
- **Breadcrumbs que no coinciden con URLs**: el breadcrumb dice "Products > Widget" pero la URL es `/shop/widget-pro`

### Soluciones Comunes

| Problema | Solución |
|---------|-----|
| Demasiados items de nav | Agrupar en dropdowns o mega menús |
| Los usuarios no encuentran páginas | Agregar búsqueda, mejorar las etiquetas |
| Alto rebote desde la nav | Simplificar opciones, usar etiquetas más claras |
| Páginas SEO sin enlazar | Agregar al pie de página o secciones de recursos |
| La nav móvil está rota | Probar en dispositivos reales, usar el patrón hamburguesa |

---

## Navegación para SEO

Los links internos en la navegación transfieren PageRank. Usar esto estratégicamente:

- **Los links de la nav de cabecera son los más fuertes** — poner las páginas más importantes aquí
- **Los links del pie de página transfieren menos valor** pero igual importan — buenos para páginas de comparación, páginas de ubicación
- **Los links de la barra lateral** ayudan con la autoridad a nivel de sección — buenos para categorías de blog, secciones de docs
- **Los breadcrumbs** proporcionan señales estructurales a los motores de búsqueda — implementar con marcado schema
- **No usar nav solo con JavaScript** — los motores de búsqueda necesitan links HTML rastreables
- **Usar texto de anclaje descriptivo** — "Analytics Features" no solo "Features"
