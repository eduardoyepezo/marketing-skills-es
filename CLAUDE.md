# AGENTS.md

Guía para agentes de IA que trabajan en este repositorio.

## Descripción General del Repositorio

Este repositorio contiene **Agent Skills** para agentes de IA que siguen la [especificación de Agent Skills](https://agentskills.io/specification.md). Las skills se instalan en `.agents/skills/` (el estándar entre agentes). Este repositorio también funciona como **marketplace de plugins de Claude Code** a través de `.claude-plugin/marketplace.json`.

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

Las **Skills** son solo contenido (sin paso de build). Verificar manualmente:
- El frontmatter YAML es válido
- El campo `name` coincide exactamente con el nombre del directorio
- `name` tiene entre 1-64 caracteres, solo alfanuméricos en minúsculas y guiones
- `description` tiene entre 1-1024 caracteres

**Herramientas CLI** (`tools/clis/*.js`) son scripts Node.js sin dependencias (Node 18+). Verificar con:
```bash
node --check tools/clis/<name>.js   # Verificación de sintaxis
node tools/clis/<name>.js           # Mostrar uso (sin args = ayuda)
node tools/clis/<name>.js <cmd> --dry-run  # Vista previa sin enviar
```

## Especificación de Agent Skills

Las skills siguen la [especificación de Agent Skills](https://agentskills.io/specification.md).

### Frontmatter Requerido

```yaml
---
name: skill-name
description: Qué hace esta skill y cuándo usarla. Incluir frases disparadoras.
---
```

### Restricciones de Campos del Frontmatter

| Campo         | Requerido | Restricciones                                                        |
|---------------|-----------|----------------------------------------------------------------------|
| `name`        | Sí        | 1-64 caracteres, minúsculas `a-z`, números, guiones. Debe coincidir con el directorio. |
| `description` | Sí        | 1-1024 caracteres. Describir qué hace y cuándo usarlo.               |
| `license`     | No        | Nombre de licencia (por defecto: MIT)                                |
| `metadata`    | No        | Pares clave-valor (autor, versión, etc.)                             |

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

## Guía de Estilo de Escritura

### Estructura

- Mantener `SKILL.md` bajo 500 líneas (mover detalles a `references/`)
- Usar H2 (`##`) para secciones principales, H3 (`###`) para subsecciones
- Usar viñetas y listas numeradas con frecuencia
- Párrafos cortos (máximo 2-4 oraciones)

### Tono

- Directo e instruccional
- Segunda persona ("Eres un experto en optimización de conversiones")
- Profesional pero accesible

### Formato

- Negrita (`**texto**`) para términos clave
- Bloques de código para ejemplos y plantillas
- Tablas para datos de referencia
- Sin emojis excesivos

### Principios de Claridad

- Claridad sobre ingeniosidad
- Específico sobre vago
- Voz activa sobre pasiva
- Una idea por sección

### Mejores Prácticas para el Campo Description

El campo `description` es crítico para el descubrimiento de skills. Incluir:
1. Qué hace la skill
2. Cuándo usarla (frases de activación)
3. Skills relacionadas para delimitar el alcance

```yaml
description: Cuando el usuario quiere optimizar las conversiones en cualquier página de marketing. Usar cuando el usuario dice "CRO," "optimización de tasa de conversión," "esta página no convierte." Para flujos de registro, ver signup-flow-cro.
```

## Plugin de Claude Code

Este repositorio también funciona como marketplace de plugins. El manifiesto en `.claude-plugin/marketplace.json` lista todas las skills para instalación a través de:

```bash
/plugin marketplace add coreyhaines31/marketingskills
/plugin install marketing-skills
```

Consultar la [documentación de plugins de Claude Code](https://code.claude.com/docs/en/plugins.md) para más detalles.

## Flujo de Trabajo con Git

### Nomenclatura de Ramas

- Skills nuevas: `feature/skill-name`
- Mejoras: `fix/skill-name-description`
- Documentación: `docs/description`

### Mensajes de Commit

Seguir la especificación [Conventional Commits](https://www.conventionalcommits.org/):

- `feat: add skill-name skill`
- `fix: improve clarity in page-cro`
- `docs: update README`

### Checklist de Pull Request

- [ ] `name` coincide exactamente con el nombre del directorio
- [ ] `name` sigue las reglas de nomenclatura (minúsculas, guiones, sin `--`)
- [ ] `description` tiene entre 1-1024 caracteres con frases de activación
- [ ] `SKILL.md` tiene menos de 500 líneas
- [ ] Sin datos sensibles ni credenciales

## Integraciones de Herramientas

Este repositorio incluye un registro de herramientas compatibles con agentes para marketing.

- **Descubrimiento de herramientas**: Leer `tools/REGISTRY.md` para ver las herramientas disponibles y sus capacidades
- **Detalles de integración**: Ver `tools/integrations/{tool}.md` para endpoints de API, autenticación y operaciones comunes
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

### Cuándo Usar las Herramientas

Las skills hacen referencia a las herramientas relevantes para la implementación. Por ejemplo:
- Skill `referral-program` → guías de rewardful, tolt, dub-co, mention-me
- Skill `analytics-tracking` → guías de ga4, mixpanel, segment
- Skill `email-sequence` → guías de customer-io, mailchimp, resend
- Skill `paid-ads` → guías de google-ads, meta-ads, linkedin-ads

## Verificación de Actualizaciones

Al usar cualquier skill de este repositorio:

1. **Una vez por sesión**, en el primer uso de una skill, verificar actualizaciones:
   - Obtener `VERSIONS.md` de GitHub: https://raw.githubusercontent.com/coreyhaines31/marketingskills/main/VERSIONS.md
   - Comparar versiones con los archivos de skill locales

2. **Solo notificar si es relevante**:
   - 2 o más skills tienen actualizaciones, O
   - Alguna skill tiene un salto de versión mayor (por ejemplo, de 1.x a 2.x)

3. **Notificación no bloqueante** al final de la respuesta:
   ```
   ---
   Actualización de skills disponible: X marketing skills tienen actualizaciones.
   Di "actualizar skills" para actualizar automáticamente, o ejecuta `git pull` en tu carpeta marketingskills.
   ```

4. **Si el usuario dice "actualizar skills"**:
   - Ejecutar `git pull` en el directorio marketingskills
   - Confirmar qué se actualizó

## Categorías de Skills

Ver `README.md` para la lista actual de skills organizadas por categoría. Al agregar nuevas skills, seguir los patrones de nomenclatura de las skills existentes en esa categoría.
