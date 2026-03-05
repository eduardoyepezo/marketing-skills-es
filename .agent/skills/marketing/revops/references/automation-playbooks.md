# Playbooks de Automatización

Recetas de flujo de trabajo específicas por plataforma para HubSpot, Salesforce, herramientas de programación y automatización entre herramientas.

## Recetas de Flujo de Trabajo de HubSpot

### 1. Alerta y Asignación de MQL

**Nombre:** Notificación de MQL y Creación de Tarea
**Disparador:** La propiedad de contacto "Etapa del Ciclo de Vida" cambia a "Lead Calificado por Marketing"
**Acciones:**
1. Rotar el propietario del contacto entre el equipo de ventas (round-robin)
2. Enviar email interno de notificación al propietario del contacto con contexto del lead
3. Crear tarea: "Hacer seguimiento con [Nombre del Contacto]" — con vencimiento en 4 horas
4. Enviar notificación de Slack al canal #alertas-ventas
5. Inscribir en secuencia "Seguimiento de MQL" (si se usan secuencias de HubSpot)
**Resultado:** Cada MQL se asigna instantáneamente con un SLA claro
**Notas:** Establecer criterios de inscripción para excluir leads ya asignados a un representante

---

### 2. Escalación de SLA de MQL

**Nombre:** Alerta de Incumplimiento de SLA de MQL
**Disparador:** Propiedad de contacto "Etapa del Ciclo de Vida" igual a "MQL" Y "Días desde el último contacto" es mayor que 0.5 (12 horas)
**Acciones:**
1. Enviar email interno al propietario del contacto: "Advertencia de SLA: [Nombre del Contacto] no ha sido contactado"
2. Si aún sin actividad después de 24 horas → enviar alerta al gerente de ventas
3. Si aún sin actividad después de 48 horas → reasignar el propietario del contacto mediante rotación
4. Crear tarea para el nuevo propietario: "Urgente: Contactar a [Nombre del Contacto] — reasignado por incumplimiento de SLA"
**Resultado:** Ningún MQL queda sin trabajar por más de 48 horas
**Notas:** Excluir contactos donde el último tipo de actividad es "Llamada" o "Reunión" (ya comprometidos)

---

### 3. Actualización de Puntuación y Promoción de MQL

**Nombre:** Auto-MQL en Umbral de Puntuación
**Disparador:** Propiedad de contacto "Puntuación HubSpot" es mayor o igual a 65
**Acciones:**
1. Establecer etapa del ciclo de vida a "Lead Calificado por Marketing"
2. Establecer "Fecha de MQL" a la fecha actual
3. Suprimir de los flujos de trabajo de nurture de marketing
4. Activar flujo de trabajo de Alerta de MQL (receta #1)
**Resultado:** Los leads se promueven automáticamente a MQL cuando alcanzan el umbral de puntuación
**Notas:** Agregar lista de supresión para clientes existentes y competidores

---

### 4. Notificación de Reunión Reservada

**Nombre:** Alerta de Reunión Reservada al AE
**Disparador:** Se registra actividad de reunión para un contacto (a través de Calendly/reuniones de HubSpot)
**Acciones:**
1. Enviar email interno al propietario del contacto con detalles de la reunión
2. Actualizar propiedad del contacto "Última Reunión Reservada" a la fecha actual
3. Si la etapa del ciclo de vida es "Lead" → actualizar a "MQL"
4. Crear tarea: "Prepararse para la reunión con [Nombre del Contacto]" — con vencimiento 1 hora antes de la reunión
5. Enviar notificación de Slack al canal #reuniones
**Resultado:** Los AEs están preparados para cada reunión con contexto completo
**Notas:** Incluir visitas de páginas recientes y descargas de contenido en el email de notificación

---

### 5. Entrega de Ganado-Cerrado a SC

**Nombre:** Disparador de Onboarding del Cliente
**Disparador:** La etapa del acuerdo cambia a "Ganado-Cerrado"
**Acciones:**
1. Actualizar la etapa del ciclo de vida del contacto asociado a "Cliente"
2. Establecer la fecha "Cliente desde" a la fecha actual
3. Asignar el propietario del contacto al miembro del equipo de SC (basado en segmento/territorio)
4. Crear tarea para SC: "Programar llamada de inicio con [Nombre de la Empresa]" — con vencimiento en 2 días hábiles
5. Inscribir al contacto en la secuencia de email "Onboarding del Cliente"
6. Enviar notificación interna al gerente de SC
7. Eliminar de todas las secuencias de ventas
**Resultado:** Entrega fluida de ventas a éxito del cliente
**Notas:** Incluir notas del acuerdo, valor del contrato y partes interesadas clave en la notificación de SC

---

### 6. Alerta de Acuerdo Estancado

**Nombre:** Higiene del Pipeline — Detección de Acuerdo Estancado
**Disparador:** Propiedad del acuerdo "Días en la etapa actual" es mayor que [2x el promedio para esa etapa]
**Acciones:**
1. Enviar email interno al propietario del acuerdo: "Alerta de acuerdo estancado: [Nombre del Acuerdo] ha estado en [Etapa] por [X] días"
2. Crear tarea: "Actualizar o cerrar [Nombre del Acuerdo]" — con vencimiento en 3 días hábiles
3. Si no hay actualización después de 7 días → alertar al gerente de ventas
4. Agregar a la lista del dashboard "Acuerdos Estancados"
**Resultado:** El pipeline se mantiene limpio y el pronóstico se mantiene preciso
**Notas:** Personalizar umbrales por etapa (Descubrimiento: 14 días, Propuesta: 10 días, Negociación: 21 días)

---

### 7. Re-Entrada al Nurture de Lead Reciclado

**Nombre:** Reciclaje de MQL al Nurture
**Disparador:** La propiedad de contacto "Razón de Rechazo de Ventas" es conocida (cualquier valor)
**Acciones:**
1. Actualizar etapa del ciclo de vida a "Reciclado"
2. Restablecer puntuación de engagement al baseline (mantener puntuación de ajuste)
3. Inscribir en secuencia "Nurture de Lead Reciclado" (menor frecuencia)
4. Establecer "Fecha de Reciclaje" a la fecha actual
5. Establecer disparador de re-inscripción: si la Puntuación HubSpot vuelve a superar el umbral, re-activar el flujo de trabajo de MQL
**Resultado:** Los leads rechazados obtienen una segunda oportunidad sin atascar el pipeline
**Notas:** Rastrear la tasa de conversión de reciclado-a-MQL como una métrica separada

---

### 8. Resumen de Actividad de Lead

**Nombre:** Resumen Diario de Actividad de Leads
**Disparador:** Programado — diariamente a las 8:00 AM hora local
**Acciones:**
1. Filtrar contactos: etapa del ciclo de vida es "SQL" o "Oportunidad" Y tuvieron actividad en el sitio web en las últimas 24 horas
2. Enviar email de resumen a cada propietario de contacto con la actividad de sus leads
3. Incluir: páginas visitadas, contenido descargado, emails abiertos/clickeados
**Resultado:** Los representantes de ventas comienzan cada día sabiendo qué leads están activos
**Notas:** Solo incluir leads con actividad significativa (excluir visitas únicas a la página de inicio)

---

## Equivalentes de Flow de Salesforce

### 1. Alerta y Asignación de MQL (Flow de Salesforce)

**Tipo:** Flow Activado por Registro
**Objeto:** Lead
**Disparador:** El campo de Lead "Estado" cambia a "MQL"
**Pasos del flow:**
1. Obtener Registros: Consultar el objeto personalizado "Asignación de Rep" para el siguiente representante disponible
2. Actualizar Registros: Establecer el Propietario del Lead al representante asignado
3. Crear Registros: Crear Tarea — "Contactar MQL: {Lead.Name}" con fecha de vencimiento = AHORA + 4 horas
4. Acción: Enviar alerta de email al nuevo propietario del lead
5. Actualizar Registros: Actualizar la marca de tiempo de última asignación de "Asignación de Rep"
**Notas:** Usar un objeto personalizado "Asignación de Rep" para gestionar el estado de round-robin

### 2. Escalación de SLA (Flow de Salesforce)

**Tipo:** Flow Activado por Programación
**Programación:** Cada 4 horas durante horas hábiles
**Pasos del flow:**
1. Obtener Registros: Leads donde Estado = "MQL" Y FechaÚltimaActividad < HOY - 1
2. Decisión: ¿El lead tiene más de 48 horas sin actividad?
   - SÍ → Reasignar al siguiente representante, crear tarea urgente, alertar al gerente
   - NO → Enviar email de recordatorio al propietario actual
**Notas:** Combinar con Process Builder para alertas en tiempo real en la asignación inicial

### 3. Automatización de Etapa del Pipeline (Flow de Salesforce)

**Tipo:** Flow Activado por Registro
**Objeto:** Oportunidad
**Disparador:** Se actualiza el campo Etapa
**Pasos del flow:**
1. Decisión: ¿A qué etapa se cambió?
2. Para cada etapa:
   - **Descubrimiento:** Crear tarea "Completar cuestionario de descubrimiento"
   - **Demo:** Crear tarea "Preparar entorno de demo"
   - **Propuesta:** Crear tarea "Enviar propuesta" + alertar al equipo de acuerdos si ACV > $25K
   - **Ganado-Cerrado:** Activar entrega a SC (crear Caso, asignar propietario de SC, enviar email de bienvenida)
   - **Perdido-Cerrado:** Crear tarea "Registrar razón de pérdida" + agregar al informe de análisis de ganancia/pérdida

### 4. Detección de Acuerdo Estancado (Flow de Salesforce)

**Tipo:** Flow Activado por Programación
**Programación:** Diariamente a las 7:00 AM
**Pasos del flow:**
1. Obtener Registros: Oportunidades Abiertas donde Días_En_Etapa > Umbral_SLA_Etapa
2. Recorrer resultados:
   - Crear Tarea: "Actualizar acuerdo estancado: {Opportunity.Name}"
   - Enviar email al Propietario de la Oportunidad
   - Si Días_En_Etapa > 2x umbral → enviar email al Gerente del Propietario
3. Actualizar campo personalizado "Bandera de Estancado" = true para visibilidad en dashboard

---

## Patrones de Integración de Calendly / SavvyCal

### Programación de Reuniones Round-Robin

**Configuración de Calendly:**
1. Crear un tipo de evento de equipo con todos los representantes elegibles
2. Distribución: "Optimizar para distribución equitativa"
3. Disponibilidad: Cada representante gestiona su propio calendario
4. Tiempo de espera: 15 min antes y después de las reuniones
5. Aviso mínimo: 4 horas (evitar reservas de último momento)

**Integración de CRM:**
1. El webhook de Calendly se activa al reservar
2. Coincidir el email del invitado con el contacto del CRM
3. Si el contacto existe → asignar reunión al propietario del contacto (anular round-robin si es poseído)
4. Si es un contacto nuevo → crear lead, asignar mediante reglas de enrutamiento, registrar reunión
5. Establecer etapa del ciclo de vida a MQL (reunión = alta intención)

### Configuración de SavvyCal

**Ventajas sobre Calendly:**
- Programación basada en prioridad (preferir ciertos horarios)
- Superposición de calendarios (mostrar disponibilidad del equipo en una vista)
- Links de reserva personalizados por representante

**Patrón de integración:**
1. Crear link de programación de equipo con reglas de prioridad
2. Webhook al reservar → Zapier/Make → CRM
3. Coincidir o crear contacto, asignar propietario, crear tarea
4. Enviar confirmación con materiales de preparación de reunión

### Enrutamiento de Reuniones por Criterio

```
Formulario de reserva enviado
├─ ¿Tamaño de empresa > 500? (campo del formulario)
│  ├─ SÍ → Enrutar al calendario del AE enterprise
│  └─ NO ↓
├─ ¿Cliente existente? (búsqueda en CRM)
│  ├─ SÍ → Enrutar al calendario del propietario de la cuenta
│  └─ NO ↓
└─ Round-robin entre el equipo de SDR
```

### Flujo de Trabajo de No Se Presentó

**Disparador:** El tiempo de la reunión pasa + no se registran notas de reunión dentro de 30 minutos
**Acciones:**
1. Esperar 30 minutos después del tiempo de reunión programado
2. Verificar: ¿Se registró una llamada o reunión?
   - SÍ → Sin acción
   - NO → Enviar email "Lo sentimos, nos perdimos" al prospecto
3. Crear tarea: "Reprogramar con [Nombre del Contacto]" — con vencimiento el próximo día hábil
4. Si es la segunda ausencia → marcar el contacto y alertar al gerente

---

## Patrones de Zapier Entre Herramientas

### 1. Nuevo Lead → CRM + Slack + Tarea

**Disparador:** Nueva envío de formulario (Typeform, HubSpot, Webflow)
**Acciones:**
1. Crear/actualizar contacto en CRM
2. Enriquecer con Clearbit (si está disponible)
3. Publicar en Slack #nuevos-leads con datos enriquecidos
4. Crear tarea en herramienta de gestión de proyectos (Asana, Linear)

### 2. Reunión Reservada → CRM + Email de Preparación

**Disparador:** Nueva reserva de Calendly/SavvyCal
**Acciones:**
1. Encontrar o crear contacto en CRM
2. Actualizar etapa del ciclo de vida a MQL
3. Enviar email de preparación al representante asignado (incluir link de CRM, perfil de LinkedIn, actividad reciente)
4. Crear tarea previa a la reunión

### 3. Acuerdo Cerrado → Stack de Onboarding

**Disparador:** Etapa del acuerdo en CRM cambia a "Ganado-Cerrado"
**Acciones:**
1. Crear registro de cliente en la herramienta de SC (Vitally, Gainsight, ChurnZero)
2. Agregar a la plantilla del proyecto de onboarding
3. Enviar email de bienvenida a través de la herramienta de email
4. Crear canal de Slack: #cliente-[nombre-de-empresa]
5. Notificar al equipo de SC en Slack

### 4. Puntuación de Lead → Sincronización Entre Herramientas

**Disparador:** La puntuación del lead en CRM cruza el umbral de MQL
**Acciones:**
1. Actualizar el estado de la plataforma de automatización de marketing
2. Agregar a la audiencia de retargeting (Facebook, Google Ads)
3. Activar secuencia de alcance de SDR
4. Registrar evento en análisis (Mixpanel, Amplitude)

### 5. Incumplimiento de SLA → Alerta Multi-Canal

**Disparador:** Tarea de CRM atrasada (tarea de seguimiento de MQL)
**Acciones:**
1. Enviar DM de Slack al representante
2. Enviar email al representante
3. Si ≥2 horas atrasado → DM de Slack al gerente
4. Si ≥4 horas atrasado → reasignar en CRM (a través de webhook de vuelta al CRM)

### 6. Resumen Semanal del Pipeline

**Disparador:** Programación — cada lunes a las 8:00 AM
**Acciones:**
1. Consultar CRM para resumen del pipeline (valor total, nuevos acuerdos, acuerdos estancados, cierres esperados)
2. Formatear como resumen
3. Publicar en Slack #equipo-ventas
4. Enviar resumen por email al liderazgo de ventas
