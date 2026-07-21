---
name: social-content-plan
version: 1.0.0
description: "Cuando el usuario quiere generar el contenido completo de redes sociales para todo un mes con el copy redactado y listo para publicar, no solo un calendario con temas o ideas. Usar cuando el usuario menciona 'plan de contenido mensual', 'planificación de contenido', 'contenido del mes completo', 'todos los posts del mes escritos', 'generar el contenido de redes sociales del mes', 'planificación mensual', 'quiero el copy de todos mis posts', 'content plan para el mes', 'posts de abril escritos', 'planificar el contenido de [mes]', 'dame todos los posts', 'contenido para instagram del mes', o 'arma el plan de redes del mes'. Esta habilidad ensambla y formatea en una estructura mensual lo que producen content-strategy (qué publicar) y social-content (cómo escribirlo). Para crear posts individuales, ver social-content. Para definir pilares y estrategia, ver content-strategy."
---

# Plan de Contenido Mensual

Eres el orquestador del plan de contenido mensual. Tu función no es generar contenido nuevo — es ensamblar y formatear en una estructura mensual coherente lo que producen dos habilidades especializadas:

- **content-strategy** define qué publicar: pilares temáticos, tipos de contenido, distribución por etapa del comprador.
- **social-content** escribe cómo publicarlo: copy completo, hooks, guiones de reel/video, hashtags, especificaciones por plataforma.

Tu rol es: leer los outputs de esas skills, asignar fechas y plataformas, y ensamblar todo en un plan de 4 semanas con formato consistente y listo para entregar.

---

## Paso 1: Leer el Contexto Disponible

Antes de hacer cualquier pregunta, verificar qué existe:

1. **`.claude/product-marketing-context.md`** o **`.agents/product-marketing-context.md`** — si existe, léelo. Extrae: nombre del cliente, voz de marca, audiencia, objetivo de negocio.
2. **Archivo de estrategia de contenido** (ej. `content-strategy-[cliente].md`) — si existe, léelo. Extrae: pilares temáticos, clusters de temas, tipos de contenido recomendados por pilar.

Solo pide lo que no esté cubierto por estos archivos.

---

## Paso 2: Recopilar lo que Falta

| Campo | Pregunta |
|-------|---------|
| Cliente / Marca | ¿Para qué cliente o marca es el plan? |
| Plataformas | ¿Cuáles plataformas incluimos? (LinkedIn, Instagram, TikTok, Facebook) |
| Frecuencia | ¿Cuántos posts por semana por plataforma? |
| Mes y año | ¿Para qué mes y año? |
| Pilares | ¿Ya tienen pilares de contenido definidos? Si no, usar content-strategy primero. |
| Tono de voz | ¿Cómo debe sonar la marca? |
| Objetivo del mes | ¿Qué se busca lograr este mes? (Awareness, engagement, leads, lanzamiento) |

**Si el cliente no tiene pilares definidos:** Detente aquí y recomienda usar la habilidad **content-strategy** primero. Los pilares son el insumo que necesita este plan para funcionar.

---

## Paso 3: Distribuir los Pilares en el Mes

Con los pilares de content-strategy en mano, distribuye los temas a lo largo de las 4 semanas. Usa este foco orientativo — adáptalo al objetivo del mes:

| Semana | Foco Temático Sugerido |
|--------|----------------------|
| Semana 1 | Educar / Awareness — contenido del pilar más amplio o introductorio |
| Semana 2 | Conectar / Comunidad — historias, preguntas, detrás de cámaras |
| Semana 3 | Demostrar / Evidencia — casos de éxito, resultados, datos |
| Semana 4 | Convertir / Acción — valor alto + CTA claro |

Asigna qué pilar cubre cada post de cada semana antes de escribir el copy.

**Para reglas de distribución y variación de formatos detalladas**: Ver [references/planning-templates.md](references/planning-templates.md)

---

## Paso 4: Generar el Copy con social-content

Para cada post asignado, usa la habilidad **social-content** para escribir el copy:

- El **tipo de post** (educativo, historia, evidencia, opinión, comunidad) lo determina el pilar y el foco semanal — viene de content-strategy.
- El **copy completo**, el **hook**, los **hashtags**, el **guion de reel/video** y el **brief visual** los produce social-content aplicando sus frameworks de plataforma.
- No escribas el copy de forma independiente. Si social-content está disponible, todo el copy pasa por sus marcos.

**Para especificaciones de plataforma, límites de caracteres y estructuras de guion**: Ver [references/post-formats.md](references/post-formats.md)

---

## Paso 5: Ensamblar el Plan

El plan se organiza **semana a semana**, no por tipo de contenido. Cada semana agrupa primero sus Historias, luego sus Reels, luego sus Posts — en ese orden, cada pieza principal (Reel, Post) como su propia unidad. Esta estructura es la que consume directamente `content-plan-html` para generar el PDF final; no requiere reordenamiento posterior.

**Para reglas de distribución, variación de formatos y cálculo de totales**: Ver [references/planning-templates.md](references/planning-templates.md)

Usar esta estructura exacta:

---

### Por cada semana (Semana 1 a Semana 4)

```
## Semana [N] — [Fechas] | [Tema de la semana]
**Publicaciones:** [resumen de piezas de la semana]

### Historias

#### Historia [N] — [Fecha] | [Plataforma] | [Tipo: Encuesta / Pregunta / Cuenta regresiva / Contenido]

**Contenido:**
[Texto principal de la historia]

**Mecánica:** [Encuesta con opciones / Caja de preguntas / Sticker de reacción / Solo texto]

**Brief visual:** [Fondo, estética, elementos de la historia]

---

### Reel — [Fecha] | [Plataforma] | [Tema/Pilar]

**Guion:**
[Hook visual — descripción de la imagen o acción de apertura]
**Voz:** "[Texto hablado del hook]"

[Setup]
**Voz:** "[Desarrollo del tema]"

[Valor]
**Voz:** "[El punto central, el tip, la revelación]"

[CTA]
**Voz:** "[Llamada a la acción hablada]"

**Brief visual:** [Descripción de la producción: locación, estética, texto en pantalla, música]

---

### Post — [Fecha] | [Plataforma] | [Formato: Carrusel / Imagen / Texto] | [Tema/Pilar]

**Contenido:**
[Para carruseles: texto de cada slide numerado.
Para imagen: descripción del visual y mensaje principal.
Para texto (LinkedIn): copy completo del post.]

**Brief visual:** [Descripción del diseño, colores, elementos visuales]

---
```

Repetir este bloque para cada semana del mes. Una semana puede tener varias Historias, varios Reels o varios Posts — repite la subsección correspondiente tantas veces como piezas haya, siempre agrupadas bajo su semana.

---

### Sección — Checklist

Tabla de seguimiento de todos los contenidos del mes. Se marca a medida que se producen y publican.

```
## Checklist — [Cliente] — [Mes Año]

| # | Fecha | Tipo | Plataforma | Tema | Guionado | Diseñado | Aprobado | Publicado |
|---|-------|------|-----------|------|----------|----------|----------|-----------|
| R1 | [fecha] | Reel | Instagram | [tema] | ☐ | ☐ | ☐ | ☐ |
| P1 | [fecha] | Post | Instagram | [tema] | ☐ | ☐ | ☐ | ☐ |
| H1 | [fecha] | Historia | Instagram | [tema] | ☐ | ☐ | ☐ | ☐ |
```

Prefijos: R = Reel, P = Post, H = Historia. Numerar en orden cronológico dentro de cada tipo.

---

### Sección — Copy

El copy listo para copiar y pegar al momento de publicar. Solo el título del post y el texto del caption — sin briefs visuales ni guiones.

```
## Copy — [Cliente] — [Mes Año]

### R1 — [Título del reel]
[Caption completo listo para publicar]
[Hashtags]

---

### P1 — [Título del post]
[Caption completo listo para publicar]
[Hashtags]

---

### H1 — [Título de la historia]
[Texto de la historia si aplica]

---
```

---

## Paso 6: Resumen del Mes

Al inicio del documento, incluir una tabla resumen antes de las secciones:

```
## Resumen — [Cliente] — [Mes Año]

| Tipo | Cantidad | Plataformas |
|------|----------|-------------|
| Reels | X | Instagram, TikTok |
| Posts | X | Instagram, LinkedIn |
| Historias | X | Instagram, Facebook |
| **Total** | **X** | |
```

---

## Paso 7: Guardar y Ofrecer Entregable

Guardar el plan como:
```
plan-contenido-[cliente]-[mes]-[año].md
```

El orden de las secciones en el archivo:
1. Resumen del mes
2. Semana 1 (Historias, Reels, Posts)
3. Semana 2 (Historias, Reels, Posts)
4. Semana 3 (Historias, Reels, Posts)
5. Semana 4 (Historias, Reels, Posts)
6. Checklist
7. Copy

En `.claude/` o donde el usuario indique.

Siempre terminar con:

> "¿Quieres convertir este plan en un HTML listo para imprimir como PDF? Usa la habilidad **content-plan-html** para generarlo con los colores de marca del cliente."

---

## Frecuencia de Referencia por Plataforma

| Plataforma | Mínimo | Óptimo | Máximo |
|-----------|--------|--------|--------|
| LinkedIn | 2x/sem | 3-4x/sem | 5x/sem |
| Instagram | 3x/sem | 5x/sem | 7x/sem |
| TikTok | 3x/sem | 5-7x/sem | 14x/sem |
| Facebook | 2x/sem | 3x/sem | 5x/sem |

---

## Habilidades Relacionadas

- **content-strategy**: Produce los pilares y tipos de contenido que este plan organiza — insumo obligatorio antes de planificar
- **social-content**: Escribe el copy de cada post que este plan ensambla — todo el copy pasa por sus marcos
- **content-plan-html**: Convierte este plan en un HTML listo para imprimir como PDF, con los colores de marca del cliente
- **product-marketing-context**: Captura el contexto de marca que alimenta tanto content-strategy como social-content
- **copywriting**: Para piezas de formato largo que luego se reutilizan en las redes sociales
