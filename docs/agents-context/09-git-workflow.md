# Contexto de flujo de trabajo con Git

## Propósito

Definir ramas, commits, revisiones y releases. Aplica a todos los agentes que modifiquen el repositorio.

## Regla principal

No hacer commit, push, merge ni abrir PR salvo que se solicite explícitamente.

## Ramas

- `main`: rama estable y desplegable.
- Ramas de trabajo: prefijo según tipo.
  - `feat/<descripcion-corta>`
  - `fix/<descripcion-corta>`
  - `chore/<descripcion-corta>`
  - `docs/<descripcion-corta>`
  - `refactor/<descripcion-corta>`
- Usar `kebab-case` en descripciones.
- Ramas cortas y con un objetivo claro.

## Commits

Formato sugerido (Conventional Commits):

```
<tipo>(<alcance opcional>): <descripción en imperativo>

[cuerpo opcional]

[pie opcional]
```

Tipos: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`, `perf`, `build`, `ci`.

- Descripción en presente e imperativo, en español, sin punto final.
- Un commit por cambio lógico.
- Cuerpo para explicar el porqué cuando no sea evidente.
- No commitear secretos, artefactos ni archivos temporales.

## Antes de commitear

1. Revisar `git status`.
2. Revisar `git diff` de lo que se va a incluir.
3. Verificar que no haya secretos ni archivos generados.
4. Ejecutar lint, typecheck y tests.
5. Stagear solo archivos intencionales.

## Pull requests

- Título claro y alcance acotado.
- Descripción con contexto, cambio y verificación.
- Incluir capturas si hay cambios visuales.
- Enlazar issues relacionados.
- Mantener el PR actualizado con la rama base.
- Responder a comentarios o marcar resolución.

Plantilla sugerida:

```markdown
## Qué
Resumen del cambio.

## Por qué
Motivación y contexto.

## Cómo se verificó
Comandos ejecutados y resultados.

## Riesgos
Impacto y plan de rollback.
```

## Revisión

- Revisar el cambio completo, no solo el último commit.
- Verificar comportamiento, tests, seguridad y consistencia.
- Señalar problemas y también mejoras opcionales por separado.
- Aprobar solo cuando el pipeline esté en verde.

## Releases

- Versionado semántico cuando aplique.
- Etiquetas `vMAJOR.MINOR.PATCH`.
- Registrar cambios relevantes (changelog).
- No reescribir historia publicada sin coordinación.

## Checklist

- [ ] Rama con prefijo y nombre descriptivo.
- [ ] Commits atómicos y con mensaje claro.
- [ ] Sin secretos ni artefactos generados.
- [ ] Lint, typecheck y tests en verde.
- [ ] PR con contexto y verificación.
- [ ] Cambios solicitados atendidos.

## Pendientes

- Definir protección de ramas.
- Definir plantilla oficial de PR.
- Definir estrategia de versionado.
