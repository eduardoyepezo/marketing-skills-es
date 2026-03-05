# HubSpot

Plataforma CRM para marketing, ventas y servicio al cliente.

## Capacidades

| Integración | Disponible | Notas |
|-------------|-----------|-------|
| API | ✓ | REST API para CRM, Marketing, Ventas |
| MCP | - | No disponible |
| CLI | ✓ | CLI `hs` para desarrollo local |
| SDK | ✓ | Librerías cliente oficiales |

## Autenticación

- **Tipo**: Token de aplicación privada u OAuth 2.0
- **Encabezado**: `Authorization: Bearer {access_token}`
- **Obtener token**: Configuración > Integraciones > Aplicaciones privadas

## Operaciones Comunes del Agente

### Obtener contactos

```bash
GET https://api.hubapi.com/crm/v3/objects/contacts?limit=10

Authorization: Bearer {access_token}
```

### Buscar contactos

```bash
POST https://api.hubapi.com/crm/v3/objects/contacts/search

{
  "filterGroups": [{
    "filters": [{
      "propertyName": "email",
      "operator": "EQ",
      "value": "user@example.com"
    }]
  }]
}
```

### Crear contacto

```bash
POST https://api.hubapi.com/crm/v3/objects/contacts

{
  "properties": {
    "email": "user@example.com",
    "firstname": "John",
    "lastname": "Doe",
    "company": "Example Inc"
  }
}
```

### Actualizar contacto

```bash
PATCH https://api.hubapi.com/crm/v3/objects/contacts/{contact_id}

{
  "properties": {
    "lifecyclestage": "customer"
  }
}
```

### Obtener negocios

```bash
GET https://api.hubapi.com/crm/v3/objects/deals?limit=10&properties=dealname,amount,dealstage

Authorization: Bearer {access_token}
```

### Crear negocio

```bash
POST https://api.hubapi.com/crm/v3/objects/deals

{
  "properties": {
    "dealname": "New Deal",
    "amount": "10000",
    "dealstage": "appointmentscheduled",
    "pipeline": "default"
  }
}
```

### Asociar contacto con negocio

```bash
PUT https://api.hubapi.com/crm/v3/objects/deals/{deal_id}/associations/contacts/{contact_id}/deal_to_contact
```

### Obtener envíos de formularios

```bash
GET https://api.hubapi.com/form-integrations/v1/submissions/forms/{form_guid}

Authorization: Bearer {access_token}
```

### Obtener correos de marketing

```bash
GET https://api.hubapi.com/marketing/v3/emails?limit=10

Authorization: Bearer {access_token}
```

## Comandos CLI

```bash
# Instalar
npm install -g @hubspot/cli

# Inicializar proyecto
hs init

# Subir archivos
hs upload src dest

# Observar cambios
hs watch src dest

# Listar portales
hs accounts list
```

## Objetos Principales

- **Contacts** - Personas en el CRM
- **Companies** - Organizaciones
- **Deals** - Oportunidades de venta
- **Tickets** - Tickets de soporte
- **Products** - Artículos a la venta
- **Line Items** - Líneas de artículos de un negocio

## Propiedades Comunes

### Propiedades de Contacto
- `email` - Dirección de correo electrónico
- `firstname`, `lastname` - Nombre
- `lifecyclestage` - Etapa del embudo
- `hs_lead_status` - Estado del lead

### Propiedades de Negocio
- `dealname` - Nombre del negocio
- `amount` - Valor del negocio
- `dealstage` - Etapa en el pipeline
- `closedate` - Cierre esperado

## Cuándo Usar

- Gestionar contactos y leads
- Seguimiento de negocios de ventas
- Automatización de marketing
- Envíos de formularios
- Campañas de correo electrónico
- Tickets de servicio al cliente

## Límites de Velocidad

- 100 solicitudes por 10 segundos
- Límites más altos en planes enterprise

## Skills Relevantes

- email-sequence
- analytics-tracking
- referral-program
