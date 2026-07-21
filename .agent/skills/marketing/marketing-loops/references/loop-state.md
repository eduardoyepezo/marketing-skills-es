# Estado de Loops y Registro de Corridas

La idempotencia solo es real si el loop puede recordar lo que ya hizo entre corridas. Esta referencia define dónde vive ese estado y cómo registrar las corridas — para que los loops no actúen dos veces, no vuelvan a molestar a las mismas personas, ni vuelvan a alertar sobre el mismo problema.

## Dónde vive el estado

Persiste el estado de cada loop en un archivo bajo `.agents/loops/` — la misma convención `.agents/` que este repositorio usa para `product-marketing.md` y `listening-sources.md`. Un archivo de estado por loop:

```
.agents/loops/<nombre-del-loop>.json     # la memoria del loop
.agents/loops/<nombre-del-loop>.log      # log de corridas de solo agregar
```

Si tu programador o plataforma provee su propio almacenamiento de deduplicación/cursor, úsalo en su lugar — el punto es el estado durable, no el archivo específico. Nunca mantengas el estado solo en memoria; un loop que olvida al reiniciar se repetirá a sí mismo.

## Qué almacenar

Un archivo de estado contiene lo que sea que el loop necesite para no repetirse:

```json
{
  "loop": "churn-signal",
  "last_run": "2026-07-01T09:00:00Z",
  "cursor": "2026-06-30T23:59:59Z",        // marca de agua — solo procesar elementos más nuevos que esto
  "handled": ["acct_1042", "acct_1077"],    // claves de deduplicación ya procesadas
  "cooldowns": {                             // entidad -> próxima marca de tiempo elegible
    "acct_1042": "2026-07-15T00:00:00Z"
  },
  "in_flight": ["exp_pricing_v3"],           // acciones/pruebas actualmente abiertas
  "counters": { "acct_1042_attempts": 2 }    // p. ej., conteos de intentos de dunning/win-back
}
```

- **cursor / marca de agua** — la marca más alta de lo que ya se procesó (una marca de tiempo o el último ID). El loop solo mira elementos posteriores a ella.
- **handled** — claves de deduplicación de elementos ya procesados, para que las re-corridas los salten.
- **cooldowns** — ventanas de supresión por entidad para que nunca vuelvas a contactar a alguien dentro de la ventana.
- **in_flight** — elementos abiertos (pruebas en curso, intervenciones activas) para que el loop no inicie uno en conflicto.
- **counters** — conteos de intentos que impulsan las condiciones de parada (p. ej., "tras 2 correos de win-back, detenerse").

Mantén el estado pequeño y pódalo: expira las entradas antiguas de `handled`/`cooldown` una vez que pasen su ventana.

## Patrones de idempotencia

- **Marca de agua**: procesar solo elementos más nuevos que `cursor`; avanzar `cursor` al final de una corrida exitosa. Seguro de re-correr — no reprocesará.
- **Conjunto de deduplicación**: antes de actuar sobre un elemento, revisar su clave contra `handled`; agregarla después de actuar.
- **Mapa de enfriamiento**: antes de contactar a una entidad, revisar `cooldowns[entidad]`; establecerlo después del contacto.
- **Guardia de in-flight**: antes de iniciar una acción que no debería solaparse (una prueba, una intervención), revisar `in_flight`.

## Registro de corridas

Agrega una línea por corrida, haya actuado o no. Este es el rastro de auditoría y el detector de loops de vanidad.

```
2026-07-01T09:00Z  checked=312  acted=2   note="2 cuentas nuevas en riesgo, intervenciones preparadas"
2026-07-02T09:00Z  checked=298  acted=0   note="sin acción"
2026-07-03T09:00Z  checked=305  acted=0   note="sin acción"
```

Registra como mínimo: marca de tiempo, cuántos elementos se revisaron, sobre cuántos se actuó, y una nota breve. Úsalo para responder dos preguntas:
- **¿Es un loop de vanidad?** Si cada corrida es `acted=0` durante semanas y a nadie le hace falta — o actúa en cada corrida (una señal de que está persiguiendo ruido) — reconsidéralo.
- **¿Actuó dos veces?** Dos corridas actuando sobre la misma entidad significa que el estado de deduplicación/enfriamiento no está funcionando.

## Reiniciar y rellenar de forma segura

- Para **reiniciar** un loop, limpia su `cursor`/`handled` — pero conserva `cooldowns` para que un reinicio no bombardee a personas contactadas recientemente.
- En la **primera corrida** (sin estado aún), establece la marca de agua en "ahora" en lugar de procesar todo el historial, o bombardearás cada elemento histórico. Si genuinamente quieres un relleno retroactivo, haz primero una corrida de prueba (registra lo que *haría*, sin actuar sobre nada) y respeta los enfriamientos.
- Nunca registres PII en bruto en el estado o los logs de corridas — usa IDs o hashes (ver `loop-guardrails.md`).
