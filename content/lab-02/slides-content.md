# Contenido de Slides - Lab 02: Contexto, Compactacion y el Lenguaje de la IA

## Slide 1 [cover]
- **Titulo**: AI Laboratory
- **Subtitulo**: Lab 02: Contexto, Compactacion y el Lenguaje de la IA
- **Presentador**: Luis Rosales — Software Engineer AI
- **Detalle**: Serie de 4 laboratorios | Sesion 2 de 4

## Slide 2 [default] (recap)
- **Titulo**: Recap: Lab 01
- **Bullets**:
  - La IA no piensa — predice la siguiente palabra mas probable
  - No inventa — recombina patrones de sus datos de entrenamiento
  - Alucinacion: genera respuestas convincentes pero incorrectas
  - Como el companero sin apuntes: sabe el tema, inventa los detalles
- **Nota presentador**: Recap rapido del Lab 1. Conectar con el tema de hoy: "Si la IA predice, como recuerda lo que le dijiste?"

## Slide 3 [default]
- **Titulo**: Que es el Contexto
- **Bullets**:
  - Toda la informacion disponible en una conversacion
  - La "memoria de trabajo" de la IA — temporal y con limite
  - Se mide en tokens (1 token ~ 0.75 palabras EN, ~0.5 ES)
  - Tiene un limite fijo: la "ventana de contexto"
- **Nota presentador**: El contexto es TODO lo que la IA puede "ver" ahora: tu mensaje, historial, archivos, instrucciones del sistema.

## Slide 4 [default]
- **Titulo**: Analogia: La Pizarra de la IA
- **Bullets**:
  - La IA trabaja con una pizarra de tamano fijo
  - Todo lo que le dices se escribe en la pizarra
  - Cuando se llena, borra lo mas antiguo para seguir
  - Por eso "olvida" el inicio de conversaciones largas
  - Lo mas reciente siempre esta visible
- **Nota presentador**: Analogia clave. Hacer que el grupo visualice una pizarra que se llena y hay que borrar.

## Slide 5 [default]
- **Titulo**: Contexto como Memoria de Trabajo
- **Visual**: Flujo: Tu mensaje + Historial + Archivos + Sistema = Contexto total
- **Bullets**:
  - 100K tokens ~ 75,000 palabras ~ un libro de 300 paginas
  - Mas contexto = la IA "ve" mas, pero no siempre = mejor
- **Nota presentador**: Mostrar los componentes del contexto. Dato importante: mas contexto no garantiza mejores respuestas.

## Slide 6 [comparison]
- **Titulo**: Ventana de Contexto: Claude Code
- **Datos**: Hasta ~1M tokens con Opus 4.6/4.7 (~750,000 palabras, 5x mas que antes). Compactacion en cascada de 5 niveles
- **Bullets**:
  - Ideal para proyectos grandes
  - Lee multiples archivos sin perder el hilo
  - Mantiene decisiones y contexto del proyecto
  - Compactacion automatica al acercarse al limite
- **Nota presentador**: Claude Code tiene una de las ventanas mas grandes. Puede ver un modulo completo de codigo.

## Slide 7 [comparison]
- **Titulo**: Ventana de Contexto: Codex
- **Datos**: ~200-400K tokens (GPT-5.3 Codex ~200K, GPT-5.5 ~400K). Ahora con compactacion server-side
- **Bullets**:
  - CLI local (terminal) + Cloud remoto (contenedores)
  - CLI: interactivo, edita archivos con sandbox de OS
  - Cloud: envia tarea, clona repo, entrega diff o PR
  - Config: AGENTS.md (similar a CLAUDE.md)
- **Nota presentador**: Codex tiene dos modos: CLI interactivo en tu terminal o tareas autonomas en la nube.

## Slide 8 [comparison]
- **Titulo**: Ventana de Contexto: Copilot
- **Datos**: ~8-192K tokens (varia por modo)
- **Bullets**:
  - Inline: autocompletado en archivo actual (~8K)
  - Chat: archivos abiertos + historial (~64-128K)
  - Agent: edita archivos y ejecuta comandos (~192K)
  - Cloud: crea PRs desde issues via GitHub Actions
- **Nota presentador**: Copilot tiene 4 modos, es multi-modelo (Claude, GPT, Gemini) y GitHub limita el contexto nativo de cada modelo.

## Slide 9 [default]
- **Titulo**: Que es la Compactacion
- **Bullets**:
  - Cuando la conversacion se acerca al limite, resume lo antiguo
  - Preserva: decisiones, archivos modificados, contexto del proyecto
  - Pierde: detalle palabra por palabra de mensajes viejos
- **Visual**: Pipeline: Conversacion larga → Compactacion → Sigue trabajando
- **Nota presentador**: La compactacion es como el mecanismo de "supervivencia" de la IA para no quedarse sin espacio.

## Slide 10 [default]
- **Titulo**: Analogia: Resumir Apuntes
- **Bullets**:
  - Tienes un cuaderno de 100 paginas, ya llenaste 90
  - En vez de empezar uno nuevo, resumes las primeras 70 en 10
  - Pierdes algo de detalle, pero mantienes las ideas clave
  - Ahora solo usas 30 paginas (10 resumen + 20 recientes) y tienes 70 libres para seguir
  - La IA puede "olvidar" instrucciones del inicio
  - Solucion: repetir instrucciones importantes o usar archivos de configuracion
- **Nota presentador**: Conectar con la experiencia de todos: resumir apuntes antes de un examen.

## Slide 11 [default]
- **Titulo**: Markdown: El Lenguaje de la IA
- **Bullets**:
  - Lenguaje de formato ligero: # titulos, - listas, ** negritas
  - La IA fue entrenada con MUCHO markdown (GitHub, documentacion)
  - Reconoce la estructura como senales de organizacion
  - Prompt estructurado = respuestas mas precisas
- **Nota presentador**: No necesitan ser expertos en markdown. Con headers y listas ya marcan diferencia.

## Slide 12 [default]
- **Titulo**: Estructura vs Texto Plano
- **Visual**: Comparacion lado a lado — texto plano vs markdown estructurado
- **Ejemplo texto plano**: "Necesito que hagas una funcion que valide emails y que devuelva true o false y que maneje..."
- **Ejemplo markdown**: "## Tarea\nCrear funcion de validacion\n## Requisitos\n- Devolver true/false\n- Validar @\n- Validar dominio"
- **Nota presentador**: Misma informacion, la IA procesa mejor la version estructurada.

## Slide 13 [interactive]
- **Pregunta**: Demo: Markdown vs Texto Plano
- **Nota presentador**: Ejercicio en vivo. Enviar el MISMO pedido en dos formatos y comparar respuestas.

## Slide 14 [interactive]
- **Pregunta**: Que diferencias notaron?
- **Nota presentador**: Discusion grupal. La respuesta markdown fue mas completa? Mas organizada? Cubrio todos los requisitos?

## Slide 15 [section]
- **Titulo**: Resumen Lab 02
- **Bullets**:
  - El contexto es la "pizarra" de la IA — tiene un limite
  - Cada herramienta tiene una ventana de contexto diferente
  - La compactacion resume lo viejo para seguir trabajando
  - Markdown ayuda a la IA a entender mejor tu solicitud
- **Preview**: Proximo Lab: Agentes, Skills y Comandos
