# Referencia de Prospección SaaS

Para cuando el usuario vende SaaS o servicios digitales a otras empresas SaaS / negocios digitales.

---

## Señales de ICP que Importan (rama SaaS)

Más allá de los firmográficos estándar (industria, tamaño, geografía), los prospectos SaaS se califican por:

### Señales tecnográficas

- **Tech stack** — ¿usan herramientas complementarias (tu target de integración) o herramientas competidoras (una oportunidad de switch)?
- **Cambios recientes de stack** — agregar/quitar herramientas señala evaluación activa de proveedor
- **Construido a medida vs listo para usar** — el tooling DIY a menudo significa un comprador que se beneficiaría de tu producto
- **Señales de plan gratis/freemium** — usar un competidor gratis puede significar que están listos para actualizar

### Señales de crecimiento

- **Ronda de financiamiento** — Serie A / B / C en los últimos 6 meses = presupuesto + nuevas contrataciones + necesidades de herramientas
- **Crecimiento de headcount** — 10%+ de crecimiento en el último trimestre señala presión de escalamiento
- **Señales de contratación** — aperturas de roles específicos (ej. "Head of RevOps" → ICP para tooling de revops)
- **Velocidad de producto** — envíos frecuentes, funciones nuevas, posts de blog = motion de crecimiento saludable
- **Posiciones abiertas para el rol de tu comprador** — si le vendes a Marketing Ops y están contratando uno, esa es una señal

### Señales de decadencia (bajan el puntaje)

- Despidos en el departamento objetivo
- Ronda de financiamiento hace más de 2 años sin seguimiento
- El producto no ha enviado nada en 6+ meses
- La página del equipo muestra solo fundadores (muy temprano — puede no tener presupuesto)

---

## Fuentes de Discovery (rama SaaS)

Combina 2+ fuentes para verificación cruzada.

### Nivel 1 — discovery primario

- **Apollo**: datos firmográficos + tecnográficos + de contacto. Bueno para construir listas iniciales grandes.
- **Clay**: enriquecimiento en cascada (waterfall), puntuación personalizada, fusiones multi-fuente. Lo mejor para listas más pequeñas de alta calidad.
- **ZoomInfo**: firmográficos de nivel empresarial + señales de intención. Costoso; mid-market en adelante.
- **LinkedIn Sales Navigator**: mapeo de tomadores de decisiones. Usar manualmente, nunca scraping masivo.

### Nivel 2 — señales tecnográficas / de crecimiento

- **BuiltWith**: búsquedas de tech stack, encontrar sitios que usan herramientas específicas
- **Wappalyzer**: extensión de navegador gratuita + API; señal de tech stack más liviana
- **Crunchbase**: rondas de financiamiento, headcount, fundadores
- **Pitchbook**: datos de inversionistas más profundos (enterprise/pago)
- **ProductHunt**: lanzamientos recientes, audiencia de builders
- **Hacker News / Show HN**: builders técnicos lanzando productos

### Nivel 3 — señales de compra

- **Bolsas de trabajo** (LinkedIn Jobs, Indeed, AngelList): aperturas de roles como señales
- **RB2B / Clearbit Reveal**: identificación de visitantes (tráfico anónimo cálido)
- **Estrellas/forks de GitHub de repos de competidores o adyacentes**: señal de intención a nivel de desarrollador (ver `tools/integrations/github.md` y el CLI `github-prospects.js`). Especialmente fuerte para SaaS de herramientas para devs — un desarrollador que le dio estrella a `vercel/next.js` la semana pasada está en modo de mercado para infraestructura adyacente a Next.js.
- **Posts recientes de blog / changelog**: señales de dirección de producto
- **Reseñas en G2 que mencionan cambios de competidor**: señal explícita de insatisfacción

#### Patrón de prospección en GitHub (cuando la audiencia son desarrolladores)

Para SaaS de herramientas para devs, GitHub es uno de los canales de discovery de mayor calidad:

1. Identifica 3–5 repos "ancla": tus competidores directos, tu líder de categoría, herramientas complementarias que usa tu comprador
2. Extrae stargazers (o forks para intención más fuerte) vía `node tools/clis/github-prospects.js stargazers <owner/repo> --enrich --with-company --format csv`
3. Filtra a usuarios con el campo `company` establecido — estos son los más fáciles de enriquecer downstream
4. Combina con Apollo/Clay/Hunter para buscar email por nombre + empresa
5. Valida con Truelist antes de agregar a la lista de outreach

Tradeoffs: GitHub produce email para solo ~5–20% de los usuarios directamente. La fortaleza es la calidad de la señal — un stargazer de una herramienta dev de nicho está genuinamente en modo de mercado de una forma que los firmográficos de Apollo solos no te pueden decir.

---

## Checklist de Calificación (rama SaaS)

Para cada candidato, verifica:

- [ ] La vertical de industria coincide con el ICP
- [ ] El tamaño de empresa (headcount) está dentro del rango
- [ ] El tech stack incluye (o notablemente excluye) una tecnología objetivo
- [ ] La etapa de financiamiento coincide con la madurez del comprador
- [ ] Al menos una señal de crecimiento en los últimos 90 días (financiamiento, contratación, velocidad de producto)
- [ ] Existe un rol de tomador de decisiones en la empresa (nombrado o inferible de las ofertas de empleo)
- [ ] Contacto de email verificable
- [ ] Sin descalificadores (cerrado, adquirido-y-pausado, despidos, no encaja el ICP)

---

## Columnas de Salida (rama SaaS)

Columnas de CSV recomendadas:

```csv
score,company,domain,industry,size_band,country,funding_stage,last_round_date,tech_stack_match,signal,signal_date,contact_name,contact_title,contact_email,email_status,linkedin_url,source_urls,why_prospect,confidence,verified_date,notes
```

Para tabla en chat, condensar a: Score | Company | Industry | Size | Signal | Contact | Email status | Confidence.

---

## Selección de Top Outreach Targets (SaaS)

Prioriza para los 3–5 leads Hot principales:

1. **Recencia de señal más fuerte** — financiamiento hace 30 días le gana a financiamiento hace 9 meses
2. **Fuerza del match de tech stack** — un partner de integración conocido le gana a un fit inferido
3. **Tomador de decisiones nombrado con email verificado** — le gana a un email adivinado por patrón de rol
4. **Confianza multi-fuente** — que Apollo + Crunchbase coincidan le gana a una sola fuente

Cada top target recibe un racional de outreach de una oración que nombra la señal específica: "Levantó Serie B hace 30 días; contratando Head of RevOps; email de VP de Operaciones verificado."

---

## Errores Comunes (SaaS)

1. **Comprar listas de Apollo en bloque** sin re-verificar el email y re-chequear los firmográficos. Los datos desactualizados son la norma.
2. **Tratar los datos de tech stack como 100% precisos**. BuiltWith y Wappalyzer se pierden cosas; los waterfalls de Clay se pierden cosas. Verifica cruzadamente.
3. **Apuntar a Serie C+ para vendedores SaaS de etapa temprana**. El perfil de comprador está equivocado — demasiados aros de procurement, demasiada burocracia.
4. **Apuntar a Serie Pre-Seed seed** para productos que requieren presupuesto significativo. No tienen ni presupuesto ni ancho de banda de evaluador.
5. **Ignorar los datos de intención cuando existen** (ZoomInfo Intent, 6sense, etc.) — las señales pre-calentadas le ganan al frío siempre.
