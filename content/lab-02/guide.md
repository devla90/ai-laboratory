# Guia del Moderador - Lab 02: Contexto, Compactacion y el Lenguaje de la IA

## Informacion General
- **Duracion**: 40 minutos de presentacion + 20 minutos abiertos
- **Audiencia**: Equipo de desarrollo (distintos niveles de experiencia con IA)
- **Objetivo**: Que el equipo entienda como la IA maneja la informacion que recibe, cuales son sus limites de memoria, y como comunicarse mejor con ella usando estructura
- **Materiales**: Presentacion Slidev, conexion a internet para demo en vivo de markdown vs texto plano

## Preparacion Previa
- [ ] Tener la presentacion corriendo (`npm run dev:lab02`)
- [ ] Verificar que los slides se ven correctamente en el proyector
- [ ] Tener una sesion de Claude o ChatGPT lista para la demo de markdown vs texto plano (slides 13-14)
- [ ] Preparar los dos prompts para la demo: uno en texto plano y otro en markdown (mismo pedido)
- [ ] Tener una pizarra o pizarron disponible (ideal para la analogia de la pizarra)
- [ ] Tener agua disponible (40 min hablando)
- [ ] Revisar brevemente las preguntas que surgieron en el Lab 01

---

## Seccion 1: Bienvenida y Portada (1 min)

### Puntos Clave
- Dar la bienvenida al Lab 02
- Recordar que es la segunda de cuatro sesiones
- Hoy entramos en un tema mas practico: como la IA maneja la informacion

### Guion Sugerido
> "Bienvenidos al Lab 02 del AI Laboratory. En la sesion anterior sentamos las bases: que es la IA, como funciona por dentro, y por que a veces se equivoca. Hoy vamos a entrar en algo mas practico: como la IA maneja la informacion que le das, cuanta puede recordar, y como hablarle para que te entienda mejor."

### Transicion
> "Pero primero, un repaso rapido de lo que vimos la vez pasada..."

---

## Seccion 2: Recap Lab 1 (2 min, slide 2)

### Puntos Clave
- Repasar los 4 conceptos clave del Lab 1
- Conectar el recap con el tema de hoy
- No extenderse: es un recordatorio, no una repeticion

### Guion Sugerido
> "Recordemos lo que vimos en el Lab 1. Primero: la IA no piensa, predice. Genera la siguiente palabra mas probable basandose en patrones. Segundo: no inventa de la nada, recombina patrones de sus datos de entrenamiento. Tercero: alucina, genera respuestas que suenan convincentes pero pueden ser incorrectas. Y cuarto: nuestra analogia del companero sin apuntes, que sabe el tema general pero inventa los detalles."

> "Ahora, si la IA funciona prediciendo la siguiente palabra, hay una pregunta natural que surge: como recuerda lo que le dijiste hace 5 minutos? O hace media hora? Ahi es donde entra el tema de hoy: el contexto."

### Posibles Preguntas del Publico
- **"Tengo una duda del Lab 1 que me quedo pendiente"** -> "Anotala y la vemos en el tiempo abierto al final. Asi no perdemos el hilo de lo de hoy."

### Transicion
> "Entonces, arrancamos con la pregunta fundamental: que es el contexto para una IA?"

---

## Seccion 3: Que es el Contexto (7 min, slides 3-5)

### Slide 3: Que es el Contexto - Concepto (2.5 min)

#### Puntos Clave
- El contexto es TODA la informacion disponible en una conversacion
- Incluye: tu mensaje actual, mensajes anteriores, archivos adjuntos, instrucciones del sistema
- Es temporal: solo existe durante la conversacion
- Se mide en tokens (repasar brevemente que son tokens del Lab 1)
- Tiene un limite fijo: la "ventana de contexto"

#### Guion Sugerido
> "Cuando le escriben algo a la IA, ella no solo ve su ultimo mensaje. Ve TODO lo que ha pasado en esa conversacion: sus mensajes, sus respuestas, archivos que hayan compartido, instrucciones que el sistema le dio por detras. A todo eso le llamamos el contexto."

> "Piensen en el contexto como la memoria de trabajo de la IA. Es temporal, solo dura mientras la conversacion esta activa. Y tiene un limite, que se mide en tokens. Recuerden del Lab 1: un token es un pedazo de palabra, mas o menos 0.75 palabras en ingles y 0.5 en espanol."

> "Lo importante es que este limite es fijo. No crece. No se expande. Es como tener una caja de un tamano determinado: puedes meter informacion hasta que se llene."

#### Datos Extra para Preguntas
- El contexto incluye tanto los mensajes del usuario como las respuestas de la IA
- Las instrucciones del sistema (system prompt) tambien ocupan espacio en el contexto
- Cada vez que la IA genera una respuesta, esa respuesta tambien se suma al contexto

### Slide 4: Analogia - La Pizarra de la IA (2.5 min)

#### Puntos Clave
- La IA trabaja con una pizarra de tamano fijo
- Todo lo que le dices se escribe en la pizarra
- Cuando se llena, tiene que borrar lo mas antiguo
- Por eso "olvida" lo que le dijiste al inicio de conversaciones largas
- Lo mas reciente siempre esta visible

#### Guion Sugerido
> "Imaginen que la IA tiene una pizarra. No una pizarra infinita, sino una de tamano fijo. Cada vez que le dicen algo, se escribe en la pizarra. Cada vez que ella responde, eso tambien se escribe en la pizarra."

> "Que pasa cuando la pizarra se llena? La IA tiene que borrar las partes mas antiguas para poder seguir escribiendo. Asi que si tuvieron una conversacion muy larga y al inicio le dijeron algo importante, es posible que eso ya se haya borrado de la pizarra."

> "Por eso a veces sienten que la IA 'se olvido' de lo que le dijeron. No es que no le haya importado, es que literalmente ya no lo puede ver. Fue borrado de su pizarra."

Si hay un pizarron fisico disponible:
> "Miren, es como si yo escribiera aqui todo lo que vamos hablando... (escribir unas lineas)... y cuando se me acaba el espacio, tengo que borrar lo de arriba para seguir abajo."

#### Posibles Preguntas del Publico
- **"Y si le repito lo que le dije antes?"** -> "Exacto, esa es una estrategia valida. Si algo es importante, puedes repetirlo para que vuelva a estar en la pizarra. Vamos a ver mas estrategias al rato."
- **"Hay alguna forma de agrandar la pizarra?"** -> "No directamente. El tamano de la pizarra depende de la herramienta que uses. Unas tienen pizarras mas grandes que otras, y eso es lo que vamos a ver en la siguiente seccion."

### Slide 5: Contexto como Memoria de Trabajo (2 min)

#### Puntos Clave
- El contexto se compone de: tu mensaje + historial + archivos + sistema
- 100K tokens equivale a 75,000 palabras o un libro de 300 paginas
- Mas contexto significa que la IA "ve" mas, pero no siempre implica mejores respuestas
- La calidad de lo que esta en el contexto importa tanto como la cantidad

#### Guion Sugerido
> "Para ponerlo en perspectiva: 100 mil tokens, que es una ventana de contexto tipica, equivale a unas 75 mil palabras. Eso es como un libro de 300 paginas. Suena a mucho, pero cuando estan trabajando en un proyecto con muchos archivos, se llena mas rapido de lo que creen."

> "Y un dato importante: mas contexto no siempre significa mejores respuestas. Si le dan a la IA un monton de informacion irrelevante, la pueden confundir. Es como si le dieran a alguien un libro de 300 paginas para responder una pregunta que se contesta con un parrafo. Puede que encuentre la respuesta, pero tambien puede perderse en lo demas."

### Transicion
> "Ahora que sabemos que es el contexto, la siguiente pregunta es: cuanto contexto tiene cada herramienta? Porque no todas son iguales..."

---

## Seccion 4: Ventanas de Contexto (7 min, slides 6-8)

### Slide 6: Claude Code - Hasta ~1M tokens (2.5 min)

#### Puntos Clave
- Claude Code ahora soporta hasta ~1M tokens con Opus 4.6/4.7 (5x mas que el anterior ~200K)
- Equivalente a ~750,000 palabras
- Ideal para proyectos grandes: puede leer multiples archivos sin perder el hilo
- Mantiene decisiones y contexto del proyecto a lo largo de la conversacion
- Tiene compactacion automatica en cascada de 5 niveles

#### Guion Sugerido
> "Empecemos con Claude Code, que ahora tiene la ventana de contexto mas grande de las herramientas que usamos. Con Opus 4.6 y 4.7, soporta hasta 1 millon de tokens — eso son unas 750 mil palabras, 5 veces mas que antes. Es como tener varios libros completos en la pizarra al mismo tiempo."

> "Que significa esto en la practica? Que pueden estar trabajando en un proyecto grande, pedirle que lea muchos archivos, que entienda toda la arquitectura, y Claude Code puede mantener todo eso en su pizarra sin problemas."

> "Ademas, ahora tiene compactacion en cascada de 5 niveles. No solo resume una vez — va comprimiendo progresivamente a medida que necesita mas espacio. Vamos a ver que significa eso en un momento."

### Slide 7: Codex - ~200-400K tokens (2.5 min)

#### Puntos Clave
- Codex de OpenAI ahora tiene entre ~200K y 400K tokens (GPT-5.3 Codex ~200K, GPT-5.5 ~400K)
- Tiene dos modos: CLI local (terminal, interactivo) y Cloud remoto (contenedores, asincrono)
- CLI: ejecuta en tu maquina con sandbox a nivel de OS (Seatbelt en macOS, Bubblewrap en Linux)
- Cloud: clona tu repo en un contenedor aislado, ejecuta la tarea, entrega diff o PR
- Se configura con AGENTS.md (similar a CLAUDE.md en Claude Code)

#### Guion Sugerido
> "Codex de OpenAI tambien crecio: ahora tiene entre 200 mil y 400 mil tokens. Pero lo mas interesante es que tiene dos modos de trabajo muy diferentes."

> "Primero, el CLI local: lo instalan en su terminal y funciona parecido a Claude Code. Es interactivo, pueden chatear con el, y edita archivos directamente en su maquina. Usa sandbox a nivel del sistema operativo para proteger su filesystem y red."

> "Segundo, el Cloud: desde la web le envian una tarea, Codex clona su repo en un contenedor aislado en la nube, ejecuta todo en background, y les entrega un diff o un PR listo. Pueden mandar varias tareas en paralelo y volver despues a revisar los resultados."

> "Se configura con AGENTS.md, que es el equivalente a CLAUDE.md en Claude Code. Ahi ponen instrucciones, convenciones del proyecto, y reglas."

#### Posibles Preguntas del Publico
- **"Entonces Codex es mejor para tareas grandes?"** -> "Depende. El CLI de Codex es interactivo como Claude Code. Pero el Cloud es ideal para tareas autonomas bien definidas: 'refactoriza este modulo', 'agrega tests a estas funciones'. Pueden mandar varias tareas en paralelo y volver despues."

### Slide 8: Copilot - ~8-192K tokens (2 min)

#### Puntos Clave
- Copilot crecio mucho: de 8K a 192K tokens segun el modo, y ahora tiene 4 modos
- Modo inline (autocompletado): solo el archivo actual (~8K)
- Modo chat: archivos abiertos + historial (~64-128K)
- Modo agent: edita archivos y ejecuta comandos autonomamente (~192K)
- Cloud agent: crea PRs desde issues via GitHub Actions — trabaja en background
- Es multi-modelo: el usuario elige entre Claude, GPT, Gemini o Grok
- GitHub limita el contexto por debajo de lo que los modelos soportan nativamente

#### Guion Sugerido
> "Y luego tenemos a Copilot, que cambio mucho. Ahora tiene 4 modos de trabajo y es multi-modelo: pueden elegir entre Claude, GPT, Gemini o Grok."

> "El modo inline sigue igual: la sugerencia gris de autocompletado solo ve el archivo actual, unos 8 mil tokens."

> "El chat ahora llega a 64-128 mil tokens. El agent mode llega hasta 192 mil tokens y es autonomo: edita multiples archivos y ejecuta comandos por ustedes, como correr tests o instalar dependencias."

> "Y lo mas nuevo: el cloud agent. Pueden asignar un issue de GitHub a Copilot y el crea una rama, abre un draft PR, y trabaja autonomamente en GitHub Actions. Vuelven despues y ya tienen el PR listo para revisar."

> "Un detalle importante: GitHub limita el contexto por debajo de lo que los modelos soportan. Aunque Claude Opus maneja 1 millon de tokens, Copilot le pone un tope de unos 144 mil."

#### Posibles Preguntas del Publico
- **"Entonces cual es mejor?"** -> "No hay un 'mejor' universal. Copilot es el mas versatil: autocompletado rapido, agent mode para tareas complejas, y cloud agent para trabajo autonomo. Claude Code tiene la ventana mas grande y la mejor ejecucion local. Codex combina CLI interactivo y cloud para tareas en paralelo. Vamos a explorar esto con mas detalle en el Lab 4."
- **"Se pueden combinar?"** -> "Absolutamente. Muchos devs usan Copilot para el dia a dia y Claude Code o Codex para tareas mas complejas. No son excluyentes."

### Transicion
> "Ahora ya sabemos que la pizarra tiene un tamano fijo y que cada herramienta tiene un tamano diferente. Pero que pasa cuando la pizarra se llena? Se acaba todo? No necesariamente..."

---

## Seccion 5: Compactacion (5 min, slides 9-10)

### Slide 9: Que es la Compactacion (2.5 min)

#### Puntos Clave
- Cuando la conversacion se acerca al limite, la IA resume lo antiguo para liberar espacio
- Preserva: decisiones tomadas, archivos modificados, contexto del proyecto
- Pierde: el detalle palabra por palabra de mensajes viejos
- Es un mecanismo automatico en herramientas como Claude Code

#### Guion Sugerido
> "Cuando la pizarra esta a punto de llenarse, la IA tiene un mecanismo de supervivencia: la compactacion. En vez de simplemente borrar todo y empezar de cero, la IA toma los mensajes mas antiguos y los resume."

> "Es como hacer un resumen ejecutivo de la conversacion. Mantiene lo importante: que decisiones se tomaron, que archivos se modificaron, cual es el objetivo del proyecto. Pero pierde el detalle fino: las frases exactas que dijeron, los intentos fallidos, las discusiones intermedias."

> "En Claude Code esto pasa automaticamente. Ustedes ni se enteran, pero en algun momento la IA internamente comprime la conversacion para poder seguir trabajando."

#### Datos Extra para Preguntas
- En Claude Code, la compactacion se puede observar porque en el chat aparece un indicador
- Los archivos de configuracion como CLAUDE.md se cargan por fuera del historial, asi que no se ven afectados por la compactacion
- La compactacion es una de las razones por las que a veces la IA "olvida" instrucciones que le dieron al inicio

### Slide 10: Analogia - Resumir Apuntes (2.5 min)

#### Puntos Clave
- Cuaderno de 100 paginas, ya llenaste 90
- En vez de empezar uno nuevo, resumes las primeras 70 en 10 paginas
- Pierdes detalle pero mantienes las ideas clave
- Ahora solo usas 30 paginas (10 resumen + 20 recientes) y tienes 70 libres para seguir
- La IA puede "olvidar" instrucciones del inicio por esto
- Solucion: repetir instrucciones importantes o usar archivos de configuracion

#### Guion Sugerido
> "Piensen en un cuaderno de 100 paginas. Estan en una sesion de trabajo larga, tomando apuntes, y ya llenaron 90 paginas. Les quedan 10. Que hacen?"

> "Una opcion es tomar las primeras 70 paginas de apuntes y resumirlas en 10 paginas. Pierden los detalles, las notas al margen, los dibujos que hicieron, pero mantienen las ideas principales. Ahora solo usan 30 paginas — 10 del resumen mas 20 recientes — y les quedan 70 paginas libres para seguir trabajando."

> "Eso es exactamente lo que hace la compactacion. La IA resume la primera parte de la conversacion para liberar espacio y poder seguir."

> "Pero hay un riesgo: si al inicio de la conversacion le dieron una instruccion especifica, por ejemplo 'siempre usa TypeScript', eso puede quedar fuera del resumen. La IA no lo olvida por mala voluntad, simplemente no cabia en el resumen."

> "La solucion? Dos opciones. Primera: si algo es importante, repitanlo. Segunda, y esta es la mejor: usen archivos de configuracion como CLAUDE.md. Estos archivos se cargan por fuera de la conversacion, asi que la compactacion no los afecta. Vamos a ver mas sobre esto en el Lab 3."

#### Posibles Preguntas del Publico
- **"Y si no quiero que la IA resuma nada?"** -> "Pueden empezar una conversacion nueva. Eso les da una pizarra limpia. A veces es mejor empezar de cero que trabajar con un resumen."
- **"Como se si la IA ya compacto?"** -> "En Claude Code aparece un indicador visual. En otras herramientas no siempre es visible. Una senal es cuando la IA empieza a 'olvidar' cosas que le dijeron antes."

### Transicion
> "Muy bien, ya sabemos que es el contexto, cuanto tiene cada herramienta, y que pasa cuando se llena. Ahora viene la parte mas practica del lab: como hablarle a la IA para que nos entienda mejor."

---

## Seccion 6: Markdown para la IA (5 min, slides 11-12)

### Slide 11: Markdown - Que es y Por que Importa (2.5 min)

#### Puntos Clave
- Markdown es un lenguaje de formato ligero: # titulos, - listas, ** negritas
- La IA fue entrenada con ENORMES cantidades de markdown (GitHub, documentacion tecnica)
- Reconoce la estructura de markdown como senales de organizacion
- Un prompt estructurado produce respuestas mas precisas
- No necesitan ser expertos: con headers y listas ya marcan diferencia

#### Guion Sugerido
> "Ahora vamos a hablar de algo muy practico: como hablarle a la IA. Resulta que la forma en que estructuran sus mensajes hace una diferencia real en la calidad de las respuestas."

> "Markdown es un lenguaje de formato ligero. Los que usan GitHub ya lo conocen: el numeral para titulos, el guion para listas, los asteriscos dobles para negritas. Es el formato en el que se escribe la documentacion en GitHub, los READMEs, los wikis."

> "Y aqui viene lo importante: la IA fue entrenada con cantidades ENORMES de markdown. Toda la documentacion de GitHub, articulos tecnicos, tutoriales... estan en markdown. La IA reconoce esa estructura como senales de organizacion. Cuando le escriben con estructura, ella entiende mejor la jerarquia de lo que le estan pidiendo."

> "No necesitan ser expertos en markdown. Con saber poner un titulo con numeral y una lista con guiones, ya estan comunicandose mejor con la IA."

### Slide 12: Estructura vs Texto Plano (2.5 min)

#### Puntos Clave
- Misma informacion, dos formatos diferentes
- Texto plano: todo en un parrafo corrido
- Markdown: separado en secciones con headers y listas
- La IA procesa mejor la version estructurada
- La respuesta tiende a ser mas completa y organizada

#### Guion Sugerido
> "Veamos un ejemplo concreto. Digamos que necesitan una funcion que valide emails. Pueden pedirla de dos formas."

> "Forma uno, texto plano: 'Necesito que hagas una funcion que valide emails y que devuelva true o false y que maneje los casos de arroba faltante y dominios invalidos'. Todo en un parrafo, todo corrido."

> "Forma dos, con markdown: un header que dice 'Tarea: crear funcion de validacion de email'. Abajo, otro header 'Requisitos', y una lista: devolver true o false, validar presencia de arroba, validar dominio valido."

> "Es la MISMA informacion. Pero la version con estructura le da a la IA senales claras de que es el objetivo, cuales son los requisitos, y cuantos requisitos son. La respuesta suele ser mas completa porque la IA puede 'tachar' cada requisito como una lista."

#### Posibles Preguntas del Publico
- **"Hay que escribir siempre en markdown?"** -> "No siempre. Para preguntas simples, texto plano esta bien. Pero cuando el pedido tiene multiples requisitos o es complejo, la estructura ayuda mucho."
- **"Funciona en ChatGPT tambien o solo en Claude?"** -> "Funciona en todas las IAs. Todas fueron entrenadas con markdown. Es una tecnica universal."
- **"Y si no se markdown?"** -> "Con tres cosas ya estan bien: numeral para titulos, guion para listas, y doble asterisco para negritas. Eso es el 80% de lo que necesitan."

### Transicion
> "Esto suena bien en teoria, pero vamos a comprobarlo. Vamos a hacer un ejercicio en vivo..."

---

## Seccion 7: Demo Markdown vs Texto Plano (5 min, slides 13-14)

### Slide 13: Demo en Vivo (3 min)

#### Preparacion
Tener lista una sesion de Claude o ChatGPT. Preparar dos prompts con el mismo pedido:

**Prompt texto plano:**
"Necesito que hagas una funcion que valide emails y que devuelva true o false y que maneje los casos de arroba faltante y dominios invalidos y que sea en TypeScript y que incluya tests"

**Prompt markdown:**
```
## Tarea
Crear funcion de validacion de email en TypeScript

## Requisitos
- Devolver `true` o `false`
- Validar presencia de `@`
- Validar dominio valido
- Manejar edge cases

## Entregables
- Funcion principal
- Tests unitarios
```

#### Guion Sugerido
> "Vamos a hacer un ejercicio en vivo. Voy a enviar el mismo pedido a la IA en dos formatos diferentes, y vamos a comparar las respuestas."

> "Primero, el texto plano..." (enviar y esperar respuesta)

> "Ahora, el mismo pedido pero con estructura markdown..." (enviar y esperar respuesta)

> "Veamos las diferencias..."

#### Si la Demo Falla o las Respuestas son Similares
> "A veces las respuestas son similares porque la IA es lo suficientemente inteligente para entender ambos formatos. Pero noten que con la version estructurada, la respuesta tambien tiende a ser mas estructurada. Y cuando los pedidos son mas complejos, con 10 o 15 requisitos, la diferencia se nota mucho mas."

### Slide 14: Discusion de Resultados (2 min)

#### Guion Sugerido
> "Que diferencias notaron? La respuesta con markdown fue mas completa? Mas organizada? Cubrio todos los requisitos?"

Dejar que el grupo comente por 1-2 minutos. Puntos a destacar si no los mencionan:
- La respuesta markdown suele ser mas estructurada
- Tiende a cubrir todos los puntos de la lista
- El codigo suele estar mejor organizado
- Los tests suelen ser mas completos

> "La leccion es simple: cuando le piden algo complejo a la IA, estructuren el pedido. No necesitan ser expertos en markdown. Un titulo y una lista de requisitos ya hacen una gran diferencia."

#### Posibles Preguntas del Publico
- **"Y si el pedido es simple?"** -> "Si es algo sencillo como 'explica que es X', texto plano esta bien. La estructura importa mas cuando hay multiples requisitos o pasos."
- **"Hay algun template que podamos usar?"** -> "En el Lab 3 vamos a ver como crear archivos de configuracion que definen instrucciones permanentes. Eso es aun mas poderoso que markdown en un mensaje."

### Transicion
> "Con eso cerramos la parte practica. Recapitulemos lo que vimos hoy..."

---

## Seccion 8: Resumen y Cierre (2 min, slide 15)

### Puntos Clave del Resumen
1. El contexto es la "pizarra" de la IA -- tiene un limite fijo
2. Cada herramienta tiene una ventana de contexto diferente (8K a 1M tokens)
3. La compactacion resume lo viejo para seguir trabajando
4. Markdown ayuda a la IA a entender mejor tu solicitud

### Guion Sugerido
> "Para cerrar el Lab 2, quiero que se queden con cuatro ideas clave."

> "Primera: el contexto es la pizarra de la IA, y tiene un limite. Todo lo que le dicen se escribe en esa pizarra, y cuando se llena, se borra lo mas antiguo."

> "Segunda: cada herramienta tiene un tamano de pizarra diferente. Claude Code tiene la pizarra mas grande — hasta un millon de tokens. Copilot crecio mucho con su agent mode, pero sigue por debajo. Saber esto les ayuda a elegir la herramienta correcta para cada tarea."

> "Tercera: la compactacion es el mecanismo que tiene la IA para sobrevivir cuando la pizarra se llena. Resume lo viejo para poder seguir. Es util, pero puede hacer que la IA olvide instrucciones del inicio."

> "Y cuarta: la forma en que le hablan a la IA importa. Un mensaje con estructura, aunque sea basica, produce mejores respuestas que un parrafo corrido."

> "En el proximo lab vamos a hablar de agentes, skills y comandos. Vamos a ver como las IAs pueden hacer cosas por si solas, no solo responder preguntas. Es donde la cosa se pone realmente interesante."

> "Alguna pregunta antes de pasar a la parte abierta?"

---

## Seccion 9: Tiempo Abierto (20 min)

### Dinamica Sugerida
Los 20 minutos restantes son flexibles. Algunas opciones:

#### Opcion A: Preguntas y Respuestas Libre
- Abrir el espacio para cualquier pregunta del equipo
- Mantener las respuestas concisas para cubrir mas preguntas
- Si una pregunta es muy especifica, ofrecer responderla despues de la sesion
- Retomar preguntas pendientes del Lab 1 si las hubo

#### Opcion B: Ejercicio Practico de Markdown
- Pedir al grupo que escriban un prompt en texto plano para una tarea de su dia a dia
- Luego que lo reescriban en markdown
- Comparar las versiones y enviar la version markdown a la IA para ver el resultado
- Esto refuerza el aprendizaje practico de la sesion

#### Opcion C: Exploracion de Ventanas de Contexto
- Abrir Claude Code y mostrar como se ve el indicador de contexto
- Mostrar como se puede ver cuanto contexto queda disponible
- Si tienen acceso, comparar con Copilot en VS Code para ver la diferencia

#### Opcion D: Combinacion
- 10 min de preguntas y respuestas
- 10 min de ejercicio practico de markdown

### Preguntas Frecuentes que Pueden Surgir

**"Si la pizarra tiene limite, para que sirve subir archivos grandes?"**
> "Excelente pregunta. Subir archivos grandes consume contexto, pero es util cuando la IA necesita entender la estructura completa de algo. La clave es ser selectivo: no subir todo el proyecto, sino los archivos relevantes para la tarea. Claude Code es inteligente para leer solo lo necesario."

**"Puedo controlar que se compacta y que no?"**
> "En general no tienes control directo sobre el proceso de compactacion. Pero si puedes influir: lo que pones en archivos de configuracion como CLAUDE.md se carga fuera del historial de conversacion, asi que nunca se compacta. En el Lab 3 vamos a ver como aprovechar esto."

**"Hay diferencia entre tokens en ingles y en espanol?"**
> "Si, bastante. Una palabra en ingles suele ser 1 token, pero en espanol puede ser 1.5 o 2 tokens. Esto significa que el mismo mensaje en espanol consume mas contexto que en ingles. Para prompts largos o instrucciones de sistema, escribir en ingles te da mas espacio."

**"Copilot inline solo ve el archivo actual, entonces como sabe del resto del proyecto?"**
> "No lo sabe, y por eso a veces sugiere cosas que no encajan. Para sugerencias que necesitan contexto del proyecto, el agent mode o el chat de Copilot son mejores opciones. El inline es perfecto para completar la linea actual o una funcion corta."

**"Entonces markdown es como 'hablar el idioma' de la IA?"**
> "Exacto, es una muy buena forma de verlo. Es como cuando viajas a otro pais: puedes comunicarte con senales, pero si hablas algo del idioma local, la comunicacion es mucho mejor. Markdown es el 'idioma local' de la IA."

---

## Notas Finales para el Moderador

### Ritmo y Tono
- Mantener un tono conversacional, no de catedra
- Este lab tiene mas contenido conceptual que el anterior -- es importante hacer pausas para que el grupo procese
- Las analogias (pizarra y cuaderno) son los momentos clave: tomarse su tiempo ahi
- La demo de markdown es el momento mas interactivo -- dejar que el grupo participe
- Si ves caras de confusion despues de hablar de tokens, volver a la analogia de la pizarra

### Si te quedas sin tiempo
- La seccion de ventanas de contexto (slides 6-8) se puede resumir en una tabla comparativa rapida
- La demo de markdown (slides 13-14) se puede simplificar mostrando los prompts sin enviarlos a la IA en vivo
- La analogia del cuaderno se puede fusionar con la explicacion de compactacion en un solo momento
- Nunca sacrifiques el tiempo abierto -- es donde el equipo mas aprende

### Si te sobra tiempo
- Profundiza en la demo de markdown: pedir al grupo que sugieran tareas para probar
- Muestra un ejemplo real de compactacion en Claude Code si tienes una sesion larga disponible
- Habla de como los archivos de configuracion (CLAUDE.md) ayudan a "fijar" contexto -- adelanto del Lab 3
- Comparte experiencias personales de cuando la IA "olvido" algo por limite de contexto

### Errores comunes a evitar
- No decir "la IA recuerda" sin aclarar que es temporal -> decir "la IA tiene disponible en su contexto"
- No presentar la compactacion como un defecto -> es un mecanismo util, no un bug
- No generar ansiedad sobre los limites de contexto -> enfocarse en que se pueden manejar con buenas practicas
- No asumir que todos saben que es markdown -> explicar lo basico antes de profundizar
- No comparar herramientas de forma que una parezca "mala" -> cada una tiene su caso de uso

### Distribucion del Tiempo - Resumen Rapido

| Seccion | Duracion | Acumulado |
|---------|----------|-----------|
| Bienvenida | 1 min | 1 min |
| Recap Lab 1 | 2 min | 3 min |
| Que es el contexto | 7 min | 10 min |
| Ventanas de contexto | 7 min | 17 min |
| Compactacion | 5 min | 22 min |
| Markdown para la IA | 5 min | 27 min |
| Demo markdown vs texto plano | 5 min | 32 min |
| Resumen y cierre | 2 min | 34 min |
| Margen/transiciones | 6 min | 40 min |
| **Tiempo abierto** | **20 min** | **60 min** |

### Checklist Post-Sesion
- [ ] Anotar las preguntas que surgieron para preparar los proximos labs
- [ ] Registrar si el grupo entendio la analogia de la pizarra (usarla como referencia en labs futuros)
- [ ] Identificar si el grupo tiene experiencia con markdown o si necesita refuerzo
- [ ] Anotar si la demo funciono bien para replicarla o ajustarla en futuros labs
- [ ] Guardar los prompts usados en la demo para referencia del equipo
