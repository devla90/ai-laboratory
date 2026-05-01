# Contenido de Slides - Lab 03: Agentes, Skills y Comandos

## Slide 1 [cover]
- **Titulo**: AI Laboratory
- **Subtitulo**: Lab 03: Agentes, Skills y Comandos
- **Presentador**: Luis Rosales — Software Engineer AI
- **Detalle**: Serie de 4 laboratorios | Sesion 3 de 4

## Slide 2 [default] (recap)
- **Titulo**: Recap: Labs 01 y 02
- **Bullets**:
  - Lab 01: La IA predice, no piensa. Alucina cuando no sabe.
  - Lab 02: El contexto es la "pizarra" con limite fijo
  - Lab 02: La compactacion resume lo viejo para seguir trabajando
  - Lab 02: Markdown ayuda a la IA a entender mejor tu solicitud
  - Hoy: como hacer que la IA trabaje de forma especializada y consistente
- **Nota presentador**: Recap breve de los dos labs anteriores. Conectar: "Ya sabemos como funciona la IA y como hablarle. Ahora veamos como organizarla."

## Slide 3 [default]
- **Titulo**: Que son los Agentes
- **Bullets**:
  - Instancia de IA con un rol, conocimiento y comportamiento definidos
  - En vez de una IA generica, creas "expertos" para tareas especificas
  - Cada agente tiene: nombre, modelo, descripcion, instrucciones, skills
  - Saben exactamente que hacer porque tienen instrucciones claras
- **Nota presentador**: Un agente es como darle a la IA un puesto de trabajo con descripcion de cargo.

## Slide 4 [default]
- **Titulo**: Analogia: Empleados Especializados
- **Visual**: Tres tarjetas de empleados (arquitecto, auditor, redactor)
- **Bullets**:
  - En vez de UN empleado que hace todo (y a veces se equivoca)...
  - Un arquitecto que solo disena estructuras
  - Un auditor de seguridad que solo revisa vulnerabilidades
  - Un redactor que solo escribe documentacion
  - Cada uno sabe su area — un agente funciona igual
- **Nota presentador**: La analogia de empleados es la mas intuitiva. Que el equipo piense en roles de su dia a dia.

## Slide 5 [default]
- **Titulo**: Agentes — Ejemplo Real
- **Visual**: Ejemplo de definicion de un agente (nombre, modelo, instrucciones)
- **Bullets**:
  - Nombre: "code-reviewer" — su identidad
  - Modelo: opus para tareas complejas, sonnet para rapidas
  - Instrucciones: que revisar, que ignorar, formato de respuesta
  - Se activa automaticamente segun el tipo de tarea
- **Nota presentador**: Mostrar un ejemplo concreto. No necesitan saber la sintaxis, solo el concepto.

## Slide 6 [default]
- **Titulo**: Que son los Skills
- **Bullets**:
  - Paquete de conocimiento reutilizable que un agente carga cuando lo necesita
  - Modulares: cada skill cubre un tema especifico
  - Reutilizables: multiples agentes pueden usar el mismo skill
  - Ligeros: se cargan bajo demanda, no todos a la vez
  - Versionables: se actualizan sin cambiar el agente
- **Nota presentador**: Los skills son la "base de conocimiento" modular. Un agente sin skills es como un empleado sin capacitacion.

## Slide 7 [default]
- **Titulo**: Analogia: Manuales de Entrenamiento
- **Visual**: Estanteria con manuales etiquetados
- **Bullets**:
  - Cada empleado tiene acceso a una estanteria de manuales
  - Cuando necesita hacer algo, toma el manual correspondiente
  - Lo lee, aplica lo que dice, y lo devuelve
  - No memoriza todo — solo carga lo que necesita cuando lo necesita
- **Nota presentador**: Como en un trabajo real: nadie memoriza todos los procesos. Consultas el manual cuando lo necesitas.

## Slide 8 [default]
- **Titulo**: Que son los Comandos
- **Bullets**:
  - Atajo que ejecuta una tarea predefinida con una sola palabra
  - Rapidos: una palabra activa multiples pasos
  - Consistentes: siempre hacen lo mismo
  - Parametrizables: aceptan argumentos (ej: /generate-lab 01)
- **Nota presentador**: Los comandos son la interfaz simple. El usuario no necesita saber que pasa por detras.

## Slide 9 [default]
- **Titulo**: Analogia: Atajos de Teclado
- **Bullets**:
  - Ctrl+C: una accion simple, operacion compleja por detras
  - En vez de seleccionar → menu → buscar copiar... presionas dos teclas
  - /generate-lab 01: una linea que ejecuta lectura de archivos, generacion, verificacion
  - Mismo concepto: simplicidad para el usuario, complejidad oculta
- **Nota presentador**: Todos usan Ctrl+C sin pensar en lo que hace por detras. Los comandos de IA funcionan igual.

## Slide 10 [default]
- **Titulo**: Como se Combinan
- **Visual**: Diagrama flujo: Comando → Agente → Skills → Output
- **Ejemplo**:
  - Comando: /generate-lab 01
  - Agente: lab-conductor (sabe como generar labs)
  - Skills: slidev-futuristic + color-system + ai-fundamentals
  - Output: presentacion Slidev completa
- **Nota presentador**: Aqui es donde todo se conecta. El comando activa al agente, que carga los skills necesarios.

## Slide 11 [default]
- **Titulo**: Beneficio: Consistencia
- **Bullets**:
  - Sin agentes: la calidad varia segun como lo pidas
  - Con agentes: el resultado sigue las mismas reglas siempre
  - Mismo formato, mismo estilo, mismas verificaciones
  - No depende de "acordarte" de incluir todo en el prompt
- **Nota presentador**: La consistencia es el primer gran beneficio. Ya no depende de tu memoria.

## Slide 12 [default]
- **Titulo**: Beneficios: Velocidad y Calidad
- **Bullets**:
  - Sin comandos: escribir 10 lineas de instrucciones cada vez
  - Con comandos: /generate-lab 01 y listo
  - Sin skills: la IA usa su conocimiento general (a veces incompleto)
  - Con skills: conocimiento especifico y actualizado
- **Nota presentador**: Velocidad + calidad. Lo que antes tomaba 10 minutos de instrucciones, ahora es un comando.

## Slide 13 [default]
- **Titulo**: Ejemplos del Equipo
- **Bullets**:
  - Generar presentaciones con estilo consistente (/generate-lab)
  - Crear guias del moderador alineadas al contenido (/generate-guide)
  - Revisar codigo con criterios especificos (agente code-reviewer)
  - Documentar con formato y nivel de detalle estandar
  - Escalar: creas una vez, usas infinitas veces
- **Nota presentador**: Ejemplos concretos de este mismo proyecto. Mostrar como se aplica en nuestro contexto.

## Slide 14 [interactive]
- **Pregunta**: Ejercicio: Disena tu Agente
- **Instrucciones**: Pensar en un agente que les seria util en su trabajo diario. Definir: nombre, que hace, que conocimiento necesita.
- **Nota presentador**: Dar 2-3 min para pensar. Pueden hacerlo en parejas. Ejemplo para arrancar: "agente de PR reviews".

## Slide 15 [interactive]
- **Pregunta**: Puesta en Comun
- **Nota presentador**: Que 3-4 personas compartan su agente. Discutir: que skills necesitaria? que comandos lo activarian?

## Slide 16 [section]
- **Titulo**: Resumen Lab 03
- **Bullets**:
  - Agentes: IA especializada con rol definido (empleados)
  - Skills: conocimiento modular y reutilizable (manuales)
  - Comandos: atajos que ejecutan tareas complejas (Ctrl+C)
  - Juntos: consistencia, velocidad y calidad
- **Preview**: Proximo Lab: Herramientas en Accion — Claude Code, Codex, Copilot
