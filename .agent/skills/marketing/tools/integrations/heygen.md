# HeyGen

Plataforma de generación de video con avatares de IA. Crea videos "talking-head" a partir de guiones de texto, con lip-sync, expresiones y gestos realistas.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | REST API v2 para generación de video, avatares, plantillas |
| MCP | ✓ | Servidor MCP oficial hospedado — no requiere instalación local |
| CLI | - | - |
| SDK | ✓ | SDK de Node.js disponible |

## Autenticación

- **Tipo**: API Key
- **Encabezado**: `X-Api-Key: {api_key}`
- **Obtener clave**: Settings > API en el dashboard de HeyGen

## Configuración del Servidor MCP

HeyGen ofrece un servidor MCP remoto hospedado. No requiere instalación local.

### Claude Code / Claude Desktop

Agrega a tu configuración MCP:

```json
{
  "mcpServers": {
    "heygen": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.heygen.com/mcp"]
    }
  }
}
```

En el primer uso, se autentica vía OAuth en el navegador. El servidor MCP expone herramientas para:
- Crear videos a partir de guiones
- Listar y seleccionar avatares
- Gestionar plantillas
- Verificar el estado de un video

## Inicio Rápido con la API

### Crear un Video

```bash
curl -X POST https://api.heygen.com/v2/video/generate \
  -H "X-Api-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "video_inputs": [{
      "character": {
        "type": "avatar",
        "avatar_id": "AVATAR_ID",
        "avatar_style": "normal"
      },
      "voice": {
        "type": "text",
        "input_text": "Aquí va tu guion.",
        "voice_id": "VOICE_ID"
      }
    }],
    "dimension": {
      "width": 1920,
      "height": 1080
    }
  }'
```

### Listar Avatares

```bash
curl https://api.heygen.com/v2/avatars \
  -H "X-Api-Key: YOUR_API_KEY"
```

### Verificar Estado de un Video

```bash
curl https://api.heygen.com/v1/video_status.get?video_id=VIDEO_ID \
  -H "X-Api-Key: YOUR_API_KEY"
```

## Casos de Uso Comunes en Marketing

| Caso de Uso | Enfoque |
|----------|----------|
| Explicativo de producto | Guion desde las funciones → el avatar presenta |
| Anuncio de funcionalidad | Plantilla con avatar + grabación de pantalla |
| Contenido multilingüe | Mismo guion, distinto idioma/voz |
| Prospección personalizada | Variables dinámicas (nombre, empresa) en el guion |
| Actualizaciones semanales | Plantilla recurrente, se cambia solo el texto del guion |

## Avatares Personalizados

Sube un video de 2-5 minutos hablando para crear un gemelo digital:
- Se ve y suena como tú
- Genera videos ilimitados a partir de guiones de texto
- Disponible desde el plan Creator en adelante

## Precios

| Plan | Videos/mes | Duración Máxima |
|------|-----------|-------------|
| Free | 3 | 3 min |
| Creator | Ilimitados | 5 min |
| Business | Ilimitados | 20 min |
| Enterprise | Ilimitados | Personalizada |

Verifica [heygen.com/pricing](https://www.heygen.com/pricing) para precios actuales — cambian con frecuencia.

## Límites de Tasa

- Free: 3 videos/mes
- Pagos: según el nivel del plan, aplican límites de generación concurrente
- Límites de la API: revisa los encabezados `X-RateLimit-*` de la respuesta

## Skills Relevantes

- video
- social
- ad-creative
- sales-enablement
