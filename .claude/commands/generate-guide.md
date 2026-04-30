---
description: Genera la guía detallada del moderador para un laboratorio. Uso: /generate-guide 01
---

Genera la guía completa del moderador para el Lab $ARGUMENTS.

## Instrucciones

### Paso 1: Leer estructura y formato (siempre)
1. Lee `content/lab-index.md` para la estructura y timing del Lab $ARGUMENTS
2. Lee `skills/content/moderator-guide/SKILL.md` para las reglas de formato de la guía
3. Lee `skills/content/lab-content-system/SKILL.md` para las reglas de timing y tipos de slide

### Paso 2: Obtener contenido del lab
1. Carga el skill de conocimiento AI relevante (siempre):
   - Lab 01: `skills/ai-knowledge/ai-fundamentals/SKILL.md`
   - Lab 02: `skills/ai-knowledge/context-compaction/SKILL.md`
   - Lab 03: `skills/ai-knowledge/agents-skills-commands/SKILL.md`
   - Lab 04: `skills/ai-knowledge/ai-tools-comparison/SKILL.md`
2. **Si existe** `content/lab-$ARGUMENTS/slides-content.md` → leerlo para alinear con los slides
3. **Si NO existe** → usar `content/lab-index.md` + el skill de conocimiento como fuente

### Paso 3: Generar guía del moderador
Genera `content/lab-$ARGUMENTS/guide.md` con:
- Información general (duración, audiencia, objetivo)
- Preparación previa (checklist)
- Cada sección con: puntos clave, guion sugerido, analogías, preguntas del público, transiciones
- Timing exacto por sección
- Sección de tiempo abierto (20 min) con opciones de dinámica
- Notas finales: ritmo, manejo de tiempo, errores comunes, distribución de tiempo, checklist post-sesión

Usar `content/lab-01/guide.md` como referencia de formato y nivel de detalle.

### Paso 4: Generar notas de timing
Genera `content/lab-$ARGUMENTS/notes.md` con:
- Tabla de timing por sección (slide, tiempo, acumulado)
- Transiciones clave entre secciones (frases exactas)
- Señales de alerta si se atrasa
- Señales de que va bien

Usar `content/lab-01/notes.md` como referencia de formato.
