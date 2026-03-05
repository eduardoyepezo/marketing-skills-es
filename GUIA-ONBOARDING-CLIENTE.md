# Guía de Onboarding — Sistema de Marketing con IA

Bienvenido al sistema de Marketing Skills. Esta guía te explica cómo configurarlo para cada uno de tus clientes y empezar a usarlo desde el primer día.

---

## ¿Cómo Funciona el Sistema?

El sistema funciona con **skills** — archivos de instrucciones que le dan a tu agente de IA (Claude, Cursor, Windsurf u otro) conocimiento especializado en marketing. Cuando describes una tarea, el agente detecta automáticamente qué skill usar y aplica los marcos y mejores prácticas correctos.

**La clave:** Las skills se instalan una sola vez. Para cada cliente tuyo creas una carpeta separada con su propio contexto. El agente lee ese contexto y trabaja específicamente para ese cliente.

---

## Estructura por Cliente

Para cada cliente que manejas, la estructura es:

```
📁 Cliente-NombreEmpresa/
├── 📄 .agents/product-marketing-context.md   ← contexto de este cliente
└── 📁 (archivos de trabajo del cliente)
```

El sistema de skills está instalado globalmente — no necesitas copiar nada. Solo debes crear la carpeta del cliente y configurar su contexto.

---

## Paso 1: Instalar el Sistema (Solo Una Vez)

Sigue las instrucciones de instalación que te proporcionó tu consultor. Una vez instalado, el sistema estará disponible en todos tus proyectos.

**Verificar que funciona:**
En cualquier carpeta, escribe:
```
/product-marketing-context
```
Si el agente responde con preguntas sobre el producto, el sistema está funcionando.

---

## Paso 2: Configurar un Cliente Nuevo

### 2.1 Crear la carpeta del cliente

```bash
mkdir "Cliente-NombreEmpresa"
cd "Cliente-NombreEmpresa"
```

### 2.2 Configurar el contexto del cliente

Abre tu agente de IA en esa carpeta y escribe:
```
/product-marketing-context
```

El agente te hará preguntas. Ten a mano esta información del cliente:

**Información que necesitas del cliente antes de esta sesión:**

| Categoría | Información |
|-----------|------------|
| **El negocio** | ¿Qué venden exactamente? ¿Cómo funciona? ¿Modelo de negocio? |
| **Sus clientes** | ¿Quién les compra? ¿Qué cargo tienen? ¿En qué industria? ¿Tamaño de empresa? |
| **El problema** | ¿Qué dolor específico resuelven? ¿Por qué sus clientes los buscan? |
| **Diferenciador** | ¿En qué son mejores o diferentes a los competidores? |
| **Competidores** | ¿Contra quién compiten directamente? ¿Indirectamente? |
| **Tono de marca** | ¿Cómo hablan? ¿Formal o casual? ¿Técnico o simple? |
| **Métricas actuales** | ¿Tráfico web? ¿Tasa de conversión? ¿Costo de adquisición? |
| **Objetivo principal** | ¿Qué quieren mejorar en los próximos 3 meses? |

El agente guardará todo en `.agents/product-marketing-context.md`. Puedes editarlo manualmente después si necesitas ajustar algo.

---

## Paso 3: Las Skills Disponibles

Una vez configurado el contexto, tienes 32 skills disponibles organizadas por área:

### Optimización de Conversiones (CRO)

| Skill | Úsala cuando... |
|-------|----------------|
| `/page-cro` | Quieres mejorar las conversiones de cualquier página del sitio |
| `/signup-flow-cro` | El cliente pierde usuarios en el proceso de registro |
| `/onboarding-cro` | Los usuarios se registran pero no usan el producto |
| `/form-cro` | Tienes formularios de captura de leads que no convierten |
| `/popup-cro` | Quieres crear o mejorar popups y modales |
| `/paywall-upgrade-cro` | Quieres mejorar las pantallas de upgrade dentro del producto |

### Contenido y Copy

| Skill | Úsala cuando... |
|-------|----------------|
| `/copywriting` | Necesitas escribir o reescribir copy para cualquier página |
| `/copy-editing` | Tienes copy existente que necesita mejoras de tono y claridad |
| `/cold-email` | El cliente necesita secuencias de prospección B2B |
| `/email-sequence` | Necesitas secuencias de email automatizadas (bienvenida, nurture, etc.) |
| `/social-content` | Necesitas posts para LinkedIn, Instagram, Twitter/X |
| `/content-strategy` | Quieres planificar qué contenido crear en los próximos meses |

### SEO y Visibilidad

| Skill | Úsala cuando... |
|-------|----------------|
| `/seo-audit` | El cliente quiere diagnosticar sus problemas de SEO |
| `/ai-seo` | Quieres aparecer en ChatGPT, Perplexity, Google AI Overviews |
| `/programmatic-seo` | Quieres crear muchas páginas de SEO a escala con plantillas |
| `/site-architecture` | El cliente va a rediseñar o lanzar su sitio web |
| `/competitor-alternatives` | Quieres páginas de comparación con competidores |
| `/schema-markup` | Quieres rich snippets (estrellas, FAQs) en Google |

### Publicidad Paga

| Skill | Úsala cuando... |
|-------|----------------|
| `/paid-ads` | Quieres planificar campañas en Google, Meta, LinkedIn, TikTok |
| `/ad-creative` | Necesitas generar muchas variantes de anuncios y copy publicitario |

### Medición y Experimentos

| Skill | Úsala cuando... |
|-------|----------------|
| `/analytics-tracking` | El cliente necesita configurar o mejorar su analítica (GA4, GTM) |
| `/ab-test-setup` | Quieres diseñar pruebas A/B estadísticamente válidas |

### Retención y Growth

| Skill | Úsala cuando... |
|-------|----------------|
| `/churn-prevention` | El cliente pierde suscriptores o tiene pagos fallidos |
| `/referral-program` | Quieres crear un programa de referidos o afiliados |
| `/free-tool-strategy` | Quieres crear una herramienta gratuita para generar leads |

### Estrategia

| Skill | Úsala cuando... |
|-------|----------------|
| `/marketing-ideas` | El cliente está estancado y necesita ideas nuevas |
| `/marketing-psychology` | Quieres aplicar principios de comportamiento a cualquier pieza |
| `/launch-strategy` | El cliente va a lanzar un producto, funcionalidad o campaña |
| `/pricing-strategy` | El cliente quiere revisar o mejorar su estructura de precios |

### Ventas y Operaciones

| Skill | Úsala cuando... |
|-------|----------------|
| `/revops` | El cliente necesita ordenar su pipeline de ventas y sistema de leads |
| `/sales-enablement` | Necesitas pitch decks, one-pagers o scripts de ventas |

---

## Paso 4: Cómo Invocar una Skill

### Opción 1: Comando directo
```
/page-cro
```
El agente leerá automáticamente el contexto del cliente y empezará.

### Opción 2: Descripción natural
```
Quiero auditar la homepage del cliente para mejorar las conversiones
```
El agente detecta que debe usar `page-cro`.

### Opción 3: Con instrucciones adicionales
```
/copywriting — quiero reescribir la sección "Cómo funciona" de la web. 
El tono debe ser más conversacional que el actual. Aquí está el texto actual: [...]
```

---

## Paso 5: Flujos de Trabajo por Objetivo del Cliente

### "Quiero más leads"
```
1. /page-cro          → ¿Qué está frenando las conversiones en el sitio?
2. /form-cro          → Optimizar el formulario de captura
3. /content-strategy  → Plan de contenido para atraer al buyer
4. /paid-ads          → Campaña de pauta para amplificar
```

### "Quiero mejorar mi SEO"
```
1. /seo-audit          → Diagnóstico de problemas actuales
2. /site-architecture  → Estructura de páginas
3. /content-strategy   → Qué contenido crear para posicionar
4. /schema-markup      → Datos estructurados para rich snippets
5. /ai-seo             → Optimizar para búsqueda en IA
```

### "Quiero lanzar algo nuevo"
```
1. /launch-strategy    → Plan completo de lanzamiento
2. /copywriting        → Copy del anuncio y página
3. /email-sequence     → Secuencia de emails del lanzamiento
4. /social-content     → Posts de soporte en redes
5. /paid-ads           → Campaña de amplificación
```

### "Mis ventas no están cerrando"
```
1. /revops             → Revisar pipeline y scoring de leads
2. /cold-email         → Mejorar secuencias de prospección
3. /sales-enablement   → Materiales para el equipo de ventas
4. /competitor-alternatives → Páginas de comparación para inbound
```

### "Tengo mucho churn"
```
1. /churn-prevention   → Flujos de retención y dunning
2. /email-sequence     → Secuencia de reactivación
3. /onboarding-cro     → ¿El problema es que no activan bien?
4. /analytics-tracking → ¿Puedo medir cuándo se van?
```

---

## Buenas Prácticas

### ✅ Hacer
- **Siempre configurar el contexto del cliente primero** antes de usar cualquier skill
- **Dar contexto específico** en cada prompt — no solo invocar la skill en vacío
- **Revisar el output** y pedir iteraciones si algo no está bien
- **Actualizar el `product-marketing-context.md`** cuando conozcas mejor al cliente

### ❌ Evitar
- No usar skills sin contexto del cliente — el output será genérico e inútil
- No compartir la carpeta de un cliente con otro (cada quien tiene su contexto)
- No asumir que el primer output es el final — siempre pide refinamientos
- No olvidar incluir métricas actuales del cliente cuando las tengas (mejora enormemente el output)

---

## Cuando el Output No es lo que Esperabas

**Si el resultado es muy genérico:**
→ El `product-marketing-context.md` probablemente está incompleto. Edítalo y agrega más detalle.

**Si el tono no es el correcto:**
→ Agrega instrucciones específicas: "Usa un tono más [formal/casual/técnico]. Evita [X]."

**Si falta información del cliente:**
→ Proporciona el contexto faltante directamente en el prompt.

**Si la skill no existe para tu caso de uso:**
→ Habla con tu consultor — puede que sea el momento de crear una skill personalizada.

---

## Preguntas Frecuentes

**¿Puedo usar más de una skill en la misma conversación?**
Sí. El agente mantiene el contexto de la sesión. Puedes encadenar: "ahora toma el copy que escribiste y conviértelo en 5 posts de LinkedIn" → invocará `social-content` automáticamente.

**¿Cuántos clientes puedo manejar con el sistema?**
Ilimitados. Cada carpeta de cliente es independiente.

**¿El sistema aprende de mis clientes o guarda información?**
No — cada sesión es independiente. El único "aprendizaje" es el contenido del `product-marketing-context.md` que tú construyes.

**¿Puedo editar una skill si no me gusta cómo funciona?**
Sí, con apoyo de tu consultor puedes modificar las skills existentes o crear nuevas adaptadas a tu flujo de trabajo.

---

## Soporte

Para dudas, nuevas skills o personalización del sistema, contacta a tu consultor:
**[Tu nombre / datos de contacto]**
