# Marco de Medición — KPIs, Métricas Norte, Cadencia

Todo plan necesita una sección de medición que le diga al equipo cómo saber si el plan está funcionando. Este documento es la fuente para la subsección de medición de la Sección 13.

**Documentos relacionados:**
- `growth-patterns.md` — la ruta de crecimiento VC 3-3-2-2-2 (3× en los años 1–2, 2× en los años 3–7 desde $1M de ARR) y en qué fase del crecimiento SaaS está la empresa ($0–10K / $10K–100K / $100K–1M+)
- `budget-planning.md` — cálculo de CAC (blended, no solo pagado) y la verificación de realidad del forecasting (los forecasts bajo $100M de ARR son suposiciones educadas, no predicciones precisas)

## El principio de la métrica norte

Una métrica norte es una sola métrica que captura la tesis del modelo de negocio al nivel más alto. Debe:
- Poder derivarse del funnel + el modelo de ingresos
- Moverse lo suficientemente lento como para ser una brújula estratégica (no sacudida por el ruido semanal)
- Intercambiarse correctamente contra otras métricas — mejorar la métrica norte generalmente debería mejorar el negocio

No caigas por defecto en "ARR" o "MRR" solos. Esos son resultados, no normas. Elige algo que capture el modelo de negocio.

## Patrones de métrica norte por modelo de negocio

### B2B SaaS (suscripción)
- **Net Revenue Retention (NRR)** — mantiene en foco a los clientes existentes + la expansión
- Alternativa: "Retención de logos × ARR de expansión"
- Por qué: el ARR solo esconde el churn / permite que el crecimiento de altas brutas enmascare problemas de fit de producto

### App de consumo D2C (suscripción)
- **LTV blended / CAC blended** — mantiene honesta la unit economics a medida que escala la capa pagada
- Alternativa: "Usuarios pagados del día 35 por cohorte × LTV"
- Por qué: las métricas mensuales de suscripción son volátiles; cohorte × LTV lo suaviza

### Híbrido hardware + software (p. ej., Quietude)
- **LTV blended / CAC blended a través de hardware + software** — captura la tesis de la cuña
- Alternativa: "Conversión de compradores de hardware a suscriptores × margen blended"
- Por qué: el ingreso de hardware no es gratis (cuesta fabricarlo); el ingreso de suscripción no es caro de adquirir si el hardware lo financia

### Marketplace (dos lados)
- **Ratio de liquidez × take-rate** — captura ambos lados + la monetización
- Alternativa: "Usuarios transaccionando mensualmente × take-rate × frecuencia de repetición"
- Por qué: el GMV solo no captura si el marketplace se está volviendo un hábito

### Herramienta para desarrolladores / open source
- **Desarrolladores activos semanales × conversión a pago** — captura tanto la adopción como la monetización
- Alternativa: "Organizaciones activas semanales × asientos por org × ARPU"

### Negocio de contenido / medios
- **Lectores/oyentes activos diarios × ingreso publicitario por sesión** — captura tanto el alcance como la monetización
- Alternativa: "Conteo de suscriptores × retención × ARPU"

### Comercio (DTC, no-suscripción)
- **Tasa de recompra × AOV × frecuencia** — captura la monetización en capas sobre la calidad del cliente
- Alternativa: "LTV de cliente / CAC × periodo de recuperación"

## Indicadores líderes por etapa AARRR

Después de la métrica norte, todo plan necesita indicadores líderes por etapa AARRR. Estos se mueven más rápido que la métrica norte y disparan investigaciones.

### Indicadores líderes de Adquisición
- Visitas orgánicas/mes, total + por pilar (salud del SEO)
- Tasa de visita-a-instalación de App Store / Play Store (salud del ASO)
- Crecimiento del canal social liderado por el founder → conversión a suscriptor de email (funnels de LinkedIn / X / Substack)
- Tasa de conversión de evento a app (ROI del evento)
- Visitas atribuidas a ambassador (funnel de referidos)
- CAC pagado por canal (cuando el pago está disparando)

### Indicadores líderes de Activación
- Tasa de conversión Día 1 / Día 7 / Día 35 → pago
- Tasa de completación de sesión de onboarding
- Completación de la primera acción clave (evento de activación post-signup)
- Tasa de conversión de App Store (instalación → trial → pago)
- Tasa de conversión trial → pago

### Indicadores líderes de Retención
- Retención Día 30 / Día 60 / Día 90
- Tasa de churn mensual (bruta + neta)
- Engagement de email de lifecycle (apertura / clic / desuscripción por flujo)
- Tasa de activación hardware → app (para negocios híbridos)
- Tasa de win-back / reactivación

### Indicadores líderes de Referidos
- Nuevas suscripciones atribuidas a ambassador (vía Dub o similar)
- Tasa de momento compartir-después-del-valor (% de usuarios que comparten)
- Tasa de completación de referidos de dos lados
- Referidos del programa Guides (cuando esté vivo)
- Puntaje NPS (si se encuesta)

### Indicadores líderes de Ingresos
- ARPU por cohorte
- % de adopción de plan anual
- LTV de cohorte por fuente
- Cambios en la mezcla de planes
- Tasa de attach de antifaz/hardware (para híbridos)
- Ingreso de expansión (B2B)

## Cadencia de revisión

El plan debe especificar tres ritmos:

### Semanal (sync operativo)
- **Quién:** fCMO ↔ founder (usualmente el CEO)
- **Duración:** 30 min
- **Formato:** Scoreboard AARRR (números actuales vs. la semana pasada a través de los indicadores líderes) + los envíos de esta semana + bloqueadores
- **Salida:** Elementos de acción, decisiones tomadas

### Mensual (revisión de métricas)
- **Quién:** fCMO + founder + equipo extendido (CXO, lead de producto, diseñador si aplica)
- **Duración:** 60–90 min
- **Formato:** Revisión completa de métricas + comparación contra metas trimestrales de KPI + aprendizajes cualitativos + repriorización del banco de ideas
- **Salida:** Posibles ajustes al plan, decisiones de contratación

### Trimestral (recalibración del plan)
- **Quién:** fCMO + founders + advisors clave
- **Duración:** 2–3 horas
- **Formato:** Revisión completa del plan contra los resultados a 90 días y 12 meses, análisis a nivel de canal, chequeo de transición de etapa de financiamiento, recalibración de los próximos 90 días
- **Salida:** Plan actualizado (podría ser iteración de documento v2 / v3)

## Fijación de metas de KPI

Para cada trimestre en la Sección 10, el plan debe incluir 3–5 metas específicas de KPI. Estas deben ser:
- **Específicas** — no "mejorar la retención," sino "retención del Día 30 de 22% → 30%"
- **Medibles** — extraídas de una fuente de datos conectada
- **Ambiciosas pero plausibles** — basadas en el estado del funnel + patrones históricos
- **Disparadoras de decisiones** — si no se alcanzan, ¿qué significa eso? (Ajustar estrategia, matar un canal, etc.)

### Patrones de meta de KPI por trimestre

**Q1 (trimestre de fundación):**
- Mayormente métricas de *base* — arreglar fugas. "La caída de conversión en el gate de audífonos se revierte." "Día 1 → pago +25–50%."
- Algunas métricas de *fundación* — sentar bases. "4 pilares de SEO sembrados." "Reescritura de App Store enviada."
- Evita metas de crecimiento audaces — las fundaciones aún no están puestas

**Q2 (trimestre de validación):**
- Mayormente métricas de *validación* — ¿funciona lo que construimos? "CAC pagado < $X blended." "Tráfico orgánico 1,500–3,500/mes."
- Algunas métricas de *cohorte* — ¿se comportan mejor las cohortes nuevas? "Retención del Día 7 de la cohorte Q2 vs. Q1."

**Q3 (trimestre de escalamiento):**
- Mayormente métricas de *escalamiento* — ¿hasta dónde llega? "Pago escalando a $20–30K/mes con CAC estable." "Primer caso de referencia de instalación B2B vivo."
- Algunas métricas de *capacidad* — ¿qué cosas nuevas están vivas? "Primer piloto de Guides lanzado."

**Q4 (trimestre de composición):**
- Mayormente métricas de *composición* — ¿está girando el flywheel? "50%+ de las nuevas suscripciones de canales no pagados." "Ambassador impulsando 15–25% de las nuevas suscripciones."
- Algunas métricas de *narrativa* — ¿se escribe sola la historia de Series A? "LTV/CAC blended > 3."

## Anclaje contra la ruta de crecimiento VC

Para clientes respaldados por VC más allá de $1M de ARR, ancla las metas a 12 meses y multi-año contra la **regla 3-3-2-2-2** (3× en los años 1 y 2, luego 2× en los años 3 al 7). Alcanzarla es raro; la mayoría de las empresas no lo logra. Anclar contra ella obliga al plan a igualarla y mostrar cómo, o defender explícitamente elegir una trayectoria más lenta. Tabla completa y contexto en `growth-patterns.md`.

Para empresas no respaldadas por VC (bootstrapped, financiadas por el founder, enfocadas en utilidad), la 3-3-2-2-2 no aplica. Usa metas de patrón lineal ("$X de MRR agregado por mes") o metas de función escalonada ("salto de $Y de ingreso después de que se lance el nivel enterprise") en su lugar.

## Verificación de realidad del forecasting

Un plan deriva un presupuesto y una meta anual. No produce un forecast mes a mes de 12 meses confiablemente preciso al dólar.

**A menos que la empresa cotice en bolsa, todos los forecasts son suposiciones educadas.** Ningún startup bajo $100M de ARR alcanza consistentemente los forecasts mes a mes. La revisión trimestral es cuando el plan se ajusta — no cuando la varianza se trata como fracaso.

Lo que el plan compromete honestamente:
- La meta anual es una dirección de viaje defendible
- El presupuesto es el compromiso de recursos que hace plausible la meta
- El roadmap a 90 días (Sección 9) es lo accionable ahora
- La proyección mes a mes es ilustrativa, no prometida

Los founders que sobre-ingenieran el forecast terminan explicando la varianza cada mes en lugar de ejecutar. El plan debe resistirse a esto — nombra la meta anual, los KPI trimestrales, y los criterios de kill. No prometas el mes.

Contexto completo en `budget-planning.md`.

## Criterios de kill

Para cada canal o iniciativa, el plan debe especificar cuándo detenerse. A menudo faltantes en los planes, los criterios de kill obligan a la disciplina.

Ejemplos:
- "Si un canal pagado tiene CAC > 2× la meta después de 30 días a gasto significativo, pausar."
- "Si la Variante 3 de onboarding no muestra un lift estadísticamente significativo (o lift direccional + señal cualitativa congruente) después de 4 semanas, mover a la Variante 1."
- "Si el Flow 4 de lifecycle tiene tasa de apertura < 12% después de 6 semanas, rehacer las líneas de asunto + segmentación de audiencia."

## Métricas de guardarraíl

Algunas métricas tienen un guardarraíl duro (no pueden caer bajo un umbral). Útil para proteger la marca o la unit economics durante el crecimiento agresivo.

Ejemplos:
- "La tasa de quejas por voz de marca > 1% del feedback de clientes dispara una revisión de contenido."
- "CAC pagado > $X durante dos meses consecutivos pausa el escalamiento pagado en espera de auditoría."
- "El puntaje de App Store cae por debajo de 4.5 dispara una revisión de producto."

## Mapeo de fuentes de datos

El plan debe nombrar de dónde viene cada métrica. Esto lo hace auditable.

| Métrica | Fuente |
|---|---|
| Tráfico orgánico | GA4 / Ahrefs |
| Conversión de App Store | App Store Connect |
| Conversión de funnel (Día N → pago) | Analítica interna (Mixpanel / Amplitude) o exportación de cohorte de App Store Connect |
| Retención | Segmentos de Customer.io + analítica de producto |
| MRR / ARR | Stripe (vía MCP si está conectado) |
| Mezcla de planes | Stripe |
| Métricas de email de lifecycle | Customer.io |
| Atribución de ambassador | Dub.co |
| Activación hardware → app | Unión interna de Shopify + App Store |
| NPS | Herramienta de encuesta (Customer.io / Typeform / SurveyMonkey) |

## Cuando los datos no están conectados

Si una métrica no puede medirse actualmente, márcala en las decisiones abiertas de la Sección 13. Ejemplo:

> "La tasa de activación hardware → app no es visible actualmente en el dashboard de App Store. Requiere una unión de Shopify ↔ App Store Connect. Elemento de trabajo de Q1."

Un plan con metas no-medibles es un plan que no puede validarse. Expón el trabajo de instrumentación explícitamente.

## Cadencia de reportes + automatización

Donde sea posible, auto-genera la revisión de métricas en lugar de construirla manualmente cada vez. Stripe MCP + GA4 MCP + Customer.io MCP pueden extraer la mayoría de lo necesario.

Para clientes Tier 1, un email semanal simple de métricas al equipo (tabla en Markdown, generada vía skills + MCPs) no cuesta nada y crea disciplina.

Para clientes Tier 2+, considera un dashboard real (Hex, Metabase, Looker, o herramienta interna).
