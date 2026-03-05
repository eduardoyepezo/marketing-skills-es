# Modelos de Puntuación de Leads

Plantillas de puntuación detalladas, modelos de ejemplo por tipo de negocio y orientación de calibración.

## Plantilla de Puntuación Explícita (Ajuste)

### Atributos de la Empresa

| Atributo | Criterio | Puntos |
|-----------|----------|--------|
| **Tamaño de empresa** | 1-10 empleados | +5 |
| | 11-50 empleados | +10 |
| | 51-200 empleados | +15 |
| | 201-1000 empleados | +20 |
| | 1000+ empleados | +15 (a menos que sea enfocado en enterprise, entonces +25) |
| **Industria** | Industria objetivo principal | +20 |
| | Industria objetivo secundaria | +10 |
| | Industria no objetivo | 0 |
| **Ingresos** | Por debajo de $1M | +5 |
| | $1M-$10M | +10 |
| | $10M-$100M | +15 |
| | $100M+ | +20 |
| **Geografía** | Mercado primario | +10 |
| | Mercado secundario | +5 |
| | Mercado no objetivo | 0 |

### Atributos del Contacto

| Atributo | Criterio | Puntos |
|-----------|----------|--------|
| **Cargo** | C-suite (CEO, CTO, CMO) | +25 |
| | Nivel VP | +20 |
| | Nivel Director | +15 |
| | Nivel Gerente | +10 |
| | Colaborador individual | +5 |
| **Departamento** | Departamento de compras principal | +15 |
| | Departamento adyacente | +5 |
| | Departamento no relacionado | 0 |
| **Antigüedad** | Tomador de decisiones | +20 |
| | Influenciador | +10 |
| | Usuario final | +5 |

### Atributos de Tecnología

| Atributo | Criterio | Puntos |
|-----------|----------|--------|
| **Stack técnico** | Usa herramienta complementaria | +15 |
| | Usa competidor | +10 (entienden la categoría) |
| | Usa herramienta que reemplazamos | +20 |
| **Madurez tecnológica** | Stack moderno (nube, SaaS-forward) | +10 |
| | Stack heredado | +5 |

---

## Plantilla de Puntuación Implícita (Engagement)

### Señales de Alta Intención

| Señal | Puntos | Decaimiento |
|--------|--------|-------|
| **Solicitud de demo** | +30 | Ninguno |
| **Visita a la página de precios** | +20 | -5 por semana |
| **Registro de prueba gratis** | +25 | Ninguno |
| **Formulario de contacto a ventas** | +30 | Ninguno |
| **Página de caso de estudio (2+)** | +15 | -5 por 2 semanas |
| **Visita a la página de comparación** | +15 | -5 por semana |
| **Calculadora de ROI usada** | +20 | -5 por 2 semanas |

### Señales de Intención Media

| Señal | Puntos | Decaimiento |
|--------|--------|-------|
| **Registro a webinar** | +10 | -5 por mes |
| **Asistencia a webinar** | +15 | -5 por mes |
| **Descarga de whitepaper** | +10 | -5 por mes |
| **Visita al blog (3+ en una semana)** | +10 | -5 por 2 semanas |
| **Clic en email** | +5 por clic | -2 por mes |
| **Apertura de email (3+)** | +5 | -2 por mes |
| **Engagement en redes sociales** | +5 | -2 por mes |

### Señales de Baja Intención

| Señal | Puntos | Decaimiento |
|--------|--------|-------|
| **Visita única al blog** | +2 | -2 por mes |
| **Apertura del newsletter** | +2 | -1 por mes |
| **Apertura única de email** | +1 | -1 por mes |
| **Visitó solo la página de inicio** | +1 | -1 por semana |

### Señales de Uso del Producto (PLG)

| Señal | Puntos | Decaimiento |
|--------|--------|-------|
| **Creó cuenta** | +15 | Ninguno |
| **Completó el onboarding** | +20 | Ninguno |
| **Usó la función central (3+ veces)** | +25 | -5 por mes inactivo |
| **Invitó a un miembro del equipo** | +25 | Ninguno |
| **Alcanzó el límite de uso** | +20 | -10 por mes |
| **Exportó datos** | +10 | -5 por mes |
| **Conectó una integración** | +15 | Ninguno |
| **Activo diariamente 5+ días** | +20 | -10 por 2 semanas inactivo |

---

## Señales de Puntuación Negativa

| Señal | Puntos | Notas |
|--------|--------|-------|
| **Dominio de email de competidor** | -50 | Marcar automáticamente para revisión |
| **Email de estudiante (.edu)** | -30 | Puede seguir siendo válido en algunos casos |
| **Email personal (gmail, yahoo)** | -10 | Menos relevante para B2B; ajustar para PYME |
| **Cancelar suscripción de emails** | -20 | Reducir puntuación de engagement |
| **Rebote (duro)** | -50 | Eliminar de la puntuación |
| **Queja de spam** | -100 | Eliminar de todas las secuencias |
| **Cargo: Estudiante/Pasante** | -25 | Baja autoridad de compra |
| **Cargo: Consultor** | -10 | Puede estar evaluando para un cliente |
| **Sin visita al sitio web en 90 días** | -15 | Decaimiento de puntuación |
| **Número de teléfono inválido** | -10 | Señal de calidad de datos |
| **Solo visitó la página de carreras** | -30 | Probablemente buscador de empleo |

---

## Modelos de Puntuación de Ejemplo

### Modelo 1: SaaS PLG (ACV $500-$5K)

**Peso: 30% ajuste / 70% engagement (favorecer fuertemente el uso del producto)**

**Criterios de ajuste:**
- Tamaño de empresa 10-500: +15
- Industria objetivo: +10
- Rol Gerente+: +10
- Usa herramienta complementaria: +10

**Criterios de engagement:**
- Creó cuenta gratis: +15
- Completó el onboarding: +20
- Usó función central 3+ veces: +25
- Invitó a un miembro del equipo: +25
- Alcanzó el límite de uso: +20
- Visita a la página de precios: +15

**Negativo:**
- Email personal: -10
- Sin inicio de sesión en 14 días: -15
- Dominio de competidor: -50

**Umbral de MQL: 60 puntos**
**Recalibración: Mensual** (ciclo de retroalimentación rápido con alto volumen)

---

### Modelo 2: Ventas-Led Enterprise (ACV $50K+)

**Peso: 60% ajuste / 40% engagement (el ajuste es crítico a este ACV)**

**Criterios de ajuste:**
- Tamaño de empresa 500+: +20
- Ingresos $50M+: +15
- Industria objetivo: +15
- Título VP+: +20
- Tomador de decisiones confirmado: +15
- Usa competidor: +10

**Criterios de engagement:**
- Solicitud de demo: +30
- Múltiples partes interesadas involucradas: +20
- Asistió a webinar ejecutivo: +15
- Descargó guía de ROI: +10
- Visitó la página de precios 2+: +15

**Negativo:**
- Empresa demasiado pequeña (<100): -30
- Solo colaborador individual: -15
- Dominio de competidor: -50

**Umbral de MQL: 75 puntos**
**Recalibración: Trimestral** (ciclos de venta más largos, tamaño de muestra más pequeño)

---

### Modelo 3: Mercado Medio Híbrido (ACV $5K-$25K)

**Peso: 50% ajuste / 50% engagement (enfoque equilibrado)**

**Criterios de ajuste:**
- Tamaño de empresa 50-1000: +15
- Industria objetivo: +10
- Título Gerente-VP: +15
- Geografía objetivo: +10
- Usa herramienta complementaria: +10

**Criterios de engagement:**
- Solicitud de demo o registro de prueba: +25
- Visita a la página de precios: +15
- Descarga de caso de estudio: +10
- Asistencia a webinar: +10
- Engagement por email (3+ clics): +10
- Visitas al blog (5+ páginas): +10

**Negativo:**
- Email personal: -10
- Sin engagement en 30 días: -10
- Dominio de competidor: -50
- Título de estudiante/pasante: -25

**Umbral de MQL: 65 puntos**
**Recalibración: Trimestral**

---

## Calibración del Umbral

### Establecer el Umbral Inicial

1. **Extraer datos de ganado-cerrado** de los últimos 6-12 meses
2. **Puntuar retroactivamente** cada acuerdo usando tu nuevo modelo
3. **Encontrar el punto de quiebre natural** — ¿qué puntuación separó las victorias de las pérdidas?
4. **Establecer el umbral** justo por debajo de donde el 80% de los acuerdos ganados cerrados habrían puntuado
5. **Validar** contra perdido-cerrado — si muchos perdidos puntúan por encima del umbral, apretar los criterios

### Cadencia de Calibración

| Tipo de Negocio | Frecuencia de Recalibración | Por Qué |
|---------------|------------------------|-----|
| PLG / Alto volumen | Mensual | Ciclo de retroalimentación rápido, muchos datos |
| Mercado medio | Trimestral | Longitud de ciclo moderada |
| Enterprise | Trimestral a semi-anual | Ciclos largos, tamaño de muestra pequeño |

### Pasos de Calibración

1. **Extraer datos de MQL a cierre** para el período de calibración
2. **Comparar MQLs puntuados vs. resultados reales:**
   - Puntuación alta + ganado-cerrado = correctamente puntuado
   - Puntuación alta + perdido-cerrado = posible falso positivo (apretar)
   - Puntuación baja + ganado-cerrado = posible falso negativo (aflojar)
3. **Ajustar los pesos** según qué atributos se correlacionaron realmente con las victorias
4. **Ajustar el umbral** si el volumen de MQL es demasiado alto (subir) o demasiado bajo (bajar)
5. **Documentar cambios** y comunicar al equipo de ventas

### Señales de Advertencia de que Tu Modelo Necesita Recalibración

- La tasa de aceptación de MQL a SQL cae por debajo del 30%
- Ventas rechaza constantemente los MQLs como "no están listos"
- Los leads de alta puntuación no se convierten; los de baja puntuación sí
- El volumen de MQL se dispara sin ingresos correspondientes
- Cambios en el producto/mercado desde la última calibración
