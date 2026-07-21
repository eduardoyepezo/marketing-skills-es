# Video Ads Estilo Motion (Sin Rostro, Totalmente Generados)

> Formato popularizado por Borja ([@borjafat](https://x.com/borjafat)) y la receta abierta de motion-collage `super-video-maker` de [Bomx](https://github.com/Bomx/super-video-maker-skill); esta guía es una re-expresión original del método, extendida con una biblioteca multi-estilo y lecciones de producción de construirlo y lanzarlo de principio a fin.

Produce un video ad o explicativo sin rostro de 15–45s a partir de nada más que un concepto: un
still tipo poster estilizado (modelo de imagen) → cobra vida con motion sutil (modelo image-to-video)
→ narrado (TTS) → subtítulos sincronizados por palabra. Sin metraje, sin presentador, sin editor. El costo por
video terminado es aproximadamente $3–6 en llamadas de API; tiempo real ~15 minutos.

El formato funciona porque el *still* lleva la idea (un visual literal, ligeramente surreal
por beat) y el *motion* solo lo hace respirar. Resiste la tentación de hacer que el
video cuente la historia — esto es diseño de poster animado, no cine.

## Cuándo Usarlo

- Anuncios de concepto/explicativos: una idea hecha concreta ("tu CRM es un cajón de cosas sueltas")
- Video social top-of-funnel (9:16 Reels/Shorts/TikTok, 4:5 y 1:1 feed)
- Híbridos de brand-response donde un estilo propio y distintivo vence al UGC de stock
- NO para: anuncios de demo/prueba (las grabaciones de pantalla ganan), formatos de
  testimonio/UGC, cualquier cosa que requiera una toma real de producto como evidencia

## Pipeline (Agnóstico de Proveedor)

1. **Guion** 3–6 beats, 20–45s de VO. Una idea por beat. Calma vence al
   hype. Termina con una sola línea de CTA.
2. **Stills de poster** — uno por beat, usando una *fórmula de estilo* (abajo). Genera el beat 1,
   apruébalo, luego pásalo como imagen de referencia para cada beat posterior para que el set se lea
   como una sola serie. Corrige texto de label confuso regenerando con una frase más corta.
3. **Anima** cada still aprobado con un modelo image-to-video (5–8s por beat).
   El motion pertenece a los objetos en el frame; la composición no debe cambiar.
4. **VO + subtítulos**: una sola toma continua de TTS, transcribe con timestamps de palabra
   (whisper), corta los beats en los límites de oración, quema grupos de subtítulos de 2–3 palabras.
5. **Ensambla**: concatena los beats recortados a sus tramos de VO (sostén el último frame para rellenar),
   normaliza el loudness a `I=-16:TP=-1.5:LRA=11`, exporta el aspecto por posicionamiento.

**Opciones de proveedor** (cualquier combinación funciona; la receta es agnóstica de modelo):

| Etapa | Ruta de una sola clave en Gemini | Alternativas |
|---|---|---|
| Stills | Nano Banana Pro (`gemini-3-pro-image-preview`) — excelente tipografía de labels | GPT-Image, Flux, Ideogram |
| Motion | Veo 3.1 fast image-to-video (nota: 1080p requiere clips de 8s) | Seedance 2.0 vía fal.ai, Kling, Runway |
| VO | Gemini TTS (voces calmadas: Charon/Kore) | ElevenLabs, OpenAI TTS |
| Subtítulos | timings de palabra de whisper + quemado con PIL/ASS | CapCut, subtítulos automáticos de la plataforma |

## La Biblioteca de Estilos

Cinco looks probados. Cada uno es una fórmula de prompt de llenar-los-espacios; mantén UN estilo por
campaña para que la cuenta construya una identidad visual reconocible. Los cinco animan bien.

### A. Collage de serigrafía (editorial, energía docu tipo "In a Nutshell")
> Poster de collage de serigrafía plano, fondo `<COLOR>` saturado único, grano sutil de papel periódico. Pieza central: un recorte en blanco y negro con medio tono de `<SUJETO HACIENDO EL CONCEPTO LITERAL>`, tratado como una calcomanía de papel con un delgado contorno troquelado blanco, bordes ligeramente rasgados, y una sombra suave. Textura visible de puntos de medio tono, sensación de foto editorial vintage, sujeto en escala de grises. Recortes de acento: 2–4 formas planas (sol de círculo crema, zigzag negro, puntos dispersos). Una etiqueta de papel rasgado cerca de la parte inferior con las palabras "`<LABEL>`" en tipografía de periódico condensada en mayúsculas y negrita. Estética risográfica impresa mate, paleta limitada. Sin gradientes, sin brillo, sin 3D, sin fotorrealismo, sin texto extra.

### B. Explicativo vectorial plano (limpio, tecnológico, infinitamente adaptable a marca)
> Ilustración explicativa vectorial plana en el estilo de un canal de ciencia animado premium: un `<SUJETO>` amigable y simplificado, formas planas audaces con bordes redondeados limpios, fondo `<COLOR DE MARCA>` sólido, paleta limitada de `<2-3 ACENTOS>`, acentos geométricos planos, sombras largas suaves, diseño 2D completamente plano. Un banner rectangular limpio cerca de la parte inferior dice "`<LABEL>`" en sans-serif geométrico audaz en mayúsculas. Sin contornos, sin 3D, sin fotorrealismo, sin textura, sin texto extra.

### C. Diorama de papercraft (cálido, táctil, artesanal premium)
> Diorama de papercraft en capas: `<SUJETO>`, cada elemento cortado a mano de papel de construcción de color con grosor de papel visible y sombras reales entre capas, fondo de papel `<COLOR>` con acentos de papel cortado, sensación artesanal táctil con cortes de tijera ligeramente imperfectos. Un banner de papel cortado cerca de la parte inferior dice "`<LABEL>`" en letras gruesas de papel recortado. Iluminación de estudio suave sobre las capas de papel. Sin gradientes digitales, sin humanos fotorrealistas, sin texto extra.

### D. Cómic pop-art (llamativo, que detiene el scroll, promocional)
> Panel de cómic pop-art vintage: `<SUJETO>`, contornos de tinta negra audaces, sombreado con puntos de medio tono Ben-Day, colores de proceso planos (`<PALETA>`), acentos de explosión de cómic, borde de panel grueso, textura de papel periódico envejecido. Una caja de caption de cómic cerca de la parte inferior dice "`<LABEL>`" en letras de cómic audaces. Estética de cómic impreso de los años 60, ligero desregistro de tinta. Sin 3D, sin fotorrealismo, sin gradientes, sin texto extra.

### E. Claymation (encantador, alto interrupt de patrón)
> Escena de claymation stop-motion: un `<SUJETO>` de plastilina hecho a mano encantador, huellas dactilares y textura de arcilla visibles, fondo y piso de arcilla `<COLOR>`, props de arcilla robustos, iluminación de estudio cálida y suave como un set de filmación stop-motion, profundidad de campo poco profunda. Un pequeño letrero de arcilla cerca de la parte inferior dice "`<LABEL>`" en letras de arcilla moldeadas a mano. Sensación de miniatura artesanal. Sin ilustración 2D, sin humanos fotorrealistas, sin texto extra.

## Estilos Flexibles de Marca (Guiados por Tokens)

Los cinco looks de arriba son *con carácter propio* — imponen su propia paleta. Este segundo
nivel es *marca-primero*: cada estilo está definido por *slots*, así que los tokens de cualquier empresa
encajan y el output se lee como el propio sistema de diseño de esa marca.

**El contrato de slots de marca.** Antes de generar, resuelve estos a partir de las
guías de la marca (o `.agents/product-marketing.md`):

- `FIELD` — el terreno neutro (blanco/off-white de marca, u oscuro de marca)
- `INK` — el color de dibujo/tipografía (gris/carbón de marca, casi negro)
- `ACCENT` — UN color o gradiente de marca, usado con moderación (una regla, un rayo, un cuadrado)
- `TYPE FEEL` — la voz tipográfica de la marca ("grotesca sans moderna y limpia", "sans geométrica", "captions mono")
- Cualquier restricción por marca (por ejemplo, "gradientes solo en bordes, nunca en rellenos")

Mantén el acento genuinamente escaso — un elemento por frame. La escasez es lo que hace
que estos se lean como diseñados en vez de generados.

### F. Editorial monolínea (la más universalmente adaptable a marca)
> Poster de ilustración editorial monolínea minimalista: `<SUJETO>`, dibujado enteramente en elegantes líneas delgadas de un solo peso en `<INK>` sobre un fondo `<FIELD>` limpio, el estilo de una ilustración de blog de una empresa tech premium. Composición dispersa con generoso espacio en blanco, unos pocos detalles de acento monolínea pequeños, y UN elemento `<ACCENT>` restringido: `<un barrido de subrayado de acento delgado / un pequeño arco de acento>`. Un pequeño caption cerca de la parte inferior dice "`<LABEL>`" en `<TYPE FEEL>`, `<INK>`, mayúsculas con letterspacing, con un subrayado `<ACCENT>` delgado. Preciso, técnico, refinado. Sin rellenos excepto el acento único, sin gradientes, sin 3D, sin fotorrealismo, sin textura, sin texto extra.

### G. Tipográfico suizo (la tipografía ES el visual — cualquier marca con una fuente y un color)
> Poster de Estilo Tipográfico Internacional Suizo: las palabras "`<LABEL>`" en tamaño enorme en un `<TYPE FEEL>` audaz, `<INK>` sobre un fondo `<FIELD>`, llenando los dos tercios superiores con interlineado ajustado y bordes recortados. Un pequeño recorte fotográfico en blanco y negro de `<SUJETO>` se sitúa sobre una grilla base delgada en el tercio inferior, alineado a una grilla asimétrica con una línea de regla `<ACCENT>` delgada y un pequeño cuadrado `<ACCENT>` como el único color. Líneas de grilla tenues visibles, márgenes precisos, composición matemática. Plano, impreso, mate. Sin gradientes, sin 3D, sin decoración, sin texto extra más allá del label y una pequeña línea de caption con letterspacing.

### H. Wireglow (keynote oscuro — marcas dev-tool / dark-mode)
> Poster de keynote tech minimalista y oscuro: `<SUJETO>` renderizado como un elegante dibujo de línea wireframe gris claro y delgado sobre un fondo `<FIELD>` casi negro con grano de película sutil. Desde `<el objeto focal>` emana un haz estrecho y suave de luz de gradiente `<ACCENT>` brillante, el único color, difuminado y atmosférico. Círculos guía geométricos concéntricos delgados y tenues. Un caption cerca de la parte inferior dice "`<LABEL>`" en `<TYPE FEEL>`, gris claro, mayúsculas con letterspacing, con una regla de gradiente fina debajo. Contenido, premium, técnico. Sin fotorrealismo, sin look de render 3D, sin elementos ocupados, sin texto extra.

### I. Serigrafía duotono (marcas de foto — punch editorial de dos tokens)
> Poster fotográfico de serigrafía duotono audaz: una fotografía dramática de `<SUJETO>`, reproducida como una serigrafía de dos colores — `<INK>` para las sombras y `<ACCENT>` para las luces — sobre un fondo de papel `<FIELD>` off-white con grano de medio tono grueso visible y ligero desregistro de tinta. Composición diagonal fuerte, la figura grande y recortada. Una barra `<INK>` sólida y ancha cerca de la parte inferior lleva las palabras "`<LABEL>`" en reversa, en `<TYPE FEEL>` condensado audaz en mayúsculas, con una pequeña viñeta cuadrada `<ACCENT>`. Energía de poster editorial, sensación mate impresa. Sin gradientes más allá del duotono, sin 3D, sin texto extra.

**Notas de motion para este nivel**: F/G animan como movimientos de dibujo (las líneas se extienden, el
barrido de acento se dibuja a sí mismo, la tipografía se asienta unos pocos píxeles); H anima como
pulso de haz + sensación de rotación wireframe lenta; I como shimmer de grano + push lento. Aplican las
mismas reglas duras: el motion pertenece a elementos existentes, la composición nunca cambia.

## Fórmula de Prompt de Motion

> Motion vivo sutil de estilo `<style>` de solo los elementos existentes. `<UN motion literal ligado al concepto: la pila se infla / la flecha avanza más alto / el megáfono tiembla con cada grito>`. `<Motion ambiental secundario: los acentos derivan, push-in suave>`. Cada elemento que es visible ahora es lo único que aparece jamás; la composición se mantiene exactamente como está. Todo se mantiene `<descriptor de estilo: un collage plano impreso / vector plano 2D / papel cortado / cómic impreso / arcilla hecha a mano>`. Sin whip de cámara, sin cambio de escena, sin morphing, sin texto agregado.

## Gotchas Ganados a Pulso

- **A los modelos de video les encanta agregar "manos de fabricante" fotorrealistas** entrando al frame,
  especialmente en movimientos de presionar/manipular — y *los prompts negativos lo empeoran* ("sin manos" es una
  trampa de atención). Nunca menciones las manos; describe el motion como perteneciente a los objetos,
  e incluye "la composición se mantiene exactamente como está."
- **Siempre haz control de calidad de los últimos 2 segundos de cada clip** — ahí es donde aparecen objetos
  intrusos y el drift de estilo. Recorta antes de eso o regenera; nunca lances un frame "realificado."
- **Un motion dominante por beat.** Dos motions se leen como caos a la velocidad del feed.
- **TTS y whisper discrepan en palabras que suenan parecido** ("cazar" → "casar"). Lee la transcripción
  contra el guion antes de quemar los subtítulos; prefiere un fraseo de CTA sin ambigüedad fonética.
- **Mantén los subtítulos fuera de la banda del label** (subtítulos ~60% de la altura, label ~80%).
  Bloquea grupos de subtítulos para que nunca se superpongan dos; encoge para ajustar grupos largos.
- **Específico de anuncios**: pon la marca/label en el propio poster (sobrevive al autoplay
  sin sonido), adelanta el concepto en el beat 1 (el hook de 3 segundos es el poster), y
  exporta 9:16 + 4:5 + 1:1 desde los mismos beats regenerando los stills por relación de aspecto
  en vez de recortar.

## Cumplimiento

Personajes totalmente sintéticos — sin problemas de divulgación de semejanza/UGC, pero verifica los
requisitos de divulgación de contenido de IA de la plataforma (Meta y TikTok etiquetan el contenido generado con IA).
No fabriques estadísticas ni testimonios en la VO; ancla cada afirmación.
