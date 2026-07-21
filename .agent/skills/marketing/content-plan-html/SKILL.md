---
name: content-plan-html
description: "Cuando el usuario quiere convertir un plan de contenido mensual en formato MD a un archivo HTML listo para imprimir como PDF. Usar cuando el usuario dice 'haz el HTML del plan', 'convierte el MD a HTML', 'quiero el plan en PDF', 'haz el plan visual', 'ponlo en HTML como los otros'. Esta skill genera un documento HTML de una sola página por semana, con diseño consistente y listo para imprimir desde Chrome (Cmd+P → Márgenes: Ninguno → Gráficos de fondo → PDF)."
---

# Plan de Contenido MD → HTML

Eres un experto en convertir planes de contenido mensual (archivos `.md`) en documentos HTML profesionales listos para imprimir como PDF. El resultado es un documento consistente, oscuro, tipográfico — idéntico en estructura para todos los clientes, diferenciado solo por color de acento y contenido.

---

## Paso 1: Preparación

Antes de crear el HTML:

1. **Leer el MD fuente** — identificar semanas, piezas por semana y tipos de contenido
2. **Verificar la organización del MD** — debe estar organizado semana a semana. Si está por formato (todos los reels, todos los posts), primero reestructurarlo.
3. **Identificar los colores de marca del cliente** — buscar en `.claude/agency-brand.md` o en archivos de branding/contexto. Si no hay colores explícitos, preguntar antes de continuar.
4. **Contar las piezas** — calcular cuántas páginas necesitará el HTML

---

## Paso 2: Reestructurar el MD (si aplica)

Si el MD está organizado por formato (Reels / Posts / Historias en secciones separadas), reestructurarlo semana a semana **antes** de crear el HTML.

**Estructura correcta del MD:**

```markdown
## Semana X — Fechas | Tema de la semana
**Publicaciones:** [resumen de piezas]

### Historias
#### H1 — [fecha] | [tipo]
...

### Reel — [fecha]
...

### Post — [fecha]
...
```

**Regla:** El contenido de cada pieza (guion, brief visual, copy, hashtags) va integrado en su semana correspondiente — no en secciones separadas al final.

---

## Paso 3: Planificar las páginas

Cada semana ocupa varias páginas. Regla de división:

| Página | Contenido | Header |
|--------|-----------|--------|
| Primera de la semana | Historias (anuncio de semana) | `piece-header` — **CON COLOR** (primera mención) |
| Siguientes de la semana | Reel, Post (una pieza por página) | `piece-header-dark` — **SIN COLOR** (menciones siguientes) |
| Portada | — | Diseño especial |
| Checklist | — | `piece-header` — con color |

**Regla crítica del header:**
- La **primera vez** que aparece una semana (siempre la página de Historias) → `piece-header` (fondo de acento, texto negro)
- Las **siguientes menciones** de esa semana (Reel, Post) → `piece-header-dark` (fondo oscuro, texto blanco)

**Una pieza = una página.** Si el contenido de una pieza puede desbordar la página A4, usar su propia página. Nunca poner dos piezas principales (dos Reels, dos Posts) en la misma página.

**Historias:** Siempre en grid. 2 historias = `historia-grid` (2 cols). 3 historias = `historia-grid-3` (3 cols). Máximo 3 por página. Si hay más, dividir en dos páginas de historias.

**Estructura de páginas típica:**
- Página 1: Portada
- Por semana (x4): Historias + Reel(s) + Post(s) — uno por página
- Última página: Checklist

---

## Paso 4: Diseño del HTML

### Variables de color (ajustar por cliente)

```css
:root {
  --black:    /* fondo más oscuro */
  --dark:     /* fondo de página */
  --dark2:    /* fondo de piece-header-dark y cards de historia */
  --card:     /* fondo de cards */
  --card2:    /* fondo de cards alternas (checklist) */
  --accent:   /* COLOR DE MARCA del cliente */
  --accent2:  /* versión más oscura del acento (no siempre necesaria) */
  --white:    /* texto principal */
  --border:   /* bordes y separadores */
  --muted:    /* texto secundario/apagado */
}
```

### Tipografía

Siempre usar **Inter** de Google Fonts:
```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
```

### Estructura de página

```html
<div class="page">
  <div class="piece-header"> <!-- o piece-header-dark -->
    <div>
      <div class="piece-num">Semana X · Tipo · Fecha</div>
      <div class="piece-title">TEMA DE LA SEMANA</div>
    </div>
    <div class="piece-meta">Plataforma · Formato</div>
  </div>
  <div class="page-inner">
    <!-- contenido -->
  </div>
</div>
```

### Headers

**`piece-header`** — primera mención de semana (Historias) + Portada-related + Checklist:
```css
.piece-header {
  background: var(--accent);
  padding: 16px 36px;
  /* piece-num: negro semitransparente */
  /* piece-title: negro, 16px, 900, uppercase */
  /* piece-meta: negro, 11px, semitransparente */
}
```

**`piece-header-dark`** — menciones siguientes (Reels, Posts):
```css
.piece-header-dark {
  background: var(--dark2);
  border-bottom: 2px solid var(--accent);
  /* piece-num: var(--accent) */
  /* piece-title: var(--white), 13px */
  /* piece-meta: var(--muted) */
}
```

### Cards

```html
<div class="card">
  <div class="card-head">
    <span class="badge badge-reel">Reel</span>  <!-- o badge-post, badge-historia -->
    <span class="card-date">Lunes 3 de junio</span>
  </div>
  <div class="card-title">TÍTULO DEL CONTENIDO EN MAYÚSCULAS</div>

  <!-- Para Reels: guion -->
  <div class="field">
    <div class="field-label">Guion</div>
    <ul class="guion">
      <li><span class="guion-label">[Hook]</span><span>Texto...</span></li>
      <li><span class="guion-label">[Escena 1]</span><span>Texto...</span></li>
      <li><span class="guion-label">[Cierre]</span><span>Texto...</span></li>
    </ul>
  </div>

  <!-- Para Posts carrusel: slides -->
  <div class="field">
    <div class="field-label">Slides</div>
    <ul class="slides">
      <li><span class="slide-n">01 —</span><span><strong>Cover:</strong> Texto...</span></li>
    </ul>
  </div>

  <!-- Para Posts imagen/foto: contenido simple -->
  <div class="field">
    <div class="field-label">Contenido</div>
    <div class="field-value">Descripción...</div>
  </div>

  <!-- Siempre: brief visual -->
  <div class="field">
    <div class="field-label">Brief visual</div>
    <div class="field-value">Instrucciones visuales...</div>
  </div>

  <!-- Siempre: caption -->
  <div class="field">
    <div class="field-label">Caption</div>
    <div class="caption-box">Texto del copy...</div>
    <div class="hashtags">#hashtag1 #hashtag2</div>
  </div>
</div>
```

### Cards de Historia

```html
<div class="card">
  <div class="card-head">
    <span class="badge badge-historia">Historia</span>
    <span class="card-date">Sem 1 · Tipo</span>
  </div>
  <div class="field">
    <div class="field-label">Contenido</div>
    <div class="field-value">Texto corto del contenido...</div>
  </div>
  <div class="field">
    <div class="field-label">Mecánica</div>
    <div class="mecanica-box">Encuesta / Sticker / Quiz — descripción</div>
  </div>
  <div class="field">
    <div class="field-label">Brief visual</div>
    <div class="field-value">...</div>
  </div>
</div>
```

### Portada

```html
<div class="page cover">
  <div class="top-bar"></div>
  <div class="cover-body">
    <div>
      <div class="cover-eyebrow">Plan de Contenido · Instagram</div>
      <div class="cover-title">NOMBRE<br><span>CLIENTE</span></div>
      <!-- La segunda línea o palabra clave va en <span> para usar --accent -->
      <div class="cover-handle">@handle</div>
      <div class="cover-rule"></div>
      <div class="cover-subtitle">Mes Año</div>
    </div>
    <div class="cover-bottom">
      <div class="cover-stats">
        <div><div class="cover-stat-label">Reels</div><div class="cover-stat-value">N</div></div>
        <!-- ...posts, historias, total -->
      </div>
      <div class="cover-date">Mes Año<br>Subtema del mes</div>
    </div>
  </div>
  <div class="bot-bar"></div>
</div>
```

### Checklist

```html
<div class="page">
  <div class="piece-header"> <!-- piece-header CON COLOR -->
    <div>
      <div class="piece-num">Cliente · Mes Año</div>
      <div class="piece-title">Checklist de Producción</div>
    </div>
    <div class="piece-meta">N piezas</div>
  </div>
  <div class="page-inner">
    <div class="checklist-wrap">
      <table class="checklist-table">
        <thead>
          <tr><th>#</th><th>Sem</th><th>Fecha</th><th>Tipo</th><th>Descripción</th><th>Diseñado</th><th>Publicado</th></tr>
        </thead>
        <tbody>
          <tr>
            <td>R1</td><td>S1</td><td>3 jun</td>
            <td class="type-reel">Reel</td>  <!-- type-reel, type-post, type-historia -->
            <td>Descripción corta</td>
            <td>☐</td><td>☐</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</div>
```

---

## Paso 5: CSS esencial (copiar siempre igual)

El CSS completo que va en `<style>` incluye, sin variaciones:

```css
/* Page base */
.page {
  width: 210mm; min-height: 297mm;
  background: var(--dark);
  margin: 20px auto;
  box-shadow: 0 4px 32px rgba(0,0,0,0.6);
  border-radius: 2px; overflow: hidden;
  display: flex; flex-direction: column;
}
.page-inner { padding: 28px 36px 40px; flex: 1; }

/* Grids de historias */
.historia-grid   { display: grid; grid-template-columns: 1fr 1fr;     gap: 12px; }
.historia-grid-3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 10px; }

/* Guion (fuente monoespaciada para las etiquetas) */
.guion-label {
  font-family: 'Courier New', monospace;
  font-size: 9.5px; font-weight: 700;
  color: var(--accent); min-width: 76px;
  text-transform: uppercase;
}

/* Caption con borde de acento */
.caption-box {
  background: var(--black); border-left: 3px solid var(--accent);
  padding: 10px 14px; font-size: 12.5px; line-height: 1.75;
  white-space: pre-line; border-radius: 0 2px 2px 0;
}

/* Print */
@page { size: A4; margin: 0; }
@media print {
  body { background: var(--black); }
  .page {
    width: 210mm; min-height: 297mm; margin: 0;
    page-break-before: always; break-before: page;
  }
  .page:first-child { page-break-before: auto; break-before: auto; }
  .cover { height: 297mm; }
  .page-inner { padding: 10mm 14mm 14mm; }
  .piece-header, .piece-header-dark { padding-left: 14mm; padding-right: 14mm; }
  .cover-body { padding: 12mm 14mm; min-height: 0; }
  .card { page-break-inside: avoid; break-inside: avoid; }
  * { -webkit-print-color-adjust: exact; print-color-adjust: exact; }
}
```

---

## Paso 6: Instrucciones de impresión

Al entregar el HTML, siempre incluir estas instrucciones:

```
Para generar el PDF:
Chrome → Cmd+P (Mac) / Ctrl+P (Windows)
→ Márgenes: Ninguno
→ Desactivar "Encabezados y pies de página"
→ Activar "Gráficos de fondo"
→ Guardar como PDF
```

---

## Reglas generales

- **Nunca** mencionar que fue generado con Marketing Skills ni ninguna herramienta de IA
- **Nunca** agrupar dos Reels o dos Posts en la misma página si el contenido es extenso
- **Siempre** `min-height: 297mm` en `.page` para que el fondo oscuro llene la página completa
- **Siempre** `page-break-inside: avoid` en `.card` para que los cards no se corten entre páginas
- El **color de acento** es el único elemento que cambia entre clientes — todo lo demás es idéntico
- Las **historias** siempre van en la primera página de su semana (página de anuncio)
- El **checklist** siempre es la última página, con `piece-header` (con color)
