---
theme: ../../theme
title: 'AI Laboratory - Lab 01: Introducción a la Inteligencia Artificial'
info: |
  ## AI Laboratory
  Laboratorio de Inteligencia Artificial - Sesión 1 de 4
  
  Introducción a los conceptos fundamentales de la IA
author: AI Laboratory Team
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

## Lab 01: Introducción a la Inteligencia Artificial

<div class="absolute bottom-10 left-1/2 -translate-x-1/2 text-sm opacity-50">
  Serie de 4 laboratorios | Sesión 1
</div>

<!--
Bienvenida al AI Laboratory. Presentarte brevemente.
Explicar que es una serie de 4 sesiones de 1 hora.
Hoy: sentamos las bases de qué es la IA.
Timing: 1 min
-->

---
layout: interactive
---

# ¿Todos conocemos qué es IA?

<!--
Pregunta para romper el hielo y medir el nivel del grupo.
Si nadie responde: "¿Alguien ha hablado con Siri? ¿Ha usado el autocorrect del celular?"
Escuchar activamente. No hay respuestas incorrectas.
Timing: 3 min
-->

---
layout: interactive
---

# ¿Qué IAs conocen?

<!--
Ir anotando mentalmente las que mencionen.
Comunes: ChatGPT, Claude, Gemini, Copilot, Midjourney, DALL-E, Siri, Alexa.
Cierre: "Fíjense cuántas hay. Y todas tienen algo en común: aprenden de datos."
Timing: 3 min
-->

---
layout: interactive
---

# ¿Quiénes han utilizado una IA?

<!--
Que levanten la mano. Preguntar: ¿para qué? ¿les fue bien?
Dejar que 2-3 personas compartan brevemente.
Esto genera conexión con el tema.
Timing: 2 min
-->

---
layout: interactive
---

# ¿Creen que la IA nos reemplazará?

<!--
Pregunta que genera debate. No dar respuesta definitiva.
Frase clave: "La IA no va a reemplazar a los desarrolladores,
pero los desarrolladores que usen IA van a reemplazar a los que no."
Timing: 3 min
-->

---

# ¿Qué es la Inteligencia Artificial?

<div class="grid grid-cols-1 gap-4 mt-8">

<v-click>
<div class="flex items-start gap-3">
  <div class="text-2xl">🧠</div>
  <div><strong>Software que aprende patrones</strong> de datos masivos</div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-3">
  <div class="text-2xl">📊</div>
  <div>No "piensa" como humano — <strong>encuentra correlaciones estadísticas</strong></div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-3">
  <div class="text-2xl">🎯</div>
  <div>La IA de hoy es <strong>"IA Estrecha"</strong> — tareas específicas</div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-3">
  <div class="text-2xl">🚫</div>
  <div>No existe la IA general de las películas <span class="text-sm opacity-60">(todavía)</span></div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-3">
  <div class="text-2xl">💡</div>
  <div>Ejemplos: traducción, reconocimiento de voz, generación de código</div>
</div>
</v-click>

</div>

<!--
La IA es software que aprende patrones de enormes cantidades de datos.
Cuando le preguntas algo, no está "pensando". Está generando la respuesta más probable.
Un punto clave: lo que usamos hoy es IA Estrecha (ANI). Muy buena en UNA cosa.
Timing: 2.5 min
-->

---

# Tipos de IA y Línea de Tiempo

<div class="grid grid-cols-2 gap-8 mt-6">
<div>

### Tipos

<div class="space-y-3 mt-4">
<v-click>
<div class="p-3 rounded-lg border-l-3" style="border-color: #EC0000; background: rgba(236,0,0,0.04)">
  <strong style="color: #EC0000">IA Estrecha (ANI)</strong><br>
  <span class="text-sm">Lo que usamos hoy — muy buena en UNA tarea</span>
</div>
</v-click>
<v-click>
<div class="p-3 rounded-lg border-l-3" style="border-color: #C00000; background: rgba(192,0,0,0.02)">
  <strong style="color: #C00000">IA General (AGI)</strong><br>
  <span class="text-sm">Hipotética — igualaría inteligencia humana</span>
</div>
</v-click>
<v-click>
<div class="p-3 rounded-lg border-l-3" style="border-color: #CC0000; background: rgba(204,0,0,0.02)">
  <strong style="color: #CC0000">Superinteligencia (ASI)</strong><br>
  <span class="text-sm">Concepto teórico — superaría al humano</span>
</div>
</v-click>
</div>

</div>
<div>

### Línea de Tiempo

<div class="mt-4 space-y-3">
<v-click>
<div class="flex gap-3 items-start">
  <span class="font-mono font-bold" style="color: #EC0000">1950</span>
  <span class="text-sm">Turing: "¿Pueden pensar las máquinas?"</span>
</div>
</v-click>
<v-click>
<div class="flex gap-3 items-start">
  <span class="font-mono font-bold" style="color: #EC0000">2012</span>
  <span class="text-sm">Deep learning revoluciona visión artificial</span>
</div>
</v-click>
<v-click>
<div class="flex gap-3 items-start">
  <span class="font-mono font-bold" style="color: #EC0000">2022</span>
  <span class="text-sm">ChatGPT populariza la IA generativa</span>
</div>
</v-click>
<v-click>
<div class="flex gap-3 items-start">
  <span class="font-mono font-bold" style="color: #EC0000">2024</span>
  <span class="text-sm">Agentes de IA y coding assistants</span>
</div>
</v-click>
<v-click>
<div class="flex gap-3 items-start">
  <span class="font-mono font-bold" style="color: #EC0000">2026</span>
  <span class="text-sm">IA integrada en el flujo de trabajo diario</span>
</div>
</v-click>
</div>

</div>
</div>

<!--
Tres tipos de IA: lo que usamos hoy (estrecha), lo hipotético (general), y lo teórico (super).
El timeline muestra que desde Turing (1950) hasta ChatGPT (2022) pasaron 70+ años.
Hoy avanzamos mucho más rápido.
Timing: 2.5 min
-->

---

# Cómo Funciona la IA — Entrenamiento

<div class="mt-6 space-y-4">

<v-click>
<div class="flex items-center gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold" style="background: #EC0000">1</div>
  <div>Se alimenta con <strong>enormes cantidades de texto</strong> (libros, web, código)</div>
</div>
</v-click>

<v-click>
<div class="flex items-center gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold" style="background: #EC0000">2</div>
  <div>Aprende patrones: <strong>"después de X suele venir Y"</strong></div>
</div>
</v-click>

<v-click>
<div class="flex items-center gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold" style="background: #EC0000">3</div>
  <div>Ajusta <strong>miles de millones de parámetros</strong> (pesos)</div>
</div>
</v-click>

<v-click>
<div class="flex items-center gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold" style="background: #EC0000">4</div>
  <div><strong>NO memoriza</strong> texto literal — aprende probabilidades</div>
</div>
</v-click>

</div>

<v-click>
<div class="mt-6 p-4 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  📚 Analogía: Como un niño que lee millones de libros. No memoriza cada frase, pero entiende cómo funciona el lenguaje.
</div>
</v-click>

<!--
Imaginen que le dan a un niño millones de libros para leer. No memoriza cada frase,
pero entiende cómo funciona el lenguaje. La IA hace lo mismo pero a escala masiva.
GPT-4: más de un trillón de parámetros. Cada uno es un "dial" ajustado durante entrenamiento.
Timing: 2.5 min
-->

---

# Cómo Funciona la IA — Inferencia y Tokens

<div class="grid grid-cols-2 gap-6 mt-6">
<div>

### ¿Qué es un Token?

<div class="mt-3 space-y-2">
<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Pedazo de palabra (~0.75 palabras EN)</span>
</div>
</v-click>
<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>En español ~0.5 palabras por token</span>
</div>
</v-click>
<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>La IA genera token por token</span>
</div>
</v-click>
<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Cada token depende de los anteriores</span>
</div>
</v-click>
</div>

</div>
<div>

### Español vs Inglés

<v-click>
<div class="mt-2 p-3 rounded-lg font-mono text-xs" style="background: #1a1a2e; color: #F7FAFC">
  <div class="mb-1 opacity-50 font-sans text-xs">🇪🇸 Español</div>
  <span style="background: rgba(236,0,0,0.4); padding: 2px 5px; border-radius: 3px">Hola</span>
  <span style="background: rgba(236,0,0,0.25); padding: 2px 5px; border-radius: 3px">,</span>
  <span style="background: rgba(236,0,0,0.4); padding: 2px 5px; border-radius: 3px"> ¿</span><span style="background: rgba(236,0,0,0.25); padding: 2px 5px; border-radius: 3px">cómo</span>
  <span style="background: rgba(236,0,0,0.4); padding: 2px 5px; border-radius: 3px"> est</span><span style="background: rgba(236,0,0,0.25); padding: 2px 5px; border-radius: 3px">ás</span>
  <span style="background: rgba(236,0,0,0.4); padding: 2px 5px; border-radius: 3px">?</span>
  <div class="mt-1" style="color: #EC0000; font-weight: bold">→ 7 tokens · 3 palabras</div>
</div>
</v-click>

<v-click>
<div class="mt-2 p-3 rounded-lg font-mono text-xs" style="background: #1a1a2e; color: #F7FAFC">
  <div class="mb-1 opacity-50 font-sans text-xs">🇺🇸 Inglés</div>
  <span style="background: rgba(100,149,237,0.4); padding: 2px 5px; border-radius: 3px">Hello</span>
  <span style="background: rgba(100,149,237,0.25); padding: 2px 5px; border-radius: 3px">,</span>
  <span style="background: rgba(100,149,237,0.4); padding: 2px 5px; border-radius: 3px"> how</span>
  <span style="background: rgba(100,149,237,0.25); padding: 2px 5px; border-radius: 3px"> are</span>
  <span style="background: rgba(100,149,237,0.4); padding: 2px 5px; border-radius: 3px"> you</span>
  <span style="background: rgba(100,149,237,0.25); padding: 2px 5px; border-radius: 3px">?</span>
  <div class="mt-1" style="color: #6495ED; font-weight: bold">→ 6 tokens · 4 palabras</div>
</div>
</v-click>

<v-click>
<div class="mt-2 p-2 rounded text-xs text-center" style="border: 1px solid rgba(236,0,0,0.12)">
  💡 Español usa <strong>más tokens</strong> por palabra
</div>
</v-click>

</div>
</div>

<!--
Cuando le escribes algo, divide tu texto en tokens. Luego genera respuesta un token a la vez.
Es como el autocomplete del celular, pero con comprensión profunda del contexto.
Timing: 2.5 min
-->

---

# De Datos a Respuesta

<div class="flex items-center justify-center mt-6">
<div class="flex items-center gap-3">

<v-click>
<div class="rounded-xl text-center" style="background: #1a1a2e; color: white; width: 140px; height: 90px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">📝</div>
  <div class="text-sm font-bold mt-1">Tu prompt</div>
</div>
</v-click>

<v-click>
<div style="color: #2D3748; font-size: 1.3em">→</div>
<div class="rounded-xl text-center" style="background: #2D3748; color: white; width: 140px; height: 90px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">✂️</div>
  <div class="text-sm font-bold mt-1">Tokenización</div>
</div>
</v-click>

<v-click>
<div style="color: #2D3748; font-size: 1.3em">→</div>
<div class="rounded-xl text-center" style="background: #2D3748; color: white; width: 140px; height: 90px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">🧠</div>
  <div class="text-sm font-bold mt-1">Red neuronal</div>
  <div class="text-xs opacity-75">capas y capas</div>
</div>
</v-click>

<v-click>
<div style="color: #2D3748; font-size: 1.3em">→</div>
<div class="rounded-xl text-center" style="background: #2D3748; color: white; width: 140px; height: 90px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">🎯</div>
  <div class="text-sm font-bold mt-1">Predicción</div>
  <div class="text-xs opacity-75">token a token</div>
</div>
</v-click>

<v-click>
<div style="color: #2D3748; font-size: 1.3em">→</div>
<div class="rounded-xl text-center" style="background: #EC0000; color: white; width: 140px; height: 90px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">💬</div>
  <div class="text-sm font-bold mt-1">Respuesta</div>
</div>
</v-click>

</div>
</div>

<v-click>
<div class="mt-8 text-center">
    <div class="inline-block p-4 rounded-lg" style="background: rgba(236,0,0,0.05); border: 1px solid rgba(236,0,0,0.2)">
    "Una máquina de predecir la siguiente palabra, entrenada con todo internet"
  </div>
</div>
</v-click>

<!--
Flujo completo: tu texto entra, se divide en tokens, pasa por capas de la red neuronal,
y sale una predicción token por token. Cada paso es matemática pura.
Frase clave para que recuerden.
Timing: 2 min
-->

---
layout: interactive
---

# ¿Crees que la IA inventa?

<!--
Breve discusión. Dejar que 2-3 personas opinen.
Luego explicar: "No inventa, recombina. Como un chef que conoce miles de recetas
y puede crear una nueva combinando ingredientes de formas que no ha visto exactamente.
El resultado puede ser sorprendente, pero siempre está basado en lo que ya existía."
Timing: 2 min
-->

---

# Alucinación en la IA

<v-click>
<div class="mt-6 p-5 rounded-xl" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  <div class="text-lg mb-3"><strong style="color: #EC0000">Definición</strong></div>
  <p>Cuando la IA genera información que <strong>suena convincente</strong> pero es <strong>incorrecta o inventada</strong></p>
</div>
</v-click>

<div class="grid grid-cols-2 gap-4 mt-6">

<v-click>
<div class="p-4 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <div class="font-bold mb-2" style="color: #C00000">⚠️ Por qué ocurre</div>
  <ul class="text-sm space-y-1">
    <li>No "sabe" que está equivocada</li>
    <li>No miente — genera lo más probable</li>
    <li>Confianza del modelo ≠ precisión</li>
  </ul>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <div class="font-bold mb-2" style="color: #C00000">🎭 La paradoja</div>
  <p class="text-sm">Cuanto mejor redacta la IA, más difícil es detectar cuando alucina</p>
</div>
</v-click>

</div>

<!--
La alucinación es cuando la IA da una respuesta que suena perfecta, está bien escrita,
tiene la estructura correcta... pero es completamente falsa.
No tiene un mecanismo interno de "esto lo sé" vs "esto me lo invento".
Timing: 2.5 min
-->

---

# Ejemplos de Alucinación

<div class="grid grid-cols-2 gap-4 mt-6">

<v-click>
<div class="p-4 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <div class="text-xl mb-2">📄</div>
  <strong>Papers fantasma</strong>
  <p class="text-sm mt-1 opacity-70">Cita papers con títulos, autores y DOIs que no existen</p>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <div class="text-xl mb-2">💻</div>
  <strong>APIs inventadas</strong>
  <p class="text-sm mt-1 opacity-70">Sugiere funciones con nombre y parámetros correctos... que no existen</p>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <div class="text-xl mb-2">📅</div>
  <strong>Datos falsos</strong>
  <p class="text-sm mt-1 opacity-70">Fechas y estadísticas incorrectas dichas con total confianza</p>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <div class="text-xl mb-2">🔀</div>
  <strong>Mezcla de hechos</strong>
  <p class="text-sm mt-1 opacity-70">Combina datos reales de diferentes temas en una respuesta "nueva"</p>
</div>
</v-click>

</div>

<v-click>
<div class="mt-4 text-center font-semibold" style="color: #EC0000">
  "Suena perfecto, está bien escrito... pero es falso"
</div>
</v-click>

<!--
Ejemplo real: pides papers y la IA inventa títulos, autores y DOIs convincentes.
En programación: sugiere funciones que no existen en esa versión de la librería.
Timing: 2.5 min
-->

---
layout: analogy
---

::visual::

<div class="text-center">
  <div style="font-size: 5em">🎓</div>
  <div class="mt-4 text-lg font-semibold" style="color: #EC0000">El Compañero de Clase</div>
  <div class="text-sm opacity-60 mt-2">Estuvo en TODAS las clases<br>No tomó NI UN apunte</div>
</div>

::default::

## El Compañero que No Tomó Apuntes

<v-clicks>

- Nunca tomó apuntes pero estuvo en **todas** las clases
- Le preguntas antes del examen...
- Recuerda el **tema general** ✅
- Reconstruye la **idea principal** ✅
- Los detalles los **"rellena"** con lo más probable ⚠️

</v-clicks>

<!--
La analogía más poderosa del lab. Tomarla con calma.
"Imaginen un compañero que NUNCA tomó apuntes pero estuvo en TODAS las clases..."
Dar tiempo para que la gente se identifique con la situación.
Timing: 2.5 min
-->

---
layout: analogy
---

::visual::

<div class="text-center">
  <div style="font-size: 5em">😎</div>
  <div class="mt-4 text-lg font-semibold" style="color: #EC0000">...Pero Responde con Total Confianza</div>
  <div class="text-sm opacity-60 mt-2">No dice "creo que..."<br>Dice "fue el 15 de marzo"</div>
</div>

::default::

## ...Pero Responde con Total Confianza

<v-clicks>

- Los detalles específicos son **inventados** ❌
- No dice "creo que..." — dice con **seguridad** ❌
- Mezcla información de **diferentes clases** ❌

</v-clicks>

<v-click>
<div class="mt-4 p-4 rounded-lg" style="background: rgba(236,0,0,0.03); border-left: 3px solid #EC0000">
  <strong>La lección:</strong> Siempre verifica los datos específicos que te da la IA — especialmente números, fechas, citas y referencias técnicas.
</div>
</v-click>

<!--
El remate de la analogía. Enfatizar: "Y lo peor: responde con TOTAL confianza."
La IA hace exactamente lo mismo: absorbe información, entiende patrones,
pero rellena los detalles con lo más probable.
Timing: 2.5 min
-->

---
layout: section
---

# Resumen Lab 01

<div class="mt-6 text-left max-w-xl mx-auto space-y-3">
<v-clicks>
  <div class="flex items-center gap-3"><span class="text-2xl">🧠</span> La IA no piensa → <strong>predice</strong></div>
  <div class="flex items-center gap-3"><span class="text-2xl">🔄</span> No inventa → <strong>recombina patrones</strong></div>
  <div class="flex items-center gap-3"><span class="text-2xl">⚠️</span> Cuando no sabe → <strong>genera con confianza</strong></div>
  <div class="flex items-center gap-3"><span class="text-2xl">🎓</span> Como el compañero sin apuntes</div>
</v-clicks>
</div>

<v-click>
<div class="mt-8 text-sm opacity-70">
  <strong>Próximo Lab:</strong> Contexto, Compactación y el Lenguaje de la IA
</div>
</v-click>

<!--
Resumen rápido de los 4 puntos clave.
Preview del siguiente lab: "¿Cómo hace la IA para 'recordar' lo que le dijiste?
¿Cuánta información puede manejar? ¿Qué pasa cuando llega al límite?"
Preguntar si hay dudas antes de pasar a la parte abierta.
Timing: 2 min
-->

---
layout: cover
---

# ¡Muchas Gracias!

## Nos vemos en el Lab 02

<!--
Agradecer al equipo. Recordar que el Lab 02 será sobre Contexto y Compactación.
Abrir espacio para preguntas finales.
-->
