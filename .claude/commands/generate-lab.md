---
description: Genera los slides Slidev completos para un laboratorio específico. Uso: /generate-lab 01
---

Genera la presentación Slidev completa para el Lab $ARGUMENTS.

## Instrucciones

1. Lee `content/lab-index.md` para obtener la estructura del Lab $ARGUMENTS
2. Lee `content/lab-$ARGUMENTS/slides-content.md` para los bullets de cada slide
3. Lee `skills/design/slidev-futuristic/SKILL.md` para la sintaxis y configuración Slidev
4. Lee `skills/design/color-system/SKILL.md` para los colores exactos
5. Genera el archivo `presentations/lab-$ARGUMENTS/slides.md` con:
   - Frontmatter Slidev correcto
   - Importación del CSS del tema
   - Cada slide con su layout correspondiente (cover, interactive, comparison, analogy, default)
   - Notas del presentador en cada slide
   - Transiciones entre slides
6. Verifica que el número de slides coincida con lab-index.md
