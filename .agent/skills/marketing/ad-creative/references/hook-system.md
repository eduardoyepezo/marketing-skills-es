# El Sistema de Hooks

Los primeros tres segundos deciden si el resto del anuncio existe. Los hooks son la unidad de mayor apalancamiento del trabajo de creatividad para performance — y la *diversidad* de hooks es lo que gana aprendizaje incremental: hooks distintos llegan a bolsillos distintos de la audiencia, mientras que aperturas casi idénticas mayormente re-testean lo que ya sabes sobre ese mismo bolsillo. Esta referencia es un sistema completo para generar, diagnosticar e iterar hooks — no una lista de frases sueltas.

Úsala dentro de la generación del Modo 1/3 (hooks para conceptos nuevos), la iteración del Modo 2 (diagnosticar por qué un anuncio tiene bajo rendimiento), y el loop de estrategia de creatividades en [creative-roadmap.md](creative-roadmap.md).

---

## Un Hook Son Tres Componentes, No una Línea

En video, el hook es la combinación simultánea de:

| Componente | Qué es | Trabajo |
|---|---|---|
| **Acción visual** | Lo que literalmente ocurre en pantalla en los segundos 0–3 | Detener el pulgar |
| **Línea hablada** | Las primeras palabras de la VO o del diálogo | Abrir el loop |
| **Texto de caption** | Texto de encabezado/overlay en pantalla | Anclar la afirmación para viewers con sonido apagado |

**La regla de no duplicación:** los tres componentes deben complementarse, nunca repetirse. Si la VO dice "dejé de pagar $200/mes por mi gimnasio" mientras el caption dice "dejé de pagar $200/mes" sobre una toma estática de una persona hablando, dos de los tres espacios se desperdician. Los hooks fuertes dividen el trabajo — el visual muestra el correo de cancelación, la VO dice la línea, el caption nombra la alternativa. Al escribir hooks, escribe las tres columnas explícitamente; una especificación de hook con una sola columna llena es un tercio de un hook.

Los anuncios estáticos colapsan esto a dos componentes (visual + titular) — aplica la misma regla: el titular no debe hacer de caption de la imagen.

---

## El Pipeline de Generación

Trabaja de arriba hacia abajo; los hooks escritos sin los pasos previos se leen como los de todos los demás anuncios.

```
Segmento → Motivación → Formato → Hook (tres componentes)
```

1. **Segmento** — qué comprador específico aborda este hook. No todo el ICP: un recorte con una situación compartida (del corpus de Insumos con Base en la Realidad: reseñas, comentarios, lenguaje de llamadas de ventas). Cuanto más angosto el segmento, más afilado el hook.
2. **Motivación** — el dolor, deseo u objeción único que mueve a este segmento, en *sus* palabras. Extrae frases textuales de reseñas y comentarios; el lenguaje del corpus siempre supera a la paráfrasis de marketing.
3. **Formato** — el vehículo de entrega: entrevista callejera, POV selfie, grabación de pantalla, unboxing, demo lado a lado, texto en pantalla estático, fundador a cámara, stitch de reacción. Elige el formato *antes* de escribir la línea — la misma motivación se lee completamente distinta como respuesta de entrevista callejera vs. confesión a cámara.
4. **Hook** — ahora escribe los tres componentes para esta celda de segmento × motivación × formato.

**Presenta como una matriz de hooks** para que la cobertura sea visible:

```
| # | Segmento | Motivación (fuente textual) | Formato | Acción visual | Línea hablada | Caption |
```

Genera a través de la matriz, no hacia abajo en una sola columna — diez hooks para diez celdas de segmento×motivación superan a treinta reformulaciones de una celda. Este es el mismo principio de diversidad de ángulos que la biblioteca de plantillas estáticas: la diversidad de la matriz es diversidad de audiencia.

---

## Movimientos de Apertura de Hooks

Un menú de estructuras de apertura probadas. Recórrelas como las plantillas estáticas — no te concentres en tus favoritas:

| Movimiento | Forma | Cuidado con |
|---|---|---|
| **Brecha de curiosidad** | Retener el sustantivo: "Nadie te dice qué causa esto realmente" | Debe pagarse dentro del anuncio o es clickbait que envenena el CVR |
| **Afirmación audaz** | Una declaración específica y falsable: "Esto reemplazó toda mi rutina matutina" | Necesita sustentación en pantalla o en el on-ramp |
| **Confesión en primera persona** | "Estaba haciendo [cosa común] completamente mal" | Se lee falso sin detalle vivido |
| **Contraste / antes-después** | Dos estados mostrados o nombrados en el primer beat | La transformación debe ser visualmente honesta — ver notas de cumplimiento en SKILL.md |
| **Relatabilidad / POV** | Reflejar una situación hiper-específica: "POV: son las 3pm y vas en tu cuarto café" | La especificidad es todo el mecanismo; el POV genérico es invisible |
| **Pregunta** | Hacer la pregunta exacta que el comprador escribe en el buscador o en ChatGPT | Usar su fraseo textual del corpus |
| **Cuenta regresiva / gamificado** | Un timer o desafío en pantalla que promete una recompensa al final | La recompensa debe existir; el hold-rate colapsa con trampas |
| **Prueba primero** | Liderar con el recibo — la captura del resultado, la estadística, el money-shot del demo | Más fuerte cuando la prueba brilla por sí sola |

---

## El Embudo de Diagnóstico

Cada métrica en el embudo de entrega aísla un componente diferente. Cuando un anuncio tiene bajo rendimiento, lee el embudo para encontrar *qué parte* arreglar en vez de descartar todo el anuncio:

| Etapa | Métrica | Si es débil, el problema es | Arreglo |
|---|---|---|---|
| Detener | Thumbstop / tasa de vista de 3 seg | **Acción visual** (y caption) | Nueva apertura visual; todo lo demás igual |
| Retener | Hold rate (3s → 15s / 50% de vista) | **El on-ramp** — lo que sigue al hook | Rehacer los segundos 3–15, no el hook |
| Clic | CTR | Claridad del deseo/oferta a mitad del anuncio | Afinar la promesa, el CTA o la prueba |
| Convertir | CVR post-clic | Congruencia — la página no continúa el anuncio | Arreglar la landing page o la afirmación, según **page-cro** |

Dos reglas que impone esta tabla:

- **Un gran thumbstop no es un gran anuncio.** Un visual clickbait que atrae a los viewers equivocados aparece como thumbstop alto + hold/CVR colapsados. Lee todo el embudo antes de declarar un hook ganador.
- **Un componente por iteración.** Cambia el visual O el on-ramp O el encuadre de la oferta por ciclo de prueba — igual que la regla de una variable en Errores Comunes.

---

## La Regla del On-Ramp

El on-ramp son los segundos ~3–15: el puente entre el hook y el cuerpo. **Un buen on-ramp extiende lógicamente la premisa del hook; uno malo gira hacia un pitch de producto que la abandona.** Si el hook promete "qué causa esto realmente", el siguiente beat debe empezar a explicar la causa — no introducir la historia de la marca.

Corolario: **toda prueba de hook es también una prueba de on-ramp.** Cambiar un hook nuevo sobre un cuerpo de anuncio existente usualmente rompe el puente de premisa; al probar hooks, reescribe el on-ramp para que coincida con cada uno. El hold rate es la métrica del on-ramp — diagnostícala por separado del thumbstop.

---

## Escalera de Fidelidad

Iguala el costo de producción con la fuerza de la evidencia (los niveles de producción están definidos en [creative-roadmap.md](creative-roadmap.md)):

- **Las corazonadas se lanzan en baja fidelidad en uno o dos días:** estáticos, video con texto en pantalla, voiceover sobre b-roll, remixes de metraje existente. La meta es una señal barata sobre el *ángulo*, no un anuncio pulido.
- **Los ángulos validados se ganan la alta fidelidad:** rodajes con creadores, entrevistas callejeras, demos escenificadas. Gasta presupuesto de producción solo en hooks cuya versión de baja fidelidad ya mostró una señal en el embudo (incluso una victoria de una sola métrica — un pico de hold-rate en un estático feo es evidencia).

Probar una corazonada con un rodaje costoso y probar un ángulo comprobado con un estático descartable son ambos errores — la escalera corre en una sola dirección.

---

## Reglas de Anclaje (heredadas, no negociables)

Los hooks heredan todas las reglas de anclaje de SKILL.md: cada hook cita la fuente del corpus de la que viene su motivación; ninguna afirmación, estadística o testimonio inventado; lenguaje textual del cliente por encima de la paráfrasis. Adicionalmente, mina el **contenido orgánico del nicho** (los TikToks/Reels/posts de mejor rendimiento, vía la habilidad **scraping** o las herramientas de social listening en **social**) para el vocabulario real de la audiencia — las palabras que usa el nicho ("GLP-1" vs. el término clínico, el slang para el dolor) pertenecen al caption y a la línea hablada. Minar contenido orgánico es investigación de lenguaje, no copiar: toma el vocabulario y las convenciones visuales, nunca la creatividad específica de un creador.

---

## Modos de Falla Comunes

- **Treinta reformulaciones de una celda** — variación sin cobertura de matriz; la diversidad de segmento×motivación es el punto
- **Componentes que se duplican entre sí** — tres espacios diciendo una cosa
- **Hook probado, on-ramp heredado** — puente de premisa roto, hold rate culpado al hook
- **La lectura del embudo se detiene en el thumbstop** — ganadores clickbait que escalan hacia cráteres de CVR
- **Corazonadas pulidas** — producción de alta fidelidad gastada en ángulos no validados
- **Captions con voz de marketing** — el corpus y el contenido orgánico del nicho definen el vocabulario; "fórmula revolucionaria" no aparece en ninguno de los dos
