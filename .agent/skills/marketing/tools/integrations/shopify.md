# Shopify

Plataforma de comercio electrónico para tiendas en línea y venta al por menor.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST Admin API, Storefront API, GraphQL |
| MCP | - | No disponible |
| CLI | ✓ | Shopify CLI para temas y aplicaciones |
| SDK | ✓ | Librerías oficiales para múltiples lenguajes |

## Autenticación

- **Tipo**: Access Token (Aplicación Personalizada u OAuth)
- **Header**: `X-Shopify-Access-Token: {access_token}`
- **URL base**: `https://{shop}.myshopify.com/admin/api/2024-01/`

## Operaciones Comunes del Agente

### Obtener información de la tienda

```bash
GET https://{shop}.myshopify.com/admin/api/2024-01/shop.json

X-Shopify-Access-Token: {access_token}
```

### Listar productos

```bash
GET https://{shop}.myshopify.com/admin/api/2024-01/products.json?limit=50

X-Shopify-Access-Token: {access_token}
```

### Obtener producto

```bash
GET https://{shop}.myshopify.com/admin/api/2024-01/products/{product_id}.json

X-Shopify-Access-Token: {access_token}
```

### Crear producto

```bash
POST https://{shop}.myshopify.com/admin/api/2024-01/products.json

X-Shopify-Access-Token: {access_token}

{
  "product": {
    "title": "Product Name",
    "body_html": "<p>Description</p>",
    "vendor": "Brand",
    "product_type": "Category",
    "variants": [{
      "price": "99.00",
      "sku": "SKU-001"
    }]
  }
}
```

### Listar pedidos

```bash
GET https://{shop}.myshopify.com/admin/api/2024-01/orders.json?status=any&limit=50

X-Shopify-Access-Token: {access_token}
```

### Obtener pedido

```bash
GET https://{shop}.myshopify.com/admin/api/2024-01/orders/{order_id}.json

X-Shopify-Access-Token: {access_token}
```

### Listar clientes

```bash
GET https://{shop}.myshopify.com/admin/api/2024-01/customers.json?limit=50

X-Shopify-Access-Token: {access_token}
```

### Buscar clientes

```bash
GET https://{shop}.myshopify.com/admin/api/2024-01/customers/search.json?query=email:user@example.com

X-Shopify-Access-Token: {access_token}
```

### Obtener análisis

```bash
GET https://{shop}.myshopify.com/admin/api/2024-01/reports.json

X-Shopify-Access-Token: {access_token}
```

## API GraphQL

```graphql
{
  products(first: 10) {
    edges {
      node {
        id
        title
        totalInventory
        priceRangeV2 {
          minVariantPrice {
            amount
          }
        }
      }
    }
  }
}
```

## Comandos CLI

```bash
# Iniciar sesión
shopify login --store={shop}

# Crear tema
shopify theme init

# Subir tema
shopify theme push

# Vista previa del tema
shopify theme dev

# Crear aplicación
shopify app create node
```

## Temas de Webhook

| Tema | Cuándo |
|-------|------|
| `orders/create` | Nuevo pedido |
| `orders/paid` | Pedido pagado |
| `orders/fulfilled` | Pedido enviado |
| `customers/create` | Nuevo cliente |
| `products/update` | Producto modificado |
| `checkouts/create` | Pago iniciado |

## Cuándo Usar

- Gestión de tienda de comercio electrónico
- Operaciones de catálogo de productos
- Procesamiento de pedidos
- Gestión de datos de clientes
- Seguimiento de inventario

## Límites de Velocidad

- REST: 2 solicitudes/segundo
- GraphQL: 50 puntos/segundo
- Operaciones en lote disponibles

## Habilidades Relevantes

- analytics-tracking
- email-sequence
- referral-program
