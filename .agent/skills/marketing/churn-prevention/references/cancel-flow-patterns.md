# Patrones de Flujo de Cancelación

Patrones detallados de flujo de cancelación por tipo de negocio, proveedor de facturación e industria.

---

## Flujo de Cancelación por Tipo de Negocio

### B2C / SaaS de Autoservicio

Alto volumen, poco contacto. El flujo debe funcionar sin intervención humana.

**Estructura del flujo:**
```
Botón de cancelar → Encuesta de salida (1 pregunta) → Oferta dinámica → Confirmar → Post-cancelación
```

**Características:**
- Completamente automatizado, sin intervención humana
- Rápido — máximo 2-3 pantallas
- Una oferta + un respaldo, no un menú de opciones
- Optimizado para móvil (cancelaciones significativas en móvil)
- "Continuar cancelando" claro en cada paso

**Tasa de retención típica:** 20-30%

**Flujo de ejemplo para una app de productividad a $29/mes:**
1. "¿Cuál es la razón principal?" → 6 opciones
2. Seleccionó "Demasiado caro" → "Obtén un 25% de descuento por 3 meses (ahorra $21.75)"
3. Rechazó → "O cambia a nuestro plan Starter por $12/mes"
4. Rechazó → "Lamentamos verte partir. Tu acceso continúa hasta el [fecha]."

---

### B2B / Planes de Equipo

Menor volumen, mayor importancia. El contacto personal vale el costo.

**Estructura del flujo:**
```
Botón de cancelar → Encuesta de salida → Oferta (o enrutar a CS) → Confirmar → Post-cancelación
```

**Características:**
- Enrutar cuentas superiores al umbral de MRR a customer success
- Mostrar el impacto en el equipo ("Tus 8 miembros del equipo perderán el acceso")
- Ofrecer llamada admin-a-admin para cuentas enterprise
- Mayor consideración — permitir "programar una llamada" como opción de retención
- Requerir rol de admin/propietario para cancelar (no cualquier miembro del equipo)

**Tasa de retención típica:** 30-45% (mayor por el toque personal)

**Enrutamiento basado en MRR:**

| MRR de la Cuenta | Flujo de Cancelación |
|-------------|-------------|
| <$100/mes | Flujo automatizado con ofertas |
| $100-$500/mes | Automatizado + marcar para seguimiento de CS |
| $500-$2,000/mes | Enrutar a CS antes de que se complete la cancelación |
| $2,000+/mes | Bloquear cancelación de autoservicio, requerir llamada a CS |

---

### Freemium / Gratis a Pago

Usuarios que cancelan el pago para volver al nivel gratuito. Psicología diferente — no se van, están degradando.

**Estructura del flujo:**
```
Botón de cancelar → Prompt "¿Cambiar a Gratis?" → Encuesta de salida (si aún cancelan) → Oferta → Confirmar
```

**Características:**
- Liderar con el nivel gratuito como primera opción (no una oferta de retención)
- Mostrar qué se conserva en gratis vs. qué se pierde
- La "retención" es mantenerlos en gratis, no perderlos completamente
- Rastrear usuarios del nivel gratuito para futuras campañas de re-actualización

---

## Flujo de Cancelación por Intervalo de Facturación

### Suscriptores Mensuales

- Más sensibles al precio, compromiso más corto
- Las ofertas de descuento funcionan bien (20-30% por 2-3 meses)
- La pausa es efectiva (1-2 meses)
- Sugerir plan anual con descuento como alternativa

**Prioridad de oferta:**
1. Descuento (si razón = precio)
2. Pausa (si razón = no está usando / temporal)
3. Cambio a plan anual (si está enganchado pero sensible al precio)

### Suscriptores Anuales

- Mayor compromiso, generalmente cancelando por razones más fuertes
- Las expectativas de reembolso prorrateado importan
- Ventana de retención más larga (ya pagaron)
- El contacto personal está más justificado (mayor LTV en juego)

**Prioridad de oferta:**
1. Pausar el resto del período (si es temporal)
2. Ajuste de plan + crédito para la próxima renovación
3. Contacto personal de CS
4. Reembolso parcial + degradación (mejor que reembolso completo + cancelación)

**Manejo de reembolsos:**
- Ofrecer reembolso prorrateado si queda tiempo significativo
- "Pausar hasta la renovación" si quedan menos de 3 meses
- Ser generoso — las malas experiencias de reembolso crean detractores vocales

---

## Patrones de Oferta de Retención

### La Escalera de Descuentos

No lideres con tu mayor descuento. Escala:

```
Clic en cancelar → 15% de descuento → Aún cancelando → 25% de descuento → Aún cancelando → Déjalos ir
```

**Reglas:**
- Máximo 2 ofertas de descuento por sesión de cancelación
- Nunca exceder el 30% (más alto entrena el comportamiento de cancelar para descuento)
- Descuentos con límite de tiempo (2-3 meses, luego se reanuda el precio completo)
- Rastrear los que aceptan descuentos — si cancelan de nuevo al precio completo, no volver a ofrecer

### El Plan de Pausa

La pausa es a menudo mejor que un descuento porque no devalúa tu producto.

**Implementación:**

| Configuración | Recomendación |
|---------|---------------|
| Opciones de duración de pausa | 1 mes, 2 meses, 3 meses |
| Selección predeterminada | 1 mes (el más corto) |
| Pausa máxima | 3 meses (las pausas más largas rara vez regresan) |
| Durante la pausa | Conservar datos, eliminar acceso |
| Reactivación | Auto-reactivar con email 7 días antes |
| Pausas repetidas | Permitir 1 pausa por período de 12 meses |

**Secuencia de reactivación de pausa:**
- Día -7: "Tu pausa termina en 7 días. Hemos estado ocupados — aquí está lo nuevo."
- Día -1: "¡Bienvenido/a de vuelta mañana! Aquí está lo que te espera."
- Día 0: "¡Has vuelto! Aquí hay un recorrido rápido de las novedades."

### El Camino de Degradación

Para productos con múltiples planes, la degradación es la retención más fuerte:

```
┌─────────────────────────────────────────┐
│  Antes de irte, ¿qué tal ajustar        │
│  tu plan?                               │
│                                         │
│  Actual: Pro ($49/mes)                  │
│                                         │
│  ┌─────────────────────────────────┐    │
│  │ Cambiar a Starter ($19/mes)     │    │
│  │                                 │    │
│  │ ✓ Conservar: Proyectos,         │    │
│  │   integraciones                 │    │
│  │ ✗ Perder: Análisis avanzados,   │    │
│  │         funciones de equipo     │    │
│  │                                 │    │
│  │ [Cambiar a Starter]             │    │
│  └─────────────────────────────────┘    │
│                                         │
│  [No gracias, continuar cancelando]     │
└─────────────────────────────────────────┘
```

**Mejores prácticas de degradación:**
- Mostrar exactamente qué conservan y qué pierden
- Usar marcas de verificación y X para facilitar el escaneo
- Conservar sus datos incluso en el plan inferior
- Si se degradan, no mostrar avisos de actualización durante al menos 30 días

### El Manejador de Cambio a Competidor

Cuando la razón de cancelación es "cambiar a un competidor":

1. **Preguntar a qué competidor** (opcional, no forzarlo)
2. **Mostrar una comparación** si tienes una (ver habilidad competitor-alternatives)
3. **Ofrecer un crédito de migración** ("Igualaremos su precio por 3 meses")
4. **Solicitar una llamada de feedback** ("15 minutos para entender lo que nos falta")

Estos datos son oro para los equipos de producto y marketing.

---

## Experiencia Post-Cancelación

Lo que sucede después de cancelar importa para:
- Potencial de win-back
- Boca a boca
- Sentimiento de reseñas

### Página de Confirmación

```
Tu suscripción ha sido cancelada.

Qué sucede a continuación:
• Tu acceso continúa hasta el [fecha de fin del período de facturación]
• Tus datos se conservarán durante 90 días
• Puedes reactivar en cualquier momento desde la configuración de tu cuenta

[Reactivar Mi Cuenta]

Nos encantaría tenerte de vuelta. Seguiremos mejorando con base en 
el feedback de clientes como tú.
```

### Secuencia Post-Cancelación

| Momento | Acción |
|--------|--------|
| Inmediatamente | Email de confirmación con fecha de fin de acceso |
| Día 1 | (Nada — no seas desesperado) |
| Día 7 | Encuesta NPS/satisfacción sobre la experiencia general |
| Día 30 | Email "novedades" con mejoras recientes |
| Día 60 | Abordar su razón específica de cancelación si fue resuelta |
| Día 90 | Win-back final con oferta especial |

**Para secuencias detalladas de email de win-back**: Ver la habilidad email-sequence.

---

## Reglas de Segmentación

Los flujos de cancelación más efectivos usan la segmentación para mostrar diferentes ofertas a diferentes clientes.

### Dimensiones de Segmentación

| Dimensión | Por Qué Importa |
|-----------|-----------------|
| Plan / MRR | Los clientes de mayor valor reciben contacto personal |
| Antigüedad | Los clientes a largo plazo reciben ofertas más generosas |
| Nivel de uso | Los clientes de alto uso reciben mensajes diferentes a los inactivos |
| Intervalo de facturación | Mensual vs. anual necesitan enfoques diferentes |
| Retenciones anteriores | No volver a ofrecer el mismo descuento a un cancelador repetido |
| Razón de cancelación | Impulsa qué oferta mostrar (mapeo central) |

### Flujos Específicos por Segmento

**Cliente nuevo (< 30 días):**
- No se han activado. La retención es el onboarding, no los descuentos.
- Oferta: Llamada de onboarding gratuita, ayuda de configuración, prueba extendida
- Preguntar: "¿Qué esperabas lograr?" (aprender qué falta)

**Cliente enganchado cancelando por precio:**
- Aman el producto pero no pueden justificar el costo.
- Oferta: Descuento, cambio a plan anual, degradación
- Alto potencial de retención

**Cliente inactivo (sin inicio de sesión 30+ días):**
- Se olvidaron de ti. Un descuento no los traerá de vuelta.
- Oferta: Pausar suscripción, conversación "¿qué cambió?"
- Bajo potencial de retención — enfocarse en aprender por qué

**Usuario de poder cambiando a competidor:**
- Están eligiendo activamente otra cosa.
- Oferta: Igualación competitiva, llamada de feedback, vista previa del roadmap
- Potencial de retención medio — depende de la razón

---

## Lista de Verificación de Implementación

### Fase 1: Fundación (Semana 1)
- [ ] Agregar flujo de cancelación (encuesta + 1 oferta + confirmación)
- [ ] Configurar encuesta de salida con 5-7 categorías de razón
- [ ] Mapear una oferta por razón (mapeo simple 1:1)
- [ ] Rastrear razones de cancelación y tasa de retención en análisis
- [ ] Activar emails pre-dunning de vencimiento de tarjeta

### Fase 2: Optimización (Semanas 2-4)
- [ ] Agregar ofertas de respaldo (primaria + secundaria por razón)
- [ ] Implementar opción de pausa de suscripción
- [ ] Configurar secuencia de email de dunning (4 emails en 10 días)
- [ ] Activar reintentos inteligentes (Stripe Smart Retries o equivalente)
- [ ] Agregar enrutamiento basado en MRR para cuentas de alto valor

### Fase 3: Avanzado (Mes 2+)
- [ ] Construir puntuación de salud desde señales de uso
- [ ] Configurar disparadores de intervención proactiva
- [ ] Probar A/B montos de descuento y tipos de oferta
- [ ] Segmentar flujos por plan, antigüedad y uso
- [ ] Secuencia de win-back post-cancelación (coordinar con habilidad email-sequence)
- [ ] Análisis de cohorte: churn por canal, plan, antigüedad

---

## Notas de Cumplimiento

### Regla de Clic para Cancelar de la FTC (EE.UU.)
- La cancelación debe ser tan fácil como el registro
- No se puede requerir una llamada telefónica para cancelar si el registro fue en línea
- No se pueden agregar pasos excesivos para desalentar la cancelación
- Las ofertas de retención están permitidas pero "continuar cancelando" debe ser claro

### GDPR / Retención de Datos (UE)
- Informar a los usuarios sobre el período de retención de datos post-cancelación
- Ofrecer exportación de datos antes de la eliminación de la cuenta
- Cumplir las solicitudes de eliminación en 30 días
- No usar datos post-cancelación para marketing sin consentimiento

### Mejores Prácticas Generales
- Siempre mostrar un camino claro para completar la cancelación
- Nunca ocultar el botón de cancelar (patrón oscuro)
- Procesar la cancelación incluso si el flujo de retención tiene errores
- Confirmar la cancelación con recibo por email
