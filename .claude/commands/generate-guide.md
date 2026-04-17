---
description: Genera la guía detallada del moderador para un laboratorio. Uso: /generate-guide 01
---

Genera la guía completa del moderador para el Lab $ARGUMENTS.

## Instrucciones

1. Lee `content/lab-index.md` para la estructura y timing del Lab $ARGUMENTS
2. Lee `content/lab-$ARGUMENTS/slides-content.md` para alinear con los slides
3. Carga el skill de conocimiento AI relevante:
   - Lab 01: `skills/ai-knowledge/ai-fundamentals/SKILL.md`
   - Lab 02: `skills/ai-knowledge/context-compaction/SKILL.md`
   - Lab 03: `skills/ai-knowledge/agents-skills-commands/SKILL.md`
   - Lab 04: `skills/ai-knowledge/ai-tools-comparison/SKILL.md`
4. Lee `skills/content/moderator-guide/SKILL.md` para el formato
5. Genera `content/lab-$ARGUMENTS/guide.md` con:
   - Información general (duración, audiencia, objetivo)
   - Preparación previa (checklist)
   - Cada sección con: puntos clave, guion sugerido, analogías, preguntas del público, transiciones
   - Timing exacto por sección
