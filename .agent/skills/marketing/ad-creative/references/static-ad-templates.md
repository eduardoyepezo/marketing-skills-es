# Biblioteca de Plantillas de Anuncios Estáticos

Quince plantillas estructurales para creatividades de anuncios estáticos (imagen). Cada una es un framework de layout con slots para copy específico de la marca — la estructura está probada; los insumos la hacen tuya.

Usa estas al generar conceptos de anuncios estáticos a volumen (Meta, Instagram, LinkedIn, display). Recorre **todas** las plantillas en vez de concentrarte en 2-3 favoritas: la diversidad de plantillas es diversidad de ángulos, y el ganador usualmente no es el que hubieras elegido a mano.

## Cómo Usar Esta Biblioteca

1. **Ancla primero.** Lee el corpus de insumos (anuncios ganadores, reseñas, comentarios de anuncios, voz de marca) antes de generar cualquier cosa. Ver "Insumos con Base en la Realidad" en SKILL.md.
2. **Recorre las plantillas.** Para un lote de N conceptos, distribuye entre las 15 plantillas (3-4 variaciones cada una para un lote de 50 conceptos).
3. **Llena los slots desde material fuente.** Cada variación extrae su copy de una reseña real, un patrón de anuncio ganador, o un comentario de anuncio — y cita cuál.
4. **Escribe la descripción visual.** Cada concepto incluye suficiente dirección visual para que un diseñador o una herramienta de generación de imagen pueda producirlo sin adivinar.

## Reglas de Generación

- Cada variación debe incluir: **nombre de plantilla, copy de titular, copy de cuerpo, descripción visual, anclaje de fuente**
- Anclaje de fuente = a qué reseña, anuncio ganador o comentario se basa este concepto
- Nunca produzcas una variación sin anclaje de fuente — sin afirmaciones, estadísticas o testimonios inventados
- Extrae copy directamente del lenguaje del cliente siempre que sea posible; no parafrasees reseñas hacia lenguaje de marketing
- Iguala el documento de voz de marca en tono, no una voz genérica de respuesta directa
- Solo nombres reales, estadísticas reales, citas reales — la prueba social fabricada es una violación de cumplimiento y de confianza

---

## Las 15 Plantillas

### 1. Declaración de Titular

Afirmación audaz en una línea. Toma hero de producto único. Fondo mínimo. El titular hace todo el trabajo.

- **Estructura**: Una línea de texto dominante (60%+ del peso visual), imagen de producto, logo pequeño
- **Slot de copy**: Una afirmación lo suficientemente específica como para detener el scroll
- **Ejemplo DTC**: "El último polvo verde que comprarás jamás."
- **Ejemplo SaaS**: "Cierra tus libros contables en 3 días, no en 3 semanas."
- **Extráelo de**: Tu hook de anuncio ganador más fuerte o el beneficio más repetido en las reseñas

### 2. Nosotros vs. Ellos

Comparación lado a lado. Competidor o "la vieja forma" a la izquierda (en gris), tu producto a la derecha (a todo color). 4-6 filas de comparación.

- **Estructura**: Dos columnas, marcas de check/cruz por fila, tu lado visualmente vivo
- **Slot de copy**: Filas de comparación — cada fila un diferenciador real, no relleno
- **Ejemplo DTC**: "Su multivitamínico: 13 ingredientes. El nuestro: 60."
- **Ejemplo SaaS**: "Hojas de cálculo: 6 horas a la semana. Nosotros: 6 minutos."
- **Extráelo de**: Reseñas que mencionan un cambio de proveedor, o comentarios que te comparan con un competidor

### 3. Stat Callout

Un número dominante ocupa el 60% del visual. Contexto de apoyo debajo.

- **Estructura**: Estadística gigante, una línea de contexto, ancla de producto o logo
- **Slot de copy**: Un número real y defendible — la medición vence al superlativo
- **Ejemplo DTC**: "97% de los usuarios sienten una diferencia en 14 días."
- **Ejemplo SaaS**: "11 horas ahorradas por representante, por semana."
- **Extráelo de**: Casos de estudio, analítica de producto, o datos de encuestas — nunca inventes el número

### 4. Review Card

Un testimonio de cinco estrellas estilizado como una reseña de producto capturada en pantalla. Nombre del reseñador, calificación en estrellas, fecha.

- **Estructura**: Se ve como una UI de reseña nativa (G2, Trustpilot, Amazon, App Store — coincide con donde tus compradores leen reseñas)
- **Slot de copy**: Una reseña real, textual — la credibilidad del artefacto es su realismo
- **Ejemplo DTC**: Una tarjeta de Trustpilot: "He probado 6 de estos. Este es el único que volví a comprar."
- **Ejemplo SaaS**: Una tarjeta estilo G2: "Eliminó 4 herramientas y las reemplazó con esta."
- **Extráelo de**: `inputs/reviews/` textualmente — con permiso donde la plataforma lo requiera

### 5. Testimonial Stack

Tres citas de clientes organizadas verticalmente, foto + nombre + una cita de una línea cada una.

- **Estructura**: Tres filas cortas; las citas deben ser escaneables en 2 segundos cada una
- **Slot de copy**: Tres citas cubriendo objeciones o beneficios *diferentes* — no el mismo elogio tres veces
- **Ejemplo DTC**: Tres clientes hablando de resultados, sabor y conveniencia
- **Ejemplo SaaS**: Tres roles (IC, manager, ejecutivo) cada uno elogiando su propio resultado
- **Extráelo de**: Reseñas — elige por cobertura, no solo por entusiasmo

### 6. Antes / Después

Imagen dividida con flecha entre medio. Encuadre de transformación — resultados de producto, flujo de trabajo, o prueba visual.

- **Estructura**: Dos paneles, flecha o divisor, copy mínimo etiquetando cada estado
- **Slot de copy**: Etiqueta los estados con las palabras del cliente ("El pavor de la hoja de cálculo del domingo por la noche" → "Los reportes se envían solos")
- **Ejemplo DTC**: Piel, energía, espacio — la transformación visual clásica
- **Ejemplo SaaS**: Flujo de trabajo desordenado de 6 pestañas → un dashboard limpio
- **Nota de cumplimiento**: Las afirmaciones de antes/después están reguladas en salud, finanzas y belleza — verifica la política de la plataforma antes de usar
- **Extráelo de**: Lenguaje de transformación en las reseñas ("Antes hacía X, ahora hago Y")

### 7. Problema / Solución

Punto de dolor arriba (texto o imagen), producto como la respuesta abajo.

- **Estructura**: Dos zonas — tensión arriba, alivio abajo
- **Slot de copy**: El dolor en las palabras exactas del cliente, luego la respuesta de una línea del producto
- **Ejemplo DTC**: "¿Cansado de tomar 6 suplementos cada mañana?" → visual de una sola cucharada
- **Ejemplo SaaS**: "Tu CRM no sabe nada sobre el uso del producto." → captura de integración
- **Extráelo de**: El fraseo de dolor más común en `inputs/reviews/` — textual vence a la paráfrasis

### 8. Mensaje del Fundador

Nota estilo manuscrita o de texto plano del fundador. Tono conversacional, personal.

- **Estructura**: Layout tipo nota, nombre/foto del fundador, sin toma glamorosa del producto
- **Slot de copy**: "Construí esto porque..." — un párrafo honesto, sin pulido de marketing
- **Ejemplo DTC**: "Hola — hice esto porque cada snack 'saludable' era en secreto un dulce."
- **Ejemplo SaaS**: "Manejé RevOps durante 6 años. Esta es la herramienta que deseaba que existiera."
- **Extráelo de**: La historia real de fundación — esta plantilla colapsa si se fabrica

### 9. Feature Spotlight (Ingredient Spotlight)

Toma hero del producto en el centro, 4-6 cajas de callout alrededor de los bordes destacando componentes clave.

- **Estructura**: Imagen central, callouts que irradian, cada callout de 3-6 palabras
- **Slot de copy**: Los componentes que los compradores realmente preguntan — no tu lista completa de características
- **Ejemplo DTC**: Botella de producto con callouts por cada ingrediente clave y qué hace
- **Ejemplo SaaS**: Captura del dashboard con callouts sobre las 4 características que más mencionan las reseñas
- **Extráelo de**: Qué características/ingredientes aparecen más en reseñas y comentarios

### 10. Mención de Prensa

"Como se vio en" con logos de publicaciones y una cita destacada.

- **Estructura**: Fila de logos + una cita fuerte + ancla de producto
- **Slot de copy**: Una cita real de cobertura real
- **Ejemplo DTC**: "La primera idea genuinamente nueva de la categoría en años." — [publicación]
- **Ejemplo SaaS**: Cita de analista o newsletter del sector con el logo del medio
- **Nota de cumplimiento**: Usa solo logos de medios que realmente te cubrieron; revisa sus términos de uso de logo
- **Extráelo de**: Prensa real, podcasts, newsletters, o menciones de analistas

### 11. Lifestyle Hero

Producto en uso en un ambiente real. Copy mínimo. Aspiracional, no vendedor.

- **Estructura**: Una fotografía hace el trabajo; como máximo una línea corta y logo
- **Slot de copy**: 5-8 palabras, con sabor de identidad ("Las mañanas, resueltas.")
- **Ejemplo DTC**: Producto en un mostrador de cocina en medio de una rutina
- **Ejemplo SaaS**: La herramienta en pantalla en un momento real de trabajo (standup, llamada de cierre, día de lanzamiento)
- **Extráelo de**: Patrones visuales de anuncios ganadores; lenguaje de identidad en reseñas

### 12. Lista Numerada

"5 razones por las que [audiencia] está cambiando a [marca]." Íconos junto a cada punto.

- **Estructura**: Filas numeradas, ícono + línea corta cada una, ancla de producto abajo
- **Slot de copy**: Cada razón un ángulo distinto — dolor, resultado, prueba, diferenciador, precio
- **Ejemplo DTC**: "5 razones por las que los corredores cambiaron a [marca] este año"
- **Ejemplo SaaS**: "4 razones por las que los equipos de finanzas están dejando [herramienta legada]"
- **Extráelo de**: Agrega las razones de cambio más comunes entre reseñas

### 13. FAQ Card

Una objeción común como la pregunta, respondida directamente.

- **Estructura**: Pregunta prominente, respuesta concisa, ancla de producto
- **Slot de copy**: La objeción *tal como la frasean los clientes* — el reconocimiento es el hook
- **Ejemplo DTC**: "¿Pero funciona para piel sensible? Sí — y aquí está el por qué."
- **Ejemplo SaaS**: "¿Esto sobrevivirá a nuestra revisión de seguridad? SOC 2 Type II, SSO, hosting en la UE."
- **Extráelo de**: `inputs/comments/` — las objeciones que la gente publica públicamente bajo tus anuncios

### 14. Competitor Callout

Nombra a un competidor específico (o el default de la categoría) y explica la diferencia. Audaz pero factual.

- **Estructura**: Su nombre vs. el tuyo, un eje claro de diferencia
- **Slot de copy**: Una diferencia que puedas defender con hechos — las afirmaciones comparativas invitan escrutinio
- **Ejemplo DTC**: "Como [competidor], menos los 14g de azúcar."
- **Ejemplo SaaS**: "[Competidor] cobra por asiento. Nosotros no."
- **Nota de cumplimiento**: La publicidad comparativa debe ser veraz y sustentable; algunas plataformas restringen nombrar competidores
- **Extráelo de**: Menciones de competidores en reseñas y comentarios — los clientes nombran la alternativa por ti

### 15. Historia de Origen

Foto del fundador con la narrativa de por-qué-construimos-esto. Copy más largo que otros formatos.

- **Estructura**: Retrato o foto de equipo, 2-3 párrafos cortos, producto secundario
- **Slot de copy**: El momento específico o la frustración que lo inició — la especificidad es la credibilidad
- **Ejemplo DTC**: "Pasamos 2 años y 47 lotes para hacerlo bien. Aquí está el por qué."
- **Ejemplo SaaS**: "Éramos el cliente. La herramienta que necesitábamos no existía, así que la construimos."
- **Extráelo de**: La historia real — combina mejor con audiencias tibias/de retargeting que con frías

---

## Formato de Salida por Concepto

Cada concepto generado sigue esta estructura:

```markdown
## Concepto [N]: [Nombre de Plantilla]

**Titular**: [el copy del titular]
**Cuerpo**: [copy de apoyo, si la plantilla lo usa]
**Visual**: [descripción de layout suficientemente específica para diseñar o generar a partir de ella]
**Prompt de imagen**: [prompt para la herramienta de imagen, si se está generando — ver generative-tools.md]
**Anclado en**: [a qué reseña / anuncio ganador / comentario se traza esto, citado o nombrado]
```

Para un lote, agrega un `INDEX.md` listando cada concepto con su tipo de plantilla y fuente de anclaje, para que quien revise pueda escanear 50 conceptos en dos minutos.

## Distribución del Lote

Para un lote estándar de 50 conceptos: 3-4 variaciones por plantilla entre las 15. Si los datos de rendimiento muestran que ciertas plantillas ganan consistentemente para esta marca, cambia a 60% plantillas comprobadas / 40% cobertura de ciclo completo — pero nunca dejes la cobertura en cero. La fatiga es la razón por la que estás generando a diario; la plantilla que está fatigada el próximo mes es la que estás escalando hoy.
