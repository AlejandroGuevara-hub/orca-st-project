# Contexto de documentación

## Propósito

Definir cómo se escribe y organiza la documentación del proyecto. Aplica a agentes que creen READMEs, guías, ADRs o comentarios de código.

## Estado

- Documentación inicial limitada a `AGENTS.md` y este directorio.
- Idioma principal: español.

## Principios

- Documentar lo que no es obvio en el código.
- Explicar el porqué, no repetir el qué.
- Mantener la documentación cerca del código que describe.
- Preferir ejemplos concretos sobre descripciones abstractas.
- Eliminar documentación obsoleta en lugar de dejarla acumular.

## Idioma y tono

- Español claro y directo.
- Voz activa y frases cortas.
- Sin jerga innecesaria ni adornos.
- Consistencia en terminología: un concepto, un término.

## Estructura de un README

1. Qué es el proyecto y para qué sirve.
2. Requisitos previos.
3. Instalación.
4. Configuración.
5. Uso básico con ejemplos.
6. Comandos de desarrollo (build, lint, test).
7. Estructura del proyecto.
8. Cómo contribuir.
9. Licencia (si aplica).

## Guías y tutoriales

- Un objetivo por documento.
- Pasos numerados y verificables.
- Incluir resultado esperado en los pasos clave.
- Señalar requisitos y advertencias antes de la acción.

## ADRs (Architecture Decision Records)

Ubicación sugerida: `docs/adr/`.

Formato:

```markdown
# ADR-0001: Título de la decisión

## Estado
Propuesto | Aceptado | Reemplazado | Obsoleto

## Contexto
Situación y fuerzas en juego.

## Decisión
Qué se decidió y por qué.

## Consecuencias
Efectos positivos, negativos y compromisos.
```

- Un ADR por decisión relevante.
- No editar ADRs aceptados; crear uno nuevo que los reemplace.

## Documentación de código

- Comentar decisiones no evidentes y casos límite.
- No comentar lo que el código ya expresa.
- Docstrings en APIs públicas con parámetros, retorno y errores.
- Mantener comentarios y nombres sincronizados con el comportamiento real.

## Checklist de documentación

- [ ] El documento responde a una necesidad concreta.
- [ ] Pasos probados y reproducibles.
- [ ] Ejemplos actualizados con el código vigente.
- [ ] Sin enlaces rotos.
- [ ] Ubicación coherente con el resto de la documentación.

## Pendientes

- Crear README raíz cuando exista stack.
- Definir carpeta y plantilla de ADRs.
- Definir guía de contribución.
