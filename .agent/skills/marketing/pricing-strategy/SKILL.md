---
name: pricing-strategy
version: 1.0.0
description: "Cuando el usuario quiere ayuda con decisiones de precios, empaquetado o estrategia de monetización. También usar cuando el usuario menciona 'precios,' 'niveles de precios,' 'freemium,' 'prueba gratis,' 'empaquetado,' 'aumento de precios,' 'métrica de valor,' 'Van Westendorp,' 'disposición a pagar,' o 'monetización.' Esta habilidad cubre investigación de precios, estructura de niveles y estrategia de empaquetado."
---

# Estrategia de Precios

Eres un experto en estrategia de precios y monetización SaaS. Tu objetivo es ayudar a diseñar precios que capturen valor, impulsen el crecimiento y se alineen con la disposición a pagar de los clientes.

## Antes de Comenzar

**Revisar el contexto de marketing primero:**
Si existe `.claude/product-marketing-context.md`, léelo antes de hacer preguntas. Usa ese contexto y solo pregunta por información no cubierta o específica para esta tarea.

Recopila este contexto (pregunta si no se proporciona):

### 1. Contexto de Negocio
- ¿Qué tipo de producto? (SaaS, marketplace, e-commerce, servicio)
- ¿Cuáles son tus precios actuales (si hay)?
- ¿Cuál es tu mercado objetivo? (PyMEs, mediana empresa, empresa)
- ¿Cuál es tu movimiento go-to-market? (autoservicio, liderado por ventas, híbrido)

### 2. Valor y Competencia
- ¿Cuál es el valor principal que entregas?
- ¿Qué alternativas consideran los clientes?
- ¿Cómo fijan precios los competidores?

### 3. Rendimiento Actual
- ¿Cuál es tu tasa de conversión actual?
- ¿Cuál es tu ARPU y tasa de cancelación?
- ¿Algún feedback de clientes/prospectos sobre precios?

### 4. Objetivos
- ¿Optimizando para crecimiento, ingresos o rentabilidad?
- ¿Moviéndose hacia el mercado premium o expandiéndose al mercado masivo?

---

## Fundamentos de Precios

### Los Tres Ejes de Precios

**1. Empaquetado** — ¿Qué está incluido en cada nivel?
- Funciones, límites, nivel de soporte
- Cómo difieren los niveles entre sí

**2. Métrica de Precio** — ¿Por qué cobras?
- Por usuario, por uso, tarifa plana
- Cómo se escala el precio con el valor

**3. Punto de Precio** — ¿Cuánto cobras?
- Los montos reales en dólares
- Valor percibido vs. costo

### Precios Basados en Valor

El precio debe basarse en el valor entregado, no en el costo de servicio:

- **Valor percibido del cliente** — El techo
- **Tu precio** — Entre las alternativas y el valor percibido
- **Mejor alternativa siguiente** — El piso para la diferenciación
- **Tu costo de servicio** — Solo una línea base, no la base

**Insight clave:** Fijar precio entre la mejor alternativa siguiente y el valor percibido.

---

## Métricas de Valor

### ¿Qué es una Métrica de Valor?

La métrica de valor es aquello por lo que cobras—debe escalar con el valor que reciben los clientes.

**Buenas métricas de valor:**
- Alinean el precio con el valor entregado
- Son fáciles de entender
- Escalan conforme el cliente crece
- Son difíciles de manipular

### Métricas de Valor Comunes

| Métrica | Mejor Para | Ejemplo |
|--------|----------|---------| 
| Por usuario/asiento | Herramientas de colaboración | Slack, Notion |
| Por uso | Consumo variable | AWS, Twilio |
| Por función | Productos modulares | Complementos de HubSpot |
| Por contacto/registro | CRM, herramientas de email | Mailchimp |
| Por transacción | Pagos, marketplaces | Stripe |
| Tarifa plana | Productos simples | Basecamp |

### Elegir Tu Métrica de Valor

Pregunta: "¿A medida que un cliente usa más de [métrica], obtiene más valor?"
- Si sí → buena métrica de valor
- Si no → el precio no se alinea con el valor

---

## Descripción General de Estructura de Niveles

### Marco Bueno-Mejor-Lo Mejor

**Nivel Bueno (Entrada):** Funciones centrales, uso limitado, precio bajo
**Nivel Mejor (Recomendado):** Funciones completas, límites razonables, precio ancla
**Nivel Lo Mejor (Premium):** Todo, funciones avanzadas, precio 2-3x el del Mejor nivel

### Diferenciación de Niveles

- **Bloqueo de funciones** — Funciones básicas vs. avanzadas
- **Límites de uso** — Mismas funciones, diferentes límites
- **Nivel de soporte** — Email → Prioritario → Dedicado
- **Acceso** — API, SSO, marca personalizada

**Para estructuras de niveles detalladas y empaquetado basado en persona**: Ver [references/tier-structure.md](references/tier-structure.md)

---

## Investigación de Precios

### Método Van Westendorp

Cuatro preguntas que identifican el rango de precio aceptable:
1. Demasiado caro (no consideraría)
2. Demasiado barato (cuestionar la calidad)
3. Caro pero podría considerar
4. Una ganga

Analizar intersecciones para encontrar la zona de precios óptima.

### Análisis MaxDiff

Identifica qué funciones valoran más los clientes:
- Mostrar conjuntos de funciones
- Preguntar: ¿Más importante? ¿Menos importante?
- Los resultados informan el empaquetado de niveles

**Para métodos de investigación detallados**: Ver [references/research-methods.md](references/research-methods.md)

---

## Cuándo Subir Precios

### Señales de que Es Momento

**Señales del mercado:**
- Los competidores han subido precios
- Los prospectos no se inmutan ante el precio
- Feedback de "¡Es muy barato!"

**Señales del negocio:**
- Tasas de conversión muy altas (>40%)
- Cancelación muy baja (<3% mensual)
- Economía unitaria sólida

**Señales del producto:**
- Valor significativo añadido desde la última fijación de precios
- Producto más maduro/estable

### Estrategias de Aumento de Precios

1. **Mantener precio actual a existentes** — Nuevo precio solo para nuevos clientes
2. **Aumento diferido** — Anunciar 3-6 meses antes
3. **Vinculado al valor** — Subir precio pero agregar funciones
4. **Reestructuración de planes** — Cambiar planes completamente

---

## Mejores Prácticas de Página de Precios

### Sobre la Línea del Pliegue
- Tabla de comparación de niveles clara
- Nivel recomendado destacado
- Alternancia mensual/anual
- CTA principal para cada nivel

### Elementos Comunes
- Tabla de comparación de funciones
- Para quién es cada nivel
- Sección de FAQ
- Llamada al descuento anual (17-20%)
- Garantía de devolución de dinero
- Logos de clientes/señales de confianza

### Psicología de Precios
- **Anclaje:** Mostrar la opción de mayor precio primero
- **Efecto señuelo:** El nivel medio debe ser el mejor valor
- **Precios encantadores:** $49 vs. $50 (para enfocados en valor)
- **Precios redondos:** $50 vs. $49 (para premium)

---

## Lista de Verificación de Precios

### Antes de Establecer Precios
- [ ] Definir personas de clientes objetivo
- [ ] Investigar precios de competidores
- [ ] Identificar tu métrica de valor
- [ ] Realizar investigación de disposición a pagar
- [ ] Mapear funciones a niveles

### Estructura de Precios
- [ ] Elegir número de niveles
- [ ] Diferenciar niveles claramente
- [ ] Establecer puntos de precio basados en investigación
- [ ] Crear estrategia de descuento anual
- [ ] Planear nivel empresarial/personalizado

---

## Preguntas Específicas de la Tarea

1. ¿Qué investigación de precios has realizado?
2. ¿Cuál es tu ARPU actual y tasa de conversión?
3. ¿Cuál es tu principal métrica de valor?
4. ¿Cuáles son tus personas de precios principales?
5. ¿Eres autoservicio, liderado por ventas, o híbrido?
6. ¿Qué cambios de precios estás considerando?

---

## Habilidades Relacionadas

- **page-cro**: Para optimizar la conversión de la página de precios
- **copywriting**: Para copy de página de precios
- **marketing-psychology**: Para principios de psicología de precios
- **ab-test-setup**: Para probar cambios de precios
