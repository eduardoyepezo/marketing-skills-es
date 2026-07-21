# El Loop de Estrategia de Creatividades

La generación (Modos 1–3) responde a "hazme anuncios." Esta referencia responde la pregunta que viene primero: **qué anuncios vale la pena hacer, en qué orden, a qué costo de producción** — y la retro que convierte los resultados de cada mes en el plan del próximo. Es el loop operativo estándar de un estratega de creatividades, ejecutado por un agente con un humano decidiendo.

```
Señales → Conceptos (rankeados por evidencia) → Roadmap (por niveles, con capacidad verificada) → Briefs → [Los Modos 1–3 producen] → Retro mensual → de vuelta al icebox
```

---

## Paso 1: Leer las Tres Señales

La dirección creativa viene de la síntesis entre tres fuentes de señales independientes. Una sola fuente engaña: la cuenta te dice qué funcionó *entre las cosas que has probado*, los clientes te dicen por qué compran *en sus propias palabras*, y el contenido orgánico te dice qué *elige ver* la audiencia cuando nadie está pagando.

| Señal | Qué extraer | Cómo |
|---|---|---|
| **Rendimiento de cuenta** | Ganadores/perdedores por ángulo, hook, formato; métricas de embudo por concepto (ver el embudo de diagnóstico en [hook-system.md](hook-system.md)); estado de fatiga | CLIs `google-ads` / `meta-ads` / `linkedin-ads` / `tiktok-ads` (ver Integraciones de Herramientas en SKILL.md) |
| **Cliente/marca** | Lenguaje textual de dolor/deseo/objeción; casos de uso inesperados; quién *realmente* está comprando vs. a quién se apunta | El corpus de Insumos con Base en la Realidad (`inputs/reviews/`, `inputs/comments/`), notas de llamadas de ventas, temas de soporte — según **customer-research** |
| **Orgánico externo** | Qué ve el nicho sin pagar: contenido orgánico top, sus hooks, formatos, vocabulario; anuncios de la competencia que llevan corriendo lo suficiente como para presumir que funcionan | **scraping**, las herramientas de social listening en **social**, bibliotecas de anuncios, **competitor-profiling** |

**Cadencia:** una inmersión profunda mensual (60–90 min, las tres fuentes, alimenta el roadmap mensual) más un refresh semanal de ~20 minutos (qué cambió: nuevos ganadores/perdedores, nuevos temas de reseñas, cualquier cosa que esté teniendo un pico orgánico). Investigar más allá de lo que necesita la próxima decisión es trabajo ocioso — cada sesión de síntesis debe terminar en conceptos, no en notas.

**Regla de confianza:** cada insight que el agente presenta debe llevar su recibo — qué reseña, las métricas de qué anuncio, qué post orgánico. Un insight sin fuente no entra al icebox. (Las mismas reglas de anclaje que todo lo demás en esta habilidad.)

---

## Paso 2: Convertir Señales en Conceptos Rankeados por Evidencia

Un **concepto** es una hipótesis creativa testeable: *segmento × motivación × ángulo × formato*, con su evidencia adjunta. "UGC para mamás" no es un concepto; "madres primerizas con insomnio (según 40+ reseñas que mencionan tomas a las 3am) × 'suficientemente silencioso para no despertar al bebé' × demo antes/después × video POV nocturno" sí lo es.

Rankea cada concepto según la evidencia más fuerte que lo respalda:

| Nivel | Evidencia | Peso |
|---|---|---|
| 1 | Tu propia cuenta: un anuncio que convierte con el mismo ángulo/segmento | Más fuerte — iterar y extender |
| 2 | Tus clientes textualmente: lenguaje recurrente de reseñas/llamadas | Fuerte — construir nueva creatividad sobre él |
| 3 | Creatividad de la competencia corriendo 60+ días (se presume que funciona) | Bueno — adaptar el ángulo, nunca el anuncio |
| 4 | Engagement orgánico en el nicho (vistas/guardados sin pagar sobre el tema) | Moderado — validar barato primero |
| 5 | Patrón cruzado de nicho (funcionó en una categoría adyacente) | Débil — icebox hasta corroborar |
| 6 | Corazonada del equipo, sin señal externa | Más débil — prueba de baja fidelidad o descartar |

Mayor evidencia gana *prioridad* en el roadmap — un espacio más temprano en el slate. El nivel de producción es una decisión separada, definida por la fuerza de validación, los assets existentes, la capacidad y el riesgo: incluso un concepto de nivel 2 con lenguaje de cliente empieza en baja fidelidad hasta que muestre una señal en el embudo. Las corazonadas no están prohibidas — solo son baratas y van al final.

---

## Paso 3: Ramificar según el Estado de la Cuenta

El mix creativo correcto depende de en cuál de dos estados está la cuenta. Diagnostica antes de hacer el roadmap — un plan construido para el estado equivocado desperdicia el mes.

**Estado de exploración** — nada (o nada nuevo) está funcionando:
- Ve **amplio, no profundo**: mayormente conceptos nuevos en diferentes segmentos y ángulos; mantén las iteraciones como una minoría pequeña — iterar sobre perdedores multiplica perdedores
- **Redefine "victoria" por métrica**: sin ganadores de embudo completo, una mejora de una sola métrica (un aumento de hold-rate, una caída de CPC, un salto de CVR) en cualquier prueba es un hit que vale la pena seguir — ver el embudo de diagnóstico
- Itera **solo sobre los hits**; todo lo demás se mantiene exploratorio
- Causas raíz comunes a revisar mientras se prueba: la creatividad es aburrida (segura, ya vista), el mensaje está sobrecomplicado, la oferta/UVP no es clara, o los CPMs están castigando a una audiencia demasiado angosta

**Estado de escalamiento** — uno o más conceptos están convirtiendo de forma rentable:
- Ve **profundo en el ganador** mientras esté abierto: un slate liderado por el ganador con variaciones visualmente distintas del concepto ganador (mismo mensaje, nueva ejecución — los casi-duplicados mayormente canibalizan el alcance del original y no enseñan nada nuevo, así que las variaciones deben verse significativamente diferentes), más un carril de remix (re-ejecuciones tonales/emocionales del mismo) y sondeos de sub-ángulo que perforan *dentro* del segmento ganador; ajusta el split según el presupuesto, la velocidad de fatiga y la velocidad de producción
- Mantén una pequeña asignación de exploración viva incluso a mitad de escala — los ganadores se fatigan, y el próximo ganador rara vez es una iteración del actual
- La velocidad importa más en este estado: una ventana de escalamiento es finita

---

## Paso 4: El Artefacto del Roadmap

Mantén un documento vivo (sugerido: `roadmap.md` junto al corpus de Insumos con Base en la Realidad) con tres horizontes:

```
## Icebox        — cada concepto, con nivel de evidencia + fuente adjunta, nada agendado
## Este trimestre  — 2-4 temas elegidos del icebox (las apuestas), con el por-qué-ahora
## Este mes    — el slate: concepto | nivel de evidencia | nivel de producción | responsable | estado
```

Cada concepto del slate mensual recibe un **nivel de producción**:

| Nivel | Costo | Qué es | Usar para |
|---|---|---|---|
| **T1 — Iteración** | Horas | Nuevo hook/caption/recorte sobre un asset existente | Extender ganadores comprobados |
| **T2 — Remix** | Días | Creatividad nueva a partir de metraje/assets existentes/generación con IA | Conceptos con evidencia decente o una primera señal de baja fidelidad |
| **T3 — Producción** | Semanas | Rodaje nuevo, creadores, construcción completa | Solo ángulos con prueba en la propia cuenta o una señal de embudo previa en baja fidelidad (escalera de fidelidad en [hook-system.md](hook-system.md)) |

**Chequeo de capacidad — la regla que mantiene honestos los roadmaps:** cuenta lo que el equipo (o el pipeline de IA) puede producir *con calidad* este mes, y haz el roadmap para ese número. Un slate de 20 conceptos contra una capacidad real de 8 conceptos no produce 20 anuncios; produce 20 anuncios comprometidos y un equipo agotado. Recorta por ranking de evidencia hasta que el slate quepa.

A partir del slate, genera **un brief por concepto** (segmento, motivación + fuente textual, ángulo, formato, filas de matriz de hooks, nivel de producción, métrica de éxito) y entrega cada uno a los Modos 1–3 para producción.

---

## Paso 5: La Retro Mensual de Creatividades

Último paso del loop, primer insumo del siguiente. Un artefacto por mes (sugerido: `retros/YYYY-MM.md`):

```
## Ganadores     — concepto, los números del embudo, y el POR QUÉ (qué elemento se lo ganó)
## Perdedores    — concepto, dónde murió en el embudo, hipótesis de por qué
## Victorias de métrica — perdedores de embudo completo con una métrica fuerte (son pistas, no pérdidas)
## Aprendizajes  — notas a nivel de patrón → escritas de vuelta al icebox como conceptos nuevos/revisados
## Bajas         — conceptos retirados del icebox, con razón
## Próximo slate — primer borrador del próximo mes, niveles de evidencia actualizados
```

Reglas de la retro:

- **Juzga conceptos, no anuncios.** Tres ejecuciones de un concepto fallando dice que el concepto está mal; una fallando dice que la ejecución estuvo mal.
- **Lee el embudo, no la columna de ROAS.** El embudo de diagnóstico dice *qué* arreglar; el ROAS solo dice *que* algo está roto.
- **Suficientes datos antes de veredictos** — respeta los umbrales de impresiones/gasto en Errores Comunes y los sistemas de decisión de la habilidad **paid-ads**; una lectura de dos días es una moneda al aire.
- **Cada aprendizaje aterriza en algún lado**: actualización del icebox, re-ranking de evidencia, o baja. Una retro que no cambia nada en el roadmap fue una reunión, no una retro.

Para correr este loop en un cronograma (retro el día 1, refresh semanal los lunes, lotes diarios vía el Modo 3), ver los loops de creatividad en **marketing-loops**.

---

## Modos de Falla

- **Hacer roadmap sin diagnóstico** — un slate construido antes de leer las tres señales es una lista de deseos; probar sin un diagnóstico no es estrategia
- **Slates cargados de iteración en estado de exploración** — pulir perdedores mientras el problema real (ángulo, oferta, audiencia) queda sin probar
- **Ignorar la capacidad** — el plan que el equipo no puede producir con calidad es un plan para producir mediocridad
- **Conceptos sin evidencia saltándose la cola** — la corazonada del stakeholder más ruidoso se lanza como un rodaje T3 mientras el lenguaje de cliente de nivel 2 se queda en el icebox
- **Retro como teatro** — se celebran ganadores, nada se re-rankea, el icebox queda intacto
- **Complacencia en estado de escalamiento** — 100% del slate en variaciones del ganador; cuando el ganador se fatiga, el pipeline queda vacío
