---
name: lab-content-system
description: >
  Sistema de contenido del AI Laboratory. Define la estructura de 4 labs,
  distribución de temas, reglas de timing y formato de archivos.
user-invocable: true
disable-model-invocation: false
---

# Lab Content System

## Cuando se Activa
- Planificar contenido de un lab
- Verificar distribución de temas
- Consultar timing o estructura

## Estructura de Labs

### Reglas de Timing
- Sesión total: 60 min (40 presentación + 20 abiertos)
- Slide de contenido: ~2.5 min
- Slide interactiva: 2-3 min (incluye discusión)
- Cover/cierre: 1-2 min
- Máximo 16-18 slides por lab

### Formato de Archivos
- `content/lab-NN/guide.md` → Guía detallada del moderador
- `content/lab-NN/slides-content.md` → Bullets compactos para slides
- `content/lab-NN/notes.md` → Notas de timing y transiciones
- `presentations/lab-NN/slides.md` → Archivo Slidev final

### Tipos de Slides
| Tipo | Layout | Características |
|------|--------|-----------------|
| cover | cover | Fondo oscuro, título grande, número de lab |
| interactiva | interactive | Pregunta centrada, borde pulsante rojo |
| presentación | default | Título + bullets (máx 5-6) |
| comparativa | comparison | 2-3 columnas con datos |
| analogía | analogy | Split: visual izquierda + texto derecha |
| recap | default | Bullets breves del lab anterior |
| cierre | section | Resumen + preview siguiente lab |
