# Contexto de seguridad

## Propósito

Establecer prácticas mínimas de seguridad para código, datos e infraestructura. Aplica a todos los agentes, con especial énfasis en backend, IA y DevOps.

## Estado

- Sin modelo de amenazas definido.
- Registrar requisitos regulatorios o de cumplimiento aplicables.

## Principios

- Mínimo privilegio por defecto.
- No confiar en ninguna entrada, incluida la del propio sistema.
- Seguridad en profundidad: varias capas, no una sola.
- Fallar de forma segura y silenciosa hacia el usuario, con detalle en logs.
- Los secretos no se commitean, no se loguean y no se comparten por chat.

## Secretos y credenciales

- Gestionar secretos con un gestor dedicado.
- Usar tokens de vida corta cuando sea posible.
- Rotar credenciales ante sospecha de filtración.
- Si un secreto se commitea: revocarlo, rotarlo y limpiar el historial.

## Autenticación y autorización

- Contraseñas con hashing fuerte y salt (Argon2id, bcrypt).
- Sesiones con expiración y revocación.
- Autorización verificada en el servidor, nunca solo en el cliente.
- Denegar por defecto; permitir explícitamente.
- Proteger endpoints sensibles con rate limiting.

## Validación de entrada

- Validar en el borde del sistema.
- Prevenir inyección: usar consultas parametrizadas, nunca concatenar SQL.
- Escapar salida según contexto (HTML, URL, JS).
- Limitar tamaños de payload y de archivos.
- Validar rutas y evitar path traversal.

## Dependencias

- Fijar versiones.
- Revisar advisories y actualizar con criterio.
- Evitar dependencias sin mantenimiento.
- Auditar antes de agregar una librería nueva.

## Datos personales

- Recoger solo lo necesario.
- Cifrar en tránsito (TLS) y en reposo cuando corresponda.
- No loggear PII ni credenciales.
- Definir retención y borrado.
- Anonimizar datos usados en desarrollo y pruebas.

## Seguridad en IA

- Tratar inputs y outputs del modelo como no confiables.
- No incluir secretos en prompts.
- Prevenir prompt injection y exfiltración de contexto.
- Ejecutar herramientas generadas en sandbox con permisos mínimos.

## Checklist de revisión de seguridad

- [ ] Sin secretos en código o logs.
- [ ] Entradas validadas y salidas escapadas.
- [ ] Autorización verificada en servidor.
- [ ] Consultas parametrizadas.
- [ ] Dependencias revisadas.
- [ ] Rate limiting en endpoints sensibles.
- [ ] Datos personales minimizados y protegidos.

## Incidentes

- Registrar fecha, impacto y alcance.
- Contener, erradicar y recuperar.
- Documentar causa raíz y acciones preventivas.

## Pendientes

- Definir modelo de amenazas.
- Definir estándar de autenticación.
- Definir requisitos de cumplimiento aplicables.
