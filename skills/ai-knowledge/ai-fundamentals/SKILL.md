---
name: ai-fundamentals
description: >
  Conocimiento profundo sobre fundamentos de IA para el Lab 1.
  Cubre: qué es IA, cómo funciona, alucinación, y analogías.
user-invocable: true
disable-model-invocation: false
---

# AI Fundamentals - Conocimiento para Lab 1

## Cuando se Activa
- Generar contenido del Lab 1
- Responder preguntas sobre fundamentos de IA
- Profundizar en conceptos de alucinación

## Qué es la Inteligencia Artificial

La IA es software que aprende patrones de datos masivos para realizar tareas que normalmente requieren inteligencia humana. No "piensa" - encuentra correlaciones estadísticas.

### Tipos de IA
- **IA Estrecha (ANI)**: Especializada en una tarea. Es lo que usamos hoy (ChatGPT, Copilot, traducción automática)
- **IA General (AGI)**: Hipotética IA que igualaría la inteligencia humana en cualquier tarea. No existe aún.
- **Superinteligencia (ASI)**: IA que superaría la inteligencia humana. Concepto teórico.

### Historia Breve
- 1950: Alan Turing propone "¿Pueden pensar las máquinas?"
- 1956: Se acuña el término "Inteligencia Artificial"
- 2012: Deep learning revoluciona reconocimiento de imágenes
- 2022-2023: ChatGPT, Claude, Gemini popularizan la IA generativa
- 2024-2026: Agentes de IA, coding assistants, IA en el flujo de trabajo diario

## Cómo Funciona la IA

### Entrenamiento
1. Se alimenta con enormes cantidades de texto (libros, web, código)
2. El modelo aprende patrones estadísticos: "después de X, suele venir Y"
3. Ajusta millones/billones de parámetros (pesos) para predecir la siguiente palabra
4. NO memoriza texto literal - aprende distribuciones de probabilidad

### Inferencia (Cuando la Usas)
1. Recibes tu prompt (entrada)
2. Tokeniza: divide el texto en tokens (~0.75 palabras por token)
3. Procesa tokens a través de capas de la red neuronal
4. Genera respuesta token por token, eligiendo el más probable
5. Cada token generado se añade al contexto para el siguiente

### Analogía del Autocomplete
La IA es como el autocomplete del celular, pero enormemente más sofisticado. Tu celular predice la siguiente palabra basándose en patrones simples. La IA hace lo mismo pero con una comprensión profunda del contexto, la gramática, y el conocimiento del mundo.

## ¿La IA Inventa?

La IA no "inventa" en el sentido creativo humano. Recombina patrones aprendidos de formas nuevas. Es como un chef que conoce miles de recetas y puede crear una nueva combinando ingredientes de formas que no ha visto exactamente, pero basándose en principios que aprendió.

## Alucinación en la IA

### Qué es
Cuando la IA genera información que suena convincente pero es incorrecta o inventada. La IA no "sabe" que está equivocada - simplemente genera la secuencia de tokens más probable.

### Por qué ocurre
- El modelo aprendió patrones, no hechos verificados
- Si no tiene información suficiente, "llena los huecos" con lo más probable
- La confianza del modelo no correlaciona con la precisión
- Es como un estudiante que responde con seguridad aunque no sepa la respuesta

### Ejemplos comunes
- Citar papers académicos que no existen
- Inventar funciones de una API
- Dar fechas o estadísticas incorrectas con total confianza
- Mezclar hechos de diferentes temas

## Analogía: El Compañero que No Tomó Apuntes

Imagina un compañero de clase que nunca tomó apuntes pero escuchó TODAS las clases. Cuando le preguntas algo:
- Recuerda el tema general ✓
- Puede reconstruir la idea principal ✓
- Pero los detalles específicos los "rellena" con lo que le parece más probable ✗
- Si le preguntas con seguridad, responde con seguridad aunque no esté seguro ✗
- A veces mezcla información de diferentes clases ✗

Así funciona la IA: absorbe enormes cantidades de información, entiende patrones y estructura, pero cuando necesita un dato específico que no "recuerda" bien, genera lo que estadísticamente encaja mejor.

**La lección**: Siempre verifica los datos específicos que te da la IA, especialmente números, fechas, citas y referencias técnicas.
