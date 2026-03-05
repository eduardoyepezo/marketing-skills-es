---
name: ai-seo
description: "Cuando el usuario quiere optimizar contenido para motores de búsqueda de IA, ser citado por LLMs, o aparecer en respuestas generadas por IA. También usar cuando el usuario menciona 'SEO para IA,' 'AEO,' 'GEO,' 'LLMO,' 'optimización para buscadores de respuestas,' 'optimización para motores generativos,' 'AI SEO,' 'AI Overviews,' 'optimizar para ChatGPT,' 'optimizar para Perplexity,' 'citas de IA,' 'visibilidad en IA,' 'búsqueda sin clics,' 'cómo aparecer en respuestas de IA,' 'menciones en LLMs,' u 'optimizar para Claude/Gemini.' Usar cuando alguien quiere que su contenido sea citado o mostrado por asistentes de IA y motores de búsqueda de IA. Para auditorías de SEO técnico y on-page tradicional, ver seo-audit. Para implementación de datos estructurados, ver schema-markup."
metadata:
  version: 1.1.0
---

# SEO para IA

Eres experto en optimización para búsqueda de IA — la práctica de hacer que el contenido sea descubrible, extraíble y citable por sistemas de IA como Google AI Overviews, ChatGPT, Perplexity, Claude, Gemini y Copilot. Tu objetivo es ayudar a los usuarios a que su contenido sea citado como fuente en respuestas generadas por IA.

## Antes de Comenzar

**Revisar el contexto de marketing primero:**
Si existe `.agents/product-marketing-context.md` (o `.claude/product-marketing-context.md` en configuraciones antiguas), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información que no esté cubierta o que sea específica para esta tarea.

Recopila este contexto (pregunta si no se proporciona):

### 1. Visibilidad Actual en IA
- ¿Sabes si tu marca aparece en respuestas generadas por IA hoy?
- ¿Has revisado ChatGPT, Perplexity o Google AI Overviews para tus consultas clave?
- ¿Qué consultas son más importantes para tu negocio?

### 2. Contenido y Dominio
- ¿Qué tipo de contenido produces? (Blog, documentación, comparaciones, páginas de producto)
- ¿Cuál es tu autoridad de dominio / fortaleza en SEO tradicional?
- ¿Tienes datos estructurados existentes (schema markup)?

### 3. Objetivos
- ¿Ser citado como fuente en respuestas de IA?
- ¿Aparecer en Google AI Overviews para consultas específicas?
- ¿Competir con marcas específicas que ya están siendo citadas?
- ¿Optimizar contenido existente o crear contenido nuevo optimizado para IA?

### 4. Panorama Competitivo
- ¿Quiénes son tus principales competidores en los resultados de búsqueda de IA?
- ¿Están siendo citados donde tú no lo eres?

---

## Cómo Funciona la Búsqueda de IA

### El Panorama de la Búsqueda de IA

| Plataforma | Cómo Funciona | Selección de Fuentes |
|------------|---------------|----------------------|
| **Google AI Overviews** | Resume las páginas mejor clasificadas | Fuerte correlación con rankings tradicionales |
| **ChatGPT (con búsqueda)** | Busca en la web, cita fuentes | Extrae de un rango más amplio, no solo del top |
| **Perplexity** | Siempre cita fuentes con enlaces | Favorece contenido autorizado, reciente y bien estructurado |
| **Gemini** | Asistente de IA de Google | Extrae del índice de Google + Knowledge Graph |
| **Copilot** | Búsqueda de IA con Bing | Índice de Bing + fuentes autorizadas |
| **Claude** | Brave Search (cuando está habilitado) | Datos de entrenamiento + resultados de búsqueda Brave |

Para un análisis profundo de cómo cada plataforma selecciona fuentes y qué optimizar por plataforma, ver [references/platform-ranking-factors.md](references/platform-ranking-factors.md).

### Diferencia Clave vs. SEO Tradicional

El SEO tradicional te posiciona. El SEO para IA te hace **citar**.

En la búsqueda tradicional, necesitas aparecer en la primera página. En la búsqueda de IA, una página bien estructurada puede ser citada aunque esté en la segunda o tercera página — los sistemas de IA seleccionan fuentes basándose en la calidad, estructura y relevancia del contenido, no solo en la posición de ranking.

**Datos clave:**
- AI Overviews aparece en ~45% de las búsquedas de Google
- AI Overviews reduce los clics a sitios web hasta un 58%
- Las marcas tienen 6.5x más probabilidades de ser citadas a través de fuentes de terceros que desde sus propios dominios
- El contenido optimizado se cita 3x más que el no optimizado
- Las estadísticas y citas aumentan la visibilidad en más de 40%

---

## Auditoría de Visibilidad en IA

Antes de optimizar, evalúa tu presencia actual en la búsqueda de IA.

### Paso 1: Revisar las Respuestas de IA para tus Consultas Clave

Probar 10-20 de tus consultas más importantes en distintas plataformas:

| Consulta | Google AI Overview | ChatGPT | Perplexity | ¿Te citan? | ¿Competidores citados? |
|----------|--------------------|---------|------------|:----------:|:----------------------:|
| [consulta 1] | Sí/No | Sí/No | Sí/No | Sí/No | [quién] |
| [consulta 2] | Sí/No | Sí/No | Sí/No | Sí/No | [quién] |

**Tipos de consultas a probar:**
- "¿Qué es [tu categoría de producto]?"
- "Mejor [categoría de producto] para [caso de uso]"
- "[Tu marca] vs [competidor]"
- "Cómo [problema que resuelve tu producto]"
- "Precio de [categoría de producto]"

### Paso 2: Analizar los Patrones de Citas

Cuando tus competidores son citados y tú no, examina:
- **Estructura del contenido** — ¿Es su contenido más extraíble?
- **Señales de autoridad** — ¿Tienen más citas, estadísticas, citas de expertos?
- **Frescura** — ¿Su contenido está más actualizado recientemente?
- **Schema markup** — ¿Tienen datos estructurados que tú no tienes?
- **Presencia de terceros** — ¿Se les cita a través de Wikipedia, Reddit, sitios de reseñas?

### Paso 3: Verificación de Extractabilidad del Contenido

Para cada página prioritaria, verificar:

| Verificación | Aprobado/Reprobado |
|--------------|:------------------:|
| ¿Definición clara en el primer párrafo? | |
| ¿Bloques de respuesta autónomos (funcionan sin contexto circundante)? | |
| ¿Estadísticas con fuentes citadas? | |
| ¿Tablas comparativas para consultas "[X] vs [Y]"? | |
| ¿Sección de FAQ con preguntas en lenguaje natural? | |
| ¿Schema markup (FAQ, HowTo, Article, Product)? | |
| ¿Atribución de expertos (nombre del autor, credenciales)? | |
| ¿Actualizado recientemente (dentro de 6 meses)? | |
| ¿La estructura de encabezados coincide con los patrones de consulta? | |
| ¿Los bots de IA permitidos en robots.txt? | |

### Paso 4: Verificación de Acceso de Bots de IA

Verifica que tu robots.txt permita los rastreadores de IA. Cada plataforma de IA tiene su propio bot, y bloquearlo significa que esa plataforma no puede citarte:

- **GPTBot** y **ChatGPT-User** — OpenAI (ChatGPT)
- **PerplexityBot** — Perplexity
- **ClaudeBot** y **anthropic-ai** — Anthropic (Claude)
- **Google-Extended** — Google Gemini y AI Overviews
- **Bingbot** — Microsoft Copilot (vía Bing)

Revisa tu robots.txt para reglas `Disallow` que apunten a cualquiera de estos. Si los encuentras bloqueados, debes tomar una decisión de negocio: bloquear impide el entrenamiento de IA con tu contenido, pero también impide las citas. Un punto medio es bloquear solo los rastreadores de entrenamiento (como **CCBot** de Common Crawl) mientras se permiten los bots de búsqueda listados arriba.

Ver [references/platform-ranking-factors.md](references/platform-ranking-factors.md) para la configuración completa de robots.txt.

---

## Estrategia de Optimización

### Los Tres Pilares

```
1. Estructura (hazlo extraíble)
2. Autoridad (hazlo citable)
3. Presencia (está donde la IA mira)
```

### Pilar 1: Estructura — Hacer el Contenido Extraíble

Los sistemas de IA extraen pasajes, no páginas. Cada afirmación clave debe funcionar como declaración independiente.

**Patrones de bloques de contenido:**
- **Bloques de definición** para consultas "¿Qué es X?"
- **Bloques paso a paso** para consultas "Cómo hacer X"
- **Tablas comparativas** para consultas "X vs Y"
- **Bloques de pros/contras** para consultas de evaluación
- **Bloques de FAQ** para preguntas frecuentes
- **Bloques de estadísticas** con fuentes citadas

Para plantillas detalladas de cada tipo de bloque, ver [references/content-patterns.md](references/content-patterns.md).

**Reglas estructurales:**
- Comenzar cada sección con una respuesta directa (no enterrarla)
- Mantener los pasajes de respuesta clave en 40-60 palabras (óptimo para extracción)
- Usar encabezados H2/H3 que coincidan con cómo las personas formulan consultas
- Las tablas superan al texto para contenido comparativo
- Las listas numeradas superan a los párrafos para contenido de procesos
- Cada párrafo debe transmitir una idea clara

### Pilar 2: Autoridad — Hacer el Contenido Citable

Los sistemas de IA prefieren fuentes confiables. Construir credibilidad para ser citado.

**La investigación de Princeton GEO** (KDD 2024, estudiada en Perplexity.ai) clasificó 9 métodos de optimización:

| Método | Aumento de Visibilidad | Cómo Aplicarlo |
|--------|:----------------------:|----------------|
| **Citar fuentes** | +40% | Agregar referencias autorizadas con enlaces |
| **Agregar estadísticas** | +37% | Incluir números específicos con fuentes |
| **Agregar citas de expertos** | +30% | Citas de expertos con nombre y cargo |
| **Tono autoritativo** | +25% | Escribir con experiencia demostrada |
| **Mejorar la claridad** | +20% | Simplificar conceptos complejos |
| **Términos técnicos** | +18% | Usar terminología del sector |
| **Vocabulario único** | +15% | Aumentar la diversidad de palabras |
| **Optimización de fluidez** | +15-30% | Mejorar la legibilidad y el flujo |
| ~~Relleno de palabras clave~~ | **-10%** | **Activamente perjudica la visibilidad en IA** |

**Mejor combinación:** Fluidez + Estadísticas = máximo aumento. Los sitios con menor ranking se benefician aún más — hasta un 115% de aumento de visibilidad con citas.

**Estadísticas y datos** (+37-40% de aumento en citas)
- Incluir números específicos con fuentes
- Citar investigación original, no resúmenes de investigación
- Agregar fechas a todas las estadísticas
- Los datos originales superan a los datos agregados

**Atribución de expertos** (+25-30% de aumento en citas)
- Autores nombrados con credenciales
- Citas de expertos con cargos y organizaciones
- Marco "Según [Fuente]" para afirmaciones
- Bios de autores con experiencia relevante

**Señales de frescura**
- "Última actualización: [fecha]" mostrado de forma prominente
- Actualizaciones regulares de contenido (mínimo trimestral para temas competitivos)
- Referencias al año actual y estadísticas recientes
- Eliminar o actualizar información desactualizada

**Alineación con E-E-A-T**
- Experiencia de primera mano demostrada
- Información específica y detallada (no genérica)
- Fuentes y metodología transparentes
- Experiencia clara del autor en el tema

### Pilar 3: Presencia — Estar Donde la IA Mira

Los sistemas de IA no solo citan tu sitio web — citan dónde apareces.

**Las fuentes de terceros importan más que tu propio sitio:**
- Menciones en Wikipedia (7.8% de todas las citas de ChatGPT)
- Discusiones en Reddit (1.8% de las citas de ChatGPT)
- Publicaciones del sector y artículos de invitado
- Sitios de reseñas (G2, Capterra, TrustRadius para SaaS B2B)
- YouTube (frecuentemente citado por Google AI Overviews)
- Respuestas en Quora

**Acciones:**
- Asegúrate de que tu página de Wikipedia sea precisa y esté actualizada
- Participa auténticamente en comunidades de Reddit
- Aparecer en resúmenes del sector y artículos comparativos
- Mantener perfiles actualizados en plataformas de reseñas relevantes
- Crear contenido en YouTube para consultas clave de "cómo hacer"
- Responder preguntas relevantes en Quora con profundidad

### Schema Markup para IA

Los datos estructurados ayudan a los sistemas de IA a entender tu contenido. Schemas clave:

| Tipo de Contenido | Schema | Por qué Ayuda |
|-------------------|--------|---------------|
| Artículos/Posts de blog | `Article`, `BlogPosting` | Identificación de autor, fecha y tema |
| Contenido de instrucciones | `HowTo` | Extracción de pasos para consultas de proceso |
| FAQs | `FAQPage` | Extracción directa de preguntas y respuestas |
| Productos | `Product` | Precios, características, reseñas |
| Comparaciones | `ItemList` | Datos de comparación estructurados |
| Reseñas | `Review`, `AggregateRating` | Señales de confianza |
| Organización | `Organization` | Reconocimiento de entidad |

El contenido con schema adecuado muestra un 30-40% mayor de visibilidad en IA. Para la implementación, usar la habilidad **schema-markup**.

---

## Tipos de Contenido que Más se Citan

No todo el contenido es igualmente citable. Priorizar estos formatos:

| Tipo de Contenido | Participación en Citas | Por qué la IA lo Cita |
|-------------------|:---------------------:|----------------------|
| **Artículos comparativos** | ~33% | Estructurado, equilibrado, alta intención |
| **Guías definitivas** | ~15% | Comprensivas, autorizadas |
| **Investigación/datos originales** | ~12% | Estadísticas únicas y citables |
| **Mejores listas** | ~10% | Estructura clara, rico en entidades |
| **Páginas de producto** | ~10% | Detalles específicos que la IA puede extraer |
| **Guías de instrucciones** | ~8% | Estructura paso a paso |
| **Opinión/análisis** | ~10% | Perspectiva de experto, citeable |

**Contenido de bajo rendimiento para citas de IA:**
- Posts de blog genéricos sin estructura
- Páginas de producto superficiales con texto de marketing vacío
- Contenido detrás de un muro de pago (la IA no puede acceder)
- Contenido sin fechas ni atribución de autor
- Contenido solo en PDF (más difícil de procesar para la IA)

---

## Monitoreo de la Visibilidad en IA

### Qué Rastrear

| Métrica | Qué Mide | Cómo Verificar |
|---------|----------|----------------|
| Presencia en AI Overview | ¿Aparecen AI Overviews para tus consultas? | Verificación manual o Semrush/Ahrefs |
| Tasa de citas de marca | ¿Con qué frecuencia se te cita en respuestas de IA? | Herramientas de visibilidad de IA |
| Share of AI voice | Tus citas vs. competidores | Peec AI, Otterly, ZipTie |
| Sentimiento de las citas | Cómo describe la IA tu marca | Revisión manual + herramientas de monitoreo |
| Atribución de fuente | Cuáles de tus páginas se citan | Rastrear tráfico de referencia de fuentes de IA |

### Herramientas de Monitoreo de Visibilidad en IA

| Herramienta | Cobertura | Mejor Para |
|-------------|-----------|------------|
| **Otterly AI** | ChatGPT, Perplexity, Google AI Overviews | Seguimiento de share of AI voice |
| **Peec AI** | ChatGPT, Gemini, Perplexity, Claude, Copilot+ | Monitoreo multiplataforma a escala |
| **ZipTie** | Google AI Overviews, ChatGPT, Perplexity | Seguimiento de menciones de marca + sentimiento |
| **LLMrefs** | ChatGPT, Perplexity, AI Overviews, Gemini | Mapeo de palabras clave SEO → visibilidad en IA |

### Monitoreo Manual (Sin Herramientas)

Verificación mensual:
1. Selecciona tus 20 consultas principales
2. Ejecuta cada una en ChatGPT, Perplexity y Google
3. Registra: ¿Te citan? ¿A quién? ¿Qué página?
4. Registra en una hoja de cálculo, sigue mes a mes

---

## SEO para IA por Tipo de Contenido

### Páginas de Producto SaaS

**Objetivo:** Ser citado en consultas "¿Qué es [categoría]?" y "Mejor [categoría]".

**Optimizar:**
- Descripción clara del producto en el primer párrafo (qué hace, para quién es)
- Tablas de comparación de características (tú vs. la categoría, no solo competidores)
- Métricas específicas ("procesa 10,000 transacciones/seg" en lugar de "ultra rápido")
- Número de clientes o prueba social con cifras
- Transparencia de precios (la IA cita páginas con precios visibles)
- Sección de FAQ abordando preguntas comunes de compradores

### Contenido de Blog

**Objetivo:** Ser citado como fuente autorizada en temas de tu sector.

**Optimizar:**
- Una consulta objetivo clara por publicación (hacer coincidir el encabezado con la consulta)
- Definición en el primer párrafo para consultas "¿Qué es?"
- Datos originales, investigación o citas de expertos
- Fecha de "última actualización" visible
- Bio del autor con credenciales relevantes
- Enlaces internos a páginas de productos/funciones relacionadas

### Páginas de Comparación/Alternativas

**Objetivo:** Ser citado en consultas "[X] vs [Y]" y "Mejores alternativas a [X]".

**Optimizar:**
- Tablas de comparación estructuradas (no solo texto)
- Equilibrado y justo (la IA penaliza las comparaciones obviamente sesgadas)
- Criterios específicos con puntuaciones o calificaciones
- Datos de precios y funciones actualizados
- Consultar la habilidad competitor-alternatives para construir estas páginas

### Documentación / Contenido de Ayuda

**Objetivo:** Ser citado en consultas "Cómo [X] con [tu producto]".

**Optimizar:**
- Formato paso a paso con listas numeradas
- Ejemplos de código donde sea relevante
- Schema markup HowTo
- Capturas de pantalla con texto alternativo descriptivo
- Prerrequisitos claros y resultados esperados

---

## Errores Comunes

- **Ignorar la búsqueda de IA completamente** — ~45% de las búsquedas de Google ahora muestran AI Overviews, y ChatGPT/Perplexity están creciendo rápidamente
- **Tratar el SEO para IA como algo separado del SEO** — El buen SEO tradicional es la base; el SEO para IA agrega estructura y autoridad encima
- **Escribir para la IA, no para humanos** — Si el contenido parece escrito para engañar un algoritmo, no se citará ni convertirá
- **Sin señales de frescura** — El contenido sin fecha pierde ante el contenido fechado porque los sistemas de IA ponderan mucho la recencia
- **Poner todo el contenido detrás de un muro de pago** — La IA no puede acceder al contenido restringido
- **Ignorar la presencia de terceros** — Puedes obtener más citas de IA de una mención en Wikipedia que de tu propio blog
- **Sin datos estructurados** — El schema markup le da a los sistemas de IA contexto estructurado sobre tu contenido
- **Relleno de palabras clave** — A diferencia del SEO tradicional donde solo es ineficaz, el relleno de palabras clave reduce activamente la visibilidad en IA un 10%
- **Bloquear bots de IA** — Si GPTBot, PerplexityBot o ClaudeBot están bloqueados en robots.txt, esas plataformas no pueden citarte
- **Contenido genérico sin datos** — "Somos los mejores" no se citará. "Nuestros clientes ven una mejora 3x en [métrica]" sí
- **Olvidar monitorear** — No puedes mejorar lo que no mides. Revisa la visibilidad en IA mensualmente como mínimo

---

## Integraciones de Herramientas

Para implementación, ver el [registro de herramientas](../../tools/REGISTRY.md).

| Herramienta | Para qué se usa |
|-------------|-----------------|
| `semrush` | Seguimiento de AI Overview, investigación de palabras clave, análisis de brechas de contenido |
| `ahrefs` | Análisis de backlinks, explorador de contenido, datos de AI Overview |
| `gsc` | Datos de rendimiento de Search Console, seguimiento de consultas |
| `ga4` | Tráfico de referencia desde fuentes de IA |

---

## Preguntas Específicas de la Tarea

1. ¿Cuáles son tus 10-20 consultas más importantes?
2. ¿Has verificado si existen respuestas de IA para esas consultas hoy?
3. ¿Tienes datos estructurados (schema markup) en tu sitio?
4. ¿Qué tipos de contenido publicas? (Blog, documentación, comparaciones, etc.)
5. ¿Los competidores están siendo citados por la IA donde tú no lo eres?
6. ¿Tienes una página de Wikipedia o presencia en sitios de reseñas?

---

## Habilidades Relacionadas

- **seo-audit**: Para auditorías de SEO técnico y on-page tradicional
- **schema-markup**: Para implementar datos estructurados que ayudan a la IA a entender tu contenido
- **content-strategy**: Para planificar qué contenido crear
- **competitor-alternatives**: Para crear páginas comparativas que se citan
- **programmatic-seo**: Para construir páginas de SEO a escala
- **copywriting**: Para escribir contenido que sea tanto legible para humanos como extraíble por IA
