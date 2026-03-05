# Herramientas de IA Generativa para Creatividades Publicitarias

Referencia para usar generadores de imágenes con IA, generadores de video y herramientas de video basadas en código para producir visuales publicitarios a escala.

---

## Cuándo Usar Herramientas Generativas

| Necesidad | Categoría de Herramienta | Mejor Opción |
|-----------|--------------------------|--------------|
| Imágenes estáticas para anuncios (banners, redes sociales) | Generación de imágenes | Nano Banana Pro, Flux, Ideogram |
| Imágenes de anuncios con texto superpuesto | Generación de imágenes (con capacidad de texto) | Ideogram, Nano Banana Pro |
| Anuncios en video cortos (6-30 seg) | Generación de video | Veo, Kling, Runway, Sora, Seedance |
| Anuncios en video con locución | Gen. de video + voz | Veo/Sora (nativo), o Runway + ElevenLabs |
| Pistas de locución para anuncios | Generación de voz | ElevenLabs, OpenAI TTS, Cartesia |
| Versiones de anuncios en múltiples idiomas | Generación de voz | ElevenLabs, PlayHT |
| Clonación de voz de marca | Generación de voz | ElevenLabs, Resemble AI |
| Mockups de productos y variaciones | Generación de imágenes + referencias | Flux (referencia multi-imagen) |
| Anuncios en video plantillados a escala | Video basado en código | Remotion |
| Video personalizado (nombre, datos) | Video basado en código | Remotion |
| Variaciones consistentes con la marca | Gen. de imágenes + refs de estilo | Flux, Ideogram, Nano Banana Pro |

---

## Generación de Imágenes

### Nano Banana Pro (Gemini)

El modelo de generación de imágenes de Google DeepMind, disponible a través de la Gemini API.

**Mejor para:** Imágenes publicitarias de alta calidad, visuales de productos, renderizado de texto
**API:** Gemini API (Google AI Studio, Vertex AI)
**Precios:** ~$0.04/imagen (Gemini 2.5 Flash Image), ~$0.24/imagen 4K (Nano Banana Pro)

**Puntos fuertes:**
- Fuerte renderizado de texto en imágenes (logotipos, titulares)
- Edición nativa de imágenes (modificar imágenes existentes con prompts)
- Disponible a través de la misma Gemini API usada para generación de texto
- Admite tanto generación como edición en un solo modelo

**Casos de uso para creatividades publicitarias:**
- Generar imágenes para anuncios en redes sociales a partir de descripciones de texto
- Crear variaciones de mockups de productos
- Editar imágenes de anuncios existentes (cambiar fondos, cambiar colores)
- Generar imágenes con texto de titular integrado

**Ejemplo de API:**
```bash
# Usando la Gemini API para generación de imágenes
curl -X POST "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-image:generateContent" \
  -H "Content-Type: application/json" \
  -H "x-goog-api-key: $GEMINI_API_KEY" \
  -d '{
    "contents": [{"parts": [{"text": "Create a clean, modern social media ad image for a project management tool. Show a laptop with a kanban board interface. Bright, professional, 16:9 ratio."}]}],
    "generationConfig": {"responseModalities": ["TEXT", "IMAGE"]}
  }'
```

**Documentación:** [Gemini Image Generation](https://ai.google.dev/gemini-api/docs/image-generation)

---

### Flux (Black Forest Labs)

Modelos de generación de imágenes de código abierto con acceso a API a través de Replicate y la API nativa de BFL.

**Mejor para:** Imágenes fotorrealistas, variaciones consistentes con la marca, generación multi-referencia
**API:** Replicate, BFL API, fal.ai
**Precios:** ~$0.01-0.06/imagen según el modelo y la resolución

**Variantes del modelo:**
| Modelo | Velocidad | Calidad | Costo | Mejor Para |
|--------|-----------|---------|-------|------------|
| Flux 2 Pro | ~6 seg | Más alta | $0.015/MP | Assets de producción final |
| Flux 2 Flex | ~22 seg | Alta + edición | $0.06/MP | Edición iterativa |
| Flux 2 Dev | ~2.5 seg | Buena | $0.012/MP | Prototipado rápido |
| Flux 2 Klein | Más rápido | Buena | Más bajo | Generación en lote de alto volumen |

**Puntos fuertes:**
- Referencia multi-imagen (hasta 8 imágenes) para identidad consistente entre anuncios
- Consistencia de producto — mismo producto en diferentes contextos
- Transferencia de estilo desde imágenes de referencia
- Modelo Dev de código abierto para autoalojamiento

**Casos de uso para creatividades publicitarias:**
- Generar 50+ variaciones de anuncios con identidad consistente de producto/persona
- Crear imágenes de producto en contexto (tu SaaS en diferentes dispositivos)
- Hacer coincidir el estilo con los assets de marca existentes usando imágenes de referencia
- Generar rápidamente variaciones de imágenes para pruebas A/B

**Documentación:** [Replicate Flux](https://replicate.com/black-forest-labs/flux-2-pro), [BFL API](https://docs.bfl.ml/)

---

### Ideogram

Especializado en tipografía y renderizado de texto dentro de imágenes.

**Mejor para:** Banners publicitarios con texto, gráficos de marca, imágenes para anuncios en redes sociales con titulares
**API:** Ideogram API, Runware
**Precios:** ~$0.06/imagen (API), ~$0.009/imagen (suscripción)

**Puntos fuertes:**
- Renderizado de texto líder en la categoría (~90% de precisión vs ~30% de la mayoría de herramientas)
- Sistema de referencia de estilo (subir hasta 3 imágenes de referencia)
- 4,300 millones de preajustes de estilo para estética de marca consistente
- Fuerte en logotipos y tipografía de marca

**Casos de uso para creatividades publicitarias:**
- Generar banners publicitarios con texto de titular directamente en la imagen
- Crear gráficos para redes sociales con texto de marca superpuesto
- Producir múltiples variaciones de diseño con tipografía consistente
- Generar materiales promocionales sin necesitar un diseñador para cada iteración

**Documentación:** [Ideogram API](https://developer.ideogram.ai/), [Ideogram](https://ideogram.ai/)

---

### Otras Herramientas de Imágenes

| Herramienta | Mejor Para | Estado de API | Notas |
|-------------|------------|---------------|-------|
| **DALL-E 3** (OpenAI) | Generación general de imágenes | API oficial | Integrado con ChatGPT, buen renderizado de texto |
| **Midjourney** | Imágenes artísticas de alta estética | Sin API pública oficial | Basado en Discord; existen APIs no oficiales pero arriesgan bloqueos |
| **Stable Diffusion** | Autoalojado, personalizable | Código abierto | Mejor para equipos con infraestructura GPU |

---

## Generación de Video

### Google Veo

El modelo de generación de video de Google DeepMind, disponible a través de la Gemini API y Vertex AI.

**Mejor para:** Anuncios en video de alta calidad con audio nativo, video vertical para redes sociales
**API:** Gemini API, Vertex AI
**Precios:** ~$0.15/seg (Veo 3.1 Fast), ~$0.40/seg (Veo 3.1 Standard)

**Capacidades:**
- Hasta 60 segundos a 1080p
- Generación de audio nativo (diálogo, efectos de sonido, ambiente)
- Salida vertical 9:16 para Stories/Reels/Shorts
- Escalar a 4K
- Texto a video e imagen a video

**Casos de uso para creatividades publicitarias:**
- Generar anuncios en video cortos (15-30 seg) a partir de descripciones de texto
- Crear anuncios en video vertical para TikTok, Reels, Shorts
- Producir demos de productos con locución
- Generar múltiples variaciones de video a partir del mismo prompt con diferentes estilos

**Documentación:** [Veo on Vertex AI](https://cloud.google.com/vertex-ai/generative-ai/docs/video/overview)

---

### Kling (Kuaishou)

Generación de video con generación audiovisual simultánea y controles de cámara.

**Mejor para:** Anuncios en video cinematográficos, contenido de formato más largo, video sincronizado con audio
**API:** Kling API, PiAPI, fal.ai
**Precios:** ~$0.09/seg (vía fal.ai de terceros)

**Capacidades:**
- Hasta 3 minutos a 1080p/30-48fps
- Generación audiovisual simultánea (Kling 2.6)
- Texto a video e imagen a video
- Controles de movimiento y cámara

**Casos de uso para creatividades publicitarias:**
- Videos de explicación de productos de mayor duración
- Videos de marca cinematográficos con audio sincronizado
- Animar imágenes de productos en anuncios de video

**Documentación:** [Kling AI Developer](https://klingai.com/global/dev/model/video)

---

### Runway

Plataforma de generación y edición de video con fuerte controlabilidad.

**Mejor para:** Generación de video controlada, contenido consistente con el estilo, edición de metraje existente
**API:** Runway Developer Portal

**Capacidades:**
- Gen-4: Consistencia de personaje/escena entre planos
- Pincel de movimiento y controles de cámara
- Imagen a video con imágenes de referencia
- Transferencia de estilo de video a video

**Casos de uso para creatividades publicitarias:**
- Generar anuncios en video con personajes/productos consistentes entre escenas
- Transferir el estilo de metraje existente para que coincida con la estética de la marca
- Extender o remezclar contenido de video existente

**Documentación:** [Runway API](https://docs.dev.runwayml.com/)

---

### Sora 2 (OpenAI)

El modelo de generación de video de OpenAI con audio sincronizado.

**Mejor para:** Video de alta fidelidad con diálogo y sonido
**API:** OpenAI API
**Precios:** Nivel gratuito disponible; Pro desde $0.10-0.50/seg según la resolución

**Capacidades:**
- Hasta 60 segundos con audio sincronizado
- Diálogo, efectos de sonido y audio ambiental
- Variantes sora-2 (rápido) y sora-2-pro (calidad)
- Texto a video e imagen a video

**Casos de uso para creatividades publicitarias:**
- Testimonios en video y anuncios estilo talking-head
- Videos de demo de productos con narración
- Videos de marca narrativos

**Documentación:** [OpenAI Video Generation](https://platform.openai.com/docs/guides/video-generation)

---

### Seedance 2.0 (ByteDance)

El modelo de generación de video de ByteDance con generación audiovisual simultánea y entradas multimodales.

**Mejor para:** Anuncios en video rápidos y asequibles con audio nativo, entradas de referencia multimodal
**API:** BytePlus (oficial), Replicate, WaveSpeedAI, fal.ai (terceros); formato de API compatible con OpenAI
**Precios:** ~$0.10-0.80/min según la resolución (estimado 10-100x más barato que Sora 2 por clip)

**Capacidades:**
- Hasta 20 segundos a resolución de hasta 2K
- Generación audiovisual simultánea (Dual-Branch Diffusion Transformer)
- Texto a video e imagen a video
- Hasta 12 archivos de referencia para entrada multimodal
- Estructura de API compatible con OpenAI

**Casos de uso para creatividades publicitarias:**
- Producción de anuncios en video cortos de alto volumen a bajo costo
- Anuncios en video con locución sincronizada y efectos de sonido en una sola pasada
- Generación multi-referencia (alimentar imágenes de productos, assets de marca, referencias de estilo)
- Iteración rápida en conceptos de anuncios en video

**Documentación:** [Seedance](https://seed.bytedance.com/en/seedance2_0)

---

### Higgsfield

Plataforma de creación de video completa con controles de cámara cinematográficos.

**Mejor para:** Anuncios en video para redes sociales, estilo cinematográfico, contenido mobile-first
**Plataforma:** [higgsfield.ai](https://higgsfield.ai/)

**Capacidades:**
- Más de 50 movimientos de cámara profesionales (zooms, paneo, tomas con dron FPV)
- Animación de imagen a video
- Edición integrada, transiciones y keyframing
- Flujo de trabajo todo en uno: generación de imagen, animación, edición

**Casos de uso para creatividades publicitarias:**
- Anuncios en video para redes sociales con sensación cinematográfica
- Animar imágenes de productos en video dinámico
- Crear múltiples variaciones de video con diferentes estilos de cámara
- Contenido de video de entrega rápida para campañas en redes sociales

---

### Comparación de Herramientas de Video

| Herramienta | Duración Máx. | Audio | Resolución | API | Mejor Para |
|-------------|---------------|-------|------------|-----|------------|
| **Veo 3.1** | 60 seg | Nativo | 1080p/4K | Gemini | Video social vertical |
| **Kling 2.6** | 3 min | Nativo | 1080p | Terceros | Cinematográfico largo |
| **Runway Gen-4** | 10 seg | No | 1080p | Oficial | Controlado, consistente |
| **Sora 2** | 60 seg | Nativo | 1080p | Oficial | Con mucho diálogo |
| **Seedance 2.0** | 20 seg | Nativo | 2K | Oficial + terceros | Alto volumen asequible |
| **Higgsfield** | Variable | Sí | 1080p | Basado en web | Social, mobile-first |

---

## Generación de Voz y Audio

Para superponer locuciones realistas en anuncios de video, agregar narración a demos de productos o generar audio para videos renderizados con Remotion. Estas herramientas convierten scripts de anuncios en pistas de voz con sonido natural.

### Cuándo Usar Herramientas de Voz

Muchos generadores de video (Veo, Kling, Sora, Seedance) ahora incluyen audio nativo. Usa herramientas de voz independientes cuando necesites:

- **Locución en video silencioso** — Runway Gen-4 y Remotion producen salida sin audio
- **Consistencia de voz de marca** — Clonar una voz específica para todos los anuncios
- **Versiones en múltiples idiomas** — El mismo script de anuncio en 20+ idiomas
- **Iteración de scripts** — Regresar a grabar la locución sin volver a filmar el video
- **Control preciso** — Temporización exacta, emoción y ritmo

---

### ElevenLabs

El líder del mercado en generación de voz realista y clonación de voz.

**Mejor para:** Locuciones con el sonido más natural, clonación de voz de marca, multilingüe
**API:** REST API con soporte de streaming
**Precios:** ~$0.12-0.30 por 1,000 caracteres según el plan; desde $5/mes

**Capacidades:**
- Más de 29 idiomas con acento e entonación naturales
- Clonación de voz desde clips de audio cortos (instantánea) o grabaciones más largas (profesional)
- Control de emoción y estilo
- Streaming para generación en tiempo real
- Biblioteca de voces con cientos de voces preconstruidas

**Casos de uso para creatividades publicitarias:**
- Generar pistas de locución para anuncios en video
- Clonar la voz del portavoz de tu marca para todas las variaciones de anuncios
- Producir el mismo anuncio en 10+ idiomas desde un solo script
- Pruebas A/B de diferentes estilos de voz (autoritativo vs. amigable vs. urgente)

**Ejemplo de API:**
```bash
curl -X POST "https://api.elevenlabs.io/v1/text-to-speech/{voice_id}" \
  -H "xi-api-key: $ELEVENLABS_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "text": "Stop wasting hours on manual reporting. Try DataFlow free for 14 days.",
    "model_id": "eleven_multilingual_v2",
    "voice_settings": {"stability": 0.5, "similarity_boost": 0.75}
  }' --output voiceover.mp3
```

**Documentación:** [ElevenLabs API](https://elevenlabs.io/docs/api-reference/text-to-speech)

---

### OpenAI TTS

Texto a voz simple y asequible integrado en la OpenAI API.

**Mejor para:** Locuciones rápidas, rentable a escala, integración sencilla
**API:** OpenAI API (mismo SDK que GPT/DALL-E)
**Precios:** $15/millón de chars (estándar), $30/millón de chars (HD); ~$0.015/min con gpt-4o-mini-tts

**Capacidades:**
- 13 voces integradas (sin clonación personalizada)
- Múltiples idiomas
- Streaming en tiempo real
- Opción de calidad HD
- API sencilla — el mismo SDK que ya usas para GPT

**Casos de uso para creatividades publicitarias:**
- Locución rápida y económica para versiones de anuncios en borrador/prueba
- Narración de alto volumen a bajo costo
- Prototipar audio de anuncios antes de invertir en voz premium

**Documentación:** [OpenAI TTS](https://platform.openai.com/docs/guides/text-to-speech)

---

### Cartesia Sonic

Generación de voz de latencia ultra-baja construida para aplicaciones en tiempo real.

**Mejor para:** Voz en tiempo real, latencia más baja, expresividad emocional
**API:** REST + streaming WebSocket
**Precios:** Desde $5/mes; pago por uso desde $0.03/min

**Capacidades:**
- 40ms de tiempo hasta el primer audio (el más rápido de su clase)
- Más de 15 idiomas
- Expresividad no verbal: risas, respiración, inflexiones emocionales
- Sonic Turbo para latencia aún más baja
- API de streaming para generación en tiempo real

**Casos de uso para creatividades publicitarias:**
- Vista previa de anuncios en tiempo real durante la iteración creativa
- Videos de demo interactivos con narración dinámica
- Anuncios que requieren risas naturales, suspiros o reacciones emocionales

**Documentación:** [Cartesia Sonic](https://docs.cartesia.ai/build-with-cartesia/tts-models/latest)

---

### Voicebox (Código Abierto)

Estudio de síntesis de voz gratuito y local, impulsado por Qwen3-TTS. La alternativa de código abierto a ElevenLabs.

**Mejor para:** Clonación de voz gratuita, generación local/privada, producción en lote sin costo
**API:** API REST local en `http://localhost:8000`
**Precios:** Gratuito (licencia MIT). Se ejecuta completamente en tu máquina.
**Stack:** Tauri (Rust) + React + FastAPI (Python)

**Capacidades:**
- Clonación de voz a partir de muestras de audio cortas vía Qwen3-TTS
- Soporte multilingüe (inglés, chino, más idiomas planeados)
- Editor de línea de tiempo con múltiples pistas para componer conversaciones
- Inferencia 4-5x más rápida en Apple Silicon vía MLX Metal acceleration
- API REST local para generación programática
- Sin dependencia en la nube — todo el procesamiento en el dispositivo

**Casos de uso para creatividades publicitarias:**
- Clonación de voz gratuita para el portavoz de la marca en todas las variaciones de anuncios
- Generación de locuciones en lote sin costos por carácter
- Generación privada/local cuando el contenido del anuncio es sensible o pre-lanzamiento
- Prototipar variaciones de voz antes de comprometerse con un servicio pago

**Ejemplo de API:**
```bash
curl -X POST http://localhost:8000/generate \
  -H "Content-Type: application/json" \
  -d '{"text": "Stop wasting hours on manual reporting.", "profile_id": "abc123", "language": "en"}'
```

**Instalación:** Aplicaciones de escritorio para macOS y Windows en [voicebox.sh](https://voicebox.sh), o compilar desde el código fuente:
```bash
git clone https://github.com/jamiepine/voicebox.git
cd voicebox && make setup && make dev
```

**Documentación:** [GitHub](https://github.com/jamiepine/voicebox)

---

### Otras Herramientas de Voz

| Herramienta | Mejor Para | Diferenciador | API |
|-------------|------------|---------------|-----|
| **PlayHT** | Gran biblioteca de voces, baja latencia | Más de 900 voces, <300ms de latencia, ultra realista | [play.ht](https://play.ht/) |
| **Resemble AI** | Clonación de voz empresarial | Despliegue on-premise, voz a voz en tiempo real | [resemble.ai](https://www.resemble.ai/) |
| **WellSaid Labs** | Voces éticas y seguras para uso comercial | Voces de actores compensados, seguras para uso comercial | [wellsaid.io](https://www.wellsaid.io/) |
| **Fish Audio** | Económico, control de emoción | ~50-70% más barato que ElevenLabs, etiquetas de emoción | [fish.audio](https://fish.audio/) |
| **Murf AI** | Equipos no técnicos | Estudio en navegador, más de 200 voces | [murf.ai](https://murf.ai/) |
| **Google Cloud TTS** | Ecosistema Google, escala | Más de 220 voces, más de 40 idiomas, SLAs empresariales | [Google TTS](https://cloud.google.com/text-to-speech) |
| **Amazon Polly** | Ecosistema AWS, costo | Voces neurales, control SSML, económico a gran volumen | [Amazon Polly](https://aws.amazon.com/polly/) |

---

### Comparación de Herramientas de Voz

| Herramienta | Calidad | Clonación | Idiomas | Latencia | Precio/1K chars |
|-------------|---------|-----------|---------|----------|-----------------|
| **ElevenLabs** | Mejor | Sí (instant + pro) | 29+ | ~200ms | $0.12-0.30 |
| **OpenAI TTS** | Buena | No | 13+ | ~300ms | $0.015-0.030 |
| **Cartesia Sonic** | Muy buena | No | 15+ | ~40ms | ~$0.03/min |
| **PlayHT** | Muy buena | Sí | 140+ | <300ms | ~$0.10-0.20 |
| **Fish Audio** | Buena | Sí | 13+ | ~200ms | ~$0.05-0.10 |
| **WellSaid** | Muy buena | No (voces de actores) | Inglés | ~300ms | Precio personalizado |
| **Voicebox** | Buena | Sí (local) | 2+ | Local | Gratis (código abierto) |

### Cómo Elegir una Herramienta de Voz

```
¿Necesitas locución para anuncios?
├── ¿Necesitas clonar una voz de marca específica?
│   ├── Mejor calidad → ElevenLabs
│   ├── Empresarial/on-premise → Resemble AI
│   └── Económico → Fish Audio, PlayHT
├── ¿Necesitas multilingüe (mismo anuncio, muchos idiomas)?
│   ├── Más idiomas → PlayHT (140+)
│   └── Mejor calidad → ElevenLabs (29+)
├── ¿Necesitas gratuito / código abierto / local?
│   └── Voicebox (MIT, se ejecuta en tu máquina)
├── ¿Necesitas económico, rápido y suficientemente bueno?
│   └── OpenAI TTS ($0.015/min)
├── ¿Necesitas licencias comercialmente seguras?
│   └── WellSaid Labs (voces de actores compensados)
└── ¿Necesitas tiempo real/interactivo?
    └── Cartesia Sonic (40ms TTFA)
```

### Flujo de Trabajo: Voz + Video

```
1. Escribir el script del anuncio (usar la habilidad ad-creative para el copy)
2. Generar la locución con ElevenLabs/OpenAI TTS
3. Generar o renderizar el video:
   a. Video silencioso desde Runway/Remotion → superponer pista de voz
   b. O usar Veo/Sora/Seedance con audio nativo (omitir VO separado)
4. Combinar con ffmpeg si se superpone por separado:
   ffmpeg -i video.mp4 -i voiceover.mp3 -c:v copy -c:a aac output.mp4
5. Generar variaciones (diferentes scripts, voces o idiomas)
```

---

## Video Basado en Código: Remotion

Para anuncios en video plantillados y basados en datos a escala, Remotion es la mejor opción. A diferencia de los generadores de video con IA que producen video único a partir de prompts, Remotion usa código React para renderizar video determinista y perfecto para la marca a partir de plantillas y datos.

**Mejor para:** Variaciones de anuncios plantillados, video personalizado, producción consistente con la marca
**Stack:** React + TypeScript
**Precios:** Gratis para individuos/equipos pequeños; licencia comercial requerida para 4+ empleados
**Documentación:** [remotion.dev](https://www.remotion.dev/)

### Por Qué Remotion para Anuncios

| Generadores de Video con IA | Remotion |
|-----------------------------|----------|
| Salida única cada vez | Determinista, pixel-perfect |
| Basado en prompts, menos control | Control total del código sobre cada frame |
| Difícil de hacer coincidir exactamente con la marca | Colores, fuentes y espaciado exactos de la marca |
| Generación de a uno por vez | Renderizar cientos en lote desde datos |
| Sin inserción de datos dinámicos | Personalizar con nombres, precios, estadísticas |

### Casos de Uso para Creatividades Publicitarias

**1. Anuncios dinámicos de productos**
Alimentar un array JSON de productos y renderizar un anuncio en video único para cada uno:
```tsx
// Componente Remotion simplificado para anuncios de productos
export const ProductAd: React.FC<{
  productName: string;
  price: string;
  imageUrl: string;
  tagline: string;
}> = ({productName, price, imageUrl, tagline}) => {
  return (
    <AbsoluteFill style={{backgroundColor: '#fff'}}>
      <Img src={imageUrl} style={{width: 400, height: 400}} />
      <h1>{productName}</h1>
      <p>{tagline}</p>
      <div className="price">{price}</div>
      <div className="cta">Shop Now</div>
    </AbsoluteFill>
  );
};
```

**2. Variaciones de video para pruebas A/B**
Renderizar la misma plantilla con diferentes titulares, CTAs o esquemas de color:
```tsx
const variations = [
  {headline: "Save 50% Today", cta: "Get the Deal", theme: "urgent"},
  {headline: "Join 10K+ Teams", cta: "Start Free", theme: "social-proof"},
  {headline: "Built for Speed", cta: "Try It Now", theme: "benefit"},
];
// Renderizar todas las variaciones programáticamente
```

**3. Videos de contacto personalizados**
Generar videos dirigidos a prospectos por nombre para contacto en frío o ventas.

**4. Producción en lote de anuncios para redes sociales**
Renderizar el mismo contenido en diferentes relaciones de aspecto:
- 1:1 para feed
- 9:16 para Stories/Reels
- 16:9 para YouTube

### Flujo de Trabajo de Remotion para Creatividades Publicitarias

```
1. Diseñar la plantilla en React (o usar IA para generar el componente)
2. Definir el esquema de datos (productos, titulares, CTAs, imágenes)
3. Alimentar el array de datos en la plantilla
4. Renderizar en lote todas las variaciones
5. Subir a la plataforma publicitaria
```

### Primeros Pasos

```bash
# Crear un nuevo proyecto Remotion
npx create-video@latest

# Renderizar un único video
npx remotion render src/index.ts MyComposition out/video.mp4

# Renderizar en lote desde datos
npx remotion render src/index.ts MyComposition --props='{"data": [...]}'
```

---

## Cómo Elegir la Herramienta Correcta

### Árbol de Decisión

```
¿Necesitas anuncios en video?
├── Plantillados, basados en datos (misma estructura, diferentes datos)
│   └── Usar Remotion
├── Creativo único desde prompts (exploratorio)
│   ├── ¿Necesitas diálogo/locución? → Sora 2, Veo 3.1, Kling 2.6, Seedance 2.0
│   ├── ¿Necesitas consistencia entre escenas? → Runway Gen-4
│   ├── ¿Necesitas video social vertical? → Veo 3.1 (9:16 nativo)
│   ├── ¿Necesitas alto volumen a bajo costo? → Seedance 2.0
│   └── ¿Necesitas trabajo de cámara cinematográfico? → Higgsfield, Kling
└── Ambos → Usar IA gen para creatividad hero, Remotion para variaciones

¿Necesitas anuncios de imagen?
├── ¿Necesitas texto/titulares en la imagen? → Ideogram
├── ¿Necesitas consistencia de producto entre variaciones? → Flux (multi-ref)
├── ¿Necesitas iteraciones rápidas en imágenes existentes? → Nano Banana Pro
├── ¿Necesitas la mayor calidad visual? → Flux Pro, Midjourney
└── ¿Necesitas alto volumen a bajo costo? → Flux Klein, Nano Banana
```

### Comparación de Costos para 100 Variaciones de Anuncios

| Enfoque | Herramienta | Costo Aproximado |
|---------|-------------|------------------|
| 100 imágenes estáticas | Nano Banana Pro | ~$4-24 |
| 100 imágenes estáticas | Flux Dev | ~$1-2 |
| 100 imágenes estáticas | Ideogram API | ~$6 |
| 100 × videos de 15 seg | Veo 3.1 Fast | ~$225 |
| 100 × videos de 15 seg | Remotion (plantillado) | ~$0 (renderizado autoalojado) |
| 10 videos hero + 90 plantillados | Veo + Remotion | ~$22 + tiempo de renderizado |

### Flujo de Trabajo Recomendado para Producción Publicitaria a Escala

1. **Generar creatividad hero** con IA (Nano Banana, Flux, Veo) — alta calidad, exploratorio
2. **Construir plantillas** en Remotion basadas en patrones creativos ganadores
3. **Producir variaciones en lote** con Remotion usando datos (productos, titulares, CTAs)
4. **Iterar** — usar herramientas de IA para nuevos ángulos, Remotion para escala

Este enfoque híbrido te brinda la exploración creativa de los generadores de IA y la consistencia y escala del renderizado basado en código.

---

## Especificaciones de Imagen por Plataforma

Al generar imágenes para anuncios, solicitar las dimensiones correctas:

| Plataforma | Posicionamiento | Relación de Aspecto | Tamaño Recomendado |
|------------|-----------------|---------------------|---------------------|
| Meta Feed | Imagen única | 1:1 | 1080x1080 |
| Meta Stories/Reels | Vertical | 9:16 | 1080x1920 |
| Meta Carousel | Cuadrado | 1:1 | 1080x1080 |
| Google Display | Horizontal | 1.91:1 | 1200x628 |
| Google Display | Cuadrado | 1:1 | 1200x1200 |
| LinkedIn Feed | Horizontal | 1.91:1 | 1200x627 |
| LinkedIn Feed | Cuadrado | 1:1 | 1200x1200 |
| TikTok Feed | Vertical | 9:16 | 1080x1920 |
| Twitter/X Feed | Horizontal | 16:9 | 1200x675 |
| Twitter/X Card | Horizontal | 1.91:1 | 800x418 |

Incluir estas dimensiones en los prompts de generación para evitar necesitar recortar o redimensionar.
