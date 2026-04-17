---
name: agents-skills-commands
description: >
  Conocimiento sobre agentes, skills y comandos en herramientas de IA.
  Conceptos, analogías y beneficios. Para el Lab 3.
user-invocable: true
disable-model-invocation: false
---

# Agents, Skills & Commands - Conocimiento para Lab 3

## Cuando se Activa
- Generar contenido del Lab 3
- Explicar conceptos de agentes, skills o comandos

## Qué son los Agentes

Un agente de IA es una instancia especializada con un rol, conocimiento y comportamiento definidos. En vez de tener una IA genérica, creas "expertos" para tareas específicas.

### Analogía: Empleados Especializados
Imagina una empresa donde en vez de tener un empleado que hace todo (y a veces se equivoca), tienes:
- Un arquitecto que solo diseña estructuras
- Un auditor de seguridad que solo revisa vulnerabilidades
- Un redactor que solo escribe documentación

Cada uno sabe exactamente qué hacer porque tiene instrucciones claras y un área de expertise definida. Un agente de IA funciona igual.

### Componentes de un Agente
- **Nombre**: identificador único
- **Modelo**: qué modelo de IA usa (opus para tareas complejas, sonnet para tareas rápidas)
- **Descripción**: cuándo debe activarse
- **Prompt del sistema**: sus instrucciones, conocimiento y reglas
- **Skills**: conocimiento modular que puede cargar

## Qué son los Skills

Un skill es un paquete de conocimiento reutilizable que un agente puede cargar cuando lo necesita. Son como "módulos de entrenamiento" que le dan expertise específica.

### Analogía: Manuales de Entrenamiento
Imagina que cada empleado tiene acceso a una estantería de manuales. Cuando necesita hacer algo específico, toma el manual correspondiente, lo lee, y aplica lo que dice. No necesita memorizar todo - solo carga lo que necesita cuando lo necesita.

### Características
- **Modulares**: cada skill cubre un tema específico
- **Reutilizables**: múltiples agentes pueden usar el mismo skill
- **Ligeros**: se cargan bajo demanda, no todos a la vez
- **Versionables**: se pueden actualizar sin cambiar el agente

## Qué son los Comandos

Un comando es un atajo que ejecuta una tarea predefinida. En vez de escribir instrucciones largas cada vez, defines un comando una vez y lo invocas con una palabra.

### Analogía: Macros o Atajos de Teclado
Como Ctrl+C para copiar: una acción simple que desencadena una operación compleja. En vez de seleccionar, ir al menú, buscar copiar... presionas dos teclas.

### Características
- **Rápidos**: una palabra ejecuta múltiples pasos
- **Consistentes**: siempre hacen lo mismo
- **Parametrizables**: aceptan argumentos (ej: /generate-lab 01)

## Cómo se Combinan

```
Comando ──triggers──▶ Agente ──loads──▶ Skills
  │                      │                 │
  │ "/generate-lab 01"   │ lab-conductor   │ slidev-futuristic
  │                      │                 │ color-system
  │                      │                 │ ai-fundamentals
  └──────────────────────┴─────────────────┘
                    │
                    ▼
              Output (slides.md)
```

## Beneficios

### Consistencia
Sin agentes: cada vez que pides algo, la calidad varía según cómo lo pidas.
Con agentes: el resultado sigue las mismas reglas siempre.

### Velocidad
Sin comandos: escribir 10 líneas de instrucciones cada vez.
Con comandos: `/generate-lab 01` y listo.

### Calidad
Sin skills: la IA usa su conocimiento general (a veces incompleto).
Con skills: la IA tiene conocimiento específico y actualizado.

### Escalabilidad
Creas un agente una vez, lo usas infinitas veces. Actualizas un skill, todos los agentes que lo usan se benefician.
