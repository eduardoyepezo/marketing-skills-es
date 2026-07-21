# Plantilla de Asesor Personalizado

Copia esta estructura para agregar un asesor al panel. Guarda los asesores personalizados en `.agents/advisors/<nombre-en-kebab-case>.md` en tu proyecto (no dentro de la carpeta de la skill) para que sobrevivan a las actualizaciones de la skill.

Dos tipos de asesores personalizados, dos estándares de fundamentación:

- **Figuras públicas** (un marketer famoso que no está en el panel): cada framework y postura debe rastrearse hasta algo que publicó o dijo — investiga antes de escribir, cita fuentes, sigue las mismas reglas de fundamentación que los dossiers integrados.
- **Asesores privados** (tu antiguo jefe, tu mejor cliente, tu CFO): el *usuario* proporciona las posturas y heurísticas. El agente no debe inventar puntos de vista para una persona privada real — entrevista al usuario para completar la plantilla.

---

```markdown
# [Nombre Completo]

**Óptica:** [Una frase — la forma distintiva en que ve los problemas de marketing.]

## Frameworks principales

- **[Nombre del framework]** ([fuente, año]): [Definición precisa de 1-2 frases.]
- …3-6 en total. Si viene de alguien más, dilo.

## Posturas documentadas

- [Una opinión fuerte que realmente sostiene] — *[fuente]*
- …5-8 en total. Incluye al menos una postura contraria; una persona sin
  opiniones impopulares no produce ningún desacuerdo útil.

## Preguntas características

- [Una pregunta que característicamente hace sobre cualquier problema de marketing]
- …3-5 en total. Estas abren la postura del asesor en una sesión.

## Mejor para / puntos ciegos

**Mejor para:** [tipos de problema que su óptica realmente ilumina]
**Puntos ciegos:** [críticas documentadas o límites reconocidos — esto es
lo que hace que su disidencia sea honesta y no decorativa]

## Notas de voz

[2-3 frases: ritmo de las oraciones, metáforas favoritas, tono, tics. Suficiente
para escribir en su registro sin inventar citas.]

## Obras clave

- *[Título]* ([año]) — [una línea sobre qué aporta a la persona]
```

---

**Sentando a un asesor personalizado:** menciónalo por nombre al convocar ("sienta a mi asesora Maria en este consejo"). El agente carga el archivo desde `.agents/advisors/` y lo trata como cualquier dossier del panel, incluyendo las reglas de fundamentación — sin citas inventadas, sin avales inventados.
