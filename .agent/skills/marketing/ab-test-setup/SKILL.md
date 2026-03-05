---
name: ab-test-setup
version: 1.0.0
description: Cuando el usuario quiere planear, diseñar o implementar una prueba A/B o experimento. También usar cuando el usuario menciona "prueba A/B," "split test," "experimento," "probar este cambio," "variante," "prueba multivariable," "hipótesis," "A/B test," "split test," "experiment," "test this change," o "multivariate test." Para implementación de seguimiento, ver analytics-tracking.
---

# Configuración de Pruebas A/B

Eres experto en experimentación y pruebas A/B. Tu objetivo es ayudar a diseñar pruebas que produzcan resultados estadísticamente válidos y accionables.

## Evaluación Inicial

**Revisar el contexto de marketing primero:**
Si existe `.claude/product-marketing-context.md`, léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información que no esté cubierta o que sea específica para esta tarea.

Antes de diseñar una prueba, entiende:

1. **Contexto de la prueba** — ¿Qué quieres mejorar? ¿Qué cambio estás considerando?
2. **Estado actual** — ¿Cuál es la tasa de conversión base? ¿Cuál es el volumen de tráfico actual?
3. **Restricciones** — ¿Complejidad técnica? ¿Plazo de tiempo? ¿Herramientas disponibles?

---

## Principios Fundamentales

### 1. Empieza con una Hipótesis
- No solo "veamos qué pasa"
- Predicción específica del resultado
- Basada en razonamiento o datos

### 2. Prueba una Sola Cosa
- Una variable por prueba
- De lo contrario no sabrás qué funcionó

### 3. Rigor Estadístico
- Determina el tamaño de muestra de antemano
- No mires los resultados antes de tiempo y detengas la prueba anticipadamente
- Comprométete con la metodología

### 4. Mide lo que Importa
- Métrica principal vinculada al valor del negocio
- Métricas secundarias para contexto
- Métricas de protección para evitar daños

---

## Marco de Hipótesis

### Estructura

```
Porque [observación/dato],
creemos que [cambio]
causará [resultado esperado]
para [audiencia].
Sabremos que es verdad cuando [métricas].
```

### Ejemplo

**Débil**: "Cambiar el color del botón podría aumentar los clics."

**Fuerte**: "Porque los usuarios reportan dificultad para encontrar el CTA (según mapas de calor y comentarios), creemos que hacer el botón más grande y usar un color con mayor contraste aumentará los clics en el CTA en 15%+ para visitantes nuevos. Mediremos la tasa de clics desde la vista de página hasta el inicio del registro."

---

## Tipos de Prueba

| Tipo | Descripción | Tráfico necesario |
|------|-------------|-------------------|
| A/B | Dos versiones, un solo cambio | Moderado |
| A/B/n | Múltiples variantes | Alto |
| MVT | Múltiples cambios en combinaciones | Muy alto |
| URL dividida | URLs diferentes para cada variante | Moderado |

---

## Tamaño de Muestra

### Referencia Rápida

| Línea base | Mejora 10% | Mejora 20% | Mejora 50% |
|------------|------------|------------|------------|
| 1% | 150k/variante | 39k/variante | 6k/variante |
| 3% | 47k/variante | 12k/variante | 2k/variante |
| 5% | 27k/variante | 7k/variante | 1.2k/variante |
| 10% | 12k/variante | 3k/variante | 550/variante |

**Calculadoras:**
- [Evan Miller's](https://www.evanmiller.org/ab-testing/sample-size.html)
- [Optimizely's](https://www.optimizely.com/sample-size-calculator/)

**Para tablas detalladas de tamaño de muestra y cálculos de duración**: Ver [references/sample-size-guide.md](references/sample-size-guide.md)

---

## Selección de Métricas

### Métrica Principal
- La métrica más importante
- Directamente vinculada a la hipótesis
- La que usarás para concluir la prueba

### Métricas Secundarias
- Apoyan la interpretación de la métrica principal
- Explican por qué/cómo funcionó el cambio

### Métricas de Protección
- Lo que no debe empeorar
- Detener la prueba si hay resultados significativamente negativos

### Ejemplo: Prueba en Página de Precios
- **Principal**: Tasa de selección de plan
- **Secundaria**: Tiempo en página, distribución de planes
- **Protección**: Tickets de soporte, tasa de reembolsos

---

## Diseño de Variantes

### Qué Variar

| Categoría | Ejemplos |
|-----------|----------|
| Titulares/Texto | Ángulo del mensaje, propuesta de valor, especificidad, tono |
| Diseño Visual | Maquetación, color, imágenes, jerarquía |
| CTA | Texto del botón, tamaño, posición, cantidad |
| Contenido | Información incluida, orden, cantidad, prueba social |

### Mejores Prácticas
- Un cambio único y significativo
- Lo suficientemente audaz para marcar una diferencia
- Fiel a la hipótesis

---

## Distribución de Tráfico

| Enfoque | División | Cuándo usar |
|---------|---------|-------------|
| Estándar | 50/50 | Por defecto para A/B |
| Conservador | 90/10, 80/20 | Limitar el riesgo de una variante negativa |
| Progresivo | Empezar pequeño, aumentar | Mitigar riesgo técnico |

**Consideraciones:**
- Consistencia: Los usuarios ven la misma variante al regresar
- Exposición equilibrada a lo largo del día/semana

---

## Implementación

### Del Lado del Cliente
- JavaScript modifica la página después de la carga
- Rápido de implementar, puede causar parpadeo
- Herramientas: PostHog, Optimizely, VWO

### Del Lado del Servidor
- La variante se determina antes de renderizar
- Sin parpadeo, requiere trabajo de desarrollo
- Herramientas: PostHog, LaunchDarkly, Split

---

## Ejecución de la Prueba

### Lista de Verificación Previa al Lanzamiento
- [ ] Hipótesis documentada
- [ ] Métrica principal definida
- [ ] Tamaño de muestra calculado
- [ ] Variantes implementadas correctamente
- [ ] Seguimiento verificado
- [ ] QA completado en todas las variantes

### Durante la Prueba

**HACER:**
- Monitorear problemas técnicos
- Verificar la calidad del segmento
- Documentar factores externos

**NO HACER:**
- Mirar los resultados antes de tiempo y detener la prueba
- Hacer cambios a las variantes
- Agregar tráfico de nuevas fuentes

### El Problema de Mirar Antes de Tiempo
Revisar los resultados antes de alcanzar el tamaño de muestra y detener la prueba anticipadamente genera falsos positivos y decisiones equivocadas. Comprométete con el tamaño de muestra de antemano y confía en el proceso.

---

## Análisis de Resultados

### Significancia Estadística
- 95% de confianza = valor p < 0.05
- Significa que hay <5% de probabilidad de que el resultado sea aleatorio
- No es una garantía — solo un umbral

### Lista de Verificación para el Análisis

1. **¿Se alcanzó el tamaño de muestra?** Si no, el resultado es preliminar
2. **¿Es estadísticamente significativo?** Verificar intervalos de confianza
3. **¿El tamaño del efecto es significativo?** Comparar con MDE, proyectar impacto
4. **¿Las métricas secundarias son consistentes?** ¿Apoyan la principal?
5. **¿Preocupaciones sobre métricas de protección?** ¿Algo empeoró?
6. **¿Diferencias por segmento?** ¿Móvil vs. escritorio? ¿Nuevos vs. recurrentes?

### Interpretación de Resultados

| Resultado | Conclusión |
|-----------|------------|
| Ganador significativo | Implementar la variante |
| Perdedor significativo | Mantener el control, aprender por qué |
| Sin diferencia significativa | Se necesita más tráfico o una prueba más audaz |
| Señales mixtas | Profundizar, quizás segmentar |

---

## Documentación

Documenta cada prueba con:
- Hipótesis
- Variantes (con capturas de pantalla)
- Resultados (muestra, métricas, significancia)
- Decisión y aprendizajes

**Para plantillas**: Ver [references/test-templates.md](references/test-templates.md)

---

## Errores Comunes

### Diseño de la Prueba
- Probar un cambio demasiado pequeño (indetectable)
- Probar demasiadas cosas a la vez (no se puede aislar)
- Sin hipótesis clara

### Ejecución
- Detener la prueba antes de tiempo
- Cambiar cosas en medio de la prueba
- No verificar la implementación

### Análisis
- Ignorar los intervalos de confianza
- Seleccionar segmentos convenientes
- Sobreinterpretar resultados no concluyentes

---

## Preguntas Específicas de la Tarea

1. ¿Cuál es tu tasa de conversión actual?
2. ¿Cuánto tráfico recibe esta página?
3. ¿Qué cambio estás considerando y por qué?
4. ¿Cuál es la mejora mínima que vale la pena detectar?
5. ¿Qué herramientas tienes disponibles para las pruebas?
6. ¿Has probado en esta área antes?

---

## Habilidades Relacionadas

- **page-cro**: Para generar ideas de prueba basadas en principios de CRO
- **analytics-tracking**: Para configurar la medición de la prueba
- **copywriting**: Para crear el texto de la variante
