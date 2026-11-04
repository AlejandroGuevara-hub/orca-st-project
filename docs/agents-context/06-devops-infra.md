# Contexto de DevOps e infraestructura

## Propósito

Definir entornos, pipelines de CI/CD, despliegues y observabilidad. Aplica a agentes que toquen configuración de infraestructura, automatización o releases.

## Estado

- Sin plataforma de despliegue ni CI definidos.
- Registrar proveedor, entornos y pipeline antes de automatizar.

## Principios

- Infraestructura como código cuando sea posible.
- Entornos reproducibles y equivalentes entre sí.
- Cambios pequeños, reversibles y observables.
- Los secretos nunca viven en el repositorio.
- Si no se puede medir, no está listo para producción.

## Entornos

| Entorno | Propósito | Datos | Acceso |
| --- | --- | --- | --- |
| local | Desarrollo | Sintéticos | Desarrolladores |
| staging | Validación previa | Anonimizados | Equipo |
| production | Usuarios reales | Reales | Restringido |

- Documentar variables requeridas por entorno.
- Mantener diferencias entre entornos al mínimo.

## CI

Etapas sugeridas, en orden:

1. Instalar dependencias con versiones fijadas.
2. Lint.
3. Typecheck.
4. Tests unitarios.
5. Tests de integración.
6. Build del artefacto.
7. Análisis de seguridad de dependencias.
8. Publicación del artefacto.

- Romper el pipeline ante cualquier fallo.
- Evitar pasos que dependan de estado manual.
- Cachear dependencias para acelerar.

## CD y despliegue

- Preferir despliegues incrementales o canary.
- Definir criterios de éxito y rollback.
- Automatizar migraciones con control de orden.
- Mantener historial de releases.

## Secretos

- Usar gestor de secretos del proveedor.
- Rotar credenciales periódicamente.
- Dar permisos mínimos por servicio.
- Nunca imprimir secretos en logs.

## Observabilidad

- Logs estructurados y centralizados.
- Métricas delatencia, errores y saturación.
- Trazas para flujos distribuidos cuando aplique.
- Alertas accionables, con dueño y runbook.

## Respuesta a incidentes

- Definir severidades.
- Documentar runbooks para fallos comunes.
- Registrar causa raíz y acciones correctivas.
- Comunicar estado a los afectados.

## Checklist antes de desplegar

- [ ] Pipeline en verde.
- [ ] Variables y secretos configurados en el entorno.
- [ ] Migraciones revisadas.
- [ ] Plan de rollback definido.
- [ ] Observabilidad disponible para el cambio.
- [ ] Documentación de release actualizada.

## Pendientes

- Elegir proveedor de CI y hosting.
- Definir entornos y variables.
- Definir estrategia de despliegue y rollback.
