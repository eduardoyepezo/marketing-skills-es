# Referencia de Implementación de GA4

Guía de implementación detallada para Google Analytics 4.

## Contenidos
- Configuración (flujos de datos, eventos de medición mejorada, eventos recomendados)
- Eventos Personalizados (implementación con gtag.js, Google Tag Manager)
- Configuración de Conversiones (crear conversiones, valores de conversión)
- Dimensiones y Métricas Personalizadas (cuándo usarlas, pasos de configuración, ejemplos)
- Audiencias (crear audiencias, ejemplos de audiencias)
- Depuración (DebugView, informes en tiempo real, problemas comunes)
- Calidad de Datos (filtros, seguimiento entre dominios, configuración de sesión)
- Integración con Google Ads (vinculación, exportación de audiencias)

## Configuración

### Flujos de Datos

- Un flujo por plataforma (web, iOS, Android)
- Activar medición mejorada para el seguimiento automático
- Configurar la retención de datos (2 meses por defecto, 14 meses máximo)
- Activar Google Signals (para múltiples dispositivos, si hay consentimiento)

### Eventos de Medición Mejorada (Automáticos)

| Evento | Descripción | Configuración |
|--------|-------------|---------------|
| page_view | Cargas de página | Automático |
| scroll | Profundidad de scroll al 90% | Activar/desactivar |
| outbound_click | Clic hacia un dominio externo | Automático |
| site_search | Consulta de búsqueda usada | Configurar parámetro |
| video_engagement | Reproducción de videos de YouTube | Activar/desactivar |
| file_download | PDF, documentos, etc. | Extensiones configurables |

### Eventos Recomendados

Usar los eventos predefinidos de Google cuando sea posible para obtener informes mejorados:

**Todas las propiedades:**
- login, sign_up
- share
- search

**E-commerce:**
- view_item, view_item_list
- add_to_cart, remove_from_cart
- begin_checkout
- add_payment_info
- purchase, refund

**Juegos:**
- level_up, unlock_achievement
- post_score, spend_virtual_currency

Referencia: https://support.google.com/analytics/answer/9267735

---

## Eventos Personalizados

### Implementación con gtag.js

```javascript
// Evento básico
gtag('event', 'signup_completed', {
  'method': 'email',
  'plan': 'free'
});

// Evento con valor
gtag('event', 'purchase', {
  'transaction_id': 'T12345',
  'value': 99.99,
  'currency': 'USD',
  'items': [{
    'item_id': 'SKU123',
    'item_name': 'Product Name',
    'price': 99.99
  }]
});

// Propiedades de usuario
gtag('set', 'user_properties', {
  'user_type': 'premium',
  'plan_name': 'pro'
});

// ID de usuario (para usuarios autenticados)
gtag('config', 'GA_MEASUREMENT_ID', {
  'user_id': 'USER_ID'
});
```

### Google Tag Manager (dataLayer)

```javascript
// Evento personalizado
dataLayer.push({
  'event': 'signup_completed',
  'method': 'email',
  'plan': 'free'
});

// Establecer propiedades de usuario
dataLayer.push({
  'user_id': '12345',
  'user_type': 'premium'
});

// Compra de e-commerce
dataLayer.push({
  'event': 'purchase',
  'ecommerce': {
    'transaction_id': 'T12345',
    'value': 99.99,
    'currency': 'USD',
    'items': [{
      'item_id': 'SKU123',
      'item_name': 'Product Name',
      'price': 99.99,
      'quantity': 1
    }]
  }
});

// Limpiar ecommerce antes de enviar (buena práctica)
dataLayer.push({ ecommerce: null });
dataLayer.push({
  'event': 'view_item',
  'ecommerce': {
    // ...
  }
});
```

---

## Configuración de Conversiones

### Crear Conversiones

1. **Recopilar el evento** — Asegurarse de que el evento se dispara en GA4
2. **Marcar como conversión** — Administrar > Eventos > Marcar como conversión
3. **Establecer el método de conteo**:
   - Una vez por sesión (leads, registros)
   - Cada evento (compras)
4. **Importar a Google Ads** — Para pujas optimizadas por conversiones

### Valores de Conversión

```javascript
// Evento con valor de conversión
gtag('event', 'purchase', {
  'value': 99.99,
  'currency': 'USD'
});
```

O establecer el valor por defecto en el Administrador de GA4 al marcar la conversión.

---

## Dimensiones y Métricas Personalizadas

### Cuándo Usarlas

**Dimensiones personalizadas:**
- Propiedades por las que quieres segmentar/filtrar
- Atributos de usuario (tipo de plan, industria)
- Atributos de contenido (autor, categoría)

**Métricas personalizadas:**
- Valores numéricos a agregar
- Puntuaciones, conteos, duraciones

### Pasos de Configuración

1. Administrar > Visualización de datos > Definiciones personalizadas
2. Crear dimensión o métrica
3. Elegir alcance:
   - **Evento**: Por evento (content_type)
   - **Usuario**: Por usuario (account_type)
   - **Ítem**: Por producto (product_category)
4. Ingresar nombre del parámetro (debe coincidir con el parámetro del evento)

### Ejemplos

| Dimensión | Alcance | Parámetro | Descripción |
|-----------|---------|-----------|-------------|
| Tipo de Usuario | Usuario | user_type | Gratuito, prueba, de pago |
| Autor de Contenido | Evento | author | Autor del post del blog |
| Categoría de Producto | Ítem | item_category | Categoría de e-commerce |

---

## Audiencias

### Crear Audiencias

Administrar > Visualización de datos > Audiencias

**Casos de uso:**
- Audiencias de remarketing (exportar a Ads)
- Análisis por segmento
- Eventos basados en disparadores

### Ejemplos de Audiencias

**Visitantes de alta intención:**
- Vieron la página de precios
- No convirtieron
- En los últimos 7 días

**Usuarios comprometidos:**
- 3+ sesiones
- O 5+ minutos de engagement total

**Compradores:**
- Evento de compra
- Para exclusión o audiencia similar

---

## Depuración

### DebugView

Activar con:
- Parámetro de URL: `?debug_mode=true`
- Extensión de Chrome: GA Debugger
- gtag: `'debug_mode': true` en la configuración

Ver en: Informes > Configurar > DebugView

### Informes en Tiempo Real

Verificar eventos en los últimos 30 minutos:
Informes > Tiempo real

### Problemas Comunes

**Eventos que no aparecen:**
- Verificar DebugView primero
- Confirmar que gtag/GTM está disparando
- Revisar exclusiones de filtros

**Valores de parámetros faltantes:**
- Dimensión personalizada no creada
- Nombre del parámetro no coincide
- Datos aún en procesamiento (24-48 h)

**Conversiones que no se registran:**
- Evento no marcado como conversión
- Nombre del evento no coincide
- Método de conteo (una vez vs. cada vez)

---

## Calidad de Datos

### Filtros

Administrar > Flujos de datos > [Flujo] > Configurar ajustes de etiqueta > Definir tráfico interno

**Excluir:**
- Direcciones IP internas
- Tráfico de desarrolladores
- Entornos de prueba

### Seguimiento entre Dominios

Para múltiples dominios que comparten analíticas:

1. Administrar > Flujos de datos > [Flujo] > Configurar ajustes de etiqueta
2. Configurar tus dominios
3. Listar todos los dominios que deben compartir sesiones

### Configuración de Sesión

Administrar > Flujos de datos > [Flujo] > Configurar ajustes de etiqueta

- Tiempo de espera de sesión (30 min por defecto)
- Duración de sesión comprometida (10 seg por defecto)

---

## Integración con Google Ads

### Vinculación

1. Administrar > Vínculos de producto > Vínculos de Google Ads
2. Activar el etiquetado automático en Google Ads
3. Importar conversiones en Google Ads

### Exportación de Audiencias

Las audiencias creadas en GA4 pueden usarse en Google Ads para:
- Campañas de remarketing
- Customer match
- Audiencias similares
