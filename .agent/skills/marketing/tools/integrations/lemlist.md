# Lemlist

Plataforma de outreach de correo frío con personalización y gestión de campañas.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API para campañas, leads, actividades, webhooks |
| MCP | - | No disponible |
| CLI | [✓](../clis/lemlist.js) | CLI Node.js sin dependencias |
| SDK | - | Solo API |

## Autenticación

- **Tipo**: Basic Auth (nombre de usuario vacío, API key como contraseña)
- **Encabezado**: `Authorization: Basic base64(:api_key)`
- **Variable de entorno**: `LEMLIST_API_KEY`
- **Obtener clave**: [Lemlist Configuración > Integraciones](https://app.lemlist.com/settings/integrations)

## Operaciones Comunes del Agente

### Listar campañas

```bash
node tools/clis/lemlist.js campaigns list --offset 0 --limit 20
```

### Obtener detalles y estadísticas de una campaña

```bash
# Obtener campaña
node tools/clis/lemlist.js campaigns get --id cam_abc123

# Obtener estadísticas de la campaña
node tools/clis/lemlist.js campaigns stats --id cam_abc123

# Exportar datos de la campaña
node tools/clis/lemlist.js campaigns export --id cam_abc123
```

### Gestionar leads en una campaña

```bash
# Listar leads
node tools/clis/lemlist.js leads list --campaign-id cam_abc123

# Agregar un lead
node tools/clis/lemlist.js leads add --campaign-id cam_abc123 --email john@example.com --first-name John --last-name Doe --company "Example Inc"

# Obtener detalles de un lead
node tools/clis/lemlist.js leads get --campaign-id cam_abc123 --email john@example.com

# Eliminar un lead
node tools/clis/lemlist.js leads delete --campaign-id cam_abc123 --email john@example.com
```

### Gestionar bajas de suscripción

```bash
# Listar correos dados de baja
node tools/clis/lemlist.js unsubscribes list

# Agregar a la lista de bajas
node tools/clis/lemlist.js unsubscribes add --email john@example.com

# Eliminar de la lista de bajas
node tools/clis/lemlist.js unsubscribes delete --email john@example.com
```

### Ver actividades

```bash
# Todas las actividades
node tools/clis/lemlist.js activities list

# Filtrar por campaña y tipo
node tools/clis/lemlist.js activities list --campaign-id cam_abc123 --type emailsOpened
```

### Gestionar webhooks

```bash
# Listar hooks
node tools/clis/lemlist.js hooks list

# Crear un webhook
node tools/clis/lemlist.js hooks create --target-url https://example.com/webhook --event emailsOpened

# Eliminar un webhook
node tools/clis/lemlist.js hooks delete --id hook_123
```

### Información del equipo

```bash
node tools/clis/lemlist.js team info
```

## Límites de Velocidad

- Los límites de velocidad de la API varían según el plan
- Recomendado: mantenerse bajo 10 solicitudes/segundo

## Casos de Uso

- **Outreach para link building**: Agregar prospectos a campañas para solicitar backlinks
- **Gestión de campañas**: Monitorear tasas de apertura y respuesta en campañas de outreach
- **Gestión de leads**: Agregar, eliminar y rastrear leads en campañas
- **Integración de webhooks**: Recibir notificaciones en tiempo real para eventos de correo
