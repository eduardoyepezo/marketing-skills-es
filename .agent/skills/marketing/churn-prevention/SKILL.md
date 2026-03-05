---
name: churn-prevention
description: "Cuando el usuario quiere reducir la cancelación, construir flujos de cancelación, configurar ofertas de retención, recuperar pagos fallidos o implementar estrategias de retención. También usar cuando el usuario menciona 'churn,' 'cancelaciones,' 'flujo de cancelación,' 'oferta de retención,' 'dunning,' 'recuperación de pagos fallidos,' 'win-back,' 'retención,' 'encuesta de salida,' 'pausar suscripción,' 'churn involuntario,' 'los usuarios siguen cancelando,' 'tasa de cancelación muy alta,' 'cómo retener usuarios,' o 'los clientes se están yendo.' Usar cuando alguien está perdiendo suscriptores o quiere construir sistemas para prevenirlo. Para secuencias de correo de reconquista post-cancelación, ver email-sequence. Para pantallas de actualización in-app, ver paywall-upgrade-cro."
metadata:
  version: 1.1.0
---

# Prevención de Cancelación (Churn Prevention)

Eres experto en retención de SaaS y prevención de cancelaciones. Tu objetivo es ayudar a reducir tanto el churn voluntario (clientes que eligen cancelar) como el involuntario (pagos fallidos) mediante flujos de cancelación bien diseñados, ofertas de retención dinámicas, retención proactiva y estrategias de dunning.

## Antes de Comenzar

**Revisar el contexto de marketing primero:**
Si existe `.agents/product-marketing-context.md` (o `.claude/product-marketing-context.md` en configuraciones antiguas), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información que no esté cubierta o que sea específica para esta tarea.

Recopila este contexto (pregunta si no se proporciona):

### 1. Situación Actual de Cancelaciones
- ¿Cuál es tu tasa de churn mensual? (Voluntario vs. involuntario si se conoce)
- ¿Cuántos suscriptores activos tienes?
- ¿Cuál es el MRR promedio por cliente?
- ¿Tienes un flujo de cancelación hoy, o la cancelación ocurre de inmediato?

### 2. Facturación y Plataforma
- ¿Qué proveedor de facturación? (Stripe, Chargebee, Paddle, Recurly, Braintree)
- ¿Facturación mensual, anual, o ambas?
- ¿Admites pausar planes o hacer downgrade?
- ¿Tienes alguna herramienta de retención existente? (Churnkey, ProsperStack, Raaft)

### 3. Datos de Producto y Uso
- ¿Rastreos el uso de funciones por usuario?
- ¿Puedes identificar caídas de engagement?
- ¿Tienes datos de razón de cancelación de churns anteriores?
- ¿Cuál es tu métrica de activación? (¿Qué hacen los usuarios retenidos que los que cancelaron no hicieron?)

### 4. Restricciones
- ¿B2B o B2C? (Afecta el diseño del flujo)
- ¿Se requiere cancelación de autoservicio? (Algunas regulaciones exigen cancelación fácil)
- ¿Tono de marca para el offboarding? (Empático, directo, amigable)

---

## Cómo Funciona Esta Habilidad

El churn tiene dos tipos que requieren estrategias diferentes:

| Tipo | Causa | Solución |
|------|-------|----------|
| **Voluntario** | El cliente elige cancelar | Flujos de cancelación, ofertas de retención, encuestas de salida |
| **Involuntario** | El pago falla | Correos de dunning, reintentos inteligentes, actualizadores de tarjeta |

El churn voluntario es típicamente el 50-70% del churn total. El involuntario es el 30-50% pero suele ser más fácil de solucionar.

Esta habilidad admite tres modos:

1. **Construir un flujo de cancelación** — Diseñar desde cero con encuesta, ofertas de retención y confirmación
2. **Optimizar un flujo existente** — Analizar datos de cancelación y mejorar las tasas de retención
3. **Configurar dunning** — Recuperación de pagos fallidos con reintentos y secuencias de correo

---

## Diseño del Flujo de Cancelación

### La Estructura del Flujo de Cancelación

Cada flujo de cancelación sigue esta secuencia:

```
Disparador → Encuesta → Oferta Dinámica → Confirmación → Post-Cancelación
```

**Paso 1: Disparador**
El cliente hace clic en "Cancelar suscripción" en la configuración de la cuenta.

**Paso 2: Encuesta de Salida**
Preguntar por qué están cancelando. Esto determina qué oferta de retención mostrar.

**Paso 3: Oferta Dinámica de Retención**
Presentar una oferta dirigida según su razón (descuento, pausa, downgrade, etc.)

**Paso 4: Confirmación**
Si aún quieren cancelar, confirmar claramente con mensajería sobre el fin del período de facturación.

**Paso 5: Post-Cancelación**
Establecer expectativas, ofrecer una ruta fácil de reactivación, activar secuencia de win-back.

### Diseño de la Encuesta de Salida

La encuesta de salida es la base. Buenas categorías de razones:

| Razón | Qué te dice |
|-------|-------------|
| Muy caro | Sensibilidad al precio, puede responder a descuento o downgrade |
| No lo uso lo suficiente | Bajo engagement, puede responder a pausa o ayuda de onboarding |
| Falta una función | Brecha de producto, mostrar hoja de ruta o solución alternativa |
| Cambiando a un competidor | Presión competitiva, entender qué ofrecen |
| Problemas técnicos / bugs | Calidad del producto, escalar a soporte |
| Necesidad temporal / estacional | Patrón de uso, ofrecer pausa |
| Empresa cerrada / cambió | Inevitable, aprender y despedirse con gracia |
| Otro | Categoría general, incluir campo de texto libre |

**Mejores prácticas para la encuesta:**
- 1 pregunta, selección única con texto libre opcional
- Máximo 5-8 opciones de razón (evitar fatiga de decisión)
- Poner las razones más comunes primero (revisar datos trimestralmente)
- No hacer que parezca un sentimiento de culpa
- El encuadre "ayúdanos a mejorar" funciona mejor que "¿por qué te vas?"

### Ofertas Dinámicas de Retención

La clave: **hacer coincidir la oferta con la razón.** Un descuento no salvará a alguien que no está usando el producto. Una hoja de ruta de funciones no salvará a alguien que no puede pagarlo.

**Mapeo de oferta según razón:**

| Razón de Cancelación | Oferta Principal | Oferta de Respaldo |
|----------------------|-----------------|-------------------|
| Muy caro | Descuento (20-30% por 2-3 meses) | Downgrade a plan inferior |
| No lo uso lo suficiente | Pausa (1-3 meses) | Sesión de onboarding gratuita |
| Falta una función | Vista previa del roadmap + plazo | Guía de alternativa |
| Cambiando a competidor | Comparación competitiva + descuento | Sesión de retroalimentación |
| Problemas técnicos | Escalar a soporte de inmediato | Crédito + solución prioritaria |
| Temporal / estacional | Pausar suscripción | Downgrade temporal |
| Empresa cerrada | Omitir oferta (respetar la situación) | — |

### Tipos de Oferta de Retención

**Descuento**
- 20-30% de descuento por 2-3 meses es el punto óptimo
- Evitar descuentos del 50%+ (entrena a los clientes a cancelar para obtener ofertas)
- Limitar la oferta en el tiempo ("Esta oferta vence cuando salgas de esta página")
- Mostrar el monto en dinero ahorrado, no solo el porcentaje

**Pausar suscripción**
- Máximo 1-3 meses de pausa (las pausas más largas raramente reactivan)
- El 60-80% de los que pausan eventualmente regresan a activo
- Auto-reactivación con correo de aviso previo
- Mantener sus datos y configuraciones intactos

**Downgrade de plan**
- Ofrecer un nivel inferior en lugar de cancelación total
- Mostrar qué conservan vs. qué pierden
- Posicionar como "ajusta tu plan" no "baja de nivel"
- Ruta fácil de regreso cuando estén listos

**Desbloqueo de función / extensión**
- Desbloquear una función premium que no han probado
- Extender la prueba de un nivel superior
- Funciona mejor para razones de "no obtengo suficiente valor"

**Alcance personal**
- Para cuentas de alto valor (top 10-20% por MRR)
- Redirigir a éxito del cliente para una llamada
- Correo personal del fundador para empresas más pequeñas

### Patrones de UI del Flujo de Cancelación

```
┌─────────────────────────────────────┐
│  Lamentamos que quieras irte        │
│                                     │
│  ¿Cuál es la razón principal por    │
│  la que cancelas?                   │
│                                     │
│  ○ Es muy caro                      │
│  ○ No lo uso lo suficiente          │
│  ○ Falta una función que necesito   │
│  ○ Me cambio a otra herramienta     │
│  ○ Problemas técnicos               │
│  ○ Temporal / no lo necesito ahora  │
│  ○ Otro: [____________]             │
│                                     │
│  [Continuar]                        │
│  [No importa, mantener suscripción] │
└─────────────────────────────────────┘
         ↓ (selecciona "Es muy caro")
┌─────────────────────────────────────┐
│  ¿Qué tal si podemos ayudarte?      │
│                                     │
│  Nos gustaría que te quedaras. Aquí │
│  hay una oferta especial:           │
│                                     │
│  ┌───────────────────────────────┐  │
│  │  25% de descuento por 3 meses │  │
│  │  Ahorra $XX/mes               │  │
│  │                               │  │
│  │  [Aceptar Oferta]             │  │
│  └───────────────────────────────┘  │
│                                     │
│  O cambia a [Plan Básico] a         │
│  $X/mes →                           │
│                                     │
│  [No gracias, continuar cancelando] │
└─────────────────────────────────────┘
```

**Principios de UI:**
- Mantener visible la opción "continuar cancelando" (sin patrones oscuros)
- Una oferta principal + una de respaldo, no una pared de opciones
- Mostrar ahorros específicos en dinero, no porcentajes abstractos
- Usar el nombre del cliente y datos de cuenta cuando sea posible
- Compatible con móvil (muchas cancelaciones ocurren en móvil)

Para patrones detallados de flujo de cancelación por industria y proveedor de facturación, ver [references/cancel-flow-patterns.md](references/cancel-flow-patterns.md).

---

## Predicción de Churn y Retención Proactiva

La mejor retención ocurre antes de que el cliente haga clic en "Cancelar."

### Señales de Riesgo

Rastrear estos indicadores adelantados de churn:

| Señal | Nivel de Riesgo | Plazo |
|-------|----------------|-------|
| Frecuencia de login cae 50%+ | Alto | 2-4 semanas antes de cancelar |
| Uso de función clave se detiene | Alto | 1-3 semanas antes de cancelar |
| Tickets de soporte se disparan y luego paran | Alto | 1-2 semanas antes de cancelar |
| Tasas de apertura de correo declinan | Medio | 2-6 semanas antes de cancelar |
| Visitas a la página de facturación aumentan | Alto | Días antes de cancelar |
| Se eliminan asientos del equipo | Alto | 1-2 semanas antes de cancelar |
| Se inicia exportación de datos | Crítico | Días antes de cancelar |
| Puntuación NPS cae por debajo de 6 | Medio | 1-3 meses antes de cancelar |

### Modelo de Puntuación de Salud

Construir una puntuación de salud simple (0-100) con señales ponderadas:

```
Puntuación de Salud = (
  Puntuación de frecuencia de login  × 0.30 +
  Puntuación de uso de funciones     × 0.25 +
  Sentimiento de soporte             × 0.15 +
  Salud de facturación               × 0.15 +
  Puntuación de engagement           × 0.15
)
```

| Puntuación | Estado | Acción |
|-----------|--------|--------|
| 80-100 | Saludable | Oportunidades de upsell |
| 60-79 | Necesita atención | Check-in proactivo |
| 40-59 | En riesgo | Campaña de intervención |
| 0-39 | Crítico | Alcance personal |

### Intervenciones Proactivas

**Antes de que piensen en cancelar:**

| Disparador | Intervención |
|------------|-------------|
| Caída de uso >50% por 2 semanas | Correo "Notamos que no has usado [función]. ¿Necesitas ayuda?" |
| Acercándose al límite del plan | Empuje de actualización (no un muro) |
| Sin login por 14 días | Correo de re-engagement con actualizaciones recientes del producto |
| Detractor de NPS (0-6) | Seguimiento personal en 24 horas |
| Ticket de soporte sin resolver >48h | Escalada + actualización proactiva de estado |
| Renovación anual en 30 días | Correo de resumen de valor + confirmación de renovación |

---

## Churn Involuntario: Recuperación de Pagos

Los pagos fallidos causan el 30-50% de todo el churn pero son los más recuperables.

### El Stack de Dunning

```
Pre-dunning → Reintento inteligente → Correos de dunning → Período de gracia → Cancelación definitiva
```

### Pre-Dunning (Prevenir Fallos)

- **Alertas de vencimiento de tarjeta**: Correo 30, 15 y 7 días antes de que venza la tarjeta
- **Método de pago de respaldo**: Solicitar un segundo método de pago al registrarse
- **Servicios de actualización de tarjeta**: Programas de auto-actualización de Visa/Mastercard (reduce rechazos duros un 30-50%)
- **Notificación pre-cobro**: Correo 3-5 días antes del cargo para planes anuales

### Lógica de Reintento Inteligente

No todos los fallos son iguales. Estrategia de reintento por tipo de rechazo:

| Tipo de Rechazo | Ejemplos | Estrategia de Reintento |
|----------------|----------|------------------------|
| Rechazo suave (temporal) | Fondos insuficientes, tiempo de espera del procesador | Reintentar 3-5 veces en 7-10 días |
| Rechazo duro (permanente) | Tarjeta robada, cuenta cerrada | No reintentar — solicitar nueva tarjeta |
| Autenticación requerida | 3D Secure, SCA | Enviar al cliente a actualizar el pago |

**Mejores prácticas de tiempo de reintento:**
- Reintento 1: 24 horas después del fallo
- Reintento 2: 3 días después del fallo
- Reintento 3: 5 días después del fallo
- Reintento 4: 7 días después del fallo (con escalada de correo de dunning)
- Después de 4 reintentos: Cancelación definitiva con ruta de reactivación

**Consejo de reintento inteligente:** Reintentar el día del mes en que el pago originalmente tuvo éxito. Stripe Smart Retries maneja esto automáticamente.

### Secuencia de Correos de Dunning

| Correo | Momento | Tono | Contenido |
|--------|---------|------|-----------|
| 1 | Día 0 (fallo) | Alerta amigable | "Tu pago no se procesó. Actualiza tu tarjeta." |
| 2 | Día 3 | Recordatorio útil | "Recordatorio rápido — actualiza tu pago para mantener el acceso." |
| 3 | Día 7 | Urgencia | "Tu cuenta será pausada en 3 días. Actualiza ahora." |
| 4 | Día 10 | Última advertencia | "Última oportunidad para mantener tu cuenta activa." |

**Mejores prácticas de correos de dunning:**
- Enlace directo a la página de actualización de pago (sin login requerido si es posible)
- Mostrar qué perderán (sus datos, el acceso de su equipo)
- No culpar ("tu pago no fue procesado" no "fallaste en pagar")
- Incluir contacto de soporte para ayuda
- El texto plano funciona mejor que los correos diseñados para dunning

### Benchmarks de Recuperación

| Métrica | Bajo | Promedio | Bueno |
|---------|------|----------|-------|
| Recuperación de rechazo suave | <40% | 50-60% | 70%+ |
| Recuperación de rechazo duro | <10% | 20-30% | 40%+ |
| Recuperación general de pagos | <30% | 40-50% | 60%+ |
| Prevención pre-dunning | Ninguna | 10-15% | 20-30% |

Para el playbook completo de dunning con configuración específica por proveedor, ver [references/dunning-playbook.md](references/dunning-playbook.md).

---

## Métricas y Medición

### Métricas Clave de Churn

| Métrica | Fórmula | Objetivo |
|---------|---------|---------|
| Tasa de churn mensual | Clientes cancelados / Clientes a inicio del mes | <5% B2C, <2% B2B |
| Churn de ingresos (neto) | (MRR perdido - MRR de expansión) / MRR inicial | Negativo (expansión neta) |
| Tasa de retención en flujo de cancelación | Retenidos / Total de sesiones de cancelación | 25-35% |
| Tasa de aceptación de oferta | Ofertas aceptadas / Ofertas mostradas | 15-25% |
| Tasa de reactivación después de pausa | Reactivados / Total pausados | 60-80% |
| Tasa de recuperación de dunning | Recuperados / Total de pagos fallidos | 50-60% |
| Tiempo hasta cancelar | Días desde primera señal de churn hasta cancelar | Seguir tendencia |

---

## Errores Comunes

- **Sin flujo de cancelación en absoluto** — La cancelación instantánea deja dinero sobre la mesa. Incluso una encuesta simple + una oferta salva el 10-15%
- **Hacer que la cancelación sea difícil de encontrar** — Los botones de cancelación ocultos generan resentimiento y malas reseñas
- **La misma oferta para todas las razones** — Un descuento general no aborda "función faltante" o "no lo uso"
- **Descuentos demasiado profundos** — Los descuentos del 50%+ entrenan a los clientes a cancelar y regresar por ofertas
- **Ignorar el churn involuntario** — A menudo el 30-50% del churn total y el más fácil de arreglar
- **Sin correos de dunning** — Dejar que los fallos de pago cancelen cuentas en silencio
- **Copy de culpa** — "¿Seguro que quieres abandonarnos?" daña la confianza en la marca
- **No rastrear el LTV de la oferta de retención** — Un cliente "retenido" que cancela 30 días después no fue realmente retenido
- **Pausas demasiado largas** — Las pausas de más de 3 meses raramente reactivan. Establecer límites.
- **Sin ruta post-cancelación** — Hacer la reactivación fácil y activar correos de win-back

---

## Integraciones de Herramientas

Para implementación, ver el [registro de herramientas](../../tools/REGISTRY.md).

### Plataformas de Retención

| Herramienta | Mejor Para | Función Clave |
|-------------|------------|---------------|
| **Churnkey** | Flujo de cancelación completo + dunning | Ofertas adaptativas con IA, 34% de tasa de retención promedio |
| **ProsperStack** | Flujos de cancelación con analíticas | Motor de reglas avanzado, integración Stripe/Chargebee |
| **Raaft** | Constructor simple de flujo de cancelación | Fácil configuración, bueno para etapas tempranas |
| **Chargebee Retention** | Clientes de Chargebee | Integración nativa |

### Integraciones Relacionadas

| Herramienta | Para qué se usa |
|-------------|-----------------|
| `stripe` | Gestión de suscripciones, configuración de dunning, reintentos de pago |
| `customer-io` | Secuencias de correo de dunning, campañas de retención |
| `posthog` | Pruebas A/B del flujo de cancelación vía feature flags, analíticas de embudo |
| `mixpanel` / `ga4` | Seguimiento de uso, análisis de señales de churn |
| `segment` | Enrutamiento de eventos para puntuación de salud |

---

## Habilidades Relacionadas

- **email-sequence**: Para secuencias de correo de win-back después de cancelación
- **paywall-upgrade-cro**: Para momentos de actualización in-app y vencimiento de prueba
- **pricing-strategy**: Para estructura de planes y estrategia de descuento anual
- **onboarding-cro**: Para activación que previene el churn temprano
- **analytics-tracking**: Para configurar eventos de señal de churn
- **ab-test-setup**: Para probar variaciones del flujo de cancelación con rigor estadístico
