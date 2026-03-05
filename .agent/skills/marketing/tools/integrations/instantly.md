# Instantly.ai

Plataforma de correo frío con calentamiento de cuentas integrado y gestión de campañas a gran escala.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API para campañas, leads, cuentas y analíticas |
| MCP | - | No disponible |
| CLI | [✓](../clis/instantly.js) | CLI Node.js sin dependencias |
| SDK | - | Solo API |

## Autenticación

- **Tipo**: API Key (parámetro de consulta)
- **Parámetro**: `api_key={key}`
- **Variable de entorno**: `INSTANTLY_API_KEY`
- **Obtener clave**: [Instantly Configuración > Integraciones > API](https://app.instantly.ai/app/settings/integrations)

## Operaciones Comunes del Agente

### Gestionar campañas

```bash
# Listar campañas
node tools/clis/instantly.js campaigns list --limit 20

# Obtener detalles de una campaña
node tools/clis/instantly.js campaigns get --id cam_abc123

# Verificar estado de una campaña
node tools/clis/instantly.js campaigns status --id cam_abc123

# Lanzar una campaña
node tools/clis/instantly.js campaigns launch --id cam_abc123

# Pausar una campaña
node tools/clis/instantly.js campaigns pause --id cam_abc123
```

### Gestionar leads

```bash
# Listar leads en una campaña
node tools/clis/instantly.js leads list --campaign-id cam_abc123 --limit 50

# Agregar un lead
node tools/clis/instantly.js leads add --campaign-id cam_abc123 --email john@example.com --first-name John --last-name Doe --company "Example Inc"

# Eliminar un lead
node tools/clis/instantly.js leads delete --campaign-id cam_abc123 --email john@example.com

# Verificar estado de un lead
node tools/clis/instantly.js leads status --campaign-id cam_abc123 --email john@example.com
```

### Gestionar cuentas de correo

```bash
# Listar cuentas conectadas
node tools/clis/instantly.js accounts list --limit 20

# Verificar estado de una cuenta
node tools/clis/instantly.js accounts status --account-id me@example.com

# Verificar estado de calentamiento
node tools/clis/instantly.js accounts warmup-status --account-id me@example.com
```

### Ver analíticas

```bash
# Analíticas de campaña
node tools/clis/instantly.js analytics campaign --campaign-id cam_abc123 --start 2024-01-01 --end 2024-01-31

# Analíticas paso a paso
node tools/clis/instantly.js analytics steps --campaign-id cam_abc123

# Analíticas a nivel de cuenta
node tools/clis/instantly.js analytics account --start 2024-01-01 --end 2024-01-31
```

### Gestionar lista de bloqueo

```bash
# Listar correos/dominios bloqueados
node tools/clis/instantly.js blocklist list

# Agregar a la lista de bloqueo
node tools/clis/instantly.js blocklist add --entries "competitor.com,spam@example.com"
```

## Límites de Velocidad

- Los límites de velocidad de la API varían según el plan
- Recomendado: mantenerse bajo 10 solicitudes/segundo

## Casos de Uso

- **Link building a gran escala**: Ejecutar campañas de outreach de alto volumen con calentamiento integrado
- **Gestión de campañas**: Lanzar, pausar y monitorear campañas de correo frío
- **Salud de cuentas**: Monitorear el calentamiento y la entregabilidad de cuentas de correo
- **Analíticas**: Rastrear tasas de apertura, tasas de respuesta y rendimiento de campañas
