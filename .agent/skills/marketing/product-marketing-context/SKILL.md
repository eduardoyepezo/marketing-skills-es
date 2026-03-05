---
name: product-marketing-context
version: 1.0.0
description: "Cuando el usuario quiere crear o actualizar su documento de contexto de marketing del producto. También usar cuando el usuario menciona 'contexto del producto,' 'contexto de marketing,' 'configurar contexto,' 'posicionamiento,' o quiere evitar repetir información fundamental en las tareas de marketing. Crea `.claude/product-marketing-context.md` que otras habilidades de marketing referencian."
---

# Contexto de Marketing del Producto

Ayudas a los usuarios a crear y mantener un documento de contexto de marketing del producto. Esto captura información fundamental de posicionamiento y mensajes que otras habilidades de marketing referencian, para que los usuarios no tengan que repetirse.

El documento se almacena en `.claude/product-marketing-context.md`.

## Flujo de Trabajo

### Paso 1: Verificar el Contexto Existente

Primero, verificar si `.claude/product-marketing-context.md` ya existe.

**Si existe:**
- Leerlo y resumir lo que está capturado
- Preguntar qué secciones quieren actualizar
- Solo recopilar información para esas secciones

**Si no existe, ofrecer dos opciones:**

1. **Borrador automático del código fuente** (recomendado): Estudiarás el repositorio—README, landing pages, copy de marketing, package.json, etc.—y redactarás una versión 1 del documento de contexto. El usuario luego revisa, corrige y llena los vacíos. Esto es más rápido que comenzar desde cero.

2. **Empezar desde cero**: Recorrer cada sección conversacionalmente, recopilando información una sección a la vez.

La mayoría de los usuarios prefieren la opción 1. Después de presentar el borrador, preguntar: "¿Qué necesita corrección? ¿Qué falta?"

### Paso 2: Recopilar Información

**Si se hace borrador automático:**
1. Leer el código fuente: README, landing pages, copy de marketing, páginas sobre nosotros, meta descripciones, package.json, cualquier documento existente
2. Borradorar todas las secciones basándose en lo que encuentres
3. Presentar el borrador y preguntar qué necesita corrección o está faltando
4. Iterar hasta que el usuario esté satisfecho

**Si se empieza desde cero:**
Recorrer cada sección conversacionalmente, una a la vez. No lanzar todas las preguntas de golpe.

Para cada sección:
1. Explicar brevemente qué estás capturando
2. Hacer preguntas relevantes
3. Confirmar precisión
4. Pasar a la siguiente

**Importante:** Empujar por el lenguaje textual del cliente. Las frases exactas son más valiosas que las descripciones pulidas.

---

## Secciones a Capturar

### 1. Descripción General del Producto
- Descripción en una línea
- Qué hace (2-3 oraciones)
- Categoría del producto (en qué "estante" estás—cómo te buscan los clientes)
- Tipo de producto (SaaS, marketplace, e-commerce, servicio, etc.)
- Modelo de negocio y precios

### 2. Audiencia Objetivo
- Tipo de empresa objetivo (industria, tamaño, etapa)
- Tomadores de decisiones objetivo (roles, departamentos)
- Caso de uso principal (el problema principal que resuelves)
- Trabajos a realizar (2-3 cosas para las que los clientes te "contratan")
- Casos de uso o escenarios específicos

### 3. Personas (Solo B2B)
Si múltiples partes interesadas están involucradas en la compra, capturar para cada una:
- Usuario, Campeón, Tomador de Decisiones, Comprador Financiero, Influenciador Técnico
- Lo que le importa a cada uno, su desafío y el valor que les prometes

### 4. Problemas y Puntos de Dolor
- Desafío central que enfrentan los clientes antes de encontrarte
- Por qué las soluciones actuales son insuficientes
- Lo que les cuesta (tiempo, dinero, oportunidades)
- Tensión emocional (estrés, miedo, duda)

### 5. Panorama Competitivo
- **Competidores directos**: Misma solución, mismo problema (ej., Calendly vs SavvyCal)
- **Competidores secundarios**: Solución diferente, mismo problema (ej., Calendly vs Superhuman scheduling)
- **Competidores indirectos**: Enfoque conflictivo (ej., Calendly vs asistente personal)
- Cómo cada uno falla para los clientes

### 6. Diferenciación
- Diferenciadores clave (capacidades que carecen las alternativas)
- Cómo resuelves de manera diferente
- Por qué eso es mejor (beneficios)
- Por qué los clientes te eligen sobre las alternativas

### 7. Objeciones y Anti-Personas
- Las 3 principales objeciones escuchadas en ventas y cómo abordarlas
- Quién NO es un buen cliente (anti-persona)

### 8. Dinámica de Cambio
Las Cuatro Fuerzas del JTBD:
- **Empuje**: Qué frustraciones los alejan de la solución actual
- **Atracción**: Qué los atrae hacia ti
- **Hábito**: Qué los mantiene atrapados con el enfoque actual
- **Ansiedad**: Qué les preocupa sobre cambiar

### 9. Lenguaje del Cliente
- Cómo los clientes describen el problema (textualmente)
- Cómo describen tu solución (textualmente)
- Palabras/frases a usar
- Palabras/frases a evitar
- Glosario de términos específicos del producto

### 10. Voz de Marca
- Tono (profesional, casual, juguetón, etc.)
- Estilo de comunicación (directo, conversacional, técnico)
- Personalidad de marca (3-5 adjetivos)

### 11. Puntos de Prueba
- Métricas o resultados clave a citar
- Clientes/logos notables
- Fragmentos de testimonios
- Temas de valor principales y evidencia de apoyo

### 12. Objetivos
- Objetivo de negocio principal
- Acción de conversión clave (lo que quieres que la gente haga)
- Métricas actuales (si se conocen)

---

## Paso 3: Crear el Documento

Después de recopilar información, crear `.claude/product-marketing-context.md` con esta estructura:

```markdown
# Contexto de Marketing del Producto

*Última actualización: [fecha]*

## Descripción General del Producto
**Descripción en una línea:**
**Qué hace:**
**Categoría del producto:**
**Tipo de producto:**
**Modelo de negocio:**

## Audiencia Objetivo
**Empresas objetivo:**
**Tomadores de decisiones:**
**Caso de uso principal:**
**Trabajos a realizar:**
-
**Casos de uso:**
-

## Personas
| Persona | Le importa | Desafío | Valor que prometemos |
|---------|-------------|-----------|---------------------|
| | | | |

## Problemas y Puntos de Dolor
**Problema central:**
**Por qué las alternativas son insuficientes:**
-
**Lo que les cuesta:**
**Tensión emocional:**

## Panorama Competitivo
**Directo:** [Competidor] — falla porque...
**Secundario:** [Enfoque] — falla porque...
**Indirecto:** [Alternativa] — falla porque...

## Diferenciación
**Diferenciadores clave:**
-
**Cómo lo hacemos diferente:**
**Por qué eso es mejor:**
**Por qué los clientes nos eligen:**

## Objeciones
| Objeción | Respuesta |
|-----------|----------|
| | |

**Anti-persona:**

## Dinámica de Cambio
**Empuje:**
**Atracción:**
**Hábito:**
**Ansiedad:**

## Lenguaje del Cliente
**Cómo describen el problema:**
- "[textual]"
**Cómo nos describen:**
- "[textual]"
**Palabras a usar:**
**Palabras a evitar:**
**Glosario:**
| Término | Significado |
|------|---------| 
| | |

## Voz de Marca
**Tono:**
**Estilo:**
**Personalidad:**

## Puntos de Prueba
**Métricas:**
**Clientes:**
**Testimonios:**
> "[cita]" — [quién]
**Temas de valor:**
| Tema | Prueba |
|-------|-------|
| | |

## Objetivos
**Objetivo de negocio:**
**Acción de conversión:**
**Métricas actuales:**
```

---

## Paso 4: Confirmar y Guardar

- Mostrar el documento completado
- Preguntar si algo necesita ajuste
- Guardar en `.claude/product-marketing-context.md`
- Decirles: "Otras habilidades de marketing ahora usarán este contexto automáticamente. Ejecuta `/product-marketing-context` en cualquier momento para actualizarlo."

---

## Consejos

- **Sé específico**: Preguntar "¿Cuál es la #1 frustración que los lleva a ti?" no "¿Qué problema resuelven?"
- **Captura palabras exactas**: El lenguaje del cliente supera a las descripciones pulidas
- **Pide ejemplos**: "¿Puedes darme un ejemplo?" desbloquea mejores respuestas
- **Valida mientras avanzas**: Resumir cada sección y confirmar antes de seguir
- **Omite lo que no aplica**: No todos los productos necesitan todas las secciones (ej., Personas para B2C)
