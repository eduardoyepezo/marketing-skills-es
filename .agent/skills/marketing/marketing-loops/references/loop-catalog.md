# Catálogo de Loops de Marketing

Una biblioteca de loops de marketing repetibles con cobertura exhaustiva a lo largo del funnel. Cada uno es una especificación completa y adaptable. Elige el más cercano, y luego ajusta la cadencia, los umbrales, el manejo de estado, y los checkpoints humanos al producto, etapa, y stack de herramientas del usuario.

Cada loop enumera nueve partes: **Cadencia de revisión · Actúa cuando · Propósito · Habilidades usadas · Cuerpo del loop · Autoverificación · Estado / idempotencia · Parada / salida · Salida**. Ver `SKILL.md` para la anatomía, la regla de cadencia, y cuándo no usar un loop.

Dos reglas que aplican a cada entrada:
- **La mayoría de las corridas no deberían hacer nada.** Un loop saludable revisa, no encuentra nada que valga la pena accionar, registra "sin acción," y termina. Los loops que actúan en cada corrida usualmente están actuando sobre ruido.
- **El estado previene el daño.** Cada loop rastrea lo que ya hizo (marcador de última ejecución, clave de deduplicación, enfriamiento) para nunca actuar dos veces, volver a molestar a la misma persona, o volver a alertar sobre el mismo problema.

Los loops están agrupados por función. La nomenclatura sigue la convención "El loop de X."

---

## SEO y Contenido

### El loop de keyword-gap
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Una keyword a distancia de impacto (posiciones 5–20) o una query en ascenso no tiene una página adecuada.
- **Propósito**: Detectar nuevas oportunidades de ranking antes de que la competencia las tome.
- **Habilidades usadas**: `seo-audit`, `programmatic-seo`, `content-strategy`
- **Cuerpo del loop**:
  1. Extraer datos de ranking + impresiones (Search Console / rastreador de rankings).
  2. Comparar contra la última corrida: nuevas keywords a distancia de impacto, queries en ascenso sin página correspondiente.
  3. Clasificar cada brecha: victoria rápida on-page / página completamente nueva / candidata a plantilla programática.
  4. Redactar briefs para las 3 principales.
- **Autoverificación**: ¿El movimiento es real o estacional? Comparar con el mismo período del mes pasado, no solo la semana pasada.
- **Estado / idempotencia**: Almacenar el conjunto de brechas ya briefeadas; no volver a briefear una que ya está abierta.
- **Parada / salida**: Ninguna brecha supera un umbral mínimo de impresiones → registrar "sin acción." Detenerse ante una caída de la fuente de datos en lugar de actuar sobre datos parciales.
- **Salida**: Hasta 3 briefs de contenido preparados para revisión + un resumen de movimiento de una línea.

### El loop de ranking-drop watch
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Una keyword o página prioritaria cae más de N posiciones vs. la base.
- **Propósito**: Detectar y diagnosticar regresiones de SEO antes de que se acumulen.
- **Habilidades usadas**: `seo-audit`, `analytics-tracking`
- **Cuerpo del loop**:
  1. Rastrear posiciones de keywords/páginas prioritarias.
  2. Señalar caídas materiales; comparar qué cambió (contenido, enlaces, diseño del SERP, momento de una actualización de algoritmo).
  3. Diagnosticar la causa probable + proponer un arreglo.
- **Autoverificación**: Descartar un cambio de feature del SERP o volatilidad puntual antes de declarar una pérdida real.
- **Estado / idempotencia**: Recordar qué caídas ya están abiertas como incidencias; actualizar en lugar de volver a registrarlas.
- **Parada / salida**: Sin caída material → registrar "estable." Escalar sospechas de golpe de algoritmo a un humano en lugar de editar masivamente.
- **Salida**: Un reporte de regresión con un arreglo recomendado.

### El loop de content-decay
- **Cadencia de revisión**: Mensual
- **Actúa cuando**: El tráfico/rankings de una página declinaron materialmente en los últimos 90 días.
- **Propósito**: Refrescar contenido en decaimiento antes de que se caiga de los rankings.
- **Habilidades usadas**: `copy-editing`, `seo-audit`, `content-strategy`
- **Cuerpo del loop**:
  1. Encontrar páginas con tráfico/rankings en declive en los últimos 90 días.
  2. Elegir las decayentes de mayor valor.
  3. Redactar un plan de refresco (actualizar estadísticas, expandir secciones delgadas, corregir el ajuste a la intención, re-enlazar).
- **Autoverificación**: ¿El decaimiento viene de la página misma, o de un cambio del SERP/estacionalidad? Refrescar solo lo que un refresco puede arreglar.
- **Estado / idempotencia**: Rastrear la fecha del último refresco por página; no volver a poner en cola una página refrescada dentro del enfriamiento.
- **Parada / salida**: Sin decayentes significativas → omitir.
- **Salida**: Una lista priorizada de refrescos con planes por página.

### El loop de internal-linking
- **Cadencia de revisión**: Al publicar/actualizar contenido, o semanal
- **Actúa cuando**: Una página publicada tiene menos enlaces internos relevantes (de entrada o salida) de los que debería.
- **Propósito**: Distribuir la autoridad de enlace y ayudar a que el contenido nuevo se descubra y posicione.
- **Habilidades usadas**: `seo-audit`, `site-architecture`, `content-strategy`
- **Cuerpo del loop**:
  1. Identificar páginas recién publicadas/actualizadas.
  2. Encontrar páginas existentes relevantes que deberían enlazar hacia ellas (y viceversa).
  3. Redactar las inserciones de enlace específicas con el anchor text.
- **Autoverificación**: ¿Cada enlace es contextualmente relevante, o es relleno de enlaces? Omitir enlaces forzados.
- **Estado / idempotencia**: Rastrear qué pares de páginas ya están enlazados; nunca sugerir un duplicado.
- **Parada / salida**: Sin objetivos de enlace relevantes → omitir. Preparar las ediciones para revisión; no editar masivamente páginas en vivo de forma autónoma.
- **Salida**: Una lista de ediciones de enlace interno específicas.

### El loop de calidad de programmatic-SEO
- **Cadencia de revisión**: Mensual
- **Actúa cuando**: Las páginas de plantilla muestran brechas de indexación, contenido delgado, duplicación, o canibalización.
- **Propósito**: Mantener saludables los grandes conjuntos de páginas con plantilla para que no arrastren a todo el dominio.
- **Habilidades usadas**: `programmatic-seo`, `seo-audit`
- **Cuerpo del loop**:
  1. Tomar una muestra del conjunto de páginas de plantilla; revisar indexación, unicidad de palabras/datos, y solapamiento de queries.
  2. Señalar páginas delgadas, duplicadas, canibalizadas, o desindexadas.
  3. Recomendar arreglar, consolidar, noindex, o podar.
- **Autoverificación**: ¿El tráfico bajo es un problema de calidad o simplemente baja demanda? No podar páginas que sirven intención real de cola larga.
- **Estado / idempotencia**: Rastrear páginas ya señaladas/accionadas; revisar de nuevo solo en el siguiente ciclo.
- **Parada / salida**: Conjunto saludable → registrar y omitir. Escalar decisiones de noindex/poda masiva a un humano.
- **Salida**: Un reporte de calidad con acciones por bucket.

### El loop de content-repurposing
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Un activo de formato largo (post/video/podcast) todavía no ha sido reutilizado.
- **Propósito**: Convertir cada activo de formato largo en una semana de contenido nativo por canal.
- **Habilidades usadas**: `social`, `content-strategy`, `copywriting`
- **Cuerpo del loop**:
  1. Encontrar el activo más nuevo aún no reutilizado.
  2. Extraer las 3–5 ideas más fuertes.
  3. Redactar versiones nativas por canal (post de LinkedIn, hilo de X, guion de formato corto).
  4. Preparar en la cola de programación.
- **Autoverificación**: ¿Cada pieza funciona por sí sola, o se lee como un volcado de enlaces? Reescribir cualquier cosa que solo funcione con el original abierto.
- **Estado / idempotencia**: Marcar los activos como reutilizados; nunca reprocesar uno.
- **Parada / salida**: Nada nuevo publicado → omitir.
- **Salida**: Borradores en la cola social para aprobación.

### El loop de relleno del content-calendar
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: El pipeline editorial tiene menos de N semanas de contenido planeado en cola.
- **Propósito**: Evitar que el pipeline de contenido se seque.
- **Habilidades usadas**: `content-strategy`, `marketing-ideas`, `seo-audit`
- **Cuerpo del loop**:
  1. Contar las piezas planeadas/en borrador que quedan en el calendario.
  2. Si está por debajo del colchón, generar nuevas ideas de tema a partir de la salida del loop de keyword-gap, preguntas de clientes, y el plan de pilares.
  3. Priorizar y ubicarlas en el calendario.
- **Autoverificación**: ¿Los nuevos temas mapean a demanda de búsqueda real o preguntas de la audiencia, y no son solo "contenido por hacer contenido"?
- **Estado / idempotencia**: Deduplicar los temas propuestos contra el calendario existente y el archivo publicado.
- **Parada / salida**: Pipeline por encima del colchón → omitir.
- **Salida**: Nuevos temas priorizados agregados al calendario.

---

## Pago

### El loop de ad-fatigue
- **Cadencia de revisión**: Cada 2–3 días
- **Actúa cuando**: Un anuncio muestra frecuencia en aumento + CTR/CVR en declive más allá de una barra de significancia real.
- **Propósito**: Refrescar la creatividad antes de que el CPA se eleve a medida que los anuncios se fatigan.
- **Habilidades usadas**: `paid-ads`, `ad-creative`, `analytics-tracking`
- **Cuerpo del loop**:
  1. Extraer métricas por anuncio: CTR, frecuencia, CPA, gasto, tendencia vs. base.
  2. Señalar anuncios en fatiga y ganadores claros.
  3. Generar 3–5 variantes frescas a partir del ángulo ganador.
  4. Preparar variantes; recomendar mover presupuesto de los fatigados hacia el ganador.
- **Autoverificación**: ¿Suficiente gasto, impresiones, y conversiones para leer el CPA más allá de la ventana de atribución, y el anuncio ya salió de la fase de aprendizaje? El aumento de frecuencia solo, con datos de conversión escasos, no es evidencia de fatiga — esperar.
- **Estado / idempotencia**: Rastrear la fecha del último refresco por anuncio; no regenerar variantes para un anuncio refrescado dentro del enfriamiento.
- **Parada / salida**: Nunca mover presupuesto o publicar automáticamente sin un checkpoint humano, a menos que los topes de gasto + una lista permitida estén explícitamente autorizados. Detenerse si el gasto diario excede su tope.
- **Salida**: Borradores de creatividad preparados + un movimiento de presupuesto recomendado.

### El loop de daily-creative-drop
- **Cadencia de revisión**: Diaria (temprano en la mañana, para que el lote esté listo cuando el comprador de medios se siente)
- **Actúa cuando**: El corpus de insumos con base en la realidad existe y los insumos requeridos están poblados — `inputs/winning-ads/` e `inputs/reviews/` (requeridos; `inputs/comments/` y `brand/` fuertemente recomendados, siguiendo las reglas de fundamentación de ad-creative). Si un insumo requerido está vacío, el loop pide los insumos en lugar de generar.
- **Propósito**: Mantener el volumen de creatividades por delante de la fatiga — un lote estándar de conceptos estáticos frescos para probar, de modo que escalar nunca se detenga esperando producción.
- **Habilidades usadas**: `ad-creative` (Modo 3 + biblioteca de plantillas de anuncios estáticos), `customer-research`
- **Cuerpo del loop**:
  1. Leer el corpus de insumos: `inputs/winning-ads/`, `inputs/reviews/`, `inputs/comments/`, y `brand/`.
  2. Generar el lote (p. ej., 50 conceptos) recorriendo las 15 plantillas estáticas, 3-4 variaciones cada una, cada concepto fundamentado en una fuente citada.
  3. Generar imágenes si hay una herramienta de imagen configurada; de lo contrario, entregar conceptos + prompts de imagen.
  4. Guardar en `outputs/AAAA-MM-DD/` con un `INDEX.md` (tipo de plantilla + fundamentación por concepto).
- **Autoverificación**: ¿Los conceptos están realmente fundamentados (verificar citas contra fuentes al azar)? ¿La cobertura de plantillas está repartida por toda la biblioteca, y no agrupada en 2-3? ¿El copy coincide con el documento de voz de marca en lugar de una voz DR genérica?
- **Estado / idempotencia**: Un lote por día — omitir si la carpeta de salida de hoy ya existe. Rastrear hashes de ángulo/titular en los lotes recientes para evitar regenerar casi-duplicados de conceptos ya entregados.
- **Parada / salida**: Insumos requeridos faltantes o vacíos → detenerse y solicitarlos; nunca generar sin fundamentación. El humano elige los 5-10 para subir — este loop prepara creatividad y **nunca publica en la cuenta de anuncios**. Si los lotes quedan sin revisar por una semana, pausar y preguntar si continuar (los lotes no elegidos son un loop de vanidad).
- **Salida**: Una carpeta con fecha de conceptos de anuncios estáticos fundamentados + índice, lista para selección humana.
- **Frescura de insumos (cadencia complementaria)**: Semanal, refrescar `inputs/winning-ads/` con lo que haya escalado y podar ejemplos obsoletos; mensual, refrescar `inputs/reviews/` e `inputs/comments/` y revisar de nuevo el documento de voz. Los insumos obsoletos son el modo de falla de este loop — la calidad de la salida sigue a la frescura de los insumos, no al número de corridas.

### El loop de monthly-creative-retro
- **Cadencia de revisión**: Mensual (primer día hábil, revisando el mes anterior)
- **Actúa cuando**: La cuenta tuvo actividad creativa significativa el mes pasado — nuevos conceptos lanzados con suficiente entrega para juzgar (respetar los umbrales de impresiones/gasto de `paid-ads`). Si nada se lanzó o nada superó los umbrales, anotarlo y omitir.
- **Propósito**: Cerrar el loop de estrategia creativa — convertir los resultados del mes pasado en el slate del próximo mes ordenado por evidencia, para que el roadmap aprenda en lugar de irse a la deriva.
- **Habilidades usadas**: `ad-creative` (Modo 4 + referencia creative-roadmap), `paid-ads` (umbrales de decisión), `analytics-tracking`
- **Cuerpo del loop**:
  1. Extraer el rendimiento de anuncios del mes pasado vía los CLIs de la plataforma; mapear resultados a los conceptos del roadmap del mes.
  2. Redactar el artefacto de retro (`retros/AAAA-MM.md`): ganadores con el porqué, perdedores con diagnóstico de etapa del funnel, victorias de una sola métrica, aprendizajes, cancelaciones.
  3. Actualizar el roadmap: volver a priorizar la evidencia del icebox, escribir los aprendizajes como conceptos nuevos/revisados, redactar el slate del próximo mes con capacidad verificada.
  4. Señalar la decisión sobre el estado de la cuenta (exploración vs. escalamiento) para confirmación humana — la recomendación de mezcla depende de eso.
- **Autoverificación**: ¿Los veredictos son sobre conceptos (no ejecuciones individuales)? ¿Cada aprendizaje aterrizó en algún lugar — actualización del icebox, re-priorización, o cancelación? ¿Algo superó los umbrales, o este mes es un omitir?
- **Estado / idempotencia**: Una retro por mes — omitir si `retros/AAAA-MM.md` ya existe. El archivo del roadmap es el estado compartido; nunca bifurcarlo.
- **Parada / salida**: Prepara solo análisis y un slate borrador — el humano aprueba el slate y la decisión sobre el estado de la cuenta; el loop **nunca lanza ni pausa anuncios**. Si las retros quedan sin leer por dos ciclos, pausar y preguntar.
- **Salida**: El artefacto de retro mensual + un roadmap actualizado con un slate borrador para el mes siguiente.

### El loop de paid-search query-mining
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Los reportes de términos de búsqueda revelan gasto desperdiciado o intención nueva.
- **Propósito**: Refinar continuamente keywords, negativas, y el mapeo a landing pages.
- **Habilidades usadas**: `paid-ads`, `analytics-tracking`
- **Cuerpo del loop**:
  1. Extraer el reporte de términos de búsqueda.
  2. Identificar términos irrelevantes (→ negativas), términos de alto rendimiento (→ nuevo exact-match), y términos cuya landing page es un mal ajuste.
  3. Preparar cambios de keyword/negativas y notas de landing page.
- **Autoverificación**: ¿Suficientes clics/conversiones por término para justificar un cambio? No negar por un solo clic.
- **Estado / idempotencia**: Rastrear negativas/keywords ya agregadas; nunca volver a agregar.
- **Parada / salida**: Ningún término supera los umbrales → omitir. Preparar cambios para revisión antes de subirlos a la cuenta.
- **Salida**: Una lista preparada de negativas, keywords nuevas, y desajustes de LP.

### El loop de retargeting-hygiene
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Las audiencias están obsoletas, son demasiado pequeñas, tienen frecuencia excesiva, o les faltan exclusiones.
- **Propósito**: Mantener el retargeting eficiente y no molesto.
- **Habilidades usadas**: `paid-ads`, `analytics-tracking`
- **Cuerpo del loop**:
  1. Revisar las audiencias de retargeting: tamaño, recencia, frecuencia, exclusiones, secuenciación de creatividad.
  2. Señalar problemas (conversores no excluidos, audiencias demasiado pequeñas para servir, frecuencia demasiado alta).
  3. Recomendar arreglos.
- **Autoverificación**: ¿La audiencia realmente tiene bajo rendimiento, o es solo pequeña-pero-valiosa? No eliminar segmentos de alta intención por su tamaño.
- **Estado / idempotencia**: Rastrear qué audiencias ya se arreglaron en este ciclo.
- **Parada / salida**: Todo saludable → omitir. Aprobación humana para eliminar audiencias.
- **Salida**: Un reporte de higiene con cambios de audiencia recomendados.

### El loop de regresión de landing-page
- **Cadencia de revisión**: Semanal (o al hacer deploy)
- **Actúa cuando**: Una página de adquisición principal regresa en conversión, velocidad, tracking, o funcionamiento del formulario.
- **Propósito**: Detectar roturas silenciosas en las páginas que reciben tráfico pagado/orgánico.
- **Habilidades usadas**: `page-cro`, `analytics-tracking`
- **Cuerpo del loop**:
  1. Monitorear las páginas de adquisición principales: tasa de conversión, velocidad de carga, envíos de formulario, disparo de tracking.
  2. Señalar regresiones vs. la base; correlacionar con deploys/cambios recientes.
  3. Diagnosticar y proponer un arreglo.
- **Autoverificación**: Descartar una rotura de tracking vs. una caída real de conversión antes de dar la alarma — y viceversa.
- **Estado / idempotencia**: Rastrear regresiones abiertas; actualizar en lugar de volver a registrarlas.
- **Parada / salida**: Sin regresión → registrar "estable." Escalar de inmediato una rotura en una página de ingresos en vivo, no esperar a la siguiente corrida.
- **Salida**: Una alerta de regresión con causa + arreglo.

---

## Earned, Social y Partnerships

### El loop de newsjacking
- **Cadencia de revisión**: Diaria
- **Actúa cuando**: Una historia en tendencia coincide con el espacio de la marca, supera la barra de valor noticioso + ajuste, **y** pasa la lista de veto.
- **Propósito**: Aprovechar noticias relevantes con un ángulo oportuno antes de que se cierre la ventana.
- **Habilidades usadas**: `public-relations`, `social`
- **Cuerpo del loop**:
  1. Escanear noticias/HN/Reddit/X en busca de historias que intersecten con el espacio del producto.
  2. Puntuar valor noticioso + ajuste + alcance.
  3. Correr la lista de veto. Para una historia principal que sobreviva, redactar un ángulo (post, pitch, o comentario).
- **Autoverificación**: ¿El ángulo es genuinamente aditivo, o forzado? Eliminar las posturas forzadas — cuestan credibilidad.
- **Lista de veto (omitir de inmediato)**: tragedias, muertes, desastres, crisis activas; historias con carga política o social a menos que la marca explícitamente tome esas posturas; temas sensibles legal/médico/financieramente; cualquier cosa proveniente de una fuente no verificada/poco confiable.
- **Estado / idempotencia**: Deduplicar por ID de historia; un ángulo por historia; nunca volver a presentar una historia ya cubierta.
- **Parada / salida**: Cualquier disparo de veto → omitir. Siempre exigir aprobación humana antes de presentar/publicar. La mayoría de los días se omitirá — eso es correcto.
- **Salida**: Un post/pitch preparado para aprobación humana, o nada.

### El loop de social-listening
- **Cadencia de revisión**: Diaria
- **Actúa cuando**: Un hilo/mención supera la puntuación de ajuste al ICP + intención + alcance.
- **Propósito**: Detectar las conversaciones de mayor valor en las que participar, en lugar de scrollear feeds.
- **Habilidades usadas**: `social` (ver su `references/listening.md`), `community-marketing`
- **Cuerpo del loop**:
  1. Extraer menciones e hilos relevantes de las fuentes configuradas.
  2. Puntuar por ajuste al ICP, intención, alcance, y oportunidad de comentario.
  3. Redactar comentarios/respuestas para los principales.
- **Autoverificación**: ¿Un humano reconocería cada respuesta como genuinamente útil, no promocional?
- **Estado / idempotencia**: Rastrear hilos ya trabajados; nunca responder dos veces. Respetar un enfriamiento de interacción por cuenta.
- **Parada / salida**: Nada supera el umbral → omitir. Preparar respuestas para publicación humana (no auto-publicar — detección de bots + riesgo de marca).
- **Salida**: Una lista corta de hilos con respuestas redactadas y en tono de marca.

### El loop de community-engagement
- **Cadencia de revisión**: Diaria
- **Actúa cuando**: Una comunidad objetivo (subreddit/Slack/Discord/foro) tiene un hilo relevante donde encaja una respuesta útil y no promocional.
- **Propósito**: Construir presencia y confianza duraderas en las comunidades donde vive el ICP.
- **Habilidades usadas**: `community-marketing`, `social`
- **Cuerpo del loop**:
  1. Escanear las comunidades configuradas en busca de hilos/preguntas relevantes.
  2. Puntuar por oportunidad de ayuda genuina (no solo coincidencia de keywords).
  3. Redactar respuestas centradas en el valor; anotar cuáles ameritan un recurso más largo.
- **Autoverificación**: ¿La respuesta lidera con ayuda y respeta las normas de la comunidad? La proporción de auto-promoción se mantiene baja.
- **Estado / idempotencia**: Rastrear hilos trabajados + cadencia de publicación por comunidad para evitar sobre-publicar.
- **Parada / salida**: Sin oportunidad genuina de ayuda → omitir. Preparar para revisión humana donde las comunidades sean estrictas con vendedores.
- **Salida**: Respuestas de comunidad redactadas + ideas de recursos.

### El loop de competitor-watch
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Un competidor hace un cambio sustantivo de precios, posicionamiento, producto, o mensajería.
- **Propósito**: Detectar movimientos de la competencia lo bastante pronto para responder.
- **Habilidades usadas**: `competitor-profiling`, `competitor-alternatives`, `product-marketing-context`
- **Cuerpo del loop**:
  1. Obtener las páginas de precios, homepages, changelogs, y posts recientes de la competencia.
  2. Comparar contra el último snapshot.
  3. Resumir los cambios significativos; señalar cualquier cosa que necesite una respuesta (actualización de página de comparación, contra-mensajería).
- **Autoverificación**: ¿Sustantivo o cosmético? No presentar un ajuste de copy como un giro estratégico.
- **Estado / idempotencia**: Almacenar snapshots por competidor; comparar contra el último, y no volver a señalar un cambio ya conocido.
- **Parada / salida**: Sin diferencias significativas → registrar "sin cambios."
- **Salida**: Un digest de cambios + respuestas recomendadas.

### El loop de backlink-prospecting
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Aparecen nuevos objetivos relevantes de enlace/guest-post/mención (o el pipeline está flaco).
- **Propósito**: Mantener un flujo constante de link building y oportunidades de mención earned.
- **Habilidades usadas**: `public-relations`, `seo-audit`
- **Cuerpo del loop**:
  1. Encontrar nuevos prospectos: sitios que enlazan a competidores, roundups relevantes, menciones de marca sin enlace, páginas de recursos.
  2. Calificar por relevancia + autoridad.
  3. Redactar ángulos de outreach para los objetivos principales.
- **Autoverificación**: ¿El objetivo es genuinamente relevante, o es un enlace de baja calidad que podría dañar? Omitir sitios spam.
- **Estado / idempotencia**: Rastrear objetivos ya contactados + resultados; respetar una cadencia de seguimiento, no volver a presentar en frío.
- **Parada / salida**: Sin objetivos nuevos calificados → omitir. Aprobación humana para los envíos de outreach.
- **Salida**: Una lista de prospectos calificados con outreach redactado.

### El loop de directory-submission
- **Cadencia de revisión**: Mensual
- **Actúa cuando**: Existe un nuevo directorio/plataforma de lanzamiento/marketplace relevante en el que el producto no está listado.
- **Propósito**: Expandir constantemente la distribución y el rastro de referidos/SEO vía directorios.
- **Habilidades usadas**: `directory-submissions`
- **Cuerpo del loop**:
  1. Revisar directorios, sitios de lanzamiento, y marketplaces nuevos/relevantes.
  2. Calificar por relevancia, autoridad, y ajuste de audiencia.
  3. Preparar copy/activos de listado para los principales.
- **Autoverificación**: ¿Valor real de audiencia/SEO, o una granja de enlaces? Omitir directorios de baja calidad.
- **Estado / idempotencia**: Mantener una lista de directorios ya enviados; nunca volver a enviar.
- **Parada / salida**: Sin directorios nuevos que valgan la pena → omitir.
- **Salida**: Listados preparados para envío.

### El loop de partner-pipeline
- **Cadencia de revisión**: Mensual
- **Actúa cuando**: Surge una oportunidad viable de co-marketing, integración, afiliado, o intercambio de newsletter (o el pipeline está flaco).
- **Propósito**: Mantener un pipeline fresco de oportunidades de partnership y co-marketing.
- **Habilidades usadas**: `co-marketing`, `referral-program`
- **Cuerpo del loop**:
  1. Buscar socios potenciales (herramientas complementarias, audiencias alineadas, newsletters activas, objetivos de integración).
  2. Calificar por solapamiento de audiencia + alcance + ajuste.
  3. Redactar outreach de partnership/intercambio para los prospectos principales.
- **Autoverificación**: ¿Solapamiento de audiencia real y valor mutuo, o una petición unilateral? Omitir los desajustes.
- **Estado / idempotencia**: Rastrear socios contactados + estado; respetar la cadencia de seguimiento.
- **Parada / salida**: Sin oportunidades calificadas → omitir. Aprobación humana para el outreach.
- **Salida**: Una lista de socios calificados con outreach redactado.

---

## Activación

### El loop de onboarding drop-off
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: La caída de un paso del onboarding excede el benchmark o regresa vs. el período anterior.
- **Propósito**: Encontrar y arreglar la fuga más grande entre el registro y el primer valor.
- **Habilidades usadas**: `onboarding-cro`, `analytics-tracking`, `page-cro`
- **Cuerpo del loop**:
  1. Extraer el funnel de activación paso a paso (registro → acción clave → momento aha).
  2. Identificar el paso con la peor caída vs. el benchmark y el período anterior.
  3. Diagnosticar la causa probable; proponer un arreglo enfocado + cómo medirlo.
- **Autoverificación**: ¿Suficientes usuarios nuevos pasando por el funnel para que las tasas por paso sean significativas?
- **Estado / idempotencia**: Rastrear qué arreglos ya se propusieron/lanzaron; medir su efecto antes de volver a tocarlos.
- **Parada / salida**: Muestra demasiado pequeña → ampliar la ventana u omitir.
- **Salida**: Un arreglo de activación priorizado con un plan de medición.

### El loop de signup-funnel-leak
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Un paso de registro/checkout regresa vs. la base.
- **Propósito**: Mantener convirtiendo el camino de registro/checkout a medida que el sitio cambia.
- **Habilidades usadas**: `signup-flow-cro`, `page-cro`, `analytics-tracking`, `ab-test-setup`
- **Cuerpo del loop**:
  1. Extraer la conversión por paso a lo largo del flujo de registro/checkout.
  2. Comparar contra la base; señalar regresiones (un deploy o cambio de copy puede haberlo dañado).
  3. Redactar una hipótesis + prueba para el peor paso (pasar la ejecución de la prueba a `ab-test-setup`).
- **Autoverificación**: Descartar una rotura de tracking antes de declarar una caída real.
- **Estado / idempotencia**: Rastrear regresiones abiertas + pruebas en curso; no iniciar una prueba en conflicto.
- **Parada / salida**: Sin regresión y sin idea que valga la pena probar → omitir.
- **Salida**: Un brief de experimento priorizado para `ab-test-setup`.

### El loop de lead-capture-asset
- **Cadencia de revisión**: Mensual
- **Actúa cuando**: Un lead magnet, herramienta gratuita, u opt-in tiene bajo rendimiento en tasa de captura.
- **Propósito**: Mantener convirtiendo visitantes en leads a los activos de captura de top-of-funnel (lead magnets + herramientas gratuitas).
- **Habilidades usadas**: `lead-magnets`, `free-tool-strategy`, `page-cro`, `popup-cro`
- **Cuerpo del loop**:
  1. Extraer la conversión vista → captura de cada lead magnet, herramienta gratuita, y opt-in.
  2. Señalar los de bajo rendimiento vs. benchmark; diagnosticar (oferta, ubicación, fricción del formulario, segmentación).
  3. Proponer un arreglo o refresco (nuevo ángulo, mejor ubicación, menos fricción).
- **Autoverificación**: ¿Suficiente tráfico por activo para que la tasa de captura sea significativa?
- **Estado / idempotencia**: Rastrear la fecha de última optimización por activo; enfriamiento antes de volver a tocarlo.
- **Parada / salida**: Todos los activos saludables → omitir.
- **Salida**: Un arreglo priorizado por cada activo de bajo rendimiento.

### El loop de feature-adoption
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Una función pegajosa/valiosa está subutilizada por un segmento que se beneficiaría de ella.
- **Propósito**: Impulsar la adopción de las funciones que correlacionan con la retención.
- **Habilidades usadas**: `onboarding-cro`, `email-sequence`, `analytics-tracking`
- **Cuerpo del loop**:
  1. Identificar las funciones de alta correlación con retención y los segmentos que no las usan.
  2. Elegir el cruce función × segmento de mayor apalancamiento.
  3. Redactar un empujón in-app o correo para impulsar la adopción.
- **Autoverificación**: ¿La función es genuinamente valiosa para ese segmento, o el empujón sería ruido? No empujar funciones que la gente racionalmente omite.
- **Estado / idempotencia**: Rastrear a quién ya se le empujó para qué función; imponer un enfriamiento; suprimir a los que ya la adoptaron.
- **Parada / salida**: Sin brecha clara de función × segmento → omitir.
- **Salida**: Un empujón de adopción preparado.

---

## Retención

### El loop de churn-signal
- **Cadencia de revisión**: Diaria (o por disparador)
- **Actúa cuando**: Una cuenta cruza recién un umbral de riesgo de churn y no está ya en una intervención.
- **Propósito**: Intervenir dentro de la ventana corta antes de que una cuenta en riesgo se vaya.
- **Habilidades usadas**: `churn-prevention`, `analytics-tracking`, `email-sequence`
- **Cuerpo del loop**:
  1. Puntuar cuentas en señales de riesgo de churn (declive de uso, caída de asientos, dunning, escaladas de soporte).
  2. Segmentar las cuentas recién en riesgo.
  3. Emparejar cada una con la intervención correcta (correo de re-engagement, outreach de CS, oferta); prepararla.
- **Autoverificación**: ¿La "caída" es una tendencia real o un bajón de fin de semana/festivo? Comparar contra la propia base de la cuenta.
- **Estado / idempotencia**: Nunca volver a disparar sobre una cuenta ya en una intervención activa; imponer un enfriamiento entre intentos.
- **Parada / salida**: Sin cuentas nuevas en riesgo → omitir. Escalar las cuentas de alto valor a un humano en lugar de enviarles correo automáticamente.
- **Salida**: Una lista priorizada de cuentas en riesgo con intervenciones preparadas.

### El loop de lifecycle-email-refresh
- **Cadencia de revisión**: Mensual
- **Actúa cuando**: Un correo de una secuencia tiene bajo rendimiento en engagement real o contiene contenido obsoleto.
- **Propósito**: Mantener las secuencias automatizadas funcionando a medida que el producto y la audiencia evolucionan.
- **Habilidades usadas**: `email-sequence`, `analytics-tracking`, `copy-editing`
- **Cuerpo del loop**:
  1. Extraer el rendimiento por correo — clics, conversiones, respuestas, bajas, quejas de spam, rebotes (**no aperturas** — el tracking de aperturas es poco confiable tras los cambios de privacidad).
  2. Señalar los de bajo rendimiento y las referencias obsoletas (funciones antiguas, fechas, precios).
  3. Redactar reescrituras o pruebas de línea de asunto para los de peor rendimiento.
- **Autoverificación**: ¿Suficientes envíos por correo para que las tasas sean significativas?
- **Estado / idempotencia**: Rastrear la fecha de última revisión por correo; enfriamiento antes de volver a probar.
- **Parada / salida**: Todas las secuencias saludables → omitir. **Pausar y escalar cualquier secuencia con tasas de quejas/rebotes en aumento** — eso es una emergencia de deliverability, no un ajuste de copy.
- **Salida**: Reescrituras de correo preparadas + pruebas de línea de asunto.

### El loop de re-engagement
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Un usuario cruza recién el umbral de inactividad.
- **Propósito**: Recuperar usuarios dormidos antes de que se pierdan para siempre.
- **Habilidades usadas**: `email-sequence`, `sms`, `offers`
- **Cuerpo del loop**:
  1. Identificar usuarios que recién cruzan el umbral de inactividad.
  2. Elegir el ángulo de win-back (función nueva, oferta, "te extrañamos," aviso de baja definitiva).
  3. Redactar el mensaje; establecer supresión para que no se les vuelva a impactar la próxima semana.
- **Autoverificación**: ¿Genuinamente dormido, o solo un usuario de baja frecuencia por diseño? No molestar a cuentas saludables.
- **Estado / idempotencia**: Rastrear intentos de win-back por usuario; suprimir tras cada envío durante el enfriamiento.
- **Parada / salida**: Tras N intentos sin éxito, pasar a baja definitiva — no otro correo más.
- **Salida**: Un mensaje de win-back preparado + una lista de supresión actualizada.

### El loop de email-deliverability
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Las tasas de rebote, queja, o baja suben, o la higiene de la lista decae.
- **Propósito**: Proteger la reputación del remitente y la entrega en la bandeja de entrada.
- **Habilidades usadas**: `email-sequence`, `analytics-tracking`
- **Cuerpo del loop**:
  1. Monitorear rebotes, quejas de spam, bajas, salud de dominio/DKIM/SPF/DMARC, y señales de colocación en bandeja de entrada.
  2. Señalar tasas de problema en aumento o incidencias de autenticación.
  3. Recomendar acciones: suprimir rebotes duros, dar de baja a los crónicamente no comprometidos, arreglar la autenticación, moderar el ritmo de envío.
- **Autoverificación**: ¿Un pico es algo puntual de un envío o una tendencia? Correlacionar con campañas recientes.
- **Estado / idempotencia**: Rastrear direcciones ya suprimidas + fecha del último barrido de higiene.
- **Parada / salida**: Todas las métricas saludables → registrar y omitir. **Escalar de inmediato un pico en la tasa de quejas** — el daño de reputación se acumula rápido.
- **Salida**: Un reporte de deliverability + una lista de acciones de supresión/higiene.

### El loop de voice-of-customer
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Ha llegado retroalimentación nueva (NPS, encuestas, tickets de soporte, reseñas, llamadas).
- **Propósito**: Enrutar la retroalimentación a la acción correcta **y** minarla para insumos de marketing.
- **Habilidades usadas**: `customer-research`, `churn-prevention`, `referral-program`, `copywriting`
- **Cuerpo del loop**:
  1. Recolectar retroalimentación nueva de todas las fuentes.
  2. Enrutar: detractores/en riesgo → gestión de rescate (`churn-prevention`); promotores → petición de referido/reseña (`referral-program`); dolor/deseo recurrente → insumos de experimento y copy.
  3. Extraer lenguaje textual de clientes para copy, FAQ, y manejo de objeciones.
- **Autoverificación**: ¿Un tema es un patrón real o una sola voz ruidosa? Exigir un conteo mínimo antes de actuar sobre él.
- **Estado / idempotencia**: Rastrear IDs de retroalimentación ya procesados; nunca enrutar el mismo elemento dos veces.
- **Parada / salida**: Sin retroalimentación nueva → omitir. Escalar quejas sensibles/legales a un humano.
- **Salida**: Acciones enrutadas + un digest de lenguaje/insight para marketing.

---

## Ingresos

### El loop de trial-conversion
- **Cadencia de revisión**: Diaria
- **Actúa cuando**: Un usuario en prueba alcanza un momento relevante para la conversión (mitad de prueba, cerca de vencer, activado-pero-no-pagado).
- **Propósito**: Mover más pruebas a pago con empujones bien cronometrados.
- **Habilidades usadas**: `email-sequence`, `paywall-upgrade-cro`, `analytics-tracking`, `offers`
- **Cuerpo del loop**:
  1. Segmentar las pruebas activas por etapa y nivel de activación.
  2. Emparejar cada una con el empujón correcto (resumen de valor, tip de caso de uso, empujón de casi-vencimiento, oferta).
  3. Preparar el empujón.
- **Autoverificación**: ¿El usuario está lo bastante activado para que un empujón de pago funcione, o necesita más valor primero?
- **Estado / idempotencia**: Rastrear empujones enviados por prueba; imponer cadencia; suprimir a los que ya convirtieron.
- **Parada / salida**: Sin pruebas en una etapa accionable → omitir. No sobre-mensajear a una sola prueba.
- **Salida**: Empujones de prueba preparados y apropiados para la etapa.

### El loop de PQL / upgrade-intent
- **Cadencia de revisión**: Diaria
- **Actúa cuando**: Un usuario gratuito/en prueba muestra intención de compra calificada por producto (límites de uso, uso de función clave, invitaciones de equipo).
- **Propósito**: Detectar usuarios de alta intención y preparar outreach de actualización en el momento correcto.
- **Habilidades usadas**: `analytics-tracking`, `sales-enablement`, `revops`
- **Cuerpo del loop**:
  1. Puntuar a los usuarios gratuitos/en prueba en señales de PQL.
  2. Detectar los usuarios recién calificados.
  3. Preparar la gestión correcta (prompt de actualización in-app, asistencia de ventas para alto valor, correo dirigido).
- **Autoverificación**: ¿La señal es intención de compra genuina o uso incidental? Calibrar el umbral para evitar falsos positivos.
- **Estado / idempotencia**: Rastrear los PQL ya accionados; no volver a enrutar dentro del enfriamiento.
- **Parada / salida**: Sin usuarios recién calificados → omitir. Enrutar las cuentas de alto valor a un humano, no cerrar automáticamente.
- **Salida**: Una lista de PQL priorizada con gestiones preparadas.

### El loop de pricing-page-experiment
- **Cadencia de revisión**: Mensual (las pruebas duran más)
- **Actúa cuando**: No hay ninguna prueba corriendo en la página y existe una hipótesis que valga la pena — o una prueba en curso concluyó.
- **Propósito**: Mejorar continuamente la conversión de la página de precios **y la calidad de los ingresos**.
- **Habilidades usadas**: `pricing-strategy`, `ab-test-setup`, `page-cro`
- **Cuerpo del loop**:
  1. Revisar la conversión de la página de precios, la mezcla de planes, y los ingresos por visitante.
  2. Generar una hipótesis de precios/empaquetado/copy, o leer una prueba concluida.
  3. Pasar el diseño/análisis a `ab-test-setup`; promover un ganador claro.
- **Autoverificación**: Juzgar a los ganadores por **ingresos por visitante, mezcla de planes, reembolsos, downgrades, churn, y carga de soporte — no solo la tasa de conversión.** ¿La prueba en curso ya es estadísticamente concluyente antes de darla por terminada?
- **Estado / idempotencia**: Rastrear la prueba en curso + el log de pruebas concluidas; nunca iniciar una prueba en conflicto en la misma página.
- **Parada / salida**: Una prueba está en curso → esperar. **No promover una variante que eleva la conversión pero baja los ingresos por visitante o sube los reembolsos/churn.**
- **Salida**: Un resultado de prueba + la siguiente hipótesis.

### El loop de paywall-optimization
- **Cadencia de revisión**: Mensual
- **Actúa cuando**: No hay ninguna prueba de paywall corriendo y existe una hipótesis — o una concluyó.
- **Propósito**: Mejorar la conversión de actualización in-app sin degradar la calidad de los ingresos.
- **Habilidades usadas**: `paywall-upgrade-cro`, `ab-test-setup`, `analytics-tracking`
- **Cuerpo del loop**:
  1. Extraer la conversión vista → actualización del paywall y los puntos de abandono.
  2. Formar una hipótesis (momento del disparador, encuadre, ancla de plan), o leer una prueba concluida.
  3. Pasar la ejecución a `ab-test-setup`.
- **Autoverificación**: Segmentar por plan/cohorte — un número agregado puede esconder un segmento que se está hundiendo. Vigilar reembolsos/downgrades junto con la conversión.
- **Estado / idempotencia**: Rastrear pruebas en curso/concluidas; sin pruebas en conflicto.
- **Parada / salida**: Prueba en curso → esperar. No promover una victoria de conversión que eleva reembolsos o churn.
- **Salida**: Un resultado de prueba + la siguiente hipótesis.

### El loop de expansion / upsell
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Una cuenta pagada existente alcanza una señal de expansión (uso cerca de los límites, asientos agregados, nuevo caso de uso).
- **Propósito**: Hacer crecer los ingresos de clientes existentes vía upsell/cross-sell bien cronometrado.
- **Habilidades usadas**: `revops`, `sales-enablement`, `email-sequence`
- **Cuerpo del loop**:
  1. Puntuar las cuentas pagadas en señales de expansión.
  2. Detectar las cuentas recién listas para expansión.
  3. Preparar la gestión correcta (prompt de actualización basado en uso, outreach de CSM, oferta de cross-sell).
- **Autoverificación**: ¿La cuenta está lo bastante saludable como para que un upsell no dañe la relación? No hacer upsell a una cuenta en riesgo — eso es trabajo del loop de churn.
- **Estado / idempotencia**: Rastrear los toques de upsell por cuenta; imponer cadencia.
- **Parada / salida**: Sin cuentas listas para expansión → omitir. Enrutar las cuentas estratégicas a un humano.
- **Salida**: Una lista de expansión priorizada con gestiones preparadas.

### El loop de failed-payment / dunning
- **Cadencia de revisión**: Diaria
- **Actúa cuando**: Un pago falla o una tarjeta está por vencer.
- **Propósito**: Recuperar el churn involuntario — a menudo el trabajo de retención de mayor ROI.
- **Habilidades usadas**: `revops`, `email-sequence`
- **Cuerpo del loop**:
  1. Detectar pagos fallidos y vencimientos de tarjeta próximos.
  2. Disparar la secuencia de dunning (calendario de reintentos + mensajería escalada de actualización de tarjeta).
  3. Enrutar los fallos persistentes a un humano/CS.
- **Autoverificación**: ¿El fallo es involuntario (problema de tarjeta) vs. una cancelación intencional? No perseguir con dunning a alguien que eligió irse.
- **Estado / idempotencia**: Rastrear la etapa de dunning por cuenta; seguir el calendario de reintentos; detenerse al recuperar el pago.
- **Parada / salida**: Tras el reintento final, escalar/desactivar según política — no correr para siempre.
- **Salida**: Una cola de dunning activa + estado de recuperación.

---

## Referidos y Advocacy

### El loop de referral-nudge
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Un usuario alcanza un "momento feliz" (hito, NPS positivo) y no se le ha pedido nada recientemente.
- **Propósito**: Pedir referidos cuando los usuarios están más contentos.
- **Habilidades usadas**: `referral-program`, `email-sequence`
- **Cuerpo del loop**:
  1. Identificar usuarios que acaban de alcanzar un momento feliz y no están en el enfriamiento de petición.
  2. Emparejar con la petición correcta (enlace para compartir, incentivo, solicitud de reseña).
  3. Preparar la petición.
- **Autoverificación**: ¿Genuinamente un momento feliz, o solo cualquier evento? Una petición mal cronometrada erosiona la buena voluntad.
- **Estado / idempotencia**: Imponer un enfriamiento — nunca pedirle al mismo usuario dos veces dentro de la ventana.
- **Parada / salida**: Nadie en un momento feliz → omitir.
- **Salida**: Una petición de referido preparada y bien cronometrada.

### El loop de review-and-UGC-harvest
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Han aparecido reseñas, testimonios, o contenido generado por usuarios nuevos.
- **Propósito**: Mantener un flujo constante de prueba social y enrutarlo hacia marketing.
- **Habilidades usadas**: `social`, `referral-program`, `sales-enablement`, `page-cro`
- **Cuerpo del loop**:
  1. Recolectar reseñas/testimonios/UGC/menciones nuevas desde la última corrida.
  2. Ordenar por fuerza y relevancia.
  3. Redactar a dónde debería ir cada uno (sección de prueba del sitio, anuncio, post social, deck de ventas).
  4. Señalar cualquier cosa negativa para respuesta humana.
- **Autoverificación**: ¿Es genuinamente fuerte y coherente con el mensaje? No forzar prueba débil hacia una ubicación prime.
- **Estado / idempotencia**: Rastrear los elementos ya cosechados; nunca reutilizar el mismo dos veces.
- **Parada / salida**: **Verificar el consentimiento y el ToS de la plataforma antes de reutilizar públicamente; agregar la divulgación requerida por la FTC para contenido incentivado.** Sin consentimiento verificable, o la plataforma prohíbe la reutilización → no usar. Negativo/sensible → escalar a un humano, no auto-publicar.
- **Salida**: Nuevos activos de prueba enrutados a sus destinos.

### El loop de review-site-management
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Llegan reseñas nuevas en G2/Capterra/tiendas de apps, o los listados se desactualizan.
- **Propósito**: Mantener la reputación y la conversión en plataformas de reseñas de terceros.
- **Habilidades usadas**: `sales-enablement`, `social`, `page-cro`
- **Cuerpo del loop**:
  1. Rastrear reseñas nuevas a través de sitios de reseñas/tiendas de apps.
  2. Redactar respuestas (agradecer a los promotores, atender a los detractores constructivamente).
  3. Señalar actualizaciones de listado necesarias (capturas de pantalla, funciones, precios).
- **Autoverificación**: ¿La respuesta es específica y no defensiva? Nunca discutir públicamente con un reseñador.
- **Estado / idempotencia**: Rastrear reseñas respondidas; nunca responder dos veces.
- **Parada / salida**: Sin reseñas/actualizaciones nuevas → omitir. Aprobación humana para respuestas a reseñas negativas/sensibles legalmente.
- **Salida**: Respuestas redactadas + un checklist de actualización de listado.

### El loop de case-study-sourcing
- **Cadencia de revisión**: Mensual
- **Actúa cuando**: Un cliente alcanza un éxito digno de caso de estudio (resultados fuertes, hito, retroalimentación entusiasta).
- **Propósito**: Mantener un pipeline de casos de estudio e historias de clientes.
- **Habilidades usadas**: `sales-enablement`, `customer-research`, `referral-program`
- **Cuerpo del loop**:
  1. Identificar clientes con resultados/engagement sobresalientes.
  2. Calificar para un caso de estudio (resultados, disposición, valor del logo).
  3. Redactar el outreach + las preguntas de entrevista.
- **Autoverificación**: ¿Los resultados son reales y atribuibles, o coincidentes? Verificar antes de presentar una historia.
- **Estado / idempotencia**: Rastrear clientes abordados + estado; respetar un enfriamiento de no-repetición.
- **Parada / salida**: Sin candidatos calificados → omitir. Aprobación humana para el outreach a clientes.
- **Salida**: Una lista de candidatos con outreach redactado.

---

## Operaciones Continuas / Meta

### El loop de weekly-marketing-review
- **Cadencia de revisión**: Semanal (lunes 9am)
- **Actúa cuando**: Siempre corre — este es el heartbeat. "Actúa" señalando los movimientos notables de la semana.
- **Propósito**: Un pulso de funnel completo permanente para que nada se le vaya de las manos sin ser notado.
- **Habilidades usadas**: `analytics-tracking`, `marketing-plan`, `marketing-ideas`
- **Cuerpo del loop**:
  1. Extraer las métricas AARRR principales vs. la semana pasada y vs. el plan.
  2. Señalar el mayor movimiento (bueno y malo) por etapa.
  3. Vincular cada señal al loop o habilidad que debería actuar sobre ella; sugerir 1–2 ideas de experimento.
- **Autoverificación**: Distinguir tendencia de ruido antes de dar la alarma.
- **Estado / idempotencia**: Almacenar el snapshot de cada semana para deltas semana-a-semana precisos.
- **Parada / salida**: Desactivación manual + detención por error. Ante una caída de la fuente de datos, reportar "datos obsoletos," nunca movimiento inventado. (No "n/a" — incluso el heartbeat necesita un interruptor de apagado y una ruta de error.)
- **Salida**: Un digest semanal de una página con dueños/próximas acciones.

### El loop de experiment-backlog
- **Cadencia de revisión**: Semanal
- **Actúa cuando**: Existen hipótesis nuevas para registrar, el backlog necesita re-priorización, o un slot de prueba está libre.
- **Propósito**: Mantener el pipeline de experimentos lleno y priorizado. **Envoltorio delgado — delegar todo el diseño de pruebas, análisis estadístico, y gestión de velocidad a `ab-test-setup`.**
- **Habilidades usadas**: `ab-test-setup` (dueño), `page-cro`, `analytics-tracking`
- **Cuerpo del loop**:
  1. Cosechar hipótesis nuevas de la semana (datos, investigación, competidores, soporte, otros loops).
  2. Volver a priorizar el backlog con ICE.
  3. Si un slot está libre, entregar la idea principal a `ab-test-setup`; si una prueba concluyó ahí, registrar el aprendizaje.
- **Autoverificación**: ¿La idea principal es realmente probable con el tráfico actual, o está inflada por ICE?
- **Estado / idempotencia**: Deduplicar las hipótesis entrantes contra el backlog; rastrear qué pruebas están en curso.
- **Parada / salida**: Backlog lleno y una prueba corriendo → solo registrar ideas nuevas. No duplicar el trabajo de `ab-test-setup`.
- **Salida**: Un backlog actualizado y priorizado (la fuente de verdad vive con `ab-test-setup`).

### El loop de analytics-anomaly
- **Cadencia de revisión**: Diaria
- **Actúa cuando**: Una métrica rastreada rompe su banda esperada (pico o caída más allá de la varianza normal).
- **Propósito**: Detectar cualquier cosa que se rompa — buena o mala — antes de que corra días sin ser notada.
- **Habilidades usadas**: `analytics-tracking`
- **Cuerpo del loop**:
  1. Revisar las métricas clave (tráfico, registros, conversión, ingresos, gasto) contra su rango normal.
  2. Señalar anomalías; separar "evento real" de "artefacto de tracking."
  3. Enrutar cada una al loop/dueño responsable para diagnóstico.
- **Autoverificación**: ¿La anomalía es real o un artefacto de tracking/estacionalidad? Revisar causas conocidas (festivo, lanzamiento, deploy) antes de alarmar.
- **Estado / idempotencia**: Rastrear anomalías ya alertadas; no volver a alertar la misma en curso a diario.
- **Parada / salida**: Todas las métricas dentro de banda → silencio (sin alerta = bueno). Escalar de inmediato una anomalía de ingresos/gasto.
- **Salida**: Una alerta de anomalía enrutada a un dueño, o nada.

### El loop de brand-mention / reputation
- **Cadencia de revisión**: Diaria
- **Actúa cuando**: Aparece una mención de marca significativa en cualquier lugar (no solo donde estás escuchando para engagement).
- **Propósito**: Monitorear y proteger la reputación; responder donde importa.
- **Habilidades usadas**: `social`, `public-relations`
- **Cuerpo del loop**:
  1. Escanear la web abierta/social/foros en busca de menciones de marca.
  2. Clasificar sentimiento + alcance + riesgo.
  3. Enrutar: positiva → amplificar/agradecer; negativa/riesgosa → respuesta redactada para revisión humana; mención sin enlace → loop de backlink-prospecting.
- **Autoverificación**: ¿Una mención negativa necesita respuesta, o participar la amplificaría? Juzgar alcance + legitimidad.
- **Estado / idempotencia**: Deduplicar por ID de mención; rastrear las menciones trabajadas.
- **Parada / salida**: Sin menciones significativas → omitir. **Siempre exigir aprobación humana para respuestas a menciones negativas/de crisis** — nunca responder automáticamente a una queja.
- **Salida**: Un digest de menciones con acciones enrutadas.

### El loop de tracking-QA
- **Cadencia de revisión**: Semanal (y al hacer deploy / lanzar campaña)
- **Actúa cuando**: Analytics, píxeles, UTMs, o eventos de conversión están faltando, fallando, o mal configurados.
- **Propósito**: Mantener confiable la capa de medición — cada otro loop depende de ella.
- **Habilidades usadas**: `analytics-tracking`
- **Cuerpo del loop**:
  1. Verificar que los eventos clave disparan correctamente, los píxeles están presentes, las UTMs son consistentes, y las conversiones se atribuyen.
  2. Señalar tracking roto/faltante/duplicado, especialmente después de deploys o campañas nuevas.
  3. Recomendar arreglos.
- **Autoverificación**: ¿Realmente está roto, o es un cambio esperado? Confirmar contra una base conocida como buena.
- **Estado / idempotencia**: Rastrear incidencias de tracking abiertas; actualizar en lugar de volver a registrarlas.
- **Parada / salida**: Todo el tracking saludable → registrar "limpio." **Escalar de inmediato un evento de ingresos/conversión roto** — cada loop río abajo está a ciegas hasta que se arregle.
- **Salida**: Un reporte de tracking-QA con arreglos priorizados.

### El loop de campaign-postmortem
- **Cadencia de revisión**: Al finalizar la campaña (basado en eventos)
- **Actúa cuando**: Una campaña (lanzamiento, promo, empuje estacional) concluye.
- **Propósito**: Capturar resultados, aprendizajes, y activos reutilizables para que cada campaña se acumule.
- **Habilidades usadas**: `analytics-tracking`, `marketing-plan`
- **Cuerpo del loop**:
  1. Extraer los resultados finales de la campaña vs. las metas.
  2. Capturar qué funcionó, qué no, y por qué; guardar activos reutilizables (copy, creatividad, flujos de trabajo).
  3. Alimentar los aprendizajes al backlog de experimentos y al siguiente plan; registrar seguimientos.
- **Autoverificación**: ¿Las conclusiones están respaldadas por los datos, o son una narrativa retrospectiva? Separar correlación de causa.
- **Estado / idempotencia**: Una retrospectiva por campaña; no volver a correr sobre una campaña ya documentada.
- **Parada / salida**: Sin campaña concluida → omitir.
- **Salida**: Un documento de retrospectiva + insumos para el backlog/plan.

---

## Adaptar y crear loops

Para adaptar un loop: conserva las nueve partes de la anatomía, sustituye habilidades/umbrales por el stack del usuario, y vuelve a ajustar la cadencia a la velocidad de la señal. Para crear uno completamente nuevo: usa `loop-template.md` (plantilla de copiar y pegar + prompts para completar + ejemplo resuelto + checklist de lanzamiento). En cualquier caso, no lances un loop hasta que cada parte esté completa — especialmente **Estado / idempotencia**, **Autoverificación**, y **Parada / salida**. Un loop sin eso no es un sistema; es una forma de hacer lo incorrecto según un horario, repetidamente, a las mismas personas.
