# WordPress

Sistema de gestión de contenidos para blogs y sitios web.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | REST API (WP REST API) |
| MCP | - | No disponible |
| CLI | ✓ | WP-CLI para gestión del lado del servidor |
| SDK | ✓ | Varias bibliotecas de cliente |

## Autenticación

- **Tipo**: Application Password, JWT u OAuth
- **Encabezado**: `Authorization: Basic {base64(username:app_password)}`
- **Configuración**: Users > Your Profile > Application Passwords

## Operaciones Comunes del Agente

### Listar entradas

```bash
GET https://example.com/wp-json/wp/v2/posts?per_page=10

Authorization: Basic {base64(username:app_password)}
```

### Obtener entrada

```bash
GET https://example.com/wp-json/wp/v2/posts/{post_id}

Authorization: Basic {base64(username:app_password)}
```

### Crear entrada

```bash
POST https://example.com/wp-json/wp/v2/posts

Authorization: Basic {base64(username:app_password)}

{
  "title": "Post Title",
  "content": "<p>Post content here</p>",
  "status": "draft",
  "categories": [1],
  "tags": [5, 6]
}
```

### Actualizar entrada

```bash
PUT https://example.com/wp-json/wp/v2/posts/{post_id}

Authorization: Basic {base64(username:app_password)}

{
  "title": "Updated Title",
  "status": "publish"
}
```

### Listar páginas

```bash
GET https://example.com/wp-json/wp/v2/pages?per_page=20

Authorization: Basic {base64(username:app_password)}
```

### Listar categorías

```bash
GET https://example.com/wp-json/wp/v2/categories
```

### Crear categoría

```bash
POST https://example.com/wp-json/wp/v2/categories

{
  "name": "Category Name",
  "slug": "category-name"
}
```

### Subir medios

```bash
POST https://example.com/wp-json/wp/v2/media

Authorization: Basic {base64(username:app_password)}
Content-Disposition: attachment; filename="image.jpg"
Content-Type: image/jpeg

[binary image data]
```

### Listar usuarios

```bash
GET https://example.com/wp-json/wp/v2/users

Authorization: Basic {base64(username:app_password)}
```

## Comandos WP-CLI

```bash
# Listar entradas
wp post list --post_type=post --post_status=publish

# Crear entrada
wp post create --post_title="Title" --post_content="Content" --post_status=publish

# Actualizar entrada
wp post update 123 --post_title="New Title"

# Exportar base de datos
wp db export backup.sql

# Buscar/reemplazar en base de datos
wp search-replace 'old-domain.com' 'new-domain.com'

# Instalar plugin
wp plugin install yoast-seo --activate

# Actualizar plugins
wp plugin update --all
```

## Estados de las entradas

- `publish` - Publicado en el sitio
- `draft` - No publicado
- `pending` - Pendiente de revisión
- `private` - Entrada privada
- `future` - Programado
- `trash` - En papelera

## Endpoints comunes

| Endpoint | Recurso |
|----------|---------|
| `/wp/v2/posts` | Entradas del blog |
| `/wp/v2/pages` | Páginas |
| `/wp/v2/media` | Imágenes/archivos |
| `/wp/v2/categories` | Categorías |
| `/wp/v2/tags` | Etiquetas |
| `/wp/v2/users` | Usuarios |
| `/wp/v2/comments` | Comentarios |

## Cuándo Usar

- Gestión de contenido del blog
- Actualizaciones de páginas
- Gestión de medios
- Configuración del sitio
- Gestión de plugins/temas

## Límites de Tasa

- Sin límites predeterminados
- Depende del servidor/host

## Habilidades Relacionadas

- content-strategy
- seo-audit
- programmatic-seo
