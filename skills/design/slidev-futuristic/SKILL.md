---
name: slidev-futuristic
description: >
  Configuración completa del tema futurista Slidev para AI Laboratory.
  Incluye frontmatter, sintaxis de slides, layouts, CSS imports y reglas de diseño.
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
theme: ../../theme
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

## Reglas de Diseño Visual

### Fondo y Espaciado
- Fondo blanco puro (#FFFFFF) en slides de contenido
- Padding global: `2.5em 3.5em` — el CSS base ya lo aplica, NO agregar padding extra inline
- Nunca usar fondos con patrones grid ni líneas

### Títulos (h1)
- Tienen contenedor automático via CSS: borde izquierdo rojo 4px + fondo degradado sutil
- Tamaño: 1.85em (~30px) via CSS base
- NO agregar estilos inline a h1 en slides normales — el CSS se encarga
- Los layouts cover/interactive/section resetean este estilo automáticamente

### Contraste Obligatorio
- Cajas con texto: SIEMPRE fondo oscuro (#1a1a2e, #2D3748, #C00000, #EC0000) + texto blanco
- NUNCA usar fondo claro (rgba rojo <20%) con texto rojo — mal contraste
- Bordes limpios: 1px solid rgba(236, 0, 0, 0.12)
- Si necesitas diferenciar cajas en un pipeline, alternar entre #2D3748 y #C00000

### Animaciones v-click
- Slides de contenido: cada bloque principal con `<v-click>`
- Listas: usar `<v-clicks>` para que cada item aparezca con click
- Slides interactivas: SIN v-click (solo la pregunta visible)
- Slide de cierre/section: cada punto con v-click

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
- `cover` → Portada con fondo oscuro, esquinas decorativas
- `interactive` → Pregunta centrada, borde sutil, hint "Pregunta abierta al equipo"
- `comparison` → Header + body para comparativas
- `analogy` → Split: `::visual::` izquierda + `::default::` derecha
- `section` → Fondo gradient rojo, para cierres/resúmenes
- `default` → Contenido estándar con padding y título contenedor
- `two-cols` → Dos columnas (built-in Slidev)

### Notas del Presentador
```markdown
<!--
Notas para el presentador aquí.
Timing: 2.5 min
Transición: "Ahora veamos..."
-->
```

### Imágenes
```markdown
![alt](/images/nombre.png)
```
Las imágenes van en `presentations/lab-NN/public/images/`

## Ejemplo de Slide con Buen Contraste

```markdown
# De Datos a Respuesta

<div class="flex items-center justify-center mt-6">
<div class="flex items-center gap-3">

<v-click>
<div class="p-4 rounded-lg text-center text-sm" style="background: #1a1a2e; color: white; min-width: 100px">
  📝<br><strong>Tu prompt</strong>
</div>
</v-click>

<v-click>
<div style="color: #EC0000; font-size: 1.5em">→</div>
<div class="p-4 rounded-lg text-center text-sm" style="background: #2D3748; color: white; min-width: 100px">
  ✂️<br><strong>Paso 2</strong>
</div>
</v-click>

<v-click>
<div style="color: #EC0000; font-size: 1.5em">→</div>
<div class="p-4 rounded-lg text-center text-sm" style="background: #EC0000; color: white; min-width: 100px">
  💬<br><strong>Resultado</strong>
</div>
</v-click>

</div>
</div>
```

## Ejemplo de Tokenización ES vs EN

Cuando muestres tokenización, siempre comparar español vs inglés para mostrar diferencia:
- Español: tokens con fondo `rgba(236,0,0,0.4)` y `rgba(236,0,0,0.25)` alternados
- Inglés: tokens con fondo `rgba(100,149,237,0.4)` y `rgba(100,149,237,0.25)` alternados
- Ambos sobre fondo oscuro #1a1a2e con texto blanco
- Mostrar conteo: "→ N tokens · M palabras" con color del idioma
