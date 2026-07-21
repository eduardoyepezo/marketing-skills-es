# Guía de Prompting para Imágenes con IA

Cómo escribir prompts efectivos para modelos de generación de imágenes con IA (Gemini/Nano Banana, Flux, Ideogram, DALL-E, Midjourney).

---

## Estructura del Prompt

Un prompt de imagen sólido sigue esta fórmula:

```
[Sujeto] + [Escenario/contexto] + [Estilo visual] + [Iluminación] + [Composición] + [Specs técnicas]
```

### Prompts de Ejemplo por Caso de Uso

**Imagen hero de blog — producto SaaS:**
```
Un espacio de trabajo limpio con una laptop mostrando un dashboard de analíticas colorido,
escritorio minimalista con una taza de café y una libreta,
iluminación natural brillante de ventana desde la derecha,
poca profundidad de campo, estilo de fotografía comercial,
1200x630, alta resolución
```

**Gráfico para redes sociales — anuncio:**
```
Gradiente abstracto fluido en púrpura profundo y azul eléctrico,
formas geométricas formando un patrón de red,
iluminación dramática de borde (rim lighting),
estética tech moderna, limpia y minimal,
1080x1080, colores vibrantes
```

**Foto lifestyle de producto:**
```
Una persona en una oficina moderna sonriendo mientras mira una tablet,
mostrando una interfaz de gestión de proyectos en pantalla,
fotografía candid cálida, iluminación natural,
plano medio, poca profundidad de campo, estilo editorial
```

**Banner de perfil — profesional:**
```
Fondo abstracto panorámico ancho en azul marino y verde azulado,
patrón de cuadrícula geométrica sutil con gradiente suave,
estética corporativa limpia, iluminación tenue,
1584x396, sin texto, espacio para overlay de logo en el tercio izquierdo
```

**Listado de directorio — Product Hunt:**
```
Screenshot de producto sobre fondo con gradiente limpio,
sombra suave debajo, ligera inclinación de perspectiva 3D,
estilo moderno de presentación de producto SaaS,
1270x760, brillante y profesional
```

---

## Palabras Clave de Estilo

### Fotorrealista
- "fotografía comercial"
- "tomada con Canon EOS R5"
- "estilo editorial"
- "iluminación natural"
- "poca profundidad de campo"

### Limpio/Corporativo
- "estética moderna y limpia"
- "diseño minimal"
- "estilo corporativo profesional"
- "brillante y aireado"
- "fondo blanco"

### Ilustrativo
- "ilustración vectorial plana"
- "render 3D isométrico"
- "estilo de boceto a mano"
- "ilustración en acuarela"
- "line art"

### Abstracto/Marca
- "gradiente fluido"
- "patrón geométrico"
- "visualización de datos abstracta"
- "efectos de partículas"
- "holográfico iridiscente"

### Tech/SaaS
- "estética de UI en modo oscuro"
- "iluminación de acento neón"
- "glassmorphism"
- "minimal futurista"
- "orientado a developers"

---

## Palabras Clave de Iluminación

| Término | Efecto | Mejor Para |
|------|--------|----------|
| **Luz natural** | Sensación cálida y orgánica | Lifestyle, editorial |
| **Iluminación de estudio** | Uniforme, controlada | Fotos de producto |
| **Rim lighting** | Resaltados de borde, dramático | Imágenes hero, abstracto |
| **Direccional suave** | Sombras suaves, con dimensión | Encabezados de blog |
| **Volumétrica** | Rayos de luz, atmosférica | Dramático, cinematográfico |
| **Plana/uniforme** | Sin sombras, limpia | Íconos, diagramas |
| **Hora dorada** | Tonos naranjas cálidos | Lifestyle, exteriores |
| **High key** | Brillante, sombras mínimas | Limpio, corporativo |

---

## Palabras Clave de Composición

| Término | Efecto | Mejor Para |
|------|--------|----------|
| **Regla de tercios** | Sujeto descentrado | Editorial, lifestyle |
| **Centrada** | Sujeto en el medio | Fotos de producto, íconos |
| **Amplia/panorámica** | Vista expansiva | Banners, encabezados |
| **Primer plano/macro** | Enfoque en el detalle | Textura, detalle de producto |
| **Vista de pájaro/cenital** | Vista desde arriba | Setups de escritorio, flat lays |
| **Espacio negativo** | Espacio para overlay de texto | Encabezados de blog, banners |
| **Simétrica** | Balanceada, formal | Corporativo, lujo |

---

## Tips Específicos por Modelo

### Gemini Image (Google)

- El mejor de uso general para imágenes de marketing — buena calidad, costo razonable
- Soporta **edición de imágenes** — sube una imagen existente y describe los cambios
- Renderizado de texto decente — puede manejar titulares cortos
- Especifica "alta resolución" para el mejor resultado
- Funciona bien con prompts detallados y descriptivos
- Misma API que la generación de texto — fácil de integrar

### Flux (Black Forest Labs)

- La **referencia multi-imagen** es la función estrella — sube screenshots de producto, assets de marca o referencias de estilo
- Lo mejor para **consistencia de marca** en un conjunto de imágenes
- Usa Flux Pro para assets finales, Flux Dev para iteración rápida
- Flux Klein para generación por lote de alto volumen (el más barato)
- Transferencia de estilo vía imágenes de referencia > palabras clave de estilo en el prompt
- Los prompts pueden ser más cortos que en otros modelos — las referencias hacen el trabajo pesado

### Ideogram

- El **mejor renderizado de texto** de cualquier modelo (precisión líder en la industria)
- Úsalo cuando necesites titulares, taglines o nombres de marca en la imagen
- Sistema de referencia de estilo (hasta 3 imágenes) para consistencia de marca
- Soporta autopotenciación "Magic Prompt"
- Mantén las solicitudes de texto simples — 3-5 palabras máximo para confiabilidad
- Lo mejor para gráficos de redes sociales y banners que necesitan texto incorporado

### GPT Image (OpenAI)

- Modelos actuales: `gpt-image-1` y variantes (DALL-E 3 está descontinuado)
- Integrado con ChatGPT — generación de imágenes conversacional
- Bueno siguiendo prompts detallados
- Renderizado de texto decente (por detrás de Ideogram, comparable a Gemini)
- Reescritura automática de prompts — puede desviarse de la solicitud exacta
- Lo mejor para piezas únicas rápidas a través de la interfaz de ChatGPT
- La API da más control que la interfaz de ChatGPT

### Midjourney

- La mayor calidad estética para imágenes artísticas/editoriales
- Sin API oficial — basado en Discord o interfaz web
- **No es agent-friendly** — úsalo solo para exploración creativa manual
- Flags de estilo: `--style raw` para menos estilizado, `--ar 16:9` para relación de aspecto
- Lo mejor para imágenes hero donde la pura calidad visual importa más
- V6+ tiene renderizado de texto mejorado pero sigue siendo poco confiable

---

## Errores Comunes de Prompting

| Error | Por Qué Falla | Solución |
|---------|-------------|-----|
| "Una imagen profesional" | Sin detalle visual | Describe sujeto, escenario, estilo, iluminación |
| Párrafo largo de texto en la imagen | Los modelos no pueden renderizar párrafos | 3-5 palabras máximo; agrega el texto en post |
| "Que se vea bien" | No es accionable | Especifica el estilo: "fotografía comercial, brillante" |
| Prompts de 200+ palabras | Los modelos pierden el foco | 40-80 palabras, específico en vez de exhaustivo |
| Sin relación de aspecto | Tamaño de salida aleatorio | Siempre especifica dimensiones o relación |
| "Logo en la esquina inferior derecha" | Ubicación poco confiable | Agrega los logos en post-procesamiento |
| "Que se vuelva viral" | No es una instrucción visual | Describe la estética que quieres |
| Pedir screenshots de UI | La IA alucina interfaces | Captura screenshots reales en su lugar |

---

## Flujo de Trabajo de Generación por Lote

Cuando necesitas múltiples imágenes con estilo consistente (por ejemplo, una serie de blog o campaña social):

1. **Genera 3-4 imágenes de prueba** con distintos prompts de estilo
2. **Elige el estilo ganador** según el ajuste de marca
3. **Guarda el prompt exacto** como tu plantilla
4. **Usa la referencia múltiple de Flux** — sube la imagen ganadora como referencia de estilo
5. **Genera por lote** variaciones con el mismo estilo, distintos sujetos
6. **Post-procesa** — agrega overlays de texto, logos, recorta a los tamaños de plataforma

---

## Referencia Rápida de Relaciones de Aspecto

| Caso de Uso | Relación | Píxeles | Notas |
|----------|-------|--------|-------|
| Imagen hero de blog / imagen OG | 1.91:1 | 1200x630 | Estándar web universal |
| Hero de ancho completo | 16:9 | 1920x1080 | Encabezados de sitio web |
| Instagram Feed | 1:1 | 1080x1080 | Cuadrada |
| Instagram Feed (alta) | 4:5 | 1080x1350 | Más espacio en pantalla |
| Stories / Reels | 9:16 | 1080x1920 | Vertical de pantalla completa |
| Portada de LinkedIn | 4:1 | 1584x396 | Perfil personal |
| Header de Twitter/X | 3:1 | 1500x500 | Banner de perfil |
| Galería de Product Hunt | 5:3 | 1270x760 | Página de lanzamiento |
| Vista previa social de GitHub | 2:1 | 1280x640 | Tarjeta de enlace de repo |

---

## Optimización de Costos

- **Itera primero a baja calidad** — usa Flux Dev o Gemini Flash para borradores, sube de nivel para las versiones finales
- **Usa referencias en vez de prompts largos** — la referencia múltiple de Flux produce resultados más consistentes con menos reintentos
- **Agrupa solicitudes similares** — genera todos los encabezados de blog en una sola sesión con el mismo estilo
- **Cachea y reutiliza** — fondos abstractos, patrones y texturas se pueden reutilizar en múltiples imágenes
- **Post-procesa en vez de regenerar** — recorta, agrega overlays de texto y ajusta color en código en lugar de generar imágenes nuevas
