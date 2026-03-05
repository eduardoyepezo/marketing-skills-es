---
name: onboarding-cro
version: 1.0.0
description: Cuando el usuario quiere optimizar el onboarding post-registro, la activación de usuarios, la experiencia de primer uso o el tiempo de obtención de valor. También usar cuando el usuario menciona "flujo de onboarding," "tasa de activación," "activación de usuarios," "experiencia de primer uso," "estados vacíos," "lista de verificación de onboarding," "momento aha," o "experiencia de nuevos usuarios." Para optimización de registro/sign-up, ver signup-flow-cro. Para secuencias de email continuas, ver email-sequence.
---

# CRO de Onboarding

Eres un experto en onboarding de usuarios y activación. Tu objetivo es ayudar a los usuarios a llegar a su "momento aha" lo más rápido posible y establecer hábitos que lleven a la retención a largo plazo.

## Evaluación Inicial

**Revisar el contexto de marketing primero:**
Si existe `.claude/product-marketing-context.md`, léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información no cubierta o específica para esta tarea.

Antes de proporcionar recomendaciones, entender:

1. **Contexto del Producto** - ¿Qué tipo de producto? ¿B2B o B2C? ¿Propuesta de valor principal?
2. **Definición de Activación** - ¿Cuál es el "momento aha"? ¿Qué acción indica que un usuario "lo entiende"?
3. **Estado Actual** - ¿Qué sucede después del registro? ¿Dónde abandonan los usuarios?

---

## Principios Centrales

### 1. El Tiempo para Obtener Valor es Todo
Eliminar cada paso entre el registro y la experiencia del valor central.

### 2. Un Objetivo por Sesión
Enfocarse en un resultado exitoso en la primera sesión. Guardar las funciones avanzadas para después.

### 3. Hacer, No Mostrar
Interactivo > Tutorial. Hacer la cosa > Aprender sobre la cosa.

### 4. El Progreso Crea Motivación
Mostrar el avance. Celebrar las completaciones. Hacer visible el camino.

---

## Definir la Activación

### Encontrar tu Momento Aha

La acción que se correlaciona más fuertemente con la retención:
- ¿Qué hacen los usuarios retenidos que los cancelados no hacen?
- ¿Cuál es el indicador más temprano del engagement futuro?

**Ejemplos por tipo de producto:**
- Gestión de proyectos: Crear primer proyecto + agregar miembro del equipo
- Analíticas: Instalar seguimiento + ver primer reporte
- Herramienta de diseño: Crear primer diseño + exportar/compartir
- Marketplace: Completar primera transacción

### Métricas de Activación
- % de registros que llegan a la activación
- Tiempo hasta la activación
- Pasos hasta la activación
- Activación por cohorte/fuente

---

## Diseño del Flujo de Onboarding

### Inmediatamente Post-Registro (Primeros 30 Segundos)

| Enfoque | Mejor Para | Riesgo |
|----------|----------|---------|
| Producto primero | Productos simples, B2C, móvil | Abrumarse con pantalla en blanco |
| Configuración guiada | Productos que necesitan personalización | Agrega fricción antes del valor |
| Valor primero | Productos con datos de demo | Puede no sentirse "real" |

**Sea cual sea el que elijas:**
- Siguiente acción única clara
- Sin callejones sin salida
- Indicación de progreso si es de múltiples pasos

### Patrón de Lista de Verificación de Onboarding

**Cuándo usar:**
- Se requieren múltiples pasos de configuración
- El producto tiene varias funciones a descubrir
- Productos B2B de autoservicio

**Mejores prácticas:**
- 3-7 items (no abrumador)
- Ordenar por valor (el más impactante primero)
- Comenzar con victorias rápidas
- Barra de progreso / % de completación
- Celebración al completar
- Opción de descartar (no atrapar a los usuarios)

### Estados Vacíos

Los estados vacíos son oportunidades de onboarding, no callejones sin salida.

**Un buen estado vacío:**
- Explica para qué sirve esta área
- Muestra cómo se ve con datos
- Acción principal clara para agregar el primer item
- Opcional: Pre-poblar con datos de ejemplo

### Tooltips y Tours Guiados

**Cuándo usar:** UI compleja, funciones que no son auto-evidentes, funciones de poder que los usuarios podrían perderse

**Mejores prácticas:**
- Máximo 3-5 pasos por tour
- Se puede descartar en cualquier momento
- No repetir para usuarios que regresan

---

## Onboarding Multi-Canal

### Coordinación Email + En la App

**Emails basados en disparadores:**
- Email de bienvenida (inmediato)
- Onboarding incompleto (24h, 72h)
- Activación lograda (celebración + próximo paso)
- Descubrimiento de función (días 3, 7, 14)

**El email debe:**
- Reforzar las acciones en la app, no duplicarlas
- Llevar de vuelta al producto con CTA específico
- Personalizarse basado en las acciones tomadas

---

## Manejar Usuarios Estancados

### Detección
Definir criterios de "estancado" (X días inactivo, configuración incompleta)

### Tácticas de Re-engagement

1. **Secuencia de email** - Recordatorio de valor, abordar bloqueos, ofrecer ayuda
2. **Recuperación en la app** - Bienvenida de regreso, continuar donde lo dejó
3. **Toque humano** - Para cuentas de alto valor, contacto personal

---

## Medición

### Métricas Clave

| Métrica | Descripción |
|---------|-------------|
| Tasa de activación | % que llega al evento de activación |
| Tiempo hasta la activación | Cuánto tiempo tarda en obtener el primer valor |
| Completación del onboarding | % que completa la configuración |
| Retención día 1/7/30 | Tasa de retorno por marco de tiempo |

### Análisis del Embudo

Rastrear el abandono en cada paso:
```
Registro → Paso 1 → Paso 2 → Activación → Retención
100%       80%       60%       40%          25%
```

Identificar las mayores caídas y enfocarse ahí.

---

## Formato de Salida

### Auditoría de Onboarding
Para cada problema: Hallazgo → Impacto → Recomendación → Prioridad

### Diseño del Flujo de Onboarding
- Objetivo de activación
- Flujo paso a paso
- Items de la lista de verificación (si aplica)
- Copy para estados vacíos
- Disparadores de secuencia de email
- Plan de métricas

---

## Patrones Comunes por Tipo de Producto

| Tipo de Producto | Pasos Clave |
|------------------|------------|
| B2B SaaS | Asistente de configuración → Primera acción de valor → Invitar al equipo → Configuración profunda |
| Marketplace | Completar perfil → Explorar → Primera transacción → Bucle de repetición |
| App Móvil | Permisos → Victoria rápida → Configuración de push → Bucle de hábito |
| Plataforma de Contenido | Seguir/personalizar → Consumir → Crear → Participar |

---

## Ideas de Experimentos

Al recomendar experimentos, considerar pruebas para:
- Simplificación del flujo (número de pasos, orden)
- Mecánicas de progreso y motivación
- Personalización por rol u objetivo
- Disponibilidad de soporte y ayuda

**Para ideas completas de experimentos**: Ver [references/experiments.md](references/experiments.md)

---

## Preguntas Específicas de la Tarea

1. ¿Qué acción se correlaciona más con la retención?
2. ¿Qué sucede inmediatamente después del registro?
3. ¿Dónde abandonan actualmente los usuarios?
4. ¿Cuál es tu objetivo de tasa de activación?
5. ¿Tienes análisis de cohorte de usuarios exitosos vs. cancelados?

---

## Habilidades Relacionadas

- **signup-flow-cro**: Para optimizar el registro antes del onboarding
- **email-sequence**: Para la serie de email de onboarding
- **paywall-upgrade-cro**: Para convertir a pagado durante/después del onboarding
- **ab-test-setup**: Para probar cambios de onboarding
