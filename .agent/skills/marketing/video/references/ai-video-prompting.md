# Guía de Prompting para Video con IA

Cómo escribir prompts efectivos para modelos de generación de video con IA (Veo, Runway, Kling, Pika).

---

## Estructura del Prompt

Un prompt de video fuerte sigue esta fórmula:

```
[Sujeto] + [Acción] + [Movimiento de cámara] + [Estilo visual] + [Iluminación/mood] + [Especificaciones técnicas]
```

### Ejemplos de Prompts por Caso de Uso

**Toma hero de producto:**
```
A sleek laptop on a minimal white desk, screen glowing with a dashboard UI,
camera slowly orbits 180 degrees around the desk,
soft volumetric lighting from the left, shallow depth of field,
cinematic commercial aesthetic, 4K
```

**B-roll lifestyle:**
```
A woman in a modern co-working space smiling while looking at her phone,
natural window light, candid documentary feel,
camera handheld with subtle movement, warm color grading
```

**Abstracto/marca:**
```
Flowing liquid gold particles forming the shape of a network graph,
dark background, particles catch light as they move,
slow-motion macro photography style, dramatic rim lighting
```

**Escena explicativa de SaaS:**
```
An overhead shot of a team around a conference table pointing at charts,
camera slowly pushes in, bright modern office,
clean corporate style, even lighting, 1080p
```

---

## Vocabulario de Movimiento de Cámara

Usa estos términos — los modelos de video los entienden:

| Término | Efecto |
|------|--------|
| **Static** | Cámara fija, sin movimiento |
| **Pan left/right** | La cámara rota horizontalmente |
| **Tilt up/down** | La cámara rota verticalmente |
| **Dolly in/out** | La cámara se mueve hacia/desde el sujeto |
| **Orbit** | La cámara rodea al sujeto |
| **Tracking shot** | La cámara sigue al sujeto en movimiento |
| **Crane/aerial** | La cámara sube o desciende |
| **Handheld** | Vibración sutil, sensación documental |
| **Zoom** | Zoom óptico (distinto del dolly) |
| **Slow push** | Dolly in gradual — genera tensión/foco |

---

## Palabras Clave de Estilo

### Cinematográfico
- "cinematic color grading"
- "anamorphic lens flare"
- "shallow depth of field"
- "film grain"
- "35mm film"

### Comercial/Corporativo
- "clean commercial lighting"
- "bright and airy"
- "professional corporate aesthetic"
- "even, diffused lighting"

### Documental
- "handheld documentary style"
- "natural lighting"
- "candid, unposed"
- "observational camera"

### Social/Trendy
- "vertical 9:16"
- "fast-paced cuts"
- "bold text overlays"
- "high contrast, saturated colors"

---

## Tips por Modelo

### Veo (Google)

- Sobresale en fotorrealismo y escenas complejas
- Soporta generación de audio sincronizado con el video
- Funciona mejor con prompts detallados y descriptivos
- Especifica "high resolution" o "1080p" para mejor calidad
- Puede manejar múltiples sujetos y transiciones de escena

### Runway Gen-4

- Control de movimiento fuerte — especifica los movimientos de cámara con precisión
- Mejor consistencia temporal (los sujetos se mantienen consistentes entre frames)
- Usa motion brush para animar áreas específicas
- Imagen a video funciona bien — provee un frame de referencia
- Mantén los prompts bajo 100 palabras para mejores resultados

### Kling

- Puede generar hasta 2 minutos (mucho más largo que otros)
- Bueno para secuencias narrativas más largas
- Más económico para generación en volumen
- La calidad baja ligeramente en duraciones más largas
- Funciona mejor con escenas simples y pocos sujetos

### Pika

- Tiempo de generación más rápido (menos de 2 minutos)
- Bueno para iteraciones rápidas y experimentación
- El modo de efectos agrega movimiento a imágenes fijas
- Mejor para clips cortos (5-15 segundos)
- Menos control sobre el movimiento de cámara

---

## Errores Comunes de Prompting

| Error | Por Qué Falla | Solución |
|---------|-------------|-----|
| "A person using our app" | Demasiado vago, sin detalle visual | Describe a la persona, el entorno, la iluminación, la cámara |
| Incluir texto/logos | La IA no puede renderizar texto legible | Agrega el texto en post con Hyperframes/CapCut |
| "Make it viral" | No es una instrucción visual | Describe el estilo visual que quieres |
| Prompts extremadamente largos (200+ palabras) | Los modelos pierden el foco | Mantén 50-100 palabras, sé específico |
| Sin dirección de cámara | Cámara aleatoria/estática | Siempre especifica el movimiento o "static" |
| "Realistic" solo | No es lo suficientemente específico | "Photorealistic, natural lighting, shot on RED camera" |

---

## Flujo de Prompting

1. **Referencia primero** — encuentra un video real que se parezca a lo que quieres
2. **Descríbelo** — desglosa: sujeto, acción, cámara, estilo, mood
3. **Genera 3-4 variaciones** — mismo concepto, distintos ángulos o estilos
4. **Itera sobre la mejor** — refina el prompt según los resultados
5. **Compón** — combina el footage de IA con texto/overlays programáticos

---

## Aspect Ratios

Siempre especifica en tu prompt o en la configuración de generación:

| Plataforma | Ratio | Resolución |
|----------|-------|-----------|
| YouTube | 16:9 | 1920x1080 o 3840x2160 |
| TikTok/Reels/Shorts | 9:16 | 1080x1920 |
| Instagram Feed | 1:1 o 4:5 | 1080x1080 o 1080x1350 |
| Hero del sitio web | 16:9 | 1920x1080 |
| LinkedIn | 16:9 o 1:1 | 1920x1080 |

---

## Optimización de Costos

- **Itera a baja resolución** — haz upscale solo de la versión final
- **Usa Kling para borradores** — el más barato por segundo, cambia a Veo/Runway para las versiones finales
- **Imagen a video** — proveer un frame de referencia ahorra créditos de generación y da mejores resultados
- **Agrupa prompts similares** — los modelos suelen ofrecer descuentos por volumen
- **Guarda y reutiliza** — los clips de B-roll pueden reutilizarse en múltiples videos
