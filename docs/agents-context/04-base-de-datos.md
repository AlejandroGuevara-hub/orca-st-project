# Contexto de base de datos

## Propósito

Guiar el modelado de datos, migraciones y operaciones de persistencia. Aplica a agentes que diseñen esquemas, consultas o procesos de datos.

## Estado

- Sin motor de base de datos definido.
- Registrar motor, versión y estrategia de migraciones antes de crear esquemas.

## Principios

- El esquema es parte del contrato del sistema: cambios requieren revisión.
- Migraciones versionadas, reproducibles y reversibles cuando sea posible.
- Sin lógica de negocio en triggers o procedimientos salvo justificación.
- Integridad de datos antes que comodidad de consulta.

## Convenciones de nombres

- Tablas en `snake_case` y plural (`users`, `order_items`).
- Columnas en `snake_case` y descriptivas (`created_at`, `is_active`).
- Claves foráneas `<tabla_singular>_id`.
- Índices con prefijo `idx_`, restricciones únicas `uq_`, foráneas `fk_`.

## Columnas estándar

- `id` como clave primaria.
- `created_at` y `updated_at` con zona horaria.
- `deleted_at` si se usa borrado lógico.
- Evitar booleanos ambiguos; nombrar con `is_` o `has_`.

## Migraciones

- Una migración por cambio lógico.
- Nombres descriptivos y ordenados por fecha.
- No editar migraciones ya aplicadas en entornos compartidos.
- Probar la migración hacia adelante y, si aplica, el rollback.
- Para cambios destructivos, planificar respaldo y ventana de mantenimiento.

## Índices y rendimiento

- Indexar claves foráneas y columnas usadas en filtros u ordenamientos frecuentes.
- Evitar índices redundantes.
- Revisar planes de consulta en operaciones críticas.
- Evitar `SELECT *` en código productivo.

## Transacciones y concurrencia

- Agrupar operaciones que deban ser atómicas en una transacción.
- Definir nivel de aislamiento cuando importe.
- Manejar conflictos de concurrencia explícitamente.

## Datos y privacidad

- Minimizar datos personales almacenados.
- Definir retención y borrado.
- Cifrar datos sensibles en reposo cuando corresponda.
- No usar datos productivos reales en desarrollo sin anonimizar.

## Respaldos

- Definir frecuencia y retención de respaldos.
- Probar restauración periódicamente.
- Documentar el procedimiento de recuperación.

## Checklist antes de entregar cambios de datos

- [ ] Migración versionada y probada.
- [ ] Nombres y columnas estándar respetados.
- [ ] Índices necesarios definidos.
- [ ] Integridad referencial asegurada.
- [ ] Sin datos sensibles innecesarios.
- [ ] Plan de rollback o respaldo para cambios destructivos.

## Pendientes

- Elegir motor de base de datos.
- Definir herramienta de migraciones.
- Documentar política de respaldos y retención.
