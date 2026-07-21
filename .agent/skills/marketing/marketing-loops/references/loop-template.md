# Plantilla de Loop

Una plantilla de copiar y pegar para crear tu propio loop de marketing. Completa cada una de las nueve partes — un loop sin **estado/idempotencia**, **autoverificación**, o **parada/salida** no es un sistema, es una forma de hacer lo incorrecto según un horario.

Antes de empezar, verifica que esto *en verdad* deba ser un loop (ver "Cuándo NO usar un loop" en `SKILL.md`): es recurrente, está impulsado por señales, y no requiere juicio humano para definir estrategia o dirección creativa en cada corrida.

---

## Plantilla en blanco (copia esto)

```markdown
### El loop de <nombre>
- **Cadencia de revisión**: <con qué frecuencia revisa — ajústalo a la velocidad con la que cambia la señal, no a la frecuencia con la que te gustaría una actualización>
- **Actúa cuando**: <la condición de acción — qué debe ser cierto para que realmente HAGA algo vs. solo revisar y pasar de largo. La mayoría de las corridas deberían pasar de largo.>
- **Propósito**: <el ÚNICO resultado que este loop existe para mover>
- **Habilidades usadas**: <qué habilidades de marketing orquesta el loop en cada corrida>
- **Cuerpo del loop**:
  1. <paso — usualmente: extraer datos / comparar contra la última corrida>
  2. <paso — identificar qué, si acaso, cruzó la condición de acción>
  3. <paso — redactar o preparar la respuesta>
- **Autoverificación**: <la verificación que se hace ANTES de actuar — ¿la señal es real o es ruido/estacionalidad/bug de tracking? ¿La muestra es lo bastante grande para ser significativa?>
- **Estado / idempotencia**: <qué recuerda entre corridas — marcador de última ejecución, clave de deduplicación, ventana de enfriamiento, conjunto de "ya manejado" — para que no actúe dos veces ni vuelva a molestar a las mismas personas>
- **Parada / salida**: <cuándo se salta, se detiene, escala a un humano, o se desactiva a sí mismo — más qué hace ante un error. Incluye un checkpoint humano antes de cualquier cosa que gaste dinero o publique.>
- **Salida**: <a dónde van los resultados — un archivo, un PR, un borrador preparado, una notificación, un reporte>
```

---

## Prompts para completar (respóndelos, en orden)

1. **¿Qué resultado protege o hace crecer esto?** (rankings, eficiencia publicitaria, activación, retención, ingresos, referidos) → *Propósito*
2. **¿Qué tan rápido cambia realmente esa señal?** (horas / días / semanas / meses) → *Cadencia de revisión*
3. **¿Qué debe ser cierto antes de que valga la pena actuar?** (un umbral cruzado, apareció un nuevo elemento, una regresión vs. la base) → *Actúa cuando*
4. **¿Qué datos lee y qué produce en cada corrida?** → *Cuerpo del loop* + *Salida*
5. **¿Qué haría que actúe sobre una señal falsa?** (ruido, estacionalidad, una falla de tracking, una muestra demasiado pequeña) → *Autoverificación*
6. **¿Qué debe recordar para no repetirse?** (clave de deduplicación, enfriamiento, marcador de última ejecución) → *Estado / idempotencia*
7. **¿Cuándo debe detenerse, pasar de largo, o traspasar a un humano?** (no se necesita acción, error, decisión de gasto/publicación, N intentos fallidos) → *Parada / salida*

Si no puedes responder 5, 6 y 7 de forma concreta, el loop no está listo para correr.

---

## Ejemplo resuelto (en blanco → completo)

Supón que vendes una herramienta de API freemium y quieres dejar de perder registros que nunca hacen su primera llamada a la API.

```markdown
### El loop de activación de primera llamada
- **Cadencia de revisión**: Diaria
- **Actúa cuando**: Un usuario que se registró hace 48h todavía no ha hecho una llamada exitosa a la API y no está ya en esta secuencia de recordatorio.
- **Propósito**: Aumentar la proporción de nuevos registros que alcanzan el primer valor (primera llamada exitosa a la API).
- **Habilidades usadas**: `onboarding-cro`, `email-sequence`, `analytics-tracking`
- **Cuerpo del loop**:
  1. Extraer los registros de hace ~48h y su estado de primera llamada.
  2. Filtrar a los que tienen cero llamadas exitosas y ningún recordatorio activo.
  3. Redactar un correo dirigido de "haz que tu primera llamada funcione" (enlace a la documentación, bloqueo común, ofrecer ayuda).
- **Autoverificación**: ¿"Sin llamada" es una brecha de activación real, o una brecha de tracking (las llamadas se disparan pero no se registran)? Confirmar contra los logs del servidor antes de enviar el correo.
- **Estado / idempotencia**: Rastrear qué usuarios han entrado en esta secuencia; suprimir a cualquiera que haya hecho una llamada desde entonces; un recordatorio por usuario por etapa.
- **Parada / salida**: Tras 2 recordatorios sin llamada, detenerse y enrutar hacia el loop más amplio de re-engagement — no seguir enviando correos. Saltar la corrida por completo si el pipeline de eventos se ve obsoleto.
- **Salida**: Un correo de activación preparado por cada usuario calificado + un conteo diario de nuevas activaciones.
```

Nota qué lo hace seguro: la **autoverificación** protege contra un bug de tracking que envíe correos a usuarios activos, el **estado** evita que vuelva a molestar, y la **parada** limita los intentos y traspasa en lugar de correr para siempre.

---

## Checklist de lanzamiento

Antes de programar un loop nuevo, confirma:

- [ ] Las nueve partes están completas — especialmente autoverificación, estado, y parada.
- [ ] La cadencia coincide con la velocidad de la señal (no estás revisando a diario una señal que se mueve semanalmente).
- [ ] Está diseñado para que **la mayoría de las corridas no hagan nada** — actúa solo ante una condición real.
- [ ] Todo lo que **gaste dinero o publique** tiene un checkpoint humano (a menos que los topes + una lista permitida estén explícitamente autorizados).
- [ ] El estado evita actuar dos veces y volver a molestar a las mismas personas.
- [ ] Hay una ruta de error (datos obsoletos → reportar "obsoleto," no inventar movimiento) y un interruptor manual de apagado.
- [ ] Para la mecánica de programación, ver la sección "Programar un loop" en `SKILL.md`.

Una vez que corra, dale unos cuantos ciclos y hazte la pregunta "¿es esto un loop de vanidad?": si nadie actúa sobre la salida, elimínalo.
