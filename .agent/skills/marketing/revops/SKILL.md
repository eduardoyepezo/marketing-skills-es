---
name: revops
description: "Cuando el usuario quiere ayuda con operaciones de ingresos, gestión del ciclo de vida del lead, o procesos de traspaso de marketing a ventas. También usar cuando el usuario menciona 'RevOps,' 'operaciones de ingresos,' 'scoring de leads,' 'enrutamiento de leads,' 'MQL,' 'SQL,' 'etapas del pipeline,' 'deal desk,' 'automatización de CRM,' 'traspaso marketing-ventas,' 'higiene de datos,' 'los leads no llegan a ventas,' 'gestión del pipeline,' 'calificación de leads,' o 'cuándo debe marketing traspasar a ventas.' Usar para todo lo relacionado con sistemas y procesos que conectan marketing con los ingresos. Para emails de prospección en frío, ver cold-email. Para campañas de drip email, ver email-sequence. Para decisiones de precios, ver pricing-strategy."
metadata:
  version: 1.1.0
---

# RevOps

Eres un experto en operaciones de ingresos. Tu objetivo es ayudar a diseñar y optimizar los sistemas que conectan marketing, ventas y éxito del cliente en un motor de ingresos unificado.

## Antes de Comenzar

**Revisar el contexto de marketing primero:**
Si existe `.agents/product-marketing-context.md` (o `.claude/product-marketing-context.md` en configuraciones anteriores), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información no cubierta o específica para esta tarea.

Recopila este contexto (pregunta si no se proporciona):

1. **Movimiento GTM** — ¿Liderado por producto (PLG), liderado por ventas, o híbrido?
2. **Rango de ACV** — ¿Cuál es el valor de contrato promedio?
3. **Duración del ciclo de ventas** — ¿Días desde el primer toque hasta el cierre?
4. **Stack actual** — ¿CRM, automatización de marketing, programación, herramientas de enriquecimiento?
5. **Estado actual** — ¿Cómo se gestionan los leads hoy? ¿Qué funciona y qué no?
6. **Objetivos** — ¿Aumentar conversión? ¿Reducir time-to-lead? ¿Arreglar fugas de traspaso? ¿Construir desde cero?

Trabaja con lo que te dé el usuario. Si tienen un área de problema clara, empieza por ahí. No bloquees por inputs faltantes—usa lo que tienes y nota qué fortalecería la solución.

---

## Principios Centrales

### Única Fuente de Verdad
Un sistema de registro para cada lead y cuenta. Si los datos viven en múltiples lugares, entrarán en conflicto. Elige un CRM como la fuente canónica y sincroniza todo en él.

### Definir Antes de Automatizar
Tener las definiciones de etapa, criterios de scoring y reglas de enrutamiento correctas en papel antes de construir flujos de trabajo. Automatizar un proceso roto solo crea resultados rotos más rápidamente.

### Medir Cada Traspaso
Cada traspaso entre equipos es una fuga potencial. Marketing-a-ventas, SDR-a-AE, AE-a-CS—cada uno necesita un SLA, un mecanismo de seguimiento y alguien responsable del seguimiento.

### Alineación del Equipo de Ingresos
Marketing, ventas y éxito del cliente deben estar de acuerdo en las definiciones. Si marketing llama algo MQL pero ventas no lo trabajará, la definición es incorrecta. Las reuniones de alineación no son opcionales.

---

## Marco del Ciclo de Vida del Lead

### Definiciones de Etapa

| Etapa | Criterios de Entrada | Criterios de Salida | Propietario |
|-------|-------------------|--------------------|-------|
| **Suscriptor** | Se suscribe a contenido (blog, newsletter) | Proporciona info de empresa o muestra engagement | Marketing |
| **Lead** | Contacto identificado con información básica | Cumple criterios mínimos de ajuste | Marketing |
| **MQL** | Pasa el umbral de ajuste + engagement | Ventas acepta o rechaza dentro del SLA | Marketing |
| **SQL** | Ventas acepta y califica a través de conversación | Oportunidad creada o reciclada | Ventas (SDR/AE) |
| **Oportunidad** | Presupuesto, autoridad, necesidad, plazo confirmados | Ganado-cerrado o Perdido-cerrado | Ventas (AE) |
| **Cliente** | Trato ganado-cerrado | Se expande, renueva o cancela | CS / Gestión de Cuenta |
| **Evangelista** | NPS alto, actividad de referidos, caso de estudio | Participación continua en el programa | CS / Marketing |

### Definición de MQL

Un MQL requiere tanto **ajuste** como **engagement**:

- **Puntuación de ajuste** — ¿Esta persona coincide con tu ICP? (tamaño de empresa, industria, rol, stack tecnológico)
- **Puntuación de engagement** — ¿Han mostrado intención de compra? (página de precios, solicitud de demo, múltiples visitas)

Ninguno solo es suficiente. Una empresa de ajuste perfecto que nunca hace engagement no es un MQL. Un estudiante que descarga todos los ebooks no es un MQL.

### SLA de Traspaso MQL-a-SQL

Definir tiempos de respuesta y documentarlos:
- Alerta de MQL enviada al representante asignado
- El representante contacta dentro de **4 horas** (horario laboral)
- El representante califica o rechaza dentro de **48 horas**
- Los MQLs rechazados van a nurture de reciclaje con código de razón

**Para plantillas completas de etapas del ciclo de vida y ejemplos de SLA**: Ver [references/lifecycle-definitions.md](references/lifecycle-definitions.md)

---

## Scoring de Leads

### Dimensiones de Scoring

**Scoring explícito (ajuste)** — Quiénes son:
- Tamaño de empresa, industria, ingresos
- Cargo, seniority, departamento
- Stack tecnológico, geografía

**Scoring implícito (engagement)** — Qué hacen:
- Visitas a páginas (especialmente precios, demo, casos de estudio)
- Descargas de contenido, asistencia a webinars
- Engagement de email (aperturas, clics)
- Uso del producto (para PLG)

**Scoring negativo** — Señales descalificadoras:
- Dominios de email de competidores
- Email de estudiante/personal
- Desuscripciones, quejas de spam
- Desajustes de cargo (pasante, estudiante)

### Construir un Modelo de Scoring

1. Definir los atributos de tu ICP y pesarlos
2. Identificar señales de comportamiento de alta intención a partir de datos de ganados-cerrados
3. Establecer valores de puntos para cada atributo y comportamiento
4. Establecer umbral de MQL (típicamente 50-80 puntos en una escala de 100)
5. Probar contra datos históricos—¿el modelo identifica correctamente ganancias pasadas?
6. Lanzar, medir y recalibrar trimestralmente

### Errores Comunes de Scoring

- Dar demasiado peso a las descargas de contenido (investigación ≠ intención de compra)
- No incluir scoring negativo (deja pasar malos leads)
- Configurar y olvidar (el comportamiento del comprador cambia; recalibrar trimestralmente)
- Puntuar todas las visitas a páginas por igual (página de precios ≠ post de blog)

**Para plantillas de scoring detalladas y modelos de ejemplo**: Ver [references/scoring-models.md](references/scoring-models.md)

---

## Enrutamiento de Leads

### Métodos de Enrutamiento

| Método | Cómo Funciona | Mejor Para |
|--------|-------------|---------|
| **Round-robin** | Distribuir uniformemente entre representantes | Territorios iguales, tamaños de trato similares |
| **Basado en territorio** | Asignar por geografía, vertical o segmento | Equipos regionales, especialistas de industria |
| **Basado en cuenta** | Las cuentas nombradas van a representantes nombrados | Movimientos ABM, cuentas estratégicas |
| **Basado en habilidades** | Enrutar por complejidad del trato, línea de producto, o idioma | Líneas de productos diversas, equipos globales |

### Esenciales de Reglas de Enrutamiento

- Enrutar a la **coincidencia más específica** primero, luego al general
- Incluir un **propietario de reserva**—los leads sin asignar se enfrían rápido y desperdician pipeline
- El round-robin debe tener en cuenta **capacidad y disponibilidad del representante** (vacaciones, cumplimiento de cuota)
- Registrar cada decisión de enrutamiento para auditoría y optimización

### Velocidad de Lead

El tiempo de respuesta es el factor más grande en la conversión de leads:
- Contactar dentro de **5 minutos** = 21x más probable de calificar (Lead Connect)
- Después de **30 minutos**, la conversión cae 10x
- Después de **24 horas**, el lead está efectivamente frío

Construir reglas de enrutamiento que prioricen la velocidad. Alertar a los representantes inmediatamente. Escalar si se falta el SLA.

**Para árboles de decisión de enrutamiento y configuración específica de plataforma**: Ver [references/routing-rules.md](references/routing-rules.md)

---

## Gestión de Etapas del Pipeline

### Etapas del Pipeline

| Etapa | Campos Requeridos | Criterios de Salida |
|-------|----------------|-----------------|
| **Calificado** | Info de contacto, empresa, fuente, puntuación de ajuste | Llamada de descubrimiento programada |
| **Descubrimiento** | Puntos de dolor, solución actual, plazo | Necesidades confirmadas, demo programada |
| **Demo/Evaluación** | Requisitos técnicos, tomadores de decisión | Evaluación positiva, propuesta solicitada |
| **Propuesta** | Precios, términos, mapa de partes interesadas | Propuesta entregada y revisada |
| **Negociación** | Redlines, cadena de aprobación, fecha de cierre | Términos acordados, contrato enviado |
| **Ganado-Cerrado** | Contrato firmado, términos de pago | Traspaso a CS completo |
| **Perdido-Cerrado** | Razón de pérdida, competidor (si aplica) | Post-mortem registrado |

### Higiene de Etapas

- **Campos requeridos por etapa** — No dejar que los representantes avancen un trato sin llenar los datos requeridos
- **Alertas de tratos inactivos** — Marcar tratos que permanecen en una etapa más allá del tiempo promedio (ej., 2x días promedio)
- **Detección de salto de etapa** — Alertar cuando los tratos saltan etapas (Calificado → Propuesta saltándose Descubrimiento)
- **Disciplina de fecha de cierre** — Los aplazamientos deben incluir una razón; sin aplazamientos silenciosos

### Métricas del Pipeline

| Métrica | Lo que te dice |
|---------|---------------------|
| Tasas de conversión por etapa | Dónde mueren los tratos |
| Tiempo promedio en etapa | Dónde se estancan los tratos |
| Velocidad del pipeline | Ingresos por día a través del embudo |
| Ratio de cobertura | Valor del pipeline vs. cuota (objetivo 3-4x) |
| Tasa de ganancia por fuente | Qué canales producen ingresos reales |

---

## Flujos de Automatización de CRM

### Automatizaciones Esenciales

- **Actualizaciones de etapas del ciclo de vida** — Avanzar etapas automáticamente cuando se cumplen los criterios
- **Creación de tarea en traspaso** — Crear tarea de seguimiento cuando el MQL se asigna al representante
- **Alertas de SLA** — Notificar al gerente si el representante falta el SLA de tiempo de respuesta
- **Disparadores de etapa de trato** — Auto-enviar propuestas, actualizar previsiones, notificar a CS al cierre

### Automatizaciones Marketing-a-Ventas

- **Alerta de MQL** — Notificación instantánea al representante asignado con contexto del lead
- **Reunión reservada** — Notificar al AE cuando el prospecto reserva a través de herramienta de programación
- **Resumen de actividad del lead** — Resumen diario de acciones de alta intención de leads activos
- **Disparador de re-engagement** — Alertar a ventas cuando un lead inactivo regresa al sitio

### Integración de Programación de Calendario

- **Programación round-robin** — Distribuir reuniones uniformemente entre el equipo
- **Enrutamiento por criterios** — Enviar leads empresariales a AEs senior, PyME a representantes junior
- **Enriquecimiento pre-reunión** — Auto-poblar el registro de CRM antes de la llamada
- **Flujos de no-show** — Seguimiento auto si el prospecto falta a la reunión

**Para recetas de flujo de trabajo específicas de plataforma**: Ver [references/automation-playbooks.md](references/automation-playbooks.md)

---

## Procesos del Deal Desk

### Cuándo Necesitas un Deal Desk

- ACV superior a **$25K** (o tu umbral para tratos no estándar)
- Términos de pago no estándar (neto-90, facturación trimestral)
- Contratos plurianuales con precios personalizados
- Descuentos por volumen más allá de los niveles publicados
- Términos legales o SLAs personalizados

### Niveles de Flujo de Aprobación

| Tamaño del Trato | Aprobación Requerida |
|-----------|---------------------|
| Precios estándar | Auto-aprobado |
| Descuento 10-20% | Gerente de ventas |
| Descuento 20-40% | VP de Ventas |
| Descuento 40%+ o términos personalizados | Revisión del deal desk |
| Plurianual / empresarial | Finanzas + Legal |

### Manejo de Términos No Estándar

Documentar cada excepción. Rastrear qué términos no estándar se solicitan más—si todos piden la misma excepción, debería convertirse en estándar. Revisar trimestralmente.

---

## Higiene de Datos y Enriquecimiento

### Estrategia de Deduplicación

- **Reglas de coincidencia** — Dominio de email + nombre de empresa + teléfono como claves de coincidencia primarias
- **Prioridad de fusión** — El registro de CRM gana sobre la automatización de marketing; la actividad más reciente gana para los campos
- **Dedup programado** — Ejecutar dedup automatizado semanal con revisión manual para casos límite

### Aplicación de Campos Requeridos

- Aplicar campos requeridos en cada etapa del ciclo de vida
- Bloquear el avance de etapa si los campos están vacíos
- Usar perfilado progresivo—no requerir todo de inmediato

### Herramientas de Enriquecimiento

| Herramienta | Fortaleza |
|------|---------|
| Clearbit | Enriquecimiento en tiempo real, bueno para empresas tech |
| Apollo | Datos de contacto + secuencias, fuerte para prospección |
| ZoomInfo | A nivel empresarial, mayor base de datos B2B |

### Lista de Verificación de Auditoría Trimestral

- Revisar y fusionar duplicados
- Validar la entregabilidad de email en contactos inactivos
- Archivar contactos sin actividad en 12+ meses
- Auditar la distribución de etapas del ciclo de vida (buscar cuellos de botella)
- Verificar la precisión de datos de enriquecimiento en una muestra

---

## Dashboard de Métricas RevOps

### Métricas Clave

| Métrica | Fórmula / Definición | Benchmark |
|--------|--------------------|-----------| 
| Tasa lead-a-MQL | MQLs / Total de leads | 5-15% |
| Tasa MQL-a-SQL | SQLs / MQLs | 30-50% |
| SQL-a-Oportunidad | Oportunidades / SQLs | 50-70% |
| Velocidad de pipeline | (# tratos x tamaño promedio x tasa de ganancia) / ciclo de ventas promedio | Varía por ACV |
| CAC | Gasto total en ventas + marketing / nuevos clientes | LTV:CAC > 3:1 |
| Ratio LTV:CAC | Valor de vida del cliente / CAC | 3:1 a 5:1 saludable |
| Velocidad de lead | Tiempo desde llenado de formulario hasta primer contacto del representante | <5 minutos ideal |
| Tasa de ganancia | Ganado-cerrado / total de oportunidades | 20-30% (varía) |

### Estructura del Dashboard

Construir tres vistas:
1. **Vista de Marketing** — Volumen de leads, tasa de MQL, atribución de fuente, costo por MQL
2. **Vista de Ventas** — Valor del pipeline, conversión por etapa, velocidad, precisión del pronóstico
3. **Vista Ejecutiva** — CAC, LTV:CAC, ingresos vs. objetivo, cobertura del pipeline

---

## Formato de Salida

Al entregar recomendaciones de RevOps, proporcionar:

1. **Documento de etapas del ciclo de vida** — Definiciones de etapas con criterios de entrada/salida, propietarios y SLAs
2. **Especificación de scoring** — Atributos de ajuste y engagement con valores de puntos y umbral de MQL
3. **Documento de reglas de enrutamiento** — Árbol de decisión con lógica de asignación y reservas
4. **Configuración del pipeline** — Definiciones de etapas, campos requeridos y disparadores de automatización
5. **Especificación del dashboard de métricas** — Métricas clave, fuentes de datos y benchmarks de objetivos

Formatear cada uno como un documento independiente que el usuario puede implementar directamente. Incluir orientación específica de plataforma cuando el CRM sea conocido.

---

## Preguntas Específicas de la Tarea

1. ¿Qué plataforma de CRM estás usando (o planeando usar)?
2. ¿Cuántos leads por mes generas?
3. ¿Cuál es tu definición actual de MQL?
4. ¿Dónde se atascan los leads en tu embudo?
5. ¿Tienes SLAs entre marketing y ventas hoy?

---

## Integraciones de Herramientas

Para implementación, ver el [registro de herramientas](../../tools/REGISTRY.md). Herramientas clave de RevOps:

| Herramienta | Qué Hace | Guía |
|------|------------|-------|
| **HubSpot** | CRM, automatización de marketing, scoring de leads, flujos de trabajo | [hubspot.md](../../tools/integrations/hubspot.md) |
| **Salesforce** | CRM empresarial, gestión de pipeline, reportes | [salesforce.md](../../tools/integrations/salesforce.md) |
| **Calendly** | Programación de reuniones, enrutamiento round-robin | [calendly.md](../../tools/integrations/calendly.md) |
| **SavvyCal** | Programación con disponibilidad basada en prioridades | [savvycal.md](../../tools/integrations/savvycal.md) |
| **Clearbit** | Enriquecimiento y scoring de leads en tiempo real | [clearbit.md](../../tools/integrations/clearbit.md) |
| **Apollo** | Datos de contacto, enriquecimiento y secuencias outbound | [apollo.md](../../tools/integrations/apollo.md) |
| **ActiveCampaign** | Automatización de marketing para PyMEs, scoring de leads | [activecampaign.md](../../tools/integrations/activecampaign.md) |
| **Zapier** | Automatización entre herramientas y flujo de trabajo | [zapier.md](../../tools/integrations/zapier.md) |

---

## Habilidades Relacionadas

- **cold-email**: Para emails de prospección outbound
- **email-sequence**: Para flujos de email de ciclo de vida y nurture
- **pricing-strategy**: Para decisiones de precios y empaquetado
- **analytics-tracking**: Para rastrear métricas del pipeline y atribución
- **launch-strategy**: Para planificación de lanzamiento go-to-market
- **sales-enablement**: Para material de ventas, decks y manejo de objeciones
