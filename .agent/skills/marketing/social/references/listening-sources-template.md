# Fuentes de Listening — Plantilla

Copia este archivo a `.agents/listening-sources.md` en tu proyecto (o `.claude/listening-sources.md`) y llena los corchetes. Claude lo lee al correr el [flujo de listening](listening.md).

Elimina las secciones que no uses. Mantén esto corto y actualizado — fuentes desactualizadas son peores que no tener fuentes.

---

## Qué Estamos Escuchando

**Marca / producto:** [Nombre de tu producto]
**Categoría:** [p. ej., "asistente de escritura con IA", "GUI de Postgres"]
**Objetivo:** [p. ej., "encontrar personas cambiándose de Notion", "hacer engagement con fundadores de SaaS B2B de 50-200 empleados"]

## ICP (para el scoring)

Usado por la [rúbrica de scoring](listening.md#rúbrica-de-scoring) para evaluar el fit con el ICP.

- **Rol:** [p. ej., "fundador, head of marketing, marketing ops lead"]
- **Etapa de la empresa:** [p. ej., "SaaS de seed a Series B, 10-200 empleados"]
- **Industria:** [p. ej., "B2B SaaS, infra, devtools"]
- **Señales de que es un buen fit:** [p. ej., "escribe sobre GTM, corre anuncios pagados, recién levantó una ronda"]

---

## Cuentas Objetivo

Haz engagement con **cada** post relevante de estas cuentas. Mantén esta lista en un máximo de 20-50.

### LinkedIn (manejado por navegador — usa dev-browser para ver el feed)
- [Nombre] — `linkedin.com/in/handle`
- [Nombre] — `linkedin.com/in/handle`

### X / Twitter (manejado por navegador)
- [@handle]
- [@handle]

### Reddit
- u/[username]
- u/[username]

### Bluesky
- [handle.bsky.social]

### Blogs / Newsletters (RSS)
- [Nombre] — `https://example.com/feed/`
- [Nombre] — `https://example.substack.com/feed`

### Canales de YouTube (RSS)
- [Nombre] — ID de canal `UCxxxxxxxx`

---

## Keywords (señales de intención)

Búsqueda en todas las plataformas. Claude ejecuta estas a través de Reddit, HN, Bluesky en el [loop diario](listening.md#el-loop-diario-de-triage).

### Alta intención (alguien comprando o cambiando)
- `"alternative to [competidor]"`
- `"looking for a [categoría] tool"`
- `"recommend a [categoría]"`
- `"switching from [competidor]"`
- `"frustrated with [competidor]"`

### Señales de problema (alguien con dolor)
- `"[categoría] is so [bad/hard/expensive]"`
- `"why is [categoría] [problema]"`
- `"hate [punto de dolor]"`

### Menciones de marca
- `"[tu marca]"`
- `"[error ortográfico de tu marca]"`
- `"[tu dominio]"`

### Menciones de competidores (monitorea por lenguaje de cambio)
- `"[competidor 1]"`
- `"[competidor 2]"`

---

## Subreddits

Extraídos vía la API JSON de Reddit en el loop diario.

- r/SaaS
- r/Entrepreneur
- r/[tu nicho, p. ej., "marketing", "devtools"]
- r/[comunidad adyacente]

---

## Búsquedas Guardadas (manual / manejado por navegador)

URLs que Claude abre vía dev-browser para escanear.

### LinkedIn Sales Navigator
- [Nombre de la búsqueda] — `https://linkedin.com/sales/search/people?...`

### LinkedIn (regular)
- Hashtag de posts — `https://linkedin.com/feed/hashtag/yourtopic/`

### Búsqueda avanzada de X
- [Nombre de la búsqueda] — `https://x.com/search?q=...&f=live`

---

## No Interactuar

Ahórrate el arrepentimiento.

- Cuentas conocidas por hacer dunking de mala fe: [@handle], [@handle]
- Marcas / competidores bloqueados que harán captura de pantalla: [lista]
- Temas a evitar: [política, [las opiniones fuertes de tu fundador], etc.]

---

## Notas para Claude

- Cuando se pida "el top 10 de hoy," muestra el output en el formato definido en [listening.md](listening.md#el-loop-diario-de-triage)
- Para LinkedIn y X, usa dev-browser con la sesión persistente (el usuario ya inició sesión)
- Para todo lo demás, usa las recetas curl en [listening.md](listening.md#fuentes-y-tooling-ligero-recetas-curl)
- Lookback por defecto: 24h. El usuario puede cambiarlo.
- Siempre pregunta antes de publicar — muestra borradores, el usuario aprueba y publica manualmente
