# Planificación de Presupuesto — Métodos Científicos para Fijar el Presupuesto de Marketing

El problema con la mayoría de los presupuestos de marketing SaaS es que se sacan de la nada — un número que ojalá no restrinja demasiado el crecimiento, pero que tampoco se ancla en la economía de adquisición de clientes. El resultado: cuando alguien pregunta "¿por qué este número?", no hay respuesta.

Dos métodos científicos resuelven esto. Usa uno (no ambos) en la Sección 8 (Ingresos) y la Sección 10 (Perspectiva a 12 meses) de cada plan.

Extraído y adaptado de *Founding Marketing* de Corey Haines.

## Método 1 — Basado en Ingresos (5–40% del ingreso anual)

**Dirección:** presupuesto → meta de ingresos.

Empiezas con lo que la empresa puede gastar cómodamente en marketing, luego proyectas qué ingreso puede generar ese gasto de forma plausible.

### Los rangos

| Postura | % del ARR | Cuándo usar |
|---|---|---|
| **Conservadora (preserva utilidad)** | 5% | Empresa establecida enfocada en distribución de utilidades; bootstrapped; base de clientes pagada por el founder |
| **Crecimiento estándar** | 15–25% | La mayoría de los SaaS saludables en el rango de seed a Series A |
| **Crecimiento agresivo (desplegando capital levantado)** | hasta 40% | Ronda recientemente financiada, mandato de desplegar rápido, el board acepta el burn |

Como referencia: las empresas SaaS públicas reportan rutinariamente gasto de ventas y marketing entre el 20% y el 55% de los ingresos (Zoom históricamente operó entre 20% y 55% a través de los años).

### Las matemáticas (ejemplo Conservador)

Empresa en $1M de ARR, asignación de 5%:

- Presupuesto anual de marketing: **$50,000**
- CAC blended: $100 → puede adquirir **500 clientes nuevos**
- ARPC: $50/mes → agrega **$300K** al ARR
- Considerando 15% de churn anual → 85% × $300K = **+$255K de ARR neto nuevo**
- Meta a fin de año: **$1.255M de ARR**

### Las matemáticas (ejemplo Agresivo)

Empresa en $1M de ARR, asignación de 40%:

- Presupuesto anual de marketing: **$400,000**
- CAC blended: $100 → puede adquirir **4,000 clientes nuevos**
- ARPC: $50/mes → agrega **$2.4M** al ARR
- Meta a fin de año: **$3.4M de ARR**

### Dos claves para que este método funcione

1. **Conoce tu CAC blended** (ver "Calculando el CAC" abajo)
2. **Haz coincidir el porcentaje de asignación con tu ambición real.** Un founder que corre con 5% de asignación mientras le dice al board que espera triplicar los ingresos está enviando dos señales incompatibles.

## Método 2 — Basado en la Meta (calculado en reversa desde la meta de ingresos)

**Dirección:** meta de ingresos → presupuesto.

Empiezas con la meta de ingresos y trabajas hacia atrás a través de la unit economics para derivar el presupuesto requerido para alcanzarla. Mejor para:

- Empresas que apenas están empezando (sin línea base histórica de CAC todavía, trabajando desde primeros principios)
- Empresas anticipando capital externo (necesitan defender la solicitud)
- Empresas que usan financiamiento basado en ingresos (Pipe, Capchase, Founderpath)

### La fórmula

```
Presupuesto de marketing = [(Nuevo ARR / (ARPC × 12)) × CAC] / tasa de retención anual
```

### Ejemplo resuelto: $1M de ARR → $2M de ARR

Paso 1 — ¿Cuánto ARR nuevo por cliente?
ARPC × 12 = $50 × 12 = **$600 de ARR por cliente nuevo**

Paso 2 — ¿Cuántos clientes nuevos necesitamos?
$1,000,000 / $600 = **1,667 clientes nuevos**

Paso 3 — ¿Cuál es el costo de adquisición en bruto?
1,667 × $100 CAC = **$166,700**

Paso 4 — Considera el churn (15% anual = 85% de retención)
$166,700 / 0.85 = **$196,118** (redondea a **$200K**)

Cuando alguien pregunte cómo llegaste al presupuesto, guíalo por los cuatro pasos. Es defendible.

### Por qué esta fórmula y no algo más simple

Los cuatro pasos corresponden cada uno a una realidad económica real:
- El Paso 1 convierte el lenguaje de MRR en el lenguaje de ARR con el que habla un board
- El Paso 2 nombra la cantidad de clientes, que es lo que el funnel realmente tiene que entregar
- El Paso 3 ancla el presupuesto en el costo de adquisición
- El Paso 4 reconoce que los clientes que se van (churn) no cuentan hacia el ARR neto nuevo, así que el presupuesto necesita cubrir la brecha

### Buffer requerido

**Siempre suma 10–20% como "presupuesto experimental"** encima de la salida de la fórmula. El CAC es la dependencia principal; si el CAC resulta 50% más alto de lo estimado, el efecto en cascada es no alcanzar la meta de ingresos. Es mucho más barato sobreestimar el CAC que subestimarlo.

El presupuesto experimental también financia los experimentos que encuentran tu siguiente canal antes de que el actual se estanque (ver `growth-patterns.md` — curvas en S por canal).

## La ruta de crecimiento VC (regla 3-3-2-2-2)

Una vez que una empresa ha cruzado $1M de ARR y tomado una Series A, el benchmark implícito que esperan los VCs es:

| Año | Múltiplo de ARR | ARR acumulado (desde el inicio en $1M) |
|---|---|---|
| Año 0 | — | $1M |
| Año +1 | 3× | $3M |
| Año +2 | 3× | $9M |
| Año +3 | 2× | $18M |
| Año +4 | 2× | $36M |
| Año +5 | 2× | $72M |
| Año +6 | 2× | $144M |
| Año +7 | 2× | $288M |

Esa es la regla 3-3-2-2-2. Útil cuando:

- El plan necesita mapear hitos a 12 y 36 meses contra las expectativas de los VC
- El founder está en medio de una ronda y el board necesita ver un camino plausible hacia la próxima ronda
- La Sección 10 (Perspectiva a 12 meses) necesita anclarse contra un benchmark de la industria, no solo ambición interna

La mayoría de las empresas no la alcanzan. Está bien. Conocer el benchmark le da al equipo una razón defendible para igualarlo o elegir explícitamente no hacerlo.

## Calculando el CAC (blended, no solo pagado)

Si no hay CAC histórico, usa una línea base: **un año de ingresos del plan pagado más pequeño.** Despliega el presupuesto, captura datos reales de CAC, reemplaza la línea base con el número medido para el siguiente ciclo de planificación.

Para un cálculo de CAC establecido, **el CAC debe ser blended.** Incluye:

- Salarios de marketing (costo totalmente cargado, no solo base)
- Gasto en publicidad
- Costos del stack de martech
- Costos de producción de contenido (redactores, diseñadores, editores de video)
- Retainers de agencia / contratistas
- Salarios de SDR / BDR si se hace outbound
- Herramientas (CRM, automatización de marketing, analítica)

Luego divide por el número de clientes nuevos adquiridos en el periodo. Ese número blended es el que hay que usar en cualquiera de los dos métodos de presupuesto.

El error a evitar: calcular el CAC solo a partir del gasto en anuncios pagados. Una empresa que "no corre anuncios" igual tiene un CAC — solo está escondido en el equipo de contenido, el tiempo del founder, el contratista de SEO, el stand en la conferencia.

## La verificación de realidad en el forecasting

Todo este marco deriva un presupuesto y una meta de ingresos — no un forecast mes a mes de 12 meses preciso al dólar.

**A menos que la empresa cotice en bolsa, todos los forecasts son suposiciones educadas.** Ningún startup por debajo de $100M de ARR alcanza forecasts de forma confiable mes a mes. El planteamiento honesto para el plan:

- La meta anual es una dirección de viaje defendible
- El presupuesto es el compromiso de recursos que hace plausible la meta
- El roadmap a 90 días (Sección 9) es lo accionable ahora
- La varianza mes a mes es esperada; la revisión trimestral es cuando el plan se ajusta

Qué es accionable: cómo desplegar el presupuesto, qué movidas concretas ejecutar, qué ajustar cuando llegan datos reales.

Qué no es accionable: intentar pronosticar tráfico, pipeline, curvas de retención, tasas de conversión y mezcla de canales todo hasta el decimal y esperar que ese forecast se sostenga. Los founders que sobre-ingenieran el forecast tienden a pasar el periodo del plan explicando la varianza en lugar de ejecutar.

**Regla para el plan:** el número de presupuesto es honesto. La meta anual es honesta. La proyección mes a mes es ilustrativa.

## Cómo esto se integra en el plan

| Sección | Qué incluir |
|---|---|
| **3 (Estado actual)** | Gasto mensual actual de marketing desglosado por línea (pago, herramientas, contenido, headcount, retainers). Calcula la asignación actual como %-de-ARR. |
| **8 (Ingresos)** | La tabla de unit economics (CAC, ARPC, churn) que alimenta el método de presupuesto que estés usando. |
| **10 (Perspectiva a 12 meses)** | Aplica el Método 1 o el Método 2 para derivar el presupuesto a 12 meses y la meta de ingresos resultante. Ancla contra la regla 3-3-2-2-2 si es Series A+ y respaldado por VC. |
| **11 (Stack de operaciones)** | Muestra la asignación del presupuesto entre las etapas AARRR — qué % va a Adquisición, Activación, etc. El mapeo del stack de operaciones informa qué líneas crecen cuando se desbloquea el siguiente nivel de financiamiento. |
| **13 (Decisiones abiertas)** | Si el CAC es desconocido o cuestionado, márcalo como la decisión abierta de mayor impacto — todos los demás números dependen de él. |

## Cuándo elegir cuál método

- **Método 1 (Basado en Ingresos)** cuando la empresa tiene datos históricos de CAC, una postura de utilidad/burn, y la pregunta es "dada nuestra postura, cuál es una meta plausible".
- **Método 2 (Basado en la Meta)** cuando la empresa tiene una meta específica (mandato del board, hito de VC, objetivo de fundraising) y la pregunta es "qué presupuesto necesitamos para alcanzarla".

Para la mayoría de los planes en el rango de seed a Series A, el Método 2 es más útil — obliga a la conversación sobre si la meta está financiada.
