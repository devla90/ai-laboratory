# Guia del Moderador - Lab 03: Agentes, Skills y Comandos

## Informacion General
- **Duracion**: 40 minutos de presentacion + 20 minutos abiertos
- **Audiencia**: Equipo de desarrollo (distintos niveles de experiencia con IA)
- **Objetivo**: Que el equipo comprenda que son los agentes, skills y comandos, como se combinan, y por que permiten usar la IA de forma consistente, rapida y con calidad
- **Materiales**: Presentacion Slidev, conexion a internet para demos opcionales

## Preparacion Previa
- [ ] Tener la presentacion corriendo (`npm run dev:lab03`)
- [ ] Verificar que los slides se ven correctamente en el proyector
- [ ] Tener un ejemplo de agente preparado para mostrar (puede ser el lab-conductor de este mismo proyecto)
- [ ] Tener claro el flujo comando → agente → skills → output para explicarlo con fluidez
- [ ] Preparar un ejemplo simple de comando que el equipo pueda entender sin contexto tecnico profundo
- [ ] Revisar las notas de los Labs 01 y 02 para hacer un recap solido
- [ ] Tener agua disponible (40 min hablando)

---

## Seccion 1: Bienvenida y Portada (1 min)

### Puntos Clave
- Dar la bienvenida al Lab 3
- Recordar que es la tercera de cuatro sesiones
- Hoy entramos en como organizar y especializar la IA

### Guion Sugerido
> "Bienvenidos al Lab 3 del AI Laboratory. Ya estamos en la tercera sesion de cuatro. En los dos primeros labs sentamos las bases: entendimos como funciona la IA por dentro y como comunicarnos con ella. Hoy vamos a dar un paso mas: vamos a ver como organizar a la IA para que trabaje de forma especializada y consistente."

### Transicion
> "Pero primero, hagamos un repaso rapido de lo que vimos en los labs anteriores..."

---

## Seccion 2: Recap Labs 1-2 (2 min, slide 2)

### Puntos Clave
- Lab 01: La IA predice, no piensa. Alucina cuando no tiene informacion suficiente
- Lab 02: El contexto es la "pizarra" de la IA, tiene un limite fijo
- Lab 02: La compactacion resume lo viejo para seguir trabajando sin perder el hilo
- Lab 02: Markdown y estructura mejoran la calidad de las respuestas
- Conectar: ya sabemos como funciona y como hablarle, ahora veamos como organizarla

### Guion Sugerido
> "Repasemos rapidamente. En el Lab 1 aprendimos que la IA no piensa, predice. Y que cuando no tiene informacion, alucina con total confianza. En el Lab 2 vimos que la IA tiene una 'pizarra' con limite fijo — el contexto — y que cuando se llena, usa compactacion para resumir lo viejo y seguir trabajando. Tambien vimos que el lenguaje que usamos importa: Markdown, estructura clara, instrucciones especificas."

> "Hoy vamos a responder una pregunta natural que sigue: si ya sabemos como funciona la IA y como hablarle... como la organizamos para que trabaje de forma consistente y especializada?"

### Posibles Preguntas del Publico
- **"No estuve en el Lab 2, me puedes explicar que es la compactacion?"** → "En resumen: cuando la conversacion con la IA se hace muy larga, la IA resume automaticamente lo anterior para liberar espacio y seguir trabajando. Es como tomar notas resumidas de una reunion larga."

### Transicion
> "Con esa base clara, vamos al primer concepto de hoy: los agentes."

---

## Seccion 3: Que son los Agentes (7 min, slides 3-5)

### Slide 3: Concepto de Agente

#### Puntos Clave
- Un agente es una instancia de IA con un rol, conocimiento y comportamiento definidos
- En vez de usar una IA generica para todo, creas "expertos" para tareas especificas
- Cada agente tiene: nombre, modelo, descripcion, instrucciones, skills
- No es un concepto teorico: se usa hoy en herramientas reales

#### Guion Sugerido
> "Cuando ustedes abren ChatGPT o Claude y le hacen una pregunta, estan hablando con una IA generica. Puede hacer de todo, pero no es experta en nada en particular. Un agente cambia eso."

> "Un agente es una IA a la que le defines un rol especifico: le das un nombre, le dices que modelo usar, le escribes instrucciones claras de que hacer y que no hacer, y le asignas conocimiento especializado. Es como contratar a un empleado y darle una descripcion de cargo bien definida."

#### Datos Extra para Preguntas
- Herramientas como Claude Code, GitHub Copilot y Cursor ya usan agentes internamente
- Un agente no es un modelo diferente: es el mismo modelo pero con instrucciones y contexto especializados
- La diferencia entre un prompt largo y un agente es que el agente es persistente y reutilizable

### Slide 4: Analogia - Empleados Especializados

#### Puntos Clave
- En vez de un empleado que hace todo (y a veces se equivoca por falta de foco)...
- Un arquitecto que solo disena estructuras
- Un auditor de seguridad que solo revisa vulnerabilidades
- Un redactor que solo escribe documentacion
- Cada uno sabe su area, tiene sus herramientas, sigue sus procesos

#### Guion Sugerido
> "Piensen en una empresa. Pueden tener un empleado que hace de todo: disena, revisa codigo, escribe documentacion, hace testing. Puede funcionar, pero es probable que cometa errores porque esta saltando entre tareas muy diferentes."

> "Ahora imaginen que en vez de uno, tienen tres empleados especializados: un arquitecto que solo disena estructuras de software, un auditor de seguridad que solo revisa vulnerabilidades, y un redactor tecnico que solo escribe documentacion. Cada uno sabe exactamente que hacer, tiene sus herramientas y sigue sus procesos."

> "Un agente de IA funciona igual. En vez de pedirle a la IA generica que haga todo, creas agentes especializados. Cada uno con instrucciones claras, conocimiento relevante y un proposito definido."

#### Posibles Preguntas del Publico
- **"Es lo mismo que los GPTs personalizados de ChatGPT?"** → "Es el mismo concepto pero mas flexible. Los GPTs de ChatGPT son una implementacion especifica. El concepto de agente es mas amplio y se aplica en muchas herramientas."
- **"Cuantos agentes se pueden tener?"** → "Los que necesites. Es como preguntar cuantos empleados puede tener una empresa. Depende de las tareas que tengas. Lo importante es que cada agente tenga un proposito claro."

### Slide 5: Ejemplo Real de Agente

#### Puntos Clave
- Ejemplo concreto: agente "code-reviewer"
- Nombre: su identidad dentro del sistema
- Modelo: opus para tareas complejas, sonnet para rapidas
- Instrucciones: que revisar, que ignorar, formato de respuesta
- No necesitan saber la sintaxis exacta, solo el concepto

#### Guion Sugerido
> "Veamos un ejemplo concreto. Imaginen un agente llamado 'code-reviewer'. Su trabajo es revisar codigo. Le definimos: usa el modelo opus porque es una tarea que requiere analisis profundo. Sus instrucciones dicen: revisa seguridad, revisa rendimiento, ignora estilos cosmeticos, responde en formato de lista con severidad."

> "Lo importante aqui no es la sintaxis. Es entender que le estas dando a la IA un rol claro, con reglas claras. Cada vez que lo actives, va a hacer lo mismo, de la misma manera."

#### Posibles Preguntas del Publico
- **"Que diferencia hay entre opus y sonnet?"** → "Son modelos de la misma familia pero con diferentes capacidades. Opus es mas potente y mas lento, ideal para tareas complejas como analisis de codigo. Sonnet es mas rapido y mas economico, ideal para tareas simples como formatear texto."
- **"Esto requiere programar?"** → "Depende de la herramienta. En algunas es pura configuracion con archivos de texto. En otras puede requerir algo de codigo. Veremos ejemplos practicos en el Lab 4."

#### Transicion
> "Ya sabemos que es un agente. Pero un agente sin conocimiento es como un empleado sin capacitacion. Ahi es donde entran los skills."

---

## Seccion 4: Que son los Skills (5 min, slides 6-7)

### Slide 6: Concepto de Skill

#### Puntos Clave
- Un skill es un paquete de conocimiento reutilizable que un agente carga cuando lo necesita
- Modulares: cada skill cubre un tema especifico
- Reutilizables: multiples agentes pueden usar el mismo skill
- Ligeros: se cargan bajo demanda, no todos a la vez
- Versionables: se pueden actualizar sin cambiar el agente

#### Guion Sugerido
> "Un skill es un paquete de conocimiento especializado. Piensen en ello como un modulo de entrenamiento que el agente puede cargar cuando lo necesita."

> "Los skills tienen cuatro caracteristicas clave. Son modulares: cada uno cubre un tema especifico, como 'como generar slides con Slidev' o 'sistema de colores del proyecto'. Son reutilizables: si tengo un skill de colores, cualquier agente que necesite aplicar colores puede usarlo. Son ligeros: el agente no carga todos los skills de una vez, solo toma el que necesita. Y son versionables: puedo actualizar un skill sin tener que cambiar nada en el agente."

#### Datos Extra para Preguntas
- Un skill tipicamente es un archivo de texto con instrucciones, reglas y ejemplos
- El tamano recomendado es menor a 2000 tokens para mantenerlo enfocado
- La ventaja de que sean modulares es que no saturan el contexto del agente

### Slide 7: Analogia - Manuales de Entrenamiento

#### Puntos Clave
- Cada empleado tiene acceso a una estanteria de manuales
- Cuando necesita hacer algo, toma el manual correspondiente
- Lo lee, aplica lo que dice, y lo devuelve
- No memoriza todo: solo carga lo que necesita cuando lo necesita

#### Guion Sugerido
> "Volvamos a la analogia de los empleados. Imaginen que en la oficina hay una estanteria con manuales: 'Manual de estilos de codigo', 'Manual de seguridad', 'Manual de documentacion', 'Manual de testing'."

> "Cuando el auditor de seguridad necesita revisar algo, va a la estanteria, toma el 'Manual de seguridad', lo consulta, aplica lo que dice, y lo devuelve. No necesita memorizar todos los manuales. Solo carga el que necesita en ese momento."

> "Eso es exactamente lo que hace un skill. Es conocimiento que esta disponible, pero solo se carga cuando el agente lo necesita. Asi no desperdiciamos contexto con informacion irrelevante."

#### Posibles Preguntas del Publico
- **"Y si necesito que el agente sepa muchas cosas?"** → "Le asignas multiples skills. El agente carga los que necesita para cada tarea. Si una tarea requiere conocimiento de estilos y de seguridad, carga ambos skills."
- **"Es como darle documentacion a la IA?"** → "Exactamente. La diferencia es que en vez de pegar la documentacion en el chat cada vez, el agente sabe donde encontrarla y la carga automaticamente."

#### Transicion
> "Tenemos agentes que son los expertos, skills que son su conocimiento. Nos falta una pieza: como activamos todo esto de forma simple? Ahi entran los comandos."

---

## Seccion 5: Que son los Comandos (4 min, slides 8-9)

### Slide 8: Concepto de Comando

#### Puntos Clave
- Un comando es un atajo que ejecuta una tarea predefinida con una sola palabra
- Rapidos: una palabra activa multiples pasos
- Consistentes: siempre hacen lo mismo
- Parametrizables: aceptan argumentos (ej: /generate-lab 01)

#### Guion Sugerido
> "El ultimo concepto es el mas simple de entender. Un comando es un atajo. En vez de escribir diez lineas de instrucciones cada vez que quieres hacer algo, defines un comando una vez y lo invocas con una palabra."

> "Por ejemplo, en este mismo proyecto tenemos el comando /generate-lab. En vez de decirle a la IA: 'lee el archivo de contenido del lab 1, lee el skill de Slidev, lee el sistema de colores, genera los slides en formato Markdown con el tema futurista rojo...' simplemente escribo /generate-lab 01. Una linea. El comando se encarga de todo lo demas."

### Slide 9: Analogia - Atajos de Teclado

#### Puntos Clave
- Ctrl+C: una accion simple que ejecuta una operacion compleja por detras
- En vez de seleccionar, ir al menu, buscar copiar... presionas dos teclas
- /generate-lab 01: una linea que ejecuta lectura de archivos, generacion, verificacion
- Mismo concepto: simplicidad para el usuario, complejidad oculta

#### Guion Sugerido
> "Todos usamos Ctrl+C para copiar. Nadie piensa en lo que pasa por detras: seleccionar la memoria, serializar el contenido, guardarlo en el portapapeles del sistema operativo... Solo presionamos dos teclas y funciona."

> "Los comandos de IA funcionan igual. /generate-lab 01 es como Ctrl+C: una accion simple que por detras activa al agente correcto, carga los skills necesarios, lee los archivos de contenido, genera los slides, y los guarda. Todo eso con una linea."

#### Posibles Preguntas del Publico
- **"Donde se definen estos comandos?"** → "Depende de la herramienta. En Claude Code se definen en archivos de configuracion del proyecto. En el Lab 4 veremos ejemplos concretos."
- **"Puedo crear mis propios comandos?"** → "Si, esa es la idea. Un comando es simplemente un atajo a una tarea que haces frecuentemente. Lo defines una vez y lo usas cuantas veces quieras."

#### Transicion
> "Ahora viene la parte mas interesante: como se conectan estos tres conceptos."

---

## Seccion 6: Como se Combinan (2.5 min, slide 10)

### Puntos Clave
- Flujo completo: Comando → Agente → Skills → Output
- Ejemplo concreto con /generate-lab 01
- El comando activa al agente lab-conductor
- El agente carga los skills que necesita: slidev-futuristic, color-system, ai-fundamentals
- El output es una presentacion Slidev completa

### Guion Sugerido
> "Veamos como se conecta todo con un ejemplo real de este mismo proyecto."

> "Cuando alguien escribe /generate-lab 01, pasa lo siguiente: el comando activa al agente llamado lab-conductor. Este agente sabe que para generar un lab necesita cierto conocimiento, entonces carga tres skills: uno que le dice como hacer slides con Slidev, otro que le dice que colores usar, y otro que tiene el contenido de IA del lab. Con todo eso, genera la presentacion completa."

> "Comando, agente, skills, output. Es una cadena donde cada pieza tiene su rol. El comando es el trigger, el agente es el ejecutor, los skills son el conocimiento, y el output es el resultado."

#### Posibles Preguntas del Publico
- **"Y si el agente necesita un skill que no tiene?"** → "Buena pregunta. Si un skill no esta definido, el agente trabaja con su conocimiento general, que puede ser incompleto. Por eso es importante definir los skills que cada agente necesita."
- **"Esto es especifico de Claude Code?"** → "El concepto es universal: agentes especializados con conocimiento modular activados por atajos. La implementacion varia segun la herramienta. En el Lab 4 veremos como se aplica en Claude Code, Codex y Copilot."

### Transicion
> "Ya entendemos el que y el como. Ahora veamos el por que. Que beneficios reales nos da trabajar de esta manera?"

---

## Seccion 7: Beneficios Reales (7 min, slides 11-13)

### Slide 11: Consistencia

#### Puntos Clave
- Sin agentes: la calidad varia segun como lo pidas. Un dia lo describes bien, otro dia se te olvida algo
- Con agentes: el resultado sigue las mismas reglas siempre
- Mismo formato, mismo estilo, mismas verificaciones
- No depende de "acordarte" de incluir todo en el prompt

#### Guion Sugerido
> "El primer beneficio grande es la consistencia. Piensen en cuantas veces le han pedido algo a la IA y el resultado vario segun como lo pidieron. Un dia escribes un prompt detallado y el resultado es bueno. Otro dia estas apurado, escribes algo rapido, y el resultado es mediocre."

> "Con agentes, eso se acaba. Las instrucciones estan definidas una vez. No importa quien active el agente ni a que hora. El agente siempre sigue las mismas reglas, aplica el mismo formato, hace las mismas verificaciones. La calidad ya no depende de tu memoria."

### Slide 12: Velocidad y Calidad

#### Puntos Clave
- Sin comandos: escribir 10 lineas de instrucciones cada vez
- Con comandos: /generate-lab 01 y listo
- Sin skills: la IA usa su conocimiento general (a veces incompleto o desactualizado)
- Con skills: conocimiento especifico y actualizado

#### Guion Sugerido
> "El segundo beneficio es velocidad. Imaginen que cada vez que quieren generar un lab tienen que escribir todas las instrucciones desde cero: el formato, los colores, la estructura, el tono, el nivel de detalle... Son facilmente 10 o 15 lineas de instrucciones. Con un comando, todo eso se reduce a una linea."

> "Y el tercer beneficio es calidad. Cuando la IA trabaja con su conocimiento general, a veces le falta contexto especifico de tu proyecto. Los skills le dan ese conocimiento: sabe exactamente que colores usar, que formato seguir, que convenciones respetar. El resultado es mejor porque tiene mejor informacion."

### Slide 13: Ejemplos del Equipo

#### Puntos Clave
- Generar presentaciones con estilo consistente (/generate-lab)
- Crear guias del moderador alineadas al contenido (/generate-guide)
- Revisar codigo con criterios especificos (agente code-reviewer)
- Documentar con formato y nivel de detalle estandar
- Escalar: creas una vez, usas infinitas veces

#### Guion Sugerido
> "Veamos ejemplos concretos. Este mismo proyecto que estamos usando para los labs usa agentes, skills y comandos. Las presentaciones se generan con /generate-lab: mismo estilo, mismos colores, misma estructura. Las guias del moderador se generan con /generate-guide: mismo formato, mismo nivel de detalle."

> "Pero esto no se limita a presentaciones. Imaginen un agente code-reviewer que revisa PRs con los mismos criterios siempre. O un agente que genera documentacion con el formato estandar del equipo. Lo creas una vez y lo usas infinitas veces. Esa es la escalabilidad."

#### Posibles Preguntas del Publico
- **"Cuanto tiempo toma crear un agente?"** → "La configuracion inicial puede tomar de 30 minutos a un par de horas, dependiendo de la complejidad. Pero ese tiempo se recupera rapidamente: si usas el agente 10 veces y cada uso te ahorra 15 minutos de instrucciones... las cuentas salen solas."
- **"Se puede compartir agentes entre el equipo?"** → "Si, de hecho esa es una de las grandes ventajas. Un agente se define en archivos de texto que van en el repositorio. Todo el equipo puede usarlo y mejorarlo."
- **"Que pasa si el agente hace algo mal?"** → "Lo corriges en las instrucciones o en los skills, y la correccion aplica para todos los usos futuros. Es como actualizar un manual: una vez actualizado, todos los que lo consulten tendran la version correcta."

#### Transicion
> "Ahora quiero que ustedes pongan esto en practica. Vamos a hacer un ejercicio rapido..."

---

## Seccion 8: Ejercicio Grupal (6 min, slides 14-15)

### Slide 14: Disena tu Agente - Instrucciones (3 min)

#### Puntos Clave
- Ejercicio individual o en parejas
- Pensar en un agente que les seria util en su trabajo diario
- Definir tres cosas: nombre del agente, que hace, que conocimiento necesita (skills)
- No hay respuestas correctas o incorrectas

#### Guion Sugerido
> "Quiero que piensen en un agente que les seria util en su dia a dia. Puede ser para cualquier tarea que hagan frecuentemente: revisar codigo, escribir tests, documentar, planificar sprints, responder correos... lo que sea."

> "Definan tres cosas: uno, un nombre para el agente. Dos, que hace exactamente. Y tres, que conocimiento necesitaria — sus skills."

> "Por ejemplo, yo podria definir un agente llamado 'pr-reviewer'. Que hace: revisa pull requests buscando problemas de seguridad, rendimiento y legibilidad. Que conocimiento necesita: las guias de estilo del equipo, las reglas de seguridad de la empresa, y los patrones de diseno que usamos."

> "Tienen dos o tres minutos. Pueden pensarlo solos o con la persona de al lado."

#### Si nadie arranca
> "Piensen en algo que hagan todas las semanas y que les gustaria que fuera mas rapido o mas consistente. Ese es un buen candidato para un agente."

### Slide 15: Puesta en Comun (3 min)

#### Puntos Clave
- Pedir a 3-4 personas que compartan su agente
- Para cada agente compartido, preguntar: que skills necesitaria? que comando lo activaria?
- Conectar las respuestas con los conceptos del lab

#### Guion Sugerido
> "Quien quiere compartir su agente?"

Para cada persona que comparta:
> "Buen ejemplo. Ahora pensemos: que skills necesitaria ese agente? Y que comando lo activaria?"

Ejemplo de como guiar la discusion:
- Si alguien dice "agente de testing" → "Que skills necesitaria? Tal vez uno con los patrones de testing del equipo, otro con la estructura de archivos del proyecto. Y el comando podria ser /generate-tests seguido del nombre del archivo."
- Si alguien dice "agente de documentacion" → "Los skills podrian ser: las convenciones de documentacion del equipo, los templates de README, y las guias de estilo. Comando: /document seguido del nombre del modulo."

#### Si nadie quiere compartir
> "Dejame dar otro ejemplo. Imaginen un agente llamado 'standup-helper'. Su trabajo: preparar un resumen de lo que hiciste ayer basado en tus commits de Git. Skills: formato de standup del equipo, acceso al historial de Git. Comando: /standup. Listo, tu reporte de standup en 5 segundos."

### Transicion
> "Excelente. Ya ven como los conceptos se aplican directamente a su trabajo. Vamos a cerrar con un resumen..."

---

## Seccion 9: Resumen y Cierre (3 min, slide 16)

### Puntos Clave del Resumen
1. Agentes: IA especializada con rol definido (como empleados especializados)
2. Skills: conocimiento modular y reutilizable (como manuales de entrenamiento)
3. Comandos: atajos que ejecutan tareas complejas (como Ctrl+C)
4. Juntos: consistencia, velocidad y calidad
5. Preview del Lab 4: veremos herramientas reales — Claude Code, Codex, Copilot

### Guion Sugerido
> "Recapitulemos lo que vimos hoy. Tres conceptos que se construyen uno sobre otro."

> "Agentes: en vez de una IA generica, creamos expertos con roles definidos. Como empleados especializados que saben exactamente que hacer."

> "Skills: el conocimiento modular que los agentes cargan cuando lo necesitan. Como manuales de entrenamiento que se consultan bajo demanda."

> "Comandos: atajos que activan todo con una palabra. Como Ctrl+C: simplicidad para el usuario, complejidad oculta."

> "Juntos, nos dan tres cosas que antes no teniamos: consistencia en los resultados, velocidad en la ejecucion, y calidad en el output."

> "En el proximo lab, el Lab 4, vamos a poner todo esto en practica. Vamos a ver herramientas reales: Claude Code, Codex y Copilot. Como se usan, en que se diferencian, y cual conviene para cada caso."

> "Alguna pregunta antes de pasar a la parte abierta?"

---

## Seccion 10: Tiempo Abierto (20 min)

### Dinamica Sugerida
Los 20 minutos restantes son flexibles. Algunas opciones:

#### Opcion A: Preguntas y Respuestas Libre
- Abrir el espacio para cualquier pregunta del equipo
- Mantener las respuestas concisas para cubrir mas preguntas
- Si una pregunta es muy especifica, ofrecer responderla despues de la sesion

#### Opcion B: Demo en Vivo de un Agente
- Abrir Claude Code o una herramienta similar en pantalla
- Mostrar como se ve un archivo de configuracion de agente
- Ejecutar un comando en vivo y mostrar como el agente carga skills y genera output
- Ejemplo: ejecutar /generate-lab o /generate-guide y explicar lo que pasa paso a paso

#### Opcion C: Ejercicio Extendido
- Retomar el ejercicio de "Disena tu agente" con mas profundidad
- Pedir que definan: instrucciones del agente (3-5 reglas), 2-3 skills con su contenido resumido, y un comando con sus parametros
- Puesta en comun mas detallada

#### Opcion D: Combinacion
- 10 min de preguntas y respuestas
- 10 min de demo en vivo

### Preguntas Frecuentes que Pueden Surgir

**"Necesito saber programar para crear agentes?"**
> "No necesariamente. Muchas herramientas permiten definir agentes con archivos de texto plano, sin codigo. Lo que necesitas es claridad sobre que quieres que haga el agente. La habilidad tecnica es secundaria al pensamiento estrategico de como organizar las tareas."

**"Cual es la diferencia entre un prompt largo y un agente?"**
> "Un prompt largo se escribe una vez y se pierde. Un agente es persistente: lo defines una vez en un archivo y esta disponible siempre. Ademas, el agente puede cargar skills bajo demanda, lo que un prompt no puede hacer. Es la diferencia entre dar instrucciones verbales cada vez versus escribir una descripcion de cargo."

**"Esto funciona con cualquier IA?"**
> "El concepto de agentes, skills y comandos se aplica en cualquier IA. La implementacion varia: Claude Code tiene su forma de definir agentes, GitHub Copilot tiene la suya, y herramientas como Cursor o Windsurf tienen la suya. En el Lab 4 veremos las diferencias."

**"Cuanto contexto consume un skill?"**
> "Depende del tamano del skill. La recomendacion es mantener cada skill en menos de 2000 tokens, que es aproximadamente una pagina de texto. Asi no saturas el contexto del agente. Si un tema necesita mas, es mejor dividirlo en multiples skills."

**"Se pueden encadenar agentes?"**
> "Si, es lo que se llama 'multi-agent' o agentes en cadena. Un agente puede activar a otro cuando termina su parte. Por ejemplo, un agente genera codigo y otro lo revisa automaticamente. Es un tema mas avanzado que pueden explorar despues de dominar los fundamentos."

**"Como se que mi agente esta bien definido?"**
> "Una buena prueba es: si le das la descripcion del agente a un humano, sabria exactamente que hacer? Si si, el agente esta bien definido. Si hay ambiguedad, necesitas ser mas especifico en las instrucciones."

---

## Notas Finales para el Moderador

### Ritmo y Tono
- Mantener un tono conversacional, no de catedra
- Este lab tiene muchos conceptos nuevos pero interconectados. Ir con calma para que se entienda cada uno antes de pasar al siguiente
- Las analogias son clave en este lab: empleados, manuales, atajos. Hacer pausas para que el grupo conecte la analogia con el concepto
- No apurarse con el ejercicio grupal. Es donde el grupo realmente internaliza los conceptos
- Si alguien hace una pregunta sobre herramientas especificas, redirigir al Lab 4: "Excelente pregunta, justo eso lo vamos a cubrir en el proximo lab"

### Si te quedas sin tiempo
- Prioriza las secciones de concepto + analogia (secciones 3-5): son el corazon del lab
- La seccion de beneficios (seccion 7) se puede resumir verbalmente en 2 minutos
- El ejercicio grupal (seccion 8) se puede reducir: solo instrucciones y 1-2 comparticiones
- El resumen se puede hacer verbalmente sin slide
- Nunca sacrifiques el tiempo abierto: es donde el equipo mas aprende

### Si te sobra tiempo
- Profundiza en el ejercicio grupal: pide mas detalle en los skills y comandos
- Muestra un ejemplo real de un archivo de configuracion de agente
- Pregunta: "Si pudieran automatizar una tarea de su semana con un agente, cual seria?"
- Explora el concepto de multi-agentes: como un agente puede llamar a otro
- Comparte una experiencia personal de como los agentes te han ahorrado tiempo

### Errores comunes a evitar
- No decir "la IA piensa" o "la IA entiende" → decir "la IA genera" o "la IA ejecuta"
- No hacer que parezca que crear agentes es complicado → enfocarse en que es configuracion, no programacion
- No prometer que los agentes eliminan errores completamente → decir que los reducen y los hacen consistentes
- No entrar en detalles de implementacion especifica de una herramienta → eso es para el Lab 4
- No saltar entre conceptos → presentar agentes, luego skills, luego comandos, en orden
- No usar terminologia sin explicar → si mencionas "token", "contexto" o "modelo", conectar con lo visto en labs anteriores

### Distribucion del Tiempo - Resumen Rapido

| Seccion | Duracion | Acumulado |
|---------|----------|-----------|
| Bienvenida | 1 min | 1 min |
| Recap Labs 1-2 | 2 min | 3 min |
| Que son los Agentes | 7 min | 10 min |
| Que son los Skills | 5 min | 15 min |
| Que son los Comandos | 4 min | 19 min |
| Como se Combinan | 2.5 min | 21.5 min |
| Beneficios Reales | 7 min | 28.5 min |
| Ejercicio Grupal | 6 min | 34.5 min |
| Resumen y cierre | 3 min | 37.5 min |
| Margen/transiciones | 2.5 min | 40 min |
| **Tiempo abierto** | **20 min** | **60 min** |

### Checklist Post-Sesion
- [ ] Anotar los agentes que propuso el equipo en el ejercicio grupal (pueden convertirse en agentes reales)
- [ ] Registrar las preguntas que surgieron para preparar el Lab 4
- [ ] Identificar quienes mostraron mas interes en crear sus propios agentes
- [ ] Anotar si el nivel de abstraccion fue correcto o si necesitan mas ejemplos practicos en el Lab 4
- [ ] Evaluar si el ejercicio grupal funciono bien o si necesita mas tiempo/estructura
