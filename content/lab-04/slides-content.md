# Contenido de Slides - Lab 04: Herramientas en Accion

## Slide 1 [cover]
- **Titulo**: AI Laboratory
- **Subtitulo**: Lab 04: Herramientas en Acción
- **Presentador**: Luis Rosales — Software Engineer AI
- **Detalle**: Serie de 4 laboratorios | Sesion 4 de 4 (Final)

## Slide 2 [default] (recap)
- **Titulo**: Recap: Labs 01, 02 y 03
- **Bullets**:
  - Lab 01: La IA predice, no piensa. Alucina cuando no sabe.
  - Lab 02: El contexto tiene limite. Compactacion resume lo viejo. Markdown mejora prompts.
  - Lab 03: Agentes (empleados), Skills (manuales), Comandos (atajos).
  - Hoy: como las herramientas reales implementan todo esto
- **Nota presentador**: Recap de los 3 labs. Conectar: "Ahora vamos a ver todo esto en accion con herramientas reales."

## Slide 3 [default]
- **Titulo**: Claude Code — Agentes
- **Bullets**:
  - CLI de Anthropic — trabaja directo en tu terminal
  - Agentes definidos como archivos .md en .claude/agents/
  - Frontmatter YAML: nombre, modelo, descripcion
  - Body: instrucciones en markdown con reglas claras
  - Se invocan por nombre o automaticamente segun la tarea
- **Nota presentador**: Claude Code es la herramienta que usamos para generar estas presentaciones.

## Slide 4 [default]
- **Titulo**: Claude Code — Skills y Comandos
- **Bullets**:
  - Skills: archivos SKILL.md en skills/{categoria}/{nombre}/
  - Se cargan bajo demanda por el agente
  - Comandos: archivos .md en .claude/commands/
  - Se invocan con /nombre-comando argumentos
  - Todo es markdown — editable y versionable en git
- **Nota presentador**: Lo clave: todo es archivos .md. No necesitas aprender un lenguaje nuevo.

## Slide 5 [default]
- **Titulo**: Claude Code — En Accion
- **Visual**: Screenshot o ejemplo de terminal con Claude Code
- **Bullets**:
  - Contexto ~200K tokens con compactacion automatica
  - CLAUDE.md como contexto base (siempre cargado)
  - Lee archivos del proyecto bajo demanda
  - Ideal para proyectos grandes con multiples archivos
- **Nota presentador**: Si hay tiempo, mostrar un ejemplo rapido en terminal.

## Slide 6 [default]
- **Titulo**: OpenAI Codex
- **Bullets**:
  - Agente de codigo de OpenAI — ejecuta en sandbox aislado
  - Clona tu repo completo y trabaja de forma autonoma
  - Modelo: GPT-4.1 / o3 / o4-mini
  - Enfoque asincrono: le das la tarea y te entrega el resultado
  - Contexto ~128-200K tokens segun modelo
- **Nota presentador**: Codex es diferente: no es conversacional. Le das una tarea y trabaja solo.

## Slide 7 [default]
- **Titulo**: Gemini CLI
- **Bullets**:
  - Herramienta de Google para interactuar con modelos Gemini
  - Google Agent Development Kit (ADK) para agentes en Python
  - Extensiones y herramientas de funcion integradas
  - Ventana de contexto hasta 1M-2M tokens (la mas grande)
  - Integracion con Google Cloud y servicios Google
- **Nota presentador**: Gemini tiene la ventana mas grande, pero la calidad puede degradar con contextos muy largos.

## Slide 8 [default]
- **Titulo**: GitHub Copilot — Agentes y Extensiones
- **Bullets**:
  - Asistente de codigo integrado en el IDE (VS Code, JetBrains)
  - Modo agente con @workspace, @terminal, @vscode
  - Copilot Extensions: agentes de terceros del marketplace
  - Instruction files: .github/copilot-instructions.md
  - MCP (Model Context Protocol) para herramientas externas
- **Nota presentador**: Copilot es el mas usado en la industria. Su fuerza: integracion directa en el IDE.

## Slide 9 [default]
- **Titulo**: Copilot — Integracion en IDE
- **Bullets**:
  - Inline suggestions: autocompletado en tiempo real (~8K contexto)
  - Chat panel: conversacion sobre tu codigo (~32-64K contexto)
  - Agent mode: ejecuta tareas multi-archivo (~128K contexto)
  - Slash commands: /explain, /fix, /test, /new
  - Menos personalizable que Claude Code, pero mas accesible
- **Nota presentador**: Tres niveles de uso: inline, chat, agent. Cada uno con mas contexto y mas capacidad.

## Slide 10 [comparison]
- **Titulo**: Matriz Comparativa
- **Tabla**:
  | Caracteristica | Claude Code | Codex | Gemini | Copilot |
  | Interfaz | Terminal CLI | Terminal CLI | Terminal/Web | IDE integrado |
  | Agentes custom | Si (.md) | Parcial | Si (ADK) | Parcial |
  | Skills modulares | Si (SKILL.md) | No | Parcial | Parcial |
  | Comandos custom | Si (/commands) | Limitado | Limitado | Parcial |
  | Contexto max | ~200K | ~200K | ~2M | ~128K |
  | Mejor para | Proyectos complejos | Tareas aisladas | Contexto masivo | Desarrollo diario |
- **Nota presentador**: Slide clave. Dar tiempo para que lean y comparen. No hay "mejor herramienta", depende del caso.

## Slide 11 [default]
- **Titulo**: Mejores Practicas para Prompting
- **Bullets**:
  - Estructurar con markdown (headers, listas, bloques de codigo)
  - Ser especifico: que quieres, como lo quieres, restricciones
  - Dar contexto: archivos relevantes, decisiones previas
  - Iterar: refinar el prompt basado en la respuesta
  - Usar templates/comandos para tareas repetitivas
- **Nota presentador**: Tips practicos que aplican a CUALQUIER herramienta de IA, no solo a una.

## Slide 12 [default]
- **Titulo**: Como Evaluar Calidad de Respuestas
- **Bullets**:
  - Verificar datos especificos (fechas, numeros, referencias)
  - Probar el codigo generado — no asumir que funciona
  - Comparar con documentacion oficial
  - Pedir explicacion del razonamiento
  - Desconfiar de respuestas demasiado confiadas sin fuentes
- **Nota presentador**: Recordar la alucinacion del Lab 1. Siempre verificar, nunca confiar ciegamente.

## Slide 13 [default]
- **Titulo**: Construyendo tu Flujo de Trabajo con IA
- **Bullets**:
  - Empezar con UNA herramienta y una tarea especifica
  - Crear agentes para tareas que repites frecuentemente
  - Documentar lo que funciona en archivos de instrucciones
  - Combinar herramientas: Copilot para inline + Claude Code para proyectos
  - La IA es un acelerador, no un reemplazo del proceso
- **Nota presentador**: Consejo practico: no intenten usar todo a la vez. Empiecen con una herramienta, una tarea.

## Slide 14 [default]
- **Titulo**: Etica y Responsabilidad con IA
- **Bullets**:
  - No pegar codigo sensible o credenciales en chats publicos
  - Revisar politicas de privacidad de cada herramienta
  - El codigo generado necesita revision humana siempre
  - Propiedad intelectual: tema legal en evolucion
  - La IA amplifica tus capacidades, la responsabilidad sigue siendo tuya
- **Nota presentador**: Tema importante. La IA es una herramienta poderosa pero la responsabilidad es nuestra.

## Slide 15 [section]
- **Titulo**: Recursos y Proximos Pasos
- **Bullets**:
  - Experimentar con la herramienta que mas les intereso
  - Crear su primer agente o comando personalizado
  - Compartir lo que descubran con el equipo
  - La practica constante es lo que marca la diferencia
- **Nota presentador**: Cerrar con accion concreta. Que cada uno elija una herramienta y la pruebe esta semana.

## Slide 16 [cover]
- **Titulo**: Gracias por ser parte del AI Laboratory
- **Subtitulo**: 4 sesiones · Fundamentos → Contexto → Agentes → Herramientas
- **Nota presentador**: Cierre emotivo. Agradecer la participacion en las 4 sesiones. Invitar a seguir explorando.
