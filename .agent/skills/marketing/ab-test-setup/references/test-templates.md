# Plantillas de Referencia para Pruebas A/B

Plantillas para planificar, documentar y analizar experimentos.

## Contenidos
- Plantilla de Plan de Prueba
- Plantilla de Documentación de Resultados
- Plantilla de Entrada al Repositorio de Pruebas
- Plantilla de Brief de Prueba Rápida
- Plantilla de Actualización para Stakeholders
- Cuadro de Priorización de Experimentos
- Plantilla de Banco de Hipótesis

## Plantilla de Plan de Prueba

```markdown
# Prueba A/B: [Nombre]

## Resumen
- **Responsable**: [Nombre]
- **ID de Prueba**: [ID en herramienta de pruebas]
- **Página/Función**: [Qué se está probando]
- **Fechas planificadas**: [Inicio] - [Fin]

## Hipótesis

Porque [observación/datos],
creemos que [cambio]
causará [resultado esperado]
para [audiencia].
Sabremos que esto es cierto cuando [métricas].

## Diseño de la Prueba

| Elemento | Detalles |
|---------|---------|
| Tipo de prueba | A/B / A/B/n / MVT |
| Duración | X semanas |
| Tamaño de muestra | X por variante |
| Asignación de tráfico | 50/50 |
| Herramienta | [Nombre de herramienta] |
| Implementación | Lado del cliente / Lado del servidor |

## Variantes

### Control (A)
[Captura de pantalla]
- Experiencia actual
- [Detalles clave del estado actual]

### Variante (B)
[Captura de pantalla o maqueta]
- [Cambio específico #1]
- [Cambio específico #2]
- Justificación: [Por qué creemos que ganará]

## Métricas

### Primaria
- **Métrica**: [nombre de la métrica]
- **Definición**: [cómo se calcula]
- **Base actual**: [X%]
- **Efecto mínimo detectable**: [X%]

### Secundarias
- [Métrica 1]: [qué nos dice]
- [Métrica 2]: [qué nos dice]
- [Métrica 3]: [qué nos dice]

### Guardianes
- [Métrica que no debería empeorar]
- [Otra métrica de seguridad]

## Plan de Análisis de Segmentos
- Móvil vs. escritorio
- Visitantes nuevos vs. recurrentes
- Fuente de tráfico
- [Otros segmentos relevantes]

## Criterios de Éxito
- Ganador: [La métrica primaria mejora en X% con 95% de confianza]
- Perdedor: [La métrica primaria disminuye significativamente]
- Inconcluso: [Qué haremos si no hay resultado significativo]

## Lista de Verificación Pre-Lanzamiento
- [ ] Hipótesis documentada y revisada
- [ ] Métrica primaria definida y rastreable
- [ ] Tamaño de muestra calculado
- [ ] Duración de la prueba estimada
- [ ] Variantes implementadas correctamente
- [ ] Seguimiento verificado en todas las variantes
- [ ] Control de calidad completado en todas las variantes
- [ ] Stakeholders informados
- [ ] Recordatorio en el calendario para la fecha de análisis
```

---

## Plantilla de Documentación de Resultados

```markdown
# Resultados de Prueba A/B: [Nombre]

## Resumen
| Elemento | Valor |
|---------|-------|
| ID de Prueba | [ID] |
| Fechas | [Inicio] - [Fin] |
| Duración | X días |
| Resultado | Ganador / Perdedor / Inconcluso |
| Decisión | [Qué haremos] |

## Hipótesis (Recordatorio)
[Copiar del plan de prueba]

## Resultados

### Tamaño de Muestra
| Variante | Objetivo | Real | % del objetivo |
|---------|--------|--------|----------------|
| Control | X | Y | Z% |
| Variante | X | Y | Z% |

### Métrica Primaria: [Nombre de la Métrica]
| Variante | Valor | IC 95% | vs. Control |
|---------|-------|--------|-------------|
| Control | X% | [X%, Y%] | — |
| Variante | X% | [X%, Y%] | +X% |

**Significancia estadística**: p = X.XX (95% = sig / no sig)
**Significancia práctica**: [¿Es este aumento significativo para el negocio?]

### Métricas Secundarias

| Métrica | Control | Variante | Cambio | ¿Significativo? |
|--------|---------|---------|--------|----------------|
| [Métrica 1] | X | Y | +Z% | Sí/No |
| [Métrica 2] | X | Y | +Z% | Sí/No |

### Métricas Guardianas

| Métrica | Control | Variante | Cambio | ¿Preocupante? |
|--------|---------|---------|--------|---------------|
| [Métrica 1] | X | Y | +Z% | Sí/No |

### Análisis de Segmentos

**Móvil vs. Escritorio**
| Segmento | Control | Variante | Aumento |
|---------|---------|---------|---------|
| Móvil | X% | Y% | +Z% |
| Escritorio | X% | Y% | +Z% |

**Nuevos vs. Recurrentes**
| Segmento | Control | Variante | Aumento |
|---------|---------|---------|---------|
| Nuevos | X% | Y% | +Z% |
| Recurrentes | X% | Y% | +Z% |

## Interpretación

### ¿Qué ocurrió?
[Explicación de los resultados en lenguaje claro]

### ¿Por qué creemos que ocurrió esto?
[Análisis y razonamiento]

### Advertencias
[Limitaciones, factores externos o preocupaciones]

## Decisión

**Ganador**: [Control / Variante]

**Acción**: [Implementar variante / Mantener control / Volver a probar]

**Plazo**: [Cuándo se implementarán los cambios]

## Aprendizajes

### Lo que aprendimos
- [Insight clave 1]
- [Insight clave 2]

### Qué probar a continuación
- [Idea de prueba de seguimiento 1]
- [Idea de prueba de seguimiento 2]

### Impacto
- **Aumento proyectado**: [Mejora de X% en la métrica Y]
- **Impacto empresarial**: [Ingresos, conversiones, etc.]
```

---

## Plantilla de Entrada al Repositorio de Pruebas

Para rastrear todas las pruebas en una ubicación central:

```markdown
| ID Prueba | Nombre | Página | Fechas | Métrica Primaria | Resultado | Aumento | Enlace |
|----------|------|------|-------|----------------|--------|------|------|
| 001 | Prueba de título hero | Inicio | 1/1-1/15 | CTR | Ganador | +12% | [Enlace] |
| 002 | Layout tabla de precios | Precios | 1/10-1/31 | Selección de plan | Perdedor | -5% | [Enlace] |
| 003 | Campos del formulario de registro | Registro | 2/1-2/14 | Completación | Inconcluso | +2% | [Enlace] |
```

---

## Plantilla de Brief de Prueba Rápida

Para pruebas simples que no necesitan documentación completa:

```markdown
## [Nombre de la Prueba]

**Qué**: [Descripción en una oración]
**Por qué**: [Hipótesis en una oración]
**Métrica**: [Métrica primaria]
**Duración**: [X semanas]
**Resultado**: [Por definir / Ganador / Perdedor / Inconcluso]
**Aprendizajes**: [Conclusión clave]
```

---

## Plantilla de Actualización para Stakeholders

```markdown
## Actualización de Prueba A/B: [Nombre]

**Estado**: En ejecución / Completa
**Días restantes**: X (o completa)
**Muestra actual**: X% del objetivo

### Observaciones preliminares
[Lo que estamos viendo — sin tomar decisiones aún]

### Próximos pasos
[Qué ocurre a continuación]

### Cronograma
- [Fecha]: Análisis completo
- [Fecha]: Decisión y recomendación
- [Fecha]: Implementación (si hay ganador)
```

---

## Cuadro de Priorización de Experimentos

Para decidir qué pruebas ejecutar:

| Factor | Peso | Prueba A | Prueba B | Prueba C |
|--------|------|--------|--------|--------|
| Impacto potencial | 30% | | | |
| Confianza en la hipótesis | 25% | | | |
| Facilidad de implementación | 20% | | | |
| Riesgo si es incorrecto | 15% | | | |
| Alineación estratégica | 10% | | | |
| **Total** | | | | |

Puntuación: 1-5 (5 = mejor)

---

## Plantilla de Banco de Hipótesis

Para recopilar ideas de prueba:

```markdown
| ID | Página/Área | Observación | Hipótesis | Impacto Potencial | Estado |
|----|-----------|-------------|------------|------------------|--------|
| H1 | Inicio | Profundidad de scroll baja | Hero más corto aumentará el scroll | Alto | Probando |
| H2 | Precios | Usuarios comparan planes | Tabla de comparación ayudará | Medio | Backlog |
| H3 | Registro | Abandono en email | Login social aumentará la completación | Medio | Backlog |
```
