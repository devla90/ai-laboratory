---
name: context-compaction
description: >
  Conocimiento sobre contexto, ventanas de contexto, compactación y
  markdown para IA. Para el Lab 2 del AI Laboratory.
user-invocable: true
disable-model-invocation: false
---

# Context & Compaction - Conocimiento para Lab 2

## Cuando se Activa
- Generar contenido del Lab 2
- Explicar conceptos de contexto o compactación

## Qué es el Contexto

El contexto es toda la información que la IA tiene disponible en una conversación: tu mensaje, mensajes anteriores, archivos leídos, instrucciones del sistema. Es la "memoria de trabajo" de la IA.

### Analogía: La Pizarra
Imagina que la IA trabaja con una pizarra de tamaño fijo. Todo lo que le dices se escribe en la pizarra. Cuando la pizarra se llena, tiene que borrar las partes más antiguas para seguir escribiendo. Por eso a veces "olvida" lo que le dijiste al inicio de una conversación larga.

### Tokens
- La unidad de medida del contexto son los **tokens**
- 1 token ≈ 0.75 palabras en inglés, ~0.5 palabras en español
- 100K tokens ≈ 75,000 palabras ≈ un libro de 300 páginas

## Ventanas de Contexto por Herramienta

| Herramienta | Contexto | Equivalencia | Notas |
|-------------|----------|-------------|-------|
| Claude Code | ~200K tokens | ~150K palabras | Contexto extendido, ideal para proyectos grandes |
| OpenAI Codex (CLI) | ~128K-200K tokens | Varía por modelo | Depende del modelo base utilizado |
| GitHub Copilot | ~8K-64K tokens | Varía por modo | Chat vs inline vs workspace tienen distintos límites |
| Gemini | ~1M-2M tokens | ~750K-1.5M palabras | Ventana más grande, pero calidad puede degradar |

### Implicaciones Prácticas
- Más contexto = la IA puede "ver" más de tu proyecto
- Pero más contexto NO siempre = mejores respuestas
- La información relevante debe estar cerca del prompt
- Claude Code maneja archivos grandes sin perder el hilo

## Qué es la Compactación

Cuando una conversación se acerca al límite de contexto, la IA puede "compactar" la conversación: resumir los mensajes anteriores para liberar espacio.

### Analogía: Resumir Apuntes
Imagina que tienes un cuaderno de 100 páginas y ya llenaste 90. En vez de empezar un cuaderno nuevo, tomas las primeras 70 páginas y las resumes en 10 páginas. Pierdes algo de detalle, pero mantienes las ideas principales y puedes seguir trabajando.

### Cómo funciona en Claude Code
1. La conversación se acerca al límite de contexto
2. Claude Code automáticamente resume los mensajes más antiguos
3. Mantiene los mensajes recientes intactos
4. El resumen preserva: decisiones tomadas, archivos modificados, contexto del proyecto
5. Se pierde: detalle palabra por palabra de mensajes viejos

### Impacto
- La IA puede "olvidar" instrucciones del inicio
- Solución: repetir instrucciones importantes o usar archivos de configuración (CLAUDE.md)
- Los archivos de proyecto (CLAUDE.md, agents, skills) se cargan FUERA del historial de conversación

## Markdown para la IA

### Qué es
Markdown es un lenguaje de formato ligero que usa símbolos para estructurar texto: `#` para títulos, `-` para listas, `**` para negritas, ``` para código.

### Por qué importa para la IA
- La IA fue entrenada con ENORMES cantidades de markdown (GitHub, documentación, web)
- Reconoce la estructura de markdown como señales de organización
- Un prompt estructurado en markdown es más claro que texto plano
- Headers ayudan a la IA a entender la jerarquía de la información
- Listas ayudan a separar instrucciones discretas

### Ejemplo
**Texto plano**: "Necesito que hagas una función que valide emails y que devuelva true o false y que maneje los casos de arroba faltante y dominios inválidos"

**Markdown estructurado**:
```
## Tarea
Crear función de validación de email

## Requisitos
- Devolver `true` o `false`
- Validar presencia de `@`
- Validar dominio válido
```

La versión markdown produce respuestas más precisas y estructuradas.
