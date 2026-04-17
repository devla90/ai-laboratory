# AI Laboratory - Laboratorio de Inteligencia Artificial

## Descripcion
Proyecto de laboratorios de IA para capacitacion del equipo. Incluye 4 sesiones de 1 hora (40 min presentacion + 20 min abiertos) con presentaciones Slidev y material del moderador.

## Stack
- **Presentaciones**: Slidev (markdown-based slides)
- **Tema**: Futurista rojo (#EC0000) con diseno personalizado
- **Agente**: `lab-conductor` para generacion modular de contenido

## Estructura
- `content/` - Guias del moderador y contenido de slides por lab
- `presentations/` - Archivos Slidev finales
- `skills/` - Skills modulares para el agente
- `theme/` - Tema futurista personalizado (CSS, layouts Vue, componentes)
- `assets/` - Imagenes y recursos visuales

## Labs
1. Introduccion a la IA
2. Contexto, Compactacion y el Lenguaje de la IA
3. Agentes, Skills y Comandos
4. Herramientas en Accion: Claude Code, Codex, Copilot

## Comandos
- `/generate-lab {N}` - Genera slides Slidev para el lab N
- `/generate-guide {N}` - Genera guia del moderador para el lab N
- `/preview-slides {N}` - Lanza servidor Slidev para el lab N

## Convenciones
- Contenido en espanol
- Skills < 2K tokens cada uno
- Imagenes sin copyright (SVG propios, Unsplash, Pexels)
- Colores: main=#EC0000, mainStrong=#C00000, light=#F7FAFC, dark=#CC0000, contrastText=#FFFFFF
