---
name: slide-content
description: >
  Reglas para escribir contenido compacto de slides del AI Laboratory.
  Define formato de bullets, nivel de detalle, estilo visual y animaciones.
user-invocable: true
disable-model-invocation: false
---

# Slide Content Rules

## Cuando se Activa
- Escribir contenido de bullets para slides
- Revisar si el contenido de una slide es apropiado

## Reglas

### Texto
- Máximo 5-6 bullets por slide
- Cada bullet: 1 línea, máximo 10-12 palabras
- No usar párrafos completos
- Usar verbos de acción al inicio
- Evitar jerga sin contexto visual

### Animaciones (v-click)
- Slides de contenido: cada bloque con `<v-click>` para aparición progresiva
- Listas: usar `<v-clicks>` para que cada item aparezca con click
- Slides interactivas: SIN v-click — solo la pregunta visible
- Pipelines/flujos: cada paso aparece con click secuencial

### Slides Interactivas
- Solo la pregunta, grande y centrada
- Sin bullets adicionales
- Sin animaciones v-click
- El moderador gestiona la discusión verbalmente

### Slides de Comparativa
- Usar tabla o columnas
- Datos concretos (números, versiones)
- Destacar diferencias clave

### Slides de Analogía
- Layout `analogy` con slots `::visual::` y `::default::`
- Lado izquierdo: imagen, emoji grande o diagrama
- Lado derecho: 3-4 bullets con `<v-clicks>` que conecten la analogía

### Contraste Visual
- Cajas informativas: SIEMPRE fondo oscuro + texto blanco
- Fondos permitidos para cajas: #1a1a2e, #2D3748, #C00000, #EC0000
- NUNCA fondo claro con texto rojo en cajas — bajo contraste
- Bordes decorativos: 1px solid rgba(236, 0, 0, 0.12)
- Para diferenciar idiomas en tokenización: rojo para ES, azul para EN

### Notas del Presentador
- Cada slide debe tener notas en bloque de comentarios Slidev `<!-- -->`
- Las notas complementan, no repiten el contenido visible
- Incluir datos extra, contexto, y timing
