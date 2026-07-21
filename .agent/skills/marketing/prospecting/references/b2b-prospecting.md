# Referencia de Prospección B2B

Para cuando el usuario le vende a B2B no-SaaS — servicios, agencias, manufactureras, empresas mid-market y enterprise, firmas de servicios profesionales.

---

## Señales de ICP que Importan (rama B2B)

### Señales firmográficas

- **Industria / vertical** — códigos NAICS o SIC si la precisión importa
- **Tamaño de empresa** — banda de headcount, banda de ingresos, cantidad de ubicaciones
- **Geografía** — relevante para zonas horarias, regulaciones, requisitos presenciales
- **Modelo de negocio** — servicio vs producto vs distribución; B2B vs B2B2C
- **Propiedad** — independiente, respaldada por PE, pública, familiar — afecta el motion de compra

### Señales de compra

- **Eventos disparadores**: nueva contratación de nivel C, adquisición o desinversión reciente, IPO/financiamiento, apertura de nueva ubicación, rebranding reciente, anuncio de expansión
- **Señales de proveedor**: publicación pública de RFPs, costos de cambio en el último reporte trimestral, ventanas de renovación de contrato
- **Señales operacionales**: despidos recientes (presión de costos) o contratación rápida (presión de capacidad)
- **Menciones en noticias**: lanzamiento de nueva iniciativa, entrada a nuevo mercado, cambio regulatorio que fuerza acción
- **PR / prensa**: cualquier cosa que señale "esta empresa está cambiando ahora mismo"

### Señales de decadencia

- Múltiples bancarrotas u operaciones despojadas por PE
- Crecimiento negativo + titulares de recorte de costos
- Estancamiento de propiedad (pequeña, familiar, sin incentivo de crecimiento)
- Rotación de comprador (3+ Directores de Marketing en 2 años)

---

## Fuentes de Discovery (rama B2B)

### Nivel 1 — discovery primario

- **Apollo**: el mejor descubrimiento firmográfico + de contactos B2B en general
- **ZoomInfo**: B2B empresarial + señales de intención (mid-market en adelante)
- **LinkedIn Sales Navigator**: búsqueda por industria + rol + señal; el estándar de oro para mapeo de tomadores de decisiones (manual)
- **Clay**: cuando necesitas búsquedas en cascada (waterfall) personalizadas (ej. enriquecer registros de Apollo con Hunter + Clearbit)

### Nivel 2 — directorios específicos de industria

- **Crunchbase / Pitchbook**: negocios financiados
- **D&B Hoovers**: datos firmográficos B2B tradicionales de gran escala
- **Registros de negocios estatales / nacionales**: para datos de incorporación verificados
- **Listados de miembros de asociaciones de industria**: los grupos comerciales a menudo publican listas de miembros
- **Listas de expositores de ferias comerciales**: señala participación activa en una vertical
- **Bases de datos de adquisiciones** (Procore para construcción, por ejemplo): señales específicas de vertical

### Nivel 3 — monitoreo de eventos disparadores

- **Google Alerts / Feedly**: palabras clave disparadoras ("adquirida," "contrata," "expansión," "levanta," "anuncia")
- **PR Newswire / Business Wire**: anuncios controlados por la empresa
- **Reportes de la SEC** (empresas públicas): divulgaciones de cambio material
- **Registros estatales**: formación de nueva entidad, disolución

---

## Checklist de Calificación (rama B2B)

- [ ] La industria / vertical coincide con el ICP (usa una clasificación reconocida si es posible)
- [ ] El tamaño de la empresa está dentro del rango (empleados o ingresos)
- [ ] La geografía encaja
- [ ] Al menos un evento disparador en los últimos 90–180 días
- [ ] Existe un rol de tomador de decisiones (CEO, COO, VP de Operaciones, Director de X — que coincida con el perfil de comprador)
- [ ] Contacto de email verificable (rol nombrado > catchall info@)
- [ ] URLs fuente capturadas para las afirmaciones firmográficas
- [ ] Sin descalificadores (cerrado, adquirido-pausado, múltiples bancarrotas, fuera de ICP)

---

## Columnas de Salida (rama B2B)

Columnas de CSV recomendadas:

```csv
score,company,domain,industry,naics_code,size_band,revenue_band,country,city,trigger_event,trigger_date,contact_name,contact_title,contact_email,email_status,linkedin_url,source_urls,why_prospect,confidence,verified_date,notes
```

Para tabla en chat, condensar a: Score | Company | Industry | Size | Trigger | Contact | Email status | Confidence.

---

## Selección de Top Outreach Targets (B2B)

Prioriza para los 3–5 leads Hot principales:

1. **Recencia del evento disparador** — 30 días le gana a 6 meses
2. **Especificidad del evento disparador** — nueva contratación de CMO en el rol de tu comprador le gana a "empresa en las noticias"
3. **Acceso al tomador de decisiones** — contacto nombrado con email verificado + LinkedIn le gana a solo-rol
4. **Precisión del fit vertical** — match exacto de NAICS le gana a "industria adyacente"

Cada racional de top target nombra el disparador y el tomador de decisiones: "Contrató nuevo VP de Marketing hace 14 días; email verificado; manufacturera mid-market que coincide con el ICP."

---

## Errores Comunes (B2B)

1. **Tratar B2B como SaaS** — las rondas de financiamiento importan menos; la propiedad PE y la actividad de adquisiciones importan más.
2. **Intentar verificar con precisión los ingresos de empresas privadas** — la mayoría de las bases de datos públicas aproximan. Usa bandas de tamaño, no estimados puntuales.
3. **Ignorar la complejidad de adquisiciones** a escala enterprise — tu lista de contactos de prospectos puede no incluir al aprobador real.
4. **Enviar cold email a asistentes ejecutivos** — no son el comprador y van a marcar tu outreach como spam.
5. **Higiene de URL fuente** — sin linaje de fuente, no puedes defender un contacto bajo un DSAR de GDPR o un desafío de CAN-SPAM.
6. **Detenerse en una sola fuente** — Apollo puede tener 60% de precisión en negocios pequeños. Verifica cruzadamente con LinkedIn o el sitio web de la empresa.
