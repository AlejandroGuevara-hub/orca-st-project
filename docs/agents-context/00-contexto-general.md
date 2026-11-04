# Contexto general para agentes

## Propósito

Este directorio centraliza el contexto que necesitan los agentes (humanos o IA) para trabajar en `orca-st-project` de forma consistente. Cada documento cubre una temática y debe leerse antes de abordar tareas de esa área.

## Estado del proyecto

- Repositorio recién inicializado.
- Sin stack, build, lint ni tests definidos todavía.
- Los documentos de este directorio son plantillas vivas: se completan y ajustan a medida que el proyecto crece.

## Cómo usar estos documentos

1. Lee `00-contexto-general.md` siempre.
2. Lee el documento de la temática que vas a tocar (por ejemplo `02-backend.md`).
3. Si una convención no está definida, propón una y documéntala aquí antes de implementarla.
4. Actualiza el documento correspondiente cuando cambien decisiones o se agregue tooling.

## Índice

| Documento | Temática |
| --- | --- |
| `00-contexto-general.md` | Contexto, índice y acuerdos base |
| `01-estilos-ui.md` | Estilos, design system y frontend visual |
| `02-backend.md` | Backend, APIs y lógica de servidor |
| `03-ia.md` | Integración de IA, prompts y evaluación |
| `04-base-de-datos.md` | Modelado de datos, migraciones e índices |
| `05-testing-qa.md` | Estrategia de pruebas y calidad |
| `06-devops-infra.md` | CI/CD, entornos y observabilidad |
| `07-seguridad.md` | Seguridad, secretos y validación |
| `08-documentacion.md` | Documentación, READMEs y ADRs |
| `09-git-workflow.md` | Ramas, commits y revisiones |

## Acuerdos base

- No hacer commit, push ni abrir PR salvo pedido explícito.
- Ejecutar lint, typecheck y tests antes de dar una tarea por terminada, una vez existan.
- No introducir dependencias sin justificar y registrar la decisión.
- Mantener `AGENTS.md` y este directorio sincronizados con la estructura real.
- Preferir cambios pequeños, revisables y con verificación asociada.

## Registro de decisiones

Agrega aquí decisiones transversales que afecten a más de un área.

| Fecha | Decisión | Motivo | Documentos afectados |
| --- | --- | --- | --- |
| - | - | - | - |

## Pendientes

- Definir stack principal.
- Definir comandos de instalación, build, lint, typecheck y test.
- Completar las plantillas de cada temática con las decisiones reales.
