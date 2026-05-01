# Guia del Moderador - Lab 04: Herramientas en Accion

## Informacion General
- **Duracion**: 40 minutos de presentacion + 20 minutos abiertos
- **Audiencia**: Equipo de desarrollo (distintos niveles de experiencia con IA)
- **Objetivo**: Que el equipo conozca las herramientas de IA disponibles, entienda sus diferencias, y salga con un plan concreto para integrarlas en su flujo de trabajo
- **Materiales**: Presentacion Slidev, conexion a internet para demos opcionales, terminal con Claude Code instalado
- **Nota especial**: Este es el ultimo lab del workshop. El cierre debe sentirse como una culminacion, no como "un lab mas".

## Preparacion Previa
- [ ] Tener la presentacion corriendo (`npm run dev:lab04`)
- [ ] Verificar que los slides se ven correctamente en el proyector
- [ ] Tener Claude Code instalado y funcionando en la terminal para demo en vivo
- [ ] Tener VS Code con Copilot abierto como respaldo para mostrar
- [ ] Imprimir o tener visible la tabla comparativa (slide 10) para referencia rapida
- [ ] Preparar un ejemplo simple de agente .md y un SKILL.md para mostrar
- [ ] Tener agua disponible (40 min hablando)
- [ ] Preparar unas palabras de cierre del workshop (este es el ultimo lab)

---

## Seccion 1: Bienvenida y Portada (1 min)

### Puntos Clave
- Dar la bienvenida al ultimo lab del AI Laboratory
- Generar expectativa: hoy toca la parte practica
- Recordar que esta es la sesion 4 de 4 (final)

### Guion Sugerido
> "Bienvenidos al Lab 4, el ultimo del AI Laboratory. Hoy es el dia que muchos estaban esperando: vamos a ver herramientas reales en accion. Todo lo que aprendimos en los tres labs anteriores, fundamentamentos, contexto, agentes y skills, hoy lo vamos a ver implementado en herramientas que pueden usar a partir de manana."

### Transicion
> "Pero antes de meternos de lleno, hagamos un repaso rapido de lo que ya sabemos..."

---

## Seccion 2: Recap Labs 1-3 (2 min, slide 2)

### Puntos Clave
- Lab 01: La IA predice, no piensa. Alucina cuando no sabe.
- Lab 02: El contexto tiene limite. La compactacion resume lo viejo. Markdown mejora los prompts.
- Lab 03: Agentes (empleados especializados), Skills (manuales), Comandos (atajos).
- Conectar todo: hoy vemos como las herramientas implementan estos conceptos

### Guion Sugerido
> "Rapido recap. En el Lab 1 aprendimos que la IA predice, no piensa. Y que cuando no sabe, alucina con total confianza. En el Lab 2 vimos que el contexto tiene un limite fisico, que la compactacion es como resumir tus apuntes viejos, y que el markdown es el lenguaje que la IA entiende mejor. En el Lab 3 hablamos de agentes como empleados especializados, skills como manuales de entrenamiento, y comandos como atajos."

> "Hoy vamos a ver como cuatro herramientas reales implementan todo esto. Vamos a comparar, vamos a ver ejemplos, y al final van a tener claro cual les conviene para su dia a dia."

### Posibles Preguntas del Publico
- **"Puedes repetir que era la compactacion?"** -> "Claro. Imagina que tienes una conversacion muy larga con la IA y se acerca al limite de contexto. La compactacion toma lo viejo y lo resume para hacer espacio. Como cuando resumes tus apuntes de 10 paginas en 2 para el examen."

### Transicion
> "Empecemos con la herramienta que conozco mas de cerca, porque literalmente la usamos para crear esta presentacion..."

---

## Seccion 3: Claude Code (7 min, slides 3-5)

### Slide 3: Claude Code - Agentes (2.5 min)

#### Puntos Clave
- CLI de Anthropic que trabaja directo en la terminal
- Los agentes son archivos .md en `.claude/agents/`
- Cada agente tiene frontmatter YAML (nombre, modelo, descripcion) y un body con instrucciones en markdown
- Se invocan por nombre o automaticamente segun la tarea
- Concepto clave: TODO es archivos markdown

#### Guion Sugerido
> "Claude Code es una herramienta de terminal de Anthropic. No es un chat en el navegador, es un agente que vive en tu terminal y trabaja directamente con tu codigo."

> "Lo interesante de Claude Code es como implementa los agentes que vimos en el Lab 3. Un agente es simplemente un archivo .md dentro de la carpeta .claude/agents/. Tiene un encabezado YAML con el nombre, el modelo y la descripcion, y despues el cuerpo del archivo son las instrucciones en markdown. Asi de simple."

> "De hecho, esta presentacion fue generada por un agente de Claude Code llamado lab-conductor. Es un archivo .md que le dice a Claude como crear slides, que formato usar, que colores, que tono. Todo definido en texto plano."

#### Datos Extra para Preguntas
- Claude Code usa el modelo Claude (Opus, Sonnet, o Haiku segun la configuracion del agente)
- Los agentes pueden tener diferentes modelos segun la complejidad de la tarea
- Se pueden tener multiples agentes para diferentes propositos en el mismo proyecto

### Slide 4: Claude Code - Skills y Comandos (2.5 min)

#### Puntos Clave
- Skills: archivos SKILL.md organizados en `skills/{categoria}/{nombre}/`
- Se cargan bajo demanda (el agente los lee cuando los necesita)
- Comandos: archivos .md en `.claude/commands/`
- Se invocan con `/nombre-comando argumentos`
- Todo es markdown, editable y versionable en git

#### Guion Sugerido
> "Los skills en Claude Code son exactamente lo que describimos en el Lab 3: manuales de entrenamiento. Son archivos SKILL.md organizados en carpetas por categoria. El agente no los carga todos de una vez, los lee bajo demanda cuando necesita ese conocimiento especifico."

> "Los comandos son todavia mas simples. Son archivos .md en .claude/commands/ y los invocas con slash y el nombre. Por ejemplo, /generate-lab 04 es el comando que genera los slides de este lab."

> "Y aqui esta lo poderoso: todo es texto plano. Puedes versionarlo en git, puedes hacer pull request de un skill nuevo, puedes revisar en el diff que cambio en un agente. No hay configuraciones ocultas ni interfaces graficas. Es markdown."

### Slide 5: Claude Code - En Accion (2 min)

#### Puntos Clave
- Contexto de ~200K tokens con compactacion automatica
- CLAUDE.md como contexto base (siempre cargado)
- Lee archivos del proyecto bajo demanda
- Ideal para proyectos grandes con multiples archivos

#### Guion Sugerido
> "En la practica, Claude Code maneja una ventana de contexto de unos 200 mil tokens con compactacion automatica. Tiene un archivo especial llamado CLAUDE.md que siempre esta cargado, es como las instrucciones permanentes del proyecto. Y despues lee otros archivos bajo demanda segun lo que necesite."

> "Es especialmente bueno para proyectos grandes donde necesitas que el agente entienda la estructura completa: multiples archivos, dependencias, convenciones del equipo."

#### Si hay tiempo para demo
- Abrir la terminal y mostrar Claude Code en accion
- Mostrar la estructura de carpetas: `.claude/agents/`, `skills/`, `.claude/commands/`
- Ejecutar un comando simple como ejemplo

#### Posibles Preguntas del Publico
- **"Se puede usar Claude Code gratis?"** -> "Claude Code tiene un uso limitado gratuito con el plan de Anthropic. Para uso intensivo necesitas una suscripcion o creditos API. Pero para probar y aprender, el tier gratuito es suficiente."
- **"Funciona con cualquier lenguaje de programacion?"** -> "Si, Claude Code trabaja con archivos de texto, asi que funciona con cualquier lenguaje. No esta limitado a un stack especifico."
- **"Cual es la diferencia con usar Claude en el navegador?"** -> "El Claude del navegador es un chat. Claude Code es un agente que vive en tu terminal, lee tus archivos, ejecuta comandos, y puede modificar tu codigo directamente. Es mucho mas integrado con tu flujo de desarrollo."

### Transicion
> "Eso es Claude Code. Ahora veamos como OpenAI aborda el mismo problema, pero con una filosofia bastante diferente..."

---

## Seccion 4: Codex (2.5 min, slide 6)

### Puntos Clave
- Agente de codigo de OpenAI que ejecuta en sandbox aislado
- Clona tu repo completo y trabaja de forma autonoma
- Modelo: GPT-4.1 / o3 / o4-mini
- Enfoque asincrono: le das la tarea y te entrega el resultado
- Contexto ~128-200K tokens segun modelo

### Guion Sugerido
> "Codex es el agente de codigo de OpenAI, y tiene una filosofia muy diferente a Claude Code. Mientras que Claude Code es conversacional y trabaja contigo en tiempo real, Codex es mas como darle una tarea a alguien y que te la entregue cuando termine."

> "Codex clona tu repositorio en un sandbox aislado, un ambiente separado y seguro, ejecuta la tarea ahi, y te devuelve el resultado. No estas interactuando con el en tiempo real. Le dices 'arregla este bug' o 'agrega esta feature', y el trabaja solo."

> "Esto tiene ventajas: puedes lanzar varias tareas en paralelo mientras tu sigues trabajando en otra cosa. Pero tambien tiene limitaciones: no puedes guiarlo en el proceso como con Claude Code."

### Posibles Preguntas del Publico
- **"Es mejor Codex que Claude Code?"** -> "No es mejor ni peor, es diferente. Codex es excelente para tareas bien definidas y aisladas. Claude Code es mejor para tareas que necesitan contexto y iteracion. Depende de lo que necesites."
- **"Que modelo usa Codex?"** -> "Puede usar GPT-4.1, o3 u o4-mini. Puedes elegir segun la complejidad de la tarea y tu presupuesto."

### Transicion
> "Ahora pasemos a la propuesta de Google, que tiene una carta muy particular bajo la manga..."

---

## Seccion 5: Gemini CLI (2.5 min, slide 7)

### Puntos Clave
- Herramienta de Google para interactuar con modelos Gemini
- Google Agent Development Kit (ADK) para crear agentes en Python
- Extensiones y herramientas de funcion integradas
- Ventana de contexto hasta 1M-2M tokens (la mas grande del mercado)
- Integracion con Google Cloud y servicios Google

### Guion Sugerido
> "Gemini CLI es la herramienta de Google, y su gran diferenciador es el tamano de la ventana de contexto. Estamos hablando de hasta 2 millones de tokens. Para que se den una idea, Claude Code maneja 200 mil, Codex 200 mil, Copilot 128 mil. Gemini puede manejar 10 veces mas contexto que la mayoria."

> "Google tiene el Agent Development Kit o ADK, que te permite crear agentes en Python con orquestacion multi-agente. Es un enfoque mas programatico que archivos .md, pero muy potente si tu equipo trabaja en Python."

> "Ahora, un dato importante: tener una ventana de 2 millones de tokens no significa que todo funcione perfecto con ese volumen. La calidad puede degradarse con contextos muy largos. Es como leer un libro de mil paginas: puedes hacerlo, pero probablemente los detalles de la pagina 50 se te olvidan cuando llegas a la 900."

### Posibles Preguntas del Publico
- **"Entonces para que sirve tener tanta ventana de contexto?"** -> "Es util cuando necesitas analizar un codebase completo de una sola vez, o cuando trabajas con documentos muy largos. No siempre necesitas tanta ventana, pero cuando la necesitas, es un game changer."
- **"Gemini CLI es gratis?"** -> "Google ofrece un tier gratuito generoso con Gemini. Para uso mas intensivo o modelos mas grandes, necesitas creditos de Google Cloud."

### Transicion
> "Y finalmente, la herramienta que probablemente es la mas popular entre desarrolladores..."

---

## Seccion 6: GitHub Copilot (5 min, slides 8-9)

### Slide 8: Copilot - Agentes y Extensiones (2.5 min)

#### Puntos Clave
- Asistente de codigo integrado directamente en el IDE (VS Code, JetBrains)
- Modo agente con @workspace, @terminal, @vscode
- Copilot Extensions: agentes de terceros del marketplace
- Instruction files: `.github/copilot-instructions.md`
- MCP (Model Context Protocol) para herramientas externas

#### Guion Sugerido
> "GitHub Copilot es probablemente la herramienta de IA para codigo mas usada en el mundo. Y su gran ventaja es que vive dentro de tu IDE. No necesitas abrir una terminal aparte ni un navegador. Esta ahi, en VS Code o JetBrains, integrado."

> "Copilot tambien tiene un concepto de agentes: puedes invocar @workspace para que analice todo tu proyecto, @terminal para que trabaje con la terminal, o @vscode para que interactue con el editor. Y tiene Extensions, que son como plugins de terceros que agregan capacidades."

> "Algo interesante es que Copilot tambien tiene su version de los instruction files que vimos en Claude Code. En este caso es un archivo .github/copilot-instructions.md donde defines las reglas de tu proyecto."

### Slide 9: Copilot - Integracion en IDE (2.5 min)

#### Puntos Clave
- Inline suggestions: autocompletado en tiempo real (~8K contexto)
- Chat panel: conversacion sobre tu codigo (~32-64K contexto)
- Agent mode: ejecuta tareas multi-archivo (~128K contexto)
- Slash commands: /explain, /fix, /test, /new
- Menos personalizable que Claude Code, pero mas accesible

#### Guion Sugerido
> "Copilot tiene tres niveles de uso, y cada uno maneja diferente cantidad de contexto. El primero es el inline, el autocompletado mientras escribes. Esto usa unos 8 mil tokens de contexto, basicamente el archivo donde estas y poco mas."

> "El segundo nivel es el chat: abres un panel lateral y conversas sobre tu codigo. Aqui ya tiene entre 32 y 64 mil tokens de contexto. Y el tercero es el modo agente, que puede ejecutar tareas en multiples archivos con hasta 128 mil tokens."

> "Copilot es menos personalizable que Claude Code, no puedes definir agentes tan granulares ni skills modulares, pero es mucho mas accesible. Lo instalas, lo activas, y funciona. No hay configuracion de agentes ni archivos .md que mantener."

#### Posibles Preguntas del Publico
- **"Usamos Copilot en el equipo?"** -> "Depende de las licencias que tengamos. Si no lo usamos aun, es una buena herramienta para empezar porque tiene la curva de aprendizaje mas baja."
- **"Copilot funciona con JetBrains?"** -> "Si, tiene plugin para IntelliJ, PyCharm, WebStorm y otros IDEs de JetBrains. La experiencia es un poco diferente que en VS Code, pero las funcionalidades core estan."
- **"Cual es la diferencia entre Copilot Free y Copilot Pro?"** -> "Free tiene un limite de sugerencias por mes y solo ofrece modelos basicos. Pro tiene sugerencias ilimitadas, acceso a modelos mas avanzados, y el modo agente completo. Para uso profesional, Pro vale la pena."

### Transicion
> "Ya conocemos las cuatro herramientas. Ahora pongamoslas lado a lado y veamos como se comparan..."

---

## Seccion 7: Matriz Comparativa (5 min, slide 10)

### Puntos Clave
- Esta es la slide mas densa del lab, hay que darle tiempo al grupo para absorberla
- No hay una "mejor herramienta", depende del caso de uso
- Las diferencias principales son: interfaz, nivel de personalizacion, y tamano de contexto
- Guiar la lectura columna por columna, no leer toda la tabla

### Guion Sugerido
> "Esta es la slide mas importante de hoy, asi que tomenle un momento para verla."

*Dar 15-20 segundos para que lean la tabla*

> "Vamos a recorrerla juntos. En interfaz: Claude Code y Codex son CLI, Gemini es CLI o web, y Copilot vive en el IDE. Cada enfoque tiene su ventaja."

> "En agentes custom: Claude Code es el mas fuerte con sus archivos .md. Gemini tiene ADK para Python. Codex y Copilot tienen soporte parcial."

> "En contexto maximo: Gemini es el rey con hasta 2 millones de tokens. Claude Code y Codex manejan 200 mil. Copilot tiene 128 mil en modo agente."

> "Y al final, lo que importa: cual es mejor para que. Claude Code para proyectos complejos donde necesitas mucha personalizacion. Codex para tareas aisladas que puedes lanzar y olvidar. Gemini cuando necesitas meter un codebase enorme en contexto. Y Copilot para el desarrollo diario, el que siempre esta ahi en tu IDE."

> "No hay una respuesta universal. Lo ideal es conocerlas todas y usar la correcta para cada situacion."

### Posibles Preguntas del Publico
- **"Podemos usar varias al mismo tiempo?"** -> "Absolutamente. De hecho, esa es la recomendacion. Puedes tener Copilot en tu IDE para el dia a dia y usar Claude Code para tareas mas complejas. No son mutuamente excluyentes."
- **"Cual recomendarias para empezar?"** -> "Si nunca has usado una herramienta de IA para codigo, empieza con Copilot. Es la mas accesible. Si ya te sientes comodo y quieres mas control, prueba Claude Code."
- **"Estas herramientas se actualizan mucho?"** -> "Constantemente. El espacio de herramientas de IA evoluciona rapidamente. Lo que importa no es memorizar las specs de hoy, sino entender los conceptos: contexto, agentes, skills. Las herramientas cambian, los conceptos se mantienen."

### Transicion
> "Ahora que conocemos las herramientas, hablemos de como sacarles el maximo provecho..."

---

## Seccion 8: Mejores Practicas (7.5 min, slides 11-13)

### Slide 11: Mejores Practicas para Prompting (2.5 min)

#### Puntos Clave
- Estructurar con markdown (headers, listas, bloques de codigo)
- Ser especifico: que quieres, como lo quieres, restricciones
- Dar contexto: archivos relevantes, decisiones previas
- Iterar: refinar el prompt basado en la respuesta
- Usar templates/comandos para tareas repetitivas

#### Guion Sugerido
> "Esto aplica a TODAS las herramientas que vimos, no solo a una. La primera regla de oro es estructurar tus prompts con markdown. Recuerden el Lab 2: la IA entiende mejor cuando le hablas en su idioma."

> "La segunda es ser especifico. No le digas 'arregla el codigo'. Dile 'en el archivo X, la funcion Y tiene un bug que hace Z. Necesito que lo corrija manteniendo la interfaz actual'. Cuanto mas claro seas, mejor resultado."

> "La tercera es dar contexto. Si estas trabajando en una feature que tiene dependencias, mencionaras. Si hay decisiones de diseno previas, explicarlas. La IA no puede adivinar lo que tu sabes."

> "Y la cuarta es iterar. El primer resultado rara vez es perfecto. Refina, ajusta, pide cambios. Es una conversacion, no un examen de una sola respuesta."

### Slide 12: Como Evaluar Calidad de Respuestas (2.5 min)

#### Puntos Clave
- Verificar datos especificos (fechas, numeros, referencias)
- Probar el codigo generado, no asumir que funciona
- Comparar con documentacion oficial
- Pedir explicacion del razonamiento
- Desconfiar de respuestas demasiado confiadas sin fuentes

#### Guion Sugerido
> "Recuerden la leccion del Lab 1: la IA alucina. Eso no cambio. Asi que cada vez que reciban una respuesta, apliquen estos filtros."

> "Primero: si la respuesta tiene datos especificos, fechas, numeros, nombres de funciones, verificar. Segundo: si es codigo, ejecutarlo. No copien y peguen a produccion sin probar. Tercero: si menciona algo de una libreria o API, comparar con la documentacion oficial."

> "Un truco util: pedirle a la IA que explique su razonamiento. Si la explicacion no tiene sentido o es vaga, probablemente la respuesta tampoco es confiable."

### Slide 13: Construyendo tu Flujo de Trabajo con IA (2.5 min)

#### Puntos Clave
- Empezar con UNA herramienta y una tarea especifica
- Crear agentes para tareas que repites frecuentemente
- Documentar lo que funciona en archivos de instrucciones
- Combinar herramientas: Copilot para inline + Claude Code para proyectos
- La IA es un acelerador, no un reemplazo del proceso

#### Guion Sugerido
> "Mi consejo practico: no intenten adoptar las cuatro herramientas de golpe. Elijan una, elijan una tarea concreta, y usenla para esa tarea durante una o dos semanas. Cuando se sientan comodos, agregan otra tarea o otra herramienta."

> "Si algo les funciona bien, documentenlo. Creen un archivo de instrucciones, un agente, un comando. Automaticen lo que se repite. Compartan con el equipo lo que descubran."

> "Y una combinacion que funciona muy bien: Copilot en el IDE para el autocompletado y las sugerencias rapidas del dia a dia, y Claude Code para cuando necesitan que un agente haga un trabajo mas grande: refactoring, generacion de tests, documentacion."

> "Pero recuerden siempre: la IA es un acelerador. Acelera tu proceso, pero no reemplaza tu criterio, tu revision, tu testing. El proceso de desarrollo sigue siendo tuyo."

### Posibles Preguntas del Publico
- **"Cuanto tiempo se ahorra realmente con estas herramientas?"** -> "Depende mucho de la tarea. Para codigo boilerplate, tests unitarios, o documentacion, puede ser 50-70% mas rapido. Para logica de negocio compleja, el ahorro es menor porque necesitas mas revision. En promedio, los equipos reportan un 30-40% de mejora en productividad."
- **"No da miedo depender de la IA y perder habilidades?"** -> "Es una preocupacion valida. La clave es usarla como complemento, no como muleta. Si la IA genera codigo, asegurate de entenderlo. Si genera tests, verifica que cubren los casos correctos. La IA te hace mas rapido, pero tu necesitas mantener la capacidad de evaluar lo que produce."

### Transicion
> "Antes de cerrar, hay un tema importante que no podemos ignorar..."

---

## Seccion 9: Etica y Responsabilidad (2 min, slide 14)

### Puntos Clave
- No pegar codigo sensible o credenciales en chats publicos
- Revisar politicas de privacidad de cada herramienta
- El codigo generado necesita revision humana siempre
- Propiedad intelectual: tema legal en evolucion
- La IA amplifica tus capacidades, la responsabilidad sigue siendo tuya

### Guion Sugerido
> "Dos minutos sobre etica, pero dos minutos importantes. Primero: tengan cuidado con lo que comparten. No peguen credenciales, tokens, API keys, ni codigo con datos sensibles en ninguna herramienta de IA, especialmente las versiones gratuitas. Revisen las politicas de privacidad."

> "Segundo: todo codigo generado por IA necesita revision humana. Siempre. No importa lo bueno que se vea. La responsabilidad del codigo que llega a produccion es nuestra, no de la IA."

> "Y tercero: el tema de propiedad intelectual esta en evolucion. Las leyes todavia no estan claras sobre quien 'posee' el codigo generado por IA. Mantenerse informados sobre las politicas de la empresa y la legislacion."

> "En resumen: la IA amplifica lo que haces. Si la usas bien, amplifica tus capacidades. Pero la responsabilidad siempre es tuya."

### Transicion
> "Y con eso, llegamos al cierre. No solo de este lab, sino de todo el workshop..."

---

## Seccion 10: Cierre del Workshop (3 min, slides 15-16)

### Slide 15: Recursos y Proximos Pasos (2 min)

#### Puntos Clave
- Experimentar con la herramienta que mas les intereso
- Crear su primer agente o comando personalizado
- Compartir lo que descubran con el equipo
- La practica constante es lo que marca la diferencia

#### Guion Sugerido
> "Antes del cierre, quiero dejarles algo concreto. Esta semana, elijan una herramienta de las que vimos hoy. Solo una. Pruébenla con una tarea real de su trabajo. No tiene que ser algo critico, puede ser generar un test, documentar una funcion, o refactorizar un archivo."

> "Si les gusta, den el siguiente paso: creen un agente o un comando personalizado. Algo que automatice una tarea que hacen seguido. Y lo mas importante: compartan lo que descubran con el equipo. Asi todos crecemos."

### Slide 16: Cierre del Workshop (1 min)

#### Puntos Clave
- Agradecer la participacion en las 4 sesiones
- Recapitular el viaje: Fundamentos -> Contexto -> Agentes -> Herramientas
- Invitar a seguir explorando
- Cierre emotivo y genuino

#### Guion Sugerido
> "Y con esto cerramos no solo el Lab 4, sino todo el AI Laboratory."

> "Quiero agradecerles por estar en las cuatro sesiones. Empezamos entendiendo que la IA predice, no piensa. Seguimos con como manejar el contexto y hablarle en su idioma. Aprendimos que los agentes, skills y comandos son la forma de organizar ese conocimiento. Y hoy vimos como las herramientas reales implementan todo eso."

> "El viaje fue de fundamentos a practica. De conceptos a herramientas. Y ahora les toca a ustedes el siguiente paso: experimentar, equivocarse, aprender, y compartir."

> "La IA no va a reemplazar a los desarrolladores. Pero los desarrolladores que usen IA van a tener una ventaja enorme. Y ustedes ya tienen las bases para ser parte de ese grupo."

> "Gracias por ser parte del AI Laboratory."

*Pausa. Dejar que el cierre respire. No apurarse a la siguiente actividad.*

---

## Seccion 11: Tiempo Abierto (20 min)

### Dinamica Sugerida
Los 20 minutos restantes son flexibles. Al ser el ultimo lab, considerar hacerlo especial.

#### Opcion A: Demo en Vivo de Claude Code
- Abrir la terminal con Claude Code
- Mostrar la estructura de agentes y skills de este mismo proyecto
- Ejecutar un comando en vivo (por ejemplo, `/generate-lab` o consultar algo)
- Dejar que el equipo sugiera tareas para que Claude Code ejecute

#### Opcion B: Preguntas y Respuestas Libre
- Abrir el espacio para cualquier pregunta, no solo del Lab 4 sino de los 4 labs
- Mantener las respuestas concisas para cubrir mas preguntas
- Si una pregunta es muy especifica, ofrecer responderla despues de la sesion

#### Opcion C: Ejercicio Hands-On
- Si el equipo tiene laptops, que instalen una de las herramientas
- Guiarlos en su primer prompt o su primer uso
- Resolver dudas en tiempo real

#### Opcion D: Retrospectiva del Workshop
- "De los 4 labs, cual les parecio mas util?"
- "Que tema les gustaria profundizar?"
- "Que van a probar primero en su trabajo?"
- Recoger feedback para futuras sesiones

#### Opcion E: Combinacion (recomendada para el ultimo lab)
- 8 min de demo en vivo de Claude Code
- 7 min de preguntas y respuestas abiertas (de cualquier lab)
- 5 min de retrospectiva y feedback del workshop

### Preguntas Frecuentes que Pueden Surgir

**"Cual herramienta deberia instalar primero?"**
> "Si ya usan VS Code, Copilot es la opcion mas natural porque se integra directamente. Si quieren mas control y personalizacion, Claude Code. Pero empiecen con una sola."

**"Estas herramientas funcionan bien con nuestro stack?"**
> "Todas las herramientas que vimos son agnosticas del lenguaje. Funcionan con JavaScript, Python, Java, Go, lo que sea. Algunas tienen mejor soporte para ciertos lenguajes, pero en general todas manejan cualquier stack moderno."

**"Cuanto cuesta esto para el equipo?"**
> "Copilot Business cuesta alrededor de $19 USD por usuario al mes. Claude Code tiene planes individuales y empresariales. Gemini tiene un tier gratuito generoso. Lo importante es evaluar el ROI: si cada desarrollador ahorra 1 hora al dia, la herramienta se paga sola en la primera semana."

**"La IA puede generar tests automaticamente?"**
> "Si, y es una de las mejores tareas para empezar. Los tests son relativamente formulaicos, la IA los genera bien. Pero siempre hay que revisarlos: verificar que cubren los edge cases correctos y que las assertions tienen sentido."

**"Que pasa si la IA genera codigo con vulnerabilidades?"**
> "Es un riesgo real. Por eso la revision humana es obligatoria. Ademas, herramientas como Copilot ya incluyen filtros de seguridad que detectan patrones inseguros. Pero la ultima linea de defensa siempre es el code review humano."

**"Se puede usar IA para hacer code reviews?"**
> "Si, y cada vez se usa mas. Puedes pedirle a Claude Code o Copilot que revise un PR y te senale problemas potenciales. No reemplaza el code review humano, pero es una buena primera pasada."

---

## Notas Finales para el Moderador

### Ritmo y Tono
- Mantener un tono conversacional, no de catedra
- Este es el ultimo lab: el tono debe ser de culminacion, no de rutina
- No apurarse. Es mejor cubrir menos contenido con claridad que correr por todos los slides
- Hacer pausas despues de conceptos importantes para que el grupo procese
- En la seccion de herramientas, no vender ninguna herramienta como "la mejor". Ser objetivo
- El cierre (slide 16) merece un momento especial. No lo apures. Deja que las palabras aterricen

### Si te quedas sin tiempo
- Prioriza Claude Code y la matriz comparativa (son las secciones core)
- Codex y Gemini CLI se pueden resumir en 1 minuto cada uno ("Codex es asíncrono, Gemini tiene la ventana mas grande, punto")
- Las mejores practicas (slides 11-13) se pueden comprimir en 2 minutos mencionando solo los puntos top
- Etica se puede resumir en una frase: "No peguen credenciales, siempre revisen el codigo, la responsabilidad es suya"
- Nunca sacrifiques el cierre del workshop, es el momento mas importante de este lab

### Si te sobra tiempo
- Profundiza en la demo en vivo de Claude Code (mostrar agentes, skills, comandos reales)
- Abre VS Code y muestra Copilot en accion si lo tienes disponible
- Compara en vivo: pide la misma tarea a dos herramientas diferentes y compara resultados
- Pregunta: "Que herramienta les intereso mas y por que?"
- Comparte anecdotas personales de uso de estas herramientas

### Errores comunes a evitar
- No favorecer una herramienta sobre otra -> ser objetivo y presentar pros y contras
- No asumir que todos tienen acceso a todas las herramientas -> preguntar antes
- No entrar en detalles de pricing que pueden cambiar rapidamente -> enfocarse en capacidades
- No prometer que la IA "siempre funciona" -> ser honesto sobre limitaciones
- No apurar el cierre del workshop -> es el momento emotivo que el equipo va a recordar
- No olvidar reconectar con conceptos de labs anteriores -> este lab es la sintesis de todo

### Distribucion del Tiempo - Resumen Rapido

| Seccion | Duracion | Acumulado |
|---------|----------|-----------|
| Bienvenida | 1 min | 1 min |
| Recap Labs 1-3 | 2 min | 3 min |
| Claude Code | 7 min | 10 min |
| Codex | 2.5 min | 12.5 min |
| Gemini CLI | 2.5 min | 15 min |
| GitHub Copilot | 5 min | 20 min |
| Matriz comparativa | 5 min | 25 min |
| Mejores practicas | 7.5 min | 32.5 min |
| Etica y responsabilidad | 2 min | 34.5 min |
| Cierre del workshop | 3 min | 37.5 min |
| Margen/transiciones | 2.5 min | 40 min |
| **Tiempo abierto** | **20 min** | **60 min** |

### Checklist Post-Sesion
- [ ] Anotar las preguntas que surgieron para referencia futura
- [ ] Registrar que herramientas generaron mas interes en el equipo
- [ ] Recoger feedback verbal o escrito sobre los 4 labs del workshop
- [ ] Identificar quienes quieren profundizar (posibles champions de IA en el equipo)
- [ ] Enviar un resumen/email de cierre con links a las herramientas mencionadas
- [ ] Compartir los slides de los 4 labs con el equipo
- [ ] Planificar seguimiento: sesion de check-in en 2-4 semanas para ver como les fue
- [ ] Celebrar: completaste un workshop de 4 sesiones. Buen trabajo.
