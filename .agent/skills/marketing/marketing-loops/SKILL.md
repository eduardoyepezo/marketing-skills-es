---
name: marketing-loops
description: "Cuando el usuario quiere configurar un flujo de trabajo de marketing recurrente y autoejecutable — un loop repetible que un agente de IA corre en una cadencia (semanal, diaria, o por disparador) en lugar de una tarea puntual. También usar cuando el usuario menciona 'loop de marketing,' 'flujo de trabajo recurrente,' 'automatizar mi marketing,' 'marketing en piloto automático,' 'revisión semanal de marketing,' 'chequeo de fatiga publicitaria,' 'loop de refresco de contenido,' 'vigilancia de churn,' 'alerta de caída de rankings,' 'marketing siempre activo,' 'flujo de automatización de marketing,' o 'ejecuta esto cada semana.' Úsala para elegir, adaptar y programar un loop de marketing continuo que orqueste las demás habilidades de marketing. Para ideas de marketing puntuales, ver marketing-ideas. Para el loop de experimentación específicamente, ver ab-test-setup."
metadata:
  version: 1.2.0
---

# Loops de Marketing

Ayudas a configurar **loops de marketing** — flujos de trabajo de marketing repetibles que un agente de IA ejecuta en una cadencia, cada uno con un disparador definido, un conjunto acotado de pasos, una autoverificación, y una condición de parada explícita. Un loop convierte una tarea de marketing que de otra forma harías manualmente (y olvidarías) en un sistema siempre activo: el escaneo semanal de oportunidades de SEO, el refresco por fatiga publicitaria, la vigilancia de señales de churn.

Esta es la prima operativa de `marketing-ideas`. Las ideas te dicen *qué probar una vez*. Los loops te dicen *qué seguir haciendo en un horario* — y conectan entre sí las demás habilidades de marketing para lograrlo.

## Cómo Usar Esta Habilidad

**Revisar el contexto de marketing del producto primero:** si existe `.agents/product-marketing.md` (o `.claude/product-marketing.md`, o el nombre de archivo legado `product-marketing-context.md`, en configuraciones antiguas), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por lo que falte.

Luego:
1. **Aclara el objetivo.** ¿Qué resultado debe proteger o hacer crecer este loop? (rankings, eficiencia publicitaria, activación, retención, ingresos, referidos)
2. **Elige un loop** del catálogo en `references/loop-catalog.md` — o adapta el más cercano.
3. **Ajusta la cadencia** a la velocidad real con la que cambia la señal subyacente (ver la regla de cadencia más abajo).
4. **Confirma el checkpoint humano.** Decide qué hace el loop de forma autónoma vs. qué deja preparado para aprobación humana antes de publicar o gastar — ver `references/loop-guardrails.md`.
5. **Prográmalo** (ver "Programar un loop" más abajo).

¿Vas a construir más de un loop, o todo un sistema operativo de marketing? Ver `references/loop-orchestration.md` para cómo se combinan los loops y el orden para adoptarlos (empieza con tracking + una revisión semanal; no construyas 43 a la vez).

## Anatomía de un Loop de Marketing

Cada loop del catálogo tiene estas nueve partes. Cuando crees o adaptes uno, complétalas todas — un loop sin condición de parada, sin autoverificación, o sin manejo de estado es un pasivo, no un activo.

| Parte | Qué define |
|------|-----------------|
| **Cadencia de revisión** | Con qué frecuencia el loop *revisa* (semanal / diaria / por disparador). Ajústala a la velocidad de la señal. |
| **Actúa cuando** | La condición de acción — qué debe ser cierto para que realmente *haga* algo, en lugar de solo revisar y pasar de largo. La mayoría de las corridas de un buen loop son "revisado, nada que hacer." |
| **Propósito** | El único resultado que este loop existe para mover. |
| **Habilidades usadas** | Qué habilidades de marketing orquesta el loop en cada iteración. |
| **Cuerpo del loop** | Los pasos ordenados que se ejecutan en cada iteración. |
| **Autoverificación** | La verificación que se hace *antes* de actuar — para que el loop no actúe sobre ruido, estacionalidad o un bug de tracking. |
| **Estado / idempotencia** | Lo que el loop recuerda entre corridas: marcador de última ejecución, clave de deduplicación, ventana de enfriamiento, conjunto de "ya manejado." Sin esto, los loops actúan dos veces, vuelven a molestar a las mismas personas, o vuelven a alertar sobre lo mismo. No negociable para todo lo programado — ver `references/loop-state.md` para dónde vive el estado y los patrones de idempotencia. |
| **Parada / salida** | Cuándo el loop se salta, se detiene, escala a un humano, o se desactiva a sí mismo — más qué hace ante un error. Todo loop necesita una, incluidos los loops de heartbeat (su parada es "desactivación manual + detención por error," nunca "n/a"). |
| **Salida** | A dónde van los resultados: un archivo, un PR, un borrador preparado, una notificación, un reporte. |

La separación entre **Cadencia de revisión / Actúa cuando** importa: un loop de señal de churn podría *revisar* diariamente pero solo *actuar* cuando una cuenta cruza un umbral de riesgo por el que no ha sido contactada dentro de la ventana de enfriamiento. Confundir ambas cosas produce loops que o bien pierden la ventana o hacen spam.

## La regla de cadencia

Ajusta la cadencia a la velocidad real con la que cambia la señal — no a la frecuencia con la que *te gustaría* recibir una actualización.

| Señal | Cadencia realista | Por qué |
|--------|-------------------|-----|
| Rankings, backlinks, autoridad de dominio | Semanal | Se mueven lento; revisar a diario es ruido |
| Fatiga de creatividades publicitarias, deriva de CPA | Cada 2–3 días | Los ciclos de retroalimentación de Meta/Google son de días, no de horas |
| Funnel de activación / onboarding | Semanal | Necesita suficientes registros para ser significativo |
| Señales de churn | Diaria o por disparador | La ventana de intervención temprana es corta |
| Decaimiento de contenido / copy | Mensual | La erosión de tráfico es gradual |
| Cambios de la competencia | Semanal | Los cambios de precios/posicionamiento son poco frecuentes pero importan |
| Escucha social / menciones | Diaria | Las ventanas de engagement se cierran rápido |

Los loops demasiado frecuentes son el modo de falla más común: generan trabajo innecesario, queman presupuesto, y te entrenan para ignorar la salida.

## Cuándo NO usar un loop

No todo debe automatizarse en una cadencia. Omite un loop — o agrega un checkpoint humano obligatorio — cuando:

- **La estrategia o la dirección creativa son el verdadero trabajo.** Los loops mantienen y optimizan; no definen el posicionamiento, no inventan campañas, ni toman decisiones de marca.
- **La acción publica o gasta sin revisión.** Auto-*redactar* un anuncio, correo o post está bien. Auto-*publicar* o auto-*mover presupuesto* necesita un checkpoint humano a menos que el usuario haya autorizado explícitamente la acción autónoma y establecido guardrails (topes, listas permitidas).
- **La señal es demasiado escasa para ser significativa.** Un loop semanal de tasa de conversión sobre 40 visitantes/semana está midiendo ruido.
- **Es un loop de vanidad.** Si nadie actúa sobre la salida, elimina el loop. Un loop que envía por correo un dashboard que nadie lee es peor que nada.

Para cualquier loop que envíe, gaste, publique, o toque datos personales, aplica `references/loop-guardrails.md` — el modelo de acción de dos niveles (autónomo-seguro vs. controlado), topes de gasto/envío, reglas de CAN-SPAM/GDPR/FTC/ToS, la lista de escalamiento obligatorio, y un interruptor de emergencia requerido.

## Programar un loop

Estos loops son agnósticos al agente — el *cuerpo* funciona en cualquier agente. La *programación* depende de tu entorno:

- **Claude Code** — opciones nativas: `/loop` (a su propio ritmo, hasta que se cumpla una condición), `ScheduleWakeup` (ritmo dinámico que reacciona al estado), y `CronCreate` (horario cron fijo). Si tienes instalada una habilidad de mecánica de loops como `loopify`, úsala para elegir entre ellas y ajustar los tiempos de espera; de lo contrario, la guía de abajo es suficiente.
- **Cualquier agente + cron** — envuelve el cuerpo del loop como un prompt/script programado (`0 9 * * 1` para los lunes a las 9am, etc.).
- **Cadencia manual** — para loops de alto juicio, "ejecuta esta habilidad cada lunes" es un loop perfectamente válido. El valor está en el *cuerpo* repetible, no en la automatización.

Por defecto usa cron a hora fija para loops de tipo revisión (revisión semanal, vigilancia de rankings) y ritmo dinámico para loops de tipo monitorear-hasta-el-umbral (vigilancia de churn, seguimiento del día de lanzamiento).

## El Catálogo

`references/loop-catalog.md` contiene la biblioteca completa — 43 loops de marketing con cobertura exhaustiva del funnel: SEO y Contenido, Pago, Earned, Social y Partnerships, Activación, Retención, Ingresos, Referidos y Advocacy, y Operaciones Continuas. Cada uno es una especificación completa y adaptable. Empieza ahí, elige el más cercano, y ajústalo al producto, etapa y stack de herramientas del usuario.

## Crear un loop nuevo

Cuando nada en el catálogo encaja, crea un loop nuevo a partir de `references/loop-template.md` — una plantilla de copiar y pegar con prompts para completar, un ejemplo antes/después resuelto, y un checklist de lanzamiento. Completa las nueve partes de la anatomía; si no puedes responder la autoverificación, el estado/idempotencia, y la parada/salida de forma concreta, el loop no está listo para correr.

## Anti-patrones

- Hacer loop sin condición de parada → gasto descontrolado o churn infinito.
- La misma cadencia para todos los loops → la mayoría corre demasiado seguido y se termina ignorando.
- Sin autoverificación → el loop actúa sobre ruido, estacionalidad, o un bug de tracking.
- Sin checkpoint humano en acciones de gasto/publicación.
- Construir 10 loops a la vez → empieza con uno, demuestra que se gana su lugar, luego agrega el siguiente.

## Vocabulario prohibido

Evita: "configúralo y olvídalo," "marketing totalmente autónomo," "la IA hace todo," "10x en piloto automático," "máquina de growth hacking." Los loops son sistemas disciplinados con checkpoints, no magia. Descríbelos con honestidad.

## Habilidades Relacionadas

- **marketing-ideas** — tácticas e inspiración puntuales (qué probar). Los loops operacionalizan las que valen la pena repetir.
- **ab-test-setup** — el loop de experimentación específicamente (hipótesis → prueba → promover ganador → repetir).
- **analytics-tracking** — la mayoría de los loops leen de analytics para decidir si actuar.
- Habilidades de canal individuales (`paid-ads`, `seo-audit`, `email-sequence`, `social`, `churn-prevention`, `pricing-strategy`, `referral-program`) — los cuerpos de los loops orquestan estas.
