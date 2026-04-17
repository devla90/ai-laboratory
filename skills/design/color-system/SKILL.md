---
name: color-system
description: >
  Sistema de colores del AI Laboratory. Define la paleta completa,
  reglas de uso, contraste y accesibilidad.
user-invocable: true
disable-model-invocation: false
---

# Color System - AI Laboratory

## Cuando se Activa
- Generar CSS o estilos
- Verificar contraste de colores
- Aplicar paleta en slides o componentes

## Paleta Principal

| Nombre | Hex | Uso |
|--------|-----|-----|
| Main | `#EC0000` | Títulos, acentos, bordes activos |
| Main Strong | `#C00000` | Hover, gradients, énfasis fuerte |
| Light | `#F7FAFC` | Fondo de slides de contenido |
| Dark | `#CC0000` | Textos sobre fondo claro cuando necesitan énfasis |
| Contrast Text | `#FFFFFF` | Texto sobre fondos rojos u oscuros |

## Paleta Extendida

| Nombre | Valor | Uso |
|--------|-------|-----|
| Glow | `rgba(236, 0, 0, 0.3)` | Sombras y efectos de brillo |
| Grid | `rgba(236, 0, 0, 0.08)` | Patrón grid de fondo |
| Surface | `rgba(255, 255, 255, 0.95)` | Tarjetas y superficies |
| Dark BG | `#1a1a2e` | Fondo de covers y secciones oscuras |
| Dark Surface | `#16213e` | Superficies sobre fondo oscuro |
| Text Primary | `#2D3748` | Texto principal en fondos claros |
| Text Secondary | `#718096` | Texto secundario |

## Reglas de Contraste
- Texto blanco (#FFF) SOLO sobre fondos rojos o dark-bg
- Texto oscuro (#2D3748) sobre fondos claros (#F7FAFC)
- Nunca usar rojo (#EC0000) como color de texto sobre fondo blanco en cuerpo (solo títulos)
- Los bullets siempre en #2D3748 sobre fondo claro

## Gradients
- Header bar: `linear-gradient(90deg, #EC0000, #C00000)`
- Cover BG: `linear-gradient(135deg, #1a1a2e, #16213e)`
- Glow effect: `radial-gradient(circle, rgba(236,0,0,0.15), transparent)`
