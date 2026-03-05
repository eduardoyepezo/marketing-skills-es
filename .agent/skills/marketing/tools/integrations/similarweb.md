# Similarweb

Plataforma de inteligencia de tráfico competitivo que ofrece análisis web, fuentes de tráfico, datos de palabras clave e información sobre competidores.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Tráfico, Búsqueda, Referencias, Competidores, Geografía |
| MCP | - | No disponible |
| CLI | ✓ | [similarweb.js](../clis/similarweb.js) |
| SDK | - | Solo REST API |

## Autenticación

- **Tipo**: API Key
- **Parámetro de consulta**: `?api_key={key}`
- **Obtener clave**: Account Settings > API en https://account.similarweb.com

## Operaciones Comunes del Agente

### Total de Visitas

```bash
GET https://api.similarweb.com/v1/website/example.com/total-traffic-and-engagement/visits?api_key={key}&start_date=2024-01&end_date=2024-03&country=us&granularity=monthly
```

### Páginas por Visita

```bash
GET https://api.similarweb.com/v1/website/example.com/total-traffic-and-engagement/pages-per-visit?api_key={key}&start_date=2024-01&end_date=2024-03
```

### Duración Promedio de Visita

```bash
GET https://api.similarweb.com/v1/website/example.com/total-traffic-and-engagement/average-visit-duration?api_key={key}&start_date=2024-01&end_date=2024-03
```

### Tasa de Rebote

```bash
GET https://api.similarweb.com/v1/website/example.com/total-traffic-and-engagement/bounce-rate?api_key={key}&start_date=2024-01&end_date=2024-03
```

### Desglose de Fuentes de Tráfico

```bash
GET https://api.similarweb.com/v1/website/example.com/traffic-sources/overview?api_key={key}&start_date=2024-01&end_date=2024-03
```

### Principales Sitios de Referencia

```bash
GET https://api.similarweb.com/v1/website/example.com/traffic-sources/referrals?api_key={key}&start_date=2024-01&end_date=2024-03
```

### Palabras Clave Orgánicas

```bash
GET https://api.similarweb.com/v1/website/example.com/search/organic-search-keywords?api_key={key}&start_date=2024-01&end_date=2024-03
```

### Palabras Clave de Pago

```bash
GET https://api.similarweb.com/v1/website/example.com/search/paid-search-keywords?api_key={key}&start_date=2024-01&end_date=2024-03
```

### Sitios Similares / Competidores

```bash
GET https://api.similarweb.com/v1/website/example.com/similar-sites/similarsites?api_key={key}
```

### Posición en Categoría

```bash
GET https://api.similarweb.com/v1/website/example.com/category-rank/category-rank?api_key={key}
```

### Tráfico por País

```bash
GET https://api.similarweb.com/v1/website/example.com/geo/traffic-by-country?api_key={key}&start_date=2024-01&end_date=2024-03
```

## Métricas Clave

### Tráfico y Participación
- `visits` - Total de visitas en el período
- `pages_per_visit` - Promedio de páginas vistas por visita
- `average_visit_duration` - Duración promedio de sesión en segundos
- `bounce_rate` - Porcentaje de visitas de una sola página

### Fuentes de Tráfico
- `search` - Porcentaje de búsqueda orgánica y de pago
- `social` - Porcentaje de tráfico de redes sociales
- `direct` - Porcentaje de tráfico directo
- `referrals` - Porcentaje de tráfico por referencias
- `mail` - Porcentaje de tráfico por correo electrónico
- `display_ads` - Porcentaje de publicidad gráfica

### Palabras Clave de Búsqueda
- `search_term` - Texto de la palabra clave
- `share` - Porcentaje de cuota de tráfico
- `volume` - Volumen de búsqueda
- `cpc` - Costo por clic
- `position` - Posición de clasificación promedio

### Geografía
- `country` - Código de país
- `share` - Cuota de tráfico proveniente de ese país

## Parámetros

### Parámetros Comunes
- `start_date` - Mes de inicio (formato YYYY-MM)
- `end_date` - Mes de fin (formato YYYY-MM)
- `country` - Código de país de dos letras (ej., us, gb, de)
- `granularity` - Granularidad de los datos: monthly, weekly, daily

### Parámetros de Búsqueda
- `limit` - Número de palabras clave a devolver
- `country` - Filtrar por país

## Cuándo Usar

- Analizar el tráfico web y las métricas de participación de los competidores
- Comparar tu sitio con los competidores
- Identificar las principales fuentes de tráfico de cualquier sitio web
- Descubrir las palabras clave orgánicas y de pago de los competidores
- Encontrar sitios similares y el panorama competitivo
- Comprender la distribución geográfica del tráfico
- Auditar el rendimiento de SEO en relación con los competidores
- Investigar la cuota de mercado por volumen de tráfico

## Límites de Velocidad

- Los límites de velocidad varían según el nivel del plan
- Estándar: 10 solicitudes/segundo
- La disponibilidad de datos depende del plan (3 meses a 36 meses de historial)
- Algunos endpoints requieren planes Premium o Enterprise

## Habilidades Relevantes

- seo-audit
- competitor-alternatives
- paid-ads
- content-strategy
