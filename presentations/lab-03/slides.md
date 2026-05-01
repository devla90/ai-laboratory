---
theme: ../../theme
title: 'AI Laboratory - Lab 03: Agentes, Skills y Comandos'
info: |
  ## AI Laboratory
  Laboratorio de Inteligencia Artificial - Sesión 3 de 4

  Agentes, skills y comandos: cómo organizar la IA para trabajo especializado
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

## Lab 03: Agentes, Skills y Comandos

<div class="mt-8 text-sm opacity-80">Luis Rosales</div>
<div class="text-xs opacity-50">Software Engineer AI</div>
<div class="mt-4 text-xs opacity-40">Serie de 4 laboratorios | Sesión 3</div>

<!--
Bienvenida a la tercera sesión del AI Laboratory.
Hoy vamos a ver cómo organizar la IA en "empleados especializados" que trabajan con consistencia y calidad.
Timing: 1 min
-->

---

# Recap: Labs 01 y 02

<div class="grid grid-cols-2 gap-5 mt-6">

<v-click>
<div class="p-4 rounded-lg" style="background: #1a1a2e; color: white">
  <div class="text-lg mb-2">🧠 Lab 01: Fundamentos</div>
  <p class="text-sm opacity-80">La IA predice, no piensa. Cuando no sabe, alucina con total confianza.</p>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg" style="background: #2D3748; color: white">
  <div class="text-lg mb-2">📝 Lab 02: Contexto</div>
  <p class="text-sm opacity-80">La "pizarra" tiene un límite. La compactación resume lo viejo. Markdown mejora los prompts.</p>
</div>
</v-click>

</div>

<v-click>
<div class="mt-6 p-4 rounded-lg" style="background: #EC0000; color: white">
  <div class="text-lg mb-2">🎯 Hoy: Organización</div>
  <p class="text-sm opacity-80">Ya sabemos cómo funciona la IA y cómo hablarle. Ahora veamos cómo organizarla para que trabaje de forma especializada y consistente.</p>
</div>
</v-click>

<!--
Recap breve de los dos labs anteriores. Lab 1: la IA predice, alucina. Lab 2: contexto limitado, markdown ayuda.
Hoy: cómo organizar la IA en roles especializados para que sea más útil y consistente.
Timing: 2 min
Transición: "Imaginen que en vez de tener UNA IA genérica, pudieran tener un equipo de expertos..."
-->

---

# ¿Qué son los Agentes?

<div class="mt-6 space-y-4">

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🤖</div>
  <div>
    <strong>Instancia de IA con un rol definido</strong>
    <p class="text-sm opacity-70 mt-1">Conocimiento específico, comportamiento predecible, área de expertise clara</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🎯</div>
  <div>
    <strong>Creas "expertos" en vez de usar una IA genérica</strong>
    <p class="text-sm opacity-70 mt-1">Cada agente sabe exactamente qué hacer porque tiene instrucciones claras</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🧩</div>
  <div>
    <strong>Componentes de un agente</strong>
    <p class="text-sm opacity-70 mt-1">Nombre, modelo, descripción, instrucciones del sistema, skills que puede cargar</p>
  </div>
</div>
</v-click>

</div>

<v-click>
<div class="mt-6 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  💡 Como darle a la IA un <strong>puesto de trabajo</strong> con descripción de cargo
</div>
</v-click>

<!--
Un agente es una instancia de IA con un rol definido. En vez de tener una IA genérica que intenta hacer todo,
creas expertos: uno para revisar código, otro para documentar, otro para generar presentaciones.
Cada uno sabe exactamente qué hacer porque tiene instrucciones claras y un área de expertise definida.
Timing: 2.5 min
Transición: "Para entender mejor, pensemos en una empresa..."
-->

---

# Analogía: Empleados Especializados

<div class="mt-6">

<v-click>
<div class="p-3 rounded-lg text-center text-sm mb-6" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  En vez de <strong>UN empleado que hace todo</strong> (y a veces se equivoca)...
</div>
</v-click>

<div class="grid grid-cols-3 gap-4">

<v-click>
<div class="p-4 rounded-lg text-center" style="background: #1a1a2e; color: white">
  <div class="text-3xl mb-3">🏗️</div>
  <strong class="text-sm">Arquitecto</strong>
  <p class="text-xs mt-2 opacity-70">Solo diseña estructuras de código</p>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg text-center" style="background: #2D3748; color: white">
  <div class="text-3xl mb-3">🔒</div>
  <strong class="text-sm">Auditor de Seguridad</strong>
  <p class="text-xs mt-2 opacity-70">Solo revisa vulnerabilidades</p>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg text-center" style="background: #C00000; color: white">
  <div class="text-3xl mb-3">📝</div>
  <strong class="text-sm">Redactor</strong>
  <p class="text-xs mt-2 opacity-70">Solo escribe documentación</p>
</div>
</v-click>

</div>

</div>

<v-click>
<div class="mt-6 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  Cada uno sabe su área porque tiene <strong>instrucciones claras</strong> y <strong>expertise definida</strong> — un agente funciona igual
</div>
</v-click>

<!--
Imaginen una empresa donde en vez de tener un empleado que hace todo (y a veces mal),
tienen especialistas: un arquitecto, un auditor, un redactor.
Cada uno sabe exactamente qué hacer. Un agente de IA funciona igual: tiene un rol claro y no se sale de él.
Timing: 2.5 min
Transición: "Veamos cómo se ve un agente en la práctica..."
-->

---

# Agentes — Ejemplo Real

<div class="mt-6">

<v-click>
<div class="p-5 rounded-lg font-mono text-sm leading-relaxed" style="background: #1a1a2e; color: #F7FAFC">
<span style="color: #EC0000">nombre:</span> code-reviewer<br>
<span style="color: #EC0000">modelo:</span> opus (tareas complejas)<br>
<span style="color: #EC0000">descripción:</span> Revisa código buscando bugs y mejoras<br>
<span style="color: #EC0000">instrucciones:</span><br>
<span class="opacity-60">&nbsp;&nbsp;- Revisar seguridad y rendimiento</span><br>
<span class="opacity-60">&nbsp;&nbsp;- Sugerir mejoras con justificación</span><br>
<span class="opacity-60">&nbsp;&nbsp;- No cambiar estilo personal del dev</span><br>
<span class="opacity-60">&nbsp;&nbsp;- Responder en español</span>
</div>
</v-click>

<div class="grid grid-cols-2 gap-4 mt-5">

<v-click>
<div class="p-3 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <div class="font-bold text-sm mb-1" style="color: #EC0000">🎯 Modelo</div>
  <p class="text-xs">Opus para tareas complejas, Sonnet para tareas rápidas</p>
</div>
</v-click>

<v-click>
<div class="p-3 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <div class="font-bold text-sm mb-1" style="color: #EC0000">⚡ Activación</div>
  <p class="text-xs">Se activa automáticamente según el tipo de tarea</p>
</div>
</v-click>

</div>

</div>

<!--
Ejemplo concreto de un agente "code-reviewer". Tiene nombre, modelo, y instrucciones claras.
No necesitan saber la sintaxis exacta, solo el concepto: le das un rol, instrucciones, y la IA se comporta así.
El modelo define la capacidad: opus para análisis profundo, sonnet para tareas rápidas.
Timing: 2 min
Transición: "Ahora, un agente necesita conocimiento. ¿De dónde lo saca?"
-->

---

# ¿Qué son los Skills?

<div class="mt-6 space-y-4">

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">📦</div>
  <div>
    <strong>Paquete de conocimiento reutilizable</strong>
    <p class="text-sm opacity-70 mt-1">Un agente lo carga cuando necesita expertise en un tema específico</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🧩</div>
  <div>
    <strong>Modulares</strong> — cada skill cubre un tema específico
    <p class="text-sm opacity-70 mt-1">No necesitas cargar todo a la vez, solo lo que necesitas</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🔄</div>
  <div>
    <strong>Reutilizables</strong> — múltiples agentes usan el mismo skill
    <p class="text-sm opacity-70 mt-1">Actualizas un skill y todos los agentes se benefician</p>
  </div>
</div>
</v-click>

</div>

<v-click>
<div class="mt-6 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  💡 Un agente sin skills es como un <strong>empleado sin capacitación</strong>
</div>
</v-click>

<!--
Los skills son paquetes de conocimiento que los agentes cargan cuando los necesitan.
Son modulares: cada uno cubre un tema. Son reutilizables: varios agentes pueden usar el mismo.
Y son ligeros: se cargan bajo demanda, no se llenan la memoria con todo.
Timing: 2.5 min
Transición: "Piensen en esto como manuales de entrenamiento..."
-->

---

# Analogía: Manuales de Entrenamiento

<div class="grid grid-cols-2 gap-6 mt-6">

<v-click>
<div class="flex flex-col items-center justify-center p-6 rounded-xl" style="background: #FAFAFA; border: 1px solid rgba(236,0,0,0.12); min-height: 220px">
  <div style="font-size: 4em">📚</div>
  <div class="mt-3 text-lg font-semibold" style="color: #EC0000">Estantería de Manuales</div>
  <div class="text-sm opacity-60 mt-1">Toma el que necesitas · Devuélvelo al terminar</div>
</div>
</v-click>

<div class="space-y-3 flex flex-col justify-center">

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Cada empleado tiene una <strong>estantería de manuales</strong></span>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Toma el <strong>manual correspondiente</strong> a la tarea</span>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>Lo lee, <strong>aplica</strong> lo que dice, y lo devuelve</span>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-2">
  <span style="color: #EC0000">▸</span>
  <span>No memoriza todo — <strong>carga lo que necesita</strong></span>
</div>
</v-click>

</div>
</div>

<!--
Como en un trabajo real: nadie memoriza todos los procesos de la empresa.
Cuando necesitas hacer algo específico, consultas el manual. Lo mismo hace un agente con sus skills.
El skill de "colores" le dice qué paleta usar. El skill de "Slidev" le dice cómo estructurar los slides.
Timing: 2.5 min
Transición: "Tenemos al experto y su conocimiento. ¿Cómo lo activamos fácilmente?"
-->

---

# ¿Qué son los Comandos?

<div class="mt-6 space-y-4">

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">⚡</div>
  <div>
    <strong>Atajo que ejecuta una tarea predefinida</strong>
    <p class="text-sm opacity-70 mt-1">Una sola palabra activa múltiples pasos complejos</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🔁</div>
  <div>
    <strong>Consistentes</strong> — siempre hacen lo mismo
    <p class="text-sm opacity-70 mt-1">No depende de cómo lo pidas: el resultado es predecible</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🎛️</div>
  <div>
    <strong>Parametrizables</strong> — aceptan argumentos
    <p class="text-sm opacity-70 mt-1">Ejemplo: <code>/generate-lab 01</code> → genera el Lab 1</p>
  </div>
</div>
</v-click>

</div>

<!--
Los comandos son la interfaz simple para el usuario. En vez de escribir 10 líneas de instrucciones,
escribes una palabra y la IA sabe exactamente qué hacer.
Son como los atajos del teclado: simples por fuera, complejos por dentro.
Timing: 2 min
Transición: "¿Les suena familiar? Es como Ctrl+C..."
-->

---

# Analogía: Atajos de Teclado

<div class="mt-6">

<div class="grid grid-cols-2 gap-6">

<v-click>
<div>
<div class="text-sm font-bold mb-2" style="color: #C00000">⌨️ Atajo de teclado</div>
<div class="p-4 rounded-lg" style="background: #1a1a2e; color: white">
  <div class="font-mono text-lg text-center mb-3"><span style="color: #EC0000">Ctrl</span> + <span style="color: #EC0000">C</span></div>
  <div class="text-xs opacity-70 space-y-1">
    <div>→ Seleccionar texto en memoria</div>
    <div>→ Serializar al clipboard</div>
    <div>→ Notificar al sistema operativo</div>
    <div>→ Hacer disponible para pegar</div>
  </div>
</div>
<div class="mt-2 text-xs text-center opacity-60">2 teclas → operación compleja</div>
</div>
</v-click>

<v-click>
<div>
<div class="text-sm font-bold mb-2" style="color: #EC0000">🤖 Comando de IA</div>
<div class="p-4 rounded-lg" style="background: #1a1a2e; color: white">
  <div class="font-mono text-lg text-center mb-3"><span style="color: #EC0000">/generate-lab</span> 01</div>
  <div class="text-xs opacity-70 space-y-1">
    <div>→ Leer estructura del lab</div>
    <div>→ Cargar skills de diseño</div>
    <div>→ Generar contenido y slides</div>
    <div>→ Verificar resultado</div>
  </div>
</div>
<div class="mt-2 text-xs text-center opacity-60">1 línea → flujo multi-paso</div>
</div>
</v-click>

</div>

</div>

<!--
Todos usan Ctrl+C sin pensar en lo que pasa por detrás: selección, serialización, clipboard...
Los comandos de IA funcionan igual: una línea simple que ejecuta un flujo complejo.
/generate-lab 01: lee estructura, carga skills, genera contenido, verifica. Todo automático.
Timing: 2 min
Transición: "Ahora veamos cómo se conectan las tres piezas..."
-->

---

# Cómo se Combinan

<div class="flex items-center justify-center mt-8">
<div class="flex items-center gap-3">

<v-click>
<div class="rounded-xl text-center" style="background: #EC0000; color: white; width: 150px; height: 100px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">⚡</div>
  <div class="text-xs font-bold mt-1">Comando</div>
  <div class="font-mono text-xs opacity-80 mt-1">/generate-lab 01</div>
</div>
</v-click>

<v-click>
<div style="color: #2D3748; font-size: 1.3em">→</div>
<div class="rounded-xl text-center" style="background: #1a1a2e; color: white; width: 150px; height: 100px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">🤖</div>
  <div class="text-xs font-bold mt-1">Agente</div>
  <div class="text-xs opacity-75 mt-1">lab-conductor</div>
</div>
</v-click>

<v-click>
<div style="color: #2D3748; font-size: 1.3em">→</div>
<div class="rounded-xl text-center" style="background: #2D3748; color: white; width: 150px; height: 100px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">📚</div>
  <div class="text-xs font-bold mt-1">Skills</div>
  <div class="text-xs opacity-75 mt-1">slidev · colores · IA</div>
</div>
</v-click>

<v-click>
<div style="color: #2D3748; font-size: 1.3em">→</div>
<div class="rounded-xl text-center" style="background: #C00000; color: white; width: 150px; height: 100px; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 0.5em">
  <div class="text-lg">📊</div>
  <div class="text-xs font-bold mt-1">Output</div>
  <div class="text-xs opacity-75 mt-1">slides.md</div>
</div>
</v-click>

</div>
</div>

<v-click>
<div class="mt-8 p-4 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  El <strong>comando</strong> activa al <strong>agente</strong>, que carga los <strong>skills</strong> necesarios y produce el <strong>resultado</strong>
</div>
</v-click>

<!--
Aquí es donde todo se conecta. El usuario escribe un comando simple.
Ese comando activa un agente especializado. El agente carga los skills que necesita.
Y produce un resultado consistente y de calidad.
Este es el flujo que usamos para generar estas mismas presentaciones.
Timing: 2.5 min
Transición: "¿Y cuáles son los beneficios concretos de trabajar así?"
-->

---

# Beneficio: Consistencia

<div class="grid grid-cols-2 gap-6 mt-8">

<v-click>
<div>
<div class="text-sm font-bold mb-3" style="color: #C00000">❌ Sin agentes</div>
<div class="p-4 rounded-lg" style="background: #1a1a2e; color: white">
  <div class="space-y-2 text-sm">
    <div>😕 La calidad <strong>varía</strong> cada vez</div>
    <div>😕 Depende de <strong>cómo lo pidas</strong></div>
    <div>😕 Diferente formato cada vez</div>
    <div>😕 Se "olvida" de requisitos</div>
  </div>
</div>
</div>
</v-click>

<v-click>
<div>
<div class="text-sm font-bold mb-3" style="color: #EC0000">✅ Con agentes</div>
<div class="p-4 rounded-lg" style="background: #EC0000; color: white">
  <div class="space-y-2 text-sm">
    <div>✓ Mismo resultado <strong>consistente</strong></div>
    <div>✓ Mismas reglas <strong>siempre</strong></div>
    <div>✓ Formato <strong>estandarizado</strong></div>
    <div>✓ Verificaciones <strong>automáticas</strong></div>
  </div>
</div>
</div>
</v-click>

</div>

<v-click>
<div class="mt-6 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  💡 Ya no depende de tu memoria — las reglas están <strong>en el agente</strong>
</div>
</v-click>

<!--
La consistencia es el primer gran beneficio. Sin agentes, cada vez que pides algo la calidad varía.
Con agentes, el resultado sigue las mismas reglas siempre: mismo formato, mismo estilo, mismas verificaciones.
Ya no depende de "acordarte" de incluir todo en el prompt.
Timing: 2 min
Transición: "Además de consistencia, ganamos velocidad..."
-->

---

# Beneficios: Velocidad y Calidad

<div class="mt-6 space-y-5">

<v-click>
<div class="grid grid-cols-2 gap-4">
  <div class="p-3 rounded-lg text-center" style="background: #1a1a2e; color: white">
    <div class="text-xs opacity-60 mb-1">Sin comandos</div>
    <div class="text-sm">Escribir <strong>10 líneas</strong> de instrucciones cada vez</div>
  </div>
  <div class="p-3 rounded-lg text-center" style="background: #EC0000; color: white">
    <div class="text-xs opacity-80 mb-1">Con comandos</div>
    <div class="text-sm font-mono">/generate-lab 01</div>
  </div>
</div>
</v-click>

<v-click>
<div class="grid grid-cols-2 gap-4">
  <div class="p-3 rounded-lg text-center" style="background: #1a1a2e; color: white">
    <div class="text-xs opacity-60 mb-1">Sin skills</div>
    <div class="text-sm">La IA usa conocimiento <strong>general</strong> (a veces incompleto)</div>
  </div>
  <div class="p-3 rounded-lg text-center" style="background: #EC0000; color: white">
    <div class="text-xs opacity-80 mb-1">Con skills</div>
    <div class="text-sm">Conocimiento <strong>específico</strong> y actualizado</div>
  </div>
</div>
</v-click>

<v-click>
<div class="p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  ⏱️ Lo que antes tomaba <strong>10 minutos</strong> de instrucciones → ahora es <strong>un comando</strong>
</div>
</v-click>

</div>

<!--
Velocidad: en vez de escribir instrucciones largas cada vez, un comando y listo.
Calidad: en vez de depender del conocimiento general de la IA (que puede estar incompleto),
le das conocimiento específico y actualizado a través de skills.
Timing: 2 min
Transición: "Veamos ejemplos concretos de cómo lo usamos en este proyecto..."
-->

---

# Ejemplos de Nuestro Equipo

<div class="mt-6 space-y-3">

<v-click>
<div class="flex items-center gap-3 p-3 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <div class="font-mono text-sm px-3 py-1 rounded" style="background: #1a1a2e; color: #EC0000">/generate-lab</div>
  <span class="text-sm">Genera presentaciones Slidev con estilo <strong>consistente</strong></span>
</div>
</v-click>

<v-click>
<div class="flex items-center gap-3 p-3 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <div class="font-mono text-sm px-3 py-1 rounded" style="background: #1a1a2e; color: #EC0000">/generate-guide</div>
  <span class="text-sm">Crea guías del moderador <strong>alineadas</strong> al contenido</span>
</div>
</v-click>

<v-click>
<div class="flex items-center gap-3 p-3 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <div class="font-mono text-sm px-3 py-1 rounded" style="background: #1a1a2e; color: #EC0000">code-reviewer</div>
  <span class="text-sm">Revisa código con <strong>criterios específicos</strong> y formato estandarizado</span>
</div>
</v-click>

<v-click>
<div class="flex items-center gap-3 p-3 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <div class="font-mono text-sm px-3 py-1 rounded" style="background: #1a1a2e; color: #EC0000">doc-writer</div>
  <span class="text-sm">Documenta con <strong>nivel de detalle</strong> y formato estándar</span>
</div>
</v-click>

</div>

<v-click>
<div class="mt-4 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  🔄 Creas una vez, usas <strong>infinitas veces</strong>. Actualizas un skill, todos se benefician.
</div>
</v-click>

<!--
Estos son ejemplos concretos de ESTE proyecto. Estas mismas presentaciones se generaron con /generate-lab.
La guía del moderador con /generate-guide. El code-reviewer revisa PRs con criterios consistentes.
Lo importante: lo creas una vez y lo usas infinitas veces. Actualizas un skill y todos mejoran.
Timing: 3 min
Transición: "Ahora les toca a ustedes. Vamos a diseñar un agente..."
-->

---
layout: interactive
---

# Ejercicio: Diseña tu Agente

<v-click>
<div class="mt-6 p-4 rounded-lg text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  <strong style="color: #EC0000">Instrucciones:</strong> Piensen en un agente que les sería útil en su trabajo diario. Definan:<br><br>
  <strong>1.</strong> Nombre del agente<br>
  <strong>2.</strong> ¿Qué hace? (su rol)<br>
  <strong>3.</strong> ¿Qué conocimiento necesita? (skills)
</div>
</v-click>

<!--
Dar 2-3 minutos para pensar. Pueden hacerlo en parejas o individualmente.
Ejemplo para arrancar si nadie empieza: "Yo haría un agente de PR reviews que revise seguridad, rendimiento y estilo."
Sugerencias: agente de testing, agente de documentación, agente de migración de datos, agente de onboarding.
Timing: 3 min
Transición: "Veamos qué agentes diseñaron..."
-->

---
layout: interactive
---

# Puesta en Común

<v-click>
<div class="mt-6 p-4 rounded-lg text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  <strong style="color: #EC0000">Discusión:</strong> ¿Qué skills necesitaría tu agente? ¿Qué comando lo activaría?
</div>
</v-click>

<!--
Que 3-4 personas compartan su agente. Para cada uno preguntar:
- ¿Qué skills necesitaría? (guías de estilo, reglas de negocio, templates)
- ¿Qué comando lo activaría? (/review-pr, /write-docs, /run-migration)
- ¿Se les ocurre algún skill que varios agentes podrían compartir?
Destacar cuando alguien identifica un skill reutilizable — ese es el poder de la modularidad.
Timing: 3 min
Transición: "Excelente. Recapitulemos lo que aprendimos..."
-->

---
layout: section
---

# Resumen Lab 03

<div class="mt-6 text-left max-w-xl mx-auto space-y-3">
<v-clicks>
  <div class="flex items-center gap-3"><span class="text-2xl">🤖</span> <strong>Agentes</strong>: IA especializada con rol definido (empleados)</div>
  <div class="flex items-center gap-3"><span class="text-2xl">📚</span> <strong>Skills</strong>: conocimiento modular y reutilizable (manuales)</div>
  <div class="flex items-center gap-3"><span class="text-2xl">⚡</span> <strong>Comandos</strong>: atajos que ejecutan tareas complejas (Ctrl+C)</div>
  <div class="flex items-center gap-3"><span class="text-2xl">🎯</span> Juntos: <strong>consistencia, velocidad y calidad</strong></div>
</v-clicks>
</div>

<v-click>
<div class="mt-6 text-sm opacity-70">
  <strong>Próximo Lab:</strong> Herramientas en Acción — Claude Code, Codex, Copilot en la práctica
</div>
</v-click>

<!--
Cuatro puntos clave del Lab 3.
Agentes son empleados especializados. Skills son sus manuales. Comandos son los atajos.
Juntos logran consistencia, velocidad y calidad.
Preview del Lab 4: vamos a ver cómo estas herramientas reales implementan estos conceptos.
Timing: 3 min
-->

---
layout: cover
---

# ¡Muchas Gracias!

## Nos vemos en el Lab 04

<!--
Agradecer al equipo por la participación y especialmente por el ejercicio grupal.
Recordar que el Lab 4 será el cierre: herramientas reales en acción.
Abrir espacio para preguntas finales.
-->
