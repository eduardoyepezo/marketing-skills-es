# Webflow

Plataforma de diseño web visual y CMS para sitios de marketing.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | REST API para sitios, CMS y formularios |
| MCP | - | No disponible |
| CLI | ✓ | CLI de Webflow para devlink y aplicaciones |
| SDK | ✓ | SDK oficial para Node.js |

## Autenticación

- **Tipo**: API Token (token de sitio u OAuth)
- **Encabezado**: `Authorization: Bearer {api_token}`
- **Obtener token**: Site Settings > Integrations > API Access

## Operaciones Comunes del Agente

### Listar sitios

```bash
GET https://api.webflow.com/v2/sites

Authorization: Bearer {api_token}
```

### Obtener sitio

```bash
GET https://api.webflow.com/v2/sites/{site_id}

Authorization: Bearer {api_token}
```

### Listar colecciones

```bash
GET https://api.webflow.com/v2/sites/{site_id}/collections

Authorization: Bearer {api_token}
```

### Listar elementos de una colección

```bash
GET https://api.webflow.com/v2/collections/{collection_id}/items

Authorization: Bearer {api_token}
```

### Obtener elemento de una colección

```bash
GET https://api.webflow.com/v2/collections/{collection_id}/items/{item_id}

Authorization: Bearer {api_token}
```

### Crear elemento en una colección

```bash
POST https://api.webflow.com/v2/collections/{collection_id}/items

Authorization: Bearer {api_token}

{
  "fieldData": {
    "name": "Item Name",
    "slug": "item-name",
    "custom-field": "value"
  }
}
```

### Actualizar elemento de una colección

```bash
PATCH https://api.webflow.com/v2/collections/{collection_id}/items/{item_id}

Authorization: Bearer {api_token}

{
  "fieldData": {
    "custom-field": "new value"
  }
}
```

### Publicar elementos de una colección

```bash
POST https://api.webflow.com/v2/collections/{collection_id}/items/publish

Authorization: Bearer {api_token}

{
  "itemIds": ["item_id_1", "item_id_2"]
}
```

### Listar envíos de formularios

```bash
GET https://api.webflow.com/v2/sites/{site_id}/forms/{form_id}/submissions

Authorization: Bearer {api_token}
```

### Publicar sitio

```bash
POST https://api.webflow.com/v2/sites/{site_id}/publish

Authorization: Bearer {api_token}

{
  "publishToWebflowSubdomain": true,
  "publishToCustomDomains": true
}
```

## SDK de Node.js

```javascript
const Webflow = require('webflow-api');

const webflow = new Webflow({ token: 'api_token' });

// Listar sitios
const sites = await webflow.sites.list();

// Obtener elementos de una colección
const items = await webflow.collections.items.listItems(collectionId);

// Crear elemento
const item = await webflow.collections.items.createItem(collectionId, {
  fieldData: {
    name: 'New Item',
    slug: 'new-item'
  }
});
```

## Comandos CLI

```bash
# Instalar
npm install -g @webflow/webflow-cli

# Iniciar sesión
webflow login

# Inicializar devlink
webflow devlink init

# Sincronizar componentes
webflow devlink sync
```

## Estructura del CMS

- **Collections** - Tipos de contenido (como entradas de blog, miembros del equipo)
- **Items** - Entradas individuales en una colección
- **Fields** - Campos de datos en los elementos

## Tipos de campos comunes

- `PlainText` - Texto simple
- `RichText` - Contenido con formato
- `Image` - Carga de imágenes
- `Link` - URL o referencia a página
- `Reference` - Enlace a otra colección
- `Multi-Reference` - Múltiples enlaces de colección
- `Switch` - Interruptor booleano
- `Number` - Valor numérico
- `Date` - Fecha/hora

## Cuándo Usar

- Gestión de CMS del sitio de marketing
- Publicación de blog/contenido
- Gestión de envíos de formularios
- Actualizaciones automáticas de contenido
- Páginas SEO programático

## Límites de Tasa

- 60 solicitudes/minuto (general)
- 10 solicitudes/minuto (publicación)

## Habilidades Relacionadas

- programmatic-seo
- content-strategy
- page-cro
