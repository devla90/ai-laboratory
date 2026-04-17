---
name: ai-tools-comparison
description: >
  Comparativa detallada de Claude Code, Codex, Gemini CLI y GitHub Copilot.
  Cómo cada herramienta implementa agentes, skills y comandos. Para Lab 4.
user-invocable: true
disable-model-invocation: false
---

# AI Tools Comparison - Conocimiento para Lab 4

## Cuando se Activa
- Generar contenido del Lab 4
- Comparar herramientas de IA
- Explicar cómo cada herramienta implementa agentes/skills

## Claude Code

### Qué es
CLI (herramienta de terminal) de Anthropic que funciona como un agente de desarrollo. Trabaja directamente en tu código desde la terminal.

### Agentes
- Archivos `.md` en `.claude/agents/`
- Frontmatter YAML: name, description, model, color
- Body: prompt del sistema en markdown
- Se invocan por nombre o automáticamente según la tarea

### Skills
- Archivos `SKILL.md` en `skills/{categoria}/{nombre}/`
- Frontmatter: name, description, user-invocable
- Carga bajo demanda por el agente
- Se pueden invocar directamente con /nombre-del-skill

### Comandos
- Archivos `.md` en `.claude/commands/`
- Se invocan con `/nombre-comando argumentos`
- Aceptan `$ARGUMENTS` como parámetro
- Ejecutan flujos multi-paso

### Contexto
- ~200K tokens de ventana
- Compactación automática
- CLAUDE.md se carga siempre como contexto base
- Lee archivos del proyecto bajo demanda

## OpenAI Codex (CLI)

### Qué es
Agente de código de OpenAI que ejecuta tareas en un sandbox. Optimizado para escritura y ejecución de código.

### Agentes
- Configurados mediante instrucciones del sistema
- Archivo `AGENTS.md` o similar en el proyecto
- Menos estructura formal que Claude Code
- Modelo: GPT-4.1 / o3 / o4-mini

### Skills/Instrucciones
- Se definen en archivos de instrucciones del proyecto
- No tiene un sistema de skills tan modular como Claude Code
- Las instrucciones se cargan completas al inicio

### Comandos
- Interfaz basada en prompts
- Menos sistema de comandos predefinidos
- Se integra con herramientas de terminal

### Contexto
- ~128K-200K tokens según modelo
- Ejecución en sandbox aislado
- Puede ejecutar código para verificar sus respuestas

## Gemini CLI / Google AI Studio

### Qué es
Herramienta de Google para interactuar con modelos Gemini desde terminal o IDE.

### Agentes
- Google Agent Development Kit (ADK)
- Agentes definidos en Python o configuración
- Multi-agent orchestration
- Integración con servicios de Google

### Skills/Extensions
- Extensiones y herramientas de función
- Google Search, Code Execution integrados
- Menos enfocado en archivos .md como skills

### Comandos
- Interfaz de chat en terminal
- Integración con Google Cloud

### Contexto
- Hasta 1M-2M tokens (Gemini 1.5/2.0)
- La ventana más grande disponible
- Pero la calidad puede degradar con contextos muy largos

## GitHub Copilot

### Qué es
Asistente de código integrado en el IDE (VS Code, JetBrains). El más utilizado en la industria.

### Agentes (Agent Mode)
- Modo agente en VS Code Copilot Chat
- Agentes predefinidos: @workspace, @terminal, @vscode
- Copilot Extensions: agentes de terceros
- Instruction files: `.github/copilot-instructions.md`

### Skills/Extensions
- Copilot Extensions del marketplace
- Pueden leer archivos, ejecutar comandos
- Menos granulares que los skills de Claude Code
- MCP (Model Context Protocol) para herramientas externas

### Comandos
- Slash commands en chat: /explain, /fix, /test, /new
- Custom instructions por proyecto
- Menos personalizable que Claude Code

### Contexto
- ~8K tokens (inline suggestions)
- ~64K tokens (chat mode)
- ~128K tokens (agent mode con workspace)
- Significativamente menor que Claude Code o Gemini

## Matriz Comparativa

| Característica | Claude Code | Codex | Gemini | Copilot |
|---------------|-------------|-------|--------|---------|
| Interfaz | Terminal CLI | Terminal CLI | Terminal/Web | IDE integrado |
| Agentes custom | ✅ .md files | ⚠️ Instrucciones | ✅ ADK/Python | ⚠️ Instructions |
| Skills modulares | ✅ SKILL.md | ❌ No modular | ⚠️ Extensions | ⚠️ Extensions |
| Comandos custom | ✅ /commands | ❌ Limitado | ❌ Limitado | ⚠️ Slash cmds |
| Contexto máx | ~200K | ~200K | ~2M | ~128K |
| Edición directa | ✅ Archivos | ✅ Sandbox | ✅ Archivos | ✅ IDE |
| Ejecución código | ✅ Terminal | ✅ Sandbox | ✅ Terminal | ✅ Terminal |
| Mejor para | Proyectos complejos | Tareas aisladas | Contexto masivo | Desarrollo diario |
