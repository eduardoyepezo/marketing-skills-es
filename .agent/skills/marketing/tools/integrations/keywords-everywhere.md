# Keywords Everywhere

API de investigación de palabras clave para volumen de búsqueda, CPC, competencia, palabras clave relacionadas y datos de tráfico.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API para datos de palabras clave, palabras clave relacionadas, tráfico |
| MCP | - | Servidor MCP comunitario disponible |
| CLI | ✓ | [keywords-everywhere.js](../clis/keywords-everywhere.js) |
| SDK | - | Solo API |

## Autenticación

- **Tipo**: API Key (Bearer token)
- **Encabezado**: `Authorization: Bearer {api_key}`
- **Obtener clave**: https://keywordseverywhere.com/first-install-addon.html
- **Límite**: 100 palabras clave por solicitud

## Operaciones Comunes del Agente

### Obtener datos de palabras clave (volumen, CPC, competencia)

```bash
POST https://api.keywordseverywhere.com/v1/get_keyword_data

Authorization: Bearer {api_key}

{
  "country": "us",
  "currency": "USD",
  "dataSource": "gkp",
  "kw": ["email marketing", "marketing automation", "crm software"]
}
```

### Obtener palabras clave relacionadas

```bash
POST https://api.keywordseverywhere.com/v1/get_related_keywords

Authorization: Bearer {api_key}

{
  "country": "us",
  "currency": "USD",
  "dataSource": "gkp",
  "kw": ["email marketing"]
}
```

### Obtener palabras clave de "Las personas también buscan"

```bash
POST https://api.keywordseverywhere.com/v1/get_pasf_keywords

Authorization: Bearer {api_key}

{
  "country": "us",
  "currency": "USD",
  "dataSource": "gkp",
  "kw": ["email marketing"]
}
```

### Obtener palabras clave de un dominio (para qué posiciona un dominio)

```bash
POST https://api.keywordseverywhere.com/v1/get_domain_keywords

Authorization: Bearer {api_key}

{
  "country": "us",
  "currency": "USD",
  "domain": "example.com"
}
```

### Obtener palabras clave de una URL (para qué posiciona una URL específica)

```bash
POST https://api.keywordseverywhere.com/v1/get_url_keywords

Authorization: Bearer {api_key}

{
  "country": "us",
  "currency": "USD",
  "url": "https://example.com/page"
}
```

### Obtener tráfico de un dominio

```bash
POST https://api.keywordseverywhere.com/v1/get_domain_traffic

Authorization: Bearer {api_key}

{
  "country": "us",
  "domain": "example.com"
}
```

### Obtener tráfico de una URL

```bash
POST https://api.keywordseverywhere.com/v1/get_url_traffic

Authorization: Bearer {api_key}

{
  "country": "us",
  "url": "https://example.com/page"
}
```

### Obtener backlinks de un dominio

```bash
POST https://api.keywordseverywhere.com/v1/get_domain_backlinks

Authorization: Bearer {api_key}

{
  "domain": "example.com"
}
```

### Obtener backlinks de una página

```bash
POST https://api.keywordseverywhere.com/v1/get_page_backlinks

Authorization: Bearer {api_key}

{
  "url": "https://example.com/page"
}
```

### Consultar créditos

```bash
GET https://api.keywordseverywhere.com/v1/get_credits

Authorization: Bearer {api_key}
```

### Obtener países compatibles

```bash
GET https://api.keywordseverywhere.com/v1/get_countries

Authorization: Bearer {api_key}
```

### Obtener monedas compatibles

```bash
GET https://api.keywordseverywhere.com/v1/get_currencies

Authorization: Bearer {api_key}
```

## Métricas Clave

### Datos de Palabras Clave
- `vol` - Volumen de búsqueda mensual
- `cpc.value` - Costo por clic
- `competition` - Puntuación de competencia
- `trend` - Datos de tendencia de 12 meses

### Datos de Tráfico
- `estimated_traffic` - Tráfico mensual estimado
- `keywords_count` - Número de palabras clave posicionadas

## Parámetros

- `country` - Código de país (us, uk, de, fr, etc.)
- `currency` - Código de moneda (USD, GBP, EUR, etc.)
- `dataSource` - Fuente de datos, predeterminado `gkp` (Google Keyword Planner)
- `kw` - Arreglo de palabras clave (máximo 100 por solicitud)

## Cuándo Usar

- Investigación rápida de palabras clave con volumen y CPC
- Encontrar palabras clave relacionadas y sugerencias PASF
- Analizar posicionamiento de palabras clave de dominios/URLs
- Estimación de tráfico para dominios y páginas
- Descubrimiento de backlinks

## Límites de Velocidad

- 100 palabras clave por solicitud
- Precios basados en créditos (1 crédito por palabra clave)

## Skills Relevantes

- seo-audit
- content-strategy
- programmatic-seo
- competitor-alternatives
