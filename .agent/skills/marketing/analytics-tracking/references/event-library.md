# Referencia de Biblioteca de Eventos

Lista exhaustiva de eventos a rastrear por tipo de negocio y contexto.

## Contenidos
- Eventos del Sitio de Marketing (navegación y engagement, CTAs e interacciones con formularios, eventos de conversión)
- Eventos de Producto/App (onboarding, uso central, errores y soporte)
- Eventos de Monetización (precios y checkout, gestión de suscripciones)
- Eventos de E-commerce (navegación, carrito, checkout, post-compra)
- Eventos Específicos de B2B / SaaS (equipo y colaboración, eventos de integración, eventos de cuenta)
- Propiedades de Eventos (Parámetros)
- Secuencias de Eventos del Embudo

## Eventos del Sitio de Marketing

### Navegación y Engagement

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| page_view | Página cargada (mejorada) | page_title, page_location, content_group |
| scroll_depth | Usuario scrolló a un umbral | depth (25, 50, 75, 100) |
| outbound_link_clicked | Clic a sitio externo | link_url, link_text |
| internal_link_clicked | Clic dentro del sitio | link_url, link_text, location |
| video_played | Video iniciado | video_id, video_title, duration |
| video_completed | Video finalizado | video_id, video_title, duration |

### CTAs e Interacciones con Formularios

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| cta_clicked | Llamada a la acción clicada | button_text, cta_location, page |
| form_started | Usuario comenzó un formulario | form_name, form_location |
| form_field_completed | Campo completado | form_name, field_name |
| form_submitted | Formulario enviado exitosamente | form_name, form_location |
| form_error | Validación del formulario falló | form_name, error_type |
| resource_downloaded | Recurso descargado | resource_name, resource_type |

### Eventos de Conversión

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| signup_started | Registro iniciado | source, page |
| signup_completed | Registro finalizado | method, plan, source |
| demo_requested | Formulario de demo enviado | company_size, industry |
| contact_submitted | Formulario de contacto enviado | inquiry_type |
| newsletter_subscribed | Suscripción a lista de email | source, list_name |
| trial_started | Prueba gratuita iniciada | plan, source |

---

## Eventos de Producto/App

### Onboarding

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| signup_completed | Cuenta creada | method, referral_source |
| onboarding_started | Onboarding iniciado | - |
| onboarding_step_completed | Paso finalizado | step_number, step_name |
| onboarding_completed | Todos los pasos finalizados | steps_completed, time_to_complete |
| onboarding_skipped | Usuario omitió el onboarding | step_skipped_at |
| first_key_action_completed | Momento aha alcanzado | action_type |

### Uso Central

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| session_started | Sesión de app iniciada | session_number |
| feature_used | Interacción con función | feature_name, feature_category |
| action_completed | Acción central realizada | action_type, count |
| content_created | Usuario creó contenido | content_type |
| content_edited | Usuario modificó contenido | content_type |
| content_deleted | Usuario eliminó contenido | content_type |
| search_performed | Búsqueda en la app | query, results_count |
| settings_changed | Configuración modificada | setting_name, new_value |
| invite_sent | Usuario invitó a otros | invite_type, count |

### Errores y Soporte

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| error_occurred | Error experimentado | error_type, error_message, page |
| help_opened | Ayuda accedida | help_type, page |
| support_contacted | Solicitud de soporte realizada | contact_method, issue_type |
| feedback_submitted | Retroalimentación del usuario dada | feedback_type, rating |

---

## Eventos de Monetización

### Precios y Checkout

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| pricing_viewed | Página de precios vista | source |
| plan_selected | Plan elegido | plan_name, billing_cycle |
| checkout_started | Checkout iniciado | plan, value |
| payment_info_entered | Pago enviado | payment_method |
| purchase_completed | Compra exitosa | plan, value, currency, transaction_id |
| purchase_failed | Compra fallida | error_reason, plan |

### Gestión de Suscripciones

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| trial_started | Prueba iniciada | plan, trial_length |
| trial_ended | Prueba expirada | plan, converted (bool) |
| subscription_upgraded | Plan actualizado | from_plan, to_plan, value |
| subscription_downgraded | Plan degradado | from_plan, to_plan |
| subscription_cancelled | Cancelado | plan, reason, tenure |
| subscription_renewed | Renovado | plan, value |
| billing_updated | Método de pago cambiado | - |

---

## Eventos de E-commerce

### Navegación

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| product_viewed | Página de producto vista | product_id, product_name, category, price |
| product_list_viewed | Categoría/lista vista | list_name, products[] |
| product_searched | Búsqueda realizada | query, results_count |
| product_filtered | Filtros aplicados | filter_type, filter_value |
| product_sorted | Ordenamiento aplicado | sort_by, sort_order |

### Carrito

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| product_added_to_cart | Artículo agregado | product_id, product_name, price, quantity |
| product_removed_from_cart | Artículo eliminado | product_id, product_name, price, quantity |
| cart_viewed | Página del carrito vista | cart_value, items_count |

### Checkout

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| checkout_started | Checkout iniciado | cart_value, items_count |
| checkout_step_completed | Paso finalizado | step_number, step_name |
| shipping_info_entered | Dirección ingresada | shipping_method |
| payment_info_entered | Pago ingresado | payment_method |
| coupon_applied | Cupón usado | coupon_code, discount_value |
| purchase_completed | Pedido realizado | transaction_id, value, currency, items[] |

### Post-Compra

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| order_confirmed | Confirmación vista | transaction_id |
| refund_requested | Reembolso iniciado | transaction_id, reason |
| refund_completed | Reembolso procesado | transaction_id, value |
| review_submitted | Producto reseñado | product_id, rating |

---

## Eventos Específicos de B2B / SaaS

### Equipo y Colaboración

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| team_created | Nuevo equipo/org creado | team_size, plan |
| team_member_invited | Invitación enviada | role, invite_method |
| team_member_joined | Miembro aceptó | role |
| team_member_removed | Miembro eliminado | role |
| role_changed | Permisos actualizados | user_id, old_role, new_role |

### Eventos de Integración

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| integration_viewed | Página de integración vista | integration_name |
| integration_started | Configuración iniciada | integration_name |
| integration_connected | Conectado exitosamente | integration_name |
| integration_disconnected | Integración eliminada | integration_name, reason |

### Eventos de Cuenta

| Nombre del Evento | Descripción | Propiedades |
|------------|-------------|------------|
| account_created | Nueva cuenta | source, plan |
| account_upgraded | Actualización de plan | from_plan, to_plan |
| account_churned | Cuenta cerrada | reason, tenure, mrr_lost |
| account_reactivated | Cliente que regresa | previous_tenure, new_plan |

---

## Propiedades de Eventos (Parámetros)

### Propiedades Estándar a Incluir

**Contexto de Usuario:**
```
user_id: "12345"
user_type: "free" | "trial" | "paid"
account_id: "acct_123"
plan_type: "starter" | "pro" | "enterprise"
```

**Contexto de Sesión:**
```
session_id: "sess_abc"
session_number: 5
page: "/pricing"
referrer: "https://google.com"
```

**Contexto de Campaña:**
```
source: "google"
medium: "cpc"
campaign: "spring_sale"
content: "hero_cta"
```

**Contexto de Producto (E-commerce):**
```
product_id: "SKU123"
product_name: "Nombre del Producto"
category: "Categoría"
price: 99.99
quantity: 1
currency: "USD"
```

**Tiempo:**
```
timestamp: "2024-01-15T10:30:00Z"
time_on_page: 45
session_duration: 300
```

---

## Secuencias de Eventos del Embudo

### Embudo de Registro
1. signup_started
2. signup_step_completed (email)
3. signup_step_completed (contraseña)
4. signup_completed
5. onboarding_started

### Embudo de Compra
1. pricing_viewed
2. plan_selected
3. checkout_started
4. payment_info_entered
5. purchase_completed

### Embudo de E-commerce
1. product_viewed
2. product_added_to_cart
3. cart_viewed
4. checkout_started
5. shipping_info_entered
6. payment_info_entered
7. purchase_completed
