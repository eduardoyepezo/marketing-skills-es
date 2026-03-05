# Contribuir

¡Gracias por tu interés en contribuir a Marketing Skills! Esta guía te ayudará a agregar nuevas skills o mejorar las existentes.

## Solicitar una Skill

También puedes sugerir nuevas skills [abriendo una solicitud de skill](https://github.com/coreyhaines31/marketingskills/issues/new?template=skill-request.yml).

## Agregar una Nueva Skill

### 1. Crea el directorio de la skill

```bash
mkdir -p skills/your-skill-name
```

### 2. Crea el archivo SKILL.md

Cada skill necesita un archivo `SKILL.md` con frontmatter YAML:

```yaml
---
name: your-skill-name
description: Cuándo usar esta skill. Incluye frases disparadoras y palabras clave que ayuden a los agentes a identificar tareas relevantes.
---

# Nombre de Tu Skill

Las instrucciones para el agente van aquí...
```

Campos opcionales de frontmatter: `license` (predeterminado: MIT), `metadata` (autor, versión, etc.)

### 3. Sigue las convenciones de nomenclatura

- **Nombre del directorio**: minúsculas, solo guiones (ej., `email-sequence`)
- **Campo name**: debe coincidir exactamente con el nombre del directorio
- **Description**: 1-1024 caracteres, incluye frases disparadoras

### 4. Estructura tu skill

```
skills/your-skill-name/
├── SKILL.md           # Requerido - instrucciones principales
├── references/        # Opcional - documentación adicional
│   └── guide.md
├── scripts/           # Opcional - código ejecutable
│   └── helper.py
└── assets/            # Opcional - plantillas, imágenes, datos
    └── template.json
```

### 5. Escribe instrucciones efectivas

- Mantén `SKILL.md` por debajo de 500 líneas
- Mueve el material de referencia detallado a `references/`
- Incluye instrucciones paso a paso
- Agrega ejemplos de entradas y salidas
- Cubre casos límite comunes

## Mejorar Skills Existentes

1. Lee la skill existente en su totalidad
2. Prueba tus cambios localmente
3. Mantén los cambios enfocados y mínimos
4. Actualiza la versión en los metadatos si realizas cambios significativos

## Enviar tu Contribución

1. Haz un fork del repositorio
2. Crea una rama de funcionalidad (`git checkout -b feature/new-skill-name`)
3. Realiza tus cambios
4. Prueba localmente con un agente de IA
5. Envía un pull request usando la plantilla apropiada:
   - [Nueva Skill](?template=new-skill.md)
   - [Actualización de Skill](?template=skill-update.md)
   - [Documentación](?template=documentation.md)

## Lista de Verificación de Calidad de la Skill

- [ ] `name` coincide con el nombre del directorio
- [ ] `description` explica claramente cuándo usar la skill
- [ ] Las instrucciones son claras y accionables
- [ ] No hay datos sensibles ni credenciales
- [ ] Sigue los patrones de skills existentes en el repositorio

## ¿Preguntas?

Abre un issue si tienes preguntas o necesitas ayuda con tu contribución.
