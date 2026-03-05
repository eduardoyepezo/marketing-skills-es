# Referencia de Implementación de Google Tag Manager

Guía detallada para implementar el seguimiento mediante Google Tag Manager.

## Contenidos
- Estructura del Contenedor (tags, triggers, variables)
- Convenciones de Nomenclatura
- Patrones de Capa de Datos
- Configuraciones Comunes de Tags (tag de configuración GA4, tag de evento GA4, pixel de Facebook)
- Vista Previa y Depuración
- Espacios de Trabajo y Versiones
- Gestión de Consentimiento
- Patrones Avanzados (secuenciación de tags, manejo de excepciones, variables de JavaScript personalizadas)

## Estructura del Contenedor

### Tags

Los tags son fragmentos de código que se ejecutan cuando se dispara un trigger.

**Tipos de tag comunes:**
- Configuración de GA4 (configuración base)
- Evento de GA4 (eventos personalizados)
- Conversión de Google Ads
- Pixel de Facebook
- LinkedIn Insight Tag
- HTML personalizado (para otros píxeles)

### Triggers

Los triggers definen cuándo se disparan los tags.

**Triggers integrados:**
- Vista de página: Todas las páginas, DOM listo, ventana cargada
- Clic: Todos los elementos, solo enlaces
- Envío de formulario
- Profundidad de scroll
- Temporizador
- Visibilidad de elemento

**Triggers personalizados:**
- Evento personalizado (desde dataLayer)
- Grupos de triggers (condiciones múltiples)

### Variables

Las variables capturan valores dinámicos.

**Integradas (activar según sea necesario):**
- Texto del clic, URL del clic, ID del clic, Clases del clic
- Ruta de página, URL de página, Hostname de página
- Referrer
- Elemento de formulario, ID de formulario

**Definidas por el usuario:**
- Variables de capa de datos
- Variables de JavaScript
- Tablas de búsqueda
- Tablas de expresiones regulares
- Constantes

---

## Convenciones de Nomenclatura

### Formato Recomendado

```
[Tipo] - [Descripción] - [Detalle]

Tags:
GA4 - Event - Signup Completed
GA4 - Config - Base Configuration
FB - Pixel - Page View
HTML - LiveChat Widget

Triggers:
Click - CTA Button
Submit - Contact Form
View - Pricing Page
Custom - signup_completed

Variables:
DL - user_id
JS - Current Timestamp
LT - Campaign Source Map
```

---

## Patrones de Capa de Datos

### Estructura Básica

```javascript
// Inicializar (en <head> antes de GTM)
window.dataLayer = window.dataLayer || [];

// Enviar evento
dataLayer.push({
  'event': 'nombre_del_evento',
  'propiedad1': 'valor1',
  'propiedad2': 'valor2'
});
```

### Datos de Carga de Página

```javascript
// Establecer al cargar la página (antes del contenedor GTM)
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  'pageType': 'product',
  'contentGroup': 'products',
  'user': {
    'loggedIn': true,
    'userId': '12345',
    'userType': 'premium'
  }
});
```

### Envío de Formulario

```javascript
document.querySelector('#contact-form').addEventListener('submit', function() {
  dataLayer.push({
    'event': 'form_submitted',
    'formName': 'contact',
    'formLocation': 'footer'
  });
});
```

### Clic en Botón

```javascript
document.querySelector('.cta-button').addEventListener('click', function() {
  dataLayer.push({
    'event': 'cta_clicked',
    'ctaText': this.innerText,
    'ctaLocation': 'hero'
  });
});
```

### Eventos de E-commerce

```javascript
// Vista de producto
dataLayer.push({ ecommerce: null }); // Limpiar el anterior
dataLayer.push({
  'event': 'view_item',
  'ecommerce': {
    'items': [{
      'item_id': 'SKU123',
      'item_name': 'Product Name',
      'price': 99.99,
      'item_category': 'Category',
      'quantity': 1
    }]
  }
});

// Agregar al carrito
dataLayer.push({ ecommerce: null });
dataLayer.push({
  'event': 'add_to_cart',
  'ecommerce': {
    'items': [{
      'item_id': 'SKU123',
      'item_name': 'Product Name',
      'price': 99.99,
      'quantity': 1
    }]
  }
});

// Compra
dataLayer.push({ ecommerce: null });
dataLayer.push({
  'event': 'purchase',
  'ecommerce': {
    'transaction_id': 'T12345',
    'value': 99.99,
    'currency': 'USD',
    'tax': 5.00,
    'shipping': 10.00,
    'items': [{
      'item_id': 'SKU123',
      'item_name': 'Product Name',
      'price': 99.99,
      'quantity': 1
    }]
  }
});
```

---

## Configuraciones Comunes de Tags

### Tag de Configuración de GA4

**Tipo de tag:** Google Analytics: Configuración de GA4

**Configuración:**
- ID de medición: G-XXXXXXXX
- Enviar vista de página: Marcado (para pageviews)
- Propiedades de usuario: Agregar dimensiones a nivel de usuario

**Trigger:** Todas las páginas

### Tag de Evento de GA4

**Tipo de tag:** Google Analytics: Evento de GA4

**Configuración:**
- Tag de configuración: Seleccionar el tag de configuración
- Nombre del evento: {{DL - event_name}} o hardcodeado
- Parámetros del evento: Agregar parámetros desde dataLayer

**Trigger:** Evento personalizado con coincidencia de nombre de evento

### Pixel de Facebook — Base

**Tipo de tag:** HTML personalizado

```html
<script>
  !function(f,b,e,v,n,t,s)
  {if(f.fbq)return;n=f.fbq=function(){n.callMethod?
  n.callMethod.apply(n,arguments):n.queue.push(arguments)};
  if(!f._fbq)f._fbq=n;n.push=n;n.loaded=!0;n.version='2.0';
  n.queue=[];t=b.createElement(e);t.async=!0;
  t.src=v;s=b.getElementsByTagName(e)[0];
  s.parentNode.insertBefore(t,s)}(window, document,'script',
  'https://connect.facebook.net/en_US/fbevents.js');
  fbq('init', 'YOUR_PIXEL_ID');
  fbq('track', 'PageView');
</script>
```

**Trigger:** Todas las páginas

### Pixel de Facebook — Evento

**Tipo de tag:** HTML personalizado

```html
<script>
  fbq('track', 'Lead', {
    content_name: '{{DL - form_name}}'
  });
</script>
```

**Trigger:** Evento personalizado — form_submitted

---

## Vista Previa y Depuración

### Modo de Vista Previa

1. Hacer clic en "Vista previa" en GTM
2. Ingresar la URL del sitio
3. El panel de depuración de GTM se abre en la parte inferior

**Qué verificar:**
- Tags disparados en este evento
- Tags no disparados (y por qué)
- Variables y sus valores
- Contenido de la capa de datos

### Consejos de Depuración

**Tag no disparándose:**
- Verificar las condiciones del trigger
- Confirmar el push a la capa de datos
- Revisar la secuenciación de tags

**Valor de variable incorrecto:**
- Verificar la estructura de la capa de datos
- Confirmar la ruta de la variable (objetos anidados)
- Revisar el momento (los datos pueden no existir aún)

**Múltiples disparos:**
- Verificar la unicidad del trigger
- Buscar tags duplicados
- Revisar las opciones de disparo del tag

---

## Espacios de Trabajo y Versiones

### Espacios de Trabajo

Usar espacios de trabajo para la colaboración en equipo:
- Espacio de trabajo predeterminado para producción
- Espacios de trabajo separados para cambios grandes
- Fusionar cuando estén listos

### Gestión de Versiones

**Mejores prácticas:**
- Nombrar cada versión de forma descriptiva
- Agregar notas explicando los cambios
- Revisar los cambios antes de publicar
- Mantener anotada la versión de producción

**Ejemplo de notas de versión:**
```
v15: Se agregó el seguimiento de conversión de compras
- Nuevo tag: GA4 - Event - Purchase
- Nuevo trigger: Custom Event - purchase
- Nuevas variables: DL - transaction_id, DL - value
- Probado en: Chrome, Safari, Móvil
```

---

## Gestión de Consentimiento

### Integración del Modo de Consentimiento

```javascript
// Estado predeterminado (antes del consentimiento)
gtag('consent', 'default', {
  'analytics_storage': 'denied',
  'ad_storage': 'denied'
});

// Actualizar al obtener consentimiento
function grantConsent() {
  gtag('consent', 'update', {
    'analytics_storage': 'granted',
    'ad_storage': 'granted'
  });
}
```

### Resumen de Consentimiento en GTM

1. Activar Resumen de consentimiento en Administrar
2. Configurar el consentimiento para cada tag
3. Los tags respetan automáticamente el estado de consentimiento

---

## Patrones Avanzados

### Secuenciación de Tags

**Configurar tags para que se disparen en orden:**
Configuración del tag > Configuración avanzada > Secuencia del tag

**Casos de uso:**
- Tag de configuración antes de los tags de eventos
- Inicialización del píxel antes del seguimiento
- Limpieza después de la conversión

### Manejo de Excepciones

**Excepciones de triggers** — Evitar que un tag se dispare:
- Excluir ciertas páginas
- Excluir tráfico interno
- Excluir durante las pruebas

### Variables de JavaScript Personalizadas

```javascript
// Obtener parámetro de URL
function() {
  var params = new URLSearchParams(window.location.search);
  return params.get('campaign') || '(not set)';
}

// Obtener valor de cookie
function() {
  var match = document.cookie.match('(^|;) ?user_id=([^;]*)(;|$)');
  return match ? match[2] : null;
}

// Obtener datos de la página
function() {
  var el = document.querySelector('.product-price');
  return el ? parseFloat(el.textContent.replace('$', '')) : 0;
}
```
