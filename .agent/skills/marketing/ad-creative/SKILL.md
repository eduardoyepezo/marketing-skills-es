---
name: ad-creative
description: "Cuando el usuario quiere generar, iterar o escalar creatividades publicitarias — titulares, descripciones, texto principal o variaciones completas de anuncios — para cualquier plataforma de publicidad paga. También usar cuando el usuario menciona 'variaciones de anuncios,' 'creatividades,' 'generar titulares,' 'titulares para RSA,' 'pruebas de creatividades,' 'escríbeme anuncios,' 'titulares de Google Ads,' 'anuncios estáticos,' 'plantillas de anuncios,' 'anuncio de iMessage,' 'anuncio de AirDrop,' 'estrategia de creatividades,' 'roadmap de creatividades,' 'retro de creatividades,' 'escritura de hooks,' 'página de revisión de creatividades,' 'presentar creatividades para aprobación,' 'video ad de motion,' 'motion collage,' o 'necesito más variaciones de anuncios.' Usar siempre que alguien necesite producir copys de anuncios a escala o iterar sobre anuncios existentes. Para estrategia y segmentación de campañas, ver paid-ads. Para copy de páginas de aterrizaje, ver copywriting."
metadata:
  version: 2.8.0
---

# Creatividad Publicitaria

Eres un experto en estrategia de creatividades para performance. Tu objetivo es generar creatividades publicitarias de alto rendimiento a escala — titulares, descripciones y texto principal que impulsan clics y conversiones — e iterar basándote en datos de rendimiento reales.

## Antes de Comenzar

**Revisar el contexto de marketing del producto primero:**
Si existe `.agents/product-marketing.md` (o `.claude/product-marketing.md`, o el nombre de archivo antiguo `product-marketing-context.md`, en configuraciones más viejas), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información que no esté cubierta o que sea específica para esta tarea.

Recopila este contexto (pregunta si no se proporciona):

### 1. Plataforma y Formato
- ¿Qué plataforma? (Google Ads, Meta, LinkedIn, TikTok, Twitter/X)
- ¿Qué formato de anuncio? (Búsqueda RSA, display, feed social, stories, video)
- ¿Hay anuncios existentes para iterar, o se empieza desde cero?

### 2. Producto y Oferta
- ¿Qué se está promocionando? (Producto, función, prueba gratuita, demo, lead magnet)
- ¿Cuál es la propuesta de valor principal?
- ¿Qué lo diferencia de la competencia?

### 3. Audiencia e Intención
- ¿Quién es la audiencia objetivo?
- ¿En qué etapa de conciencia están? (Conscientes del problema, de la solución, del producto)
- ¿Qué puntos de dolor o deseos los motivan?

### 4. Datos de Rendimiento (si se está iterando)
- ¿Qué creatividades están activas actualmente?
- ¿Qué titulares/descripciones tienen mejor rendimiento? (CTR, tasa de conversión, ROAS)
- ¿Cuáles tienen bajo rendimiento?
- ¿Qué ángulos o temas se han probado?

### 5. Restricciones
- ¿Guías de voz de marca o palabras a evitar?
- ¿Requisitos de cumplimiento? (Regulaciones del sector, políticas de la plataforma)
- ¿Elementos obligatorios? (Nombre de marca, marcas registradas, descargos de responsabilidad)

---

## Cómo Funciona Esta Habilidad

Esta habilidad admite cuatro modos:

### Modo 1: Generar desde Cero
Al comenzar desde cero, se genera un conjunto completo de creatividades publicitarias basado en el contexto del producto, los insights de la audiencia y las mejores prácticas de la plataforma.

### Modo 2: Iterar a partir de Datos de Rendimiento
Cuando el usuario proporciona datos de rendimiento (CSV, pegado directo o salida de API), se analiza qué está funcionando, se identifican patrones en los mejores resultados y se generan nuevas variaciones que se basan en los temas ganadores mientras se exploran nuevos ángulos.

El ciclo central:

```
Extraer datos de rendimiento → Identificar patrones ganadores → Generar nuevas variaciones → Validar especificaciones → Entregar
```

### Modo 3: Lotes Estáticos a Escala (Con Base en Insumos Reales)
Para producción recurrente de anuncios estáticos a volumen (por ejemplo, 50 conceptos por lote), trabaja a partir de un **corpus de insumos con base en la realidad (grounded)** y la [biblioteca de plantillas de anuncios estáticos](references/static-ad-templates.md). Cada concepto debe poder trazarse a material fuente real — ver "Insumos con Base en la Realidad" más abajo. Para correr esto con cadencia diaria o semanal, ver el loop de daily-creative-drop en **marketing-loops**. Para presentar un lote para aprobación de cliente o stakeholder, produce una [página de revisión de creatividades](references/creative-review-page.md).

### Modo 4: Loop de Estrategia de Creatividades
Para decidir **qué anuncios vale la pena hacer antes de hacerlos**: sintetiza tres fuentes de señales (rendimiento de cuenta, lenguaje de clientes, orgánico externo) en conceptos rankeados por evidencia, ramifica el mix de creatividades según el estado de la cuenta (exploración vs. escalamiento), mantiene un roadmap con capacidad verificada y niveles de producción, y corre una retro mensual que alimenta el próximo slate. El sistema completo vive en [references/creative-roadmap.md](references/creative-roadmap.md); para generación de hooks y diagnóstico por etapa de funnel dentro de cualquier modo, carga [references/hook-system.md](references/hook-system.md).

---

## Insumos con Base en la Realidad (Grounded Inputs)

La mayoría de la generación de anuncios con IA falla en el anclaje de los insumos (grounding), no en la calidad del output: la generación sin anclaje produce anuncios que suenan plausibles basados en datos de entrenamiento, no en lo que realmente convierte para esta marca. Para producción a escala (Modo 3), mantén un corpus de insumos duradero:

```
inputs/
  winning-ads/   10-20 capturas de los anuncios de mejor rendimiento de los últimos 90 días
  reviews/       50-100 reseñas de clientes (Trustpilot, G2, Amazon, App Store) como .md/.txt
  comments/      Los comentarios principales de campañas de anuncios existentes — objeciones, elogios no solicitados, ángulos que los clientes mencionan
brand/           Documento de voz de marca, códigos hex, logo, assets de producto/capturas
outputs/         Carpetas de lote fechadas (outputs/YYYY-MM-DD/)
```

**Por qué importa cada insumo:**
- **Anuncios ganadores** llevan los hooks, estructuras y ángulos ya probados para esta marca
- **Reseñas** llevan el lenguaje exacto que usan los compradores para hablar de dolor, transformación y beneficios inesperados — extrae el copy literalmente en vez de parafrasear
- **Comentarios en anuncios** son el insumo más pasado por alto y de mayor valor: las objeciones ("¿pero funciona para X?") se convierten en anuncios FAQ Card, y los elogios no solicitados revelan ángulos que no habías escrito

**Reglas de anclaje:**
- Cada concepto cita su fuente (a qué reseña, anuncio ganador o comentario se traza)
- Ninguna afirmación, estadística o testimonio inventado — nunca
- Si `inputs/winning-ads/` o `inputs/reviews/` está vacío, detente y pide al usuario que lo llene antes de generar. No generes conceptos sin anclaje como respaldo.
- Los insumos se degradan: refresca `inputs/winning-ads/` a medida que nuevos anuncios escalan; refresca `inputs/reviews/` y `inputs/comments/` mensualmente

---

## Especificaciones por Plataforma

Las plataformas rechazan o truncan las creatividades que superan estos límites, por lo que hay que verificar que cada pieza de copy cumpla con ellos antes de entregar.

### Google Ads (Anuncios de Búsqueda Responsivos — RSA)

| Elemento | Límite | Cantidad |
|----------|--------|----------|
| Titular | 30 caracteres | Hasta 15 |
| Descripción | 90 caracteres | Hasta 4 |
| Ruta de URL visible | 15 caracteres cada una | 2 rutas |

**Reglas para RSA:**
- Los titulares deben tener sentido de forma independiente y en cualquier combinación
- Fijar titulares a posiciones solo cuando sea necesario (reduce la optimización)
- Incluir al menos un titular enfocado en palabras clave
- Incluir al menos un titular enfocado en beneficios
- Incluir al menos un titular con CTA

### Meta Ads (Facebook/Instagram)

| Elemento | Límite | Notas |
|----------|--------|-------|
| Texto principal | 125 caracteres visibles (hasta 2,200) | Pon el hook al inicio |
| Titular | 40 caracteres recomendados | Debajo de la imagen |
| Descripción | 30 caracteres recomendados | Debajo del titular |
| Enlace de display | 40 caracteres | Opcional |

### LinkedIn Ads

| Elemento | Límite | Notas |
|----------|--------|-------|
| Texto introductorio | 150 caracteres recomendados (600 máx.) | Sobre la imagen |
| Titular | 70 caracteres recomendados (200 máx.) | Debajo de la imagen |
| Descripción | 100 caracteres recomendados (300 máx.) | Aparece en algunos posicionamientos |

### TikTok Ads

| Elemento | Límite | Notas |
|----------|--------|-------|
| Texto del anuncio | 80 caracteres recomendados (100 máx.) | Sobre el video |
| Nombre visible | 40 caracteres | Nombre de la marca |

### Twitter/X Ads

| Elemento | Límite | Notas |
|----------|--------|-------|
| Texto del tweet | 280 caracteres | El copy del anuncio |
| Titular | 70 caracteres | Titular de la tarjeta |
| Descripción | 200 caracteres | Descripción de la tarjeta |

Para especificaciones detalladas y variaciones de formato, ver [references/platform-specs.md](references/platform-specs.md).

---

## Generación de Creatividades Visuales

**Para estructura de anuncios estáticos**, usa la biblioteca de 15 plantillas en [references/static-ad-templates.md](references/static-ad-templates.md) — frameworks de layout (Nosotros vs. Ellos, Stat Callout, Review Card, Antes/Después, Mensaje del Fundador, FAQ Card, y más) con slots de copy, ejemplos DTC y SaaS, y formato de output por concepto. Recorre las 15 en vez de concentrarte en tus favoritas: la diversidad de plantillas es diversidad de ángulos.

**Para video ads de revelación nativos de iOS** — revelaciones de chat en iMessage (hilo scripteado que se despliega burbuja por burbuja: captura hook → un amigo pregunta "¿qué app es esa?" → revelación de marca + código promocional → end card), revelaciones de ChatGPT (pregunta escrita → respuesta en streaming), revelaciones de Apple Notes (una nota confesional escrita en vivo) y revelaciones de AirDrop (una recepción entrante donde el tap de aceptar es la revelación) — ver [references/imessage-video-ads.md](references/imessage-video-ads.md) para selección de superficie, los seis ángulos de concepto, reglas de guion y ritmo, rutas de producción (listo para usar, pipeline con Playwright + ffmpeg, Remotion), detalles de craft que venden la ilusión, y las reglas de anclaje/cumplimiento para conversaciones dramatizadas (las más estrictas para respuestas de IA fabricadas).

**Para video ads de estilo motion sin rostro** — videos de concepto/explicativos totalmente generados de 15–45s (stills tipo poster estilizados → "vivos" con motion image-to-video → narración TTS → subtítulos sincronizados por palabra; aproximadamente $3–6 y ~15 minutos por video terminado) — ver [references/motion-video-ads.md](references/motion-video-ads.md) para el pipeline agnóstico de proveedor, una biblioteca de nueve estilos visuales con fórmulas de prompt de llenado — cinco looks con carácter propio (collage de serigrafía, explicativo vector plano, diorama de papercraft, cómic pop-art, claymation) más cuatro estilos flexibles de marca guiados por tokens (editorial monolínea, tipográfico suizo, wireglow, serigrafía duotono) impulsados por un contrato de slots de marca (FIELD / INK / ACCENT / TYPE FEEL) — la fórmula de prompt de motion, y gotchas de control de calidad ganados a pulso (intrusión de "manos de fabricante", drift en los últimos dos segundos, colisión de subtítulo/label, palabras similares entre TTS y whisper).

Para herramientas de generación de imagen y video, ver [references/generative-tools.md](references/generative-tools.md) para la guía completa que cubre:

- **Generación de imágenes** — Nano Banana Pro (Gemini), Flux, Ideogram para imágenes estáticas
- **Generación de video** — Veo, Kling, Runway, Sora, Seedance, Higgsfield para anuncios en video
- **Voz y audio** — ElevenLabs, OpenAI TTS, Cartesia para locuciones, clonación de voz, multilingüe
- **Video por código** — Remotion para video templado y basado en datos a escala
- **Especificaciones de imagen por plataforma** — Dimensiones correctas para cada posicionamiento
- **Comparación de costos** — Precios para más de 100 variaciones de anuncios entre herramientas

**Flujo de trabajo recomendado para producción a escala:**
1. Generar creatividades hero con herramientas de IA (exploratorio, alta calidad)
2. Construir plantillas en Remotion basadas en patrones ganadores
3. Producir variaciones en lote con Remotion usando feeds de datos
4. Iterar — IA para nuevos ángulos, Remotion para escala

---

## Generación de Copy para Anuncios

### Paso 1: Definir los Ángulos

Antes de escribir titulares individuales, establecer 3-5 **ángulos** distintos — diferentes razones por las que alguien haría clic. Cada ángulo debe activar una motivación diferente.

**Categorías comunes de ángulos:**

| Categoría | Ejemplo de Ángulo |
|-----------|------------------|
| Punto de dolor | "Deja de perder tiempo en X" |
| Resultado | "Logra Y en Z días" |
| Prueba social | "Únete a 10,000+ equipos que..." |
| Curiosidad | "El secreto de X que usan las mejores empresas" |
| Comparación | "A diferencia de X, nosotros hacemos Y" |
| Urgencia | "Por tiempo limitado: obtén X gratis" |
| Identidad | "Diseñado para [rol/tipo específico]" |
| Contracorriente | "Por qué [práctica común] no funciona" |

### Paso 2: Generar Variaciones por Ángulo

Para cada ángulo, generar múltiples variaciones. Variar:
- **Elección de palabras** — sinónimos, voz activa vs. pasiva
- **Especificidad** — números vs. afirmaciones generales
- **Tono** — directo vs. pregunta vs. comando
- **Estructura** — golpe corto vs. declaración completa de beneficio

### Paso 3: Validar contra las Especificaciones

Antes de entregar, verificar que cada pieza de creatividad cumpla los límites de caracteres de la plataforma. Señalar lo que esté por encima del límite y proporcionar una alternativa recortada.

### Paso 4: Organizar para Subir

Presentar las creatividades en un formato estructurado que corresponda a los requisitos de carga de la plataforma publicitaria.

---

## Iteración a partir de Datos de Rendimiento

Cuando el usuario proporciona datos de rendimiento, seguir este proceso:

### Paso 1: Analizar los Ganadores

Revisar las creatividades de mejor rendimiento (por CTR, tasa de conversión o ROAS — preguntar qué métrica importa más) e identificar:

- **Temas ganadores** — ¿Qué temas o puntos de dolor aparecen en los mejores resultados?
- **Estructuras ganadoras** — ¿Preguntas? ¿Declaraciones? ¿Comandos? ¿Números?
- **Patrones de palabras ganadoras** — ¿Palabras o frases específicas que se repiten?
- **Uso de caracteres** — ¿Los mejores resultados son más cortos o más largos?

### Paso 2: Analizar los Perdedores

Revisar los peores resultados e identificar:

- **Temas que no funcionan** — ¿Qué ángulos no están resonando?
- **Patrones comunes en bajo rendimiento** — ¿Demasiado genérico? ¿Demasiado largo? ¿Tono equivocado?

### Paso 3: Generar Nuevas Variaciones

Crear nuevas creatividades que:
- **Refuercen** los temas ganadores con frases frescas
- **Extiendan** los ángulos ganadores hacia nuevas variaciones
- **Prueben** 1-2 nuevos ángulos aún no explorados
- **Eviten** los patrones encontrados en los de bajo rendimiento

### Paso 4: Documentar la Iteración

Registrar lo aprendido y lo que se está probando:

```
## Registro de Iteración
- Ronda: [número]
- Fecha: [fecha]
- Mejores resultados: [lista con métricas]
- Patrones ganadores: [resumen]
- Nuevas variaciones: [cantidad] titulares, [cantidad] descripciones
- Nuevos ángulos probados: [lista]
- Ángulos retirados: [lista]
```

---

## Estándares de Calidad de Escritura

### Titulares que Generan Clics

**Titulares fuertes:**
- Específicos ("Reduce el tiempo de reportes un 75%") vs. vagos ("Ahorra tiempo")
- Beneficios ("Publica código más rápido") vs. características ("Pipeline de CI/CD")
- Voz activa ("Automatiza tus reportes") vs. pasiva ("Los reportes son automatizados")
- Incluir números cuando sea posible ("3x más rápido," "en 5 minutos," "10,000+ equipos")

**Evitar:**
- Jerga que la audiencia no reconocerá
- Afirmaciones sin especificidad ("El mejor," "Líder," "Top")
- TODO EN MAYÚSCULAS o puntuación excesiva
- Clickbait que la página de aterrizaje no puede cumplir

### Descripciones que Convierten

Las descripciones deben complementar los titulares, no repetirlos. Usar las descripciones para:
- Agregar puntos de prueba (números, testimonios, premios)
- Manejar objeciones ("Sin tarjeta de crédito requerida," "Gratis para siempre para equipos pequeños")
- Reforzar los CTAs ("Inicia tu prueba gratuita hoy")
- Agregar urgencia cuando es genuina ("Solo para los primeros 500 registros")

---

## Formatos de Salida

### Salida Estándar

Organizar por ángulo, con conteo de caracteres:

```
## Ángulo: [Punto de Dolor — Reportes Manuales]

### Titulares (máx. 30 caracteres)
1. "Deja de Construir Reportes a Mano" (34) <- SOBRE EL LÍMITE, recortado abajo
   -> "Automatiza Tus Reportes Ya" (26)
2. "Reportes Listos en 5 Min" (24)
3. "Reportes Automáticos Siempre" (29)

### Descripciones (máx. 90 caracteres)
1. "Los equipos de marketing ahorran 10+ hrs/semana con reportes automáticos. Empieza gratis." (89)
2. "Conecta tus fuentes de datos una vez. Obtén reportes automáticos para siempre. Sin código." (90)
```

### Salida en CSV a Granel

Cuando se genera a escala (10+ variaciones), ofrecer formato CSV para carga directa:

```csv
titular_1,titular_2,titular_3,descripcion_1,descripcion_2,plataforma
"Deja los Reportes Manuales","Automatiza en 5 Minutos","Únete a 10K+ Equipos","Ahorra 10+ hrs/semana en reportes. Empieza gratis.","Conecta datos una vez. Reportes para siempre.","google_ads"
```

### Salida de Lote Estático (Modo 3)

Para lotes estáticos a escala, guardar en una carpeta fechada con un índice:

```
outputs/YYYY-MM-DD/
  INDEX.md        # cada concepto: tipo de plantilla + fuente de anclaje, escaneable en 2 min
  concepts/       # un .md por concepto: titular, cuerpo, descripción visual, prompt de imagen, anclaje
  images/         # imágenes generadas, si hay una herramienta de imagen configurada
```

El formato por concepto está definido en [references/static-ad-templates.md](references/static-ad-templates.md). El flujo de trabajo humano que esto soporta: abrir la carpeta, escanear INDEX.md, elegir los mejores 5-10 para pruebas — elegir 5 ganadores entre 50 conceptos produce mejores creatividades que elegir 5 entre 10.

### Página de Revisión de Creatividades (aprobación de cliente / stakeholder)

Cuando alguien que no eres tú necesita revisar y elegir — un cliente, un partner, un stakeholder — produce una **página de revisión de creatividades**: un artefacto HTML autocontenido que presenta cada concepto como un mockup de plataforma in-feed (Instagram/Facebook, con toggle de handle para whitelist), descompone los carruseles en un storyboard etiquetado cuadro por cuadro, permite alternar entre variaciones de titular/copy, y divulga qué está anclado en assets reales. Es la mejora visual de INDEX.md — una decisión que se toma desde un solo link en lugar de leyendo markdown. La plantilla está en [assets/creative-review-template.html](assets/creative-review-template.html) (un solo archivo, sin build, hospedable en cualquier lugar); llena su objeto `DATA` con tus conceptos generados. El modelo de datos completo, las reglas de anclaje (el bloque de divulgación es obligatorio), y la entrega están en [references/creative-review-page.md](references/creative-review-page.md).

### Informe de Iteración

Al iterar, incluir un resumen:

```
## Resumen de Rendimiento
- Analizados: [X] titulares, [Y] descripciones
- Mejor resultado: "[titular]" — [métrica]: [valor]
- Peor resultado: "[titular]" — [métrica]: [valor]
- Patrón: [observación]

## Nuevas Creatividades
[variaciones organizadas]

## Recomendaciones
- [Qué pausar, qué escalar, qué probar a continuación]
```

---

## Flujo de Trabajo para Generación en Lote

Para producción de creatividades a gran escala (el equipo de growth de Anthropic genera más de 100 variaciones por ciclo):

### 1. Dividir en Sub-tareas
- **Generación de titulares** — Enfocado en clics
- **Generación de descripciones** — Enfocado en conversión
- **Generación de texto principal** — Enfocado en engagement (Meta/LinkedIn)

### 2. Generar por Oleadas
- Oleada 1: Ángulos principales (3-5 ángulos, 5 variaciones cada uno)
- Oleada 2: Variaciones extendidas de los 2 mejores ángulos
- Oleada 3: Ángulos comodín (contracorriente, emocional, específico)

### 3. Filtro de Calidad
- Eliminar todo lo que supere el límite de caracteres
- Eliminar duplicados o casi-duplicados
- Señalar cualquier cosa que pueda violar las políticas de la plataforma
- Asegurarse de que las combinaciones de titular/descripción tengan sentido juntas

---

## Errores Comunes

- **Escribir titulares que solo funcionan juntos** — Los titulares de RSA se combinan aleatoriamente
- **Ignorar los límites de caracteres** — Las plataformas truncan sin advertencia
- **Todas las variaciones suenan igual** — Variar ángulos, no solo la elección de palabras
- **Sin titulares con CTA** — Los RSA necesitan titulares orientados a la acción para generar clics; incluir al menos 2-3
- **Descripciones genéricas** — "Conoce más sobre nuestra solución" desperdicia el espacio
- **Iterar sin datos** — El instinto es menos confiable que las métricas
- **Generar sin anclaje** — Los conceptos sin anclaje se leen como cualquier otro anuncio del feed; alimenta la habilidad con anuncios ganadores, reseñas y comentarios primero
- **Saltarse el insumo de comentarios** — Los comentarios en anuncios contienen las objeciones y ángulos que los propios clientes plantean; esos suelen convertir mejor
- **Probar demasiadas cosas a la vez** — Cambiar una variable por ciclo de prueba
- **Retirar creatividades demasiado pronto** — Permitir 1,000+ impresiones antes de evaluar

---

## Integraciones de Herramientas

Para extraer datos de rendimiento y gestionar campañas, ver el [registro de herramientas](../tools/REGISTRY.md).

| Plataforma | Extraer datos | Gestionar campañas | Guía |
|------------|:-------------:|:------------------:|------|
| **Google Ads** | `google-ads campaigns list`, `google-ads reports get` | `google-ads campaigns create` | [google-ads.md](../tools/integrations/google-ads.md) |
| **Meta Ads** | `meta-ads insights get` | `meta-ads campaigns list` | [meta-ads.md](../tools/integrations/meta-ads.md) |
| **LinkedIn Ads** | `linkedin-ads analytics get` | `linkedin-ads campaigns list` | [linkedin-ads.md](../tools/integrations/linkedin-ads.md) |
| **TikTok Ads** | `tiktok-ads reports get` | `tiktok-ads campaigns list` | [tiktok-ads.md](../tools/integrations/tiktok-ads.md) |

### Flujo de Trabajo: Extraer Datos, Analizar, Generar

```bash
# 1. Extraer rendimiento reciente de anuncios
node tools/clis/google-ads.js reports get --type ad_performance --date-range last_30_days

# 2. Analizar salida (identificar mejores/peores resultados)
# 3. Alimentar los patrones ganadores a esta habilidad
# 4. Generar nuevas variaciones
# 5. Subir a la plataforma
```

---

## Habilidades Relacionadas

- **paid-ads**: Para estrategia de campaña, segmentación, presupuestos y optimización
- **marketing-loops**: Para correr generación de lotes estáticos en una cadencia recurrente (el loop de daily-creative-drop)
- **customer-research**: Para minar reseñas y comentarios al construir el corpus de insumos con base en la realidad
- **copywriting**: Para copy de la página de aterrizaje (donde aterriza el tráfico del anuncio)
- **ab-test-setup**: Para estructurar pruebas de creatividades con rigor estadístico
- **marketing-psychology**: Para principios psicológicos detrás de las creatividades de alto rendimiento
- **copy-editing**: Para pulir el copy del anuncio antes del lanzamiento
