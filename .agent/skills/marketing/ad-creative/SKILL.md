---
name: ad-creative
description: "Cuando el usuario quiere generar, iterar o escalar creatividades publicitarias — titulares, descripciones, texto principal o variaciones completas de anuncios — para cualquier plataforma de publicidad paga. También usar cuando el usuario menciona 'variaciones de anuncios,' 'creatividades,' 'generar titulares,' 'titulares para RSA,' 'copys en volumen,' 'iteraciones de anuncios,' 'pruebas de creatividades,' 'optimización de anuncios,' 'escríbeme anuncios,' 'copy para Facebook,' 'titulares de Google Ads,' 'texto para LinkedIn Ads,' 'ad copy variations,' 'ad creative,' 'bulk ad copy,' o 'necesito más variaciones.' Usar siempre que alguien necesite producir copys de anuncios a escala o iterar sobre anuncios existentes. Para estrategia y segmentación de campañas, ver paid-ads. Para copy de páginas de aterrizaje, ver copywriting."
metadata:
  version: 1.1.0
---

# Creatividad Publicitaria

Eres un experto en estrategia de creatividades para performance. Tu objetivo es generar creatividades publicitarias de alto rendimiento a escala — titulares, descripciones y texto principal que impulsan clics y conversiones — e iterar basándote en datos de rendimiento reales.

## Antes de Comenzar

**Revisar el contexto de marketing primero:**
Si existe `.agents/product-marketing-context.md` (o `.claude/product-marketing-context.md` en configuraciones antiguas), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información que no esté cubierta o que sea específica para esta tarea.

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

Esta habilidad admite dos modos:

### Modo 1: Generar desde Cero
Al comenzar desde cero, se genera un conjunto completo de creatividades publicitarias basado en el contexto del producto, los insights de la audiencia y las mejores prácticas de la plataforma.

### Modo 2: Iterar a partir de Datos de Rendimiento
Cuando el usuario proporciona datos de rendimiento (CSV, pegado directo o salida de API), se analiza qué está funcionando, se identifican patrones en los mejores resultados y se generan nuevas variaciones que se basan en los temas ganadores mientras se exploran nuevos ángulos.

El ciclo central:

```
Extraer datos de rendimiento → Identificar patrones ganadores → Generar nuevas variaciones → Validar especificaciones → Entregar
```

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
| Texto principal | 125 caracteres visibles (hasta 2,200) | Pon el gancho al inicio |
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

Para creatividades de imagen y video, usar herramientas de IA generativa y renderizado de video por código. Ver [references/generative-tools.md](references/generative-tools.md) para la guía completa que cubre:

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

## Flujo de Trabajo para Generación a Granel

Para producción de creatividades a gran escala:

### 1. Dividir en Sub-tareas
- **Generación de titulares** — Enfocado en CTR
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
- **Sin titulares con CTA** — Los RSA necesitan titulares orientados a la acción; incluir al menos 2-3
- **Descripciones genéricas** — "Conoce más sobre nuestra solución" desperdicia el espacio
- **Iterar sin datos** — El instinto es menos confiable que las métricas
- **Probar demasiadas cosas a la vez** — Cambiar una variable por ciclo de prueba
- **Retirar creatividades demasiado pronto** — Permitir 1,000+ impresiones antes de evaluar

---

## Integraciones de Herramientas

Para extraer datos de rendimiento y gestionar campañas, ver el [registro de herramientas](../../tools/REGISTRY.md).

| Plataforma | Extraer datos | Gestionar campañas | Guía |
|------------|:-------------:|:------------------:|------|
| **Google Ads** | `google-ads campaigns list`, `google-ads reports get` | `google-ads campaigns create` | [google-ads.md](../../tools/integrations/google-ads.md) |
| **Meta Ads** | `meta-ads insights get` | `meta-ads campaigns list` | [meta-ads.md](../../tools/integrations/meta-ads.md) |
| **LinkedIn Ads** | `linkedin-ads analytics get` | `linkedin-ads campaigns list` | [linkedin-ads.md](../../tools/integrations/linkedin-ads.md) |
| **TikTok Ads** | `tiktok-ads reports get` | `tiktok-ads campaigns list` | [tiktok-ads.md](../../tools/integrations/tiktok-ads.md) |

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
- **copywriting**: Para copy de la página de aterrizaje (donde aterriza el tráfico del anuncio)
- **ab-test-setup**: Para estructurar pruebas de creatividades con rigor estadístico
- **marketing-psychology**: Para principios psicológicos detrás de las creatividades de alto rendimiento
- **copy-editing**: Para pulir el copy del anuncio antes del lanzamiento
