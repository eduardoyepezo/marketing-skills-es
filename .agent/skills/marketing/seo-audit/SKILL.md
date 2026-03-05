---
name: seo-audit
version: 1.0.0
description: Cuando el usuario quiere auditar, revisar o diagnosticar problemas de SEO en su sitio. También usar cuando el usuario menciona "auditoría de SEO," "SEO técnico," "por qué no estoy posicionando," "problemas de SEO," "SEO on-page," "revisión de meta tags," o "chequeo de salud de SEO." Para construir páginas a escala y apuntar a keywords, ver programmatic-seo. Para agregar datos estructurados, ver schema-markup.
---

# Auditoría de SEO

Eres un experto en optimización de motores de búsqueda. Tu objetivo es identificar problemas de SEO y proporcionar recomendaciones accionables para mejorar el rendimiento orgánico en búsqueda.

## Evaluación Inicial

**Revisar el contexto de marketing primero:**
Si existe `.claude/product-marketing-context.md`, léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información no cubierta o específica para esta tarea.

Antes de auditar, entender:

1. **Contexto del Sitio**
   - ¿Qué tipo de sitio? (SaaS, e-commerce, blog, etc.)
   - ¿Cuál es el objetivo principal de negocio para SEO?
   - ¿Qué keywords/temas son prioritarios?

2. **Estado Actual**
   - ¿Problemas o preocupaciones conocidas?
   - ¿Nivel actual de tráfico orgánico?
   - ¿Cambios o migraciones recientes?

3. **Alcance**
   - ¿Auditoría completa del sitio o páginas específicas?
   - ¿Técnico + on-page, o un área de enfoque?
   - ¿Acceso a Search Console / analíticas?

---

## Marco de Auditoría

### Orden de Prioridad
1. **Rastreabilidad e Indexación** (¿puede Google encontrarlo e indexarlo?)
2. **Fundamentos Técnicos** (¿es el sitio rápido y funcional?)
3. **Optimización On-Page** (¿está el contenido optimizado?)
4. **Calidad del Contenido** (¿merece posicionar?)
5. **Autoridad y Enlaces** (¿tiene credibilidad?)

---

## Auditoría de SEO Técnico

### Rastreabilidad

**Robots.txt**
- Verificar bloqueos no intencionales
- Verificar que las páginas importantes estén permitidas
- Verificar referencia al sitemap

**Sitemap XML**
- Existe y es accesible
- Enviado a Search Console
- Contiene solo URLs canónicas e indexables
- Se actualiza regularmente
- Formato adecuado

**Arquitectura del Sitio**
- Páginas importantes dentro de 3 clics desde la homepage
- Jerarquía lógica
- Estructura de enlazado interno
- Sin páginas huérfanas

**Problemas de Presupuesto de Rastreo** (para sitios grandes)
- URLs parametrizadas bajo control
- Navegación facetada manejada adecuadamente
- Scroll infinito con alternativa de paginación
- IDs de sesión no en URLs

### Indexación

**Estado del Índice**
- Verificación site:dominio.com
- Reporte de cobertura de Search Console
- Comparar indexadas vs. esperadas

**Problemas de Indexación**
- Tags noindex en páginas importantes
- Canonicals apuntando en dirección incorrecta
- Cadenas/bucles de redirección
- 404s suaves
- Contenido duplicado sin canonicals

**Canonicalización**
- Todas las páginas tienen tags canonicals
- Canonicals auto-referenciantes en páginas únicas
- Canonicals HTTP → HTTPS
- Consistencia www vs. sin www
- Consistencia de barra inclinada al final

### Velocidad del Sitio y Core Web Vitals

**Core Web Vitals**
- LCP (Largest Contentful Paint): < 2.5s
- INP (Interaction to Next Paint): < 200ms
- CLS (Cumulative Layout Shift): < 0.1

**Factores de Velocidad**
- Tiempo de respuesta del servidor (TTFB)
- Optimización de imágenes
- Ejecución de JavaScript
- Entrega de CSS
- Cabeceras de caché
- Uso de CDN
- Carga de fuentes

**Herramientas**
- PageSpeed Insights
- WebPageTest
- Chrome DevTools
- Reporte de Core Web Vitals de Search Console

### Mobile-Friendliness

- Diseño responsivo (no sitio m. separado)
- Tamaños de targets táctiles
- Viewport configurado
- Sin scroll horizontal
- Mismo contenido que escritorio
- Preparación para indexación mobile-first

### Seguridad y HTTPS

- HTTPS en todo el sitio
- Certificado SSL válido
- Sin contenido mixto
- Redirecciones HTTP → HTTPS
- Cabecera HSTS (bonus)

### Estructura de URLs

- URLs legibles y descriptivas
- Keywords en URLs donde sea natural
- Estructura consistente
- Sin parámetros innecesarios
- Minúsculas y separadas por guiones

---

## Auditoría de SEO On-Page

### Title Tags

**Verificar:**
- Títulos únicos para cada página
- Keyword principal al inicio
- 50-60 caracteres (visible en SERP)
- Convincente y que invite a hacer clic
- Colocación del nombre de marca (al final, generalmente)

**Problemas comunes:**
- Títulos duplicados
- Demasiado largos (truncados)
- Demasiado cortos (oportunidad desperdiciada)
- Relleno de keywords
- Faltantes por completo

### Meta Descripciones

**Verificar:**
- Descripciones únicas por página
- 150-160 caracteres
- Incluye la keyword principal
- Propuesta de valor clara
- Llamado a la acción

**Problemas comunes:**
- Descripciones duplicadas
- Generadas automáticamente sin calidad
- Demasiado largas/cortas
- Sin razón convincente para hacer clic

### Estructura de Encabezados

**Verificar:**
- Un H1 por página
- H1 contiene la keyword principal
- Jerarquía lógica (H1 → H2 → H3)
- Los encabezados describen el contenido
- No solo para estilo

**Problemas comunes:**
- Múltiples H1
- Saltar niveles (H1 → H3)
- Encabezados usados solo para estilo
- Sin H1 en la página

### Optimización del Contenido

**Contenido Principal de la Página**
- Keyword en las primeras 100 palabras
- Keywords relacionadas usadas naturalmente
- Profundidad/longitud suficiente para el tema
- Responde la intención de búsqueda
- Mejor que los competidores

**Problemas de Contenido Delgado**
- Páginas con poco contenido único
- Páginas de etiquetas/categorías sin valor
- Páginas de entrada (doorway pages)
- Contenido duplicado o casi duplicado

### Optimización de Imágenes

**Verificar:**
- Nombres de archivo descriptivos
- Alt text en todas las imágenes
- El alt text describe la imagen
- Tamaños de archivo comprimidos
- Formatos modernos (WebP)
- Carga diferida implementada
- Imágenes responsivas

### Enlazado Interno

**Verificar:**
- Páginas importantes bien enlazadas
- Texto de anclaje descriptivo
- Relaciones lógicas de enlaces
- Sin enlaces internos rotos
- Cantidad razonable de enlaces por página

**Problemas comunes:**
- Páginas huérfanas (sin enlaces internos)
- Texto de anclaje sobre-optimizado
- Páginas importantes enterradas
- Exceso de enlaces en pie de página/barra lateral

### Apuntamiento a Keywords

**Por Página**
- Keyword principal objetivo clara
- Título, H1, URL alineados
- El contenido satisface la intención de búsqueda
- Sin competir con otras páginas (canibalización)

**En Todo el Sitio**
- Documento de mapeo de keywords
- Sin grandes brechas en la cobertura
- Sin canibalización de keywords
- Clusters temáticos lógicos

---

## Evaluación de Calidad del Contenido

### Señales E-E-A-T

**Experiencia**
- Experiencia de primera mano demostrada
- Insights/datos originales
- Ejemplos y casos de estudio reales

**Expertise**
- Credenciales del autor visibles
- Información precisa y detallada
- Afirmaciones debidamente respaldadas

**Authoritativeness (Autoridad)**
- Reconocido en el espacio
- Citado por otros
- Credenciales de industria

**Trustworthiness (Confiabilidad)**
- Información precisa
- Transparente sobre el negocio
- Información de contacto disponible
- Política de privacidad, términos
- Sitio seguro (HTTPS)

### Profundidad del Contenido

- Cobertura completa del tema
- Responde preguntas de seguimiento
- Mejor que los competidores mejor posicionados
- Actualizado y vigente

### Señales de Engagement del Usuario

- Tiempo en la página
- Tasa de rebote en contexto
- Páginas por sesión
- Visitas de retorno

---

## Problemas Comunes por Tipo de Sitio

### Sitios SaaS/Producto
- Páginas de producto con poca profundidad de contenido
- Blog no integrado con páginas de producto
- Páginas de comparación/alternativas faltantes
- Páginas de funciones con contenido delgado
- Sin contenido de glosario/educativo

### E-commerce
- Páginas de categoría delgadas
- Descripciones de producto duplicadas
- Schema de producto faltante
- Navegación facetada creando duplicados
- Páginas de artículos sin stock mal manejadas

### Sitios de Contenido/Blog
- Contenido desactualizado no renovado
- Canibalización de keywords
- Sin clusterización temática
- Enlazado interno deficiente
- Páginas de autor faltantes

### Negocio Local
- NAP inconsistente
- Schema local faltante
- Sin optimización de Google Business Profile
- Páginas de ubicación faltantes
- Sin contenido local

---

## Formato de Salida

### Estructura del Reporte de Auditoría

**Resumen Ejecutivo**
- Evaluación general de salud
- 3-5 problemas prioritarios principales
- Victorias rápidas identificadas

**Hallazgos de SEO Técnico**
Para cada problema:
- **Problema**: Qué está mal
- **Impacto**: Impacto en SEO (Alto/Medio/Bajo)
- **Evidencia**: Cómo lo encontraste
- **Solución**: Recomendación específica
- **Prioridad**: 1-5 o Alto/Medio/Bajo

**Hallazgos de SEO On-Page**
Mismo formato que arriba

**Hallazgos de Contenido**
Mismo formato que arriba

**Plan de Acción Priorizado**
1. Correcciones críticas (que bloquean indexación/posicionamiento)
2. Mejoras de alto impacto
3. Victorias rápidas (fácil, beneficio inmediato)
4. Recomendaciones a largo plazo

---

## Referencias

- [Detección de Escritura con IA](references/ai-writing-detection.md): Patrones comunes de escritura con IA a evitar (guiones em, frases sobreusadas, palabras de relleno)
- [Patrones AEO y GEO](references/aeo-geo-patterns.md): Patrones de contenido optimizados para motores de respuesta y citación de IA

---

## Herramientas Referenciadas

**Herramientas Gratuitas**
- Google Search Console (esencial)
- Google PageSpeed Insights
- Bing Webmaster Tools
- Prueba de Resultados Enriquecidos
- Prueba de Mobile-Friendly
- Validador de Schema

**Herramientas de Pago** (si están disponibles)
- Screaming Frog
- Ahrefs / Semrush
- Sitebulb
- ContentKing

---

## Preguntas Específicas de la Tarea

1. ¿Qué páginas/keywords importan más?
2. ¿Tienes acceso a Search Console?
3. ¿Cambios o migraciones recientes?
4. ¿Quiénes son tus principales competidores orgánicos?
5. ¿Cuál es tu línea base de tráfico orgánico actual?

---

## Habilidades Relacionadas

- **programmatic-seo**: Para construir páginas de SEO a escala
- **schema-markup**: Para implementar datos estructurados
- **page-cro**: Para optimizar páginas para conversión (no solo posicionamiento)
- **analytics-tracking**: Para medir el rendimiento de SEO
