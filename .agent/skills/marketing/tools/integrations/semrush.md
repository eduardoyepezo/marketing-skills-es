# SEMrush

Plataforma de SEO y análisis competitivo para investigación de palabras clave y auditorías de sitios.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | Analytics API, Projects API |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | - | Solo API |

## Autenticación

- **Tipo**: API Key
- **Parámetro**: `key={api_key}` en la cadena de consulta
- **Obtener clave**: My Profile > API en el panel de SEMrush

## Operaciones Comunes del Agente

### Resumen de dominio

```bash
GET https://api.semrush.com/?type=domain_ranks&key={api_key}&export_columns=Db,Dn,Rk,Or,Ot,Oc,Ad,At,Ac&domain=example.com
```

### Palabras clave orgánicas

```bash
GET https://api.semrush.com/?type=domain_organic&key={api_key}&export_columns=Ph,Po,Pp,Pd,Nq,Cp,Ur,Tr,Tc,Co,Nr&domain=example.com&database=us&display_limit=100
```

### Resumen de palabra clave

```bash
GET https://api.semrush.com/?type=phrase_all&key={api_key}&export_columns=Ph,Nq,Cp,Co,Nr&phrase=keyword&database=us
```

### Palabras clave relacionadas

```bash
GET https://api.semrush.com/?type=phrase_related&key={api_key}&export_columns=Ph,Nq,Cp,Co,Nr,Td&phrase=keyword&database=us&display_limit=50
```

### Dificultad de palabra clave

```bash
GET https://api.semrush.com/?type=phrase_kdi&key={api_key}&export_columns=Ph,Kd&phrase=keyword&database=us
```

### Resumen de backlinks

```bash
GET https://api.semrush.com/?type=backlinks_overview&key={api_key}&target=example.com&target_type=root_domain
```

### Lista de backlinks

```bash
GET https://api.semrush.com/?type=backlinks&key={api_key}&target=example.com&target_type=root_domain&export_columns=source_url,source_title,target_url,anchor&display_limit=100
```

### Competidores

```bash
GET https://api.semrush.com/?type=domain_organic_organic&key={api_key}&export_columns=Dn,Cr,Np,Or,Ot,Oc,Ad&domain=example.com&database=us&display_limit=20
```

## Formato de Respuesta

Las respuestas son CSV por defecto. Agregar `&export_escape=1` para un escape adecuado.

## Columnas de Exportación

### Informe de Dominio
- `Db` - Base de datos
- `Dn` - Dominio
- `Rk` - Posición
- `Or` - Palabras clave orgánicas
- `Ot` - Tráfico orgánico
- `Oc` - Costo orgánico

### Informe de Palabras Clave
- `Ph` - Frase/palabra clave
- `Nq` - Volumen de búsqueda
- `Cp` - CPC
- `Co` - Competencia
- `Kd` - Dificultad de la palabra clave
- `Nr` - Número de resultados

### Backlinks
- `source_url` - Página de origen del enlace
- `target_url` - Página de destino
- `anchor` - Texto de ancla
- `source_title` - Título de la página

## Bases de Datos

Usar código de país: `us`, `uk`, `de`, `fr`, `ca`, `au`, etc.

## Cuándo Usar

- Investigación de palabras clave
- Análisis competitivo
- Análisis de backlinks
- Auditorías de sitios
- Seguimiento de posiciones
- Análisis de brechas de contenido

## Límites de Velocidad

- Varía según el plan (10-30K unidades/día)
- Cada llamada a la API consume unidades

## Habilidades Relevantes

- seo-audit
- programmatic-seo
- content-strategy
- competitor-alternatives
