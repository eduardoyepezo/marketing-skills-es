# Orquestación y Despliegue de Loops

Los loops no son scripts independientes — se combinan en un sistema operativo de marketing. Esta referencia cubre cómo encajan entre sí y el orden para adoptarlos, de modo que nunca construyas 43 a la vez.

## La vista de sistema

Los loops caen en cuatro capas. Los datos fluyen hacia abajo y los aprendizajes fluyen de regreso hacia arriba.

```
DETECCIÓN      analytics-anomaly · tracking-QA · weekly-marketing-review
                  │  (detectar qué cambió; confiar primero en los números)
                  ▼
DIAGNÓSTICO    vigías por etapa — onboarding drop-off, churn-signal,
               ranking-drop, landing-page regression, ad-fatigue, …
                  │  (averiguar qué hacer al respecto)
                  ▼
ACCIÓN         borradores preparados, recordatorios, outreach, movimientos de presupuesto
                  │  (mayormente con checkpoint humano)
                  ▼
APRENDIZAJE    experiment-backlog · campaign-postmortem · voice-of-customer
                  │  (capturar qué funcionó)
                  └──────────────► retroalimenta a DETECCIÓN y DIAGNÓSTICO
```

Tejido conectivo clave:
- **weekly-marketing-review es el enrutador.** Lee las métricas principales y despacha cada movimiento notable al loop que lo posee. Es el único loop que ve todo el tablero.
- **tracking-QA + analytics-anomaly son la base.** Todos los demás loops leen de analytics. Si el tracking está roto, cada loop río abajo actúa sobre mentiras. Estos van primero.
- **experiment-backlog es el sumidero.** Las hipótesis generadas por muchos loops (signup-leak, pricing, onboarding, voice-of-customer) convergen aquí, y luego se traspasan a `ab-test-setup`. No dejes que cada loop corra sus propias pruebas.
- **voice-of-customer es una fuente.** El lenguaje de clientes que extrae alimenta el copy de los loops de ad-fatigue, lifecycle-email, landing-page, y pricing.
- **campaign-postmortem cierra el loop.** Sus aprendizajes se convierten en las hipótesis y los insumos del plan del próximo trimestre.

Evita la propiedad duplicada: cuando dos loops podrían actuar sobre la misma señal, uno posee la acción y el otro solo señala. (P. ej., una cuenta en riesgo pertenece a churn-signal, no a expansion/upsell — nunca hagas upsell a una cuenta que está haciendo churn.)

## Ruta de despliegue (adoptar en este orden)

Agrega un loop solo cuando los loops anteriores estén corriendo y ganándose su lugar. Cada etapa asume que la anterior es sólida.

**Etapa 0 — Fundación (confiar en los datos + ver el tablero).**
`tracking-QA`, `weekly-marketing-review`.
No puedes correr ningún loop de forma responsable sobre datos no confiables o sin un pulso de funnel completo. Esto no es negociable y va primero.

**Etapa 1 — Tapar las fugas (mayor ROI, protege los ingresos existentes).**
`failed-payment/dunning`, `churn-signal`, `lifecycle-email-refresh`.
Recuperar clientes que ya tienes es más barato que adquirir nuevos. El dunning por sí solo a menudo paga todo el sistema.

**Etapa 2 — Convertir lo que ya consigues (arreglar el balde antes de agregar agua).**
`onboarding drop-off`, `signup-funnel-leak`, `trial-conversion`.
Más tráfico hacia un funnel con fugas es desperdicio. Sella la activación y la conversión primero.

**Etapa 3 — Crecer la parte superior (ahora escala la adquisición).**
`keyword-gap`, `content-repurposing`, `ad-fatigue`, `social-listening`, `analytics-anomaly`.
Con el balde sellado, activa la generación de demanda y el vigía de anomalías como red de seguridad.

**Etapa 4 — Optimizar la monetización.**
`pricing-page-experiment`, `paywall-optimization`, `PQL/upgrade-intent`, `expansion/upsell`.
Una vez que el volumen está saludable, ajusta los ingresos por usuario — juzgados por la calidad de los ingresos, no solo por la conversión.

**Etapa 5 — Efecto compuesto y advocacy.**
`referral-nudge`, `review-and-UGC-harvest`, `review-site-management`, `case-study-sourcing`, `partner-pipeline`, `brand-mention/reputation`, `experiment-backlog`, `campaign-postmortem`.
El volante: clientes felices y earned media que retroalimentan la adquisición, más los loops de aprendizaje que hacen que todo se acumule.

Los demás loops del catálogo (content-decay, internal-linking, programmatic-SEO quality, content-calendar refill, paid-search query-mining, retargeting-hygiene, landing-page regression, community-engagement, competitor-watch, backlink-prospecting, directory-submission, feature-adoption, lead-capture-asset, email-deliverability, voice-of-customer) encajan en la etapa que corresponde a su función a medida que cada canal se vuelve prioritario.

## Reglas de despliegue

- **Uno a la vez.** Demuestra que un loop se gana su lugar (alguien actúa sobre su salida, mueve su métrica) antes de agregar el siguiente.
- **Fundación antes que crecimiento.** Loops de adquisición antes de tener tracking sólido + retención = verter agua en un balde con fugas.
- **Limita el total.** Si estás corriendo más loops de los que puedes revisar, tienes loops de vanidad. Retira los que nadie usa.
- **Re-audita trimestralmente.** Recalibra los umbrales, elimina los loops muertos, promueve los que consistentemente impulsan acción.
