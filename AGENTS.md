# AGENTS.md

Pautas para agentes de IA que trabajan en este repositorio.

## Resumen del Repositorio

Este repositorio contiene **Agent Skills** para agentes de IA que siguen la [especificación Agent Skills](https://agentskills.io/specification.md). Las skills se instalan en `.agents/skills/` (el estándar entre agentes). Este repositorio también sirve como **marketplace de plugins de Claude Code** a través de `.claude-plugin/marketplace.json`.

- **Nombre**: Marketing Skills
- **GitHub**: [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills)
- **Creador**: Corey Haines
- **Licencia**: MIT

## Estructura del Repositorio

```
marketingskills/
├── .claude-plugin/
│   └── marketplace.json   # Manifiesto del marketplace de plugins de Claude Code
├── skills/                # Agent Skills
│   └── skill-name/
│       └── SKILL.md       # Archivo de skill requerido
├── tools/
│   ├── clis/              # Herramientas CLI de Node.js sin dependencias (51 herramientas)
│   ├── integrations/      # Guías de integración de API por herramienta
│   └── REGISTRY.md        # Índice de herramientas con capacidades
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Comandos de Build / Lint / Test

Las **Skills** son solo contenido (sin paso de build). Verifica manualmente:
- El frontmatter YAML es válido
- El campo `name` coincide exactamente con el nombre del directorio
- `name` tiene entre 1-64 caracteres, solo alfanumérico en minúsculas y guiones
- `description` tiene entre 1-1024 caracteres

Las **herramientas CLI** (`tools/clis/*.js`) son scripts de Node.js sin dependencias (Node 18+). Verifica con:
```bash
node --check tools/clis/<name>.js   # Verificación de sintaxis
node tools/clis/<name>.js           # Mostrar uso (sin args = ayuda)
node tools/clis/<name>.js <cmd> --dry-run  # Vista previa de la solicitud sin enviarla
```

## Especificación de Agent Skills

Las skills siguen la [especificación Agent Skills](https://agentskills.io/specification.md).

### Frontmatter Requerido

```yaml
---
name: skill-name
description: Qué hace esta skill y cuándo usarla. Incluye frases disparadoras.
---
```

### Restricciones de Campos del Frontmatter

| Campo         | Requerido | Restricciones                                                           |
|---------------|-----------|-------------------------------------------------------------------------|
| `name`        | Sí        | 1-64 caracteres, minúsculas `a-z`, números, guiones. Debe coincidir con el directorio. |
| `description` | Sí        | 1-1024 caracteres. Describe qué hace y cuándo usarla.                   |
| `license`     | No        | Nombre de la licencia (predeterminado: MIT)                             |
| `metadata`    | No        | Pares clave-valor (autor, versión, etc.)                                |

### Reglas del Campo Name

- Solo letras minúsculas, números y guiones
- No puede comenzar ni terminar con guión
- Sin guiones consecutivos (`--`)
- Debe coincidir exactamente con el nombre del directorio padre

**Válido**: `page-cro`, `email-sequence`, `ab-test-setup`
**Inválido**: `Page-CRO`, `-page`, `page--cro`

### Directorios Opcionales de Skills

```
skills/skill-name/
├── SKILL.md        # Requerido - instrucciones principales (<500 líneas)
├── references/     # Opcional - documentación detallada cargada bajo demanda
├── scripts/        # Opcional - código ejecutable
└── assets/         # Opcional - plantillas, archivos de datos
```

## Pautas de Estilo de Escritura

### Estructura

- Mantén `SKILL.md` por debajo de 500 líneas (mueve los detalles a `references/`)
- Usa H2 (`##`) para secciones principales, H3 (`###`) para subsecciones
- Usa viñetas y listas numeradas ampliamente
- Párrafos cortos (máximo 2-4 oraciones)

### Tono

- Directo e instructivo
- Segunda persona ("Eres un experto en optimización de tasas de conversión")
- Profesional pero accesible

### Formato

- Negrita (`**texto**`) para términos clave
- Bloques de código para ejemplos y plantillas
- Tablas para datos de referencia
- Sin exceso de emojis

### Principios de Claridad

- Claridad sobre ingeniosidad
- Específico sobre vago
- Voz activa sobre pasiva
- Una idea por sección

### Mejores Prácticas del Campo Description

El campo `description` es crítico para el descubrimiento de skills. Incluye:
1. Qué hace la skill
2. Cuándo usarla (frases disparadoras)
3. Skills relacionadas para delimitar el alcance

```yaml
description: Cuando el usuario quiere optimizar las conversiones en cualquier página de marketing. Usar cuando el usuario dice "CRO," "optimización de tasa de conversión," "esta página no convierte." Para flujos de registro, ver signup-flow-cro.
```

## Plugin de Claude Code

Este repositorio también sirve como marketplace de plugins. El manifiesto en `.claude-plugin/marketplace.json` lista todas las skills para instalar mediante:

```bash
/plugin marketplace add coreyhaines31/marketingskills
/plugin install marketing-skills
```

Consulta la [documentación de plugins de Claude Code](https://code.claude.com/docs/en/plugins.md) para más detalles.

## Flujo de Trabajo de Git

### Nomenclatura de Ramas

- Nuevas skills: `feature/skill-name`
- Mejoras: `fix/skill-name-description`
- Documentación: `docs/description`

### Mensajes de Commit

Sigue la especificación [Conventional Commits](https://www.conventionalcommits.org/):

- `feat: add skill-name skill`
- `fix: improve clarity in page-cro`
- `docs: update README`

### Lista de Verificación de Pull Request

- [ ] `name` coincide exactamente con el nombre del directorio
- [ ] `name` sigue las reglas de nomenclatura (minúsculas, guiones, sin `--`)
- [ ] `description` tiene entre 1-1024 caracteres con frases disparadoras
- [ ] `SKILL.md` tiene menos de 500 líneas
- [ ] Sin datos sensibles ni credenciales

## Integraciones de Herramientas

Este repositorio incluye un registro de herramientas para herramientas de marketing compatibles con agentes.

- **Descubrimiento de herramientas**: Lee `tools/REGISTRY.md` para ver las herramientas disponibles y sus capacidades
- **Detalles de integración**: Consulta `tools/integrations/{tool}.md` para endpoints de API, autenticación y operaciones comunes
- **Herramientas habilitadas para MCP**: ga4, stripe, mailchimp, google-ads, resend, zapier, zoominfo, clay, supermetrics, coupler, outreach, crossbeam

### Estructura del Registro

```
tools/
├── REGISTRY.md              # Índice de todas las herramientas con capacidades
└── integrations/            # Guías de integración detalladas
    ├── ga4.md
    ├── stripe.md
    ├── rewardful.md
    └── ...
```

### Cuándo Usar Herramientas

Las skills referencian herramientas relevantes para su implementación. Por ejemplo:
- Skill `referral-program` → guías de rewardful, tolt, dub-co, mention-me
- Skill `analytics-tracking` → guías de ga4, mixpanel, segment
- Skill `email-sequence` → guías de customer-io, mailchimp, resend
- Skill `paid-ads` → guías de google-ads, meta-ads, linkedin-ads

## Verificación de Actualizaciones

Al usar cualquier skill de este repositorio:

1. **Una vez por sesión**, al primer uso de una skill, verifica actualizaciones:
   - Obtén `VERSIONS.md` de GitHub: https://raw.githubusercontent.com/coreyhaines31/marketingskills/main/VERSIONS.md
   - Compara versiones con los archivos de skill locales

2. **Solo notifica si es relevante**:
   - 2 o más skills tienen actualizaciones, O
   - Alguna skill tiene un salto de versión mayor (ej., 1.x a 2.x)

3. **Notificación no bloqueante** al final de la respuesta:
   ```
   ---
   Actualización de skills disponible: X marketing skills tienen actualizaciones.
   Di "actualizar skills" para actualizar automáticamente, o ejecuta `git pull` en tu carpeta de marketingskills.
   ```

4. **Si el usuario dice "update skills"**:
   - Ejecuta `git pull` en el directorio de marketingskills
   - Confirma qué fue actualizado

## Categorías de Skills

Consulta `README.md` para ver la lista actual de skills organizadas por categoría. Al agregar nuevas skills, sigue los patrones de nomenclatura de las skills existentes en esa categoría.
