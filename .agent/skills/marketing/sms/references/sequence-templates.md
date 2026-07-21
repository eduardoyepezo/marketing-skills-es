# Plantillas de Secuencia de SMS

Plantillas de copy completas con conteo de caracteres, tiempos y lógica de segmentación para cada flujo principal de SMS.

> Los conteos de caracteres mostrados asumen codificación GSM-7. Los emojis fuerzan UCS-2 (70 caracteres/segmento en lugar de 160). Todas las plantillas usan `[Brand]`, `[FirstName]`, y `[short.link]` como tokens de sustitución.
>
> **Nota sobre los conteos en esta traducción:** el texto en español suele ser más largo que el original en inglés, así que los conteos aproximados de cada plantilla pueden variar unos cuantos caracteres frente al real. Ninguno de los casos restantes cruza el umbral de 160 (siguen siendo 1 segmento), pero vuelve a contar el texto final en tu plataforma de envío antes de usarlo en producción.

---

## Bienvenida / Confirmación de Opt-In

### Envío 1 — Inmediato (después del opt-in)

```
From [Brand]: ¡Bienvenido! Aquí tu código de 10% de descuento: WELCOME10. Compra ahora: [short.link]
Responde STOP para darte de baja, HELP para ayuda. Pueden aplicar tarifas de mensajes y datos.
```
~195 caracteres / **2 segmentos** (el texto en español es más largo que el original en inglés y cruza el umbral de 160). Pie de página requerido en el primer envío.

### Envío 2 — 24 horas después (opcional)

```
From [Brand]: No olvides tu código WELCOME10 — expira en 48hrs. Los favoritos: [short.link]
```
~108 caracteres / 1 segmento.

### Envío 3 — 7 días después (opcional, condicionado a no compra)

```
From [Brand]: Última oportunidad de 10% de descuento con WELCOME10. Expira esta noche a medianoche: [short.link]
```
~107 caracteres / 1 segmento.

---

## Carrito Abandonado (flujo de mayor ROI para ecommerce)

### Envío 1 — 30 minutos después del abandono

```
From [Brand]: Oye [FirstName], ¡dejaste algo atrás! Tu carrito está aquí: [short.link]
```
~95 caracteres / 1 segmento.

### Envío 2 — 4 horas después del abandono (si no hay compra)

```
From [Brand]: Los artículos en tu carrito se están agotando. Reservados para ti por 24hrs: [short.link]
```
~98 caracteres / 1 segmento.

### Envío 3 — 24 horas después del abandono (si no hay compra, descuento permitido)

```
From [Brand]: ¿Sigues pensándolo? Aquí tu 10% de descuento para cerrar el trato: SAVE10. Compra: [short.link]
```
~99 caracteres / 1 segmento.

**Notas**:
- El descuento en el Envío 1 entrena a los clientes a abandonar. Resérvalo para el Envío 2 o 3.
- Excluye a los clientes que abandonaron con un valor de carrito menor a $X o a los abandonadores recurrentes (que abusan del descuento).
- Detén la secuencia al ocurrir una compra, un opt-out, o al pasar 48 horas.

---

## Abandono de Navegación (Browse Abandonment)

### Envío 1 — 1 hora después de navegar (producto o categoría única)

```
From [Brand]: ¿Sigues pensando en [producto]? Échale otro vistazo: [short.link]
```
~84 caracteres / 1 segmento.

**Notas**:
- Dispara solo después de una señal de navegación significativa (3+ vistas de producto o 2+ min en la página del producto).
- Excluye si ocurrió una compra de un producto diferente.

---

## Flujo Post-Compra

### Envío 1 — Inmediatamente después de la compra (transaccional, consentimiento separado)

```
From [Brand]: ¡Pedido #12345 confirmado! Te enviaremos actualizaciones de envío aquí. Rastrea: [short.link]
```
~95 caracteres / 1 segmento.

### Envío 2 — Día del envío

```
From [Brand]: Tu pedido va en camino. Entrega estimada: [fecha]. Rastrea: [short.link]
```
~92 caracteres / 1 segmento.

### Envío 3 — Día de la entrega

```
From [Brand]: ¡Tu pedido debería llegar hoy! ¿Preguntas? Responde o visita [short.link]
```
~88 caracteres / 1 segmento.

### Envío 4 — 2 días después de la entrega (requiere consentimiento de marketing)

```
From [Brand]: ¿Qué te pareció tu [producto]? Comparte una reseña por 15% de descuento en tu próximo pedido: [short.link]
```
~108 caracteres / 1 segmento.

### Envío 5 — 14 días después de la entrega (cross-sell, consentimiento de marketing)

```
From [Brand]: Combina perfecto con tu [producto]: [related-item]. 10% de descuento en el combo: [short.link]
```
~99 caracteres / 1 segmento.

---

## Recuperación de Clientes Inactivos (Win-Back)

### Envío 1 — 60-90 días después de la última compra

```
From [Brand]: [FirstName], ¡te extrañamos! Selección que creemos que te encantará: [short.link]
```
~84 caracteres / 1 segmento.

### Envío 2 — 14 días después (si no hay compra)

```
From [Brand]: Regresa por 15% de descuento en tu próximo pedido: COMEBACK15. Expira en 7 días: [short.link]
```
~106 caracteres / 1 segmento.

### Envío 3 — 14 días después del Envío 2 (final, si no hay compra)

```
From [Brand]: Última oportunidad — 20% de descuento termina esta noche: COMEBACK20. Dejamos de escribirte si prefieres: responde STOP. [short.link]
```
~130 caracteres / 1 segmento.

**Notas**:
- Después del Envío 3 sin engagement, suprime por un mínimo de 90 días.
- Después de dos ciclos completos de win-back sin engagement, retira definitivamente (elimina de la lista activa).

---

## Envíos Promocionales / de Campaña

### Venta flash (envío único)

```
From [Brand]: FLASH DE 24 HORAS: 25% de descuento en todo con FLASH25. Termina a medianoche: [short.link]
```
~94 caracteres / 1 segmento.

### Drop limitado / lanzamiento

```
From [Brand]: Nuevo drop recién llegado: [product-name]. Stock limitado, los miembros tienen acceso anticipado: [short.link]
```
~115 caracteres / 1 segmento.

### Días festivos / BFCM (secuencia de 2 envíos)

Envío 1 — Día del lanzamiento:
```
From [Brand]: El Black Friday ya está AQUÍ — hasta 50% de descuento en todo. Compra ahora: [short.link]
```
~92 caracteres / 1 segmento.

Envío 2 — El mismo día (o en la noche, empuje de expiración):
```
From [Brand]: Últimas 6 horas de descuentos de BFCM. No te lo pierdas: [short.link]
```
~73 caracteres / 1 segmento.

---

## Transaccional / Notificaciones de Cuenta

### Confirmación de pedido

```
[Brand]: Pedido #12345 confirmado. Total $XX.XX. Rastrea en [short.link]. Responde HELP para ayuda.
```

### Actualización de envío

```
[Brand]: ¡Tu pedido #12345 fue enviado! Rastrea: [short.link]. ETA [fecha].
```

### Confirmación de entrega

```
[Brand]: Pedido #12345 entregado. ¡Disfrútalo! ¿Problemas? Responde o [support-link].
```

### Código de autenticación (2FA)

```
[Brand] código de verificación: 123456. Expira en 10 min. No lo compartas.
```

### Alerta de cuenta

```
[Brand]: Inicio de sesión desde un nuevo dispositivo en [ubicación]. ¿No fuiste tú? Asegura tu cuenta: [short.link]
```

---

## Re-Engagement / Reactivación (Suscriptores que se Enfriaron)

Para suscriptores de SMS que no han interactuado con ningún envío en 60+ días.

### Envío 1 — Reactivación suave

```
From [Brand]: ¡Te extrañamos, [FirstName]! Esto es lo nuevo: [short.link]
```
~80 caracteres / 1 segmento.

### Envío 2 — Confirmar interés (si no hay engagement)

```
From [Brand]: ¿Quieres seguir sabiendo de nosotros? Responde YES para seguir en la lista, o STOP para darte de baja.
```
~98 caracteres / 1 segmento.

Tras no recibir respuesta: suprime por 60 días, luego elimina de la lista activa. Esto protege las métricas de tasa de opt-out y reduce el gasto desperdiciado.

---

## Reabastecimiento (Ecommerce de Consumibles)

Para productos con ciclos de uso predecibles (skincare, suplementos, café, alimento para mascotas).

### Envío 1 — En la ventana esperada de reorden (p. ej., 28 días para un suministro de 30 días)

```
From [Brand]: ¿Se te está acabando [producto]? Reordena con un solo toque: [short.link]
```
~73 caracteres / 1 segmento.

### Envío 2 — 7 días después (si no hay compra)

```
From [Brand]: ¡No te quedes sin! 10% de descuento en tu reorden de [producto]: REFILL10 [short.link]
```
~92 caracteres / 1 segmento.

---

## Miembros VIP / Lealtad

Mayor frecuencia, ofertas exclusivas, acceso anticipado — aplican reglas de cadencia distintas, pero el horario de silencio y STOP siguen siendo requeridos.

### Acceso anticipado

```
From [Brand]: Los VIP tienen el nuevo drop 24hrs antes. Ya es tuyo: [short.link]
```
~72 caracteres / 1 segmento.

### Hito de lealtad

```
From [Brand]: ¡Alcanzaste el estatus Gold! Tus beneficios: 15% de descuento + envío gratis. [short.link]
```
~95 caracteres / 1 segmento.

---

## Reglas de segmentación en todos los flujos

- **Suprime** a los clientes en secuencias activas de los envíos promocionales (sin doble impacto)
- **Suprime** a los suscriptores que se dieron de baja de todo (la plataforma maneja esto)
- **Límite de frecuencia**: máximo 4–6 envíos de marketing/semana por suscriptor (menor para suscriptores más nuevos)
- **Horario de silencio**: 9am–8pm hora local del destinatario
- **Enfriamiento (cool-off)**: después de una compra impulsada por descuento, suprime los envíos promocionales por 14 días
