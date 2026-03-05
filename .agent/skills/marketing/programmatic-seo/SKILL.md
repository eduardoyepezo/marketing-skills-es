---
name: programmatic-seo
version: 1.0.0
description: Cuando el usuario quiere crear páginas orientadas a SEO a escala usando plantillas y datos. También usar cuando el usuario menciona "SEO programático," "páginas de plantilla," "páginas a escala," "páginas de directorio," "páginas de ubicación," "páginas de [keyword] + [ciudad]," "páginas de comparación," "páginas de integración," o "construir muchas páginas para SEO." Para auditar problemas de SEO existentes, ver seo-audit.
---

# SEO Programático

Eres un experto en SEO programático—construir páginas optimizadas para SEO a escala usando plantillas y datos. Tu objetivo es crear páginas que posicionen, proporcionen valor y eviten penalizaciones por contenido delgado.

## Evaluación Inicial

**Revisar el contexto de marketing primero:**
Si existe `.claude/product-marketing-context.md`, léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información no cubierta o específica para esta tarea.

Antes de diseñar una estrategia de SEO programático, entender:

1. **Contexto de Negocio**
   - ¿Cuál es el producto/servicio?
   - ¿Quién es la audiencia objetivo?
   - ¿Cuál es el objetivo de conversión para estas páginas?

2. **Evaluación de Oportunidad**
   - ¿Qué patrones de búsqueda existen?
   - ¿Cuántas páginas potenciales?
   - ¿Cuál es la distribución de volumen de búsqueda?

3. **Panorama Competitivo**
   - ¿Quién posiciona para estos términos ahora?
   - ¿Cómo se ven sus páginas?
   - ¿Puedes competir de manera realista?

---

## Principios Centrales

### 1. Valor Único por Página
- Cada página debe proporcionar valor específico para esa página
- No solo variables intercambiadas en una plantilla
- Maximizar el contenido único—cuanto más diferenciado, mejor

### 2. Los Datos Propietarios Ganan
Jerarquía de defensibilidad de datos:
1. Propietario (lo creaste tú)
2. Derivado del producto (de tus usuarios)
3. Generado por usuarios (tu comunidad)
4. Licenciado (acceso exclusivo)
5. Público (cualquiera puede usar—el más débil)

### 3. Estructura de URL Limpia
**Siempre usar subcarpetas, no subdominios**:
- Bueno: `tusitio.com/plantillas/curriculum/`
- Malo: `plantillas.tusitio.com/curriculum/`

### 4. Genuina Coincidencia de Intención de Búsqueda
Las páginas deben realmente responder lo que las personas están buscando.

### 5. Calidad sobre Cantidad
Mejor tener 100 páginas excelentes que 10,000 delgadas.

### 6. Evitar Penalizaciones de Google
- Sin páginas de entrada (doorway pages)
- Sin relleno de palabras clave
- Sin contenido duplicado
- Utilidad genuina para los usuarios

---

## Los 12 Playbooks (Descripción General)

| Playbook | Patrón | Ejemplo |
|----------|---------|---------| 
| Plantillas | "[Tipo] plantilla" | "plantilla de currículum" |
| Curación | "mejores [categoría]" | "mejores constructores de sitios web" |
| Conversiones | "[X] a [Y]" | "$10 USD a GBP" |
| Comparaciones | "[X] vs [Y]" | "webflow vs wordpress" |
| Ejemplos | "ejemplos de [tipo]" | "ejemplos de landing pages" |
| Ubicaciones | "[servicio] en [ubicación]" | "dentistas en Madrid" |
| Personas | "[producto] para [audiencia]" | "crm para bienes raíces" |
| Integraciones | "integración [producto A] [producto B]" | "integración slack asana" |
| Glosario | "qué es [término]" | "qué es pSEO" |
| Traducciones | Contenido en múltiples idiomas | Contenido localizado |
| Directorio | "herramientas de [categoría]" | "herramientas de redacción con IA" |
| Perfiles | "[nombre de entidad]" | "ceo de stripe" |

**Para implementación detallada de playbook**: Ver [references/playbooks.md](references/playbooks.md)

---

## Elegir Tu Playbook

| Si tienes... | Considera... |
|----------------|-------------|
| Datos propietarios | Directorios, Perfiles |
| Producto con integraciones | Integraciones |
| Producto de diseño/creativo | Plantillas, Ejemplos |
| Audiencia multi-segmento | Personas |
| Presencia local | Ubicaciones |
| Producto de herramienta o utilidad | Conversiones |
| Contenido/experiencia | Glosario, Curación |
| Panorama de competidores | Comparaciones |

Puedes combinar múltiples playbooks (ej., "Mejores espacios de coworking en Barcelona").

---

## Marco de Implementación

### 1. Investigación de Patrones de Palabras Clave

**Identificar el patrón:**
- ¿Cuál es la estructura repetitiva?
- ¿Cuáles son las variables?
- ¿Cuántas combinaciones únicas existen?

**Validar la demanda:**
- Volumen de búsqueda agregado
- Distribución de volumen (head vs. long tail)
- Dirección de tendencia

### 2. Requisitos de Datos

**Identificar fuentes de datos:**
- ¿Qué datos poblará cada página?
- ¿Es de primera parte, scrapeado, licenciado, público?
- ¿Cómo se actualiza?

### 3. Diseño de Plantilla

**Estructura de página:**
- Encabezado con palabra clave objetivo
- Intro único (no solo variables intercambiadas)
- Secciones impulsadas por datos
- Páginas relacionadas / enlaces internos
- CTAs apropiados para la intención

**Asegurar unicidad:**
- Cada página necesita valor único
- Contenido condicional basado en datos
- Insights/análisis originales por página

### 4. Arquitectura de Enlazado Interno

**Modelo hub y spoke:**
- Hub: Página de categoría principal
- Spokes: Páginas programáticas individuales
- Cross-links entre spokes relacionados

**Evitar páginas huérfanas:**
- Cada página accesible desde el sitio principal
- Sitemap XML para todas las páginas
- Breadcrumbs con datos estructurados

### 5. Estrategia de Indexación

- Priorizar patrones de alto volumen
- Noindex para variaciones muy delgadas
- Gestionar el presupuesto de rastreo cuidadosamente
- Sitemaps separados por tipo de página

---

## Controles de Calidad

### Lista de Verificación Pre-Lanzamiento

**Calidad del contenido:**
- [ ] Cada página proporciona valor único
- [ ] Responde la intención de búsqueda
- [ ] Legible y útil

**SEO técnico:**
- [ ] Títulos y meta descripciones únicos
- [ ] Estructura de encabezados adecuada
- [ ] Schema markup implementado
- [ ] Velocidad de página aceptable

**Enlazado interno:**
- [ ] Conectado a la arquitectura del sitio
- [ ] Páginas relacionadas enlazadas
- [ ] Sin páginas huérfanas

**Indexación:**
- [ ] En el sitemap XML
- [ ] Rastreable
- [ ] Sin noindex conflictivo

### Monitoreo Post-Lanzamiento

Rastrear: Tasa de indexación, Posicionamiento, Tráfico, Engagement, Conversión

Vigilar: Advertencias de contenido delgado, Caídas de ranking, Acciones manuales, Errores de rastreo

---

## Errores Comunes

- **Contenido delgado**: Solo intercambiar nombres de ciudades en contenido idéntico
- **Canibalización de palabras clave**: Múltiples páginas apuntando a la misma keyword
- **Sobre-generación**: Crear páginas sin demanda de búsqueda
- **Mala calidad de datos**: Información desactualizada o incorrecta
- **Ignorar UX**: Las páginas existen para Google, no para los usuarios

---

## Formato de Salida

### Documento de Estrategia
- Análisis de oportunidades
- Plan de implementación
- Directrices de contenido

### Plantilla de Página
- Estructura de URL
- Plantillas de título/meta
- Esquema de contenido
- Schema markup

---

## Preguntas Específicas de la Tarea

1. ¿Qué patrones de palabras clave estás apuntando?
2. ¿Qué datos tienes (o puedes adquirir)?
3. ¿Cuántas páginas estás planeando?
4. ¿Cómo es la autoridad de tu sitio?
5. ¿Quién posiciona actualmente para estos términos?
6. ¿Cuál es tu stack técnico?

---

## Habilidades Relacionadas

- **seo-audit**: Para auditar páginas programáticas después del lanzamiento
- **schema-markup**: Para agregar datos estructurados
- **competitor-alternatives**: Para marcos de páginas de comparación
