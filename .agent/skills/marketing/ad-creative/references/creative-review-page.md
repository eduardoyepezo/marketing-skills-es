# La Página de Revisión de Creatividades

Una página web compartible y autocontenida que presenta los conceptos de anuncio generados para que un cliente o stakeholder los **revise y elija** — la mejora visual de `INDEX.md`. Donde los outputs en markdown están construidos para el operador, la página de revisión está construida para la persona que aprueba el gasto: muestra cada concepto como un mockup de plataforma in-feed, descompone los carruseles en un storyboard etiquetado cuadro por cuadro, permite alternar entre variaciones de copy, y divulga qué está anclado en assets reales.

La plantilla está en [assets/creative-review-template.html](../assets/creative-review-template.html). Es un solo archivo — CSS y JS inline, sin build, sin dependencias, sin red. Ábrelo localmente, hospédalo en cualquier host estático (Vercel/Netlify/GitHub Pages), o entrega el archivo `.html` directamente.

## Cuándo Producir Una

- **Presentar un lote para aprobación** — después de la generación del Modo 1 o Modo 3, empaqueta los mejores conceptos en una página de revisión en lugar de (o junto a) `INDEX.md`. Elegir 5 de 50 es una decisión *visual*; un cliente no debería tener que leer markdown para tomarla.
- **Presentar un whitelist / partnership de co-marca** — el formato para el que se construyó el patrón fuente: mostrar al partner exactamente cómo se ve el anuncio bajo cada handle, con la mecánica del rollout explicada.
- **Una revisión de slate mensual** (Modo 4) — renderiza los conceptos del slate para que la decisión sobre el estado de la cuenta y la elección ocurran desde un solo link.

No produzcas una para un ajuste de un solo titular o un chequeo interno rápido — el output en markdown es más rápido. Recurre a la página de revisión cuando un humano que no eres tú necesita elegir.

## Cómo Está Construida

La plantilla se renderiza enteramente a partir de un bloque JSON cerca de la parte superior del archivo — `<script type="application/json" id="review-data">`. Llénalo con tus conceptos generados y todo lo demás se renderiza — pestañas, previews, storyboard, panel de copy. No editas el código de renderizado debajo del bloque de datos. El modelo anotado abajo se muestra con comentarios `//` para legibilidad; **el archivo en sí es JSON estricto** — sin comentarios, sin comas colgantes (ver "Llenando los datos de forma segura").

### Modelo de Datos

```jsonc
{
  project: {
    brand: "Truvani",              // requerido
    agency: "Light Labs",          // opcional — agrega la línea de co-marca + el fallback de handle default (label/iniciales del partner)
    date: "2026-07-12",            // opcional
    note: "contexto de una línea"  // opcional
  },
  platforms: ["instagram", "facebook"],   // previews a ofrecer; el primero es el default. Soportados: instagram, facebook
  concepts: [                              // cada concepto es un ÁNGULO estratégico (ver SKILL.md "Definir los Ángulos")
    {
      name: "Prueba de Metales Pesados",   // requerido — el nombre del ángulo
      tagline: "Lifestyle hero, luego los resultados del laboratorio",   // una línea, qué hace distinto a este concepto
      handles: [                            // opcional. 1 entrada = post normal; 2 = toggle de handle whitelist
        { name: "truvani", partner: "Paid partnership with lightlabs", initials: "TV" },
        { name: "Light Labs", partner: "Paid partnership with truvani", initials: "LL" }
      ],
      frames: [                             // 1 frame = anuncio único; múltiples = storyboard de carrusel
        {
          label: "Hook",                    // el trabajo del frame en el arco narrativo
          prompt: "Toma hero de la bolsa de producto sobre rosa suave, overlay de encaje dorado",  // descripción de imagen (se muestra como placeholder si no hay imagen)
          image: "images/heavy-metal-01.png",   // opcional — URL, ruta relativa, o data URI; omitir para conceptos solo de texto
          headline: "Por fin — una proteína a base de plantas probada por terceros contra metales pesados.",  // overlay opcional por frame
          headlineTheme: "dark"             // opcional: "dark" (default, texto blanco) o "light" (texto oscuro sobre imagen clara)
        }
        // … un objeto por frame
      ],
      headlines: [                          // variaciones seleccionables; la elegida se superpone al frame 1 en el preview
        "Por fin — una proteína a base de plantas probada por terceros contra metales pesados.",
        "Probamos nuestra proteína contra metales pesados. Esto encontró un laboratorio independiente.",
        "La mayoría de los polvos de proteína nunca se prueban contra metales pesados. El nuestro sí."
      ],
      primaryText: "El copy / cuerpo de la caption.",
      destination: { url: "shop.truvani.com", cta: "Comprar ahora", offer: "72% OFF Kit Inicial de Proteína" },
      rollout: {                            // opcional — la mecánica de cómo corre esto (whitelist, plan de lanzamiento)
        title: "Cómo funciona el whitelist",
        steps: ["paso 1", "paso 2", "…"]
      },
      grounding: "Qué en este concepto es real — la divulgación obligatoria. Ver abajo."
    }
    // … 2–4 conceptos es el punto óptimo; más que eso y las pestañas dejan de ser una decisión
  ]
}
```

### El Storyboard de Frames = un Arco Narrativo de Carrusel

Los `frames` de un concepto son su storyboard. Etiqueta cada frame por el *trabajo que hace*, no por su contenido — `Hook`, `El problema`, `Los resultados`, `El ask`. Este es el mismo pensamiento de arco narrativo que los frameworks de carrusel: un concepto liderado por prueba es literalmente Hook → Problema → Mecanismo → Resultados → Contexto → Ask. Para los cinco arcos de carrusel reutilizables (Value-Stack, Problem-Proof, Hack List, Rant Callout, Demo Walkthrough), ver `carousel-frameworks.md` en la habilidad **social** y elegir el arco que se ajuste al ángulo antes de escribir los frames.

### Imágenes vs. Placeholders

Cada frame se renderiza de una de dos formas:
- **`image` proporcionada** — la creatividad real (de la carpeta `images/` del Modo 3, una URL hospedada, o un data URI) llena el frame.
- **`image` omitida** — un placeholder estilizado muestra el `label` del frame + el `prompt`. Este es el estado esperado para conceptos que son copy + prompt de imagen pero aún no renderizados a imagen — la página de revisión es útil *antes* de que existan las imágenes, y sigue siendo útil a medida que se van llenando.

Lanza páginas de revisión con placeholders libremente; comunican el concepto. Reemplázalos por imágenes a medida que se generan.

## Anclaje — el Bloque de Divulgación Es Obligatorio

Cada concepto debe llevar una línea `grounding`, y debe ser verdadera. Esta es la misma regla que el corpus de Insumos con Base en la Realidad, expuesta al cliente: declara exactamente qué es real (qué panel de laboratorio, qué reseña, qué fotografía de producto) y, por omisión, qué es ilustrativo. La línea del patrón fuente es el modelo — *"Los resultados son el panel real de Light Labs de Truvani (Vainilla, probado el 13 de noviembre de 2025). Las imágenes son fotografía propia de producto y lifestyle de Truvani."*

Nunca presentes estadísticas inventadas, resultados de prueba fabricados, o imágenes de stock como propias de la marca. Si la prueba de un concepto aún no es real, la línea de grounding lo dice ("Los resultados mostrados son ilustrativos pendiente del panel de laboratorio") — una página de revisión que lava ficción como hecho es peor que no tener página de revisión.

## Llenando los Datos de Forma Segura

El `DATA` vive en un bloque `<script type="application/json" id="review-data">` — son datos inertes (parseados con `JSON.parse`), no código ejecutable, así que un valor nunca puede correr como script. Dos reglas al escribirlo:

- **Solo JSON válido** — claves y strings entre comillas dobles, sin comentarios, sin comas colgantes. (La página muestra un banner de error claro si el JSON está mal formado, así que un error tipográfico falla ruidosamente, no en silencio.)
- **Escapa `<` como `\u003c` en cada valor de texto.** Un valor que literalmente contenga `</script>` cerraría el bloque de datos antes de tiempo. Como los agentes escriben el JSON, aplica este escape mecánicamente a todos los valores de string. Todos los valores se escapan como HTML de nuevo en tiempo de renderizado, así que esto es defensa en profundidad, pero el escape a nivel de fuente es el que importa — hazlo.

## Produciéndola y Entregándola

1. Copia `assets/creative-review-template.html` a la carpeta de output del lote como `review.html` (por ejemplo, `outputs/YYYY-MM-DD/review.html`).
2. Reemplaza el objeto `DATA` con el proyecto real — conceptos, frames, copy, grounding. Llena las rutas de `image` para cualquier frame que hayas renderizado (mantenlas relativas al archivo html para que la carpeta siga siendo portable).
3. Verifica que se renderiza: ábrelo en un navegador, haz clic en cada pestaña de concepto, ambos toggles de plataforma y handle, y cada frame del storyboard.
4. Entrega: entrega la carpeta (html + `images/`), o hospédala. Para un link de cliente, `vercel deploy` o cualquier host estático funciona — es una sola página con assets locales.

Mantén la página de revisión junto a los outputs en markdown, no en su lugar: `INDEX.md` y los archivos por concepto siguen siendo el registro del operador y el rastro de auditoría de anclaje; `review.html` es la superficie de aprobación construida encima.

## Errores Comunes

- **Demasiados conceptos** — 2–4 pestañas es una decisión; 10 es un menú que nadie termina. Cura antes de presentar.
- **Frames sin etiquetar o etiquetados por contenido** — etiqueta por trabajo narrativo (`La prueba`), no por lo que se muestra (`Captura de tabla`).
- **Grounding faltante o deshonesto** — cada concepto divulga qué es real; la prueba ilustrativa se etiqueta como ilustrativa.
- **Editar el código de renderizado** — todo está impulsado por datos; si algo no se muestra, es un campo de `DATA`, no el JS.
- **Rutas de imagen absolutas** — mantén las rutas de imagen relativas para que la carpeta de output pueda comprimirse, moverse, o hospedarse intacta.
