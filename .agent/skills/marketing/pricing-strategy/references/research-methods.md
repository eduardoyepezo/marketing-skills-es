# Métodos de Investigación de Precios

## Contenidos
- Medidor de Sensibilidad al Precio de Van Westendorp (Las Cuatro Preguntas, Cómo Analizar, Consejos de Encuesta, Resultado de Muestra)
- Análisis MaxDiff (Cómo Funciona, Pregunta de Encuesta de Ejemplo, Analizando Resultados, Usando MaxDiff para el Packaging)
- Encuestas de Disposición a Pagar
- Análisis de Correlación Uso-Valor

## Medidor de Sensibilidad al Precio de Van Westendorp

La encuesta de Van Westendorp identifica el rango de precio aceptable para tu producto.

### Las Cuatro Preguntas

Hacer a cada encuestado:
1. "¿A qué precio considerarías que [producto] es tan caro que no lo comprarías?" (Demasiado caro)
2. "¿A qué precio considerarías que [producto] tiene un precio tan bajo que cuestionarías su calidad?" (Demasiado barato)
3. "¿A qué precio comenzarías a considerar que [producto] está caro, pero aún podrías considerarlo?" (Caro/en el lado alto)
4. "¿A qué precio considerarías que [producto] es una ganga — una excelente compra por el dinero?" (Barato/buen valor)

### Cómo Analizar

1. Trazar distribuciones acumuladas para cada pregunta
2. Encontrar las intersecciones:
   - **Punto de Baratura Marginal (PMC):** "Demasiado barato" cruza "Caro"
   - **Punto de Carestía Marginal (PME):** "Demasiado caro" cruza "Barato"
   - **Punto de Precio Óptimo (OPP):** "Demasiado barato" cruza "Demasiado caro"
   - **Punto de Precio de Indiferencia (IDP):** "Caro" cruza "Barato"

**El rango de precio aceptable:** PMC a PME
**Zona de precio óptima:** Entre OPP e IDP

### Consejos de Encuesta
- Se necesitan 100-300 encuestados para datos confiables
- Segmentar por persona (diferente disposición a pagar)
- Usar descripciones del producto realistas
- Considerar agregar preguntas de intención de compra

### Resultado de Muestra

```
Resultados del Análisis de Sensibilidad al Precio:
─────────────────────────────────
Punto de Baratura Marginal:          $29/mes
Punto de Precio Óptimo:              $49/mes
Punto de Precio de Indiferencia:     $59/mes
Punto de Carestía Marginal:          $79/mes

Rango recomendado: $49-59/mes
Precio actual: $39/mes (por debajo del óptimo)
Oportunidad: Aumento de precio del 25-50% sin impacto significativo en la demanda
```

---

## Análisis MaxDiff (Escalamiento Mejor-Peor)

El análisis MaxDiff identifica qué características más valoran los clientes, informando las decisiones de packaging.

### Cómo Funciona

1. Listar 8-15 funciones que podrías incluir
2. Mostrar a los encuestados conjuntos de 4-5 funciones a la vez
3. Preguntar: "¿Cuál es MÁS importante? ¿Cuál es MENOS importante?"
4. Repetir a través de múltiples conjuntos hasta que se comparen todas las funciones
5. El análisis estadístico produce puntuaciones de importancia

### Pregunta de Encuesta de Ejemplo

```
¿Cuál función es MÁS importante para ti?
¿Cuál función es MENOS importante para ti?

□ Proyectos ilimitados
□ Marca personalizada
□ Soporte prioritario
□ Acceso API
□ Análisis avanzado
```

### Analizando Resultados

Las funciones se clasifican por puntuación de utilidad:
- Alta utilidad = Imprescindible (incluir en el nivel base)
- Utilidad media = Diferenciador (usar para separación de nivel)
- Baja utilidad = Agradable de tener (nivel premium o eliminar)

### Usando MaxDiff para el Packaging

| Puntuación de Utilidad | Decisión de Packaging |
|---------------|-------------------|
| Top 20% | Incluir en todos los niveles (tabla de requisitos) |
| 20-50% | Usar para diferenciar niveles |
| 50-80% | Solo en niveles superiores |
| Bottom 20% | Considerar eliminar o como complemento premium |

---

## Encuestas de Disposición a Pagar

**Método directo (simple pero sesgado):**
"¿Cuánto pagarías por [producto]?"

**Mejor: Método Gabor-Granger:**
"¿Comprarías [producto] a [$X]?" (Sí/No)
Variar el precio entre encuestados para construir una curva de demanda.

**Aún mejor: Análisis Conjoint:**
Mostrar paquetes de productos a diferentes precios
Los encuestados eligen la opción preferida
El análisis estadístico revela la sensibilidad al precio por función

---

## Análisis de Correlación Uso-Valor

### 1. Instrumentar los datos de uso
Rastrear cómo los clientes usan tu producto:
- Frecuencia de uso de función
- Métricas de volumen (usuarios, registros, llamadas API)
- Métricas de resultado (ingresos generados, tiempo ahorrado)

### 2. Correlacionar con el éxito del cliente
- ¿Qué patrones de uso predicen la retención?
- ¿Qué patrones de uso predicen la expansión?
- ¿Qué clientes pagan más, y por qué?

### 3. Identificar umbrales de valor
- ¿A qué nivel de uso los clientes "lo entienden"?
- ¿A qué nivel de uso se expanden?
- ¿A qué nivel de uso debería aumentar el precio?

### Análisis de Ejemplo

```
Análisis de Correlación Uso-Valor:
─────────────────────────────────
Segmento: Clientes de alto LTV (>$10k ARR)
Usuarios activos mensuales promedio: 15
Proyectos promedio: 8
Integraciones promedio: 4

Segmento: Clientes que cancelaron
Usuarios activos mensuales promedio: 3
Proyectos promedio: 2
Integraciones promedio: 0

Insight: El valor se correlaciona con la adopción del equipo (usuarios)
        y la profundidad de uso (integraciones)

Recomendación: Precio por usuario, restringir integraciones a niveles superiores
```
