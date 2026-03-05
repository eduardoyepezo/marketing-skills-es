# Snov.io

Plataforma de búsqueda de correos electrónicos, verificación y campañas drip para prospección.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | ✓ | REST API para búsqueda de emails, verificación, prospectos, campañas drip |
| MCP | - | No disponible |
| CLI | [✓](../clis/snov.js) | CLI de Node.js sin dependencias |
| SDK | - | Solo API |

## Autenticación

- **Tipo**: Credenciales de cliente OAuth2
- **Flujo**: POST a `/oauth/access_token` con client_id + client_secret
- **Variables de entorno**: `SNOV_CLIENT_ID`, `SNOV_CLIENT_SECRET`
- **Obtener claves**: [Snov.io > Integration > API](https://app.snov.io/integration/api)

El CLI gestiona la obtención de tokens automáticamente.

## Operaciones Comunes del Agente

### Buscar correos electrónicos por dominio

```bash
node tools/clis/snov.js domain search --domain example.com --type all --limit 10
```

### Encontrar el correo electrónico de una persona específica

```bash
node tools/clis/snov.js email find --domain example.com --first-name John --last-name Doe
```

### Verificar un correo electrónico

```bash
node tools/clis/snov.js email verify --email john@example.com
```

### Encontrar prospecto por correo electrónico

```bash
node tools/clis/snov.js prospect find --email john@example.com
```

### Añadir prospecto a una lista

```bash
node tools/clis/snov.js prospect add --email john@example.com --first-name John --last-name Doe --list-id 12345
```

### Gestionar listas de prospectos

```bash
# Listar todas las listas
node tools/clis/snov.js lists list

# Obtener prospectos de una lista
node tools/clis/snov.js lists prospects --id 12345 --page 1 --per-page 50
```

### Verificar el stack tecnológico de un dominio

```bash
node tools/clis/snov.js technology check --domain example.com
```

### Gestionar campañas drip

```bash
# Listar campañas
node tools/clis/snov.js drips list

# Obtener detalles de una campaña
node tools/clis/snov.js drips get --id 12345

# Añadir prospecto a campaña drip
node tools/clis/snov.js drips add-prospect --id 12345 --email john@example.com
```

## Límites de Tasa

- Los límites de tasa varían según el plan
- Los tokens OAuth expiran tras un período determinado; el CLI gestiona la renovación automáticamente

## Casos de Uso

- **Link building**: Encontrar contactos y ejecutar prospección automatizada con campañas drip
- **Prospección**: Construir y gestionar listas de prospectos
- **Investigación tecnológica**: Verificar el stack tecnológico que utiliza un dominio objetivo
- **Verificación de correos**: Limpiar listas antes de enviar
