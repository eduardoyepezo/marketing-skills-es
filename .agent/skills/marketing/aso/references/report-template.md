# Plantilla de Reporte de Auditoría ASO

Usa esta estructura para todos los reportes de auditoría ASO.

---

## Encabezado

```
# Auditoría ASO: {Nombre de la App}
**Tienda:** {Apple App Store / Google Play}
**URL:** {URL de la ficha}
**Fecha de auditoría:** {fecha}
**Nivel de marca:** {Dominante / Establecida / Retadora} — {justificación en una línea}
**Puntaje General:** {puntaje}/100 (Grado: {A/B/C/D/F})
```

---

## Tarjeta de Puntaje

```
| Dimensión | Puntaje | Grado | Problema Clave |
|-----------|-------|-------|-----------|
| Título y Subtítulo | X/10 | {grado} | {resumen en una línea} |
| Descripción | X/10 | {grado} | {resumen en una línea} |
| Elementos Visuales | X/10 | {grado} | {resumen en una línea} |
| Ratings y Reviews | X/10 | {grado} | {resumen en una línea} |
| Metadata y Frescura | X/10 | {grado} | {resumen en una línea} |
| Señales de Conversión | X/10 | {grado} | {resumen en una línea} |
| **GENERAL** | **{ponderado}/100** | **{grado}** | |
```

Escala de grado por dimensión: 9-10 = A, 7-8 = B, 5-6 = C, 3-4 = D, 1-2 = F

---

## Top 3 Quick Wins

Cambios de mayor impacto que toman menos de 1 hora:

```
### 1. {Verbo de acción} — {cambio específico}
**Impacto:** {Alto/Medio} | **Esfuerzo:** {<15 min / <30 min / <1 hora}
**Actual:** {cómo está ahora}
**Recomendado:** {reemplazo exacto, con conteo de caracteres}
**Por qué:** {una oración explicando el impacto}

### 2. ...
### 3. ...
```

---

## Hallazgos Detallados

### Análisis de Título y Subtítulo

```
**Título actual:** "{título}" ({X}/30 caracteres usados)
**Subtítulo/desc. corta actual:** "{subtítulo}" ({X}/30 o /80 caracteres usados)

**Problemas encontrados:**
- {problema 1}
- {problema 2}

**Título recomendado:** "{nuevo título}" ({X}/30 caracteres) — {justificación}
**Subtítulo recomendado:** "{nuevo subtítulo}" ({X}/30 o /80 caracteres) — {justificación}
```

### Análisis de Descripción

```
**Primeras 3 líneas (arriba del fold):**
> {texto citado}

**Problemas encontrados:**
- {problema 1}
- {problema 2}

**Densidad de keywords (solo Google Play):** {X}% — objetivo: 2-3%
**Top keywords encontradas:** {keyword1} (Xn), {keyword2} (Xn), ...
**Keywords de alto valor faltantes:** {keyword1}, {keyword2}, ...

**Primeras 3 líneas recomendadas:**
> {texto reescrito}
```

### Análisis de Elementos Visuales

```
**Screenshots:** {cantidad} ({tienda} muestra los primeros {3/todos} en búsqueda)
**Video de vista previa:** {Sí/No}
**Evaluación del ícono:** {descripción}
**Feature graphic (Google Play):** {Sí/No}

**Auditoría de screenshots:**
1. {descripción del screenshot 1} — {aprobado/problema}
2. {descripción del screenshot 2} — {aprobado/problema}
...

**Recomendaciones:**
- {cambio visual específico 1}
- {cambio visual específico 2}
```

### Análisis de Ratings y Reviews

```
**Rating promedio:** {X.X} estrellas ({cantidad} ratings)
**Sentimiento de reviews recientes:** {Positivo/Mixto/Negativo}
**Quejas comunes:** {tema1}, {tema2}
**Respuestas del desarrollador:** {Sí, activo / Esporádico / Ninguno}

**Recomendaciones:**
- {acción específica 1}
- {acción específica 2}
```

### Metadata y Frescura

```
**Última actualización:** {fecha} ({X días/meses atrás})
**Localizaciones:** {cantidad} idiomas
**Categoría:** {categoría actual}
**Eventos dentro de la app/LiveOps:** {Sí/No}

**Recomendaciones:**
- {acción específica 1}
- {acción específica 2}
```

### Señales de Conversión

```
**Modelo de precio:** {Gratis / Freemium / Pago}
**Cantidad de IAP:** {cantidad}
**Descargas (Google Play):** {rango}
**Prueba social visible:** {premios, prensa, insignias — o "ninguna"}

**Recomendaciones:**
- {acción específica 1}
- {acción específica 2}
```

---

## Sugerencias de Keywords

```
| Keyword | Justificación | Dónde Colocarla | Prioridad |
|---------|-----------|----------------|----------|
| {keyword} | {por qué esta keyword} | {título/subtítulo/descripción/campo de keywords} | {Alta/Media/Baja} |
| ... | ... | ... | ... |
```

Nota: Sin herramientas pagas de ASO, el volumen de búsqueda exacto no está disponible.
Estas sugerencias se basan en análisis de categoría, metadata de competidores y
relevancia semántica. Valida con AppTweak, Sensor Tower, o MobileAction para datos de volumen.

---

## Comparación con Competidores (si aplica)

```
| Métrica | {Tu App} | {Competidor 1} | {Competidor 2} |
|--------|-----------|----------------|----------------|
| Keywords del título | ... | ... | ... |
| Rating | ... | ... | ... |
| Screenshots | ... | ... | ... |
| Video | ... | ... | ... |
| Keywords de la descripción | ... | ... | ... |
| Última actualización | ... | ... | ... |
| Puntaje ASO general | ... | ... | ... |
```

---

## Plan de Acción Priorizado

Ordenado por impacto (de alto a bajo), agrupado por esfuerzo:

```
### Hacer Esta Semana (Quick Wins)
1. {acción} — {impacto esperado}
2. {acción} — {impacto esperado}

### Hacer Este Mes (Esfuerzo Medio)
3. {acción} — {impacto esperado}
4. {acción} — {impacto esperado}

### Planear para el Próximo Trimestre (Alto Esfuerzo)
5. {acción} — {impacto esperado}
6. {acción} — {impacto esperado}
```

---

## Limitaciones

Incluye siempre esta sección:

> **Lo que esta auditoría no puede medir sin herramientas pagas de ASO:**
>
> - Volumen de búsqueda exacto de keywords y puntajes de dificultad
> - Posiciones históricas de ranking de keywords
> - Estimaciones de descargas e ingresos
> - Contenido del campo de keywords de Apple (oculto de la vista pública)
> - Datos de tasa de conversión de instalación (solo disponibles para el dueño de la app en la consola)
> - Resultados de pruebas A/B previas
>
> Para estos datos, considera usar AppTweak ($69/mes), Sensor Tower, o
> MobileAction ($69/mes).
