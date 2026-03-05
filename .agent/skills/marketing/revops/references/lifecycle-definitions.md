# Definiciones de Etapa del Ciclo de Vida

Plantillas completas para las etapas del ciclo de vida de leads, criterios de MQL por tipo de negocio, SLAs y flujos de trabajo de rechazo/reciclaje.

## Plantillas de Etapa

### Suscriptor

**Criterios de entrada:**
- Se registró en el blog, newsletter o actualizaciones de contenido
- No se requiere información de la empresa

**Criterios de salida:**
- Proporciona información de la empresa a través de formulario o enriquecimiento
- Visita 3+ páginas en una sesión
- Descarga contenido cerrado

**Propietario:** Marketing (automatizado)

**Acciones en la entrada:**
- Agregar al nurture de newsletter
- Comenzar a rastrear la puntuación de engagement

---

### Lead

**Criterios de entrada:**
- Contacto identificado con nombre + email + empresa
- Puede provenir de relleno de formulario, enriquecimiento o importación

**Criterios de salida:**
- Alcanza el umbral de MQL (ajuste + engagement)
- Calificado manualmente por marketing/SDR

**Propietario:** Marketing

**Acciones en la entrada:**
- Enriquecer datos del contacto (tamaño de empresa, industria, rol)
- Comenzar puntuación
- Agregar a la secuencia de nurture relevante

---

### MQL (Lead Calificado por Marketing)

**Criterios de entrada:**
- Cumple el umbral de puntuación de ajuste Y el umbral de puntuación de engagement
- O activa una acción de alta intención (solicitud de demo, página de precios + relleno de formulario)

**Criterios de salida:**
- Ventas acepta (se convierte en SQL)
- Ventas rechaza (reciclado al nurture con código de razón)
- Sin respuesta dentro del SLA (escalado al gerente)

**Propietario:** Marketing → Ventas (entrega)

**Acciones en la entrada:**
- Alerta instantánea al representante de ventas asignado
- Crear tarea de seguimiento con SLA de 4 horas
- Pausar secuencias de nurture de marketing
- Registrar toda la actividad reciente para el contexto de ventas

---

### SQL (Lead Calificado por Ventas)

**Criterios de entrada:**
- El representante de ventas ha tenido una conversación de calificación
- Confirmado: presupuesto, autoridad, necesidad o cronograma (al menos 2 de 4)

**Criterios de salida:**
- Oportunidad creada con valor proyectado
- Descalificado (reciclado con código de razón)

**Propietario:** Ventas (SDR o AE)

**Acciones en la entrada:**
- Actualizar etapa del ciclo de vida en CRM
- Notificar al AE si el SDR calificó
- Comenzar secuencia de ventas si aún no está en conversación

---

### Oportunidad

**Criterios de entrada:**
- Oportunidad formal creada en CRM
- Valor del acuerdo, fecha de cierre y etapa asignados

**Criterios de salida:**
- Ganado-cerrado o perdido-cerrado

**Propietario:** Ventas (AE)

**Acciones en la entrada:**
- Agregar a los reportes del pipeline
- Crear tareas del acuerdo (propuesta, demo, etc.)
- Notificar a SC si el acuerdo es probable que se cierre

---

### Cliente

**Criterios de entrada:**
- Acuerdo ganado-cerrado
- Contrato firmado y términos de pago establecidos

**Criterios de salida:**
- Cancela, se expande o renueva

**Propietario:** Éxito del Cliente / Gestión de Cuentas

**Acciones en la entrada:**
- Activar secuencia de onboarding
- Asignar gerente de SC
- Programar llamada de inicio
- Eliminar de todas las secuencias de ventas

---

### Evangelista

**Criterios de entrada:**
- Puntuación NPS 9-10, o comportamiento de referido activo
- Aceptó el caso de estudio, testimonio o programa de referidos

**Criterios de salida:**
- Participación continua en el programa

**Propietario:** Éxito del Cliente + Marketing

**Acciones en la entrada:**
- Agregar al programa de defensa
- Solicitar caso de estudio o testimonio
- Invitar al programa de referidos
- Presentar en campañas de marketing (con permiso)

---

## Plantillas de Criterios de MQL por Tipo de Negocio

### PLG (Crecimiento Impulsado por el Producto)

**Puntuación de ajuste (40% de peso):**

| Atributo | Puntos |
|-----------|--------|
| Tamaño de empresa 10-500 | +15 |
| Tamaño de empresa 500-5000 | +20 |
| Industria objetivo | +10 |
| Rol de tomador de decisiones | +15 |
| Usa herramienta complementaria | +10 |

**Puntuación de engagement (60% de peso) — ponderar el uso del producto con más peso:**

| Señal | Puntos |
|--------|--------|
| Creó cuenta gratuita | +15 |
| Completó el onboarding | +20 |
| Usó la función central 3+ veces | +25 |
| Invitó a un miembro del equipo | +20 |
| Alcanzó el límite de uso | +15 |
| Visitó la página de precios | +10 |

**Umbral de MQL:** 65 puntos

---

### Ventas-Led (Enterprise)

**Puntuación de ajuste (60% de peso) — ponderar el ajuste fuertemente:**

| Atributo | Puntos |
|-----------|--------|
| Tamaño de empresa 500+ | +20 |
| Industria objetivo | +15 |
| Título VP+ | +20 |
| Autoridad de presupuesto confirmada | +15 |
| Usa producto de la competencia | +10 |

**Puntuación de engagement (40% de peso):**

| Señal | Puntos |
|--------|--------|
| Solicitó demo | +25 |
| Asistió al webinar | +10 |
| Descargó whitepaper | +10 |
| Visitó la página de precios 2+ veces | +15 |
| Se involucró con el email de ventas | +10 |

**Umbral de MQL:** 70 puntos

---

### Mercado Medio (Equilibrado)

**Puntuación de ajuste (50% de peso):**

| Atributo | Puntos |
|-----------|--------|
| Tamaño de empresa 50-1000 | +15 |
| Industria objetivo | +10 |
| Título Gerente+ | +15 |
| Geografía objetivo | +10 |

**Puntuación de engagement (50% de peso):**

| Señal | Puntos |
|--------|--------|
| Solicitud de demo | +25 |
| Registro de prueba gratis | +20 |
| Visita a la página de precios | +10 |
| Descarga de contenido (2+) | +10 |
| Clic en email (3+) | +10 |
| Asistencia a webinar | +10 |

**Umbral de MQL:** 60 puntos

---

## Plantillas de SLA

### SLA de MQL a SQL

| Métrica | Objetivo | Escalación |
|--------|--------|------------|
| Primer intento de contacto | Dentro de 4 horas hábiles | Alertar al gerente de ventas a las 4 horas |
| Decisión de calificación | Dentro de 48 horas | Auto-escalar a las 48 horas |
| Reunión programada (si calificado) | Dentro de 5 días hábiles | Marca en revisión semanal del pipeline |

### SLA de SQL a Oportunidad

| Métrica | Objetivo | Escalación |
|--------|--------|------------|
| Llamada de descubrimiento completada | Dentro de 3 días hábiles de SQL | Alertar al gerente del AE |
| Oportunidad creada | Dentro de 5 días hábiles de SQL | Marca en revisión del pipeline |

### SLA de Oportunidad a Cierre

| Métrica | Objetivo | Escalación |
|--------|--------|------------|
| Propuesta entregada | Dentro de 5 días hábiles de la demo | Alerta al gerente del AE |
| Acuerdo estancado en etapa | 2x días promedio para esa etapa | Marca en revisión del pipeline |
| Fecha de cierre postergada 2+ veces | Inmediata | Revisión de pronóstico requerida |

---

## Rechazo y Reciclaje de Leads

### Códigos de Razón de Rechazo

| Código | Razón | Acción de Reciclaje |
|------|--------|----------------|
| **AJUSTE-01** | Empresa demasiado pequeña | Nurture; re-puntuar si la empresa crece |
| **AJUSTE-02** | Industria incorrecta | Archivar; no reciclar |
| **AJUSTE-03** | Rol incorrecto / sin autoridad | Nurture; monitorear cambios organizacionales |
| **ENG-01** | Sin respuesta después de 3 intentos | Reciclar al nurture en 90 días |
| **ENG-02** | Interesado pero mala temporada | Reciclar al nurture; re-engañar en 60 días |
| **CUAL-01** | Sin presupuesto | Reciclar al nurture en 90 días |
| **CUAL-02** | Usando un competidor, comprometido | Reciclar; activar antes de la renovación del contrato |
| **CUAL-03** | No es un proyecto real | Archivar; no reciclar |

### Flujo de Trabajo de Reciclaje

1. Ventas rechaza MQL con código de razón
2. CRM actualiza la etapa del ciclo de vida a "Reciclado"
3. El lead entra en la secuencia de nurture de reciclaje (diferente del nurture original)
4. La puntuación de engagement se reinicia al baseline (mantener puntuación de ajuste)
5. Si el lead se re-engancha y cruza el umbral de MQL, re-enrutar a ventas con la marca "MQL Reciclado"
6. Rastrear la tasa de conversión de MQL reciclado por separado

### Secuencia de Nurture de Reciclaje

- **Frecuencia:** Quincenal o mensual (menor frecuencia que el nurture inicial)
- **Contenido:** Insights de la industria, casos de estudio, actualizaciones del producto
- **Duración:** 6 meses, luego archivar si no hay engagement
- **Disparador de re-MQL:** Acción de alta intención (solicitud de demo, revisita a la página de precios)
