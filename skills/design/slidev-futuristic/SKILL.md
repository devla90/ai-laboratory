---
name: slidev-futuristic
description: >
  Configuración completa del tema futurista Slidev para AI Laboratory.
  Incluye frontmatter, sintaxis de slides, layouts y CSS imports.
user-invocable: true
disable-model-invocation: false
---

# Slidev Futuristic Theme

## Cuando se Activa
- Generar archivos slides.md para Slidev
- Configurar o modificar el tema visual
- Crear nuevos layouts o componentes

## Frontmatter Base

```yaml
---
theme: ./theme
title: 'AI Laboratory - Lab NN: Título'
info: 'Laboratorio de Inteligencia Artificial'
author: 'AI Laboratory Team'
transition: slide-left
mdc: true
fonts:
  sans: Inter
  mono: Fira Code
---
```

## Sintaxis de Slides

### Separador
Cada slide se separa con `---`

### Asignar Layout
```markdown
---
layout: cover
---
# Título
```

### Layouts Disponibles
- `cover` → Portada con fondo oscuro
- `interactive` → Pregunta centrada con borde glow
- `comparison` → Columnas para comparar
- `analogy` → Split visual/texto
- `section` → Divisor de sección
- `default` → Contenido estándar
- `two-cols` → Dos columnas (built-in Slidev)
- `image-right` → Imagen a la derecha (built-in Slidev)

### Notas del Presentador
```markdown
<!--
Notas para el presentador aquí.
Timing: 2.5 min
Transición: "Ahora veamos..."
-->
```

### Estilos Inline
```markdown
<style>
h1 { color: #EC0000; }
</style>
```

### Imágenes
```markdown
![alt](/images/nombre.png)
```
Las imágenes van en `presentations/lab-NN/public/images/`

## Estructura de un Slide File Completo

```markdown
---
theme: ./theme
title: 'AI Laboratory - Lab 01'
transition: slide-left
mdc: true
fonts:
  sans: Inter
  mono: Fira Code
---

---
layout: cover
---

# AI Laboratory
## Lab 01: Introducción a la IA

<!--
Bienvenida. Presentarte. Explicar dinámica del lab.
Timing: 1 min
-->

---
layout: interactive
---

# ¿Todos conocemos qué es IA?

<!--
Pregunta abierta. Dar 30 segundos para que piensen.
Si nadie responde: "¿Alguien ha usado Siri o Alexa?"
Timing: 3 min
-->

---

# Introducción a la IA

- La IA es software que aprende patrones de datos
- No "piensa" como un humano
- Tipos: IA estrecha, IA general, superinteligencia
- Hoy usamos IA estrecha (tareas específicas)
- Ejemplos: traducción, reconocimiento de voz, código

<!--
Enfatizar que la IA actual es "estrecha" - muy buena en tareas específicas.
Timing: 2.5 min
-->
```
