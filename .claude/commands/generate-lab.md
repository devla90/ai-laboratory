---
description: Genera los slides Slidev completos para un laboratorio específico. Uso: /generate-lab 01
---

Genera la presentación Slidev completa para el Lab $ARGUMENTS.

## Instrucciones

### Paso 1: Leer estructura y diseño (siempre)
1. Lee `content/lab-index.md` para obtener la estructura del Lab $ARGUMENTS (slides, tipos, timing)
2. Lee `skills/design/slidev-futuristic/SKILL.md` para la sintaxis y configuración Slidev
3. Lee `skills/design/color-system/SKILL.md` para los colores exactos
4. Lee `skills/content/slide-content/SKILL.md` para las reglas de formato de bullets y animaciones

### Paso 2: Obtener contenido del lab
**Si existe** `content/lab-$ARGUMENTS/slides-content.md` → usarlo como fuente de bullets
**Si NO existe** → cargar el skill de conocimiento correspondiente y generar el contenido:
  - Lab 01: `skills/ai-knowledge/ai-fundamentals/SKILL.md`
  - Lab 02: `skills/ai-knowledge/context-compaction/SKILL.md`
  - Lab 03: `skills/ai-knowledge/agents-skills-commands/SKILL.md`
  - Lab 04: `skills/ai-knowledge/ai-tools-comparison/SKILL.md`

Usar `content/lab-01/slides-content.md` como referencia de formato (## Slide N [tipo] con bullets y notas).

### Paso 3: Generar slides-content.md (si no existía)
Si en el Paso 2 no existía el archivo, generar `content/lab-$ARGUMENTS/slides-content.md` con los bullets de cada slide siguiendo el formato de referencia del Lab 01. Crear el directorio si no existe.

### Paso 4: Generar presentación Slidev
Genera el archivo `presentations/lab-$ARGUMENTS/slides.md` con:
- Frontmatter Slidev correcto (theme: ../../theme, título del lab, fonts Inter/Fira Code)
- Cada slide con su layout correspondiente (cover, interactive, comparison, analogy, default, section)
- Contenido visual con buen contraste (fondos oscuros + texto blanco en cajas)
- Animaciones v-click en slides de contenido, sin v-click en interactivas
- Notas del presentador en cada slide (timing, guion, transición)

Usar `presentations/lab-01/slides.md` como referencia de estilo visual y estructura HTML.
Crear directorio `presentations/lab-$ARGUMENTS/public/images/` si no existe.

### Paso 5: Verificar
- El número de slides debe coincidir con lab-index.md
- Cada slide debe tener notas del presentador
- Los layouts deben corresponder al tipo indicado en lab-index.md
