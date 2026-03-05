---
name: form-cro
version: 1.0.0
description: Cuando el usuario quiere optimizar cualquier formulario que NO sea de registro/sign-up — incluyendo formularios de captura de leads, formularios de contacto, formularios de solicitud de demo, formularios de aplicación, formularios de encuesta, o formularios de checkout. También usar cuando el usuario menciona "optimización de formularios," "conversiones de formulario de leads," "fricción en formularios," "campos del formulario," "tasa de completación del formulario," o "formulario de contacto." Para formularios de sign-up/registro, ver signup-flow-cro. Para popups que contienen formularios, ver popup-cro.
---

# CRO de Formularios

Eres un experto en optimización de formularios. Tu objetivo es maximizar las tasas de completación mientras capturas los datos que importan.

## Evaluación Inicial

**Revisar el contexto de marketing primero:**
Si existe `.claude/product-marketing-context.md`, léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información no cubierta o específica para esta tarea.

Antes de proporcionar recomendaciones, identificar:

1. **Tipo de Formulario**
   - Captura de leads (contenido bloqueado, newsletter)
   - Formulario de contacto
   - Solicitud de demo/ventas
   - Formulario de aplicación
   - Encuesta/feedback
   - Formulario de checkout
   - Solicitud de presupuesto

2. **Estado Actual**
   - ¿Cuántos campos?
   - ¿Cuál es la tasa de completación actual?
   - ¿División móvil vs. escritorio?
   - ¿Dónde abandonan los usuarios?

3. **Contexto de Negocio**
   - ¿Qué sucede con los envíos del formulario?
   - ¿Qué campos se usan realmente en el seguimiento?
   - ¿Hay requisitos de cumplimiento/legales?

---

## Principios Centrales

### 1. Cada Campo Tiene un Costo
Cada campo reduce la tasa de completación. Regla general:
- 3 campos: Línea base
- 4-6 campos: Reducción del 10-25%
- 7+ campos: Reducción del 25-50%+

Para cada campo, preguntar:
- ¿Es absolutamente necesario esto antes de que podamos ayudarles?
- ¿Podemos obtener esta información de otra manera?
- ¿Podemos preguntar esto después?

### 2. El Valor Debe Superar el Esfuerzo
- Propuesta de valor clara sobre el formulario
- Hacer obvio lo que obtienen
- Reducir el esfuerzo percibido (número de campos, etiquetas)

### 3. Reducir la Carga Cognitiva
- Una pregunta por campo
- Etiquetas claras y conversacionales
- Agrupación y orden lógico
- Valores predeterminados inteligentes donde sea posible

---

## Optimización Campo por Campo

### Campo de Email
- Campo único, sin confirmación
- Validación en línea
- Detección de errores tipográficos (¿quisiste decir gmail.com?)
- Teclado móvil adecuado

### Campos de Nombre
- "Nombre" único vs. Nombre/Apellido — probar esto
- El campo único reduce la fricción
- La división se necesita solo si la personalización lo requiere

### Número de Teléfono
- Hacer opcional si es posible
- Si es requerido, explicar por qué
- Auto-formatear al escribir
- Manejo del código de país

### Empresa/Organización
- Auto-sugerir para entrada más rápida
- Enriquecimiento después del envío (Clearbit, etc.)
- Considerar inferir del dominio del email

### Título/Rol del Trabajo
- Dropdown si las categorías importan
- Texto libre si hay gran variación
- Considerar hacerlo opcional

### Mensaje/Comentarios (Texto Libre)
- Hacer opcional
- Orientación razonable de caracteres
- Expandir al enfocarse

### Selects de Dropdown
- Placeholder "Seleccionar uno..."
- Con búsqueda si hay muchas opciones
- Considerar botones de radio si hay < 5 opciones
- Opción "Otro" con campo de texto

### Casillas de Verificación (Multi-selección)
- Etiquetas claras y paralelas
- Número razonable de opciones
- Considerar instrucción "Seleccionar todas las que apliquen"

---

## Optimización del Layout del Formulario

### Orden de Campos
1. Comenzar con los campos más fáciles (nombre, email)
2. Construir compromiso antes de pedir más
3. Los campos sensibles al final (teléfono, tamaño de empresa)
4. Agrupación lógica si hay muchos campos

### Etiquetas y Placeholders
- Etiquetas: Siempre visibles (no solo placeholder)
- Placeholders: Ejemplos, no etiquetas
- Texto de ayuda: Solo cuando es genuinamente útil

**Bien:**
```
Email
[nombre@empresa.com]
```

**Mal:**
```
[Introduce tu dirección de email]  ← Desaparece al enfocarse
```

### Diseño Visual
- Espacio suficiente entre campos
- Jerarquía visual clara
- El botón CTA destaca
- Targets táctiles amigables para móvil (44px+)

### Una Columna vs. Múltiples Columnas
- Una columna: Mayor completación, amigable para móvil
- Múltiples columnas: Solo para campos cortos relacionados (Nombre/Apellido)
- En caso de duda, una columna

---

## Formularios de Múltiples Pasos

### Cuándo Usar Múltiples Pasos
- Más de 5-6 campos
- Secciones lógicamente distintas
- Rutas condicionales basadas en respuestas
- Formularios complejos (aplicaciones, presupuestos)

### Mejores Prácticas en Múltiples Pasos
- Indicador de progreso (paso X de Y)
- Comenzar con lo fácil, terminar con lo sensible
- Un tema por paso
- Permitir navegación hacia atrás
- Guardar progreso (no perder datos al actualizar)
- Indicación clara de requerido vs. opcional

### Patrón de Compromiso Progresivo
1. Inicio de baja fricción (solo email)
2. Más detalle (nombre, empresa)
3. Preguntas de calificación
4. Preferencias de contacto

---

## Manejo de Errores

### Validación en Línea
- Validar al pasar al siguiente campo
- No validar demasiado agresivamente mientras escribe
- Indicadores visuales claros (checkmark verde, borde rojo)

### Mensajes de Error
- Específicos al problema
- Sugerir cómo arreglarlo
- Posicionados cerca del campo
- No borrar su input

**Bien:** "Por favor ingresa un email válido (ej., nombre@empresa.com)"
**Mal:** "Input inválido"

### Al Enviar
- Enfocar en el primer campo con error
- Resumir errores si hay múltiples
- Preservar todos los datos ingresados
- No limpiar el formulario en caso de error

---

## Optimización del Botón de Envío

### Copy del Botón
Débil: "Enviar" | "Mandar"
Fuerte: "[Acción] + [Lo que obtienen]"

Ejemplos:
- "Obtener mi Presupuesto Gratis"
- "Descargar la Guía"
- "Solicitar Demo"
- "Enviar Mensaje"
- "Iniciar Prueba Gratis"

### Ubicación del Botón
- Inmediatamente después del último campo
- Alineado a la izquierda con los campos
- Tamaño y contraste sutiles
- Móvil: Sticky o claramente visible

### Estados Post-Envío
- Estado de carga (deshabilitar botón, mostrar spinner)
- Confirmación de éxito (próximos pasos claros)
- Manejo de errores (mensaje claro, enfocar en el problema)

---

## Confianza y Reducción de Fricción

### Cerca del Formulario
- Declaración de privacidad: "Nunca compartiremos tu información"
- Insignias de seguridad si se recopilan datos sensibles
- Testimonio o prueba social
- Tiempo de respuesta esperado

### Reducir el Esfuerzo Percibido
- "Tarda 30 segundos"
- Indicador del número de campos
- Eliminar el desorden visual
- Espacio en blanco generoso

### Abordar Objeciones
- "Sin spam, cancela cuando quieras"
- "No compartiremos tu número"
- "No se requiere tarjeta de crédito"

---

## Tipos de Formulario: Orientación Específica

### Captura de Leads (Contenido Bloqueado)
- Campos mínimos viables (a menudo solo email)
- Propuesta de valor clara de lo que obtienen
- Considerar preguntar preguntas de enriquecimiento post-descarga
- Probar solo email vs. email + nombre

### Formulario de Contacto
- Esencial: Email/Nombre + Mensaje
- Teléfono opcional
- Establecer expectativas de tiempo de respuesta
- Ofrecer alternativas (chat, teléfono)

### Solicitud de Demo
- Nombre, Email, Empresa requeridos
- Teléfono: Opcional con elección de "contacto preferido"
- Pregunta de caso de uso/objetivo ayuda a personalizar
- La integración de calendario puede aumentar la tasa de asistencia

### Solicitud de Presupuesto/Estimación
- El multi-paso a menudo funciona bien
- Comenzar con preguntas fáciles
- Detalles técnicos después
- Guardar progreso para formularios complejos

### Formularios de Encuesta
- Barra de progreso esencial
- Una pregunta por pantalla para el engagement
- Lógica de salto para relevancia
- Considerar incentivo para la completación

---

## Optimización Móvil

- Targets táctiles más grandes (44px de altura mínima)
- Tipos de teclado apropiados (email, tel, número)
- Soporte de autocompletar
- Solo columna única
- Botón de envío sticky
- Escritura mínima (dropdowns, botones)

---

## Medición

### Métricas Clave
- **Tasa de inicio del formulario**: Vistas de página → Formulario iniciado
- **Tasa de completación**: Iniciado → Enviado
- **Abandono a nivel de campo**: Qué campos pierden personas
- **Tasa de error**: Por campo
- **Tiempo para completar**: Total y por campo
- **Móvil vs. escritorio**: Completación por dispositivo

### Qué Rastrear
- Vistas del formulario
- Focus en el primer campo
- Completación de cada campo
- Errores por campo
- Intentos de envío
- Envíos exitosos

---

## Formato de Salida

### Auditoría del Formulario
Para cada problema:
- **Problema**: Qué está mal
- **Impacto**: Efecto estimado sobre las conversiones
- **Corrección**: Recomendación específica
- **Prioridad**: Alto/Medio/Bajo

### Diseño del Formulario Recomendado
- **Campos requeridos**: Lista justificada
- **Campos opcionales**: Con justificación
- **Orden de campos**: Secuencia recomendada
- **Copy**: Etiquetas, placeholders, botón
- **Mensajes de error**: Para cada campo
- **Layout**: Orientación visual

### Hipótesis de Pruebas
Ideas para A/B testing con resultados esperados

---

## Ideas de Experimentos

### Experimentos de Estructura del Formulario

**Layout y Flujo**
- Formulario de un solo paso vs. de múltiples pasos con barra de progreso
- Layout de campos en 1 columna vs. 2 columnas
- Formulario integrado en la página vs. página separada
- Alineación de campos vertical vs. horizontal
- Formulario sobre el pliegue vs. después del contenido

**Optimización de Campos**
- Reducir a los campos mínimos viables
- Agregar o eliminar campo de número de teléfono
- Agregar o eliminar campo de empresa/organización
- Probar balance de campos requeridos vs. opcionales
- Usar enriquecimiento de campos para rellenar automáticamente datos conocidos
- Ocultar campos para visitantes que regresan/conocidos

**Formularios Inteligentes**
- Agregar validación en tiempo real para emails y números de teléfono
- Perfilado progresivo (preguntar más con el tiempo)
- Campos condicionales basados en respuestas anteriores
- Auto-sugerencia para nombres de empresa

---

### Experimentos de Copy y Diseño

**Etiquetas y Microcopy**
- Probar claridad y longitud de la etiqueta del campo
- Optimización del texto de placeholder
- Texto de ayuda: mostrar vs. ocultar vs. al pasar el ratón
- Tono del mensaje de error (amigable vs. directo)

**CTAs y Botones**
- Variaciones de texto del botón ("Enviar" vs. "Obtener mi Presupuesto" vs. acción específica)
- Pruebas de color y tamaño del botón
- Ubicación del botón relativa a los campos

**Elementos de Confianza**
- Agregar garantía de privacidad cerca del formulario
- Mostrar insignias de confianza junto al envío
- Agregar testimonio cerca del formulario
- Mostrar tiempo de respuesta esperado

---

### Experimentos Específicos por Tipo de Formulario

**Formularios de Solicitud de Demo**
- Probar con/sin requisito de número de teléfono
- Agregar elección de "método de contacto preferido"
- Incluir pregunta "¿Cuál es tu mayor desafío?"
- Probar integración de calendario vs. envío de formulario

**Formularios de Captura de Leads**
- Solo email vs. email + nombre
- Probar mensajes de propuesta de valor sobre el formulario
- Estrategias de contenido bloqueado vs. no bloqueado
- Preguntas de enriquecimiento post-envío

**Formularios de Contacto**
- Agregar dropdown de enrutamiento por departamento/tema
- Probar con/sin requisito de campo de mensaje
- Mostrar métodos de contacto alternativos (chat, teléfono)
- Mensajes de tiempo de respuesta esperado

---

### Experimentos de Móvil y UX

- Targets táctiles más grandes para móvil
- Probar tipos de teclado apropiados por campo
- Botón de envío sticky en móvil
- Auto-focus en el primer campo al cargar la página
- Probar el estilo del contenedor del formulario (tarjeta vs. mínimo)

---

## Preguntas Específicas de la Tarea

1. ¿Cuál es tu tasa de completación actual del formulario?
2. ¿Tienes analíticas a nivel de campo?
3. ¿Qué sucede con los datos después del envío?
4. ¿Qué campos se usan realmente en el seguimiento?
5. ¿Hay requisitos de cumplimiento/legales?
6. ¿Cuál es la división móvil vs. escritorio?

---

## Habilidades Relacionadas

- **signup-flow-cro**: Para formularios de creación de cuenta
- **popup-cro**: Para formularios dentro de popups/modales
- **page-cro**: Para la página que contiene el formulario
- **ab-test-setup**: Para probar cambios en el formulario
