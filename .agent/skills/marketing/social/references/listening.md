# Social Listening y Triage de Engagement

Cómo descubrir los posts correctos para hacer engagement cada día — en lugar de hacer scroll al azar. El objetivo es una lista corta y evaluable ("aquí están tus 10 mejores posts para comentar") en lugar de un feed abierto.

## Contenido
- Cuándo usar esto
- El loop diario de triage
- Rúbrica de scoring
- Niveles de calidad de comentario
- Fuentes y tooling ligero (recetas curl)
- Notas por plataforma
- Flujos de trabajo comunes

---

## Cuándo Usar Esto

Usa social listening cuando el objetivo sea **comentar y construir relaciones**, no publicar. Pedidos típicos:
- "Dame los 10 mejores posts para comentar hoy"
- "¿Quién se está quejando de [competidor] ahora mismo?"
- "Encuentra personas que están buscando una herramienta como la mía"
- "Muéstrame los posts de mis 20 cuentas objetivo en las últimas 24h"
- "¿Cómo está la conversación sobre [tema] esta semana?"

Si el usuario quiere **crear** contenido, usa el resto de la skill social. El listening alimenta la creación (descubre ángulos, lenguaje, objeciones), pero el output es diferente.

---

## El Loop Diario de Triage

Un loop repetible de 20 minutos que el usuario (o tú, en su nombre) puede correr cada mañana.

1. **Extraer** — obtén posts nuevos de las fuentes definidas (cuentas objetivo, keywords, subreddits, hashtags). Ver [tooling](#fuentes-y-tooling-ligero-recetas-curl).
2. **Filtrar** — descarta todo lo de más de 24h, de baja señal, o fuera de tema.
3. **Puntuar** — aplica la [rúbrica](#rúbrica-de-scoring). Quédate con el top 10.
4. **Redactar** — para cada uno, redacta un comentario acorde al nivel del post.
5. **Publicar** — el usuario revisa, edita, publica. Marca cuáles realmente salieron en vivo.
6. **Registrar** — lleva registro de qué comentaste y qué obtuvo respuestas. Este es tu dataset del loop de engagement.

Formato de output que Claude debe producir:

```
TOP 10 POSTS — 2026-06-05

1. [Score 9/10] @autor — LinkedIn — hace 2h
   "Acabamos de lanzar X y el equipo está encantado…"
   Por qué: encaja con el ICP (B2B SaaS, 50–200 empleados), señal de intención de compra
   Comentario sugerido: [borrador]
   Link: https://…
```

---

## Rúbrica de Scoring

Puntúa cada post de 1–10 en cinco dimensiones, luego suma y ordena.

| Dimensión | Qué mide | Peso |
|-----------|------------------|--------|
| **Fit con el ICP** | ¿El autor es tu cliente objetivo / influenciador? | 2x |
| **Señal de intención** | ¿Está expresando un problema, preguntando, o comprando? | 2x |
| **Potencial de alcance** | ¿El post está ganando tracción (likes/comentarios en aumento)? | 1x |
| **Oportunidad de comentario** | ¿Puedes decir algo genuinamente útil, no genérico? | 2x |
| **Recencia** | Publicado en las últimas 1–4h (los comentarios tempranos ganan, especialmente en LinkedIn) | 1x |

**Ejemplos de señal de intención (alto valor):**
- "Busco una herramienta que haga X"
- "¿Por qué [categoría] es tan doloroso?"
- "Recién nos cambiamos de [competidor] porque…"
- "¿Alguien usa [competidor]? ¿Vale la pena?"
- Una queja sobre un competidor conocido

**Descarta si alguna de estas es cierta:**
- El autor no es ICP ni es un influenciador
- El post tiene más de 24h y ya tiene 50+ comentarios (tu comentario se entierra)
- Post motivacional genérico/AI-slop
- Hilo de autopromoción donde los comentarios no obtienen alcance
- No puedes agregar nada más allá de "¡Gran post!"

---

## Niveles de Calidad de Comentario

Ajusta el comentario al post. No gastes un borrador de nivel 1 en una oportunidad de nivel 3.

**Nivel 1 — Constructor de relaciones (cuentas objetivo, ICP, alta intención)**
- Agrega un insight específico o un contraejemplo
- Haz referencia a tu propia experiencia con detalles (números, nombres, resultados)
- Haz una pregunta de seguimiento reflexiva que invite a responder
- Extensión: 2–4 oraciones, sin link

**Nivel 2 — Jugada de visibilidad (post de alto alcance, tema adyacente)**
- Agrega un insight agudo en una sola oración
- Patrón: "De acuerdo — y la parte que la mayoría se pierde es [X]"
- Extensión: 1–2 oraciones

**Nivel 3 — Toque ligero (mantenimiento de relación)**
- Reacción específica, no "Me encanta esto"
- Cita una línea específica y reacciona a ella
- Extensión: 1 oración

**Nunca:** "¡Gran post!", solo emoji, "+1", muletillas de LinkedIn como "Esto es oro 🔥"

---

## Fuentes y Tooling Ligero (recetas curl)

Estos son endpoints JSON públicos — no requieren autenticación. Ejecútalos desde bash, canalízalos a `jq`, y Claude puede parsear el output para puntuar y redactar comentarios.

**Requiere:** `jq` (la mayoría de las recetas) y `xmllint` (solo RSS). Instala una vez:
```bash
# macOS
brew install jq
# xmllint viene con macOS; en Linux: apt install libxml2-utils
```

### Reddit (gratis, scriptable)

**Posts nuevos en un subreddit:**
```bash
curl -s -A "listening/1.0" \
  "https://www.reddit.com/r/SaaS/new.json?limit=25" \
  | jq '.data.children[].data | {title, author, url: ("https://reddit.com"+.permalink), score, num_comments, created_utc, selftext: (.selftext | .[0:300])}'
```

**Buscar en Reddit por keyword (último día, ordenado por nuevo):**
```bash
curl -s -A "listening/1.0" \
  "https://www.reddit.com/search.json?q=KEYWORD&sort=new&t=day&limit=25" \
  | jq '.data.children[].data | {subreddit, title, url: ("https://reddit.com"+.permalink), author, score, created_utc}'
```

Reemplaza `KEYWORD` por cosas como `"alternative to notion"`, `"recommend a crm"`, nombres de tus competidores, o tu propia marca para menciones. Usa comillas alrededor de frases de varias palabras.

### Hacker News (búsqueda Algolia)

**Historias recientes que mencionan una keyword (últimas 24h):**
```bash
SINCE=$(($(date +%s) - 86400))
curl -s "https://hn.algolia.com/api/v1/search_by_date?query=KEYWORD&tags=story&numericFilters=created_at_i>${SINCE}" \
  | jq '.hits[] | {title, url, author, points, num_comments, created_at, story_id: .objectID, hn_url: ("https://news.ycombinator.com/item?id="+.objectID)}'
```

**Comentarios recientes que mencionan una keyword:**
```bash
curl -s "https://hn.algolia.com/api/v1/search_by_date?query=KEYWORD&tags=comment&numericFilters=created_at_i>${SINCE}" \
  | jq '.hits[] | {author, comment_text, story_title, hn_url: ("https://news.ycombinator.com/item?id="+.objectID)}'
```

### Bluesky (gratis, API pública)

**Buscar posts por keyword:**
```bash
curl -s "https://public.api.bsky.app/xrpc/app.bsky.feed.searchPosts?q=KEYWORD&limit=25&sort=latest" \
  | jq '.posts[] | {author: .author.handle, text: .record.text, likes: .likeCount, replies: .replyCount, url: ("https://bsky.app/profile/"+.author.handle+"/post/"+(.uri | split("/") | last))}'
```

### RSS para blogs, podcasts, canales de YouTube

Para cuentas objetivo que publican en RSS (la mayoría de blogs, todos los canales de YouTube):
```bash
# Feed de canal de YouTube (reemplaza CHANNEL_ID)
curl -s "https://www.youtube.com/feeds/videos.xml?channel_id=CHANNEL_ID"

# Feed genérico de blog
curl -s "https://example.com/feed/" | xmllint --xpath "//item[position()<6]" - 2>/dev/null
```

### LinkedIn y X — usa el navegador

LinkedIn y X no exponen APIs públicas útiles, pero puedes manejar una sesión real de navegador. **dev-browser** (MCP, ya incluido en la configuración global) y **Playwright** mantienen ambos un estado persistente — inicia sesión una vez, la sesión sigue activa, Claude puede navegar el feed autenticado.

**Flujo de trabajo con dev-browser (preferido — ya está configurado):**
1. El usuario inicia sesión en LinkedIn / X una vez en la sesión de dev-browser
2. Claude navega a una URL objetivo (feed, perfil, búsqueda guardada, hashtag)
3. Claude lee el árbol de accesibilidad / texto de la página, extrae los posts
4. Claude puntúa usando la [rúbrica](#rúbrica-de-scoring) y redacta comentarios
5. El usuario revisa y publica manualmente (no publiques automáticamente — es de alto riesgo, riesgo de detección de bots)

**URLs útiles para alimentar dev-browser:**

| Patrón de URL | Qué muestra |
|-------------|---------------|
| `linkedin.com/in/HANDLE/recent-activity/all/` | Los posts recientes de una cuenta objetivo |
| `linkedin.com/feed/hashtag/TOPIC/` | Feed de hashtag |
| `linkedin.com/feed/` | Tu feed principal (algorítmico — menos útil para triage) |
| `x.com/HANDLE` | El perfil de una cuenta objetivo |
| `x.com/search?q=QUERY&f=live` | Búsqueda en tiempo real (usa `f=live` para orden cronológico) |
| `x.com/i/lists/LIST_ID` | Una lista curada — la mejor opción para cuentas objetivo |

**Tips:**
- En X, arma una lista privada de cuentas objetivo y usa la URL de la lista. Mucho más limpio que el feed algorítmico.
- La URL `/recent-activity/all/` de LinkedIn es la forma más limpia de ver los posts de una persona sin el algoritmo.
- En ambas plataformas, haz scroll programáticamente (dev-browser lo soporta) para cargar más posts antes de extraer.

**Alternativas pagas si no quieres manejar un navegador:**

| Plataforma | Herramientas |
|----------|-------|
| LinkedIn | Sales Navigator (búsquedas guardadas), Taplio (engagement) |
| X | TweetDeck/X Pro (columnas guardadas), Typefully, Taplio, Tweet Hunter |

**Todavía cerrado (sin buen camino):**
- Instagram y TikTok — APIs cerradas, la automatización de navegador es detectable y riesgosa. Usa búsquedas guardadas nativas / seguimiento de hashtags.

---

## Notas por Plataforma

### LinkedIn
- **Manejado por navegador** (dev-browser con sesión persistente) — ver [LinkedIn y X — usa el navegador](#linkedin-y-x--usa-el-navegador)
- **Los comentarios de la primera hora importan más** — el algoritmo pondera fuertemente el engagement temprano. Prioriza posts de <2h de antigüedad de cuentas objetivo.
- Los comentarios con 5+ palabras obtienen más alcance que las reacciones
- Responder a otros comentaristas puede ponerte frente a su red
- Etiqueta al autor en tu respuesta solo si aporta contexto

### Twitter/X
- **Manejado por navegador** (dev-browser) — arma una lista privada de cuentas objetivo y apunta dev-browser a la URL de la lista
- Responde dentro de los primeros 30 min para máximo alcance en cuentas grandes
- Quote-tweet > respuesta cuando agregas valor sustancial
- Encadenar tu respuesta (multi-tweet) señala esfuerzo
- No te sumes a los ataques (dunks) — las relaciones valen más que el clout

### Reddit
- Lee las reglas del subreddit antes de comentar (algunos prohíben la autopromoción directamente)
- Gana karma en el sub antes de enlazar a algo propio
- Las respuestas largas y específicas ganan. Los AMA y los hilos de "ayúdenme a decidir" son oro
- Nunca lideres con tu producto — responde primero la pregunta

### Hacker News
- La barra de calidad del comentario es alta; el esfuerzo bajo se downvotea rápido
- Se acepta bien que los fundadores comenten en hilos sobre su producto si son transparentes
- Busca discusiones pasadas de tu categoría — a menudo son minas de oro dormidas

### Bluesky
- Menor volumen pero alta proporción de engagement por seguidor
- Las comunidades tech e indie-hacker están activas
- Los feeds personalizados (como "Siguiendo" + feeds de tema de Bluesky) reemplazan la búsqueda algorítmica

---

## Flujos de Trabajo Comunes

### "Dame mis 10 mejores posts para comentar hoy"
1. Extrae de: RSS/búsquedas guardadas de cuentas objetivo + Reddit (subs relevantes) + HN (últimas 24h)
2. Puntúa con la [rúbrica](#rúbrica-de-scoring)
3. Muestra el top 10 con comentarios sugeridos

### "Encuentra personas que se quejan de [competidor]"
1. Búsqueda en Reddit: `"nombre del competidor" -site:competidor.com` ordenado por nuevo
2. Búsqueda de comentarios en HN por nombre del competidor
3. Búsqueda en Bluesky por handle/nombre del competidor
4. Puntúa por señal de intención (alto si hay lenguaje de cambio: "moviéndome de", "alternativas a", "frustrado con")

### "Muéstrame las menciones de marca de la última semana"
1. Búsqueda en Reddit por nombre de marca
2. Búsqueda en HN (historias + comentarios) por nombre de marca
3. Búsqueda en Bluesky por nombre de marca + handle
4. Muestra como: respuesta necesaria (sí/no), tono (positivo/negativo/neutral), respuesta sugerida

### "Encuentra posts de cuentas objetivo que me perdí"
1. Mantén una lista de cuentas objetivo con su RSS / usuarios de Reddit / handles de Bluesky
2. Obtén los posts recientes de cada fuente
3. Filtra a las últimas 24h, muestra ordenado por score

---

## Configurar la Lista de Fuentes

El usuario debe mantener una lista de fuentes en algún lugar persistente en `.agents/listening-sources.md` (o `.claude/listening-sources.md`). Claude lo lee cuando corre el loop diario.

**Una plantilla lista para llenar está en [listening-sources-template.md](listening-sources-template.md).** Cópiala al proyecto y edítala. La ruta de origen depende de cómo se instaló la skill:

```bash
# Instalación por plugin / marketplace (la más común):
cp .agents/skills/social/references/listening-sources-template.md .agents/listening-sources.md
# Instalación .claude/:
cp .claude/skills/social/references/listening-sources-template.md .agents/listening-sources.md
# Trabajando dentro del repo marketingskills:
cp skills/social/references/listening-sources-template.md .agents/listening-sources.md
```

La plantilla cubre: marca/categoría, ICP (para el scoring), cuentas objetivo por plataforma, keywords de intención, subreddits, URLs de búsqueda guardada, y una lista de no-engagement.
