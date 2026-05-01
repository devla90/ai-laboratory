# Demo: Markdown vs Texto Plano

## Objetivo
Mostrar al equipo cómo la estructura del prompt afecta la calidad de la respuesta de la IA.

## Instrucciones para el Moderador
1. Abrir cualquier herramienta de IA (Claude, ChatGPT, etc.)
2. Enviar el **Prompt A** (texto plano) y mostrar la respuesta
3. Abrir una nueva conversación
4. Enviar el **Prompt B** (markdown) y mostrar la respuesta
5. Comparar lado a lado con el equipo

---

## Prompt A: Texto Plano

Copiar y pegar tal cual:

```
Necesito que me hagas una función en TypeScript que valide direcciones de email y que devuelva true si el email es válido o false si no lo es y que maneje los casos donde falta la arroba y donde el dominio no es válido y que no sea sensible a mayúsculas o minúsculas y también que no acepte espacios en blanco
```

---

## Prompt B: Markdown Estructurado

Copiar y pegar tal cual:

```
## Tarea
Crear una función de validación de email en TypeScript

## Requisitos funcionales
- Devolver `true` si el email es válido, `false` si no
- Validar presencia de `@`
- Validar que el dominio sea válido
- Case insensitive (no sensible a mayúsculas/minúsculas)
- Rechazar emails con espacios en blanco

## Firma esperada
`function isValidEmail(email: string): boolean`
```

---

## Qué observar en las respuestas

| Aspecto | Texto Plano | Markdown |
|---------|-------------|----------|
| ¿Cubrió todos los requisitos? | Puede saltarse alguno | Generalmente cubre todos |
| ¿Está bien organizada? | Variable | Más estructurada |
| ¿Incluyó tests o ejemplos? | Menos probable | Más probable |
| ¿Explicó su razonamiento? | Puede ser desordenado | Sigue la estructura del prompt |

## Puntos de discusión con el equipo
- ¿Cuál respuesta les parece más completa?
- ¿Cuál sería más fácil de llevar a producción?
- ¿Cuánto esfuerzo extra toma escribir el prompt en markdown?
- ¿Vale la pena esos 30 segundos extra de estructura?
