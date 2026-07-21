# Video Ads de Revelación Nativos de iOS (iMessage, ChatGPT, Apple Notes, AirDrop)

Una familia de formatos de video social-nativos en 9:16 que recrean una superficie familiar de iOS en tiempo real y dejan que la marca emerja dentro de ella. La bandera insignia es la **revelación de chat en iMessage** — alguien envía una captura de un resultado o producto, un amigo reacciona y pregunta qué es, y la conversación revela la marca, usualmente con un código promocional. Las burbujas de mensaje aparecen a lo largo de ~15–22 segundos con sonidos auténticos de enviar/recibir, y luego un end card de marca estático aterriza el CTA. La misma arquitectura potencia las **revelaciones de ChatGPT**, las **revelaciones de Apple Notes** y las **revelaciones de AirDrop** — cubiertas en [Otras Superficies de Revelación Nativas de iOS](#otras-superficies-de-revelación-nativas-de-ios) más abajo.

El formato funciona porque toma prestada la UI más leída del planeta. Un hilo de chat es una dramatización familiar y de alta atención — refleja cómo ocurren las recomendaciones reales, así que el viewer se inclina hacia adelante en vez de seguir haciendo scroll. El CTA llega de forma conversacional ("usa el código FREEPACK") en lugar de como una venta forzada, lo que evita que se dispare el reflejo de saltarse el anuncio antes de que el pitch ya haya aterrizado. Corre esto solo como un posicionamiento pagado claramente etiquetado (la etiqueta "Patrocinado" de Meta hace el trabajo de divulgación); nunca lo siembres orgánicamente como si fuera una conversación filtrada real.

Crédito: esta referencia destila el formato popularizado por Shiv Sakhuja y el equipo de Gooseworks ([@shivsakhuja](https://x.com/shivsakhuja), [gooseworks-ai/gooseworks-ads-skills](https://github.com/gooseworks-ai/gooseworks-ads-skills)), quienes reportan que el formato tiene un desempeño fuerte en Meta.

---

## Cuándo Usar Este Formato

**Buen ajuste:**
- Anuncios de reacción/descubrimiento donde el punchline es la curiosidad del receptor ("espera, ¿qué app es esa?")
- Ofertas con código promocional — la entrega conversacional se siente mucho menos como anuncio que un código en una placa
- Productos con un resultado capturable en pantalla: un número, un dashboard, un recibo, un antes/después
- Ángulos estilo UGC cuando no tienes creadores de UGC disponibles

**Mal ajuste:**
- Compras B2B consideradas donde un intercambio de texto casual socava la credibilidad
- Productos sin nada visual o numérico que capturar (arregla primero el hook, no el formato)
- Marcas cuya revisión de cumplimiento no puede aprobar conversaciones dramatizadas (industrias reguladas — verifica primero)

**Ajuste de plataforma:** Construido para posicionamientos de Meta Reels/Stories (9:16, 1080×1920) con una variante de recorte central 1:1 para feed. Funciona en TikTok y YouTube Shorts con el mismo archivo maestro.

---

## Cumplimiento y Anclaje

Esto es una **dramatización** — una conversación scripteada, no una real. Ese es un recurso publicitario estándar y legítimo, pero dos reglas lo mantienen honesto y del lado correcto de las directrices de la FTC:

1. **Cada afirmación en el hilo debe ser verdadera del producto.** El tiempo de la carrera, la matemática de los ahorros, los "5 minutos al día" — ancla cada uno en un resultado real de cliente, una reseña, o un hecho verificable del producto, exactamente como lo exigen las reglas de Insumos con Base en la Realidad en SKILL.md. La conversación es ficticia; los hechos dentro de ella no pueden serlo.
2. **No presentes el hilo como un testimonio real.** Sin nombres reales de clientes, sin el encuadre "este es un texto real de un cliente", sin respaldos fabricados. El formato persuade a través de la reconocibilidad, no fingiendo ser metraje encontrado.

Si una afirmación necesita un descargo de responsabilidad en tu landing page, también lo necesita en este anuncio.

---

## Ángulos de Concepto

La mayoría de los anuncios de iMessage encajan en uno de seis ángulos. Elige el ángulo antes de escribir cualquier copy — el modo de falla más común ("el guion está bien pero el anuncio se siente mal") es un desajuste de ángulo, no líneas malas. Los hooks más fuertes comparten uno de tres rasgos: un número específico, un pequeño acto de autoconfianza, o una mecánica de producto físicamente novedosa.

| Ángulo | El adjunto del hook | La revelación |
|---|---|---|
| **Resultado-como-captura** | Un número que presume por sí solo — tiempo de carrera, resumen de app, estadística de dashboard | "X minutos al día. Eso es todo." |
| **Setup flex** | Una foto de tu espacio — gimnasio de departamento pequeño, rincón de kit de carrera, setup de escritorio | "este es todo el setup" |
| **Momento de cancelación** | Un recibo de confirmación — correo de cancelación del gimnasio, página de "suscripción cancelada" | "$X/mes → $Y/mes. haz la cuenta" |
| **Feature-como-punchline** | Un clip corto de la mecánica del producto en movimiento | La mecánica *es* la marca |
| **Amigo-le-pregunta-a-amigo (inverso)** | El *peer* abre con el asombro — "cómo estás haciendo esto 😭" | *Tú* respondes con la marca |
| **Recibo-como-hook** | Un documento financiero mundano — estado de cuenta, recibo de App Store | Un pequeño acto de autoconfianza |

---

## Anatomía del Anuncio

```
0:00  Aterriza el adjunto del hook (la captura sobre la que trata todo el chat)
      ↓ reacciones cortas, 250–450ms de separación ("no puede ser" / "espera ¿eso es real?")
0:06  La pregunta — "¿¿qué app es esa??"
      ↓ indicador de escritura … luego la respuesta con el nombre de la marca
0:12  El pitch, en voz de texteo — una o dos burbujas máximo
0:15  El código — "usa FREEPACK, el primer pack es gratis" (el código se renderiza subrayado como link)
0:17  Beat de silencio, luego el cierre — "dale" / "ok descargando"
0:18  Crossfade de 300ms → end card de marca estático: logo, código, tagline (~3s)
```

**Reglas de guion:**

- **8–14 burbujas en total.** Más corto se lee escaso; más largo pierde al viewer que hace scroll.
- **Escribe en voz de texteo real.** Minúsculas, fragmentos, un emoji máximo por mensaje, sin adjetivos de marketing. Léelo en voz alta como dos amigos — cualquier burbuja que suene como copy de anuncio se elimina.
- **La marca aparece una vez, tarde.** El hilo trata sobre el *resultado* hasta que alguien pregunta. Nombrar la marca en la burbuja dos mata la revelación.
- **El ritmo tiene cadencia, no un metrónomo.** Las reacciones de una palabra se disparan con 250–450ms de separación; las respuestas de oración completa reciben 600–900ms de aire después; deja ~600ms de silencio antes de la reacción final para que aterrice.
- **Los indicadores de escritura van antes de respuestas del peer de largo de oración**, opcionales antes de reacciones cortas. Que aparezca el indicador es silencioso (ver reglas de SFX abajo).
- **El código promocional va dentro de una burbuja**, estilizado con el subrayado de detección de link de iOS, *y* en el end card. Entrega conversacional primero, refuerzo segundo.

---

## Rutas de Producción

Tres formas de producirlo, en orden de control:

### Ruta 1: Habilidad lista para usar (la más rápida)

Gooseworks distribuye su pipeline como una agent skill instalable — `npx gooseworks install --all`, luego invoca la habilidad goose-ads desde tu agente. Maneja renderizado, grabación, SFX y ensamblaje de principio a fin. Usa esto para validar el formato antes de construir algo personalizado. (Su repositorio fuente de ads-skills es público pero no lleva licencia de código abierto — trátalo como lectura de referencia, no como código para incorporar.)

### Ruta 2: Pipeline basado en código (control total)

La arquitectura que produce un resultado convincente: renderiza el chat como HTML/CSS imitando la UI de iMessage, dirige la animación con un script de timeline, grábalo sin interfaz gráfica con Playwright, y ensambla audio + end card con ffmpeg.

1. **El guion como datos.** Almacena el hilo como JSON: participantes (nombre del peer, iniciales, color de avatar), mensajes ordenados (`from`, `text`, rutas de adjuntos, flags de indicador de escritura), tema, header. El guion es revisable y re-renderizable sin tocar código.
2. **Renderiza la UI del chat en HTML/CSS.** El tema oscuro se lee más nativo. Dos variantes: chat de sangrado completo, o el chat dentro de un marco de iPhone (barra de estado + Dynamic Island) sobre una foto de fondo relevante a la marca — la variante enmarcada se lee más nativa in-feed y es el default preferido.
3. **Anima con un timeline, graba en UNA sesión continua.** Todas las burbujas existen en el DOM pero ocultas (`display: none` — no `opacity: 0`, o el hilo pre-asigna espacio y nunca "crece"). Un script conductor recorre un array de timeline revelando cada burbuja, dirigiendo el composer, y haciendo auto-scroll. Nunca grabes escena por escena y concatenes — cada recarga de página causa un micro-parpadeo visible.
4. **Escribe en el composer para cada burbuja enviada.** El texto tecleado debe ser exactamente igual al texto enviado (un desajuste se lee falso en la segunda mirada). Ritmo de ~12–15 caracteres/seg con jitter de ±30% por carácter para que se sienta como pulgares, no como un script.
5. **Graba a la resolución de salida nativa.** Configura tanto el `viewport` de Playwright *como* `recordVideo.size` en 1080×1920 — si omites `recordVideo.size`, Playwright graba por defecto un video reducido de escala. Grabar pequeño y escalar hacia arriba produce texto de burbuja suave y borroso.
6. **Superpón audio con ffmpeg.** Los cues de SFX se calculan de forma determinista a partir del mismo timeline que dirigió la grabación, así los sonidos aterrizan exactamente en la aparición de las burbujas.
7. **Ensambla: chat → crossfade de 300ms → end card estático.** El `xfade` de ffmpeg requiere que ambos inputs coincidan en resolución, formato de píxel y frame rate — renderiza el end card a un MP4 de frame fijo con las mismas especificaciones que la grabación del chat antes de hacer el fade. Exporta el master en 9:16 más un recorte central en 1:1.

### Ruta 3: Remotion (escala templada)

Una vez que emerge una estructura de guion ganadora, reconstrúyela como una composición de Remotion (ver [generative-tools.md](generative-tools.md)) con el JSON del hilo como props. Entonces las variaciones — nuevos hooks, nuevos códigos, nuevas personas — son cambios de datos, no re-producciones. El movimiento correcto en la etapa de "estamos probando 10 variantes de guion a la semana", no para el primer anuncio.

---

## Reglas de Craft (los detalles que venden la ilusión)

Estas son la diferencia entre "se siente como un chat real" y "se siente como una maqueta":

- **Los sonidos reales de enviar/recibir, nunca sonidos de notificación genéricos.** La sensación de iMessage es mayormente el audio. BigSoundBank hospeda grabaciones de los sonidos de mensaje de Apple bajo CC0: whoosh de envío (`bigsoundbank.com/UPLOAD/mp3/1313.mp3`, ~0.5s) y tritono de recepción (`bigsoundbank.com/UPLOAD/mp3/1111.mp3` — recorta a ~1.4s con un fade de 400ms). Normaliza fuerte (≈ -9 LUFS) para que corten a través de la música. Nota: que las grabaciones sean CC0 no significa que Apple haya licenciado sus marcas sonoras o su trade dress de UI — esta es una práctica estándar en el formato, pero marcas reguladas y equipos legales adversos al riesgo deberían revisar la imitación de iMessage como un todo; un skin de app de chat genérico (burbujas neutras, sonidos no-Apple) es el respaldo que mantiene la mecánica.
- **Sin sonido en el indicador de escritura.** iOS está silencioso cuando alguien empieza a escribir. Reproduce el sonido de recepción solo cuando la burbuja real reemplaza los puntos. Esta es la señal delatora más común.
- **Cama musical: instrumental lofi/hip-hop suave.** ~30% de volumen, highpass alrededor de 60Hz para despejar espacio para el SFX, fade out ~1.5s antes de la revelación del código para que el CTA aterrice en silencio relativo.
- **End card estático — sin zoom, sin drift tipo Ken Burns.** La placa de marca debe aterrizar con fuerza; un end card que deriva se lee como relleno.
- **SVG real del logo de la marca en el end card, nunca texto estilizado con CSS.** Las wordmarks aproximadas con fuente se ven amateur incluso cuando están cerca. Extrae el SVG oficial del kit de prensa de la marca, Wikimedia, o brandfetch.com.
- **Capturas del hook: imita la UI real de la app, no la generes con IA.** Las UIs de app generadas con IA producen chrome confuso que se lee como slop. Construye una pequeña página HTML copiando los colores de marca reales de la app, la tipografía y las convenciones de layout (la franja naranja de Strava, el timestamp "Público · hace 2h") y captúrala en pantalla. Reserva la generación de imagen con IA para hooks *fotográficos* — una foto de playa, una toma de lifestyle, el fondo de la variante enmarcada.
- **Gotcha de mezcla de audio:** el `amix` de ffmpeg divide el volumen por la cantidad de inputs por defecto — pasa `normalize=0` o toda la mezcla sale misteriosamente silenciosa. Luego pasa la mezcla por un limitador con el techo justo debajo de la escala completa (por ejemplo `alimiter=limit=0.95`, ≈ -0.4 dB) para que suene fuerte sin clipping.

---

## Lista de Verificación de Calidad

Antes de lanzar:

- [ ] Cada afirmación factual en el hilo se traza a una reseña real, resultado, o hecho de producto (Insumos con Base en la Realidad)
- [ ] El guion se lee como voz de texteo real al leerlo en voz alta — sin adjetivos de marketing en las burbujas
- [ ] El nombre de la marca aparece solo después de que el peer pregunta
- [ ] Sin sonido en ningún indicador de escritura; el SFX de recepción se dispara cuando aterriza la burbuja de texto
- [ ] Los SFX aterrizan exactamente en la aparición de las burbujas (revisa la primera y la última)
- [ ] Cada burbuja enviada tuvo una escritura completa en el composer; el texto tecleado es igual al texto enviado
- [ ] Sin micro-parpadeo en ningún lugar del chat — el único corte es chat → end card (crossfade de 300ms)
- [ ] El código promocional está subrayado como link en su burbuja y repetido en el end card
- [ ] El end card es estático con el SVG real del logo
- [ ] El master es nativo 1080×1920; la variante 1:1 es un recorte, no un aplastamiento
- [ ] La burbuja final recibe ~600–800ms de aire antes del crossfade
- [ ] El audio está limitado justo debajo de la escala completa (sin clipping); la música nunca compite con el SFX

---

## Iterando el Formato

Trata el hilo como la variable y el pipeline como fijo. Prueba en este orden — el hook primero, todo lo demás después:

1. **Adjunto del hook** — la captura es el thumbnail y los primeros 2 segundos; decide el scroll-stop
2. **Ángulo** — resultado-flex vs. cancelación vs. inverso cambia con quién se identifica el viewer
3. **Fraseo de la revelación del código** — "el primer pack es gratis con FREEPACK" vs. "FREEPACK te da uno gratis"
4. **Persona del peer** — nombre, avatar y estilo de texteo cambian la audiencia percibida
5. **Duración** — prueba un corte de 12 burbujas y uno de 8 burbujas del mismo guion

La misma arquitectura se extiende también a otras superficies — WhatsApp, Slack, un cuadro de búsqueda — la misma grabación dirigida por timeline, distinto shell de UI.

---

## Otras Superficies de Revelación Nativas de iOS

Todo lo anterior sobre producción (maqueta de UI → grabación continua dirigida por timeline → cues de SFX deterministas → end card estático), anclaje, y divulgación se traslada sin cambios. Lo que cambia por superficie es el *mecanismo de persuasión* y un puñado de detalles de craft.

| Superficie | Mecanismo de persuasión | Recurre a ella cuando |
|---|---|---|
| **iMessage** | La recomendación de un amigo — prueba social a través del diálogo | El producto se descubre a través de resultados que la gente comparte ("¿qué app es esa?") |
| **ChatGPT** | Una respuesta autoritativa a la propia pregunta del viewer | El problema tiene forma de pregunta — algo que la gente literalmente escribiría en ChatGPT |
| **Apple Notes** | Una confesión privada hecha pública — primera persona, sin diálogo | El ángulo es transformación o darse cuenta ("cosas que nadie me dijo sobre los 45") |
| **AirDrop** | Un compartir espontáneo entre pares — "alguien cerca pensó que esto valía la pena enviarte ahora mismo," con una decisión de aceptar/rechazar incorporada | El producto es algo que la gente se pasa entre sí (una oferta, un link, un hallazgo, un archivo) y el tap de aceptar puede *ser* la revelación |

La señal más fuerte para elegir: cuál de estas superficies ya llena el día de tu audiencia. Los productos de recomendación quieren iMessage; los problemas que buscan consejo quieren ChatGPT; las historias de identidad/transformación quieren Notes; y cualquier cosa que la gente se pasa espontáneamente quiere AirDrop.

### Revelación de ChatGPT

El viewer se identifica con quien *pregunta*. La pregunta escrita es el hook y debe ser la pregunta textual del cliente objetivo — con fraseo torpe y todo ("¿por qué de repente estoy tan hinchada a los 47?"). La respuesta en streaming nombra el mecanismo real del problema, luego la categoría de solución; la marca aterriza en la recomendación de la respuesta o en un seguimiento tecleado ("¿cuál es la mejor?").

**Detalles de craft:**
- **Transmite la respuesta en bloques de palabras**, no carácter por carácter (eso es tecleo, no generación) y no en párrafos completos de una vez. Un tick sutil debajo del stream y un stop limpio cuando la respuesta se completa; sin tritonos de iMessage en ningún lugar.
- **Teclea la pregunta como pulgares, transmite la respuesta como un modelo.** Dos ritmos distintos — el contraste es lo que se lee como "ChatGPT real."
- **Mantén la respuesta escaneable:** párrafos cortos, una frase en negrita o una lista corta, exactamente como ChatGPT realmente formatea. Un muro de texto rompe la ilusión y pierde al viewer.
- La interfaz de OpenAI es su trade dress — la misma postura de revisión legal que la nota de imitación de UI de Apple arriba, con un skin genérico de "asistente de IA" como respaldo.

**Cumplimiento — más estricto aquí que en cualquier otro lugar de esta familia.** La "respuesta" es tu copy de anuncio disfrazado de bata de laboratorio: un traje de autoridad. Cada afirmación en ella necesita la misma sustentación que una afirmación en tu propia voz, y la autoridad prestada del formato sube la barra, no la baja. No pongas consejo de salud, médico o financiero en una respuesta de IA fabricada sin revisión legal — esa es la versión de mayor riesgo de este formato. Y nunca presentes el intercambio como un output real y no solicitado de ChatGPT que respalda tu producto; es una dramatización, igual que el hilo de iMessage.

### Revelación de Apple Notes

Un género diferente de los formatos de chat: **confesión, no conversación.** El viewer observa a alguien escribir una nota privada — una lista de realizaciones, una entrada de "cosas que desearía haber sabido" — con el teclado visible. El título de la nota es el hook y hace el trabajo que hace la slide 1 en un carrusel ("Cosas que nadie me dijo sobre los 45."). El producto aparece como un ítem en la lista, nombrado como una persona realmente lo escribiría para sí misma — no como lo escribiría una marca.

**Detalles de craft:**
- **El audio es solo tecleo de teclado.** Sin SFX de chat, sin tonos de recepción — una nota no tiene otra parte. Una cama musical suave sigue funcionando debajo.
- **Teclea a ritmo real de pulgar con jitter**, igual que la regla del composer de iMessage. Un typo-y-corrección se lee humano; varios se leen ensayados.
- **Consigue el chrome de Notes correcto:** título estilizado más grande que el cuerpo, la barra de formato sobre el teclado, acentos amarillo-iOS. El mismo enfoque de imitación con HTML — y la misma nota de revisión de trade dress de Apple y respaldo de app de notas genérica — que todo lo demás aquí.
- **Ajusta la nota al frame.** Escribe lo suficientemente corto para que la nota completa quepa sin hacer scroll, o haz scroll una vez, deliberadamente, tarde.
- **Primera persona o no funciona.** En el momento en que la nota se lee como copy de anuncio ("¡[Marca] lo cambió todo!"), se pierde la intimidad que hace que el formato convierta. La mención del producto debe ser la línea *menos* entusiasta de la nota.

La regla de anclaje golpea diferente aquí: la confesión es una dramatización de una historia de cliente *compuesta pero verdadera* — extrae las realizaciones de reseñas y entrevistas reales (el corpus de Insumos con Base en la Realidad), y mantén cualquier número o resultado dentro de lo documentado.

### Revelación de AirDrop

El único formato nativo de interacción de la familia: el hook es una **solicitud de AirDrop entrante**, y el **tap de Aceptar es la revelación**. El viewer observa desde el punto de vista del *receptor* — una tarjeta translúcida de AirDrop se desliza hacia arriba, "[Remitente] quiere compartir [preview]," con un Rechazar gris y un Aceptar azul. La curiosidad es estructural ("¿qué es esto y quién lo envía?") y la elección de aceptar/rechazar es un beat de micro-conversión incorporado en el propio iOS. Tocar Aceptar transfiere el ítem — y *ahí* es donde aterriza el producto, la oferta o el resultado.

**Detalles de craft:**
- **El thumbnail de vista previa es el hook.** Es la única imagen en la tarjeta de AirDrop antes de Aceptar, así que tiene que ganarse el tap — el mismo trabajo que el adjunto de captura en iMessage. Hazlo el resultado, el money-shot del producto, o la oferta.
- **Elige el nombre del remitente como un compartir real.** "iPhone de Sarah," "Mamá," "MacBook de Jordan" se lee nativo; un nombre de marca en el slot del remitente se lee como anuncio — guarda marca-como-remitente para la revelación, no para la tarjeta entrante.
- **El anillo de progreso de transferencia es el motion distintivo — no lo omitas.** Tarjeta entrante → un beat de duda ("¿aceptar?") → el tap de Aceptar → el anillo de progreso se llena → el ítem aterriza + end card. Ese beat del anillo de progreso es lo que hace que se lea como un AirDrop real y no como un corte.
- **El audio es el swoosh / tono de recepción de AirDrop**, no los tritonos de iMessage. La misma fuente de sonidos CC0-Apple y la misma nota de revisión de trade dress de Apple que el resto de la familia, con un skin genérico de "compartir cercano" como respaldo.
- **Mantenlo corto y consigue el material correcto.** El blur/translucidez de la tarjeta y el par de botones Rechazar gris / Aceptar azul son las señales reconocibles; una hoja opaca y plana rompe la ilusión. Todo el beat es más rápido que los formatos de chat — la interacción *es* el anuncio.
- **Punto de vista del receptor por defecto; punto de vista del remitente como flex.** Recibir se lee como descubrimiento ("alguien me envió esto"); enviar se lee como una recomendación que estás haciendo ("tuve que hacerle AirDrop a esto al grupo") — usa el punto de vista del remitente cuando el ángulo es advocacy en vez de descubrimiento.

El anclaje es la misma regla de familia: es una dramatización de un compartir, no una afirmación de que una persona real le hizo AirDrop a tu producto. Cada afirmación sobre el ítem transferido está sustentada según las reglas de Insumos con Base en la Realidad, y el intercambio nunca se presenta como un respaldo real y no solicitado.
