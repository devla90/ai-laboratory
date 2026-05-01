---
theme: ../../theme
title: 'AI Laboratory - Lab 04: Herramientas en Acción'
info: |
  ## AI Laboratory
  Laboratorio de Inteligencia Artificial - Sesión 4 de 4

  Claude Code, Codex, Gemini CLI y GitHub Copilot en acción
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

## Lab 04: Herramientas en Acción

<div class="mt-8 text-sm opacity-80">Luis Rosales</div>
<div class="text-xs opacity-50">Software Engineer AI</div>
<div class="mt-4 text-xs opacity-40">Serie de 4 laboratorios | Sesión Final</div>

<!--
Bienvenida a la última sesión del AI Laboratory.
Hoy vamos a ver cómo las herramientas reales implementan todo lo que aprendimos: agentes, skills, comandos, contexto.
Timing: 1 min
-->

---

# Recap: Labs 01, 02 y 03

<div class="grid grid-cols-3 gap-4 mt-6">

<v-click>
<div class="p-4 rounded-lg" style="background: #1a1a2e; color: white">
  <div class="text-lg mb-2">🧠 Lab 01</div>
  <p class="text-sm opacity-80">La IA predice, no piensa. Alucina cuando no sabe.</p>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg" style="background: #2D3748; color: white">
  <div class="text-lg mb-2">📝 Lab 02</div>
  <p class="text-sm opacity-80">Contexto limitado. Compactación. Markdown mejora prompts.</p>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg" style="background: #C00000; color: white">
  <div class="text-lg mb-2">🤖 Lab 03</div>
  <p class="text-sm opacity-80">Agentes (empleados), Skills (manuales), Comandos (atajos).</p>
</div>
</v-click>

</div>

<v-click>
<div class="mt-6 p-4 rounded-lg" style="background: #EC0000; color: white">
  <div class="text-lg mb-2">🔧 Hoy: Todo en Acción</div>
  <p class="text-sm opacity-80">Cómo las herramientas reales implementan estos conceptos. Claude Code, Codex, Gemini, Copilot.</p>
</div>
</v-click>

<!--
Recap de los 3 labs: fundamentos, contexto, organización.
Hoy cerramos el ciclo: vamos a ver cómo todo esto se aplica en herramientas reales que podemos usar ya.
Timing: 2 min
Transición: "Empecemos con la herramienta que usamos para crear estas presentaciones..."
-->

---

# Claude Code — Agentes

<div class="mt-6 space-y-4">

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">💻</div>
  <div>
    <strong>CLI de Anthropic</strong> — trabaja directo en tu terminal
    <p class="text-sm opacity-70 mt-1">No es un chat: lee, edita y ejecuta en tu proyecto real</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">📄</div>
  <div>
    <strong>Agentes como archivos <code>.md</code></strong>
    <p class="text-sm opacity-70 mt-1">En <code>.claude/agents/</code> — frontmatter YAML + instrucciones en markdown</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🎯</div>
  <div>
    <strong>Se invocan por nombre</strong> o automáticamente según la tarea
    <p class="text-sm opacity-70 mt-1">Cada agente tiene: nombre, modelo (opus/sonnet), descripción y reglas</p>
  </div>
</div>
</v-click>

</div>

<v-click>
<div class="mt-5 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  💡 Estas presentaciones se generaron con un agente de Claude Code
</div>
</v-click>

<!--
Claude Code es la herramienta que usamos para generar estas presentaciones.
Es un CLI: trabaja directamente en tu terminal, lee y edita archivos de tu proyecto.
Los agentes se definen como archivos .md — markdown puro, editable, versionable en git.
Timing: 2.5 min
Transición: "¿Y cómo maneja los skills y comandos?"
-->

---

# Claude Code — Skills y Comandos

<div class="mt-6">

<div class="grid grid-cols-2 gap-5">

<v-click>
<div>
<div class="text-sm font-bold mb-2" style="color: #EC0000">📚 Skills</div>
<div class="p-4 rounded-lg font-mono text-xs leading-relaxed" style="background: #1a1a2e; color: #F7FAFC">
<span style="color: #EC0000">skills/</span><br>
<span class="opacity-60">├──</span> design/<br>
<span class="opacity-60">│&nbsp;&nbsp;├──</span> <span style="color: #EC0000">slidev-futuristic/</span>SKILL.md<br>
<span class="opacity-60">│&nbsp;&nbsp;└──</span> <span style="color: #EC0000">color-system/</span>SKILL.md<br>
<span class="opacity-60">└──</span> ai-knowledge/<br>
<span class="opacity-60">&nbsp;&nbsp;&nbsp;└──</span> <span style="color: #EC0000">ai-fundamentals/</span>SKILL.md
</div>
<div class="mt-2 text-xs opacity-60 text-center">Carga bajo demanda por el agente</div>
</div>
</v-click>

<v-click>
<div>
<div class="text-sm font-bold mb-2" style="color: #EC0000">⚡ Comandos</div>
<div class="p-4 rounded-lg font-mono text-xs leading-relaxed" style="background: #1a1a2e; color: #F7FAFC">
<span style="color: #EC0000">.claude/commands/</span><br>
<span class="opacity-60">├──</span> generate-lab.md<br>
<span class="opacity-60">├──</span> generate-guide.md<br>
<span class="opacity-60">└──</span> preview-slides.md<br>
<br>
<span class="opacity-60"># Uso:</span><br>
<span style="color: #EC0000">/generate-lab</span> 01
</div>
<div class="mt-2 text-xs opacity-60 text-center">Se invocan con /nombre argumentos</div>
</div>
</v-click>

</div>

</div>

<v-click>
<div class="mt-5 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  💡 Todo es <strong>markdown</strong> — editable y versionable en git, sin lenguaje nuevo que aprender
</div>
</v-click>

<!--
Los skills son archivos SKILL.md organizados por categoría. Se cargan cuando el agente los necesita.
Los comandos son archivos .md en .claude/commands/. Se invocan con /nombre.
Lo clave: TODO es markdown. No necesitan aprender un lenguaje nuevo. Si saben escribir texto, pueden crear skills y comandos.
Timing: 2.5 min
Transición: "Veamos cómo se ve en acción..."
-->

---

# Claude Code — En Acción

<div class="mt-6">
<v-click>
<div class="p-5 rounded-lg font-mono text-sm" style="background: #1a1a2e; color: #F7FAFC">
<div><span style="color: #EC0000">$</span> claude</div>
<div class="my-2 p-3 rounded" style="border: 1px solid rgba(255,255,255,0.2)">
<div><span style="color: #EC0000">Claude Code</span></div>
<div>Contexto: <span style="color: #6495ED">~200K tokens</span></div>
<div>CLAUDE.md cargado</div>
</div>
<div><span style="color: #EC0000">&gt;</span> /generate-lab 04</div>
<div class="opacity-60">Leyendo lab-index.md...</div>
<div class="opacity-60">Cargando skills de diseno...</div>
<div class="opacity-60">Generando presentacion...</div>
<div style="color: #6495ED">Presentacion generada en presentations/lab-04/slides.md</div>
</div>
</v-click>
<v-click>
<div class="grid grid-cols-3 gap-3 mt-4">
<div class="p-2 rounded text-xs text-center" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">~200K tokens de contexto</div>
<div class="p-2 rounded text-xs text-center" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">Compactacion automatica</div>
<div class="p-2 rounded text-xs text-center" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">Lee archivos bajo demanda</div>
</div>
</v-click>
</div>

<!--
Así se ve Claude Code en acción. Abres la terminal, escribes un comando, y se ejecuta todo el flujo.
El CLAUDE.md se carga siempre como contexto base — ahí están las reglas del proyecto.
Contexto de ~200K tokens con compactación automática. Lee archivos del proyecto bajo demanda.
Si hay tiempo, pueden mostrar un ejemplo rápido en terminal.
Timing: 2 min
Transición: "Veamos cómo otras herramientas abordan los mismos problemas..."
-->

---

# OpenAI Codex

<div class="mt-6 space-y-4">

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">📦</div>
  <div>
    <strong>Agente de código en sandbox aislado</strong>
    <p class="text-sm opacity-70 mt-1">Clona tu repo completo y trabaja de forma autónoma</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🔄</div>
  <div>
    <strong>Enfoque asíncrono</strong> — le das la tarea, te entrega el resultado
    <p class="text-sm opacity-70 mt-1">No es conversacional: ejecuta y entrega</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🧠</div>
  <div>
    <strong>Modelos: GPT-4.1 / o3 / o4-mini</strong>
    <p class="text-sm opacity-70 mt-1">Contexto ~128-200K tokens según modelo utilizado</p>
  </div>
</div>
</v-click>

</div>

<v-click>
<div class="mt-5 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  💡 Ideal para tareas aisladas que no necesitan <strong>conversación interactiva</strong>
</div>
</v-click>

<!--
Codex de OpenAI tiene un enfoque muy diferente: no es conversacional.
Le das una tarea, clona tu repo en un sandbox, ejecuta, y te entrega el resultado.
Es ideal para tareas bien definidas que no necesitan ir y venir.
Timing: 2.5 min
Transición: "Google tiene su propia propuesta..."
-->

---

# Gemini CLI

<div class="mt-6 space-y-4">

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🌐</div>
  <div>
    <strong>Google Agent Development Kit (ADK)</strong>
    <p class="text-sm opacity-70 mt-1">Agentes definidos en Python con orquestación multi-agente</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🔌</div>
  <div>
    <strong>Extensiones y herramientas integradas</strong>
    <p class="text-sm opacity-70 mt-1">Google Search, Code Execution, integración con Google Cloud</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">📏</div>
  <div>
    <strong>Hasta 1M-2M tokens de contexto</strong>
    <p class="text-sm opacity-70 mt-1">La ventana más grande disponible — pero la calidad puede degradar</p>
  </div>
</div>
</v-click>

</div>

<v-click>
<div class="mt-5 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  ⚠️ Más contexto no siempre = mejor resultado (recordar Lab 02)
</div>
</v-click>

<!--
Gemini de Google tiene la ventana de contexto más grande: hasta 2 millones de tokens.
Pero recuerden del Lab 2: más contexto no siempre significa mejor respuesta.
El ADK permite crear agentes en Python con orquestación multi-agente.
Timing: 2.5 min
Transición: "Y la herramienta más usada en la industria..."
-->

---

# GitHub Copilot — Agentes y Extensiones

<div class="mt-6 space-y-4">

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🖥️</div>
  <div>
    <strong>Integrado directamente en el IDE</strong>
    <p class="text-sm opacity-70 mt-1">VS Code, JetBrains — no necesitas salir del editor</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">🤖</div>
  <div>
    <strong>Agentes predefinidos:</strong> <code>@workspace</code>, <code>@terminal</code>, <code>@vscode</code>
    <p class="text-sm opacity-70 mt-1">Copilot Extensions: agentes de terceros del marketplace</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold shrink-0" style="background: #EC0000">📋</div>
  <div>
    <strong>Instruction files</strong> para personalizar
    <p class="text-sm opacity-70 mt-1"><code>.github/copilot-instructions.md</code> + MCP para herramientas externas</p>
  </div>
</div>
</v-click>

</div>

<v-click>
<div class="mt-5 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  💡 El más utilizado en la industria — su fuerza es la <strong>integración en el IDE</strong>
</div>
</v-click>

<!--
Copilot es probablemente el que más conocen. Vive dentro del IDE.
Tiene agentes predefinidos como @workspace y @terminal, más extensiones del marketplace.
Se puede personalizar con instruction files — similar al CLAUDE.md pero en formato GitHub.
Timing: 2.5 min
Transición: "Veamos los diferentes modos de uso..."
-->

---

# Copilot — Integración en IDE

<div class="mt-6 space-y-3">

<v-click>
<div class="p-4 rounded-lg flex items-center gap-4" style="background: #1a1a2e; color: white">
  <div class="text-2xl">⌨️</div>
  <div class="flex-1">
    <strong>Inline Suggestions</strong> <span class="text-xs opacity-60 ml-2">~8K tokens</span>
    <p class="text-xs opacity-70 mt-1">Autocompletado en tiempo real mientras escribes</p>
  </div>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg flex items-center gap-4" style="background: #2D3748; color: white">
  <div class="text-2xl">💬</div>
  <div class="flex-1">
    <strong>Chat Panel</strong> <span class="text-xs opacity-60 ml-2">~32-64K tokens</span>
    <p class="text-xs opacity-70 mt-1">Conversación sobre tu código con archivos abiertos como contexto</p>
  </div>
</div>
</v-click>

<v-click>
<div class="p-4 rounded-lg flex items-center gap-4" style="background: #C00000; color: white">
  <div class="text-2xl">🤖</div>
  <div class="flex-1">
    <strong>Agent Mode</strong> <span class="text-xs opacity-60 ml-2">~128K tokens</span>
    <p class="text-xs opacity-70 mt-1">Ejecuta tareas multi-archivo con slash commands: /explain, /fix, /test</p>
  </div>
</div>
</v-click>

</div>

<v-click>
<div class="mt-4 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  Menos personalizable que Claude Code, pero <strong>más accesible</strong> — ideal para el día a día
</div>
</v-click>

<!--
Tres niveles de uso, cada uno con más contexto y más capacidad.
Inline: autocompletado rápido. Chat: conversación sobre código. Agent: tareas multi-archivo.
Es menos personalizable que Claude Code, pero mucho más accesible para el uso diario.
Timing: 2.5 min
Transición: "Pongamos todo en perspectiva con una comparativa..."
-->

---
layout: comparison
---

::header::

# Matriz Comparativa

::default::

<v-click>
<div class="overflow-auto">
<table class="text-xs w-full" style="border-collapse: collapse">
<thead>
<tr style="background: #1a1a2e; color: white">
  <th class="p-2 text-left">Característica</th>
  <th class="p-2 text-center">Claude Code</th>
  <th class="p-2 text-center">Codex</th>
  <th class="p-2 text-center">Gemini</th>
  <th class="p-2 text-center">Copilot</th>
</tr>
</thead>
<tbody>
<tr style="border-bottom: 1px solid rgba(236,0,0,0.12)">
  <td class="p-2 font-bold">Interfaz</td>
  <td class="p-2 text-center">Terminal CLI</td>
  <td class="p-2 text-center">Terminal CLI</td>
  <td class="p-2 text-center">Terminal/Web</td>
  <td class="p-2 text-center">IDE</td>
</tr>
<tr style="border-bottom: 1px solid rgba(236,0,0,0.12); background: rgba(236,0,0,0.02)">
  <td class="p-2 font-bold">Agentes custom</td>
  <td class="p-2 text-center" style="color: #EC0000">✅ .md files</td>
  <td class="p-2 text-center">⚠️ Instrucciones</td>
  <td class="p-2 text-center" style="color: #EC0000">✅ ADK/Python</td>
  <td class="p-2 text-center">⚠️ Instructions</td>
</tr>
<tr style="border-bottom: 1px solid rgba(236,0,0,0.12)">
  <td class="p-2 font-bold">Skills modulares</td>
  <td class="p-2 text-center" style="color: #EC0000">✅ SKILL.md</td>
  <td class="p-2 text-center">❌</td>
  <td class="p-2 text-center">⚠️ Extensions</td>
  <td class="p-2 text-center">⚠️ Extensions</td>
</tr>
<tr style="border-bottom: 1px solid rgba(236,0,0,0.12); background: rgba(236,0,0,0.02)">
  <td class="p-2 font-bold">Comandos custom</td>
  <td class="p-2 text-center" style="color: #EC0000">✅ /commands</td>
  <td class="p-2 text-center">❌</td>
  <td class="p-2 text-center">❌</td>
  <td class="p-2 text-center">⚠️ Slash cmds</td>
</tr>
<tr style="border-bottom: 1px solid rgba(236,0,0,0.12)">
  <td class="p-2 font-bold">Contexto máx</td>
  <td class="p-2 text-center">~200K</td>
  <td class="p-2 text-center">~200K</td>
  <td class="p-2 text-center" style="color: #EC0000">~2M</td>
  <td class="p-2 text-center">~128K</td>
</tr>
<tr style="background: rgba(236,0,0,0.04)">
  <td class="p-2 font-bold">Mejor para</td>
  <td class="p-2 text-center text-xs">Proyectos complejos</td>
  <td class="p-2 text-center text-xs">Tareas aisladas</td>
  <td class="p-2 text-center text-xs">Contexto masivo</td>
  <td class="p-2 text-center text-xs">Desarrollo diario</td>
</tr>
</tbody>
</table>
</div>
</v-click>

<v-click>
<div class="mt-4 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  💡 No hay "mejor herramienta" — depende del <strong>caso de uso</strong> y el <strong>flujo de trabajo</strong>
</div>
</v-click>

<!--
Esta es la slide clave del lab. Dar tiempo para que lean y comparen.
No hay una herramienta que sea la mejor en todo. Cada una tiene su fortaleza.
Claude Code: proyectos complejos con agentes custom. Codex: tareas aisladas.
Gemini: cuando necesitas contexto masivo. Copilot: el día a día en el IDE.
Timing: 5 min
Transición: "Ahora, sin importar qué herramienta usen, hay prácticas que aplican a todas..."
-->

---

# Mejores Prácticas para Prompting

<div class="mt-6 space-y-3">

<v-click>
<div class="flex items-start gap-3">
  <div class="w-8 h-8 rounded-full flex items-center justify-center text-white text-sm font-bold shrink-0" style="background: #EC0000">1</div>
  <div>
    <strong>Estructurar con markdown</strong>
    <span class="text-sm opacity-70"> — headers, listas, bloques de código</span>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-3">
  <div class="w-8 h-8 rounded-full flex items-center justify-center text-white text-sm font-bold shrink-0" style="background: #EC0000">2</div>
  <div>
    <strong>Ser específico</strong>
    <span class="text-sm opacity-70"> — qué quieres, cómo lo quieres, restricciones</span>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-3">
  <div class="w-8 h-8 rounded-full flex items-center justify-center text-white text-sm font-bold shrink-0" style="background: #EC0000">3</div>
  <div>
    <strong>Dar contexto</strong>
    <span class="text-sm opacity-70"> — archivos relevantes, decisiones previas, restricciones</span>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-3">
  <div class="w-8 h-8 rounded-full flex items-center justify-center text-white text-sm font-bold shrink-0" style="background: #EC0000">4</div>
  <div>
    <strong>Iterar</strong>
    <span class="text-sm opacity-70"> — refinar el prompt basado en la respuesta</span>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-3">
  <div class="w-8 h-8 rounded-full flex items-center justify-center text-white text-sm font-bold shrink-0" style="background: #EC0000">5</div>
  <div>
    <strong>Usar templates para tareas repetitivas</strong>
    <span class="text-sm opacity-70"> — comandos y agentes</span>
  </div>
</div>
</v-click>

</div>

<!--
Tips prácticos que aplican a CUALQUIER herramienta de IA, no solo a una.
Markdown lo vimos en el Lab 2, contexto en el Lab 2, templates/comandos en el Lab 3.
Todo se conecta. La clave es ser específico e iterar.
Timing: 2.5 min
Transición: "Y una vez que la IA responde, ¿cómo sabemos si la respuesta es buena?"
-->

---

# Cómo Evaluar Calidad de Respuestas

<div class="mt-6 space-y-4">

<v-click>
<div class="flex items-start gap-3 p-3 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <span class="text-xl">🔍</span>
  <div>
    <strong>Verificar datos específicos</strong>
    <p class="text-xs opacity-70">Fechas, números, referencias — recordar la alucinación del Lab 1</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-3 p-3 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <span class="text-xl">🧪</span>
  <div>
    <strong>Probar el código generado</strong>
    <p class="text-xs opacity-70">No asumir que funciona — ejecutar, testear, validar</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-3 p-3 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <span class="text-xl">📚</span>
  <div>
    <strong>Comparar con documentación oficial</strong>
    <p class="text-xs opacity-70">La IA puede inventar APIs — siempre verificar contra la fuente</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-3 p-3 rounded-lg" style="border: 1px solid rgba(236,0,0,0.12)">
  <span class="text-xl">🧠</span>
  <div>
    <strong>Pedir explicación del razonamiento</strong>
    <p class="text-xs opacity-70">Si no puede explicar por qué, probablemente está alucinando</p>
  </div>
</div>
</v-click>

</div>

<!--
Recordar la alucinación del Lab 1. El compañero sin apuntes responde con confianza pero puede estar mal.
Regla de oro: siempre verificar. Probar el código. Comparar con documentación oficial.
Un buen truco: pedir que explique su razonamiento. Si no puede, desconfiar.
Timing: 2.5 min
Transición: "Con todo esto, ¿cómo empezamos a construir nuestro flujo de trabajo?"
-->

---

# Construyendo tu Flujo de Trabajo con IA

<div class="mt-6 space-y-4">

<v-click>
<div class="flex items-start gap-4">
  <div class="w-10 h-10 rounded-full flex items-center justify-center text-white text-sm font-bold shrink-0" style="background: #1a1a2e">1</div>
  <div>
    <strong>Empezar con UNA herramienta</strong> y una tarea específica
    <p class="text-xs opacity-70">No intentar usar todo a la vez</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-10 h-10 rounded-full flex items-center justify-center text-white text-sm font-bold shrink-0" style="background: #2D3748">2</div>
  <div>
    <strong>Crear agentes</strong> para tareas que repites frecuentemente
    <p class="text-xs opacity-70">Si lo haces 3+ veces, automatízalo</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-10 h-10 rounded-full flex items-center justify-center text-white text-sm font-bold shrink-0" style="background: #C00000">3</div>
  <div>
    <strong>Documentar lo que funciona</strong> en archivos de instrucciones
    <p class="text-xs opacity-70">CLAUDE.md, copilot-instructions.md, etc.</p>
  </div>
</div>
</v-click>

<v-click>
<div class="flex items-start gap-4">
  <div class="w-10 h-10 rounded-full flex items-center justify-center text-white text-sm font-bold shrink-0" style="background: #EC0000">4</div>
  <div>
    <strong>Combinar herramientas</strong> según la tarea
    <p class="text-xs opacity-70">Copilot para inline + Claude Code para proyectos complejos</p>
  </div>
</div>
</v-click>

</div>

<v-click>
<div class="mt-5 p-3 rounded-lg text-center text-sm" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  💡 La IA es un <strong>acelerador</strong>, no un reemplazo del proceso de desarrollo
</div>
</v-click>

<!--
Consejo práctico: no intenten usar todo a la vez. Empiecen con una herramienta y una tarea.
Cuando encuentren algo que funciona, documéntenlo. Creen agentes para lo repetitivo.
Y recuerden: la IA es un acelerador, no un reemplazo. Amplifica lo que saben hacer.
Timing: 2.5 min
Transición: "Antes de cerrar, un tema importante..."
-->

---

# Ética y Responsabilidad con IA

<div class="mt-6 space-y-3">

<v-click>
<div class="p-3 rounded-lg flex items-center gap-3" style="border: 1px solid rgba(236,0,0,0.12)">
  <span class="text-xl">🔒</span>
  <span class="text-sm"><strong>No pegar código sensible</strong> o credenciales en chats públicos</span>
</div>
</v-click>

<v-click>
<div class="p-3 rounded-lg flex items-center gap-3" style="border: 1px solid rgba(236,0,0,0.12)">
  <span class="text-xl">📋</span>
  <span class="text-sm"><strong>Revisar políticas de privacidad</strong> de cada herramienta</span>
</div>
</v-click>

<v-click>
<div class="p-3 rounded-lg flex items-center gap-3" style="border: 1px solid rgba(236,0,0,0.12)">
  <span class="text-xl">👁️</span>
  <span class="text-sm"><strong>Revisión humana siempre</strong> — el código generado necesita validación</span>
</div>
</v-click>

<v-click>
<div class="p-3 rounded-lg flex items-center gap-3" style="border: 1px solid rgba(236,0,0,0.12)">
  <span class="text-xl">⚖️</span>
  <span class="text-sm"><strong>Propiedad intelectual</strong> — tema legal en evolución</span>
</div>
</v-click>

</div>

<v-click>
<div class="mt-5 p-4 rounded-lg text-center" style="background: rgba(236,0,0,0.03); border: 1px solid rgba(236,0,0,0.12)">
  La IA <strong>amplifica tus capacidades</strong> — la <strong>responsabilidad</strong> sigue siendo tuya
</div>
</v-click>

<!--
Tema importante para cerrar. La IA es una herramienta poderosa, pero la responsabilidad es nuestra.
No pegar código sensible, revisar políticas de privacidad, siempre validar el output.
La propiedad intelectual del código generado por IA es un tema legal que todavía se está definiendo.
Timing: 2 min
Transición: "Para cerrar este workshop..."
-->

---
layout: section
---

# Recursos y Próximos Pasos

<div class="mt-6 text-left max-w-xl mx-auto space-y-3">
<v-clicks>
  <div class="flex items-center gap-3"><span class="text-2xl">🔧</span> Experimentar con la herramienta que más les interesó</div>
  <div class="flex items-center gap-3"><span class="text-2xl">🤖</span> Crear su primer agente o comando personalizado</div>
  <div class="flex items-center gap-3"><span class="text-2xl">🤝</span> Compartir lo que descubran con el equipo</div>
  <div class="flex items-center gap-3"><span class="text-2xl">🎯</span> La práctica constante es lo que marca la diferencia</div>
</v-clicks>
</div>

<!--
Cerrar con acción concreta. Que cada uno elija una herramienta y la pruebe esta semana.
Crear su primer agente o comando. Lo más simple que se les ocurra.
Y compartir con el equipo lo que descubran — así todos crecemos.
Timing: 2 min
-->

---
layout: cover
---

# ¡Gracias por ser parte del AI Laboratory!

## 4 sesiones · Fundamentos → Contexto → Agentes → Herramientas

<div class="mt-8 text-sm opacity-80">Luis Rosales</div>
<div class="text-xs opacity-50">Software Engineer AI</div>

<!--
Cierre emotivo del workshop completo. Agradecer la participación en las 4 sesiones.
Recapitular el viaje: empezamos entendiendo qué es la IA, aprendimos sobre su memoria y lenguaje,
organizamos su trabajo con agentes y skills, y hoy lo vimos todo en acción.
Invitar a seguir explorando y experimentando.
Timing: 1 min
-->
