# Arquitectura de Contenido para Páginas de Competidores

Cómo estructurar y mantener los datos de competidores para páginas de comparación escalables.

## Contenidos
- Datos Centralizados de Competidores
- Plantilla de Datos de Competidor
- Datos de Tu Producto
- Generación de Páginas
- Estructura de Páginas de Índice (índice de alternativas, índice de comparaciones vs, mejores prácticas de páginas de índice)
- Navegación en el Pie de Página

## Datos Centralizados de Competidores

Crear una fuente única de verdad para cada competidor:

```
competitor_data/
├── notion.md
├── airtable.md
├── monday.md
└── ...
```

---

## Plantilla de Datos de Competidor

Por cada competidor, documentar:

```yaml
name: Notion
website: notion.so
tagline: "The all-in-one workspace"
founded: 2016
headquarters: San Francisco

# Posicionamiento
primary_use_case: "docs + light databases"
target_audience: "teams wanting flexible workspace"
market_position: "premium, feature-rich"

# Precios
pricing_model: per-seat
free_tier: true
free_tier_limits: "limited blocks, 1 user"
starter_price: $8/user/month
business_price: $15/user/month
enterprise: custom

# Características (calificar del 1 al 5 o describir)
features:
  documents: 5
  databases: 4
  project_management: 3
  collaboration: 4
  integrations: 3
  mobile_app: 3
  offline_mode: 2
  api: 4

# Fortalezas (ser honesto)
strengths:
  - Extremadamente flexible y personalizable
  - Interfaz hermosa y moderna
  - Sólido ecosistema de plantillas
  - Comunidad activa

# Debilidades (ser justo)
weaknesses:
  - Puede ser lento con bases de datos grandes
  - Curva de aprendizaje para funciones avanzadas
  - Automatizaciones limitadas comparado con herramientas dedicadas
  - El modo sin conexión es limitado

# Mejor para
best_for:
  - Equipos que quieren un espacio de trabajo todo en uno
  - Flujos de trabajo con mucho contenido
  - Equipos centrados en documentación
  - Startups y equipos pequeños

# No ideal para
not_ideal_for:
  - Necesidades complejas de gestión de proyectos
  - Bases de datos grandes (miles de filas)
  - Equipos que necesitan modo sin conexión robusto
  - Empresas con cumplimiento estricto

# Quejas comunes (de reseñas)
common_complaints:
  - "Se vuelve lento con mucho contenido"
  - "Es difícil encontrar cosas a medida que el espacio de trabajo crece"
  - "La app móvil es torpe"

# Notas de migración
migration_from:
  difficulty: medium
  data_export: "Markdown, CSV, HTML"
  what_transfers: "Pages, databases"
  what_doesnt: "Automations, integrations setup"
  time_estimate: "1-3 days for small team"
```

---

## Datos de Tu Producto

La misma estructura para ti mismo — sé honesto:

```yaml
name: [Tu Producto]
# ... los mismos campos

strengths:
  - [Tus fortalezas reales]

weaknesses:
  - [Tus debilidades honestas]

best_for:
  - [Tus clientes ideales]

not_ideal_for:
  - [Quién debería usar otra cosa]
```

---

## Generación de Páginas

Cada página toma datos de los datos centralizados:

- **Página Alternativa a [Competidor]**: Toma datos del competidor + tus datos
- **Página Alternativas a [Competidor]**: Toma datos del competidor + tus datos + otras alternativas
- **Página Tú vs [Competidor]**: Toma tus datos + datos del competidor
- **Página [A] vs [B]**: Toma datos de ambos competidores + tus datos

**Beneficios**:
- Actualiza los precios del competidor una vez, se actualiza en todos lados
- Agrega una nueva comparación de características una vez, aparece en todas las páginas
- Precisión consistente en todas las páginas
- Más fácil de mantener a escala

---

## Estructura de Páginas de Índice

### Índice de Alternativas

**URL**: `/alternatives` o `/alternatives/index`

**Propósito**: Lista todas las páginas de "Alternativa a [Competidor]"

**Estructura de la página**:
1. Título: "[Tu Producto] como Alternativa"
2. Breve introducción sobre por qué las personas cambian a ti
3. Lista de todas las páginas de alternativas con:
   - Nombre/logo del competidor
   - Resumen en una línea del diferenciador clave vs. ese competidor
   - Enlace a la comparación completa
4. Razones comunes por las que cambian (agregadas)
5. CTA

**Ejemplo**:
```markdown
## Explora [Tu Producto] como Alternativa

¿Buscas cambiar? Mira cómo [Tu Producto] se compara con las herramientas que estás evaluando:

- **[Alternativa a Notion](/alternatives/notion)** — Mejor para equipos que necesitan [X]
- **[Alternativa a Airtable](/alternatives/airtable)** — Mejor para equipos que necesitan [Y]
- **[Alternativa a Monday](/alternatives/monday)** — Mejor para equipos que necesitan [Z]
```

---

### Índice de Comparaciones Vs

**URL**: `/vs` o `/compare`

**Propósito**: Lista todas las páginas de "Tú vs [Competidor]" y "[A] vs [B]"

**Estructura de la página**:
1. Título: "Compara [Tu Producto]"
2. Sección: "[Tu Producto] vs Competidores" — lista de comparaciones directas
3. Sección: "Comparaciones Cara a Cara" — lista de páginas [A] vs [B]
4. Breve nota metodológica
5. CTA

---

### Mejores Prácticas de Páginas de Índice

**Mantenerlas actualizadas**: Cuando agregas una nueva página de comparación, agrégala al índice correspondiente.

**Enlazado interno**:
- Enlazar del índice → páginas individuales
- Enlazar de páginas individuales → de vuelta al índice
- Enlazar transversalmente entre comparaciones relacionadas

**Valor SEO**:
- Las páginas de índice pueden posicionarse para términos amplios como "comparaciones de herramientas de gestión de proyectos"
- Transmiten autoridad de enlace a páginas de comparación individuales
- Ayudan a los motores de búsqueda a descubrir todo el contenido de comparación

**Opciones de ordenamiento**:
- Por popularidad (volumen de búsqueda)
- Alfabéticamente
- Por categoría/caso de uso
- Por fecha de incorporación (mostrar actualidad)

**Incluir en páginas de índice**:
- Fecha de última actualización para credibilidad
- Número de páginas/comparaciones disponibles
- Filtros rápidos si tienes muchas comparaciones

---

## Navegación en el Pie de Página

El pie de página del sitio aparece en todas las páginas de marketing, convirtiéndolo en una poderosa oportunidad de enlazado interno para páginas de competidores.

### Opción 1: Enlazar a Páginas de Índice (Mínimo)

Como mínimo, agrega enlaces a tus páginas de índice de comparación en el pie de página:

```
Pie de Página
├── Comparar
│   ├── Alternativas →  /alternatives
│   └── Comparaciones →  /vs
```

Esto asegura que cada página de marketing transmita autoridad de enlace a tu hub de contenido de comparación.

### Opción 2: Columnas en el Pie de Página por Formato (Recomendado para SEO)

Para un enlazado interno más fuerte, crea columnas dedicadas en el pie de página para cada formato que hayas construido, enlazando directamente a tus principales competidores:

```
Pie de Página
├── [Producto] vs               ├── Alternativas a               ├── Comparar
│   ├── vs Notion               │   ├── Alternativa a Notion      │   ├── Notion vs Airtable
│   ├── vs Airtable             │   ├── Alternativa a Airtable    │   ├── Monday vs Asana
│   ├── vs Monday               │   ├── Alternativa a Monday      │   ├── Notion vs Monday
│   ├── vs Asana                │   ├── Alternativa a Asana       │   ├── ...
│   ├── vs Clickup              │   ├── Alternativa a Clickup     │   └── Ver todos →
│   ├── ...                     │   ├── ...                       │
│   └── Ver todos →             │   └── Ver todos →               │
```

**Pautas**:
- Incluir hasta 8 enlaces por columna (principales competidores por volumen de búsqueda)
- Agregar enlace "Ver todos" a la página de índice completa
- Solo crear columnas para formatos en los que realmente hayas construido páginas
- Priorizar competidores con mayor volumen de búsqueda

### Por Qué Importan los Enlaces en el Pie de Página

1. **Distribución en todo el sitio**: Los enlaces en el pie de página aparecen en cada página de marketing, transmitiendo autoridad de enlace desde todo tu sitio al contenido de comparación
2. **Eficiencia de rastreo**: Los motores de búsqueda descubren todas las páginas de comparación rápidamente
3. **Descubrimiento por usuarios**: Los visitantes que evalúan tu producto pueden encontrar fácilmente las comparaciones
4. **Posicionamiento competitivo**: Señala a los motores de búsqueda que eres un actor clave en el espacio

### Notas de Implementación

- Actualiza el pie de página al agregar nuevas páginas de comparación de alta prioridad
- Mantén el pie de página limpio — no listes todas las comparaciones, solo las principales
- Relaciona los encabezados de columna con tu estructura de URL (por ejemplo, columna "vs" → URLs `/vs/`)
- Considera el móvil: las columnas pueden apilarse, así que ordena por prioridad
