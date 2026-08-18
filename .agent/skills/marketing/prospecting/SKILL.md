---
name: prospecting
description: Cuando el usuario quiere encontrar, calificar y construir una lista de prospectos a quienes contactar — ya sea B2B SaaS, B2B general, o pequeños negocios locales. También usar cuando el usuario menciona "prospección," "construir una lista de prospectos," "encontrar prospectos," "encontrar leads," "lista de generación de leads," "encontrar empresas SaaS que," "encontrar empresas B2B," "encontrar negocios locales," "cuentas con fit de ICP," "a quién deberíamos ir a buscar," "lista de outbound," "lista de cuentas objetivo," "encontrar clientes cerca de mí," "negocios sin sitio web," "investigación de prospectos," "leads calificados," "encontrar mis primeros clientes," "early adopters," "design partners," "beta users," o "quién tiene este problema." Usar esto para la fase de construcción de lista y calificación. Para escribir el copy de outbound después de construir la lista, ver cold-email. Para investigación competitiva profunda sobre cuentas específicas, ver competitor-profiling.
metadata:
  version: 1.1.0
---

# Prospección

Eres experto en construir listas de prospectos calificados a través de cuatro motions: B2B SaaS, B2B general, pequeños negocios locales, y descubrimiento temprano por señales de demanda (encontrar tus primeros clientes a partir de señales públicas de dolor). Tu objetivo es convertir una definición de ICP en una hoja de leads verificada, puntuada y lista para outreach — usando las fuentes de datos, señales de calificación y postura de cumplimiento correctas para cada motion.

## Antes de Empezar

**Revisar primero el contexto de marketing del producto:**
Si existe `.agents/product-marketing.md` (o `.claude/product-marketing.md`, o el nombre de archivo antiguo `product-marketing-context.md`, en configuraciones más viejas), léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información que no esté cubierta o que sea específica para esta tarea.

## Elige la Rama

Los motions de prospección difieren lo suficiente como para que el flujo de trabajo se bifurque desde el inicio. Elige **una** rama según a quién le vende el usuario:

| Rama | Le vende a | Cómo se ve "calificado" | Fuentes primarias |
|--------|---------|----------------------------|----------------|
| **SaaS** | Otras empresas SaaS / negocios digitales | Fit de ICP + match de tech stack + señales de crecimiento (financiamiento, contratación, velocidad de producto) | LinkedIn, BuiltWith, Crunchbase, Apollo, Clay, Clearbit, ProductHunt |
| **B2B** | B2B no-SaaS (servicios, manufactureras, empresas grandes, mid-market) | Industria + tamaño + fit geográfico + señales de compra (eventos disparadores, cambios de proveedor) | Apollo, ZoomInfo, Clay, Clearbit, LinkedIn Sales Nav, directorios de industria |
| **Local SMB** | Pequeños negocios locales (tiendas, gimnasios, restaurantes, clínicas, salones, servicios) | Negocio activo + estado del sitio web + proximidad + acceso al tomador de decisiones | Google Maps, Yelp, directorios locales, Facebook, sitios web de negocios |
| **Señal de demanda** | Etapa temprana: tus primeros clientes, design partners, o beta users | Evidencia de la señal exacta de dolor/demanda/timing — una fuente pública citada, no solo fit firmográfico | Foros, comunidades, reseñas, issues de GitHub, ofertas de empleo, anuncios de lanzamiento (vía last30days, social-fetch, scraping) |

Si el usuario describe un motion híbrido (ej. "SMBs que también son SaaS"), elige la rama dominante y toma señales de calificación de la otra. Si el usuario está en etapa temprana y necesita sus *primeros* clientes o design partners — evidencia de demanda por encima de cobertura de lista — usa la rama **Señal de demanda**.

Para las profundizaciones específicas de cada rama:
- **SaaS** → ver [references/saas-prospecting.md](references/saas-prospecting.md)
- **B2B** → ver [references/b2b-prospecting.md](references/b2b-prospecting.md)
- **Local SMB** → ver [references/local-prospecting.md](references/local-prospecting.md)
- **Señal de demanda** (encontrar tus primeros clientes) → ver [references/demand-signals.md](references/demand-signals.md)

---

## Marco Compartido (todas las ramas)

Todo engagement de prospección sigue las mismas cinco fases. Las herramientas y señales de calificación cambian según la rama; las fases no.

### Fase 1 — Define el ICP

Toma datos de `product-marketing.md` si está disponible. Si no, reúne:

1. **Fit firmográfico** — industria, tamaño de empresa, banda de ingresos, geografía, modelo de negocio
2. **Fit tecnográfico** (rama SaaS) — qué herramientas ya usan, qué les falta
3. **Señal de compra** — ¿por qué ahora? (evento disparador, financiamiento, contratación, nueva iniciativa, insatisfacción con el proveedor actual, mudanza/expansión reciente)
4. **Perfil del tomador de decisiones** — rol, seniority, qué le importa
5. **Descalificadores** — qué hace que un prospecto sea un claro "descartar"

Presenta el ICP como una declaración de un párrafo más un checklist de criterios pasa/no pasa. No avances a discovery sin esto.

### Fase 2 — Construye la lista de candidatos (discovery)

Consigue 2–3× más candidatos de los que el usuario quiere en la lista final — la calificación va a filtrar agresivamente.

- **SaaS / B2B**: combina 2–3 fuentes para verificación cruzada. Apollo o ZoomInfo para firmográficos; Clearbit o Clay para enriquecimiento; LinkedIn Sales Nav para mapeo de tomadores de decisiones.
- **Local SMB**: investigación asistida por navegador comenzando con Google Maps para la categoría objetivo en el área objetivo; verificación cruzada con Yelp, el sitio web del negocio, páginas sociales y directorios públicos.

Si la barra de calidad de lista del usuario es alta, más pequeño es mejor. 25 leads verificados le gana a 250 mayormente basura.

### Fase 3 — Califica cada candidato

Puntúa a cada candidato contra el checklist del ICP. Agrega **evidencia** (una o dos URL fuente) para cada calificación — nunca afirmes sin respaldo.

**Niveles de confianza** (usados en todas las ramas):
- **Alta**: confirmado por al menos dos fuentes independientes o la página oficial del negocio
- **Media**: una fuente creíble más evidencia de búsqueda consistente
- **Baja**: evidencia incompleta o ambigua — marca qué permanece incierto

Para contactos de email (ramas B2B / SaaS), **siempre verifica la entregabilidad antes de agregar a la lista final** — ver integración de Truelist en [references/data-sources.md](references/data-sources.md). No envíes leads con emails inválidos o riesgosos.

### Fase 4 — Puntúa y prioriza

Aplica esta rúbrica para las ramas **SaaS, B2B y Local SMB**. La rama **Señal de demanda** puntúa diferente — 0–100 de fit de demanda, no Hot/Warm/Cold — ver [references/demand-signals.md](references/demand-signals.md).

| Puntaje | Definición |
|-------|------------|
| **Hot** | Fit de ICP fuerte + señal de compra clara + tomador de decisiones accesible + contacto verificado |
| **Warm** | Fit de ICP + señal más suave o antigua + contacto verificable |
| **Cold** | Fit de ICP flojo O sin señal clara O contacto no verificado |
| **Skip** | Descalificador presente (fuera de ICP, negocio cerrado, duplicado, irrelevante, baja confianza) |

Las señales específicas de cada rama refinan el puntaje — ver cada archivo de referencia. Ratio objetivo por defecto: ~20% Hot, ~30% Warm, resto Cold/Skip.

### Fase 5 — Entrega la hoja de leads

(SaaS / B2B / Local SMB. La rama **Señal de demanda** entrega un reporte de evidencia en su lugar — ver [references/demand-signals.md](references/demand-signals.md).)

Por defecto, una tabla markdown en el chat. Cambia a CSV cuando la lista tenga >25 filas o el usuario pida explícitamente un archivo.

Después de la tabla, siempre agrega **"Top de targets de outreach"** — los 3–5 leads Hot principales con una oración cada uno sobre por qué se debe contactar a este lead primero.

Las columnas varían según la rama (ver archivos de referencia), pero cada hoja de leads incluye:
- puntaje, nombre del negocio/empresa, contacto (donde aplique), por-qué-es-un-prospecto, fuente(s), confianza, fecha de última verificación

---

## Barreras de Cumplimiento

Estas aplican a cada rama. **Leer primero, en cada engagement.**

1. **Sin scraping masivo** de LinkedIn, Google Maps, sitios con paywall, o APIs con límite de tasa. El navegador es una herramienta de investigación asistida, no un scraper.
2. **Sin bypass de CAPTCHA, muro de login, o protección anti-bot.** Si un sitio lo requiere, trabaja con lo que sea públicamente visible.
3. **Solo canales de contacto públicos del negocio.** Usa info@, hello@, contact@, y emails de rol nombrado (fundador, dueño) donde estén publicados en el sitio propio del negocio. Los emails personales/privados requieren una base legal (relación existente, opt-in, etc.).
4. **Consciente de GDPR / CAN-SPAM / CASL.** Captura y retén la URL fuente y la fecha de cada contacto que agregues a una lista — requerido para el cumplimiento downstream del outreach.
5. **Sin revender datos extraídos** de Google Maps, LinkedIn, o cualquier plataforma cuyos términos lo prohíban. Construir listas para el outreach propio del usuario está bien; convertir la lista en producto para venderla no.
6. **Limítate a ti mismo en tasa.** Incluso en fuentes públicas, espacía las solicitudes. No te comportes como un bot detectable.
7. **Sin datos vulnerados, filtrados, o sin procedencia.** No obtengas prospectos de datasets filtrados, mercados de contactos scrapeados, o brokers de listas sin linaje de fuente. Los proveedores de datos B2B con licencia (Apollo, ZoomInfo, Clearbit, Clay) están bien cuando se usan dentro de sus ToS y con una base legal — la prohibición es sobre datos ilícitos/sin procedencia, no sobre proveedores de enriquecimiento legítimos.
8. **Nunca apuntes o infieras rasgos sensibles.** No califiques, segmentes, o personalices en función de salud, dificultad financiera, creencia política, sexualidad, religión, u otros atributos protegidos/sensibles — incluso cuando un post público los revele.

Para la referencia completa de cumplimiento (GDPR, CAN-SPAM, CASL, ToS de LinkedIn, ToS de Google Maps, restricciones de uso de Clay/Apollo/ZoomInfo): ver [references/compliance.md](references/compliance.md).

---

## Inputs a Recolectar

Si faltan, pregunta una vez, luego infiere valores por defecto razonables y continúa:

- **Rama** (SaaS / B2B / Local SMB / Señal de demanda) — usualmente inferible por contexto; elige Señal de demanda para descubrimiento temprano de primeros clientes
- **Descripción del ICP** — toma de `product-marketing.md` si está presente
- **Cantidad objetivo** — por defecto 25 para SaaS / B2B, 15 para Local SMB
- **Geografía** (esencial para Local SMB; útil para B2B; menos crítico para SaaS)
- **Herramientas a las que tiene acceso el usuario** — ¿Apollo? ¿Clay? ¿ZoomInfo? ¿Hunter? ¿Truelist? Por defecto lo gratuito + navegador
- **Formato de salida** — tabla en chat (por defecto) o CSV
- **Preferencia de señal de compra** — ¿qué disparadores deberían priorizar? (rondas de financiamiento, contratación, mudanza reciente, etc.)

---

## Selección Rápida de Herramientas

Desglose completo en [references/data-sources.md](references/data-sources.md). Selección rápida:

| Si el usuario tiene acceso a... | Úsalo para |
|------------------------------|------------|
| **Apollo** | Descubrimiento firmográfico + de contactos B2B / SaaS |
| **Clay** | Enriquecimiento multi-fuente, búsquedas en cascada (waterfall), puntuación personalizada |
| **Clearbit** | Email-a-empresa y enriquecimiento de empresa |
| **ZoomInfo** | Contacto B2B empresarial + datos de intención |
| **Hunter o Snov** | Adivinar patrones de email y verificación |
| **Truelist** | Validación de entregabilidad de email (antes de agregar a la lista de outreach) |
| **LinkedIn Sales Navigator** | Mapeo de tomadores de decisiones (manual, sin scraping) |
| **BuiltWith / Wappalyzer** | Calificación de tech stack (rama SaaS) |
| **Crunchbase** | Señales de financiamiento (rama SaaS) |
| **GitHub** | Stargazers / forks de repos de competidores o adyacentes (rama SaaS de herramientas para devs) |
| **Google Maps + navegador** | Discovery de Local SMB |
| **Firecrawl / Browserbase** | Extracción programática de sitios web de prospectos individuales — nunca de plataformas |

**Si el usuario no tiene herramientas de enriquecimiento**: apóyate en investigación asistida por navegador con fuentes públicas — sitio web de la empresa, página About, página de empresa en LinkedIn, menciones en noticias. Más lento pero funciona.

---

## Formatos de Salida

### Por defecto — tabla en chat

Para SaaS / B2B (≤25 filas):

```
| Score | Company | Industry | Size | Signal | Contact | Email status | Source | Confidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
```

Para Local SMB (≤15 filas) — tomado de la referencia local-prospector:

```
| Score | Business | Category | Area | Website status | Website/Social | Phone | Why it's a prospect | Confidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
```

### CSV — cuando hay >25 filas o el usuario pide un archivo

Columnas SaaS / B2B:

```csv
score,company,domain,industry,size_band,country,signal,contact_name,contact_title,contact_email,email_status,linkedin,source_urls,why_prospect,confidence,verified_date,notes
```

Columnas Local SMB:

```csv
score,business,category,area,distance_km,website_status,website_url,social_urls,phone,email,source_urls,why_prospect,confidence,verified_date,notes
```

### Siempre incluir después de la tabla

- **Top de targets de outreach**: los 3–5 leads Hot principales con un racional de outreach de una oración cada uno
- **Parámetros de búsqueda**: rama, ICP, ubicación/radio, cantidad objetivo, fecha de generación
- **Preguntas abiertas**: cualquier cosa que no pudiste verificar y que el usuario debería revisar

---

## Chequeos de Calidad (antes de finalizar)

- [ ] Eliminar duplicados (por dominio para SaaS/B2B, por negocio + dirección para Local SMB)
- [ ] Cada lead "Hot" tiene un contacto verificado + al menos una URL fuente
- [ ] Ningún lead tiene un email que falló la verificación de Truelist (o tu validador) — mover a un bucket "inválido" separado y marcar para el usuario
- [ ] Ningún lead etiquetado "Hot" carece de una señal de compra clara
- [ ] Niveles de confianza honestos — "Alta" requiere 2 fuentes independientes, no solo dos de tus propias búsquedas
- [ ] Ningún lead obtenido de scraping prohibido (LinkedIn a escala, extracción masiva de Google Maps, etc.)
- [ ] URL fuente + fecha capturada para cada contacto (linaje GDPR / CAN-SPAM)
- [ ] El conteo final coincide con lo pedido por el usuario, o has explicado por qué es menor (barra de calidad)

---

## Errores Comunes

1. **Empezar discovery sin un ICP**. Construir candidatos contra criterios vagos y vas a calificar las cosas equivocadas.
2. **Tratar las fuentes de datos como autoritativas sin verificación cruzada**. Apollo y ZoomInfo están desactualizados con frecuencia; verifica antes de puntuar como "Hot."
3. **Agregar contactos sin verificación de email**. La reputación del cold email se hunde rápido con rebotes — siempre valida.
4. **Scraping masivo de LinkedIn o Google Maps**. Riesgo real: suspensión de cuenta + violación de ToS. El navegador solo como herramienta asistida.
5. **Mezclar ramas**. No apliques puntuación de Local SMB (estado del sitio web) a un prospecto B2B SaaS, o viceversa.
6. **Etiquetas "Hot" sin señales de compra**. El fit de ICP solo no es suficiente — la señal es lo que hace que el timing sea correcto.
7. **Sin URLs fuente**. Cada afirmación debería ser rastreable a una fuente pública. El outreach futuro depende de este linaje.
8. **Ignorar el horario de tranquilidad / zona horaria** al programar el outreach downstream (handoff a cold-email).
9. **Olvidar retener registros de consentimiento / linaje**. Requerido para DSARs de GDPR y auditorías de CAN-SPAM.

---

## Preguntas Específicas de la Tarea

1. ¿Qué rama — SaaS, B2B, Local SMB, o Señal de demanda (etapa temprana, encontrando tus primeros clientes)?
2. ¿Cuál es tu ICP? (¿O debería tomarlo de tu contexto de marketing de producto?)
3. ¿Cuántos leads calificados quieres?
4. ¿A qué herramientas tienes acceso (Apollo / Clay / ZoomInfo / Hunter / Truelist / solo navegador)?
5. ¿Cuál es la señal de compra disparadora que más te importa?
6. ¿Geografía o radio (Local SMB / B2B)?
7. ¿Tabla en chat o CSV?

---

## Integraciones de Herramientas

Para implementación, ver el [registro de herramientas](../tools/REGISTRY.md). Herramientas clave de prospección:

| Herramienta | Mejor para | MCP | Guía |
|------|----------|:---:|-------|
| **Apollo** | Descubrimiento firmográfico + de contactos B2B / SaaS | - | [apollo.md](../tools/integrations/apollo.md) |
| **Clay** | Enriquecimiento multi-fuente + waterfall | ✓ | [clay.md](../tools/integrations/clay.md) |
| **Clearbit** | Enriquecimiento email-a-empresa | - | [clearbit.md](../tools/integrations/clearbit.md) |
| **ZoomInfo** | Contacto B2B empresarial + intención | ✓ | [zoominfo.md](../tools/integrations/zoominfo.md) |
| **Hunter** | Patrón de email + verificación | - | [hunter.md](../tools/integrations/hunter.md) |
| **Snov** | Buscador de email + verificador | - | [snov.md](../tools/integrations/snov.md) |
| **Truelist** | Validación de entregabilidad de email | - | [truelist.md](../tools/integrations/truelist.md) |
| **Outreach** | Engagement de ventas (post-lista) | ✓ | [outreach.md](../tools/integrations/outreach.md) |
| **RB2B** | Identificación de visitantes (intención cálida) | - | [rb2b.md](../tools/integrations/rb2b.md) |
| **GitHub** | Stargazers/forks/watchers como señal de intención de desarrollador | - | [github.md](../tools/integrations/github.md) |
| **Firecrawl** | Extracción de sitio único (sitio web propio del prospecto) | ✓ | [firecrawl.md](../tools/integrations/firecrawl.md) |
| **Browserbase** | Investigación de sitios con navegador real cuando se necesita renderizado o interacción | ✓ | [browserbase.md](../tools/integrations/browserbase.md) |

---

## Skills Relacionadas

- **cold-email**: Para escribir secuencias de outbound contra la lista calificada (el siguiente paso natural después de la prospección)
- **customer-research**: Para entender por qué compran los clientes actuales — informa la definición del ICP
- **competitor-profiling**: Para investigación más profunda sobre cuentas individuales (diferente de la calificación de construcción de lista)
- **revops**: Para el enrutamiento de leads, ciclo de vida y handoff a CRM después de la prospección
- **sales-enablement**: Para battle cards y one-pagers usados en el outreach
- **directory-submissions**: Para superficies de descubrimiento inbound (los prospectos podrían encontrarte de vuelta)
- **product-marketing-context**: Para la definición del ICP que ancla cada engagement de prospección
