# Hunter.io

Plataforma de búsqueda y verificación de correos electrónicos para outreach y link building.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API para búsqueda de dominios, buscador de correos, verificación |
| MCP | - | No disponible |
| CLI | [✓](../clis/hunter.js) | CLI Node.js sin dependencias |
| SDK | - | Solo API |

## Autenticación

- **Tipo**: API Key (parámetro de consulta)
- **Parámetro**: `api_key={key}`
- **Variable de entorno**: `HUNTER_API_KEY`
- **Obtener clave**: [Panel de Hunter > API](https://hunter.io/api-keys)

## Operaciones Comunes del Agente

### Buscar correos para un dominio

```bash
node tools/clis/hunter.js domain search --domain example.com --limit 10
```

### Buscar el correo de una persona específica

```bash
node tools/clis/hunter.js email find --domain example.com --first-name John --last-name Doe
```

### Verificar una dirección de correo

```bash
node tools/clis/hunter.js email verify --email john@example.com
```

### Contar correos disponibles para un dominio

```bash
node tools/clis/hunter.js domain count --domain example.com
```

### Gestionar leads

```bash
# Listar leads
node tools/clis/hunter.js leads list --limit 20

# Crear un lead
node tools/clis/hunter.js leads create --email john@example.com --first-name John --last-name Doe --company "Example Inc"

# Eliminar un lead
node tools/clis/hunter.js leads delete --id 12345
```

### Gestionar campañas

```bash
# Listar campañas
node tools/clis/hunter.js campaigns list

# Obtener detalles de una campaña
node tools/clis/hunter.js campaigns get --id 12345

# Iniciar/pausar una campaña
node tools/clis/hunter.js campaigns start --id 12345
node tools/clis/hunter.js campaigns pause --id 12345
```

### Consultar uso de la cuenta

```bash
node tools/clis/hunter.js account info
```

## Límites de Velocidad

- Plan gratuito: 25 búsquedas/mes, 50 verificaciones/mes
- Los planes de pago escalan según el nivel
- Límite de velocidad de la API: 10 solicitudes/segundo

## Casos de Uso

- **Link building**: Encontrar contactos de correo en dominios objetivo para outreach
- **Prospección**: Crear listas de leads a partir de dominios de empresas
- **Verificación**: Limpiar listas de correos antes de enviar campañas
