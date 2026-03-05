# Playbook de Dunning

Guía completa para recuperar pagos fallidos y reducir el churn involuntario.

---

## Por Qué Importa el Dunning

- Los pagos fallidos causan el 30-50% de todo el churn de suscripciones
- La mayoría de los pagos fallidos son recuperables con la estrategia correcta
- Las empresas de suscripciones pierden an estimated $129 mil millones al año por churn involuntario
- Un dunning efectivo recupera el 50-60% de los pagos fallidos

---

## La Cronología del Dunning

```
Día -30 a -7:  Pre-dunning (prevenir fallos)
Día 0:         El pago falla → Reintento inteligente #1 + Correo #1
Día 1-3:       Reintento inteligente #2 + Correo #2
Día 3-5:       Reintento inteligente #3
Día 5-7:       Reintento inteligente #4 + Correo #3
Día 7-10:      Reintento final + Correo #4 (última advertencia)
Día 10-14:     Fin del período de gracia → Cuenta pausada/cancelada
Día 14+:       Comienza la secuencia de win-back
```

---

## Pre-Dunning: Prevenir Fallos Antes de que Ocurran

### Gestión del Vencimiento de Tarjetas

| Momento | Acción |
|---------|--------|
| 30 días antes del vencimiento | Correo: "Tu tarjeta terminada en 4242 vence el próximo mes" |
| 15 días antes del vencimiento | Correo: "Actualiza tu método de pago para evitar interrupciones" |
| 7 días antes del vencimiento | Correo: "Tu tarjeta vence en 7 días — actualiza ahora" |
| 3 días antes del vencimiento | Banner en la app: "Método de pago próximo a vencer" |

**Plantilla de correo — Tarjeta próxima a vencer:**
```
Asunto: Tu tarjeta terminada en 4242 vence pronto

Hola [Nombre],

La tarjeta registrada para tu suscripción a [Producto] vence el [fecha].

Actualiza tu método de pago ahora para evitar cualquier interrupción:

[Actualizar Método de Pago →]

Toma menos de 30 segundos.

— El equipo de [Producto]
```

### Servicios de Actualización de Tarjetas

Las principales redes de tarjetas ofrecen programas de actualización automática:

| Servicio | Red | Qué hace |
|---------|-----|----------|
| Visa Account Updater (VAU) | Visa | Actualiza automáticamente números de tarjeta y fechas de vencimiento almacenados |
| Mastercard Automatic Billing Updater (ABU) | Mastercard | Lo mismo para Mastercard |
| Amex Cardrefresher | American Express | Lo mismo para Amex |

**Impacto:** Reduce los rechazos duros por tarjetas vencidas o reemplazadas en un 30-50%.

**Cómo activarlo:**
- **Stripe**: Automático — activado por defecto
- **Chargebee**: Activado a través de la configuración del gateway
- **Recurly**: Integrado, activado por defecto
- **Braintree**: Contactar al procesador para activarlo

### Métodos de Pago de Respaldo

Solicitar un segundo método de pago:
- Durante el registro: "Agrega un método de pago de respaldo" (baja conversión)
- Después del primer pago exitoso: "Protege tu cuenta con una tarjeta de respaldo" (mejor momento)
- Después de recuperar un pago fallido: "Agrega un respaldo para prevenir futuras interrupciones" (mejor momento — ya sintieron el problema)

### Notificaciones Pre-Cobro

Para planes anuales o suscripciones de alto valor:
- Correo 7 días antes de la renovación con el monto y la fecha
- Incluir enlace para actualizar el método de pago
- Mostrar qué está incluido en la renovación
- Requerido por algunas regulaciones para renovaciones automáticas

---

## Estrategia de Reintentos Inteligentes

### Clasificación del Tipo de Rechazo

| Código | Tipo | Significado | ¿Reintentar? |
|--------|------|-------------|--------------|
| `insufficient_funds` | Suave | Saldo temporalmente bajo | Sí — reintentar en 2-3 días |
| `card_declined` (genérico) | Suave | Varias razones temporales | Sí — reintentar 3-4 veces |
| `processing_error` | Suave | Problema de gateway/red | Sí — reintentar en 24h |
| `expired_card` | Duro | La tarjeta está vencida | No — solicitar nueva tarjeta |
| `stolen_card` | Duro | Tarjeta reportada como robada | No — solicitar nueva tarjeta |
| `do_not_honor` | Suave/Duro | El banco rechazó (ambiguo) | Intentar una vez más, luego pedir nueva tarjeta |
| `authentication_required` | Auth | Se requiere SCA/3DS | Enviar al cliente a autenticar |

### Calendario de Reintentos por Proveedor

**Stripe (Smart Retries — recomendado):**
- Activar "Smart Retries" en el Panel de Stripe → Facturación → Configuración
- El modelo ML de Stripe elige el momento óptimo de reintento basándose en miles de millones de transacciones
- Típicamente 4-8 intentos de reintento en 3-4 semanas
- Recupera ~15% más que los reintentos con calendario fijo

**Calendario de reintentos manual (si no hay reintentos inteligentes):**

| Reintento | Momento | Mejor día/hora |
|-----------|---------|----------------|
| 1 | Día 1 (24h después del fallo) | Mañana, mismo día de la semana que el original |
| 2 | Día 3 | Probar una hora diferente del día |
| 3 | Día 5 | Después del día de pago típico (1, 15) |
| 4 | Día 7 | Mañana del siguiente día hábil |
| 5 (final) | Día 10 | Último intento antes de que termine el período de gracia |

**Insights sobre el momento de reintento:**
- Reintentar el mismo día del mes en que el pago original tuvo éxito
- Reintentar después de los días de pago comunes (el 1 y el 15 del mes)
- Evitar reintentar los fines de semana (tasas de aprobación más bajas)
- Los reintentos por la mañana (8-10 am hora local) funcionan ligeramente mejor

---

## Secuencia de Correos de Dunning

### Correo 1: Pago Fallido (Día 0)

**Tono:** Amigable, directo. Sin alarma.

```
Asunto: Acción requerida — tu pago no se procesó

Hola [Nombre],

Intentamos cobrar a tu [tipo de tarjeta] terminada en [últimos 4] por tu
suscripción a [Producto] ($[monto]), pero no se procesó.

Esto pasa a veces — generalmente actualizando la tarjeta se soluciona.

[Actualizar Método de Pago →]

Tu acceso no se ha visto afectado todavía. Reintentaremos automáticamente, pero
actualizar tu tarjeta es la solución más rápida.

¿Necesitas ayuda? Solo responde a este correo.

— El equipo de [Producto]
```

### Correo 2: Recordatorio (Día 3)

**Tono:** Útil, un poco más urgente.

```
Asunto: Recordatorio rápido — actualiza tu pago para [Producto]

Hola [Nombre],

Solo un aviso — todavía no hemos podido procesar tu
pago de $[monto] por [Producto].

[Actualizar Método de Pago →]

Toma menos de 30 segundos. Tus [datos/proyectos/acceso del equipo]
están seguros, pero necesitamos un método de pago válido para mantener tu
cuenta activa.

¿Tienes preguntas? Responde aquí y te ayudamos.

— El equipo de [Producto]
```

### Correo 3: Urgencia (Día 7)

**Tono:** Directo, consecuencias claras.

```
Asunto: Tu cuenta de [Producto] será pausada en 3 días

Hola [Nombre],

Hemos intentado procesar tu pago varias veces, pero tu
[tipo de tarjeta] terminada en [últimos 4] sigue siendo rechazada.

Si no recibimos el pago para el [fecha], tu cuenta será
pausada y perderás acceso a:

• [Función clave/datos que usan]
• [Sus proyectos/espacio de trabajo]
• [Acceso del equipo para X miembros]

[Actualizar Método de Pago Ahora →]

Tus datos no serán eliminados — puedes reactivar en cualquier momento
actualizando tu método de pago.

— El equipo de [Producto]
```

### Correo 4: Última Advertencia (Día 10)

**Tono:** Final, claro, sin culpa.

```
Asunto: Última oportunidad para mantener tu cuenta de [Producto] activa

Hola [Nombre],

Este es nuestro último recordatorio. Tu pago de $[monto] está
vencido, y tu cuenta será pausada mañana ([fecha]).

[Actualizar Método de Pago →]

Después de la pausa:
• Tus datos se guardan por [90 días]
• Puedes reactivar en cualquier momento
• Solo actualiza tu tarjeta para restablecer el acceso

Si tenías intención de cancelar, no es necesaria ninguna acción — tu cuenta
será pausada automáticamente.

— El equipo de [Producto]
```

---

## Gestión del Período de Gracia

### Qué Sucede Durante el Período de Gracia

| Configuración | Recomendación |
|---------------|---------------|
| Duración | 7-14 días después del último reintento |
| Acceso | Degradado (solo lectura) o acceso completo |
| Visibilidad | Banner en la app: "Pago vencido — actualiza para continuar" |
| Reintento | Continuar los reintentos en segundo plano durante la gracia |
| Comunicación | Los correos de dunning continúan |

### Opciones de Degradación del Acceso

**Opción A: Acceso completo durante la gracia (recomendado para B2B)**
- Menor fricción, el cliente se siente respetado
- Mayor tasa de recuperación (siguen viendo el valor)
- Riesgo: algunos clientes aprovechan el período de gracia

**Opción B: Acceso de solo lectura (recomendado para B2C)**
- Pueden ver pero no crear/editar
- Crea urgencia sin miedo a pérdida de datos
- Mensaje claro: "Actualiza el pago para retomar el acceso completo"

**Opción C: Bloqueo inmediato (no recomendado)**
- Agresivo, daña la relación
- Menor tasa de recuperación
- Solo apropiado para planes de muy bajo costo

### Post-Período de Gracia

| Momento | Acción |
|---------|--------|
| Fin del período de gracia | Pausar cuenta (no eliminar) |
| Día 1 post-pausa | Correo "Tu cuenta ha sido pausada" |
| Día 7 post-pausa | Recordatorio "Tus datos siguen aquí" |
| Día 30 post-pausa | Intento de win-back con nueva oferta |
| Día 60 post-pausa | Win-back final |
| Día 90 post-pausa | Aviso de eliminación de datos (si aplica) |

---

## Configuración por Proveedor

### Stripe

**Activar Smart Retries:**
1. Panel → Configuración → Facturación → Suscripciones y correos
2. Activar "Smart Retries" en las reglas de reintento
3. Configurar correos de pago fallido en Panel → Configuración → Correos

**Reglas de reintento personalizadas (si no usas Smart Retries):**
```
Reintento 1: 3 días después del fallo
Reintento 2: 5 días después del fallo
Reintento 3: 7 días después del fallo
Final:       Marcar suscripción como impaga después del último reintento
```

**Eventos de webhook a manejar:**
- `invoice.payment_failed` — activar dunning
- `invoice.paid` — cancelar dunning, restaurar acceso
- `customer.subscription.updated` — cambios de estado
- `customer.subscription.deleted` — cancelación definitiva

### Chargebee

**Dunning integrado:**
1. Configuración → Configurar Chargebee → Configuración de reintentos
2. Configurar intentos de reintento e intervalos
3. Configuración → Configurar Chargebee → Notificaciones por correo → Dunning

**Opciones de dunning:**
- Reintentos automáticos con calendario configurable
- Correos de dunning integrados (plantillas personalizables)
- Configuración del período de gracia por plan

### Paddle

**Dunning gestionado:**
- Paddle maneja los reintentos y el dunning automáticamente
- Personalización limitada (Paddle gestiona la relación)
- Webhook: `subscription.payment_failed`, `subscription.cancelled`
- Ideal para un enfoque sin intervención manual

### Recurly

**Revenue Recovery:**
1. Configuración → Gestión de Dunning
2. Establecer el calendario de reintentos por plan
3. Configurar el período de gracia y la acción final (pausar vs. cancelar)

**Funciones avanzadas:**
- Optimización de reintentos con machine learning
- Calendarios de dunning por plan
- Account Updater integrado

---

## Dunning en la App

No depender solo del correo. Mostrar los fallos de pago en la app:

### Patrón de Banner
```
┌──────────────────────────────────────────────────────┐
│ ⚠ Tu pago de $29 falló. Actualiza tu tarjeta para    │
│ evitar perder el acceso. [Actualizar Pago →] [Cerrar] │
└──────────────────────────────────────────────────────┘
```

**Reglas:**
- Mostrar en cada carga de página durante el período de dunning
- Permitir cerrar (pero mostrar de nuevo en la siguiente sesión)
- Enlace directo a la actualización del pago (el menor número de clics posible)
- No bloquear el producto — dejar que sigan usándolo

### Patrón de Modal (para la última advertencia)
```
┌─────────────────────────────────────┐
│                                     │
│  Tu cuenta será pausada             │
│  el [fecha]                         │
│                                     │
│  Actualiza tu método de pago para   │
│  mantener el acceso a tus [X]       │
│  proyectos y [Y] miembros del       │
│  equipo.                            │
│                                     │
│  [Actualizar Método de Pago]        │
│  [Recordarme Después]               │
│                                     │
└─────────────────────────────────────┘
```

---

## Medir el Rendimiento del Dunning

### Métricas Clave

| Métrica | Cómo Calcular | Objetivo |
|---------|---------------|---------|
| Tasa de recuperación | Pagos recuperados / Total de fallos | 50-60% |
| Tasa de recuperación por tipo de rechazo | Recuperados / Fallidos por tipo | Suave: 70%+, Duro: 40%+ |
| Tiempo hasta la recuperación | Días desde el fallo hasta el pago exitoso | <5 días |
| Tasa de prevención pre-dunning | Fallos prevenidos / Fallos esperados | 20-30% |
| Tasa de apertura de correos de dunning | Aperturas / Enviados por correo | 60%+ |
| Tasa de clic de correos de dunning | Clics / Aperturas por correo | 30%+ |
| Ingresos recuperados (mensual) | Suma de montos de pagos recuperados | Seguir tendencia |
| Ingresos perdidos por churn involuntario | Suma de fallos no recuperados | Seguir tendencia |

### Benchmarking

**Por etapa de la empresa:**

| Etapa | Churn Involuntario Típico | Objetivo Tras la Optimización |
|-------|--------------------------|-------------------------------|
| Temprana (< $1M ARR) | 3-5% del MRR/mes | 1-2% |
| Crecimiento ($1-10M ARR) | 2-4% del MRR/mes | 0.5-1.5% |
| Escala ($10M+ ARR) | 1-3% del MRR/mes | 0.3-0.8% |

### Cálculo del ROI

```
MRR de pagos fallidos mensual:        $10,000
Tasa de recuperación actual:           30% ($3,000 recuperados)
Tasa de recuperación objetivo:         60% ($6,000 recuperados)
Mejora mensual:                        $3,000/mes
Mejora anual:                          $36,000/año
Costo de la optimización de dunning:   ~$200-500/mes (herramientas)
ROI:                                   6-15x
```
