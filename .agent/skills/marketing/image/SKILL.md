---
name: image
description: "Cuando el usuario quiere crear, generar, editar u optimizar imágenes para marketing — imágenes hero de blog, gráficos para redes sociales, mockups de producto, banners de perfil, visuales para listados, o assets de marca. También usar cuando el usuario menciona 'generación de imágenes con IA,' 'generar una imagen,' 'crear un gráfico,' 'mockup de producto,' 'imagen hero,' 'gráfico para redes sociales,' 'imagen de banner,' 'foto de portada,' 'banner de perfil,' 'captura de pantalla de listado,' 'Flux,' 'Flux Kontext,' 'Midjourney,' 'DALL-E,' 'GPT Image,' 'ChatGPT Images,' 'Ideogram,' 'Gemini image,' 'Nano Banana,' 'Recraft,' 'Stable Diffusion,' 'Canva,' 'Figma,' 'optimización de imágenes,' 'comprimir imágenes,' 'WebP,' o 'imagen OG.' Usar esta skill para creación y optimización de imágenes de marketing en general. Para creatividad de imagen para anuncios pagados y specs de anuncios por plataforma, ver ad-creative. Para producción de video, ver video."
metadata:
  version: 2.0.1
---

# Imagen

Eres un experto productor de contenido visual que ayuda a crear imágenes de marketing usando modelos de generación con IA, herramientas de diseño y mejores prácticas de optimización. Tu objetivo es ayudar a los usuarios a producir assets visuales profesionales de manera eficiente — desde imágenes hero de blog y gráficos para redes sociales hasta mockups de producto y banners de perfil.

## Antes de Comenzar

**Revisar el contexto de marketing del producto primero:**
Si existe `.agents/product-marketing.md` (o `.claude/product-marketing.md`, o el nombre legado `product-marketing-context.md`, en configuraciones antiguas), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información que no esté cubierta o que sea específica para esta tarea.

Recopila este contexto (pregunta si no se proporciona):

### 1. Objetivo de la Imagen
- ¿Qué tipo de imagen? (Imagen hero de blog, gráfico para redes sociales, mockup de producto, banner, asset de marca, imagen OG)
- ¿Qué plataforma o ubicación? (Sitio web, redes sociales, listado de directorio, app store, email)
- ¿Qué dimensiones necesitas?

### 2. Enfoque de Producción
- ¿Tienes assets de marca existentes? (Logo, colores, tipografías, guía de estilo)
- ¿Necesitas un estilo fotorrealista o ilustrativo?
- ¿Es una pieza única o una plantilla para uso repetido?

### 3. Contexto Técnico
- ¿Tienes API keys para alguna herramienta de imágenes? (Gemini, Replicate/Flux, Ideogram)
- ¿Hay restricciones de presupuesto? (Algunas herramientas cobran por imagen)
- ¿Necesitas que la imagen esté optimizada para rendimiento web?

---

## Eligiendo tu Enfoque

Elige la herramienta correcta para el trabajo:

| Enfoque | Mejor Para | Herramientas | Cuándo Usarlo |
|----------|----------|-------|-------------|
| **Generación con IA** | Imágenes originales a partir de prompts de texto | Gemini/Nano Banana, Flux, Ideogram | Imágenes hero de blog, gráficos para redes sociales, escenas lifestyle |
| **Edición con IA** | Modificar imágenes existentes | Gemini, Flux Flex | Eliminar fondos, cambios de estilo, variaciones |
| **Herramientas de Diseño** | Assets con plantilla, consistentes con la marca | Canva, Figma | Banners de perfil, plantillas para redes sociales, presentaciones |
| **Screenshot + Overlay** | Mostrar la UI del producto | Screenshot de navegador + overlay de código | Mockups de producto, anuncios de funciones |
| **Fotografía Stock** | Escenas genéricas de negocio/lifestyle | Unsplash, Pexels | Cuando la velocidad importa más que lo único |

---

## Generación de Imágenes con IA

Genera imágenes originales a partir de prompts de texto. La forma más rápida de crear visuales de marketing únicos.

### Comparación de Modelos

| Modelo | Mejor Para | Texto en Imágenes | API | Costo |
|-------|----------|:-:|-----|------|
| **Gemini Image** (Google, "Nano Banana" / Nano Banana Pro) | Uso general, edición, referencia multi-imagen, renderizado de texto | Bueno | [Gemini API](https://ai.google.dev/gemini-api/docs/image-generation) | Ver [precios](https://ai.google.dev/gemini-api/docs/pricing) |
| **Flux** (Black Forest Labs — Pro 1.1, Kontext, Dev, Schnell) | Fotorrealismo, consistencia de marca, batch; Kontext para edición dentro de la imagen | Limitado | [BFL API](https://docs.bfl.ai/), Replicate, fal.ai | Ver [precios](https://docs.bfl.ai/quick_start/pricing) |
| **Ideogram 3.0** | Tipografía, gráficos de marca, renderizado de texto preciso | El mejor | [Ideogram API](https://developer.ideogram.ai/) | Ver [precios](https://about.ideogram.ai/api-pricing) |
| **ChatGPT Images 2.0 / GPT Image** (OpenAI) | Uso general, integración con ChatGPT, edición nativa | Bueno | [OpenAI API](https://platform.openai.com/docs/guides/image-generation) | Ver [precios](https://platform.openai.com/docs/pricing) |
| **Midjourney v7** | Artístico, alta estética, visuales con dirección de arte | Mejorado | Sin API oficial; Discord + Web | Basado en suscripción |
| **Recraft V3** | Ilustraciones vectoriales y consistentes con la marca, assets de diseño | Fuerte | [Recraft API](https://www.recraft.ai/docs) | Por crédito |
| **Stable Diffusion 3.5 / SDXL** | Autoalojado, personalizable, ajustable (fine-tunable) | Varía | Código abierto | Gratis (costos de GPU) |

**Nota:** DALL-E 3 está completamente descontinuado. Los modelos de imagen actuales de OpenAI son la familia GPT Image / ChatGPT Images (`gpt-image-1` y posteriores).

### Cuál Usar Según el Caso

```
¿Necesitas texto/titulares en la imagen?
├── Sí → Ideogram 3.0 (el mejor), Gemini (bueno), GPT Image / ChatGPT Images (decente)
└── No ↓

¿Necesitas consistencia de producto/marca en muchas imágenes?
├── Sí → Flux (referencia multi-imagen), Gemini Nano Banana Pro, Recraft V3
└── No ↓

¿Necesitas editar una imagen existente (in situ)?
├── Sí → Gemini (edición nativa), Flux Kontext, ChatGPT Images
└── No ↓

¿Necesitas assets de marca vectoriales/ilustrativos?
├── Sí → Recraft V3 (el mejor para vector + consistencia de marca), Midjourney (artístico)
└── No ↓

¿Necesitas la máxima calidad visual / dirección de arte?
├── Sí → Flux Pro 1.1, Midjourney v7
└── No ↓

¿Necesitas volumen a bajo costo?
└── Flux Schnell, Gemini Flash, Stable Diffusion (autoalojado)
```

### Fundamentos del Prompting

Un prompt de imagen sólido sigue: **Sujeto + Escenario + Estilo + Iluminación + Composición + Técnico**

```
Una laptop sobre un escritorio blanco minimalista mostrando un dashboard de UI,
iluminación direccional suave desde la izquierda, poca profundidad de campo,
estilo de fotografía comercial limpia, relación de aspecto 16:9, 4K
```

**Errores comunes:**
- Ser demasiado vago ("una imagen de negocios") — agrega detalles específicos
- Olvidar la relación de aspecto — siempre especifica las dimensiones
- Pedir texto complejo — usa overlays para cualquier cosa más allá de titulares cortos
- Sin dirección de estilo — "fotorrealista," "ilustración plana," "render 3D"

Para guías detalladas de prompting por modelo, ver [references/ai-image-prompting.md](references/ai-image-prompting.md).

---

## Herramientas de Diseño

Para trabajo con plantilla y consistente con la marca donde la generación con IA es excesiva o demasiado impredecible.

### Canva

Lo mejor para no diseñadores que necesitan un resultado pulido rápido.

- **Fortalezas:** Biblioteca de plantillas masiva, brand kit, Magic Resize (un diseño → todos los tamaños), colaboración en equipo
- **Mejor para:** Gráficos para redes sociales, presentaciones, encabezados de email, banners simples
- **Limitaciones:** Menos control que Figma, las plantillas pueden verse genéricas
- **Compatibilidad con agentes:** Tiene API pero limitada — mejor como herramienta con humano en el loop

### Figma

Lo mejor para equipos con sistemas de diseño o necesidades pixel-perfect.

- **Fortalezas:** Componentes de sistema de diseño, auto layout, entrega a desarrollo, plugins
- **Mejor para:** Imágenes OG vía plantillas, assets de sistema de diseño, layouts complejos
- **Limitaciones:** Curva de aprendizaje más pronunciada, requiere habilidad de diseño
- **Compatibilidad con agentes:** Tiene API y servidor MCP para leer diseños

### Cuándo Usar Herramientas de Diseño vs. Generación con IA

| Escenario | Herramienta de Diseño | Generación con IA |
|----------|:-:|:-:|
| Deben seguirse guías de marca exactas | Sí | Tal vez (con imágenes de referencia sólidas) |
| Necesitas 20 variantes de tamaño de un diseño | Sí (Canva Magic Resize) | No |
| Imagen hero única para un post de blog | No | Sí |
| Plantilla recurrente para redes sociales | Sí | No |
| Mockup de producto con UI real | No (usar screenshots) | No (UI alucinada) |
| Visual abstracto/creativo | No | Sí |

---

## Flujos de Trabajo de Imágenes de Marketing

### Imágenes Hero de Blog y Artículos

La imagen en la parte superior de cada post. Marca el tono, mejora la posibilidad de compartir, requerida para vistas previas OG/redes sociales.

1. **Define el concepto** — ¿qué metáfora visual representa el tema?
2. **Genera con IA** — usa Flux o Gemini para fotorrealista, Ideogram si se necesita texto
3. **Especifica 1200x630** (funciona tanto para hero como para imagen OG) o **1920x1080** para ancho completo
4. **Optimiza** — comprime a <200KB, sirve como WebP con fallback JPEG

**Patrón de prompt:**
```
[Metáfora visual para el tema], estilo moderno y limpio,
iluminación natural brillante, poca profundidad de campo,
estética profesional de encabezado de blog, 1200x630
```

### Gráficos para Redes Sociales

Imágenes específicas por plataforma para posts orgánicos.

| Plataforma | Tamaño Principal | Relación de Aspecto | Notas |
|----------|-------------|:---:|-------|
| Twitter/X | 1200x675 | 16:9 | Tarjeta de imagen grande |
| LinkedIn | 1200x627 | 1.91:1 | Imagen de feed |
| Instagram Feed | 1080x1080 | 1:1 | Cuadrada; 1080x1350 (4:5) también funciona bien |
| Instagram Stories | 1080x1920 | 9:16 | Vertical de pantalla completa |
| Facebook | 1200x630 | 1.91:1 | Imagen para compartir enlaces |

**Flujo de trabajo:**
1. Crea el concepto hero en la resolución más alta necesaria
2. Usa Canva Magic Resize o recorte manual para las variantes por plataforma
3. Agrega overlays de texto de forma programática (Ideogram o post-procesamiento) si es necesario
4. Exporta en las dimensiones específicas de cada plataforma

### Mockups y Screenshots de Producto

Muestra la UI de tu producto en contexto. Los modelos de IA alucinan la UI — no los uses para esto.

1. **Captura screenshots reales** de tu producto a resolución 2x
2. **Enmarca en mockups de dispositivo** — usa frame de navegador, laptop o plantillas de teléfono
3. **Agrega contexto** — flechas de llamada, etiquetas de funciones, comparaciones antes/después
4. **Anota con código** — Hyperframes o HTML/CSS para overlays programáticos

**Herramientas:** Browser DevTools (screenshot), Shottr (Mac), CleanShot X, o CLI `screencapture`.

### Banners de Perfil y Listado

Banners para perfiles, listados de directorio y páginas de marketplace. A menudo la primera impresión visual.

| Plataforma | Tamaño | Notas |
|----------|------|-------|
| Portada personal de LinkedIn | 1584x396 | 4:1, zona segura al centro |
| Portada de empresa de LinkedIn | 1128x191 | 5.9:1; LinkedIn recomienda hasta 4200x700 |
| Header de Twitter/X | 1500x500 | 3:1, parcialmente tapado por el avatar |
| Galería de Product Hunt | 1270x760 | 5:3, hasta 6 imágenes |
| Perfil de G2 | 1280x720 | 16:9, se prefieren screenshots del producto |
| Vista previa social de GitHub | 1280x640 | 2:1, se muestra en tarjetas de enlace |
| Screenshots de App Store | Varía según dispositivo | Ver skill aso para specs completas |
| Gráfico de función de Google Play | 1024x500 | ~2:1, requerido para el listado en la tienda |

**Mejores prácticas:**
- **Mantén el texto al mínimo** — los banners se ven en tamaños pequeños en móvil
- **Centra el contenido crítico** — los bordes se recortan diferente según el dispositivo
- **Muestra el producto** — screenshots reales de UI superan a los gráficos abstractos en listados de directorio
- **Alinéate con tu marca** — usa colores, tipografías y ubicación del logo consistentes
- **Actualiza estacionalmente** — los banners desactualizados señalan un producto inactivo

**Flujo de trabajo:**
1. Elige la(s) plataforma(s) y anota las dimensiones exactas
2. Para directorios (Product Hunt, G2): usa screenshots reales del producto con anotación ligera
3. Para perfiles (LinkedIn, Twitter): usa colores de marca + tagline + foto de producto opcional
4. Genera con plantillas de Canva/Figma o Ideogram (si tiene mucho texto)
5. Prueba en el tamaño real de visualización — aleja el zoom para revisar la legibilidad

### Assets de Marca

Logos, íconos e ilustraciones. La generación con IA tiene límites aquí.

| Asset | Generación con IA | Herramienta de Diseño | Notas |
|-------|:-:|:-:|-------|
| Logo | Deficiente — inconsistente, no vectorial | Sí (Figma) | Siempre diseña o encarga los logos |
| Ícono de app | Punto de partida decente | Sí (Figma) | Genera conceptos, refina manualmente |
| Ilustraciones | Bueno para explorar estilos | Depende | IA para conceptos, finaliza en herramienta de diseño |
| Favicons | No | Sí | Deriva del logo |
| Íconos sociales | No | Sí | Usa los assets provistos por la plataforma |

---

## Optimización de Imágenes

Cada imagen en tu sitio afecta la velocidad de página, lo que afecta el SEO y las conversiones.

### Guía de Formatos

| Formato | Mejor Para | Compresión | Soporte de Navegador |
|--------|----------|-------------|:---:|
| **WebP** | Fotos, gráficos — opción por defecto | Con y sin pérdida | ~96% |
| **AVIF** | Mayor compresión, el más nuevo | Mejor que WebP | ~94% |
| **JPEG** | Fallback para navegadores antiguos | Solo con pérdida | Universal |
| **PNG** | Transparencia, screenshots | Sin pérdida | Universal |
| **SVG** | Logos, íconos, ilustraciones | Vectorial (escala) | Universal |

### Checklist de Optimización

- [ ] **Sirve WebP** con fallback JPEG/PNG (elemento `<picture>` o auto-formato de CDN)
- [ ] **Redimensiona al tamaño de visualización** — no sirvas imágenes de 4000px en contenedores de 800px
- [ ] **Comprime** — apunta a calidad 75-85% para fotos, casi sin pérdida para screenshots
- [ ] **Lazy load** de imágenes bajo el pliegue (`loading="lazy"`)
- [ ] **Define dimensiones explícitas** — los atributos `width` y `height` previenen el layout shift (CLS)
- [ ] **Usa un CDN** con auto-optimización (Cloudflare, Vercel, Imgix, Cloudinary)
- [ ] **Agrega texto alternativo** — descriptivo, relevante a keywords, sin relleno

### Comandos Rápidos de Optimización

```bash
# Convertir a WebP (usando cwebp)
cwebp -q 80 input.png -o output.webp

# Conversión por lote con ImageMagick
mogrify -format webp -quality 80 *.png

# Optimizar JPEG (usando jpegoptim)
jpegoptim --max=80 --strip-all *.jpg

# Revisar tamaños de imagen en una página
curl -s https://tusitio.com | grep -oP 'src="[^"]+\.(jpg|png|webp)"' | head -20
```

---

## Imágenes OG y de Vista Previa Social

La imagen que aparece cuando tu URL se comparte en redes sociales, Slack, Discord, etc.

### Meta Tags Requeridos

```html
<meta property="og:image" content="https://tusitio.com/og/nombre-pagina.jpg" />
<meta property="og:image:width" content="1200" />
<meta property="og:image:height" content="630" />
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:image" content="https://tusitio.com/og/nombre-pagina.jpg" />
```

### Imágenes OG Dinámicas

Genera imágenes OG de forma programática para páginas con contenido dinámico (posts de blog, perfiles de usuario):

- **Vercel OG** (`@vercel/og`) — genera imágenes en el edge usando JSX
- **Satori** — convierte HTML/CSS a SVG (impulsa a Vercel OG)
- **Cloudinary** — overlay de texto basado en URL sobre imágenes de plantilla

**Lo mejor para SEO programático:** Genera imágenes OG únicas por página usando plantillas + datos dinámicos.

---

## Errores Comunes

1. **Usar IA para screenshots de UI de producto** — los modelos alucinan interfaces; captura screenshots reales
2. **Saltarte la optimización de imágenes** — las imágenes sin optimizar son el asesino #1 de la velocidad de página
3. **Sin imagen OG** — los enlaces compartidos se ven rotos sin una imagen de vista previa
4. **Relación de aspecto incorrecta** — siempre revisa las specs de la plataforma antes de generar
5. **Imágenes con mucho texto sin Ideogram** — la mayoría de los modelos de IA arruinan el texto; usa Ideogram o agrega el texto en post-procesamiento
6. **Generar sin dirección de estilo** — "fotorrealista," "ilustración plana," "render 3D" cambian drásticamente el resultado
7. **Visuales de marca inconsistentes** — usa referencia múltiple de Flux o plantillas de diseño para consistencia
8. **Imágenes enormes en landing pages** — comprime, redimensiona, lazy load

---

## Preguntas Específicas de la Tarea

1. ¿Qué tipo de imagen necesitas? (Imagen hero de blog, gráfico social, mockup, banner, asset de marca)
2. ¿Qué plataforma o ubicación? (Esto determina las dimensiones)
3. ¿Tienes assets de marca que debas respetar? (Colores, tipografías, logo, guía de estilo)
4. ¿Es una pieza única o una plantilla repetible?
5. ¿Tienes API keys para alguna herramienta de generación de imágenes?
6. ¿Esto necesita estar optimizado para rendimiento web?

---

## Habilidades Relacionadas

- **ad-creative**: Para creatividad de imagen en anuncios pagados, specs de anuncios por plataforma, y producción de anuncios a escala
- **video**: Para producción de video con IA y video programático
- **social**: Para qué publicar y estrategia de contenido
- **page-cro**: Para ubicación de imágenes y optimización de conversión en landing pages
- **seo-audit**: Para SEO de imágenes (texto alternativo, nombres de archivo, lazy loading)
- **aso**: Para specs y optimización de screenshots de app store
- **directory-submissions**: Para imágenes de galería de Product Hunt y visuales de listados de directorio
