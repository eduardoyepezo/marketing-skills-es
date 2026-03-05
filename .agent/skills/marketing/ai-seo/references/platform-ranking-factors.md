# Cómo Cada Plataforma de IA Selecciona Sus Fuentes

Cada plataforma de búsqueda de IA tiene su propio índice de búsqueda, lógica de clasificación y preferencias de contenido. Esta guía cubre qué importa para ser citado en cada una.

Fuentes citadas a lo largo del documento: Estudio GEO de Princeton (KDD 2024), estudio de autoridad de dominio de SE Ranking, análisis de ajuste contenido-respuesta de ZipTie.

---

## Los Fundamentos

Todas las plataformas de IA comparten tres requisitos básicos:

1. **Tu contenido debe estar en su índice** — Cada plataforma usa un backend de búsqueda diferente (Google, Bing, Brave o el propio). Si no estás indexado, no puedes ser citado.
2. **Tu contenido debe ser rastreable** — Los bots de IA necesitan acceso vía robots.txt. Bloquear el bot equivale a perder la cita.
3. **Tu contenido debe ser extraíble** — Los sistemas de IA extraen pasajes, no páginas. Una estructura clara y párrafos autocontenidos son los ganadores.

Más allá de estos fundamentos, cada plataforma pondera diferentes señales. Aquí está qué importa y dónde.

---

## Google AI Overviews

Los AI Overviews de Google extraen del propio índice de Google y se apoyan fuertemente en las señales E-E-A-T (Experiencia, Expertise, Autoridad, Confiabilidad). Aparecen en aproximadamente el 45% de las búsquedas de Google.

**Qué hace diferente a Google AI Overviews:** Ya tienen tus señales de SEO tradicional — backlinks, autoridad de página, relevancia temática. La capa adicional de IA agrega una preferencia por contenido con fuentes citadas y datos estructurados. La investigación muestra que incluir citas autorizadas en tu contenido correlaciona con un aumento de visibilidad del 132%, y escribir con un tono autoritativo (no de ventas) agrega otro 89%.

**Importante: Los AI Overviews no simplemente reciclan el Top 10 tradicional.** Solo alrededor del 15% de las fuentes de AI Overview se superponen con los resultados orgánicos convencionales. Las páginas que no entrarían en la página 1 en búsqueda tradicional todavía pueden ser citadas si tienen datos estructurados sólidos y respuestas claras y extraíbles.

**En qué enfocarse:**
- El schema markup es la palanca más grande — los schemas Article, FAQPage, HowTo y Product dan a los AI Overviews contexto estructurado con el que trabajar (aumento de visibilidad del 30-40%)
- Construir autoridad temática a través de clusters de contenido con fuerte enlazado interno
- Incluir citas nombradas y con fuente en tu contenido (no solo afirmaciones)
- Las bios de autores con credenciales reales importan — E-E-A-T se pondera fuertemente
- Ingresar al Knowledge Graph de Google cuando sea posible (una entrada precisa en Wikipedia ayuda)
- Apuntar a patrones de consultas "cómo hacer" y "qué es" — estos activan AI Overviews con más frecuencia

---

## ChatGPT

La búsqueda web de ChatGPT se nutre de un índice basado en Bing. Combina esto con su conocimiento de entrenamiento para generar respuestas, y luego cita las fuentes web en las que se apoyó.

**Qué hace diferente a ChatGPT:** La autoridad de dominio importa más aquí que en otras plataformas de IA. Un análisis de SE Ranking de 129,000 dominios encontró que las señales de autoridad y credibilidad representan aproximadamente el 40% de lo que determina la cita, con la calidad del contenido en torno al 35% y la confianza de la plataforma en el 25%. Los sitios con recuentos muy altos de dominios de referencia (350K+) promedian 8.4 citas por respuesta, mientras que los sitios con puntuaciones de confianza ligeramente más bajas (91-96 vs 97-100) caen de 8.4 a 6 citas.

**La frescura es un gran diferenciador.** El contenido actualizado en los últimos 30 días se cita aproximadamente 3.2x más que el contenido más antiguo. ChatGPT claramente favorece la información reciente.

**La señal más importante es el ajuste contenido-respuesta** — un análisis de ZipTie de 400,000 páginas encontró que qué tan bien el estilo y la estructura de tu contenido coincide con el propio formato de respuesta de ChatGPT representa aproximadamente el 55% de la probabilidad de cita. Esto es mucho más importante que la autoridad de dominio (12%) o la estructura on-page (14%) por sí solas. Escribe de la manera en que ChatGPT respondería la pregunta, y es más probable que seas la fuente que cite.

**Dónde mira ChatGPT más allá de tu sitio:** Wikipedia representa el 7.8% de todas las citas de ChatGPT, Reddit el 1.8%, y Forbes el 1.1%. Los sitios oficiales de las marcas se citan con frecuencia, pero las menciones de terceros tienen un peso significativo.

**En qué enfocarse:**
- Invertir en backlinks y autoridad de dominio — es la señal de línea base más fuerte
- Actualizar el contenido competitivo al menos mensualmente
- Estructurar tu contenido de la manera en que ChatGPT estructura sus respuestas (conversacional, directo, bien organizado)
- Incluir estadísticas verificables con fuentes nombradas
- Jerarquía de encabezados limpia (H1 > H2 > H3) con encabezados descriptivos

---

## Perplexity

Perplexity siempre cita sus fuentes con enlaces clicables, lo que lo convierte en la plataforma de búsqueda de IA más transparente. Combina su propio índice con el de Google y ejecuta los resultados a través de múltiples pasadas de reranking — recuperación de relevancia inicial, luego puntuación de factores de clasificación tradicionales, luego evaluación de calidad basada en ML que puede descartar conjuntos de resultados completos si no cumplen los umbrales de calidad.

**Qué hace diferente a Perplexity:** Es el motor de búsqueda de IA más "orientado a la investigación", y su comportamiento de citas lo refleja. Perplexity mantiene listas curadas de dominios autorizados (Amazon, GitHub, grandes sitios académicos) que obtienen impulsos de clasificación inherentes. Utiliza un algoritmo de decaimiento temporal que evalúa el contenido nuevo rápidamente, dando a los publicadores nuevos una oportunidad real de ser citados.

**Perplexity tiene preferencias de contenido únicas:**
- **FAQ Schema (JSON-LD)** — Las páginas con datos estructurados FAQ se citan notablemente más a menudo
- **Documentos PDF** — Los PDFs accesibles públicamente (whitepapers, informes de investigación) son priorizados. Si tienes contenido PDF autorizado detrás de un formulario, considera hacer pública una versión.
- **Velocidad de publicación** — Con qué frecuencia publicas importa más que la segmentación de palabras clave
- **Párrafos autocontenidos** — Perplexity prefiere párrafos atómicos y semánticamente completos que puede extraer limpiamente

**En qué enfocarse:**
- Permitir PerplexityBot en robots.txt
- Implementar schema FAQPage en cualquier página con contenido de preguntas y respuestas
- Alojar recursos PDF públicamente (whitepapers, guías, informes)
- Agregar schema Article con marcas de tiempo de publicación y modificación
- Escribir en párrafos claros y autocontenidos que funcionen como respuestas independientes
- Construir autoridad temática profunda en tu nicho específico

---

## Microsoft Copilot

Copilot está integrado en todo el ecosistema de Microsoft — Edge, Windows, Microsoft 365 y Bing Search. Se basa completamente en el índice de Bing, por lo que si Bing no ha indexado tu contenido, Copilot no puede citarlo.

**Qué hace diferente a Copilot:** La conexión con el ecosistema de Microsoft crea oportunidades únicas de optimización. Las menciones y el contenido en LinkedIn y GitHub proporcionan impulsos de clasificación que otras plataformas no ofrecen. Copilot también pone más énfasis en la velocidad de página — los tiempos de carga de menos de 2 segundos son un umbral claro.

**En qué enfocarse:**
- Enviar tu sitio a Bing Webmaster Tools (muchos sitios solo envían a Google Search Console)
- Usar el protocolo IndexNow para una indexación más rápida del contenido nuevo y actualizado
- Optimizar la velocidad de página a menos de 2 segundos
- Escribir definiciones claras de entidades — cuando tu contenido define un término o concepto, hacer que la definición sea explícita y extraíble
- Construir presencia en LinkedIn (publicar artículos, mantener página de empresa) y GitHub si es relevante
- Asegurarse de que Bingbot tenga acceso completo de rastreo

---

## Claude

Claude usa Brave Search como su backend de búsqueda cuando la búsqueda web está habilitada — no Google, no Bing. Este es un índice completamente diferente, lo que significa que tu visibilidad en Brave Search determina directamente si Claude puede encontrarte y citarte.

**Qué hace diferente a Claude:** Claude es extremadamente selectivo sobre lo que cita. Si bien procesa enormes cantidades de contenido, su tasa de citas es muy baja — está buscando el contenido más factualmente preciso y bien fundamentado sobre un tema dado. El contenido rico en datos con números específicos y atribución clara tiene un rendimiento significativamente mejor que el contenido de propósito general.

**En qué enfocarse:**
- Verificar que tu contenido aparezca en los resultados de Brave Search (buscar tu marca y términos clave en search.brave.com)
- Permitir los agentes de usuario ClaudeBot y anthropic-ai en robots.txt
- Maximizar la densidad factual — números específicos, fuentes nombradas, estadísticas fechadas
- Usar estructura clara y extraíble con encabezados descriptivos
- Citar fuentes autorizadas dentro de tu contenido
- Apuntar a ser la fuente más factualmente precisa sobre tu tema — Claude premia la precisión

---

## Permitir Bots de IA en robots.txt

Si tu robots.txt bloquea un bot de IA, esa plataforma no puede citar tu contenido. Aquí están los agentes de usuario que debes permitir:

```
User-agent: GPTBot           # OpenAI — potencia la búsqueda de ChatGPT
User-agent: ChatGPT-User     # Modo de navegación de ChatGPT
User-agent: PerplexityBot    # Búsqueda de IA Perplexity
User-agent: ClaudeBot        # Anthropic Claude
User-agent: anthropic-ai     # Anthropic Claude (alternativo)
User-agent: Google-Extended   # Google Gemini y AI Overviews
User-agent: Bingbot          # Microsoft Copilot (vía Bing)
Allow: /
```

**Entrenamiento vs. búsqueda:** Algunos bots de IA se usan tanto para entrenamiento de modelos como para citas de búsqueda. Si quieres ser citado pero no quieres que tu contenido se use para entrenamiento, tus opciones son limitadas — GPTBot gestiona ambos para OpenAI. Sin embargo, puedes bloquear de forma segura **CCBot** (Common Crawl) sin afectar ninguna cita de búsqueda de IA, ya que solo se usa para la recopilación de conjuntos de datos de entrenamiento.

---

## Por Dónde Empezar

Si estás optimizando para búsqueda de IA por primera vez, concentra tu esfuerzo donde realmente está tu audiencia:

**Comenzar con Google AI Overviews** — Alcanzan a la mayoría de usuarios (más del 45% de las búsquedas de Google) y probablemente ya tienes bases de SEO de Google establecidas. Agregar schema markup, incluir fuentes citadas en tu contenido y fortalecer las señales E-E-A-T.

**Luego abordar ChatGPT** — Es la herramienta de búsqueda de IA independiente más usada para audiencias de tecnología y negocios. Enfocarse en la frescura (actualizar el contenido mensualmente), la autoridad de dominio y hacer coincidir la estructura de tu contenido con cómo ChatGPT formatea sus respuestas.

**Luego expandirse a Perplexity** — Especialmente valioso si tu audiencia incluye investigadores, adoptadores tempranos o profesionales de tecnología. Agregar schema FAQ, publicar recursos PDF y escribir en párrafos claros y autocontenidos.

**Copilot y Claude son de menor prioridad** a menos que tu audiencia se incline hacia empresarial/Microsoft (Copilot) o desarrollador/analista (Claude). Pero los fundamentos — contenido estructurado, fuentes citadas, schema markup — ayudan en todas las plataformas.

**Acciones que ayudan en todas partes:**
1. Permitir todos los bots de IA en robots.txt
2. Implementar schema markup (FAQPage, Article, Organization como mínimo)
3. Incluir estadísticas con fuentes nombradas en tu contenido
4. Actualizar el contenido regularmente — mensualmente para temas competitivos
5. Usar estructura de encabezados clara (H1 > H2 > H3)
6. Mantener el tiempo de carga de página por debajo de 2 segundos
7. Agregar bios de autores con credenciales
