# Guía de Tamaño de Muestra

Referencia para calcular tamaños de muestra y duración de pruebas.

## Contenidos
- Fundamentos del Tamaño de Muestra (inputs requeridos, qué significan)
- Tablas de Referencia Rápida de Tamaño de Muestra
- Calculadora de Duración (fórmula, ejemplos, reglas de duración mínima, directrices de duración máxima)
- Calculadoras en Línea
- Ajuste para Múltiples Variantes
- Errores Comunes con el Tamaño de Muestra
- Cuando los Requisitos de Tamaño de Muestra son Demasiado Altos
- Pruebas Secuenciales
- Marco de Decisión Rápida

## Fundamentos del Tamaño de Muestra

### Inputs Requeridos

1. **Tasa de conversión base**: Tu tasa actual
2. **Efecto mínimo detectable (MDE)**: El cambio más pequeño que vale la pena detectar
3. **Nivel de significancia estadística**: Usualmente 95% (α = 0.05)
4. **Potencia estadística**: Usualmente 80% (β = 0.20)

### Qué Significan

**Tasa de conversión base**: Si tu página convierte al 5%, esa es tu base.

**MDE (Efecto Mínimo Detectable)**: La mejora más pequeña que te importa detectar. Establecer esto basándose en:
- Impacto empresarial (¿es significativo un aumento del 5%?)
- Costo de implementación (¿vale el esfuerzo?)
- Expectativas realistas (¿qué han mostrado las pruebas anteriores?)

**Significancia estadística (95%)**: Significa que hay menos del 5% de probabilidad de que la diferencia observada sea por azar.

**Potencia estadística (80%)**: Significa que si hay un efecto real del tamaño MDE, tienes un 80% de probabilidad de detectarlo.

---

## Tablas de Referencia Rápida de Tamaño de Muestra

### Tasa de Conversión: 1%

| Aumento a Detectar | Muestra por Variante | Muestra Total |
|--------------------|---------------------|----------------|
| 5% (1% → 1.05%) | 1,500,000 | 3,000,000 |
| 10% (1% → 1.1%) | 380,000 | 760,000 |
| 20% (1% → 1.2%) | 97,000 | 194,000 |
| 50% (1% → 1.5%) | 16,000 | 32,000 |
| 100% (1% → 2%) | 4,200 | 8,400 |

### Tasa de Conversión: 3%

| Aumento a Detectar | Muestra por Variante | Muestra Total |
|--------------------|---------------------|----------------|
| 5% (3% → 3.15%) | 480,000 | 960,000 |
| 10% (3% → 3.3%) | 120,000 | 240,000 |
| 20% (3% → 3.6%) | 31,000 | 62,000 |
| 50% (3% → 4.5%) | 5,200 | 10,400 |
| 100% (3% → 6%) | 1,400 | 2,800 |

### Tasa de Conversión: 5%

| Aumento a Detectar | Muestra por Variante | Muestra Total |
|--------------------|---------------------|----------------|
| 5% (5% → 5.25%) | 280,000 | 560,000 |
| 10% (5% → 5.5%) | 72,000 | 144,000 |
| 20% (5% → 6%) | 18,000 | 36,000 |
| 50% (5% → 7.5%) | 3,100 | 6,200 |
| 100% (5% → 10%) | 810 | 1,620 |

### Tasa de Conversión: 10%

| Aumento a Detectar | Muestra por Variante | Muestra Total |
|--------------------|---------------------|----------------|
| 5% (10% → 10.5%) | 130,000 | 260,000 |
| 10% (10% → 11%) | 34,000 | 68,000 |
| 20% (10% → 12%) | 8,700 | 17,400 |
| 50% (10% → 15%) | 1,500 | 3,000 |
| 100% (10% → 20%) | 400 | 800 |

### Tasa de Conversión: 20%

| Aumento a Detectar | Muestra por Variante | Muestra Total |
|--------------------|---------------------|----------------|
| 5% (20% → 21%) | 60,000 | 120,000 |
| 10% (20% → 22%) | 16,000 | 32,000 |
| 20% (20% → 24%) | 4,000 | 8,000 |
| 50% (20% → 30%) | 700 | 1,400 |
| 100% (20% → 40%) | 200 | 400 |

---

## Calculadora de Duración

### Fórmula

```
Duración (días) = (Muestra por variante × Número de variantes) / (Tráfico diario × % expuesto)
```

### Ejemplos

**Escenario 1: Página de alto tráfico**
- Necesitas: 10,000 por variante (2 variantes = 20,000 total)
- Tráfico diario: 5,000 visitantes
- 100% expuesto a la prueba
- Duración: 20,000 / 5,000 = **4 días**

**Escenario 2: Página de tráfico medio**
- Necesitas: 30,000 por variante (60,000 total)
- Tráfico diario: 2,000 visitantes
- 100% expuesto
- Duración: 60,000 / 2,000 = **30 días**

**Escenario 3: Bajo tráfico con exposición parcial**
- Necesitas: 15,000 por variante (30,000 total)
- Tráfico diario: 500 visitantes
- 50% expuesto a la prueba
- Efectivo diario: 250
- Duración: 30,000 / 250 = **120 días** (¡demasiado largo!)

### Reglas de Duración Mínima

Incluso con tamaño de muestra suficiente, ejecutar pruebas por al menos:
- **1 semana completa**: Para capturar la variación del día de la semana
- **2 ciclos de negocio**: Si es B2B (patrones de días laborables vs. fin de semana)
- **A través de días de pago**: Si es e-commerce (inicio/fin de mes)

### Directrices de Duración Máxima

Evitar ejecutar pruebas por más de 4-8 semanas:
- Los efectos de novedad se desvanecen
- Los factores externos intervienen
- Costo de oportunidad de otras pruebas

---

## Calculadoras en Línea

### Herramientas Recomendadas

**Calculadora de Evan Miller**
https://www.evanmiller.org/ab-testing/sample-size.html
- Interfaz simple
- Vale la pena marcarla

**Calculadora de Optimizely**
https://www.optimizely.com/sample-size-calculator/
- Lenguaje empresarial amigable
- Estimaciones de duración

**Calculadora de AB Test Guide**
https://www.abtestguide.com/calc/
- Incluye opción Bayesiana
- Múltiples tipos de prueba

**Calculadora de Duración VWO**
https://vwo.com/tools/ab-test-duration-calculator/
- Enfocada en duración
- Buena para planificación

---

## Ajuste para Múltiples Variantes

Con más de 2 variantes (pruebas A/B/n), necesitas más muestra:

| Variantes | Multiplicador |
|-----------|--------------|
| 2 (A/B) | 1x |
| 3 (A/B/C) | ~1.5x |
| 4 (A/B/C/D) | ~2x |
| 5+ | Considerar reducir variantes |

**¿Por qué?** Más comparaciones aumentan la probabilidad de falsos positivos. Estás comparando:
- A vs B
- A vs C
- B vs C (a veces)

Aplica la corrección de Bonferroni o usa herramientas que lo manejen automáticamente.

---

## Errores Comunes con el Tamaño de Muestra

### 1. Pruebas sin suficiente potencia
**Problema**: No hay suficiente muestra para detectar efectos realistas
**Solución**: Ser realista sobre el MDE, obtener más tráfico o no probar

### 2. Pruebas con demasiada potencia
**Problema**: Esperar el tamaño de muestra cuando ya tienes significancia
**Solución**: Está bien — te comprometiste con el tamaño de muestra, respétalo

### 3. Tasa base incorrecta
**Problema**: Usar la tasa de conversión incorrecta para el cálculo
**Solución**: Usar la métrica y página específicas, no los promedios del sitio

### 4. Ignorar segmentos
**Problema**: Calcular para tráfico completo, luego analizar segmentos
**Solución**: Si planeas análisis de segmentos, calcular muestra para el segmento más pequeño

### 5. Probar demasiadas cosas
**Problema**: Dividir el tráfico demasiadas veces
**Solución**: Priorizar despiadadamente, ejecutar menos pruebas concurrentes

---

## Cuando los Requisitos de Tamaño de Muestra son Demasiado Altos

Opciones cuando no puedes obtener suficiente tráfico:

1. **Aumentar el MDE**: Aceptar solo detectar efectos más grandes (aumento del 20%+)
2. **Reducir la confianza**: Usar 90% en lugar de 95% (arriesgado, documentarlo)
3. **Reducir variantes**: Probar solo la variante más prometedora
4. **Combinar tráfico**: Probar en múltiples páginas similares
5. **Probar antes en el embudo**: Probar en etapas anteriores donde hay más tráfico
6. **No probar**: Tomar decisiones basadas en datos cualitativos
7. **Prueba más larga**: Aceptar mayor duración (semanas/meses)

---

## Pruebas Secuenciales

Si debes revisar los resultados antes de alcanzar el tamaño de muestra:

### ¿Qué es?
Método estadístico que ajusta por múltiples miradas a los datos.

### Cuándo usar
- Cambios de alto riesgo
- Necesidad de detener variantes malas temprano
- Decisiones sensibles al tiempo

### Herramientas que lo soportan
- Optimizely (Stats Accelerator)
- VWO (SmartStats)
- PostHog (enfoque Bayesiano)

### Compensación
- Más flexibilidad para detener antes
- Requisito de tamaño de muestra ligeramente mayor
- Análisis más complejo

---

## Marco de Decisión Rápida

### ¿Puedo ejecutar esta prueba?

```
Tráfico diario a la página: _____
Tasa de conversión base: _____
MDE que me importa: _____

Muestra necesaria por variante: _____ (de las tablas arriba)
Días para ejecutar: Muestra / Tráfico diario = _____

Si días > 60: Considerar alternativas
Si días > 30: Aceptable para pruebas de alto impacto
Si días < 14: Probablemente factible
Si días < 7: Fácil de ejecutar, considerar ejecutar más tiempo de todos modos
```
