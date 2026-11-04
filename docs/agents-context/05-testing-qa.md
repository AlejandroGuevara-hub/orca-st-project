# Contexto de testing y QA

## Propósito

Definir la estrategia de pruebas y los criterios de calidad. Aplica a agentes que escriban tests, validen cambios o revisen entregables.

## Estado

- Sin framework de testing definido.
- Registrar frameworks, comandos y cobertura objetivo antes de escribir tests.

## Principios

- Probar comportamiento, no implementación.
- Los tests deben ser deterministas y aislados.
- Un test que falla debe explicar qué se rompió.
- Cobertura es una señal, no un objetivo por sí mismo.
- Todo bug corregido debe tener un test de regresión.

## Pirámide de pruebas

| Nivel | Cantidad | Velocidad | Alcance |
| --- | --- | --- | --- |
| Unitarias | Muchas | Rápidas | Funciones y módulos aislados |
| Integración | Moderadas | Medias | Interacción entre componentes reales |
| End-to-end | Pocas | Lentas | Flujos críticos de usuario |

## Convenciones

- Nombre del test describe escenario y resultado esperado.
- Estructura clara: preparar, ejecutar, verificar (arrange/act/assert).
- Un concepto por test.
- Datos de prueba explícitos y legibles; usar factories o fixtures.
- Evitar dependencias de red, hora o estado global sin control.

## Qué probar siempre

- Casos felices.
- Entradas inválidas y límites.
- Errores de dependencias externas.
- Permisos y autorización.
- Idempotencia y concurrencia cuando aplique.

## Pruebas de integración y e2e

- Usar entornos reproducibles (contenedores o servicios efímeros).
- Limpiar estado entre pruebas.
- Cubrir flujos críticos: registro, login, compra, pago, etc. según el dominio.
- Evitar pruebas frágiles basadas en tiempos arbitrarios.

## Calidad manual

Checklist de revisión:

- [ ] El cambio cumple el objetivo planteado.
- [ ] Casos de error se comportan de forma razonable.
- [ ] UI revisada en tamaños y navegadores objetivo.
- [ ] Sin errores en consola ni logs inesperados.
- [ ] Accesibilidad básica verificada.
- [ ] Rendimiento sin degradación evidente.

## Comandos

Documentar aquí una vez definidos:

| Acción | Comando |
| --- | --- |
| Instalar | pendiente |
| Lint | pendiente |
| Typecheck | pendiente |
| Tests unitarios | pendiente |
| Tests e2e | pendiente |
| Cobertura | pendiente |

## Checklist antes de entregar

- [ ] Tests nuevos o actualizados para el cambio.
- [ ] Suite completa ejecutada y en verde.
- [ ] Lint y typecheck sin errores.
- [ ] Sin tests omitidos o comentados sin justificación.

## Pendientes

- Elegir frameworks de test.
- Definir cobertura objetivo por área.
- Configurar ejecución en CI.
