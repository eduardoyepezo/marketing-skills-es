# Newsjacking — Flujo de Trabajo de PR Reactivo

Inyectar tu punto de vista en una historia que ya está en tendencia. Bien hecho: distribución gratis sobre una ola de atención. Mal hecho: vergüenza ajena en el mejor caso, daño de marca en el peor.

## Contenido
- Cuándo funciona el newsjacking (y cuándo no)
- El loop detectar → puntuar → ángulo → pitch
- Rúbrica de puntuación de noticiabilidad
- Biblioteca de ángulos de historia
- Velocidad: lo único que importa
- Fuentes y herramientas
- Modos de fallo

---

## Cuándo Funciona el Newsjacking

- **Noticias tech/regulatorias en tu categoría** — nueva ley, lanzamiento de nueva plataforma, pivote de un competidor, adquisición grande
- **Publicaciones de datos de la industria** — sale un reporte importante, tú tienes un take más filoso o datos que lo contradicen
- **Conversación pública** — un debate o controversia donde tu expertise es genuinamente relevante
- **Momentos estacionales/cíclicos** — temporada de resultados, resúmenes de fin de año, semanas de conferencias

## Cuándo Saltártelo

- **Tragedias, accidentes, muertes** — sin excepciones. No lo hagas.
- **Historias políticamente cargadas** a menos que tu marca tome posiciones políticas explícitamente
- **No tienes expertise genuina** en el área
- **La ventana ya se cerró** — si una historia tiene 48h+ de antigüedad y no fuiste el primero, llegaste tarde
- **El ángulo es "tenemos un producto para esto"** — eso es marketing, no periodismo

---

## El Loop

Un flujo de trabajo repetible que Claude puede correr bajo demanda o diariamente.

1. **Detectar** — descubre historias en tendencia en tu categoría (ver [Fuentes y Herramientas](#fuentes-y-herramientas))
2. **Puntuar** — aplica la [rúbrica de noticiabilidad](#rúbrica-de-puntuación-de-noticiabilidad); descarta todo lo que esté por debajo del umbral
3. **Ángulo** — genera 2–3 ángulos por historia usando la [biblioteca de ángulos](#biblioteca-de-ángulos-de-historia)
4. **Validar** — chequeo de sanidad: ¿realmente tienes la expertise/datos para respaldar este ángulo?
5. **Pitch** — redacta un pitch ajustado a 3–5 periodistas que cubran este tema (ver [journalist-pitching.md](journalist-pitching.md))
6. **Publicar** — publica también en tu blog, LinkedIn, X — construye el rastro que los periodistas revisan antes de citarte

Formato de salida que Claude debería producir:

```
CANDIDATO DE NEWSJACK — 2026-06-10

Historia: "La UE aprueba enmienda a la Ley de IA que exige registro de agentes"
Fuente: TechCrunch, hace 3h
Puntaje: 8/10 (alta relevancia, fresca, tienes datos propios)

Ángulos:
1. Data hot take: "Nuestro análisis de 12,000 despliegues de agentes muestra que el 73% fallaría este requisito"
2. Contrarian: "Por qué la regla de registro dañará la seguridad, no la mejorará"
3. Historia de cliente: "Cómo [cliente] se está preparando — oferta de entrevista"

Recomendado: #1 (tienes datos únicos, el gancho más fuerte)
Borrador de pitch: [ver journalist-pitching.md para la plantilla]
Periodistas objetivo: [lista con justificación]
```

---

## Rúbrica de Puntuación de Noticiabilidad

Puntúa cada candidato de 1–10 en cinco dimensiones, multiplica por el peso, luego suma. Máximo posible: 80 (10 × el peso total de 8x).

| Dimensión | Qué mide | Peso |
|-----------|------------------|--------|
| **Oportunidad temporal** | ¿La historia tiene <24h? ¿La ventana sigue abierta? | 2x |
| **Relevancia** | ¿Genuinamente está en tu área de expertise? | 2x |
| **Singularidad del ángulo** | ¿Puedes decir algo que nadie más está diciendo? | 2x |
| **Autoridad** | ¿Tienes datos, clientes o experiencia para respaldarlo? | 1x |
| **Potencial de alcance** | ¿Esta historia seguirá creciendo o ya llegó a su pico? | 1x |

**Umbral:** total ponderado ≥ 50/80. Por debajo de eso, sáltatelo.

**Descalifica automáticamente si:**
- La historia trata sobre algo trágico
- Tu ángulo es "no estoy de acuerdo" sin nada que lo respalde
- No has formado realmente una opinión — solo quieres que te citen

---

## Biblioteca de Ángulos de Historia

Usa estas plantillas para generar ángulos rápido.

### 1. Data hot take
*"Analizamos [N] [cosas] después de [evento]. Esto es lo que encontramos."*

Mejor cuando tienes datos propios. El periodista obtiene una estadística, tú obtienes la citación.

### 2. Contrarian
*"Todos dicen [opinión popular]. Aquí está por qué están equivocados."*

Mejor cuando puedes defender la posición con especificidad. Débil cuando es solo contrarianismo por atención.

### 3. "Lo predijimos"
*"Hace seis meses escribimos [cosa] — esto es lo que está pasando ahora y lo que sigue."*

Mejor cuando realmente lo predijiste. Letal para tu credibilidad si no lo hiciste.

### 4. Impacto en el cliente
*"Aquí hay un [tipo de cliente] directamente afectado. Podemos ponerte en contacto."*

Mejor para B2B. A los reporteros les encantan los clientes con nombre dispuestos a hablar.

### 5. Explicador desde adentro
*"Esta historia es complicada. Esto es lo que realmente está pasando."*

Mejor cuando la mayoría de la cobertura le falta matiz. No estás argumentando — estás educando.

### 6. Conector de tendencias
*"Esto no es aislado — es parte de un cambio más grande que estamos viendo en [patrón]."*

Mejor cuando tienes varios datos o ejemplos para conectar.

### 7. Punto de vista del founder
*"Como alguien que ha construido en este espacio durante [X años], esto es lo que la mayoría se está perdiendo."*

Mejor para piezas de opinión / op-eds. Débil como pitch de soundbite.

---

## Velocidad: Lo Único que Importa

El newsjacking decae rápido. Ventanas aproximadas:

| Tipo de historia | Ventana efectiva |
|-----------|------------------|
| Noticia tech de última hora | 4–12 horas |
| Regulación / política pública mayor | 24–48 horas |
| Reporte de industria / publicación de datos | 24–72 horas |
| Anuncio de conferencia | Mismo día |
| Adquisición / noticia de financiamiento | 12–24 horas |

**Implicación:** si no puedes redactar y enviar dentro de la ventana, no te molestes. Configura el loop para que detectar → hacer pitch tome <2 horas.

---

## Fuentes y Herramientas

Reutiliza las herramientas del flujo de listening de la skill `social`. Misma instalación: `brew install jq`.

### Google News RSS (sin autenticación)

```bash
# Reemplaza QUERY con el tema (usa + para espacios, %22 para comillas)
curl -s "https://news.google.com/rss/search?q=QUERY&hl=en-US&gl=US&ceid=US:en" \
  | xmllint --xpath "//item[position()<11]" - 2>/dev/null
```

### Hacker News (Algolia) para historias tech

```bash
SINCE=$(($(date +%s) - 86400))
curl -s "https://hn.algolia.com/api/v1/search_by_date?query=QUERY&tags=story&numericFilters=created_at_i>${SINCE}" \
  | jq '.hits[] | {title, url, points, num_comments, created_at, hn_url: ("https://news.ycombinator.com/item?id="+.objectID)}'
```

### Reddit (para subreddits específicos de categoría)

```bash
curl -s -A "newsjack/1.0" \
  "https://www.reddit.com/r/SUBREDDIT/top.json?t=day&limit=15" \
  | jq '.data.children[].data | {title, url, score, num_comments, created_utc}'
```

### Investigación de periodistas (basada en navegador)

Para encontrar *qué* periodistas están cubriendo la historia ahora mismo:
- **dev-browser** → busca la historia en Google News → haz clic en los artículos → anota los bylines
- Luego ve a los perfiles de X / LinkedIn / Muck Rack de esos periodistas para confirmar el tema y la cobertura reciente

Ver también [journalist-pitching.md](journalist-pitching.md) para el flujo completo de descubrimiento.

### Lista de fuentes

Para monitoreo repetible, agrega una sección "Temas de newsjacking" a `.agents/listening-sources.md` (plantilla en las referencias de la skill `social`):

```markdown
## Temas de newsjacking (Google News RSS)
- "regulación de agentes de IA"
- "financiamiento de [tu categoría]"
- "[tus competidores] OR [competidores adyacentes]"

## Publicaciones de datos de la industria (RSS / manual)
- Reportes de Pitchbook
- Reportes "state of [industria]" de a16z
- Reportes de benchmark de [tu categoría]
```

---

## Modos de Fallo

Cosas que han acabado con carreras y marcas.

- **Tragedy-jacking** — el tweet del Super Bowl 2013 de Oreo funcionó. La mayoría de los intentos desde entonces no. Guerras, desastres, muertes: no lo hagas.
- **El encaje forzado** — "Aquí está nuestro take sobre [historia en tendencia] — en realidad se trata de [nuestro producto]." Los periodistas lo ven venir al instante.
- **El take vacío** — hacer pitch de "tenemos una opinión" sin especificidad. Los periodistas necesitan una línea citable, no "estamos siguiendo esto de cerca."
- **Velocidad sin criterio** — ser el primero con un mal take es peor que llegar tarde con uno bueno. El chequeo intestinal de 30 minutos de "¿esto es apropiado para la marca?" existe por una razón.
- **Hacer pitch del mismo ángulo a 50 periodistas** — hablan entre ellos. Que te agarren una vez y pierdes las relaciones.
- **Sin seguimiento** — sale el pitch, el periodista responde en 20 minutos, el founder tarda 6 horas en responder. La historia sigue su curso.

---

## Práctica Complementaria: El Rastro Público

Cada pitch de newsjacking es más fuerte si el periodista puede encontrar evidencia de que has estado pensando en esto públicamente. Antes de hacer pitch:

1. Publica un post corto (blog, LinkedIn, hilo de X) con tu take
2. Referéncialo en el pitch ("más pensamiento aquí: [link]")
3. Esto indica que no eres oportunista — eres una voz real en el espacio

Si no tienes tiempo para publicar, probablemente no estés listo para hacer pitch.
