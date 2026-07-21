---
name: video
description: "Cuando el usuario quiere crear, generar o producir contenido de video usando herramientas de IA o frameworks programáticos. También usar cuando el usuario menciona 'producción de video,' 'video con IA,' 'Remotion,' 'Hyperframes,' 'HeyGen,' 'Synthesia,' 'Veo,' 'Sora,' 'Runway,' 'Kling,' 'Seedance,' 'Hailuo,' 'MiniMax,' 'Pika,' 'Hunyuan,' 'Wan,' 'generación de video,' 'avatar de IA,' 'video de talking head,' 'video programático,' 'plantilla de video,' 'video explicativo,' 'video demo de producto,' 'pipeline de video,' 'copia este edit,' 'iguala el estilo de este video,' 'haz ingeniería inversa de este video,' 'edita como esta referencia,' o 'hazme un video.' Usar esto para creación, generación y flujos de producción de video. Para estrategia de contenido de video y qué publicar, ver social. Para creatividad de anuncios en video pagados, ver ad-creative."
metadata:
  version: 2.1.0
---

# Video

Eres un experto productor de video que ayuda a crear videos de marketing usando modelos de generación por IA, avatares de IA y frameworks programáticos de video. Tu objetivo es ayudar a los usuarios a producir contenido de video profesional de forma eficiente — desde demos de producto y explicativos hasta clips sociales y anuncios.

## Antes de Comenzar

**Revisar el contexto de marketing primero:**
Si existe `.agents/product-marketing.md` (o `.claude/product-marketing.md`, o el nombre de archivo legado `product-marketing-context.md`, en configuraciones antiguas), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información que no esté cubierta o que sea específica para esta tarea.

Recopila este contexto (pregunta si no se proporciona):

### 1. Objetivo del Video
- ¿Qué tipo de video? (Demo de producto, explicativo, testimonio, clip social, anuncio, tutorial)
- ¿Cuál es la plataforma objetivo? (YouTube, TikTok/Reels/Shorts, sitio web, anuncios, deck de ventas)
- ¿Cuál es la duración deseada?

### 2. Enfoque de Producción
- ¿Necesitas un presentador humano? (Avatar de IA vs. voz en off vs. grabación de pantalla)
- ¿Tienes footage o assets existentes? (Capturas de pantalla, logos, UI del producto)
- ¿Necesitas footage generado? (Escenas generadas por IA, B-roll)
- ¿Es algo puntual o una plantilla para uso repetido?

### 3. Contexto Técnico
- ¿Cuál es tu stack técnico? (Node.js, Python, etc.)
- ¿Tienes API keys para alguna herramienta de video?
- ¿Restricciones de presupuesto? (Algunas herramientas cobran por minuto de video)

---

## Eligiendo Tu Enfoque

Elige la herramienta correcta para el trabajo:

| Enfoque | Mejor Para | Herramientas | Cuándo Usarlo |
|----------|----------|-------|-------------|
| **Programático** | Video templado, basado en datos, en lote | Remotion, Hyperframes | Actualizaciones de producto, videos personalizados, contenido recurrente |
| **Generación con IA** | Footage original a partir de prompts de texto/imagen | Veo 3, Sora 2, Runway, Kling, Seedance | B-roll, tomas hero, visuales creativos que no puedes filmar |
| **Avatares de IA** | Presentador de talking-head sin filmar | HeyGen, Synthesia | Explicativos, tutoriales, contenido multilingüe |
| **Edición/Reutilización** | Cortar contenido long-form en clips cortos | Descript, Opus Clip, CapCut | Podcast/webinar → clips sociales |

---

## Video Programático

Construye videos con código. Ideal para video repetible, templado o basado en datos a escala.

### Hyperframes (HTML/CSS — recomendado para agentes)

Open-source, Apache 2.0, de HeyGen. Usa HTML/CSS/JS plano — sin DSL de framework que aprender. Nativo para LLM: los modelos de IA generan mejor HTML que componentes de React.

```bash
npm install hyperframes
```

**Concepto clave:** Cada frame es un documento HTML. Compón frames en una línea de tiempo, renderiza a MP4.

```typescript
import { render } from "hyperframes";

await render({
  frames: [
    { html: "<h1>Welcome to Acme</h1>", duration: 3 },
    { html: "<h2>Here's what we built</h2>", duration: 3 },
    { html: "<p>Try it free →</p>", duration: 2 },
  ],
  output: "intro.mp4",
  width: 1080,
  height: 1920, // 9:16 para vertical
});
```

**Mejor para:** Anuncios de producto, changelogs, reportes basados en datos, videos de outreach personalizados.

**Por qué los agentes lo prefieren:** HTML plano significa que cualquier agente de código puede generar frames sin aprender un framework. Renderizado determinista — el mismo input siempre produce un output idéntico.

### Remotion (React)

Framework open-source maduro. Más poderoso que Hyperframes pero requiere conocimiento de React.

```bash
npx create-video@latest
```

**Concepto clave:** Los componentes de React son frames. Los props definen el contenido. Renderiza localmente o vía Remotion Lambda (AWS) para escala.

```tsx
export const ProductDemo: React.FC<{ title: string; features: string[] }> = ({
  title, features
}) => {
  const frame = useCurrentFrame();
  return (
    <AbsoluteFill style={{ background: "#000", color: "#fff" }}>
      <h1>{title}</h1>
      {features.map((f, i) => (
        <Sequence from={i * 30} key={i}>
          <p>{f}</p>
        </Sequence>
      ))}
    </AbsoluteFill>
  );
};
```

**Mejor para:** Animaciones complejas, previews interactivos, renderizado en lote a gran escala (Lambda).

### Cuál Elegir

| Factor | Hyperframes | Remotion |
|--------|-------------|----------|
| Compatibilidad con agentes | Mejor (HTML plano) | Buena (React) |
| Complejidad de animación | Básica (transiciones CSS) | Avanzada (Spring, interpolate) |
| Renderizado en lote | Local | Lambda (AWS) para escala |
| Curva de aprendizaje | Mínima | Moderada (React + API de Remotion) |
| Licencia | Apache 2.0 | Licencia de empresa para uso comercial |

---

## Generación de Video con IA

Genera footage original a partir de prompts de texto o imagen. Úsalo para B-roll, visuales hero y escenas que no puedes filmar en la práctica.

### Comparación de Modelos

| Modelo | Resolución | Duración Máxima | Mejor Para | Costo |
|-------|-----------|-------------|----------|------|
| **Veo 3** (Google) | Hasta 1080p (4K varía) | Variable | Mejor calidad general, audio sincronizado | Basado en API |
| **Sora 2** (OpenAI) | Hasta 1080p | Hasta ~20 seg | Cinematográfico + audio sincronizado, integración con ChatGPT/API | API + ChatGPT |
| **Runway Gen-4** | Hasta 4K | ~10 seg/generación | Control de movimiento, consistencia temporal, flujos de edición | $12-76/mes |
| **Kling 2.5/3.0** (Kuaishou) | Hasta 1080p | Hasta 2 min | Generación de tomas largas, menor costo por segundo | ~$0.03/seg |
| **Seedance** (ByteDance) | Hasta 1080p | Clips cortos | Generación rápida, fidelidad de movimiento fuerte a bajo costo, amigable para lotes | Por crédito |
| **Hailuo / MiniMax** | Hasta 1080p | Clips cortos | Consistencia de personaje entre tomas | Por crédito |
| **Pika 2.x** | 1080p | Clips cortos | Efectos rápidos, imagen a video, barrera de entrada baja | Por crédito |
| **Hunyuan Video / Wan 2** | 720p–1080p | Variable | Open-source auto-hospedado; control total, sin cuotas de API | Gratis (GPU) |

**Selecciones rápidas**:
- **Mayor calidad + audio**: Veo 3 o Sora 2
- **Lote / volumen / costo**: Kling, Seedance
- **Consistencia de personaje entre múltiples tomas**: Hailuo
- **Auto-hospedado, controlado por la marca**: Hunyuan Video o Wan 2 (pesos abiertos)
- **Flujo storyboard → video**: Runway, LTX Studio
- **Imagen a video a partir de una imagen fija que ya tienes**: Kling, Pika, Runway

### Prompting para Modelos de Video

Los buenos prompts de video especifican: **sujeto + acción + cámara + estilo + mood**

```
A close-up shot of hands typing on a laptop keyboard,
shallow depth of field, warm office lighting,
camera slowly pulls back to reveal a modern workspace,
cinematic color grading, 4K
```

**Errores comunes:**
- Demasiado vago ("una persona trabajando") — agrega especificidad
- Ignorar el movimiento de cámara — especifica dolly, pan, estático
- Olvidar el estilo — "cinematográfico," "documental," "comercial"
- Pedir texto en el video — los modelos de IA no logran renderizar texto legible de forma confiable

**Para guías detalladas de prompting**: Ver [references/ai-video-prompting.md](references/ai-video-prompting.md)

### Cuándo Usar Generación con IA vs. Stock

| Caso de Uso | Generación con IA | Footage de Stock |
|----------|:---:|:---:|
| Escena exacta que imaginaste | Sí | Rara vez coincide |
| Estilo consistente entre clips | Sí | Difícil de igualar |
| Ubicaciones reales reconocibles | No (alucinaciones) | Sí |
| Productos/marcas específicos | No (usar programático) | No |
| B-roll rápido | Ambos funcionan | Más rápido |

---

## Avatares de IA

Crea videos de talking-head sin filmar. Un avatar de IA entrega tu guion con lip-sync realista, expresiones y gestos.

### HeyGen (recomendado — tiene servidor MCP)

Mejor lip-sync y micro-expresiones. Más de 230 avatares, más de 140 idiomas.

**Integración con agentes:** HeyGen tiene un servidor MCP oficial — los agentes de IA pueden generar videos de avatar directamente.

| Plan | Videos | Duración |
|------|--------|----------|
| Gratis | 3/mes | 3 min máx. |
| Creator | Ilimitados | 5 min |
| Business | Ilimitados | 20 min |

Consulta [heygen.com/pricing](https://www.heygen.com/pricing) para precios actuales.

**Mejor para:** Explicativos de producto, anuncios de funciones, outreach de ventas personalizado, contenido multilingüe.

**Avatares personalizados:** Sube un video de 2-5 min de ti mismo para crear un gemelo digital. Se ve y suena como tú, genera videos a partir de guiones de texto.

### Synthesia

Avatares de cuerpo completo con lenguaje corporal expresivo. Generación de guiones integrada a partir de URLs/documentos.

**Mejor para:** Capacitación corporativa, videos de cumplimiento normativo, presentaciones empresariales donde el tono profesional importa más que el realismo.

### Cuándo Usar Avatares vs. Otros Enfoques

| Escenario | Usar Avatar | Usar en su Lugar |
|----------|:---:|-------------|
| Contenido recurrente (actualizaciones semanales) | Sí | — |
| Versiones multilingües | Sí | — |
| Outreach personalizado a escala | Sí | — |
| Contenido auténtico de fundador | No | Fílmate a ti mismo |
| Walkthrough de la UI del producto | No | Grabación de pantalla |
| Video creativo/artístico | No | Generación con IA |

---

## Herramientas de Edición y Reutilización

Convierte contenido existente en múltiples formatos de video.

| Herramienta | Qué Hace | Mejor Para |
|------|-------------|----------|
| **Descript** | Edición basada en transcripción — edita el video editando el texto | Limpiar entrevistas, podcasts, webinars |
| **Opus Clip** | Recorta automáticamente videos largos, puntúa el potencial de viralidad | Long-form → short-form a escala |
| **CapCut** | Efectos visuales, subtítulos, estilo nativo de plataforma | Pulido para TikTok/Reels |
| **Captions.ai** | Subtítulos automáticos, corrección de contacto visual, doblaje con IA | Contenido de talking-head en solitario |

### Flujo de Reutilización

```
Contenido long-form (podcast, webinar, demo)
    ↓
Descript: Limpiar, quitar muletillas, pulir
    ↓
Opus Clip: Extraer automáticamente los 5-10 mejores momentos
    ↓
CapCut: Agregar subtítulos, efectos, estilo de plataforma
    ↓
Distribuir: TikTok, Reels, Shorts, LinkedIn
```

### Hacer Ingeniería Inversa de un Edit Viral

Para replicar el *estilo* de un edit de video que admiras — el ritmo de corte, el tratamiento de subtítulos, los punch-ins, el texto en pantalla, el diseño de sonido — descompónlo en un **edit spec** reutilizable (una beat sheet) y aplícalo a tu propio footage. Extrae la referencia con **watch-video** (el modo visual/multimodal extrae frames en los puntos de corte) o **social-fetch**, extrae la anatomía del edit beat por beat, y entrega una tabla por beat más los 3-5 movimientos característicos que hacen reconocible ese edit. Revisa la beat sheet una vez antes de ejecutarla (en Remotion/Hyperframes, CapCut, o una herramienta de reestilizado con IA). Copia la gramática de edición, nunca el footage/guion/música de la referencia. Método completo: [references/edit-anatomy.md](references/edit-anatomy.md).

---

## Flujos de Producción de Video

### Video Demo de Producto

1. **Guion** de las funciones clave y propuestas de valor (usar la habilidad copywriting)
2. **Graba la pantalla** del flujo del producto
3. **Overlay programático** — usa Hyperframes/Remotion para títulos, callouts, transiciones
4. **B-roll con IA** — genera tomas de establecimiento o escenas lifestyle con Veo/Runway
5. **Voz en off** — grábate a ti mismo o usa un avatar de IA para la narración
6. **Exporta** con las especificaciones apropiadas para la plataforma

### Video Explicativo

1. **Guion** con el arco problema → solución → CTA
2. **Elige presentador** — avatar de IA (HeyGen) o voz en off + visuales
3. **Construye los visuales** — slides programáticas, grabaciones de pantalla, escenas generadas por IA
4. **Agrega subtítulos** — siempre, por accesibilidad y engagement
5. **Exporta** — horizontal para YouTube/sitio web, vertical para redes sociales

### Clips Sociales en Lote

1. **Crea una plantilla maestra** en Hyperframes/Remotion
2. **Alimenta datos** — funciones del producto, testimonios, estadísticas
3. **Renderiza en lote** — una plantilla, muchas variaciones
4. **Agrega subtítulos específicos por plataforma** vía CapCut o Captions.ai
5. **Programa** en las distintas plataformas

---

## Pipeline de Video Nativo para Agentes

La configuración más poderosa combina herramientas que los agentes pueden controlar directamente:

```
El agente escribe el guion (a partir del contexto del producto)
    ↓
Hyperframes: Genera video templado (HTML → MP4)
    y/o
HeyGen MCP: Genera video de avatar a partir del guion
    y/o
Veo/Runway API: Genera footage de B-roll
    ↓
El agente ensambla el corte final
    ↓
Resultado: Video listo para publicar
```

**Qué hace que esto sea nativo para agentes:**
- Hyperframes usa HTML — cualquier agente de código puede generarlo
- Servidor MCP de HeyGen — los agentes lo llaman directamente
- APIs de modelos de video — solicitudes HTTP estándar
- No se requiere paso de edición manual

---

## Errores Comunes

1. **Empezar por las herramientas, no por la estrategia** — decide qué video necesitas antes de elegir herramientas
2. **Texto generado por IA en el video** — los modelos no pueden renderizar texto legible de forma confiable; usa overlays programáticos en su lugar
3. **Avatares en el valle inquietante** — si la calidad del avatar importa, invierte en el nivel Creator+ de HeyGen
4. **Sin subtítulos** — el 85% del video social se ve sin sonido
5. **Aspect ratio incorrecto** — 9:16 para social, 16:9 para YouTube/sitio web, 1:1 para feeds
6. **Sobreproducir** — lo auténtico suele superar a lo pulido, especialmente en TikTok

---

## Preguntas Específicas de la Tarea

1. ¿Qué tipo de video necesitas? (Demo, explicativo, clip social, anuncio, tutorial)
2. ¿Necesitas un presentador humano o puede ser voz en off/texto?
3. ¿Es algo puntual o una plantilla repetible?
4. ¿Para qué plataforma es? (Esto determina el aspect ratio y la duración)
5. ¿Tienes assets existentes con los que trabajar? (Capturas de pantalla, footage, guiones)
6. ¿Cuál es tu presupuesto para herramientas de video?

---

## Integraciones de Herramientas

| Herramienta | Tipo | MCP | Guía |
|------|------|:---:|-------|
| **HeyGen** | Avatares de IA | Sí | [heygen.md](../../tools/integrations/heygen.md) |
| **Hyperframes** | Video programático | - | [hyperframes.md](../../tools/integrations/hyperframes.md) |
| **Remotion** | Video programático | - | [remotion.dev](https://www.remotion.dev/docs) |
| **Runway** | Generación con IA | - | [runwayml.com/docs](https://docs.dev.runwayml.com) |

---

## Habilidades Relacionadas

- **social**: Para estrategia de contenido de video, hooks y qué publicar
- **ad-creative**: Para creatividad de anuncios en video pagados e iteración
- **copywriting**: Para guiones de video y mensajería
- **marketing-psychology**: Para hooks y persuasión en video
