# Guardrails y Cumplimiento de Loops

Los loops actúan según un horario, a menudo sobre datos de clientes, a veces con dinero o una voz pública. Esta referencia consolida las reglas de seguridad que evitan que los loops autónomos hagan daño. Aplícala a todo loop que envíe, gaste, publique, o toque datos personales.

## El modelo de acción de dos niveles

Clasifica cada acción que un loop puede realizar:

**Nivel 1 — Autónomo-seguro** (un loop puede hacer esto sin supervisión):
leer datos, analizar, comparar, puntuar, **redactar**, y **preparar** trabajo para revisión.

**Nivel 2 — Controlado** (requiere un checkpoint humano por defecto):
**gastar** dinero, **mover presupuesto**, **enviar** mensajes, **publicar** cualquier cosa pública, **eliminar/suprimir** registros, **cambiar** configuraciones de cuenta en vivo.

Una acción de Nivel 2 solo puede correr sin una revisión humana por acción si el usuario la ha **autorizado explícitamente** *y* está acotada por topes + una lista permitida (abajo). Sin eso, el loop prepara un borrador y un humano lo aprueba.

## Guardrails de gasto (ad-fatigue, paid-search, retargeting, expansion)

- **Topes duros**: un techo de gasto diario/semanal que el loop nunca puede exceder; detenerse y alertar si se acerca.
- **Límite de cambio por corrida**: acotar cuánto presupuesto puede moverse en una corrida (p. ej., ≤20%), para que una mala lectura no reasigne todo.
- **Lista permitida**: solo las cuentas/campañas especificadas son elegibles para cambios autónomos; todo lo demás se prepara para revisión.
- **Guardrails direccionales**: juzgar los cambios pagados por ingresos/ROAS, no solo CTR/CPA — nunca optimizar una métrica proxy hasta el punto de perder ingresos.

## Guardrails de publicación y envío (email, social, PR, comunidad, reseñas)

- **Por defecto, una cola de preparación** + aprobación humana para todo lo público o saliente. Auto-*redactar* está bien; auto-*publicar* no, a menos que esté explícitamente autorizado.
- **Topes de volumen**: límites por corrida y por destinatario para que un loop no pueda bombardear una lista o sobre-publicar en un canal.
- **Supresión primero**: siempre revisar las listas de supresión/baja/no-contactar antes de enviar.
- **Sin auto-publicación donde la detección/ToS afecta**: el social propio, los pitches de prensa, y las respuestas en comunidades se preparan para un humano (detección de bots + riesgo de marca).

## Cumplimiento

Haz coincidir cada regla con los loops que gobierna:

- **CAN-SPAM / CASL (loops de email/SMS — lifecycle, re-engagement, churn, trial, dunning, referral)**: honrar las bajas de inmediato y de forma permanente; incluir un enlace de baja funcional + dirección física; identificar al remitente; no enviar correo/SMS sin una base legal o consentimiento; verificar contra la supresión en cada envío.
- **GDPR / CCPA (cualquier loop que toque datos personales)**: procesar sobre una base legal; obtener consentimiento para marketing en la UE; honrar las solicitudes de eliminación y exclusión; minimizar los datos extraídos y retenidos; no reutilizar datos más allá de su propósito de recolección.
- **FTC (review-and-UGC-harvest, referral, social)**: divulgar conexiones materiales e incentivos (#ad, "recibí una compensación"); usar testimonios solo con permiso; sin afirmaciones fabricadas o seleccionadas engañosamente.
- **ToS de la plataforma (social-listening, community-engagement, review-site-management, loops basados en scraping)**: respetar los límites de tasa y las reglas de automatización; seguir las políticas de respuesta de las plataformas de reseñas; no hacer scraping ni actuar automáticamente donde esté prohibido.

Cuando un loop no puede confirmar el consentimiento, el permiso, o la compatibilidad con el ToS, su condición de parada es **no actuar** — preparar para un humano en su lugar.

## Manejo de PII

- No registrar PII en bruto en el **estado** del loop ni en los **logs de corridas** — usar IDs internos o hashes.
- Extraer el mínimo de datos personales necesarios para tomar la decisión; no acumularlos en el estado.
- Mantener las exportaciones y borradores fuera de ubicaciones compartidas/sincronizadas a menos que sea intencional.

## Lista de escalamiento obligatorio

Estos nunca corren de forma totalmente autónoma — enrutar a un humano sin importar la autorización:

- Menciones de marca negativas o de crisis; respuestas a quejas o temas sensibles legal/médico/financieramente.
- Ángulos de newsjacking (ver la lista de veto en el catálogo) — aprobación humana antes de cualquier pitch/publicación.
- Cuentas de alto valor o estratégicas (empresas grandes, logos en riesgo).
- Anomalías en **ingresos** o **gasto publicitario** — señalar de inmediato, no autocorregir.
- Cualquier cosa que elimine datos o contacte a una audiencia grande de una sola vez.

## Interruptor de emergencia

Todo loop programado necesita un interruptor manual de apagado, y debes saber cómo detener **todos** los loops rápidamente (desactivar el horario / cron, o una bandera global que los cuerpos de los loops revisen). Documéntalo donde los loops están programados. Un loop que no puedes detener rápidamente es un pasivo.

## Checklist de guardrails previo al lanzamiento

Antes de programar cualquier loop que envíe, gaste, publique, o toque datos personales:

- [ ] Cada acción está clasificada como Nivel 1 (auto) o Nivel 2 (controlado).
- [ ] Las acciones de Nivel 2 están preparadas para aprobación — o acotadas por autorización explícita + topes + lista permitida.
- [ ] Los loops de gasto tienen un tope duro y un límite de cambio por corrida.
- [ ] Los loops de envío revisan la supresión/baja y tienen topes de volumen.
- [ ] Las reglas de cumplimiento aplicables (CAN-SPAM/GDPR/FTC/ToS) están satisfechas, con "no actuar" como respaldo.
- [ ] No hay PII en bruto en el estado ni en los logs.
- [ ] Los casos de escalamiento obligatorio se enrutan a un humano.
- [ ] Hay un interruptor de emergencia documentado.
