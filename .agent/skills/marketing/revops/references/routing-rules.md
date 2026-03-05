# Reglas de Enrutamiento de Leads

Árboles de decisión, configuraciones específicas por plataforma, enrutamiento por territorio, enrutamiento ABM y benchmarks de velocidad hacia el lead.

## Árbol de Decisión de Enrutamiento

Usar esta plantilla para mapear tu lógica de enrutamiento:

```
Nuevo Lead Llega
│
├─ ¿Es esta una cuenta nombrada/objetivo?
│  ├─ SÍ → Enrutar al propietario de cuenta asignado
│  └─ NO ↓
│
├─ ¿El ACV probable es > $50K? (basado en tamaño de empresa + industria)
│  ├─ SÍ → Enrutar al equipo de AE enterprise
│  └─ NO ↓
│
├─ ¿Es esto un registro PLG con uso de equipo?
│  ├─ SÍ → Enrutar al especialista en ventas PLG
│  └─ NO ↓
│
├─ ¿El lead coincide con un territorio?
│  ├─ SÍ → Enrutar al propietario del territorio
│  └─ NO ↓
│
└─ Por defecto: Round-robin entre representantes disponibles
   └─ Si no hay representante disponible: Asignar a la cola del equipo con SLA de 1 hora
```

Personalizar este árbol para tu negocio. El principio clave: **enrutar al match más específico primero, recurrir al general.**

---

## Configuración de Round-Robin

### Reglas Básicas de Round-Robin

1. Distribuir leads equitativamente entre representantes elegibles
2. Omitir representantes que están de vacaciones, con capacidad máxima o tienen un pipeline lleno
3. Ponderar por logro de cuota (los representantes por debajo de la cuota reciben ligera prioridad)
4. Restablecer el conteo de distribución semanal o mensualmente
5. Registrar cada asignación para auditoría

### Configuración de Round-Robin en HubSpot

**Usando la herramienta de rotación de HubSpot:**
- Navegar a Automatización → Flujos de trabajo
- Disparador: Propiedad de contacto "Etapa del Ciclo de Vida" igual a "MQL"
- Acción: Rotar el propietario del contacto entre los usuarios seleccionados
- Opciones: Distribución equitativa, omitir propietarios no disponibles
- Agregar retraso + creación de tarea después de la asignación

**Rotación personalizada con flujos de trabajo:**
1. Crear una propiedad personalizada "Contador de Rotación" (número)
2. Disparador del flujo de trabajo: Nuevo MQL creado
3. Ramificar por valor del contador de rotación (0, 1, 2... para cada representante)
4. Establecer el propietario del contacto al representante correspondiente
5. Incrementar el contador (restablecer al máximo)
6. Crear tarea de seguimiento con fecha límite de SLA

### Configuración de Round-Robin en Salesforce

**Usando Reglas de Asignación de Lead:**
1. Configuración → Ajustes de Funciones → Marketing → Reglas de Asignación de Lead
2. Crear entradas de reglas en orden de prioridad (más específico primero)
3. Para round-robin: Usar regla de asignación + lógica personalizada

**Usando Flow para enrutamiento avanzado:**
1. Crear un Flow Activado por Registro en la creación de Lead
2. Obtener Registros: Consultar un objeto personalizado "Cola de Representantes" para el siguiente representante disponible
3. Elemento de Decisión: Verificar disponibilidad del representante, capacidad, territorio
4. Actualizar Registros: Asignar propietario del lead
5. Crear Tarea: Tarea de seguimiento con SLA
6. Actualizar "Cola de Representantes" para rastrear la última asignación

---

## Enrutamiento por Territorio

### Por Geografía

| Territorio | Regiones | Equipo Asignado |
|-----------|---------|---------------|
| Oeste | CA, WA, OR, NV, AZ, UT, CO, HI | Equipo Oeste |
| Central | TX, IL, MN, MO, OH, MI, WI, IN | Equipo Central |
| Este | NY, MA, PA, NJ, CT, VA, FL, GA | Equipo Este |
| Internacional | Todo fuera de EE.UU. | Equipo Internacional |

### Por Tamaño de Empresa

| Segmento | Tamaño de Empresa | Equipo |
|---------|-------------|------|
| PYME | 1-50 empleados | Ventas internas |
| Mercado medio | 51-500 empleados | AEs de mercado medio |
| Enterprise | 501-5000 empleados | AEs Enterprise |
| Estratégico | 5000+ empleados | Equipo de cuentas estratégicas |

### Por Industria

| Vertical | Industrias | Especialista |
|----------|-----------|------------|
| Tecnología | SaaS, servicios de TI, hardware | Rep. vertical de tecnología |
| Finanzas | Banca, seguros, fintech | Rep. vertical financiero |
| Salud | Hospitales, farmacia, healthtech | Rep. vertical de salud |
| General | Todos los demás | Pool general (round-robin) |

### Modelo de Territorio Híbrido

Combinar múltiples dimensiones para precisión:

```
Lead llega
├─ ¿Tamaño de empresa > 1000?
│  ├─ SÍ → Equipo enterprise
│  │  └─ Sub-enrutar por geografía
│  └─ NO ↓
├─ ¿Industria = Salud o Finanzas?
│  ├─ SÍ → Especialista vertical
│  └─ NO ↓
└─ Round-robin entre el pool general
   └─ Ponderado por preferencia geográfica
```

---

## Enrutamiento de Cuenta Nombrada / ABM

### Configuración

1. **Definir la lista de cuentas objetivo** (típicamente 50-500 cuentas)
2. **Asignar propietarios de cuentas** en CRM (1 representante por cuenta)
3. **Lógica de coincidencia:** Cualquier lead de un dominio de cuenta objetivo se enruta al propietario de la cuenta
4. **Reglas de coincidencia:**
   - Coincidencia de dominio de email (primaria)
   - Coincidencia aproximada del nombre de empresa (secundaria, requiere revisión manual)
   - Resolución de IP a empresa (terciaria, para visitantes anónimos)

### Reglas de Enrutamiento ABM

| Nivel | Tipo de Cuenta | Enrutamiento | SLA de Respuesta |
|------|-------------|---------|----------|
| Nivel 1 | 20 cuentas estratégicas principales | Propietario nombrado, alerta instantánea | 1 hora |
| Nivel 2 | 100 cuentas objetivo principales | Propietario nombrado, alerta estándar | 4 horas |
| Nivel 3 | Coincidencia de industria / tamaño objetivo | Territorio o round-robin | El mismo día hábil |

### Manejo de Múltiples Contactos

Cuando varios contactos de la misma cuenta se involucran:
- Enrutar todos los contactos al **mismo propietario de cuenta**
- Notificar al propietario de los nuevos contactos que entran
- Rastrear la puntuación de engagement a nivel de cuenta (suma de todos los contactos)
- Activar alerta de "comité de compra" cuando 3+ contactos de una cuenta se involucran

---

## Datos de Velocidad hacia el Lead

### Impacto del Tiempo de Respuesta en la Conversión

| Tiempo de Respuesta | Tasa de Calificación Relativa | Notas |
|---------------|---------------------------|-------|
| Menos de 5 minutos | **21x** más probabilidades de calificar | Estándar dorado |
| 5-10 minutos | 10x más probabilidades | Aún fuerte |
| 10-30 minutos | 4x más probabilidades | Aceptable para la mayoría |
| 30 min - 1 hora | 2x más probabilidades | Por debajo de la mejor práctica |
| 1-24 horas | Baseline | Promedio de la industria |
| 24+ horas | 60% menor que el baseline | El lead está efectivamente frío |

Fuente: Lead Connect, InsideSales.com

### Implementando la Velocidad hacia el Lead

1. **Notificación instantánea** — Notificación push + email al representante al crear MQL
2. **Tarea automática con temporizador** — Crear tarea con cuenta regresiva de SLA de 5 minutos
3. **Cadena de escalación:**
   - 5 min: Rep. original alertado
   - 15 min: Rep. de respaldo alertado
   - 30 min: Gerente alertado
   - 1 hora: Lead reasignado al siguiente representante disponible
4. **Medir y reportar** — Rastrear tiempos de respuesta reales semanalmente; reconocer a los que responden rápido

### Automatización de Velocidad hacia el Lead

**Disparador:** Nuevo MQL creado
**Acciones:**
1. Asignar al representante mediante reglas de enrutamiento (instantáneo)
2. Enviar notificación push + email al representante
3. Crear tarea: "Contactar a [Nombre del Lead] — SLA de 5 min"
4. Iniciar temporizador de SLA
5. Si no se registra actividad en 15 min → alertar al representante de respaldo
6. Si no hay actividad en 30 min → alertar al gerente
7. Si no hay actividad en 60 min → reasignar mediante round-robin

### Medir la Velocidad hacia el Lead

Rastrear estas métricas semanalmente:
- **Tiempo promedio hasta el primer contacto** (desde la creación del MQL hasta primera llamada/email)
- **Tiempo mediano hasta el primer contacto** (menos sesgado por valores atípicos)
- **% de leads contactados dentro del SLA** (objetivo: 90%+)
- **Tasa de contacto por hora del día** (identificar brechas de cobertura)
- **Tasa de conversión por tiempo de respuesta** (demostrar el ROI de la velocidad)
