# Referencia de Prospección Local SMB

Para cuando el usuario le vende a pequeños negocios locales — tiendas, gimnasios, restaurantes, salones, clínicas, servicios profesionales, contratistas, bienes raíces, estudios de fitness, consultorios dentales.

Adaptado y generalizado a partir del patrón local-client-prospector (discovery asistido por navegador + clasificación de estado de sitio web + puntuación de proximidad).

---

## Señales de ICP que Importan (rama Local SMB)

### Señales operacionales

- **Negocio activo** — Perfil de Negocio de Google actualizado, reseñas recientes, actualizaciones de horario recientes
- **Actividad reciente** — abierto ahora mismo, horario regular publicado, fotos recientes subidas por el dueño
- **Engagement del cliente** — el dueño responde reseñas, publica en redes sociales, calendario activo (para negocios de servicios)

### Señales de presencia online (el eje de calificación central de SMB)

La skill de referencia local-client-prospector usa el **estado del sitio web** como la calificación primaria — trasládala directamente. Cuatro clasificaciones:

| Estado | Definición | Resultado típico |
|--------|-----------|-----------------|
| **Sin sitio encontrado** | Sin sitio web independiente creíble tras búsqueda cruzada verificada | **Prospecto Hot** para servicio de web/marketing |
| **Solo redes sociales** | Solo Facebook, Instagram, WhatsApp, Linktree, portal de reservas, o página de marketplace — sin sitio independiente | **Prospecto Hot** para servicio de web/marketing |
| **Sitio débil** | Existe un sitio independiente pero está desactualizado, roto, muy pobre, no apto para móvil, o le falta un flujo claro de contacto/conversión | **Prospecto Warm** para servicio de refresh / reconstrucción |
| **Tiene sitio** | Existe un sitio independiente creíble y moderno | **Prospecto bajo** a menos que apliquen otras señales (ej. SEO pobre, diseño de conversión débil) |

### Señales de proximidad

- **Distancia** desde la ubicación o área de servicio del usuario
- **Densidad** — clusters de negocios similares en una zona = oportunidad de targeting de vecindario
- **Tiempo de viaje** — útil cuando el discovery en persona, instalación, o entrega de servicio es requerida

### Señales de decadencia

- Cerrado permanentemente (banner de Google Maps)
- Reseñas pausadas o listado de negocio reportado como cerrado
- Última actividad (reseña, post) hace más de 12 meses

---

## Fuentes de Discovery (rama Local SMB)

### Primarias

- **Google Maps** (navegador, manual) — busca "categoría cerca de [ubicación]" y recorre los resultados visibles. Verifica cruzadamente los detalles. No extraigas masivamente.
- **Yelp** — verificación secundaria; categorías complementarias
- **Bing Local / Apple Maps** — cobertura diferente en negocios más pequeños
- **Búsqueda de Páginas de Facebook** — muchos SMBs solo tienen Facebook

### Verificación cruzada

- **Sitio web propio del negocio** (si tiene)
- **Directorios de industria** (ej. Healthgrades para médico, OpenTable para restaurantes, Avvo para legal)
- **Listados de la Cámara de Comercio local**
- **Registros de negocios estatales** para estado de incorporación
- **Resultados de búsqueda de "[nombre del negocio] [ciudad]"** para descubrir presencia fuera de Maps

---

## Flujo de Investigación con Navegador

1. Abre un navegador y busca en Google Maps la categoría cerca de `base_location`
2. Construye una lista de candidatos a partir de resultados locales visibles, resultados de búsqueda, y directorios públicos
3. Para cada candidato, inspecciona fuentes públicas para completar los campos requeridos
4. Busca el nombre exacto del negocio más ciudad/pueblo para verificar si existe un sitio web independiente
5. Clasifica el estado del sitio web según la tabla de arriba
6. Marca la confianza: Alta (2+ fuentes), Media (1 fuente + evidencia consistente), Baja (incompleta/ambigua)

Cuando el usuario pida explícitamente subagentes Y los subagentes estén disponibles, divide a los candidatos en lotes sin superposición y pide a cada subagente que verifique solo el estado de sitio web/redes sociales/contacto. No uses subagentes para la búsqueda primaria si eso ralentiza el progreso.

### Opcional: verificación programática con Firecrawl o Browserbase

Una vez que tengas la URL del sitio web de un candidato (encontrada vía discovery manual en Maps/Yelp), puedes acelerar la clasificación de estado de sitio web accediendo a la URL programáticamente:

- **Firecrawl** para lecturas simples de "¿está vivo este sitio, es moderno, apto para móvil, tiene flujo de conversión?" — devuelve markdown limpio que puedes inspeccionar
- **Browserbase** cuando el sitio del candidato requiere renderizado JS, tiene un diálogo de consentimiento de cookies, o necesitas estado de sesión

**Línea estricta**: usa estas herramientas en la URL del negocio individual. **No** las apuntes a Google Maps, Yelp, o cualquier plataforma cuyos ToS prohíban la extracción masiva — el discovery se mantiene manual.

Ver [data-sources.md](data-sources.md) para detalles de configuración.

---

## Checklist de Calificación (rama Local SMB)

- [ ] El negocio está activo (reseñas o actividad reciente en los últimos 6 meses)
- [ ] La categoría coincide con la oferta de servicio del usuario
- [ ] Distancia / proximidad dentro del radio objetivo
- [ ] Estado del sitio web clasificado
- [ ] Teléfono o canal de contacto verificado
- [ ] Al menos una fuente cruzada confirma que el negocio opera en la dirección listada
- [ ] No es un duplicado / ubicación de cadena / categoría fuera de alcance
- [ ] No está cerrado permanentemente

---

## Puntuación de Leads (Local SMB)

Usa esta rúbrica simple (coincide con el patrón local-client-prospector):

| Puntaje | Criterios |
|-------|----------|
| **Hot** | Sin sitio encontrado O solo redes sociales + teléfono presente + negocio activo + dentro del radio objetivo |
| **Warm** | Sitio débil, presentación online pobre, o solo página de marketplace/reservas |
| **Cold** | Ya tiene buen sitio web O baja confianza |
| **Skip** | Cerrado, duplicado, fuera del radio, categoría irrelevante, o no es un prospecto de negocio |

---

## Columnas de Salida (rama Local SMB)

Tabla en chat (≤15 filas):

```
| Score | Business | Category | Area | Distance | Website status | Website/Social | Phone | Why it's a prospect | Confidence |
```

CSV:

```csv
score,business,category,area,distance_km,website_status,website_url,social_urls,phone,email,source_urls,why_prospect,confidence,verified_date,notes
```

Reglas:
- Mantén "Why it's a prospect" corto y accionable
- Usa `Not found` en lugar de dejar campos en blanco
- Incluye enlaces fuente con moderación, no todos
- Después de la tabla, agrega **Best first outreach targets** con los 3 leads principales y una razón práctica cada uno
- Si la confianza es baja, indica exactamente qué permanece incierto

---

## Selección de Top Outreach Targets (Local SMB)

Prioriza para los 3 leads Hot principales:

1. **Sin sitio / solo redes sociales + teléfono presente** = la oportunidad de servicio más clara
2. **Alto conteo de reseñas** = negocio activo, establecido, con clientes reales
3. **Reseñas respondidas por el dueño** = dueño comprometido = más probable que evalúe a un proveedor
4. **Alineación de industria con tu especialidad de servicio** le gana a un match de categoría genérico

Cada racional de top target debe ser una oración nombrando la brecha y la señal: "Sin sitio web independiente (verificado cruzadamente); 80+ reseñas de Google con respuestas del dueño; a 2 km del área objetivo."

---

## Notas de Cumplimiento (específicas de Local SMB)

La rama local es la más sensible al scraping de los tres motions. Específicamente:

- **Los Términos de Servicio de Google Maps** prohíben la extracción masiva. Trata las visitas con navegador como investigación, no como adquisición de datos.
- **No almacenes Place IDs completos de Google Maps en tu CRM** — el ToS limita el almacenamiento de datos de Maps.
- **Solo canales de contacto públicos del negocio**: teléfono publicado, formulario de contacto, email info@. No contactes a empleados individuales por sus canales personales.
- **El nombre del dueño/operador cuando está publicado en el sitio propio del negocio** está OK usarlo. Si solo lo obtuviste de LinkedIn, marca la fuente.

---

## Errores Comunes (Local SMB)

1. **Scraping masivo de Google Maps** — la forma más rápida de violar el ToS y perder el canal de investigación.
2. **Tratar los datos de Google Maps como verdad absoluta** — los listados se desactualizan. Verifica cruzadamente horario, estado y reseñas.
3. **Saltarse la verificación cruzada del estado del sitio web** — encontrar "sin sitio" en Maps no significa que no exista un sitio; haz una búsqueda web del nombre exacto antes de clasificar.
4. **Apuntar solo a los negocios más grandes** — ya están cubiertos por otros proveedores. Los SMBs de 2–5 empleados son la oportunidad desatendida.
5. **Outreach genérico a todos los leads Hot** — los SMBs locales responden mejor a outreach que nombra su brecha específica ("noté que tu menú no es visible en móvil") que a pitches genéricos.
6. **Descartar cadenas y franquicias como Skip** — a veces el franquiciado es el comprador y tiene autoridad de marketing local. Verifica antes de descartar.
