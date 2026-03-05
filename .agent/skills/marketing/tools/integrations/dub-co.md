# Dub.co

Plataforma de gestión de enlaces y atribución para equipos de marketing modernos.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API para links, analytics, domains |
| MCP | - | No disponible |
| CLI | - | No disponible |
| SDK | ✓ | TypeScript SDK disponible |

## Autenticación

- **Tipo**: API Key
- **Header**: `Authorization: Bearer {api_key}`
- **Obtener clave**: Settings > API Keys en el panel de Dub

## Operaciones Comunes del Agente

### Crear enlace corto

```bash
POST https://api.dub.co/links

{
  "url": "https://example.com/landing-page",
  "domain": "link.example.com",
  "key": "summer-sale",
  "tags": ["campaign:summer", "channel:email"]
}
```

### Obtener enlace por clave

```bash
GET https://api.dub.co/links?domain=link.example.com&key=summer-sale
```

### Listar enlaces

```bash
GET https://api.dub.co/links?domain=link.example.com&page=1
```

### Obtener analytics de un enlace

```bash
GET https://api.dub.co/analytics?domain=link.example.com&key=summer-sale&interval=30d
```

### Obtener clics por ubicación

```bash
GET https://api.dub.co/analytics/country?domain=link.example.com&key=summer-sale
```

### Obtener clics por dispositivo

```bash
GET https://api.dub.co/analytics/device?domain=link.example.com&key=summer-sale
```

### Actualizar enlace

```bash
PATCH https://api.dub.co/links/{link_id}

{
  "url": "https://example.com/new-landing-page",
  "tags": ["campaign:summer", "channel:social"]
}
```

### Eliminar enlace

```bash
DELETE https://api.dub.co/links/{link_id}
```

### Crear enlaces en masa

```bash
POST https://api.dub.co/links/bulk

[
  {"url": "https://example.com/page1", "key": "page1"},
  {"url": "https://example.com/page2", "key": "page2"}
]
```

## TypeScript SDK

### Instalación

```bash
npm install dub
```

### Uso

```typescript
import { Dub } from "dub";

const dub = new Dub({ token: "YOUR_API_KEY" });

// Crear enlace
const link = await dub.links.create({
  url: "https://example.com",
  domain: "link.example.com"
});

// Obtener analytics
const analytics = await dub.analytics.retrieve({
  domain: "link.example.com",
  key: "summer-sale"
});
```

## Funcionalidades Clave

- **Dominios personalizados** - Usa tus propios dominios de marca
- **Analytics de enlaces** - Clics, ubicaciones, dispositivos, referentes
- **Etiquetas** - Organiza enlaces por campaña, canal, etc.
- **Códigos QR** - Generados automáticamente para cada enlace
- **Protección con contraseña** - Asegura enlaces sensibles
- **Expiración** - Enlaces con límite de tiempo
- **Geo-targeting** - Redirige según la ubicación

## Dimensiones de Analytics

- `clicks` - Total de clics
- `country` - Clics por país
- `city` - Clics por ciudad
- `device` - Clics por tipo de dispositivo
- `browser` - Clics por navegador
- `os` - Clics por sistema operativo
- `referer` - Clics por referente

## Cuándo Usar

- Crear enlaces de marketing rastreables
- Construir sistemas de enlaces de referidos
- Seguimiento de atribución de campañas
- Pruebas A/B de páginas de destino mediante enlaces
- Generar URLs cortas de marca
- Analizar el rendimiento de enlaces

## Límites de Velocidad

- Free: 1.000 enlaces, 5 solicitudes API/segundo
- Pro: Enlaces ilimitados, 50 solicitudes API/segundo
- Enterprise: Límites personalizados

## Skills Relacionadas

- referral-program
- analytics-tracking
- paid-ads
