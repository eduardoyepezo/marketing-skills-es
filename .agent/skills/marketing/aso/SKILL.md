---
name: aso
metadata:
  version: 2.0.0
description: "Cuando el usuario quiere auditar u optimizar una ficha de App Store o Google Play. También usar cuando el usuario menciona 'auditoría ASO,' 'app store optimization,' 'optimizar mi ficha de la app,' 'mejorar la visibilidad de mi app,' 'ranking en el App Store,' 'audita mi ficha,' 'por qué nadie descarga mi app,' 'mejorar la conversión de mi app,' 'optimización de keywords para apps,' o 'compara mi app con la competencia.' Usar cuando el usuario comparte una URL de App Store o Google Play y quiere mejorarla."
---

# Auditoría ASO

Analiza fichas de App Store y Google Play contra las mejores prácticas de ASO. Obtiene
datos en vivo de la ficha, califica metadata, elementos visuales y ratings, y luego
produce un plan de acción priorizado.

## Cuándo Usar

- El usuario comparte una URL de App Store o Google Play
- El usuario pide auditar u optimizar una ficha de app
- El usuario quiere comparar su app contra la competencia
- El usuario pregunta sobre ranking en la tienda, visibilidad o conversión de descargas

## Antes de Auditar

**Verifica primero el contexto de marketing del producto:**
Si existe `.agents/product-marketing.md` (o `.claude/product-marketing.md`, o el nombre de archivo legado `product-marketing-context.md`, en configuraciones antiguas), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información no cubierta o específica para esta tarea.

## Fase 1 — Identificar Tienda y Obtener Datos

### Detectar el tipo de tienda desde la URL

```
Apple:  apps.apple.com/{country}/app/{name}/id{digits}
Google: play.google.com/store/apps/details?id={package}
```

Si el usuario da un nombre de app en vez de una URL, busca en la web:
`site:apps.apple.com "{nombre de la app}"` o `site:play.google.com "{nombre de la app}"`

### Obtener la ficha

Usa WebFetch para obtener la página de la ficha. Extrae todos los campos disponibles:

**Campos de Apple App Store:**

- Nombre de la app (título) — límite de 30 caracteres
- Subtítulo — límite de 30 caracteres
- Descripción (larga) — no se indexa para búsqueda, pero importa para la conversión
- Texto promocional — 170 caracteres, actualizable sin nueva versión
- Categoría (primaria + secundaria)
- Screenshots (cantidad, orden, texto de caption)
- Video de vista previa (presencia, duración)
- Rating (promedio + cantidad)
- Reviews recientes (las visibles)
- Precio / compras dentro de la app
- Nombre del desarrollador
- Fecha de última actualización
- Notas del historial de versiones
- Clasificación por edad
- Tamaño
- Idiomas / localizaciones listadas
- Eventos dentro de la app (si hay alguno visible)

**Campos de Google Play:**

- Nombre de la app (título) — límite de 30 caracteres
- Descripción corta — límite de 80 caracteres
- Descripción completa — límite de 4,000 caracteres, SÍ se indexa para búsqueda
- Categoría + etiquetas
- Feature graphic (presencia)
- Screenshots (cantidad, orden)
- Video de vista previa (presencia)
- Rating (promedio + cantidad)
- Reviews recientes (las visibles)
- Precio / compras dentro de la app
- Nombre del desarrollador
- Fecha de última actualización
- Texto de "Novedades"
- Rango de descargas
- Clasificación de contenido
- Sección de seguridad de datos
- Idiomas listados

Si WebFetch retorna datos incompletos (las tiendas renderizan del lado del cliente),
anota los vacíos y trabaja con lo disponible. Pide al usuario que pegue los campos
faltantes si son críticos.

### Evaluación de elementos visuales

WebFetch no puede extraer las imágenes de los screenshots ni el texto de los captions.
**Toma un screenshot de la página de la ficha** para obtener datos visuales:

1. Navega a la URL de la ficha y captura un screenshot de página completa
2. Evalúa el screenshot para: calidad del ícono, cantidad de screenshots, texto de
   captions, calidad del mensaje, presencia de video de vista previa, feature graphic
   (Google Play)
3. Si las herramientas de navegador no están disponibles, pide al usuario que comparta
   un screenshot de la página de la ficha

**Texto promocional (Apple):** Este campo de 170 caracteres aparece encima de la
descripción pero a menudo es indistinguible de ella en el HTML extraído. Si no puedes
confirmar su presencia, anótalo y recomienda al usuario revisar App Store Connect.

---

## Fase 1.5 — Evaluar Madurez de Marca

Antes de calificar, clasifica la app en uno de tres niveles. Esto determina cómo
interpretas las desviaciones del "ASO de manual" — una elección de marca deliberada
por un nombre reconocido no es lo mismo que una oportunidad perdida por una app
desconocida.

### Definiciones de nivel

| Nivel            | Señales                                                                                                                                | Ejemplos                                    |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| **Dominante**     | Nombre reconocido, 1M+ ratings, top-10 en su categoría, reconocimiento de marca casi universal. Los usuarios buscan por nombre de marca, no por keywords genéricas. | Instagram, Uber, Spotify, WhatsApp, Netflix |
| **Establecida**   | Bien conocida en su categoría, 100K+ ratings, fuertes instalaciones orgánicas, marca reconocida pero no universalmente conocida.        | Strava, Notion, Duolingo, Cash App, Calm    |
| **Retadora**      | Construyendo awareness, <100K ratings, necesita descubrimiento a través de keywords y tácticas de ASO. La mayoría de las apps están aquí. | Tu app, la mayoría de apps indie/startup    |

### Cómo el nivel afecta la calificación

**Las apps Dominantes** obtienen calificación ajustada en estas áreas:

- **Título:** Títulos solo de marca o marca primero son válidos (calificación 8+ si la
  marca es la keyword). Estas apps no necesitan descubrimiento genérico por keywords.
- **Descripción:** Calificar puramente por calidad de conversión, no por presencia de
  keywords. Si la app es un nombre reconocido, una descripción de marca bien elaborada
  supera a una saturada de keywords.
- **Elementos Visuales:** Fotografía de lifestyle/marca en lugar de demos de UI es una
  estrategia de conversión legítima. La ausencia de video es aceptable si el producto
  es difícil de demostrar en 30s o el awareness de marca es casi universal.
- **Novedades:** Notas de lanzamiento genéricas con cadencia semanal o mayor son
  aceptables (calificación 8+). A esa escala, los changelogs detallados tienen un ROI
  mínimo y arriesgan una reacción negativa.
- **Eventos dentro de la app:** La ausencia de eventos para apps utilitarias con bases
  de instalación masivas (Uber, WhatsApp) no es una penalización. Estas apps no
  necesitan ayuda de descubrimiento.
- **Localización:** Calificar en relación con el mercado real, no con la cantidad
  absoluta. Una fintech solo de EE.UU. con 2 idiomas (inglés + español) está
  apropiadamente localizada.

**Las apps Establecidas** obtienen un ajuste parcial:

- Los títulos marca-primero están bien pero deberían incluir 1-2 keywords
- Las decisiones estratégicas de descripción reciben el beneficio de la duda
- Las demás dimensiones se califican normalmente

**Las apps Retadoras** se califican estrictamente contra las mejores prácticas de
ASO de manual — cada carácter, screenshot y keyword importa.

**Principio clave:** Antes de restar puntos, pregunta: "¿Es esto un error o una
elección deliberada de un equipo que tiene datos que yo no tengo?" Si la app tiene
1M+ ratings y un equipo dedicado de ASO, asume que sus decisiones están informadas
por datos a menos que sean claramente erróneas.

---

## Fase 2 — Calificar Cada Dimensión

Califica cada dimensión de 0-10 usando los criterios en `references/scoring-criteria.md`.
Aplica los ajustes por nivel de madurez de marca de la Fase 1.5.

Archivos de referencia para specs de plataforma y benchmarks:

- `references/apple-specs.md` — Límites oficiales de caracteres de Apple, specs de
  screenshots/video, reglas de CPP/PPO, triggers de rechazo
- `references/google-play-specs.md` — Límites oficiales de Google Play, specs de
  screenshots, umbrales de Android Vitals, políticas
- `references/benchmarks.md` — Datos de conversión, impacto de rating, lift de video,
  comportamiento de screenshots, benchmarks de CPP/eventos

### Dimensiones y Pesos

| #   | Dimensión                | Peso | Qué Cubre                                                                    |
| --- | ------------------------- | ---- | ----------------------------------------------------------------------------- |
| 1   | Título y Subtítulo        | 20%  | Uso de caracteres, presencia de keywords, claridad, balance marca + keyword   |
| 2   | Descripción                | 15%  | Primeras 3 líneas, densidad de keywords (Google), CTA, estructura, texto promocional |
| 3   | Elementos Visuales         | 25%  | Cantidad/calidad/mensaje de screenshots, video, ícono, feature graphic        |
| 4   | Ratings y Reviews          | 20%  | Rating promedio, volumen, recencia, respuestas del desarrollador              |
| 5   | Metadata y Frescura        | 10%  | Elección de categoría, recencia de actualización, cantidad de localizaciones, seguridad de datos |
| 6   | Señales de Conversión      | 10%  | Posicionamiento de precio, transparencia de IAP, prueba social, rango de descargas |

**Puntaje final** = suma ponderada, sobre 100.

### Interpretación del puntaje

| Puntaje | Grado | Significado                                                       |
| ------- | ----- | ------------------------------------------------------------------- |
| 85-100  | A     | Bien optimizado; enfocarse en A/B testing e iteración                |
| 70-84   | B     | Buena base; oportunidades claras de mejora                          |
| 50-69   | C     | Brechas significativas; las correcciones priorizadas tendrán alto impacto |
| 30-49   | D     | Se necesita optimización mayor en múltiples dimensiones              |
| 0-29    | F     | La ficha necesita una revisión completa                              |

---

## Fase 3 — Comparación con Competidores (Opcional)

Si el usuario proporciona URLs de competidores o pide una comparación:

1. Obtén los datos de 2-3 competidores top en la misma categoría
2. Ejecuta la misma calificación en cada uno
3. Construye una tabla comparativa destacando dónde la app del usuario es más débil/fuerte
4. Identifica brechas de keywords — términos por los que rankean los competidores y que
   la app del usuario no está apuntando

Si no se especifican competidores, sugiere al usuario proporcionar 2-3 u ofrece
buscar las apps top en su categoría.

---

## Fase 4 — Generar Reporte

Usa la plantilla en `references/report-template.md` para estructurar el output.

El reporte debe incluir:

1. **Tarjeta de puntaje** — tabla con las 6 dimensiones, puntajes y grado
2. **Top 3 quick wins** — cambios que toman <1 hora y tienen el mayor impacto
3. **Hallazgos detallados** — desglose por dimensión con problemas específicos y correcciones
4. **Sugerencias de keywords** — basadas en análisis de título/descripción y brechas de competidores
5. **Recomendaciones de elementos visuales** — mejoras específicas de screenshot/video
6. **Plan de acción priorizado** — lista ordenada de cambios por impacto vs. esfuerzo

### Reglas del reporte

- Cada recomendación debe ser **específica y accionable** ("Cambia el subtítulo de X a Y" no "Mejora el subtítulo")
- Incluye el conteo de caracteres para todas las recomendaciones de texto
- Marca las diferencias específicas de plataforma (Apple vs. Google) cuando sea relevante
- Anota lo que NO se puede evaluar sin herramientas pagas (volumen de búsqueda, rankings exactos)
- Al sugerir cambios de keywords, explica POR QUÉ importa cada keyword

---

## Reglas Específicas por Plataforma

### Apple App Store — Datos Clave

- Título (30 caracteres) + Subtítulo (30 caracteres) + Campo de keywords (100 **bytes**, oculto) = texto indexado
- El campo de keywords se mide en bytes, no en caracteres — árabe/CJK usan 2-3 bytes por carácter
- La descripción larga NO se indexa para búsqueda — optimízala solo para conversión
- El texto promocional (170 caracteres) NO afecta la búsqueda (confirmado por Apple)
- Nunca repitas palabras entre título/subtítulo/campo de keywords (Apple indexa cada palabra una sola vez)
- Campo de keywords: comas, sin espacios ("photo,editor,filter" no "photo, editor, filter")
- Screenshots: hasta 10 por dispositivo. Los primeros 3 son visibles en búsqueda — el 90% nunca hace scroll pasado el 3ro
- Los captions de screenshots se indexan desde junio de 2025 (extracción con IA)
- Eventos dentro de la app: máximo 10 publicados a la vez, máximo 31 días cada uno. Se indexan y aparecen en búsqueda
- Custom Product Pages (hasta 70) en búsqueda orgánica desde julio de 2025. +5.9% de lift promedio en conversión
- Video de vista previa: hasta 3, 15-30s cada uno. Autoplay silenciado — +20-40% de lift en conversión
- SKStoreReviewController: máximo 3 prompts por 365 días
- Apple tiene curación editorial humana — la calidad y el diseño importan más
- Ver `references/apple-specs.md` para specs completas, dimensiones y triggers de rechazo

### Google Play — Datos Clave

- Título (30 caracteres) + Descripción corta (80 caracteres) + Descripción completa (4,000 caracteres) = texto indexado
- La descripción completa SÍ se indexa — apunta a una densidad de keywords de 2-3% de forma natural
- No hay campo de keywords oculto — todas las keywords deben estar en el texto visible
- Google usa NLP/comprensión semántica — el keyword stuffing se detecta y se penaliza
- Prohibido en el título: emojis, TODO EN MAYÚSCULAS, "best"/"#1"/"free", CTAs (aplicado desde 2021)
- Screenshots: mínimo 2, **máximo 8** por dispositivo (no 10 como Apple)
- Feature graphic (1024x500, exacto) requerido para posicionamientos destacados
- El video NO hace autoplay — solo ~6% de los usuarios toca play (bajo ROI vs. iOS)
- Android Vitals afecta directamente el ranking: crash >1.09% o ANR >0.47% = visibilidad reducida
- Promotional Content: envíalo 14 días antes para ser destacado. Las apps ven 2x más adquisiciones desde explorar
- Custom Store Listings: hasta 50 (pueden apuntar a usuarios inactivos, países específicos, campañas de ads)
- Store Listing Experiments: prueba hasta 3 variantes, corre 7+ días, 1 experimento a la vez
- Ver `references/google-play-specs.md` para specs completas y detalles de políticas

### Qué Indexa Apple vs. Qué Indexa Google

| Campo                    | ¿Apple Indexa?      | ¿Google Indexa?          |
| ------------------------- | -------------------- | -------------------------- |
| Título                    | Sí                   | Sí (señal más fuerte)      |
| Subtítulo / Desc. corta   | Sí                   | Sí                          |
| Campo de keywords         | Sí (oculto)          | No existe                  |
| Descripción larga         | No                   | Sí (fuertemente)           |
| Captions de screenshots   | Sí (desde 2025)      | No                          |
| Eventos dentro de la app  | Sí                   | N/A (LiveOps en su lugar)  |
| Nombre del desarrollador  | No                   | Parcial                    |
| Nombres de IAP            | Sí                   | Sí                          |

---

## Checklist de Problemas Comunes

Marca estos si los encuentras. Los ítems marcados _(depende del nivel)_ deben
evaluarse contra el nivel de madurez de marca de la app — pueden ser elecciones
deliberadas para apps Dominantes.

**Siempre marcar (todos los niveles):**

- [ ] Rating por debajo de 4.0
- [ ] Última actualización > 3 meses atrás
- [ ] La descripción de Google Play no tiene estrategia de keywords (densidad menor a 1%)
- [ ] A Google Play le falta el feature graphic
- [ ] El campo de keywords de Apple probablemente tiene palabras repetidas (inferido del título+subtítulo)
- [ ] Desajuste de categoría — la app enfrentaría menos competencia en otra categoría
- [ ] Menos de 5 screenshots

**Marcar solo para Retadora/Establecida** _(no son errores para apps Dominantes):_

- [ ] El título desperdicia caracteres solo en el nombre de marca (sin keywords) _(Dominante: la marca ES la keyword)_
- [ ] El subtítulo/descripción corta duplica las keywords del título
- [ ] Las primeras 3 líneas de la descripción son genéricas _(Dominante: puede ser una elección de voz de marca)_
- [ ] Sin video de vista previa _(Dominante: puede ser racional si el producto es difícil de demostrar)_
- [ ] Los screenshots son solo capturas de UI sin mensaje/captions _(Dominante: fotos de lifestyle/marca pueden convertir mejor)_
- [ ] Solo 1-2 localizaciones _(calificar en relación al mercado real, no a la cantidad absoluta)_
- [ ] Sin eventos dentro de la app ni contenido promocional _(Dominante: las apps utilitarias pueden no necesitar ayuda de descubrimiento)_

**Marcar para todos los niveles pero anotar el contexto:**

- [ ] Sin respuestas del desarrollador a reviews negativos _(anota el volumen — responder con 10M+ reviews es un desafío distinto que con 1K)_
- [ ] Texto genérico de "Novedades" _(aceptable con cadencia de lanzamiento semanal o mayor para apps Establecidas/Dominantes)_

---

## Preguntas Específicas de la Tarea

1. ¿Cuál es la URL de App Store o Google Play?
2. ¿Es tu app o la de un competidor?
3. ¿En qué categoría compite la app?
4. ¿Tienes URLs de competidores para comparar?
5. ¿Estás enfocado en visibilidad de búsqueda, tasa de conversión, o ambas?
6. ¿Tienes acceso a datos de App Store Connect o Google Play Console?

---

## Skills Relacionadas

- **page-cro**: Para optimizar la conversión de landing pages web que impulsan instalaciones de apps
- **ad-creative**: Para crear creatividades de anuncios para App Store y Google Play
- **analytics-tracking**: Para configurar atribución de instalaciones y tracking de eventos dentro de la app
- **customer-research**: Para entender las necesidades y el lenguaje de los usuarios e informar el copy de la ficha
