# Hyperframes

Framework de video programático de código abierto de HeyGen. Crea videos desde HTML/CSS/JS — sin React, sin DSL propietario. Diseñado para flujos de trabajo de agentes de IA.

## Capacidades

| Integración | Disponible | Notas |
|-------------|------------|-------|
| API | - | Es una librería, no un servicio hospedado |
| MCP | - | - |
| CLI | ✓ | `npx hyperframes render` |
| SDK | ✓ | Paquete de Node.js/TypeScript |

## Por Qué Hyperframes

- **Nativo para LLMs**: los modelos de IA generan mejor HTML que componentes de React — estándares web planos, sin DSL de framework
- **Determinístico**: la misma entrada siempre produce el mismo resultado (ideal para automatización)
- **Código abierto**: licencia Apache 2.0, sin costo por render
- **Amigable para agentes**: cualquier agente de código que sepa escribir HTML puede crear videos

## Instalación

```bash
npm install hyperframes
```

Requiere: Node.js 22+, Chrome/Chromium (para renderizar)

## Inicio Rápido

```typescript
import { render } from "hyperframes";

await render({
  frames: [
    {
      html: `
        <div style="display:flex; align-items:center; justify-content:center;
                    height:100%; background:#000; color:#fff; font-family:system-ui;">
          <h1 style="font-size:64px;">Bienvenido a Acme</h1>
        </div>
      `,
      duration: 3,
    },
    {
      html: `
        <div style="display:flex; flex-direction:column; align-items:center;
                    justify-content:center; height:100%; background:#000; color:#fff;
                    font-family:system-ui;">
          <h2 style="font-size:48px;">Lanza más rápido con IA</h2>
          <p style="font-size:24px; color:#888;">Pruébalo gratis hoy</p>
        </div>
      `,
      duration: 3,
    },
  ],
  output: "intro.mp4",
  width: 1080,
  height: 1920, // 9:16 vertical
  fps: 30,
});
```

## Conceptos Centrales

### Frames

Cada frame es un documento HTML renderizado en un punto específico de la línea de tiempo. Piénsalo como una diapositiva con una duración.

```typescript
{
  html: "<div>...</div>",  // Contenido HTML completo
  duration: 3,              // Segundos que se muestra
  css?: "body { ... }",     // CSS externo opcional
}
```

### Transiciones

Las transiciones y animaciones CSS funcionan entre frames:

```html
<div style="animation: fadeIn 0.5s ease-in;">
  <h1>Entrada Deslizante</h1>
</div>
<style>
  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }
</style>
```

### Videos Basados en Datos

Genera frames a partir de datos para producción en lote:

```typescript
const features = ["Analítica", "Automatización", "Insights de IA"];

const frames = features.map((feature) => ({
  html: `
    <div style="display:flex; align-items:center; justify-content:center;
                height:100%; background:linear-gradient(135deg, #667eea, #764ba2);
                color:#fff; font-family:system-ui;">
      <h1 style="font-size:56px;">${feature}</h1>
    </div>
  `,
  duration: 2.5,
}));

await render({ frames, output: "features.mp4", width: 1080, height: 1920 });
```

## Plantillas Comunes de Marketing

### Anuncio de Producto

```typescript
const frames = [
  { html: hookSlide("Algo nuevo llegó"), duration: 2 },
  { html: featureSlide(title, description, screenshot), duration: 4 },
  { html: ctaSlide("Pruébalo gratis →", url), duration: 3 },
];
```

### Video de Testimonio

```typescript
const frames = [
  { html: quoteSlide(testimonial.text), duration: 4 },
  { html: attributionSlide(testimonial.author, testimonial.company), duration: 2 },
  { html: ctaSlide("Únete a más de 1,000 clientes felices"), duration: 3 },
];
```

### Video de Estadísticas/Métricas

```typescript
const metrics = [
  { label: "Usuarios", value: "10,000+" },
  { label: "Uptime", value: "99.9%" },
  { label: "NPS", value: "72" },
];

const frames = metrics.map(m => ({
  html: metricSlide(m.label, m.value),
  duration: 2.5,
}));
```

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
