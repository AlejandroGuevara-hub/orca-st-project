# Contexto de backend

## Propósito

Guiar el diseño e implementación de APIs, lógica de servidor y servicios internos. Aplica a agentes que trabajen en endpoints, dominio, integraciones o configuración.

## Estado

- Sin lenguaje ni framework de backend definido.
- Registrar la elección de stack aquí antes de implementar.

## Principios

- Separar capas: entrada (HTTP), aplicación (casos de uso), dominio e infraestructura.
- Validar en los bordes; asumir datos internos ya validados.
- Errores explícitos y consistentes.
- Sin lógica de negocio en controladores ni en la capa de persistencia.
- Configuración por entorno, nunca hardcodeada.

## Diseño de API

- Recursos en plural y sustantivos: `/users`, `/orders/{id}`.
- Verbos HTTP con semántica correcta: GET lectura, POST creación, PATCH cambio parcial, PUT reemplazo, DELETE borrado.
- Versionado explícito cuando haya consumidores externos (`/v1/...`).
- Paginación obligatoria en listados grandes (cursor preferido sobre offset).
- Filtros y ordenamiento documentados y validados.
- Idempotencia en operaciones de creación sensibles.

## Formato de errores

Usar una estructura única, por ejemplo:

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Descripción legible",
    "details": [{ "field": "email", "issue": "invalid" }],
    "requestId": "..."
  }
}
```

- Códigos estables en `UPPER_SNAKE_CASE`.
- No exponer stack traces ni detalles internos al cliente.
- Incluir identificador de correlación en logs y respuestas.

## Validación

- Validar tipos, rangos, formatos y campos requeridos en la entrada.
- Rechazar campos desconocidos cuando sea posible.
- Normalizar datos antes de persistir (trim, lowercase de emails, etc.).

## Configuración y secretos

- Variables de entorno con nombres claros y documentados.
- Nunca commitear secretos.
- Definir valores por defecto seguros para desarrollo.
- Fallar al arrancar si falta configuración crítica.

## Logging y observabilidad

- Logs estructurados con nivel, timestamp, `requestId` y contexto.
- No loggear datos personales ni credenciales.
- Medir latencia y tasa de error por endpoint.

## Convenciones de código

- Nombres descriptivos; evitar abreviaturas ambiguas.
- Funciones pequeñas y con una responsabilidad.
- Sin efectos secundarios ocultos en getters o validadores.
- Tipado cuando el lenguaje lo permita.

## Checklist antes de entregar backend

- [ ] Entrada validada y errores consistentes.
- [ ] Sin secretos ni configuración hardcodeada.
- [ ] Capas respetadas.
- [ ] Logs útiles y sin datos sensibles.
- [ ] Tests de casos felices y de error.
- [ ] Documentación del endpoint actualizada.

## Pendientes

- Definir lenguaje, framework y estilo de arquitectura.
- Definir estándar de autenticación y autorización.
- Definir contrato de API (OpenAPI u otro).
