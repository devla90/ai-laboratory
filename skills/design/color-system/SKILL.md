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
| Light | `#FFFFFF` | Fondo de slides de contenido (blanco puro) |
| Dark | `#CC0000` | Textos sobre fondo claro cuando necesitan énfasis |
| Contrast Text | `#FFFFFF` | Texto sobre fondos rojos u oscuros |

## Paleta Extendida

| Nombre | Valor | Uso |
|--------|-------|-----|
| Dark BG | `#1a1a2e` | Fondo de covers, cajas de contenido con texto blanco |
| Dark Surface | `#16213e` | Superficies sobre fondo oscuro |
| Neutral Dark | `#2D3748` | Cajas intermedias en pipelines, texto principal en fondos claros |
| Text Secondary | `#718096` | Texto secundario |
| Border | `rgba(236, 0, 0, 0.12)` | Bordes sutiles y separadores |
| Blue Accent | `#6495ED` | Diferenciador para idioma inglés en comparativas de tokens |

## Reglas de Contraste

### Obligatorio
- Cajas/tarjetas con texto: SIEMPRE fondo oscuro + texto blanco
- Fondos permitidos para cajas: `#1a1a2e`, `#2D3748`, `#C00000`, `#EC0000`
- NUNCA usar fondo claro transparente (rgba rojo <20%) con texto rojo — ilegible
- Bordes decorativos: siempre `1px solid rgba(236, 0, 0, 0.12)`

### Texto
- Texto blanco (#FFF) SOLO sobre fondos oscuros o rojos
- Texto oscuro (#2D3748) sobre fondo blanco
- Rojo (#EC0000) solo para títulos h1 (tienen contenedor CSS automático)
- Bullets: color del texto base (#2D3748)

### Fondos
- Slides de contenido: blanco puro #FFFFFF — sin grids, sin patrones
- Cover: gradient oscuro `#1a1a2e → #16213e`
- Section/cierre: gradient rojo `#EC0000 → #C00000`
- Analogía visual: #FAFAFA con borde sutil

## Gradients
- Header bar: `linear-gradient(90deg, #EC0000, #C00000)`
- Cover BG: `linear-gradient(135deg, #1a1a2e, #16213e)`
- Título h1: `linear-gradient(90deg, rgba(236,0,0,0.04), transparent 60%)` — automático via CSS
