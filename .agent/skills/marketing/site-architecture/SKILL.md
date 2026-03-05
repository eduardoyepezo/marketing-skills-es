---
name: site-architecture
description: Cuando el usuario quiere planificar, mapear o reestructurar la jerarquía de páginas, navegación, estructura de URLs o enlazado interno de su sitio web. También usar cuando el usuario menciona "sitemap," "mapa del sitio," "sitemap visual," "estructura del sitio," "jerarquía de páginas," "arquitectura de información," "IA," "diseño de navegación," "estructura de URLs," "breadcrumbs," "estrategia de enlazado interno," "planificación del sitio web," "qué páginas necesito," "cómo debo organizar mi sitio," o "navegación del sitio." Usar cuando alguien está planificando qué páginas debe tener un sitio y cómo se conectan. NO para sitemaps XML (eso es SEO técnico — ver seo-audit). Para auditorías de SEO, ver seo-audit. Para datos estructurados, ver schema-markup.
metadata:
  version: 1.1.0
---

# Arquitectura de Sitio

Eres un experto en arquitectura de información. Tu objetivo es ayudar a planificar la estructura del sitio web—jerarquía de páginas, navegación, patrones de URL y enlazado interno—para que el sitio sea intuitivo para los usuarios y esté optimizado para los motores de búsqueda.

## Antes de Planificar

**Revisar el contexto de marketing primero:**
Si existe `.agents/product-marketing-context.md` (o `.claude/product-marketing-context.md` en configuraciones anteriores), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información no cubierta o específica para esta tarea.

Recopila este contexto (pregunta si no se proporciona):

### 1. Contexto de Negocio
- ¿Qué hace la empresa?
- ¿Cuáles son las audiencias principales?
- ¿Cuáles son los 3 objetivos principales para el sitio? (conversiones, tráfico SEO, educación, soporte)

### 2. Estado Actual
- ¿Sitio nuevo o reestructurando uno existente?
- Si reestructurando: ¿qué está roto? (rebote alto, mal SEO, los usuarios no encuentran cosas)
- ¿URLs existentes que deben preservarse (para redirecciones)?

### 3. Tipo de Sitio
- Sitio de marketing SaaS
- Sitio de contenido/blog
- E-commerce
- Documentación
- Híbrido (SaaS + contenido)
- Negocio pequeño / local

### 4. Inventario de Contenido
- ¿Cuántas páginas existen o están planeadas?
- ¿Cuáles son las páginas más importantes? (por tráfico, conversiones o valor de negocio)
- ¿Alguna sección o expansión planeada?

---

## Tipos de Sitio y Puntos de Partida

| Tipo de Sitio | Profundidad Típica | Secciones Clave | Patrón de URL |
|-----------|--------------|--------------|-------------|
| Marketing SaaS | 2-3 niveles | Home, Funciones, Precios, Blog, Docs | `/funciones/nombre`, `/blog/slug` |
| Contenido/blog | 2-3 niveles | Home, Blog, Categorías, Sobre nosotros | `/blog/slug`, `/categoria/slug` |
| E-commerce | 3-4 niveles | Home, Categorías, Productos, Carrito | `/categoria/subcategoria/producto` |
| Documentación | 3-4 niveles | Home, Guías, Referencia API | `/docs/seccion/pagina` |
| SaaS+contenido híbrido | 3-4 niveles | Home, Producto, Blog, Recursos, Docs | `/producto/funcion`, `/blog/slug` |
| Negocio pequeño | 1-2 niveles | Home, Servicios, Sobre nosotros, Contacto | `/servicios/nombre` |

**Para plantillas completas de jerarquía de páginas**: Ver [references/site-type-templates.md](references/site-type-templates.md)

---

## Diseño de Jerarquía de Páginas

### La Regla de los 3 Clics

Los usuarios deben llegar a cualquier página importante en 3 clics desde la homepage. Esto no es absoluto, pero si las páginas críticas están enterradas a 4+ niveles de profundidad, algo está mal.

### Plano vs. Profundo

| Enfoque | Mejor Para | Compensación |
|----------|----------|---------|
| Plano (2 niveles) | Sitios pequeños, portfolios | Simple pero no escala |
| Moderado (3 niveles) | Mayoría de SaaS, sitios de contenido | Buen balance de profundidad y encontrabilidad |
| Profundo (4+ niveles) | E-commerce, docs grandes | Escala pero arriesga enterrar contenido |

**Regla general**: Ir tan plano como sea posible manteniendo la navegación limpia. Si un dropdown de nav tiene más de 20 items, agregar un nivel de jerarquía.

### Niveles de Jerarquía

| Nivel | Qué Es | Ejemplo |
|-------|-----------|---------| 
| L0 | Homepage | `/` |
| L1 | Secciones primarias | `/funciones`, `/blog`, `/precios` |
| L2 | Páginas de sección | `/funciones/analiticas`, `/blog/guia-seo` |
| L3+ | Páginas de detalle | `/docs/api/autenticacion` |

### Formato de Árbol ASCII

Usar este formato para jerarquías de páginas:

```
Homepage (/)
├── Funciones (/funciones)
│   ├── Analíticas (/funciones/analiticas)
│   ├── Automatización (/funciones/automatizacion)
│   └── Integraciones (/funciones/integraciones)
├── Precios (/precios)
├── Blog (/blog)
│   ├── [Categoría: SEO] (/blog/categoria/seo)
│   └── [Categoría: CRO] (/blog/categoria/cro)
├── Recursos (/recursos)
│   ├── Casos de Estudio (/recursos/casos-de-estudio)
│   └── Plantillas (/recursos/plantillas)
├── Docs (/docs)
│   ├── Primeros Pasos (/docs/primeros-pasos)
│   └── Referencia API (/docs/api)
├── Sobre Nosotros (/sobre-nosotros)
│   └── Carreras (/sobre-nosotros/carreras)
└── Contacto (/contacto)
```

**Cuándo usar ASCII vs Mermaid**:
- ASCII: borradores rápidos de jerarquía, contextos solo de texto, estructuras simples
- Mermaid: presentaciones visuales, relaciones complejas, mostrando zonas de nav o patrones de enlazado

---

## Diseño de Navegación

### Tipos de Navegación

| Tipo de Nav | Propósito | Ubicación |
|----------|---------|-----------| 
| Nav de cabecera | Navegación primaria, siempre visible | Parte superior de cada página |
| Menús dropdown | Organizar subpáginas bajo el padre | Se expande desde items del encabezado |
| Nav de pie de página | Links secundarios, legal, sitemap | Parte inferior de cada página |
| Nav de barra lateral | Navegación de sección (docs, blog) | Lado izquierdo dentro de una sección |
| Breadcrumbs | Mostrar ubicación actual en jerarquía | Debajo del encabezado, sobre el contenido |
| Links contextuales | Contenido relacionado, próximos pasos | Dentro del contenido de la página |

### Reglas de Navegación del Encabezado

- **Máximo 4-7 items** en el nav primario (más causa parálisis de decisión)
- **Botón CTA** va más a la derecha (ej., "Iniciar Prueba Gratis," "Comenzar")
- **Logo** enlaza a la homepage (lado izquierdo)
- **Orden por prioridad**: páginas más importantes/visitadas primero
- Si tienes un mega menú, limitar a 3-4 columnas

### Organización del Pie de Página

Agrupar links del pie de página en columnas:
- **Producto**: Funciones, Precios, Integraciones, Changelog
- **Recursos**: Blog, Casos de Estudio, Plantillas, Docs
- **Empresa**: Sobre Nosotros, Carreras, Contacto, Prensa
- **Legal**: Privacidad, Términos, Seguridad

### Formato de Breadcrumb

```
Home > Funciones > Analíticas
Home > Blog > Categoría SEO > Título del Post
```

Los breadcrumbs deben reflejar la jerarquía de URL. Cada segmento del breadcrumb debe ser un link clicable excepto la página actual.

**Para patrones de navegación detallados**: Ver [references/navigation-patterns.md](references/navigation-patterns.md)

---

## Estructura de URLs

### Principios de Diseño

1. **Legibles por humanos** — `/funciones/analiticas` no `/f/a123`
2. **Guiones, no guiones bajos** — `/blog/guia-seo` no `/blog/guia_seo`
3. **Reflejar la jerarquía** — La ruta URL debe coincidir con la estructura del sitio
4. **Política consistente de barra inclinada** — elegir una (con o sin) y aplicarla
5. **Minúsculas siempre** — `/SobreNosotros` debe redirigir a `/sobre-nosotros`
6. **Corta pero descriptiva** — `/blog/como-mejorar-las-tasas-de-conversion-de-landing-page` es demasiado larga; `/blog/conversiones-landing-page` es mejor

### Patrones de URL por Tipo de Página

| Tipo de Página | Patrón | Ejemplo |
|-----------|---------|---------| 
| Homepage | `/` | `ejemplo.com` |
| Página de función | `/funciones/{nombre}` | `/funciones/analiticas` |
| Precios | `/precios` | `/precios` |
| Post de blog | `/blog/{slug}` | `/blog/guia-seo` |
| Categoría de blog | `/blog/categoria/{slug}` | `/blog/categoria/seo` |
| Caso de estudio | `/clientes/{slug}` | `/clientes/empresa-xyz` |
| Documentación | `/docs/{seccion}/{pagina}` | `/docs/api/autenticacion` |
| Legal | `/{pagina}` | `/privacidad`, `/terminos` |
| Landing page | `/{slug}` o `/lp/{slug}` | `/prueba-gratis`, `/lp/webinar` |
| Comparación | `/comparar/{competidor}` o `/vs/{competidor}` | `/comparar/nombre-competidor` |
| Integración | `/integraciones/{nombre}` | `/integraciones/slack` |
| Plantilla | `/plantillas/{slug}` | `/plantillas/plan-de-marketing` |

### Errores Comunes

- **Fechas en URLs de blog** — `/blog/2024/01/15/titulo-del-post` no agrega valor y hace las URLs largas. Usar `/blog/titulo-del-post`.
- **Anidamiento excesivo** — `/productos/categoria/subcategoria/articulo/detalle` es demasiado profundo. Aplanar donde sea posible.
- **Cambiar URLs sin redirecciones** — Cada URL antigua necesita una redirección 301 a su nueva URL. Sin ellas, pierdes equidad de backlinks y creas páginas rotas.
- **IDs en URLs** — `/producto/12345` no es legible por humanos. Usar slugs.
- **Parámetros de consulta para contenido** — `/blog?id=123` debería ser `/blog/titulo-del-post`.
- **Patrones inconsistentes** — No mezclar `/funciones/analiticas` y `/producto/automatizacion`. Elegir un padre.

### Alineación Breadcrumb-URL

El rastro del breadcrumb debe reflejar la ruta URL:

| URL | Breadcrumb |
|-----|-----------| 
| `/funciones/analiticas` | Home > Funciones > Analíticas |
| `/blog/guia-seo` | Home > Blog > Guía SEO |
| `/docs/api/auth` | Home > Docs > API > Autenticación |

---

## Salida Visual del Sitemap (Mermaid)

Usar Mermaid `graph TD` para sitemaps visuales. Esto hace las relaciones de jerarquía claras y puede anotar zonas de navegación.

### Jerarquía Básica

```mermaid
graph TD
    HOME[Homepage] --> FEAT[Funciones]
    HOME --> PRICE[Precios]
    HOME --> BLOG[Blog]
    HOME --> ABOUT[Sobre Nosotros]

    FEAT --> F1[Analíticas]
    FEAT --> F2[Automatización]
    FEAT --> F3[Integraciones]

    BLOG --> B1[Post 1]
    BLOG --> B2[Post 2]
```

### Con Zonas de Navegación

```mermaid
graph TD
    subgraph Nav Cabecera
        HOME[Homepage]
        FEAT[Funciones]
        PRICE[Precios]
        BLOG[Blog]
        CTA[Comenzar]
    end

    subgraph Nav Pie de Página
        ABOUT[Sobre Nosotros]
        CAREERS[Carreras]
        CONTACT[Contacto]
        PRIVACY[Privacidad]
    end

    HOME --> FEAT
    HOME --> PRICE
    HOME --> BLOG
    HOME --> ABOUT

    FEAT --> F1[Analíticas]
    FEAT --> F2[Automatización]
```

**Para más plantillas Mermaid**: Ver [references/mermaid-templates.md](references/mermaid-templates.md)

---

## Estrategia de Enlazado Interno

### Tipos de Enlace

| Tipo | Propósito | Ejemplo |
|------|---------|---------| 
| Navegacional | Mover entre secciones | Links de encabezado, pie de página, barra lateral |
| Contextual | Contenido relacionado dentro del texto | "Aprende más sobre [analíticas](/funciones/analiticas)" |
| Hub-and-spoke | Conectar contenido de clúster al hub | Posts de blog enlazando a página pilar |
| Entre secciones | Conectar páginas relacionadas entre secciones | Página de función enlazando a caso de estudio relacionado |

### Reglas de Enlazado Interno

1. **Sin páginas huérfanas** — cada página debe tener al menos un enlace interno apuntando a ella
2. **Texto de anclaje descriptivo** — "nuestras funciones de analíticas" no "haz clic aquí"
3. **5-10 enlaces internos por 1000 palabras** de contenido (aproximadamente)
4. **Enlazar a páginas importantes más frecuentemente** — homepage, páginas de funciones clave, precios
5. **Usar breadcrumbs** — enlaces internos gratuitos en cada página
6. **Secciones de contenido relacionado** — "Posts Relacionados" o "También podría interesarte" al final de la página

### Modelo Hub-and-Spoke

Para sitios con mucho contenido, organizar alrededor de páginas hub:

```
Hub: /blog/guia-seo (descripción general completa)
├── Spoke: /blog/investigacion-de-keywords (enlaza de vuelta al hub)
├── Spoke: /blog/seo-on-page (enlaza de vuelta al hub)
├── Spoke: /blog/seo-tecnico (enlaza de vuelta al hub)
└── Spoke: /blog/construccion-de-enlaces (enlaza de vuelta al hub)
```

Cada spoke enlaza de vuelta al hub. El hub enlaza a todos los spokes. Los spokes se enlazan entre sí donde sea relevante.

### Lista de Verificación de Auditoría de Enlazado

- [ ] Cada página tiene al menos un enlace interno entrante
- [ ] Sin enlaces internos rotos (404s)
- [ ] El texto de anclaje es descriptivo (no "haz clic aquí" o "leer más")
- [ ] Las páginas importantes tienen más enlaces internos entrantes
- [ ] Los breadcrumbs están implementados en todas las páginas
- [ ] Los links de contenido relacionado existen en los posts de blog
- [ ] Los links entre secciones conectan funciones con casos de estudio, blog con páginas de producto

---

## Formato de Salida

Al crear un plan de arquitectura de sitio, proporcionar estos entregables:

### 1. Jerarquía de Páginas (Árbol ASCII)
Estructura completa del sitio con URLs en cada nodo. Usar el formato de árbol ASCII de la sección Diseño de Jerarquía de Páginas.

### 2. Sitemap Visual (Mermaid)
Diagrama Mermaid mostrando relaciones de páginas y zonas de navegación. Usar `graph TD` con subgrafos para zonas de nav donde sea útil.

### 3. Tabla de Mapa de URLs

| Página | URL | Padre | Ubicación en Nav | Prioridad |
|------|-----|--------|-------------|---------|
| Homepage | `/` | — | Cabecera | Alta |
| Funciones | `/funciones` | Homepage | Cabecera | Alta |
| Analíticas | `/funciones/analiticas` | Funciones | Dropdown cabecera | Media |
| Precios | `/precios` | Homepage | Cabecera | Alta |
| Blog | `/blog` | Homepage | Cabecera | Media |

### 4. Especificación de Navegación
- Items de nav de cabecera (ordenados, con CTA)
- Secciones y links del pie de página
- Nav de barra lateral (si aplica)
- Notas de implementación de breadcrumbs

### 5. Plan de Enlazado Interno
- Páginas hub y sus spokes
- Oportunidades de links entre secciones
- Auditoría de páginas huérfanas (si se reestructura)
- Links recomendados por página clave

---

## Preguntas Específicas de la Tarea

1. ¿Es un sitio nuevo o estás reestructurando uno existente?
2. ¿Qué tipo de sitio es? (SaaS, contenido, e-commerce, docs, híbrido, negocio pequeño)
3. ¿Cuántas páginas existen o están planeadas?
4. ¿Cuáles son las 5 páginas más importantes del sitio?
5. ¿Hay URLs existentes que necesiten preservarse o redirigirse?
6. ¿Quiénes son las audiencias principales y qué intentan lograr en el sitio?

---

## Habilidades Relacionadas

- **content-strategy**: Para planificar qué contenido crear y clusters de temas
- **programmatic-seo**: Para construir páginas de SEO a escala con plantillas y datos
- **seo-audit**: Para SEO técnico, optimización on-page y problemas de indexación
- **page-cro**: Para optimizar páginas individuales para conversión
- **schema-markup**: Para implementar datos estructurados de breadcrumb y navegación del sitio
- **competitor-alternatives**: Para marcos de páginas de comparación y patrones de URL
