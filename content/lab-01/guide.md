# Guía del Moderador - Lab 01: Introducción a la Inteligencia Artificial

## Información General
- **Duración**: 40 minutos de presentación + 20 minutos abiertos
- **Audiencia**: Equipo de desarrollo (distintos niveles de experiencia con IA)
- **Objetivo**: Que el equipo comprenda qué es la IA, cómo funciona a nivel conceptual, y por qué a veces se equivoca (alucinación)
- **Materiales**: Presentación Slidev, conexión a internet para demos opcionales

## Preparación Previa
- [ ] Tener la presentación corriendo (`npm run dev:lab01`)
- [ ] Verificar que los slides se ven correctamente en el proyector
- [ ] Tener ejemplos de alucinación preparados por si preguntan
- [ ] Preparar una anécdota personal sobre uso de IA
- [ ] Tener agua disponible (40 min hablando)

---

## Sección 1: Bienvenida y Portada (1 min)

### Puntos Clave
- Dar la bienvenida al AI Laboratory
- Explicar que es una serie de 4 sesiones
- Este es el Lab 1: sentaremos las bases

### Guión Sugerido
> "Bienvenidos al AI Laboratory. Esta es la primera de cuatro sesiones donde vamos a explorar la Inteligencia Artificial juntos. Hoy vamos a arrancar con lo fundamental: entender qué es realmente la IA, cómo funciona por dentro, y por qué a veces nos da respuestas que suenan bien pero están mal."

### Transición
> "Pero antes de arrancar con la teoría, quiero saber qué tanto saben ustedes..."

---

## Sección 2: Preguntas Interactivas (11 min total)

### Pregunta 1: "¿Todos conocemos qué es IA?" (3 min)

#### Puntos Clave
- Es una pregunta para romper el hielo y medir el nivel del grupo
- No hay respuestas incorrectas aquí
- Escuchar activamente y anotar mentalmente el nivel del grupo

#### Guión Sugerido
> "Arranquemos con algo básico: ¿todos conocemos qué es la Inteligencia Artificial? No me refiero a la definición de Wikipedia, sino a lo que ustedes entienden, a lo que les viene a la mente cuando escuchan IA."

#### Si nadie responde
> "Piensen en lo que usan en el día a día... ¿Alguien ha hablado con Siri? ¿Ha usado el autocorrect del celular? Eso ya es IA en acción."

#### Posibles Respuestas del Público
- **"Robots"** → "Sí, los robots pueden usar IA, pero la IA es mucho más que robots físicos. La mayoría de la IA hoy vive en software."
- **"ChatGPT"** → "Exacto, ChatGPT es un ejemplo muy conocido. Es lo que llamamos IA generativa."
- **"Algo que piensa como humano"** → "Esa es una creencia común. Vamos a ver hoy por qué no es exactamente así, aunque a veces lo parece."

### Pregunta 2: "¿Qué IAs conocen?" (3 min)

#### Guión Sugerido
> "¿Qué herramientas de IA conocen? No importa si las han usado o solo las han escuchado nombrar."

#### Puntos a Destacar
Ir anotando mentalmente (o en una lista mental) las que mencionen. Las más comunes:
- ChatGPT (OpenAI)
- Claude (Anthropic)
- Gemini (Google)
- Copilot (GitHub/Microsoft)
- Midjourney / DALL-E (generación de imágenes)
- Siri, Alexa (asistentes de voz)

> "Fíjense cuántas hay. Y todas tienen algo en común: aprenden de datos. Eso es lo que las hace 'inteligentes'."

### Pregunta 3: "¿Quiénes han utilizado una IA?" (2 min)

#### Guión Sugerido
> "Levanten la mano los que han utilizado alguna IA, ya sea para trabajo, para algo personal, o simplemente por curiosidad."

#### Seguimiento
> "¿Para qué la usaron? ¿Les fue bien o tuvieron alguna experiencia frustrante?"

Dejar que 2-3 personas compartan brevemente. Esto genera conexión con el tema.

### Pregunta 4: "¿Creen que la IA nos reemplazará?" (3 min)

#### Guión Sugerido
> "Esta es la gran pregunta que todos se hacen: ¿la IA va a reemplazar nuestros trabajos?"

#### Puntos a Destacar
- No dar una respuesta definitiva aquí, es pregunta abierta
- Si el grupo se inclina a "sí": "Es un miedo válido. Vamos a ver hoy cómo funciona la IA por dentro, y van a entender por qué todavía nos necesita."
- Si el grupo se inclina a "no": "Buena perspectiva. Yo diría que la IA no reemplaza, pero sí cambia cómo trabajamos."
- Frase clave: **"La IA no va a reemplazar a los desarrolladores, pero los desarrolladores que usen IA van a reemplazar a los que no."**

#### Transición
> "Muy bien, con eso ya tengo una idea de dónde estamos como grupo. Ahora sí, entremos en materia..."

---

## Sección 3: Introducción a la IA (5 min, slides 6-7)

### Slide 6: Qué es la IA

#### Puntos Clave
- La IA es software que aprende patrones de datos masivos
- No "piensa" como un humano - encuentra correlaciones estadísticas
- La IA que usamos hoy es "IA estrecha" (especializada en tareas específicas)
- No existe la IA general (la que ven en películas)

#### Guión Sugerido
> "La Inteligencia Artificial, en términos simples, es software que aprende patrones de enormes cantidades de datos. Cuando ustedes le preguntan algo a ChatGPT, no está 'pensando'. Está haciendo algo más parecido a: 'basándome en todo lo que he leído, ¿cuál es la respuesta más probable a esta pregunta?'"

> "Un punto importante: lo que usamos hoy se llama IA Estrecha o ANI. Es muy buena haciendo UNA cosa - traducir, generar código, responder preguntas. Pero no puede hacer TODO. No es la IA de las películas de ciencia ficción."

#### Datos Extra para Preguntas
- GPT-4 fue entrenado con ~13 trillones de tokens (básicamente gran parte del internet)
- Claude fue entrenado con una mezcla de texto público y datos curados
- Un humano lee ~1 millón de palabras al año. Estos modelos "leyeron" el equivalente a miles de millones de años de lectura humana

### Slide 7: Tipos de IA e Historia Breve

#### Puntos Clave
- Tres tipos: IA Estrecha (hoy), IA General (hipotética), Superinteligencia (teórica)
- Timeline rápido: 1950 (Turing) → 2022 (ChatGPT) → 2024-2026 (agentes de IA)

#### Guión Sugerido
> "Hagamos un recorrido rápido. En 1950, Alan Turing preguntó '¿pueden pensar las máquinas?'. Tuvieron que pasar más de 70 años para que viéramos algo que se acerca a una respuesta. En 2022, ChatGPT explotó y todo cambió. Hoy, en 2026, ya hablamos de agentes de IA que pueden ejecutar tareas completas por nosotros."

#### Transición
> "Pero, ¿cómo funciona esto realmente? ¿Qué pasa por dentro cuando le haces una pregunta a la IA?"

---

## Sección 4: ¿Cómo Funciona la IA? (7 min, slides 8-10)

### Slide 8: Entrenamiento

#### Puntos Clave
- Se alimenta con cantidades masivas de texto (libros, web, código, documentación)
- El modelo aprende patrones: "después de X, suele venir Y"
- Ajusta miles de millones de parámetros
- NO memoriza texto literal - aprende distribuciones de probabilidad

#### Guión Sugerido
> "Imaginen que le dan a un niño millones de libros para leer. Después de leer todo eso, el niño no memoriza cada frase, pero entiende cómo funciona el lenguaje. Sabe que después de 'buenos' probablemente viene 'días'. Sabe que un correo electrónico empieza de cierta manera."

> "La IA hace algo similar, pero a una escala que es difícil de imaginar. GPT-4, por ejemplo, tiene más de un trillón de parámetros. Cada parámetro es como un 'dial' que se ajustó durante el entrenamiento para que las respuestas sean lo más precisas posible."

### Slide 9: Inferencia y Tokens

#### Puntos Clave
- Tokenización: el texto se divide en tokens (~0.75 palabras en inglés, ~0.5 en español)
- La IA genera respuesta token por token
- Cada token generado se basa en todos los tokens anteriores
- Es un proceso de predicción probabilística

#### Guión Sugerido
> "Cuando ustedes le escriben algo a la IA, lo primero que hace es dividir su texto en 'tokens'. Un token es como un pedazo de palabra. En español, una palabra puede ser 1 o 2 tokens. Luego, la IA genera su respuesta un token a la vez, eligiendo siempre el más probable."

> "Es como el autocomplete del celular, pero enormemente más sofisticado. Tu celular predice la siguiente palabra. La IA predice la siguiente palabra con una comprensión profunda del contexto."

### Slide 10: De Datos a Respuesta (diagrama visual)

#### Puntos Clave
- Flujo: Prompt → Tokenización → Red neuronal → Generación token a token → Respuesta
- Cada paso es una transformación matemática
- No hay "comprensión" real, solo patrones estadísticos

#### Guión Sugerido
> "Si tuviera que resumir cómo funciona la IA en una frase: es una máquina de predecir la siguiente palabra, entrenada con todo el texto que existe en internet."

#### Transición
> "Ahora, si la IA solo predice la siguiente palabra más probable, ¿realmente inventa cosas nuevas?"

---

## Sección 5: ¿La IA Inventa? (2 min, slide 11)

### Guión Sugerido
> "¿Ustedes creen que la IA inventa? Cuando le pides que escriba un poema o genere código nuevo, ¿está creando algo original?"

#### Puntos a Destacar
- La IA no "inventa" en el sentido creativo humano
- Recombina patrones de formas nuevas
- Analogía del chef: conoce miles de recetas y puede crear una nueva combinando ingredientes de formas que no ha visto exactamente
- La "creatividad" de la IA es recombinación estadística sofisticada

> "Es como un chef que ha probado miles de platos. No inventa ingredientes nuevos, pero puede combinar los que conoce de formas que nunca se han visto. El resultado puede ser sorprendente, pero siempre está basado en lo que ya existía."

#### Transición
> "Y aquí viene lo interesante: si la IA no realmente 'sabe' cosas, sino que predice respuestas probables, ¿qué pasa cuando no tiene suficiente información? Ahí es donde entramos en un concepto clave..."

---

## Sección 6: Alucinación en la IA (5 min, slides 12-13)

### Slide 12: Qué es la Alucinación - Concepto

#### Puntos Clave
- Alucinación: cuando la IA genera información que suena convincente pero es incorrecta
- La IA no "sabe" que está equivocada
- No miente intencionalmente - simplemente genera lo más probable
- La confianza del modelo NO correlaciona con la precisión

#### Guión Sugerido
> "La alucinación es cuando la IA te da una respuesta que suena perfectamente razonable, está bien redactada, tiene la estructura correcta... pero es completamente falsa."

> "¿Por qué pasa esto? Porque la IA no 'sabe' nada en el sentido humano. No tiene un mecanismo interno que diga 'esto lo sé seguro' vs 'esto me lo estoy inventando'. Para ella, todo es una predicción de probabilidad."

### Slide 13: Ejemplos de Alucinación

#### Puntos Clave
- Citar papers académicos que no existen
- Inventar funciones de una API
- Dar fechas o estadísticas incorrectas con total confianza
- Mezclar hechos de diferentes temas

#### Guión Sugerido
> "Les doy un ejemplo real: si le pides a la IA que cite papers sobre un tema, puede inventar títulos de papers, autores, e incluso DOIs que no existen. Todo suena legítimo, pero cuando vas a buscar la fuente... no existe."

> "En programación pasa algo similar. La IA puede sugerirte una función de una librería que tiene el nombre correcto, los parámetros correctos, pero esa función no existe en esa versión de la librería."

#### Posibles Preguntas del Público
- **"¿Entonces no podemos confiar en la IA?"** → "Sí podemos, pero con verificación. Es como confiar en un colega nuevo: su trabajo es generalmente bueno, pero revisas antes de enviarlo al cliente."
- **"¿Hay formas de reducir la alucinación?"** → "Sí: dar más contexto, ser específico en el prompt, y pedirle que cite fuentes verificables. Veremos más de esto en los próximos labs."

#### Transición
> "Para entender mejor por qué pasa esto, les voy a contar una analogía que creo que lo explica perfectamente..."

---

## Sección 7: Analogía del Compañero que No Tomó Apuntes (5 min, slides 14-15)

### Slide 14: La Analogía - Parte 1

#### Guión Sugerido
> "Imaginen que están en la universidad. Tienen un compañero que NUNCA tomó apuntes en ninguna clase. Pero estuvo presente en TODAS las clases. Escuchó todo. No se durmió en ninguna."

> "Ahora, antes del examen, le preguntan: 'Oye, ¿qué dijo el profesor sobre tal tema?'"

> "¿Qué pasa?"

Dar un momento para que el grupo responda. Luego continuar:

> "El compañero recuerda el tema general. Puede reconstruir la idea principal. Te da una explicación que suena bastante bien..."

### Slide 15: La Analogía - Parte 2

#### Guión Sugerido
> "PERO... los detalles específicos los 'rellena' con lo que le parece más probable. Si el profesor dijo una fecha, tu compañero dice una fecha... pero probablemente no es la correcta. Si el profesor citó un autor, tu compañero dice un nombre... pero puede que se lo haya inventado."

> "Y lo peor: tu compañero te dice todo esto con TOTAL confianza. No dice 'creo que fue tal fecha'. Dice 'fue el 15 de marzo'. Sin dudar."

> "Eso es EXACTAMENTE lo que hace la IA. Absorbe enormes cantidades de información, entiende los patrones y la estructura, pero cuando necesita un dato específico que no 'recuerda' bien, genera lo que estadísticamente encaja mejor."

#### Frase de Cierre de la Analogía
> **"La lección es simple: siempre verifica los datos específicos que te da la IA. Especialmente números, fechas, citas y referencias técnicas."**

#### Posibles Preguntas
- **"¿Y si le dices que no invente?"** → "Puedes pedirle que diga 'no sé' cuando no esté segura, y ayuda un poco. Pero no elimina el problema completamente."

---

## Sección 8: Resumen y Cierre (2 min, slide 16)

### Puntos Clave del Resumen
1. La IA es software que aprende patrones de datos (no piensa)
2. Funciona prediciendo la siguiente palabra más probable
3. No inventa, recombina patrones existentes
4. Alucina: genera respuestas convincentes pero incorrectas
5. Como el compañero sin apuntes: sabe el tema pero inventa los detalles

### Guión Sugerido
> "Para cerrar el Lab 1, quiero que se queden con estas ideas clave: la IA no piensa, predice. No inventa, recombina. Y cuando no tiene la información, la genera con confianza... aunque esté mal."

> "En el próximo lab vamos a entrar en un tema fascinante: el contexto. ¿Cómo hace la IA para 'recordar' lo que le dijiste? ¿Cuánta información puede manejar a la vez? ¿Y qué pasa cuando llega al límite."

> "¿Alguna pregunta antes de pasar a la parte abierta?"

---

## Sección 9: Tiempo Abierto (20 min)

### Dinámica Sugerida
Los 20 minutos restantes son flexibles. Algunas opciones:

#### Opción A: Preguntas y Respuestas Libre
- Abrir el espacio para cualquier pregunta del equipo
- Mantener las respuestas concisas para cubrir más preguntas
- Si una pregunta es muy específica, ofrecer responderla después de la sesión

#### Opción B: Demo en Vivo
- Abrir ChatGPT o Claude en pantalla
- Pedir al grupo que sugieran preguntas para la IA
- Mostrar en tiempo real cómo responde y buscar un caso de alucinación
- Ejemplo: pedirle que cite papers sobre un tema oscuro y verificar si existen

#### Opción C: Discusión Guiada
- "¿En qué situaciones de su trabajo diario creen que la IA les sería más útil?"
- "¿Qué les da miedo o desconfianza de usar IA en su trabajo?"
- "¿Qué les gustaría aprender en los próximos labs?"

#### Opción D: Combinación
- 10 min de preguntas y respuestas
- 10 min de demo en vivo

### Preguntas Frecuentes que Pueden Surgir

**"¿Cuál IA es mejor, ChatGPT o Claude?"**
> "Depende del caso de uso. ChatGPT es muy bueno para tareas generales y tiene plugins. Claude tiende a ser más preciso en tareas de análisis y código largo. En los próximos labs vamos a explorar cómo sacar el mejor provecho de cada una."

**"¿La IA puede ver mi código si lo pego en el chat?"**
> "Excelente pregunta de seguridad. Sí, cuando pegas código en ChatGPT o Claude, ese texto pasa por sus servidores. Las versiones de pago generalmente no usan tus datos para entrenamiento, pero es importante revisar las políticas de cada herramienta. Para código sensible, hay opciones locales que veremos más adelante."

**"¿Cuánto cuesta usar IA?"**
> "Hay opciones gratuitas con limitaciones (ChatGPT Free, Claude Free). Las versiones de pago rondan los $20 USD/mes. Para uso vía API el costo depende del volumen. Es una inversión que generalmente se paga sola en productividad."

**"¿La IA puede generar código en producción directamente?"**
> "Técnicamente sí, pero no debería sin revisión humana. La IA es excelente para generar borradores de código, pero siempre necesita revisión, testing, y validación. Es un acelerador, no un reemplazo del proceso de desarrollo."

**"¿Qué pasa con la propiedad intelectual del código generado por IA?"**
> "Es un tema legal que todavía se está definiendo. En general, el código generado por IA no tiene un dueño claro en términos de copyright. Para uso empresarial, es importante revisar los términos de servicio de cada herramienta y las políticas internas de la empresa."

---

## Notas Finales para el Moderador

### Ritmo y Tono
- Mantener un tono conversacional, no de cátedra
- No apurarse. Es mejor cubrir menos contenido con claridad que correr por todos los slides
- Hacer pausas después de conceptos importantes para que el grupo procese
- Sonreír y mantener contacto visual con diferentes personas del grupo
- Si alguien hace una pregunta que se responde más adelante, decir: "Excelente pregunta, la vamos a cubrir en unos minutos"

### Si te quedas sin tiempo
- Prioriza las preguntas interactivas iniciales (romper hielo es clave)
- La analogía del compañero se puede resumir en 1 slide si es necesario
- El resumen se puede hacer verbalmente sin slide
- Nunca sacrifiques el tiempo abierto - es donde el equipo más aprende

### Si te sobra tiempo
- Profundiza en las preguntas del público
- Muestra un ejemplo en vivo de alucinación (pedir a una IA algo verificable)
- Pregunta: "¿En qué situaciones de su trabajo diario creen que la IA les sería más útil?"
- Comparte una anécdota personal sobre una experiencia con IA (buena o mala)

### Errores comunes a evitar
- No decir "la IA piensa" o "la IA entiende" → decir "la IA genera" o "la IA predice"
- No prometer que la IA "siempre funciona" → ser honesto sobre limitaciones
- No menospreciar a quienes no han usado IA → todos empezamos desde algún punto
- No entrar en debates técnicos profundos sobre arquitectura de redes neuronales → mantenerlo conceptual
- No comparar IA con humanos de forma que genere ansiedad → enfocarse en que es una herramienta

### Distribución del Tiempo - Resumen Rápido

| Sección | Duración | Acumulado |
|---------|----------|-----------|
| Bienvenida | 1 min | 1 min |
| Preguntas interactivas | 11 min | 12 min |
| Introducción a la IA | 5 min | 17 min |
| Cómo funciona la IA | 7 min | 24 min |
| ¿La IA inventa? | 2 min | 26 min |
| Alucinación | 5 min | 31 min |
| Analogía del compañero | 5 min | 36 min |
| Resumen y cierre | 2 min | 38 min |
| Margen/transiciones | 2 min | 40 min |
| **Tiempo abierto** | **20 min** | **60 min** |

### Checklist Post-Sesión
- [ ] Anotar las preguntas que surgieron para preparar los próximos labs
- [ ] Registrar el nivel general del grupo (principiante/intermedio/avanzado)
- [ ] Identificar quiénes mostraron más interés (posibles champions de IA en el equipo)
- [ ] Anotar temas que quedaron pendientes para la sección abierta del próximo lab
