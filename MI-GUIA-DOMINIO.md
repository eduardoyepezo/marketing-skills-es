# Mi Guía de Dominio — 32 Marketing Skills

Guía personal para aprender, practicar y enseñar cada skill antes de presentárselas a clientes.

---

## Cómo Usar Esta Guía

Para cada skill, la estructura es siempre la misma:
1. **Entiende qué hace** — lee el SKILL.md
2. **Practica con un ejemplo tuyo** — invócala con un producto real que conozcas
3. **Aprende cuándo NO usarla** — tan importante como cuándo sí
4. **Prepara tu demo** — el ejemplo que le mostrarás al cliente

---

## El Fundamento: Siempre Empieza Aquí

### `product-marketing-context`
**Lo más importante del sistema.** Antes de usar cualquier skill, el agente necesita conocer el producto/negocio.

**Para un cliente de agencia, configuras esto por su cliente:**
- ¿Qué hace el producto/servicio del cliente de la agencia?
- ¿A quién le venden?
- ¿Cuál es su diferenciador?
- ¿Qué tono de marca tienen?

**Cómo invocarlo:**
```
/product-marketing-context
```
El agente te hace las preguntas y crea el archivo en `.agents/product-marketing-context.md` (o `.claude/`).

**Demo para cliente:** Muéstrale cómo en 10 minutos el agente captura todo el contexto de su cliente y ya nunca más tienes que repetirle quién es el cliente.

---

## BLOQUE 1: Optimización de Conversiones (CRO)

Estas 6 skills son las más impactantes para agencias — directamente mejoran resultados medibles.

### `page-cro` — Optimización de Páginas
**Qué hace:** Audita cualquier página de marketing (home, landing, precios) y da recomendaciones concretas para mejorar conversiones.

**Cuándo usarla:** Un cliente dice "esta página no convierte bien" o "quiero mejorar mi tasa de conversión."

**Prompt de práctica:**
```
Audita la homepage de [empresa que conozcas]. 
La URL es [url]. El objetivo principal es que se registren en la prueba gratis.
```

**Lo que debe salir:** Problemas específicos con el hero, CTA, propuesta de valor, estructura. No opiniones vagas.

**Cuándo NO usarla:** Para formularios específicos (usa `form-cro`) o flujo de registro (usa `signup-flow-cro`).

---

### `signup-flow-cro` — Flujo de Registro
**Qué hace:** Optimiza el proceso de crear cuenta / activar prueba gratis.

**Cuándo usarla:** El cliente tiene muchas visitas pero poca gente completa el registro. O quieren reducir fricción en el onboarding inicial.

**Prompt de práctica:**
```
Nuestro flujo de registro tiene 5 pasos y perdemos el 70% de usuarios en el paso 3.
El paso 3 pide: nombre, apellido, empresa, cargo, teléfono, tamaño de empresa.
¿Qué está mal y cómo lo mejoramos?
```

---

### `onboarding-cro` — Activación Post-Registro
**Qué hace:** Mejora qué pasa DESPUÉS de que alguien se registra — cómo llevarlos a experimentar el valor del producto rápido.

**Cuándo usarla:** El cliente tiene registros pero nadie activa o usa el producto.

**La diferencia clave:** `signup-flow-cro` = llegar a la cuenta. `onboarding-cro` = primeros días dentro del producto.

---

### `form-cro` — Formularios
**Qué hace:** Optimiza formularios de captura de leads, contacto, solicitud de demo.

**Prompt de práctica:**
```
Tenemos un formulario de "solicitar demo" con 8 campos. 
La tasa de conversión es del 2%. ¿Cómo lo mejoramos?
```

---

### `popup-cro` — Popups y Modales
**Qué hace:** Crea o mejora popups de salida, modales de suscripción, banners de oferta.

**Cuándo usarla:** El cliente quiere capturar leads con popups o tiene popups que no convierten.

---

### `paywall-upgrade-cro` — Pantallas de Upgrade
**Qué hace:** Optimiza las pantallas dentro del producto donde el usuario ve el "límite" y puede actualizar su plan.

**Solo para clientes con:** Productos con modelo freemium o trial → paid.

---

## BLOQUE 2: Contenido y Copy

### `copywriting` — Escribir Copy de Marketing
**La más usada por agencias.** Escribe o reescribe copy para cualquier página de marketing.

**El truco:** Esta skill usa principios reales de copywriting (frameworks como PAS, AIDA, etc.) — no es solo escribir bien. Sabe cuándo usar qué framework.

**Prompts de práctica:**
```
Escribe el hero de la homepage para [empresa]. 
El visitante típico es [descripción]. El CTA principal es "Empezar gratis".
```
```
Reescribe esta sección de beneficios para que sea más convincente:
[pegar texto actual]
```

**Demo impactante:** Pega copy real del sitio web del cliente de la agencia y pide que lo mejore. El cliente ve resultados inmediatos.

---

### `copy-editing` — Editar Copy Existente
**Qué hace:** Toma texto ya escrito y lo pule — tono, claridad, voz de marca.

**Diferencia con `copywriting`:** `copywriting` escribe desde cero. `copy-editing` mejora lo que ya existe.

**Prompt de práctica:**
```
Edita este texto de email para que suene más conversacional y menos corporativo:
[pegar texto]
```

---

### `cold-email` — Emails en Frío B2B
**Qué hace:** Escribe secuencias de prospección B2B. No emails genéricos — emails que parecen escritos por un par, no por un vendedor.

**Para agencias de marketing:** Utilísimo para ayudar al equipo de ventas de sus clientes a prospectar.

**Prompts de práctica:**
```
Escribe un email en frío para el Director de Marketing de medianas empresas de retail.
Vendemos una plataforma de automatización de email. 
Diferenciador: configuración en 1 día vs. semanas de los competidores.
```

**Señal de calidad:** El asunto debe ser corto (2-4 palabras), minúsculas, no parece marketing.

---

### `email-sequence` — Secuencias de Email
**Qué hace:** Diseña y escribe secuencias completas de email automatizadas (bienvenida, nurture, reactivación, etc.)

**Para agencias:** Los clientes de la agencia siempre necesitan secuencias. Esta skill las produce rápido y bien.

**Prompts de práctica:**
```
Crea una secuencia de bienvenida de 5 emails para nuevos usuarios de [producto SaaS].
El objetivo es llevarlos a completar su primera [acción clave] en los primeros 7 días.
```

---

### `social-content` — Contenido para Redes Sociales
**Qué hace:** Posts para LinkedIn, Twitter/X, Instagram. Adaptado a cada plataforma.

**Para agencias:** Una de las tareas más repetitivas que hacen para sus clientes. Esta skill acelera muchísimo.

**Prompts de práctica:**
```
Crea 5 posts de LinkedIn para [empresa]. 
Tema: lanzamiento de nueva funcionalidad de [X].
Tono: profesional pero cercano.
```

---

### `content-strategy` — Estrategia de Contenido
**Qué hace:** Define QUÉ contenido crear, para qué audiencia, con qué frecuencia y qué temas cubrir.

**Cuándo usarla:** Al inicio de un proyecto de contenido — antes de ponerse a escribir nada.

**Prompt de práctica:**
```
Crea una estrategia de contenido para [empresa B2B SaaS] 
para los próximos 3 meses. Queremos generar leads calificados.
```

---

## BLOQUE 3: SEO y Descubrimiento

### `seo-audit` — Auditoría de SEO
**Qué hace:** Diagnostica problemas de SEO técnico, on-page y de estructura.

**Para agencias:** Herramienta de diagnóstico rápido para mostrarle al cliente qué está mal en su SEO antes de proponer soluciones.

**Prompt de práctica:**
```
Audita el SEO de [sitio web]. 
Tengo acceso a Google Search Console y veo que el tráfico bajó 30% en los últimos 3 meses.
```

---

### `ai-seo` — SEO para IA
**La más nueva y diferencial.** Optimiza para aparecer en ChatGPT, Perplexity, Google AI Overviews.

**Por qué importa:** Cada vez más personas buscan en IA, no en Google. Esta skill cubre ese canal nuevo.

**Prompt de práctica:**
```
¿Cómo optimizamos el contenido de [empresa] para que aparezca 
cuando alguien le pregunte a ChatGPT por [su categoría de producto]?
```

**Demo WOW:** Pregúntale a ChatGPT por la categoría de tu cliente. Si no aparece, ahí está el problema. Luego muestra cómo esta skill lo resuelve.

---

### `programmatic-seo` — SEO Programático
**Qué hace:** Crea estrategias para generar cientos de páginas de alta intención usando plantillas + datos.

**Para qué tipo de clientes:** Empresas con muchas variantes (ubicaciones, categorías, comparaciones). Ej: "agencia de marketing en [ciudad]", "[herramienta] vs [competidor]".

---

### `site-architecture` — Arquitectura del Sitio
**Qué hace:** Planifica estructura de páginas, jerarquía, navegación, URLs.

**Cuándo usarla:** Cliente va a rediseñar o lanzar sitio web nuevo.

**Prompt de práctica:**
```
Planifica la arquitectura del sitio para [empresa SaaS B2B].
Tienen: homepage, producto, precios, blog. Quieren agregar casos de estudio y comparaciones.
```

---

### `competitor-alternatives` — Páginas de Comparación
**Qué hace:** Crea páginas de "[Tu producto] vs [Competidor]" y "[Competidor] alternativas".

**Por qué es poderoso:** Este tipo de páginas atrae usuarios que YA están considerando comprar — la intención más alta posible.

---

### `schema-markup` — Datos Estructurados
**Qué hace:** Genera e implementa JSON-LD para rich snippets en Google.

**Para quién:** Clientes que quieren aparecer con estrellas, FAQs, o precios en los resultados de búsqueda.

---

## BLOQUE 4: Publicidad Paga

### `paid-ads` — Estrategia de Campañas
**Qué hace:** Estructura campañas en Google, Meta, LinkedIn, TikTok. Segmentación, objetivos, presupuesto.

**Para agencias:** El "cerebro" de la campaña — la estrategia y estructura antes de crear los anuncios.

---

### `ad-creative` — Creativos Publicitarios
**Qué hace:** Genera titulares, copy principal, variantes de anuncios en volumen.

**La combinación poderosa:** `paid-ads` (estrategia) + `ad-creative` (ejecución) = campaña completa.

**Prompt de práctica:**
```
Genera 10 titulares para anuncios de Google Search para [empresa].
La keyword principal es "[X]". El diferenciador es [Y].
```

---

## BLOQUE 5: Medición y Pruebas

### `analytics-tracking` — Configurar Analítica
**Qué hace:** Define qué eventos rastrear, cómo configurar GA4, GTM, Mixpanel, Segment.

**Para agencias:** Muchos clientes tienen analítica mal configurada. Esta skill ayuda a definir qué medir y cómo.

---

### `ab-test-setup` — Pruebas A/B
**Qué hace:** Diseña experimentos estadísticamente válidos. Hipótesis, tamaño de muestra, métricas.

**El error más común que evita:** Detener un test antes de tiempo porque "ya hay un ganador" (el "peeking problem").

---

## BLOQUE 6: Retención y Growth

### `churn-prevention` — Prevención de Churn
**Qué hace:** Diseña flujos de cancelación, ofertas de retención, secuencias de dunning (pagos fallidos).

**Para clientes con:** Suscripciones. Crítico para SaaS.

---

### `referral-program` — Programa de Referidos
**Qué hace:** Diseña estructuras de incentivos, mecánicas del programa, copy.

**La pregunta clave para el cliente:** ¿Cuánto vale un cliente nuevo? (LTV) — ese número determina qué incentivo puedes dar.

---

### `free-tool-strategy` — Estrategia de Herramientas Gratuitas
**Qué hace:** Planifica herramientas gratuitas (calculadoras, generators) para generar leads y backlinks.

**Ejemplo:** Hubspot tiene el "Website Grader" gratuito → genera miles de leads.

---

## BLOQUE 7: Estrategia

### `marketing-ideas` — Banco de Ideas
**Qué hace:** Genera ideas de marketing para SaaS — tiene más de 140 indexadas por categoría.

**Para usar cuando:** Un cliente está estancado y no sabe qué probar.

---

### `marketing-psychology` — Psicología del Marketing
**Qué hace:** Aplica principios de ciencia del comportamiento (urgencia, escasez, prueba social, etc.) a cualquier pieza de marketing.

**No es una skill independiente — es una lente** que potencia todo lo demás.

**Prompt de práctica:**
```
¿Qué principios de psicología del comportamiento podemos aplicar 
a la página de precios de [empresa] para aumentar conversiones?
```

---

### `launch-strategy` — Estrategia de Lanzamiento
**Qué hace:** Planifica el lanzamiento de un producto, funcionalidad o campaña.

**Para agencias:** Cuando un cliente lanza algo nuevo, esta skill crea el plan completo (emails, redes, ads, PR).

---

### `pricing-strategy` — Estrategia de Precios
**Qué hace:** Estructura de niveles, freemium vs. trial, precios enterprise, investigación de disposición a pagar.

**Demo WOW:** Muchos clientes de agencias tienen precios mal estructurados. Esta skill puede mostrar problemas inmediatos.

---

## BLOQUE 8: Ventas y Operaciones

### `revops` — Operaciones de Ingresos
**Qué hace:** Scoring de leads, enrutamiento, definición de MQL/SQL, gestión del pipeline, automatización de CRM.

**Para qué clientes:** Los que tienen equipo de ventas y sienten que marketing no está generando leads que ventas pueda cerrar.

---

### `sales-enablement` — Habilitación de Ventas
**Qué hace:** Pitch decks, one-pagers, documentos de manejo de objeciones, scripts de demo.

**Para agencias:** Cuando los clientes necesitan material para que su equipo de ventas cierre mejor.

---

## Flujos Combinados (los más poderosos)

Estas combinaciones de skills son donde realmente brillas ante un cliente:

### Flujo "Mejorar Conversiones"
```
1. page-cro → identificar qué cambiar
2. copywriting → reescribir el copy
3. ab-test-setup → diseñar el experimento
4. analytics-tracking → asegurarse de poder medir
```

### Flujo "Lanzar Campaña de Contenido"
```
1. content-strategy → definir qué crear
2. copywriting → escribir las piezas
3. social-content → adaptar para redes
4. email-sequence → secuencia de distribución por email
5. paid-ads → amplificar con pauta
```

### Flujo "Arrancar desde Cero con Cliente Nuevo"
```
1. product-marketing-context → capturar el contexto del cliente
2. seo-audit → diagnóstico de SEO
3. page-cro → auditoría de la homepage
4. content-strategy → plan de contenido
```

### Flujo "Aumentar Ventas B2B"
```
1. revops → ordenar el pipeline
2. cold-email → secuencias de prospección
3. sales-enablement → materiales para cerrar
4. competitor-alternatives → páginas para inbound
```

---

## Cómo Preparar una Demo

**La regla de oro:** Nunca demuestres una skill con datos inventados. Siempre usa el negocio real del cliente.

### Antes de la reunión:
1. Investiga el negocio del cliente (5-10 min)
2. Identifica UN problema obvio que tienen (mala homepage, no tienen blog, etc.)
3. Prepara el `product-marketing-context` con lo que ya sabes de ellos

### Durante la demo:
1. Muestra la skill resolviendo SU problema específico
2. Involúcralos — pídeles que ellos escriban el prompt
3. Mostra cómo el resultado cambia cuando añades más contexto

### Las mejores skills para demo en vivo:
- `copywriting` — resultados visibles en segundos
- `page-cro` — audita su propia página en tiempo real
- `ai-seo` — muéstrales que no aparecen en ChatGPT
- `email-sequence` — escribe emails para su propio negocio

---

## Cómo Personalizar una Skill

Cuando el output de una skill no es exactamente lo que el cliente necesita, puedes ajustarla:

### 1. Ajustar el prompt
Agrega restricciones:
```
Usa un tono más formal. No uses preguntas retóricas. 
El cliente es conservador y desconfía de promesas exageradas.
```

### 2. Editar el SKILL.md
Abre el archivo y añade una sección de "Contexto Adicional" con las preferencias del cliente.

### 3. Crear una skill nueva
Si un cliente tiene un caso de uso muy específico que se repetirá (ej: "reportes semanales para clientes"), crear una skill nueva para eso. La estructura es simple:
```yaml
---
name: nombre-de-la-skill
description: Cuándo usarla. Palabras clave que la activan.
---

# Título

Instrucciones para el agente...
```

---

## Señales de que una Skill Está Funcionando Bien

- El output es específico, no genérico
- Usa el lenguaje del cliente (del product-marketing-context)
- Da recomendaciones accionables, no vagas
- Hace preguntas cuando le falta contexto

## Señales de que Falta Contexto

- Output muy genérico ("mejora tu propuesta de valor")
- No menciona el producto ni la audiencia específica
- Podría servir para cualquier empresa

**Solución:** Siempre asegúrate de que el `product-marketing-context.md` esté bien llenado antes de usar cualquier skill.
