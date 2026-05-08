---
theme: ../../theme
title: 'AI Laboratory - Lab 02: Contexto, Compactación y el Lenguaje de la IA'
info: |
  ## AI Laboratory
  Laboratorio de Inteligencia Artificial - Sesión 2 de 4

  Contexto, ventanas de contexto, compactación y markdown para IA
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

## Lab 02: Contexto, Compactación y el Lenguaje de la IA

<div class="mt-8 text-sm opacity-80">Luis Rosales</div>
<div class="text-xs opacity-50">Software Engineer AI</div>
<div class="mt-4 text-xs opacity-40">Serie de 4 laboratorios | Sesión 2</div>

<!--
Bienvenida a la segunda sesión del AI Laboratory.
Hoy vamos a entender cómo la IA "recuerda" lo que le decimos, qué pasa cuando se le acaba la memoria, y cómo podemos hablarle de forma más efectiva.
Timing: 1 min
-->

---

# Recap: Lab 01

<div class="grid grid-cols-2 gap-6 mt-6">

<v-click>
<div class="p-4 rounded-lg" style="background: #1a1a2e; color: white">
  <div class="text-lg mb-2">🧠 La IA no piensa</div>
  <p class="text-sm opacity-80">Predice la siguiente palabra más probable basándose en patrones aprendidos</p>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg" style="background: #2D3748; color: white">
  <div class="text-lg mb-2">🔄 No inventa, recombina</div>
  <p class="text-sm opacity-80">Combina patrones de sus datos de entrenamiento para generar respuestas</p>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg" style="background: #C00000; color: white">
  <div class="text-lg mb-2">⚠️ Alucinación</div>
  <p class="text-sm opacity-80">Cuando no sabe algo, genera con total confianza — como el compañero sin apuntes</p>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg" style="background: #EC0000; color: white">
  <div class="text-lg mb-2">💡 Hoy vamos a ver...</div>
  <p class="text-sm opacity-80">¿Cómo "recuerda" la IA lo que le dijiste? ¿Qué pasa cuando se le acaba la memoria?</p>
</div>
</v-click>

</div>

<!--
Recap rápido del Lab 1: la IA predice, no piensa. Recombina patrones, no inventa.
Y cuando no sabe, genera con confianza (alucinación).
Hoy vamos más profundo: ¿cómo hace la IA para recordar lo que le estás diciendo?
Timing: 2 min
Transición: "Empecemos con una pregunta: cuando hablas con una IA, ¿cómo sabe de qué estás hablando?"
-->

---

# ¿Qué es el Contexto?

<div class="mt-6 space-y-4">

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">📋</div>
  <div>
    <strong>Toda la información disponible</strong> en una conversación
    <p class="text-sm opacity-70 mt-1">Tu mensaje, mensajes anteriores, archivos leídos, instrucciones del sistema</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🧠</div>
  <div>
    <strong>La "memoria de trabajo"</strong> de la IA
    <p class="text-sm opacity-70 mt-1">Como la RAM de una computadora — temporal y con límite</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">📏</div>
  <div>
    <strong>Se mide en tokens</strong>
    <p class="text-sm opacity-70 mt-1">1 token ≈ 0.75 palabras en inglés, ~0.5 palabras en español</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">⚡</div>
  <div>
    <strong>Tiene un límite fijo</strong> — la "ventana de contexto"
    <p class="text-sm opacity-70 mt-1">Cuando se llena, la IA empieza a "olvidar" lo más antiguo</p>
  </div>
</div>
</v-click>

</div>

<!--
El contexto es TODO lo que la IA puede "ver" en este momento. Tu mensaje actual, los mensajes anteriores, archivos que le compartiste, instrucciones del sistema.
Es como la memoria de trabajo: temporal y con un límite claro.
¿Y cómo se mide ese límite? En tokens — esas unidades que vimos en el Lab 1.
Timing: 2.5 min
Transición: "Para entender mejor este concepto, pensemos en una analogía..."
-->

---

# Analogía: La Pizarra de la IA

<div class="grid grid-cols-2 gap-6 mt-6">

<v-click>
<div class="flex flex-col items-center justify-center p-6 rounded-xl" style="background: #FAFAFA; border: 1px solid rgba(236,0,0,0.12); min-height: 220px">
  <div style="font-size: 4em">📝</div>
  <div class="mt-3 text-lg font-semibold" style="color: #EC0000">La Pizarra</div>
  <div class="text-sm opacity-60 mt-1">Tamaño fijo · Se llena y hay que borrar</div>
</div>
</v-click>

<div class="space-y-3 flex flex-col justify-center">

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>La IA trabaja con una <strong>pizarra de tamaño fijo</strong></span>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Todo lo que le dices se <strong>escribe</strong> en la pizarra</span>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Cuando se llena, <strong>borra lo más antiguo</strong> para seguir</span>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Por eso "olvida" el <strong>inicio</strong> de conversaciones largas</span>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Lo más <strong>reciente</strong> siempre está visible</span>
</div>
</v-click>

</div>
</div>

<!--
Imaginen que la IA tiene una pizarra frente a ella. Cada vez que le dices algo, lo escribe. Cada vez que responde, también lo escribe.
Pero la pizarra tiene un tamaño fijo. Cuando se llena, tiene que borrar las partes más viejas para seguir escribiendo.
Por eso, en conversaciones largas, la IA puede "olvidar" lo que le dijiste al inicio.
Timing: 2.5 min
Transición: "Entonces, ¿qué tan grande es esta pizarra? Veamos los componentes..."
-->

---

# Contexto como Memoria de Trabajo

<div class="flex items-center justify-center mt-6">
<div class="flex items-center gap-3">

<v-click>
<div class="rounded-xl text-center" style="background: #1a1a2e; color: white; width: 130px; height: 90px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">💬</div>
  <div class="text-xs font-bold mt-1">Tu mensaje</div>
</div>
</v-click>

<v-click>
<div style="color: #2D3748; font-size: 1.3em">+</div>
<div class="rounded-xl text-center" style="background: #2D3748; color: white; width: 130px; height: 90px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">🔄</div>
  <div class="text-xs font-bold mt-1">Historial</div>
  <div class="text-xs opacity-75">mensajes previos</div>
</div>
</v-click>

<v-click>
<div style="color: #2D3748; font-size: 1.3em">+</div>
<div class="rounded-xl text-center" style="background: #2D3748; color: white; width: 130px; height: 90px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">📄</div>
  <div class="text-xs font-bold mt-1">Archivos</div>
  <div class="text-xs opacity-75">código, docs</div>
</div>
</v-click>

<v-click>
<div style="color: #2D3748; font-size: 1.3em">+</div>
<div class="rounded-xl text-center" style="background: #2D3748; color: white; width: 130px; height: 90px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">⚙️</div>
  <div class="text-xs font-bold mt-1">Sistema</div>
  <div class="text-xs opacity-75">instrucciones</div>
</div>
</v-click>

<v-click>
<div style="color: #EC0000; font-size: 1.3em">=</div>
<div class="rounded-xl text-center" style="background: #EC0000; color: white; width: 130px; height: 90px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">🧠</div>
  <div class="text-xs font-bold mt-1">Contexto</div>
  <div class="text-xs opacity-75">total</div>
</div>
</v-click>

</div>
</div>

<v-click>
<div class="mt-8 grid grid-cols-2 gap-4">
  <div class="p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
    📚 100K tokens ≈ <strong>75,000 palabras</strong> ≈ un libro de 300 páginas
  </div>
  <div class="p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
    💡 Más contexto = la IA "ve" más, pero <strong>no siempre = mejor</strong>
  </div>
</div>
</v-click>

<!--
El contexto es la suma de todo: tu mensaje, el historial, archivos cargados e instrucciones del sistema.
Todo esto junto se mide en tokens. 100K tokens es como un libro de 300 páginas.
Un dato importante: más contexto no siempre significa mejores respuestas. Lo relevante debe estar cerca del prompt.
Timing: 2 min
Transición: "Ahora veamos cuánto contexto tienen las herramientas que usamos..."
-->

---
layout: comparison
---

::header::

# Ventana de Contexto: Claude Code

::default::

<div class="grid grid-cols-2 gap-6">
<div>

<v-click>
<div class="p-5 rounded-xl" style="background: #1a1a2e; color: white">
  <div class="text-3xl mb-2">Hasta ~1M</div>
  <div class="text-sm opacity-80">tokens de contexto</div>
  <div class="mt-3 text-xs opacity-60">≈ 750,000 palabras (5x más que antes)</div>
  <div class="text-xs opacity-60">Con Opus 4.6/4.7 · Compactación en 5 niveles</div>
</div>
</v-click>

</div>
<div>

<v-click>
<div class="space-y-3">
  <div class="flex items-start gap-2">
    <span style="color: #EC0000">✓</span>
    <span class="text-sm">Ideal para <strong>proyectos grandes</strong></span>
  </div>
  <div class="flex items-start gap-2">
    <span style="color: #EC0000">✓</span>
    <span class="text-sm">Lee múltiples archivos <strong>sin perder el hilo</strong></span>
  </div>
  <div class="flex items-start gap-2">
    <span style="color: #EC0000">✓</span>
    <span class="text-sm">Mantiene <strong>decisiones y contexto</strong> del proyecto</span>
  </div>
  <div class="flex items-start gap-2">
    <span style="color: #EC0000">✓</span>
    <span class="text-sm">Compactación automática en <strong>cascada de 5 niveles</strong></span>
  </div>
</div>
</v-click>

<v-click>
<div class="mt-4 p-3 rounded-lg text-sm" style="background: rgba(236,0,0,0.05); border: 1px solid rgba(236,0,0,0.12)">
  💡 Puede "ver" todo un módulo completo de código a la vez
</div>
</v-click>

</div>
</div>

<!--
Claude Code ahora soporta hasta ~1 millón de tokens con Opus 4.6/4.7, 5 veces más que antes.
Eso son unas 750 mil palabras. Puede leer múltiples archivos de tu proyecto y mantener el contexto entre ellos.
Además, tiene compactación automática en cascada de 5 niveles — ya veremos qué significa eso.
Timing: 2.5 min
Transición: "¿Y las otras herramientas?"
-->

---
layout: comparison
---

::header::

# Ventana de Contexto: Codex

::default::

<div class="grid grid-cols-2 gap-6">
<div>

<v-click>
<div class="p-5 rounded-xl" style="background: #1a1a2e; color: white">
  <div class="text-3xl mb-2">~200-400K</div>
  <div class="text-sm opacity-80">tokens de contexto</div>
  <div class="mt-3 text-xs opacity-60">GPT-5.3 Codex ~200K · GPT-5.5 ~400K</div>
  <div class="text-xs opacity-60">Ahora con compactación server-side</div>
</div>
</v-click>

</div>
<div>

<v-click>
<div class="space-y-3">
  <div class="flex items-start gap-2">
    <span style="color: #EC0000">✓</span>
    <span class="text-sm"><strong>CLI local</strong> (terminal) + <strong>Cloud</strong> remoto (contenedores)</span>
  </div>
  <div class="flex items-start gap-2">
    <span style="color: #EC0000">✓</span>
    <span class="text-sm">CLI: interactivo, edita archivos con <strong>sandbox de OS</strong></span>
  </div>
  <div class="flex items-start gap-2">
    <span style="color: #EC0000">✓</span>
    <span class="text-sm">Cloud: envía tarea, clona repo, <strong>entrega diff o PR</strong></span>
  </div>
  <div class="flex items-start gap-2">
    <span style="color: #EC0000">▸</span>
    <span class="text-sm">Config: <strong>AGENTS.md</strong> (similar a CLAUDE.md)</span>
  </div>
</div>
</v-click>

<v-click>
<div class="mt-4 p-3 rounded-lg text-sm" style="background: rgba(236,0,0,0.05); border: 1px solid rgba(236,0,0,0.12)">
  💡 Dos modos: interactivo en tu terminal o tareas autónomas en la nube
</div>
</v-click>

</div>
</div>

<!--
Codex de OpenAI tiene dos modos: CLI local y Cloud remoto.
El CLI corre en tu terminal, es interactivo como un chat, y edita archivos directamente en tu máquina con sandbox a nivel de OS.
El Cloud clona tu repo en un contenedor, ejecuta la tarea en background, y te entrega un diff o PR.
Timing: 2.5 min
Transición: "Y Copilot tiene un enfoque completamente diferente..."
-->

---
layout: comparison
---

::header::

# Ventana de Contexto: Copilot

::default::

<div class="grid grid-cols-2 gap-6">
<div>

<v-click>
<div class="p-5 rounded-xl" style="background: #1a1a2e; color: white">
  <div class="text-3xl mb-2">~8-192K</div>
  <div class="text-sm opacity-80">tokens de contexto</div>
  <div class="mt-3 text-xs opacity-60">Varía por modo:</div>
  <div class="text-xs opacity-60">inline · chat · agent</div>
</div>
</v-click>

</div>
<div>

<v-click>
<div class="space-y-3">
  <div class="flex items-start gap-2">
    <span style="color: #EC0000">▸</span>
    <span class="text-sm"><strong>Inline:</strong> autocompletado en archivo actual (~8K)</span>
  </div>
  <div class="flex items-start gap-2">
    <span style="color: #EC0000">▸</span>
    <span class="text-sm"><strong>Chat:</strong> archivos abiertos + historial (~64-128K)</span>
  </div>
  <div class="flex items-start gap-2">
    <span style="color: #EC0000">▸</span>
    <span class="text-sm"><strong>Agent:</strong> edita archivos y ejecuta comandos (~192K)</span>
  </div>
  <div class="flex items-start gap-2">
    <span style="color: #EC0000">▸</span>
    <span class="text-sm"><strong>Cloud:</strong> crea PRs desde issues via GitHub Actions</span>
  </div>
</div>
</v-click>

<v-click>
<div class="mt-4 p-3 rounded-lg text-sm" style="background: rgba(236,0,0,0.05); border: 1px solid rgba(236,0,0,0.12)">
  ⚠️ Contexto más limitado = respuestas más "locales"
</div>
</v-click>

<v-click>
<div class="mt-2 p-3 rounded-lg text-sm" style="background: rgba(236,0,0,0.05); border: 1px solid rgba(236,0,0,0.12)">
  💡 Multi-modelo: elige entre Claude, GPT, Gemini. GitHub limita el contexto nativo
</div>
</v-click>

</div>
</div>

<!--
Copilot ahora tiene 4 modos: inline (~8K), chat (~64-128K), agent (~192K) y cloud agent (GitHub Actions).
El agent mode edita archivos y ejecuta comandos autónomamente. El cloud agent crea PRs desde issues.
Es multi-modelo: puedes elegir entre Claude, GPT, Gemini o Grok. GitHub limita el contexto nativo de cada modelo.
Timing: 2 min
Transición: "Ahora que sabemos que el contexto tiene un límite... ¿qué pasa cuando se llena?"
-->

---

# ¿Qué es la Compactación?

<div class="mt-6 space-y-4">

<v-click>
<div class="p-5 rounded-xl" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  <div class="text-lg mb-2"><strong style="color: #EC0000">Definición</strong></div>
  <p>Cuando la conversación se acerca al límite, la IA <strong>resume los mensajes antiguos</strong> para liberar espacio y seguir trabajando</p>
</div>
</v-click>

<div class="grid grid-cols-3 gap-4 mt-4">

<v-click>
<div class="p-4 rounded-lg text-center" style="background: #1a1a2e; color: white">
  <div class="text-2xl mb-2">📝</div>
  <strong class="text-sm">Conversación larga</strong>
  <p class="text-xs mt-1 opacity-70">Se acerca al límite de tokens</p>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg text-center" style="background: #2D3748; color: white">
  <div class="text-2xl mb-2">✂️</div>
  <strong class="text-sm">Compactación</strong>
  <p class="text-xs mt-1 opacity-70">Resume lo antiguo, mantiene lo reciente</p>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg text-center" style="background: #EC0000; color: white">
  <div class="text-2xl mb-2">✅</div>
  <strong class="text-sm">Sigue trabajando</strong>
  <p class="text-xs mt-1 opacity-70">Con el resumen + mensajes nuevos</p>
</div>
</v-click>

</div>

</div>

<v-click>
<div class="mt-4 text-center text-sm" style="color: #C00000">
  <strong>Preserva:</strong> decisiones, archivos modificados, contexto del proyecto<br>
  <strong>Pierde:</strong> detalle palabra por palabra de mensajes viejos
</div>
</v-click>

<!--
La compactación es el mecanismo que usa la IA para no quedarse sin espacio.
Cuando la conversación se acerca al límite, automáticamente resume los mensajes más antiguos.
Mantiene lo importante: qué decidimos, qué archivos tocamos, el contexto del proyecto.
Pierde el detalle exacto de lo que se dijo al inicio.
Timing: 2.5 min
Transición: "Pensemos en una analogía para entenderlo mejor..."
-->

---

# Analogía: Resumir Apuntes

<div class="grid grid-cols-2 gap-6 mt-6">

<v-click>
<div class="flex flex-col items-center justify-center p-6 rounded-xl" style="background: #FAFAFA; border: 1px solid rgba(236,0,0,0.12); min-height: 220px">
  <div style="font-size: 4em">📓</div>
  <div class="mt-3 text-lg font-semibold" style="color: #EC0000">El Cuaderno de Apuntes</div>
  <div class="text-sm opacity-60 mt-1">100 páginas · Ya llenaste 90</div>
</div>
</v-click>

<div class="space-y-3 flex flex-col justify-center">

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Tienes un cuaderno de <strong>100 páginas</strong></span>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Ya llenaste <strong>90 páginas</strong> con apuntes</span>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Resumes las primeras 70 páginas <strong>en solo 10</strong></span>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Pierdes <strong>detalle</strong>, pero mantienes las <strong>ideas clave</strong></span>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Ahora tienes <strong>70 páginas libres</strong> para seguir</span>
</div>
</v-click>

</div>
</div>

<v-click>
<div class="mt-4 p-3 rounded-lg text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  💡 <strong>Tip:</strong> La IA puede "olvidar" instrucciones del inicio → repite lo importante o usa archivos de configuración (CLAUDE.md)
</div>
</v-click>

<!--
Imaginen que tienen un cuaderno de 100 páginas y ya llenaron 90.
En vez de empezar uno nuevo (perder todo), toman las primeras 70 páginas y las resumen en 10.
Pierden algo de detalle, pero mantienen las ideas principales.
Ahora solo usan 30 páginas (10 de resumen + 20 recientes) y tienen 70 páginas libres. La IA hace exactamente eso.
Timing: 2.5 min
Transición: "Hay algo que podemos hacer para ayudar a la IA: hablarle en su idioma..."
-->

---

# Markdown: El Lenguaje de la IA

<div class="mt-6 space-y-4">

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">#</div>
  <div>
    <strong>Lenguaje de formato ligero</strong>
    <p class="text-sm opacity-70 mt-1">Usa símbolos simples para estructurar texto: <code>#</code> títulos, <code>-</code> listas, <code>**</code> negritas</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🎓</div>
  <div>
    <strong>La IA fue entrenada con MUCHO markdown</strong>
    <p class="text-sm opacity-70 mt-1">GitHub, documentación técnica, foros — todo usa markdown</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🧠</div>
  <div>
    <strong>Reconoce la estructura como señales</strong>
    <p class="text-sm opacity-70 mt-1">Headers = jerarquía, listas = instrucciones discretas, código = bloques técnicos</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🎯</div>
  <div>
    <strong>Prompt estructurado = respuestas más precisas</strong>
    <p class="text-sm opacity-70 mt-1">La IA entiende mejor qué quieres y cómo organizarlo</p>
  </div>
</div>
</v-click>

</div>

<!--
Markdown es un lenguaje de formato muy simple que usa símbolos para estructurar texto.
¿Por qué nos importa? Porque la IA fue entrenada con enormes cantidades de markdown.
Reconoce headers como jerarquía, listas como instrucciones separadas, código como bloques técnicos.
Cuando le escribes en markdown, entiende mucho mejor la estructura de tu solicitud.
Timing: 2.5 min
Transición: "Veamos un ejemplo concreto de la diferencia..."
-->

---

# Estructura vs Texto Plano

<div class="grid grid-cols-2 gap-5 mt-6">

<v-click>
<div>
<div class="text-sm font-bold mb-2" style="color: #C00000">❌ Texto plano</div>
<div class="p-4 rounded-lg font-mono text-xs leading-relaxed" style="background: #1a1a2e; color: #F7FAFC">
Necesito que hagas una función que valide emails y que devuelva true o false y que maneje los casos de arroba faltante y dominios inválidos y también que sea case insensitive
</div>
<div class="mt-2 p-2 rounded text-xs text-center" style="border: 1px solid rgba(236,0,0,0.12)">
  Un bloque de texto sin estructura clara
</div>
</div>
</v-click>

<v-click>
<div>
<div class="text-sm font-bold mb-2" style="color: #EC0000">✅ Markdown estructurado</div>
<div class="p-4 rounded-lg font-mono text-xs leading-relaxed" style="background: #1a1a2e; color: #F7FAFC">
<span style="color: #EC0000">## Tarea</span><br>
Crear función de validación de email<br><br>
<span style="color: #EC0000">## Requisitos</span><br>
<span style="opacity: 0.6">-</span> Devolver `true` o `false`<br>
<span style="opacity: 0.6">-</span> Validar presencia de `@`<br>
<span style="opacity: 0.6">-</span> Validar dominio válido<br>
<span style="opacity: 0.6">-</span> Case insensitive
</div>
<div class="mt-2 p-2 rounded text-xs text-center" style="border: 1px solid rgba(236,0,0,0.12)">
  Estructura clara → respuesta más precisa
</div>
</div>
</v-click>

</div>

<v-click>
<div class="mt-4 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  💡 La misma información, pero la IA <strong>procesa mejor</strong> la versión estructurada
</div>
</v-click>

<!--
A la izquierda: un párrafo largo con todo mezclado. La IA tiene que "desenredar" qué es qué.
A la derecha: la misma información con headers y listas. La IA sabe exactamente: tarea = validar email, requisitos = estos 4 puntos.
La versión markdown produce respuestas más organizadas y completas.
Timing: 2.5 min
Transición: "¿Quieren verlo en acción?"
-->

---
layout: interactive
---

# Demo: Markdown vs Texto Plano

<v-click>
<div class="mt-6 p-4 rounded-lg text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  <strong style="color: #EC0000">Ejercicio en vivo:</strong> Vamos a enviar el MISMO pedido a una IA en dos formatos diferentes y comparar las respuestas
</div>
</v-click>

<!--
Ejercicio en vivo. Abrir la herramienta de IA disponible.
Enviar la misma solicitud en dos formatos: texto plano y markdown.
Ejemplo: pedir que cree una función de validación o que explique un concepto.
Comparar las respuestas lado a lado: ¿cuál es más completa? ¿más organizada?
Timing: 3 min
Transición: "Veamos qué diferencias encontramos..."
-->

---
layout: interactive
---

# ¿Qué diferencias notaron?

<v-click>
<div class="mt-6 p-4 rounded-lg text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  <strong style="color: #EC0000">Para reflexionar:</strong> ¿La respuesta con markdown fue más completa? ¿Más organizada? ¿Cubrió todos los requisitos?
</div>
</v-click>

<!--
Discusión grupal sobre los resultados del demo.
Preguntas guía: ¿La respuesta del prompt con markdown cubrió todos los puntos?
¿La del texto plano se saltó algo? ¿Cuál fue más fácil de leer?
Conclusión: estructurar nuestros prompts ayuda a la IA a darnos mejores respuestas.
No necesitan ser expertos en markdown — con headers y listas ya marcan la diferencia.
Timing: 2 min
Transición: "Recapitulemos lo que aprendimos hoy..."
-->

---
layout: section
---

# Resumen Lab 02

<div class="mt-6 text-left max-w-xl mx-auto space-y-3">
<v-clicks>
  <div class="flex items-center gap-3"><span class="text-2xl">📝</span> El contexto es la <strong>"pizarra"</strong> de la IA — tiene un límite</div>
  <div class="flex items-center gap-3"><span class="text-2xl">📏</span> Cada herramienta tiene una <strong>ventana de contexto</strong> diferente</div>
  <div class="flex items-center gap-3"><span class="text-2xl">✂️</span> La compactación <strong>resume lo viejo</strong> para seguir trabajando</div>
  <div class="flex items-center gap-3"><span class="text-2xl">#️⃣</span> Markdown ayuda a la IA a <strong>entender mejor</strong> tu solicitud</div>
</v-clicks>
</div>

<v-click>
<div class="mt-6 text-sm opacity-70">
  <strong>Próximo Lab:</strong> Agentes, Skills y Comandos — cómo la IA trabaja con "empleados especializados"
</div>
</v-click>

<!--
Cuatro puntos clave para recordar del Lab 2.
El contexto tiene límites, cada herramienta tiene su ventana, la compactación es como resumir apuntes,
y markdown es el "idioma" que la IA entiende mejor.
Preview del Lab 3: vamos a ver cómo la IA puede tener "empleados especializados" que hacen tareas específicas.
Timing: 2 min
-->

---
layout: cover
---

# ¡Muchas Gracias!

## Nos vemos en el Lab 03

<!--
Agradecer al equipo por la participación.
Recordar que el Lab 3 será sobre Agentes, Skills y Comandos.
Abrir espacio para preguntas finales.
-->
