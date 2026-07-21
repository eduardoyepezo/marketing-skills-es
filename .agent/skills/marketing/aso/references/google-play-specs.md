# Google Play Store — Specs y Guías Oficiales

Todos los datos son de support.google.com y developer.android.com a marzo de 2026.

## Límites de Caracteres

| Campo               | Límite       | ¿Se Indexa?             | Notas                                     |
| --------------------- | ------------ | ------------------------- | -------------------------------------------- |
| Título de la App       | 30 caracteres | Sí (señal más fuerte)     | Reducido de 50 en septiembre de 2021         |
| Descripción Corta       | 80 caracteres | Sí                         | Visible sin necesidad de expandir            |
| Descripción Completa    | 4,000 caracteres | **Sí (fuertemente)**  | El NLP de Google indexa todo el texto        |
| Nombre del Desarrollador | 64 caracteres | Parcial                   | Mismas restricciones de emoji/mayúsculas que el título |

## Prohibido en Metadata (aplicado desde septiembre de 2021)

**Título, Ícono, Nombre del Desarrollador:**

- Emojis, emoticones, caracteres especiales repetidos
- TODO EN MAYÚSCULAS (a menos que sea marca registrada)
- Afirmaciones de desempeño: "top," "best," "#1," "free," "no ads"
- Desempeño o respaldo engañoso de la tienda
- Llamadas a la acción: "update now," "download now"

**Descripción Corta:**

- Las mismas afirmaciones de desempeño que el título
- Llamadas a la acción
- Testimonios sin atribución

**Screenshots, Feature Graphic, Video:**

- Frases promocionales con vigencia limitada
- Llamadas a la acción ("Download now," "Play now")
- Deben mostrar auténticamente la funcionalidad de la app

## Specs de Screenshots

| Dispositivo   | Mín.  | Máx.  | Aspect Ratio  | Resolución Mín. | Lado Largo Máx. |
| -------------- | ----- | ----- | -------------- | ----------------- | ------------------ |
| Teléfono       | **2** | **8** | 9:16 o 16:9    | 320px cualquier lado | 3,840px         |
| Tablet 7"      | 4     | 8     | 9:16 o 16:9    | 1,080px lado corto | 7,680px           |
| Tablet 10"     | 4     | 8     | 9:16 o 16:9    | 1,080px lado corto | 7,680px           |
| Chromebook     | 4     | 8     | 9:16 o 16:9    | 1,080px lado corto | 7,680px           |
| Wear OS        | 1     | 8     | **1:1**        | 384x384            | 3,840px           |
| Android TV     | 1     | 8     | **16:9**       | 1,920x1,080        | 3,840px           |

- **Tamaño recomendado para teléfono:** 1080x1920 (vertical)
- **Formato:** JPEG o PNG de 24 bits (sin alfa)
- **Tamaño máximo de archivo:** 8 MB cada uno

**Nota:** El máximo de Google Play es 8 screenshots por dispositivo, no 10 como Apple.

## Feature Graphic

- **Dimensiones:** 1024 x 500 px (exacto, requerido)
- **Formato:** JPEG o PNG de 24 bits (sin alfa)
- Se muestra en la parte superior de la ficha y en posicionamientos destacados

## Ícono de la App

- **Dimensiones:** 512 x 512 px
- **Formato:** PNG de 32 bits (con alfa)
- **Tamaño máximo de archivo:** 1,024 KB
- **Forma:** Cuadrado completo (Google aplica automáticamente un radio de esquina del 30%)
- **Prohibido:** Afirmaciones de ranking, conteos de descargas, texto de ofertas, emoji

## Video de Vista Previa

- **Formato:** URL de YouTube (pública o no listada)
- **Duración:** 30 segundos a 2 minutos recomendado
- Sin anuncios, sin monetización, debe ser embebible, no restringido por edad
- **NO hace autoplay** (solo ~6% de los visitantes toca play)

## Store Listing Experiments (Pruebas A/B)

- **Variantes:** Hasta 3 por experimento (más el control)
- **Elementos que se pueden probar:** Ícono, feature graphic, screenshots, video, descripción corta, descripción completa
- **Concurrencia:** No se puede correr más de 1 experimento de gráficos por defecto simultáneamente
- **Audiencia:** Solo usuarios de Google Play con sesión iniciada
- **Métricas:** Primeros instaladores + primeros instaladores retenidos (retención a 1 día)
- **Duración:** Correr al menos 7 días (variación entre semana/fin de semana)
- **Localizado:** Probar en hasta 5 idiomas simultáneamente

## Custom Store Listings

- **Máximo:** 50 por app (100 para Play partners)
- **Personalizable:** Título, descripción corta/completa, ícono, screenshots, feature graphic, video
- **Targeting:** País/región, pre-registro, estado de instalación, campañas de Google Ads, usuarios inactivos/perdidos (28+ días)
- **Novedad de 2025:** Gemini AI genera automáticamente texto para CSLs en Play Console

## Promotional Content (LiveOps)

| Tipo               | Descripción                          | Duración               |
| -------------------- | -------------------------------------- | ------------------------- |
| Ofertas               | Descuentos, artículos gratis, paquetes | Hasta 28 días              |
| Eventos               | Eventos dentro de la app con tiempo límite | Debe tener límite de tiempo |
| Actualización Mayor    | Funciones nuevas significativas        | Máximo 1 semana            |
| Crossover (juegos)    | Colaboración cruzada entre juegos/IP   | Varía                      |

- Enviar con **4+ días** de anticipación (revisión estándar)
- Enviar con **14+ días** de anticipación para solicitudes de featuring
- **Impacto:** "Más del doble de adquisiciones desde explorar durante el featuring" (oficial de Google)

## Android Vitals — Umbrales de Ranking

Las apps que exceden estos umbrales obtienen **visibilidad reducida** en búsqueda y recomendaciones.

| Métrica                          | Umbral General | Umbral por Dispositivo |
| ----------------------------------- | ---------------- | ------------------------- |
| Tasa de Crash Percibida por el Usuario | **1.09%**     | 8%                         |
| Tasa de ANR Percibida por el Usuario   | **0.47%**     | 8%                         |
| Wake Locks Parciales Excesivos         | 5%             | N/A                        |

**Consecuencias:** Visibilidad reducida en búsqueda, etiquetas de advertencia en la ficha, alertas de calidad a los usuarios antes de instalar.
**Recuperación:** Google verifica diariamente usando un promedio móvil de 28 días.

## Ranking de Búsqueda — Factores Oficiales

Google confirma que estos afectan el ranking:

1. **Relevancia de metadata** — El título tiene el mayor peso. El NLP escanea título + desc. corta + desc. completa.
2. **Calidad de la app** — Android Vitals (tasas de crash/ANR)
3. **Ratings y reviews** — Rating en estrellas + texto de review. El 85% de las apps destacadas tienen 4.0+
4. **Volumen y velocidad de instalación** — Total de instalaciones + frecuencia diaria/semanal
5. **Engagement y retención** — Frecuencia de sesión, duración, tasas de retención
6. **Frecuencia de actualización** — Actualizaciones regulares indican mantenimiento activo
7. **Localización** — Adaptación regional de keywords/visuales. El 59% de las apps de EE.UU. localiza sus títulos.

Fuentes: support.google.com/googleplay/android-developer/answer/4448378,
support.google.com/googleplay/android-developer/answer/9898842,
developer.android.com/topic/performance/vitals
