# Apple App Store — Specs y Guías Oficiales

Todos los datos son de developer.apple.com a marzo de 2026.

## Límites de Caracteres

| Campo                       | Límite               | ¿Se Indexa para Búsqueda? | Notas                                                    |
| ----------------------------- | --------------------- | --------------------------- | -------------------------------------------------------- |
| Nombre de la App               | 30 caracteres (mín. 2) | Sí                           | Debe ser único; sin marcas registradas, nombres de competidores, precios |
| Subtítulo                      | 30 caracteres          | Sí                           | Sin afirmaciones no verificables                          |
| Keywords                       | 100 bytes              | Sí (oculto)                  | Comas, sin espacios entre términos                        |
| Descripción                    | 4,000 caracteres       | **No**                       | Solo texto plano, sin HTML                                 |
| Texto Promocional              | 170 caracteres         | **No** (confirmado por Apple) | Actualizable sin nueva versión                             |
| Novedades                      | 4,000 caracteres       | No                           | Requerido para todas las versiones después de la primera   |
| Nombre de IAP                  | 35 caracteres          | Sí                           | Aparece en búsqueda                                        |
| Descripción de IAP              | 55 caracteres          | No                           |                                                            |
| Nombre de Evento Dentro de la App | 30 caracteres        | Sí                           | Se requiere formato de título                              |
| Desc. Corta de Evento Dentro de la App | 50 caracteres  | Sí                           | Formato de oración                                          |
| Desc. Larga de Evento Dentro de la App | 120 caracteres | No                           | Formato de oración                                          |

**El campo de keywords es de 100 bytes, no 100 caracteres.** Los scripts no latinos
(árabe, chino, japonés, coreano) usan 2-3 bytes por carácter, reduciendo
significativamente la cantidad efectiva de keywords.

## Specs de Screenshots

| Dispositivo        | ¿Requerido?    | Cantidad | Dimensiones (vertical)     |
| -------------------- | --------------- | -------- | --------------------------- |
| iPhone 6.9"           | **Requerido**   | 1-10     | 1260 x 2736                  |
| iPad 13"              | **Requerido**   | 1-10     | 2064 x 2752                  |
| Mac                   | Si aplica       | 1-10     | Hasta 2880 x 1800 (16:10)    |
| Apple Watch           | Si aplica       | 1-10     | Varía según el modelo         |
| Apple TV              | Si aplica       | 1-10     | 1920 x 1080 o 3840 x 2160    |
| Apple Vision Pro      | Si aplica       | 1-10     | 3840 x 2160                  |

- Formatos: JPEG, PNG
- Apple auto-escala desde los tamaños base requeridos a dispositivos más pequeños

## Specs del Video de Vista Previa de la App

- **Cantidad:** Hasta 3 por app
- **Duración:** 15-30 segundos
- **Tamaño máximo de archivo:** 500 MB
- **Códecs:** H.264 (10-12 Mbps, hasta 30fps) o ProRes 422 HQ
- **Audio:** Estéreo, 256 kbps AAC o PCM, 44.1/48 kHz
- **Formatos:** .mov, .m4v, .mp4
- **Comportamiento:** Autoplay silenciado en la página del producto (iOS 11+)

## Custom Product Pages (CPPs)

- **Máximo:** 70 páginas adicionales (más 1 por defecto)
- **Personalizable:** Screenshots, texto promocional, app previews, deep links (iOS 18+)
- **Keywords:** Cada combinación de keywords debe ser única para una sola CPP
- **Revisión:** Se envía a App Review de forma independiente de las actualizaciones de la app
- **Búsqueda orgánica:** Las CPPs aparecen en resultados de búsqueda orgánica desde julio de 2025
- **Rendimiento:** +2.5 puntos porcentuales de conversión en promedio vs. el default

## Product Page Optimization (Pruebas A/B)

- **Tratamientos:** Hasta 3 vs. el original
- **Se puede probar:** Íconos de la app, screenshots, videos de vista previa
- **NO se puede probar:** Título, subtítulo, descripción, keywords
- **Pruebas concurrentes:** 1 por app
- **Duración máxima:** 90 días
- **Restricción de ícono:** Todas las variantes de ícono deben estar en el binario publicado de la app
- **Confianza:** Apple recomienda un umbral del 90% (método bayesiano)
- **No se puede modificar** una prueba una vez iniciada

## Eventos Dentro de la App

- **Máximo aprobado:** 15 en App Store Connect a la vez
- **Máximo publicado:** 10 en el App Store simultáneamente
- **Duración máxima:** 31 días por evento
- **Promoción previa al evento:** Hasta 14 días antes del inicio
- **Tipos de insignia:** Challenge, Competition, Live Event, Major Update, New Season, Premiere, Special Event

**Imagen de tarjeta del evento:** 16:9, mín. 1920x1080, máx. 3840x2160
**Imagen de detalles del evento:** 9:16, mín. 1080x1920, máx. 2160x3840

**No adecuado para:** Tareas diarias repetitivas, promociones de precio sin contenido nuevo, campañas generales de awareness.

## Ratings y Reviews

- **SKStoreReviewController:** Máximo 3 prompts por período de 365 días
- El sistema controla la frecuencia de aparición (puede mostrar menos de 3)
- No usar botones personalizados para pedir reviews
- Los desarrolladores pueden responder a todos los reviews en App Store Connect
- El rating resumen es específico por territorio

## Triggers de Rechazo de Metadata (Guías de Revisión de App Review)

| Guía      | Trigger de Rechazo                                                         |
| ---------- | --------------------------------------------------------------------------- |
| 2.3.1      | Funciones ocultas, marketing engañoso, precios falsos                        |
| 2.3.2      | No revelar IAPs en la descripción/screenshots                                |
| 2.3.3      | Screenshots que no muestran la app en uso (solo splash/login)                |
| 2.3.4      | Videos de vista previa que usan contenido ajeno a la app                     |
| 2.3.5      | Categoría incorrecta seleccionada                                             |
| 2.3.7      | Keyword stuffing: marcas registradas, nombres de competidores, precios, términos irrelevantes |
| 2.3.8      | Metadata no apropiada para todas las audiencias (debe estar clasificado 4+)   |
| 2.3.10     | Nombres/imágenes de otras plataformas (Android, etc.) en la metadata          |
| 2.3.12     | "Novedades" genérico para cambios significativos                              |
| 2.3.13     | Metadata inexacta de eventos dentro de la app                                 |

Fuentes: developer.apple.com/app-store/product-page/,
developer.apple.com/app-store/search/,
developer.apple.com/app-store/review/guidelines/
