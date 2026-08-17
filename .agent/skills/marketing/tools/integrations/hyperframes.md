# Hyperframes

Framework de video programático de código abierto de HeyGen. Crea videos desde HTML/CSS/JS — sin React, sin DSL propietario. Diseñado para flujos de trabajo de agentes de IA.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | - | Es un CLI que escafolda proyectos, no un servicio hospedado ni una librería de JS importable |
| MCP | - | - |
| CLI | ✓ | `npx hyperframes <comando>` (init, preview, render, doctor, y más) |
| SDK | - | No existe un paquete `import { render } from "hyperframes"` — la composición se edita como HTML de proyecto, no se llama por código |

## Por Qué Hyperframes

- **Nativo para LLMs**: los modelos de IA generan mejor HTML que componentes de React — estándares web planos, sin DSL de framework
- **Determinístico**: la misma entrada siempre produce el mismo resultado (ideal para automatización)
- **Código abierto**: licencia Apache 2.0, sin costo por render
- **Amigable para agentes**: cada proyecto escafoldado trae `AGENTS.md`/`CLAUDE.md` — está diseñado para que un agente de código (como Claude Code) edite el HTML directamente

## Instalación

No requiere instalación global — se usa vía `npx`. Cada proyecto escafoldado trae su propio `package.json` con scripts que también invocan `npx hyperframes` internamente.

**Requiere:**
- Node.js 22+
- Chrome/Chromium (se descarga automáticamente si falta)
- **FFmpeg** (`brew install ffmpeg`) — sin esto el render falla con error explícito
- Al menos ~2 GB de RAM disponible para renderizar sin fallos

Verifica el entorno antes de una sesión con cliente:
```bash
npx hyperframes doctor
```

## Inicio Rápido

```bash
# 1. Escafoldar un proyecto nuevo
npx hyperframes init mi-video --example blank --resolution portrait

cd mi-video

# 2. Previsualizar en el navegador mientras editas index.html
npm run dev

# 3. Validar la composición antes de renderizar
npm run check

# 4. Renderizar a MP4
npm run render
```

`--resolution` acepta: `landscape` (1920x1080), `portrait` (1080x1920), `square` (1080x1080), y variantes 4K.

## Conceptos Centrales

### El proyecto es un archivo HTML

`init` genera `index.html` con un contenedor raíz que define la composición completa:

```html
<div
  id="root"
  data-composition-id="main"
  data-start="0"
  data-duration="10"
  data-width="1080"
  data-height="1920"
>
  <!-- Los clips van aquí dentro -->
</div>
```

### Clips

Cada pieza de contenido en la línea de tiempo es un `<div class="clip">` con su propio tiempo de entrada, duración y pista:

```html
<div
  id="hook"
  class="clip"
  data-start="0"
  data-duration="3"
  data-track-index="1"
  style="display:flex; align-items:center; justify-content:center; height:100%;
         background:#000; color:#fff; font-family:system-ui; font-size:64px;"
>
  Este es el lugar exacto de donde sale tu café
</div>
```

Agrega tantos `.clip` como frames necesite el video — cada uno con su `data-start` y `data-duration` propios. GSAP (`gsap.min.js`) viene precargado en el HTML escafoldado para animaciones dentro de un clip.

### Transiciones

Las transiciones y animaciones CSS funcionan igual que en cualquier HTML — `@keyframes` y `animation` sobre los clips.

### Producción en lote (varios videos desde datos)

No hay una función `render()` para llamar por código con distintos datos. El patrón real para lotes es generar varios **proyectos** (uno por pieza de contenido) y renderizarlos con `npx hyperframes render <directorio>` en un loop de shell, o editar el `index.html` de un mismo proyecto para cada variante antes de renderizar.

## Plantillas Comunes de Marketing

Estos son casos de uso, no código para copiar — la implementación real es HTML dentro de `index.html` del proyecto:

- **Anuncio de producto:** hook (2s) → feature con screenshot (4s) → CTA (3s), cada uno como un `.clip` con su `data-start`.
- **Video de testimonio:** cita (4s) → atribución (2s) → CTA (3s).
- **Estadísticas/métricas:** un `.clip` por métrica, distribuidos en la línea de tiempo con `data-start` consecutivos.

## Relaciones de Aspecto

| Plataforma | Ancho | Alto | Proporción |
|----------|-------|--------|-------|
| TikTok/Reels/Shorts | 1080 | 1920 | 9:16 |
| YouTube | 1920 | 1080 | 16:9 |
| Instagram Feed | 1080 | 1080 | 1:1 |
| Instagram Feed | 1080 | 1350 | 4:5 |

## Hyperframes vs. Remotion

| Factor | Hyperframes | Remotion |
|--------|-------------|----------|
| Lenguaje | HTML/CSS/JS | React/TypeScript |
| Compatibilidad con agentes | Mejor (HTML plano) | Buena (requiere conocimiento de React) |
| Animación | Transiciones/keyframes CSS | Física de resortes, interpolación |
| Renderizado en la nube | No incluido | Lambda (AWS) |
| Licencia | Apache 2.0 (gratis) | Licencia comercial de pago |
| Ecosistema | Nuevo, en crecimiento | Maduro, comunidad grande |

**Usa Hyperframes cuando:** un agente de IA está generando el video, animaciones simples, contenido de plantilla en lote, sensible al costo.

**Usa Remotion cuando:** se necesitan animaciones complejas, ya usas React, necesitas Lambda para escala masiva, quieres un ecosistema más grande.

## Skills Relevantes

- video
- social
- ad-creative
