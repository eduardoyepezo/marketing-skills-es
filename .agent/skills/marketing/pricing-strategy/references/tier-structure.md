# Estructura de Niveles y Packaging

## Contenidos
- ¿Cuántos Niveles?
- Framework Bueno-Mejor-Óptimo
- Estrategias de Diferenciación de Niveles
- Ejemplo de Estructura de Niveles
- Packaging para Personas (Identificar Personas de Precios, Packaging Basado en Personas)
- Freemium vs. Prueba Gratis (Cuándo Usar Freemium, Cuándo Usar Prueba Gratis, Enfoques Híbridos)
- Precios Enterprise (Cuándo Agregar Precios Personalizados, Elementos del Nivel Enterprise, Estrategias de Precios Enterprise)

## ¿Cuántos Niveles?

**2 niveles:** Simple, opción clara
- Funciona para: División clara de PYME vs. Enterprise
- Riesgo: Puede dejar dinero sobre la mesa

**3 niveles:** Estándar de la industria
- Nivel Bueno = Punto de entrada
- Nivel Mejor = Recomendado (anclar al mejor)
- Nivel Óptimo = Clientes de alto valor

**4+ niveles:** Más granularidad
- Funciona para: Amplio rango de tamaños de cliente
- Riesgo: Parálisis de decisión, complejidad

---

## Framework Bueno-Mejor-Óptimo

**Nivel Bueno (Entrada):**
- Propósito: Eliminar barreras de entrada
- Incluye: Funciones centrales, uso limitado
- Precio: Bajo, accesible
- Objetivo: Equipos pequeños, probar antes de comprar

**Nivel Mejor (Recomendado):**
- Propósito: Donde aterriza la mayoría de los clientes
- Incluye: Funciones completas, límites razonables
- Precio: Tu precio "ancla"
- Objetivo: Equipos en crecimiento, usuarios serios

**Nivel Óptimo (Premium):**
- Propósito: Capturar clientes de alto valor
- Incluye: Todo, funciones avanzadas, límites más altos
- Precio: Premium (a menudo 2-3x "Mejor")
- Objetivo: Equipos más grandes, usuarios de poder, empresas

---

## Estrategias de Diferenciación de Niveles

**Restricción de funciones:**
- Funciones básicas en todos los niveles
- Funciones avanzadas en niveles superiores
- Funciona cuando las funciones tienen diferencias de valor claras

**Límites de uso:**
- Mismas funciones, diferentes límites
- Más usuarios, almacenamiento, llamadas API en niveles superiores
- Funciona cuando el valor escala con el uso

**Nivel de soporte:**
- Soporte por email → Soporte prioritario → Éxito dedicado
- Funciona para productos con complejidad de implementación

**Acceso y personalización:**
- Acceso API, SSO, marca personalizada
- Funciona para diferenciación enterprise

---

## Ejemplo de Estructura de Niveles

```
┌────────────────┬─────────────────┬─────────────────┬─────────────────┐
│                │ Starter         │ Pro             │ Business        │
│                │ $29/mes         │ $79/mes         │ $199/mes        │
├────────────────┼─────────────────┼─────────────────┼─────────────────┤
│ Usuarios       │ Hasta 5         │ Hasta 20        │ Ilimitados      │
│ Proyectos      │ 10              │ Ilimitados      │ Ilimitados      │
│ Almacenamiento │ 5 GB            │ 50 GB           │ 500 GB          │
│ Integraciones  │ 3               │ 10              │ Ilimitadas      │
│ Análisis       │ Básico          │ Avanzado        │ Personalizado   │
│ Soporte        │ Email           │ Prioritario     │ Dedicado        │
│ Acceso API     │ ✗               │ ✓               │ ✓               │
│ SSO            │ ✗               │ ✗               │ ✓               │
│ Logs de auditoría│ ✗             │ ✗               │ ✓               │
└────────────────┴─────────────────┴─────────────────┴─────────────────┘
```

---

## Packaging para Personas

### Identificar Personas de Precios

Diferentes clientes tienen:
- Diferente disposición a pagar
- Diferentes necesidades de función
- Diferentes procesos de compra
- Diferente percepción de valor

**Segmentar por:**
- Tamaño de empresa (autónomo → PYME → enterprise)
- Caso de uso (marketing vs. ventas vs. soporte)
- Sofisticación (principiante → usuario de poder)
- Industria (diferentes normas de presupuesto)

### Packaging Basado en Personas

**Paso 1: Definir personas**

| Persona | Tamaño | Necesidades | DAP | Ejemplo |
|---------|------|-------|-----|---------| 
| Freelancer | 1 persona | Funciones básicas | Bajo | $19/mes |
| Equipo Pequeño | 2-10 | Colaboración | Medio | $49/mes |
| Empresa en Crecimiento | 10-50 | Escala, integraciones | Más alto | $149/mes |
| Enterprise | 50+ | Seguridad, soporte | Alto | Personalizado |

**Paso 2: Mapear funciones a personas**

| Función | Freelancer | Equipo Peq. | En Crecimiento | Enterprise |
|---------|------------|------------|---------|------------|
| Funciones centrales | ✓ | ✓ | ✓ | ✓ |
| Colaboración | — | ✓ | ✓ | ✓ |
| Integraciones | — | Limitadas | Completas | Completas |
| Acceso API | — | — | ✓ | ✓ |
| SSO/SAML | — | — | — | ✓ |
| Logs de auditoría | — | — | — | ✓ |
| Contrato personalizado | — | — | — | ✓ |

**Paso 3: Precio según el valor de cada persona**
- Investigar la disposición a pagar por segmento
- Establecer precios que capturen valor sin bloquear la adopción
- Considerar páginas de destino específicas por segmento

---

## Freemium vs. Prueba Gratis

### Cuándo Usar Freemium

**El freemium funciona cuando:**
- El producto tiene efectos virales/de red
- Los usuarios gratuitos proporcionan valor (contenido, datos, referidos)
- Mercado grande donde el % de conversión impulsa el volumen
- Bajo costo marginal para servir a usuarios gratuitos
- Límites claros de función/uso para el disparador de actualización

**Riesgos del freemium:**
- Los usuarios gratuitos pueden no convertirse nunca
- Devalúa la percepción del producto
- Costos de soporte para usuarios no pagadores
- Más difícil subir los precios más tarde

### Cuándo Usar Prueba Gratis

**La prueba gratis funciona cuando:**
- El producto necesita tiempo para demostrar valor
- Se requiere inversión en onboarding/configuración
- B2B con comités de compra
- Puntos de precio más altos
- El producto es "adhesivo" una vez configurado

**Mejores prácticas de prueba:**
- 7-14 días para productos simples
- 14-30 días para productos complejos
- Acceso completo (no con funciones limitadas)
- Cuenta regresiva clara y recordatorios
- Compensación de tarjeta de crédito opcional vs. requerida

**Tarjeta de crédito por adelantado:**
- Mayor conversión de prueba a pago (40-50% vs. 15-25%)
- Menor volumen de prueba
- Leads mejor calificados

### Enfoques Híbridos

**Freemium + Prueba:**
- Nivel gratuito con funciones limitadas
- Prueba de funciones premium
- Ejemplo: Zoom (gratis 40 min, prueba de Pro)

**Prueba inversa:**
- Comenzar con acceso completo
- Después de la prueba, degradar al nivel gratuito
- Ejemplo: Ver el valor premium, vivir con las limitaciones hasta estar listo

---

## Precios Enterprise

### Cuándo Agregar Precios Personalizados

Agregar "Contactar Ventas" cuando:
- Los tamaños de acuerdo superan $10k+ ARR
- Los clientes necesitan contratos personalizados
- Se requiere implementación/onboarding
- Requisitos de seguridad/cumplimiento
- Procesos de adquisición involucrados

### Elementos del Nivel Enterprise

**Tabla de requisitos:**
- SSO/SAML
- Logs de auditoría
- Controles de administrador
- SLA de tiempo de actividad
- Certificaciones de seguridad

**Complementos de valor:**
- Soporte/éxito dedicado
- Onboarding personalizado
- Sesiones de capacitación
- Integraciones personalizadas
- Entrada prioritaria al roadmap

### Estrategias de Precios Enterprise

**Por asiento a escala:**
- Descuentos por volumen para equipos grandes
- Ejemplo: $15/usuario (estándar) → $10/usuario (100+)

**Tarifa de plataforma + uso:**
- Tarifa base para el acceso
- Basado en uso por encima de umbrales
- Ejemplo: $500/mes base + $0.01 por llamada API

**Contratos basados en valor:**
- Precio vinculado a ingresos/resultados del cliente
- Ejemplo: % de transacciones, participación en ingresos
