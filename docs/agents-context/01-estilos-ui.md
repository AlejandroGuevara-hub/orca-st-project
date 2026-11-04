# Contexto de estilos y UI

## Propósito

Definir cómo se construyen, nombran y mantienen los estilos y componentes de interfaz. Este documento aplica a agentes que toquen frontend, diseño visual o accesibilidad.

## Estado

- Sin framework de UI ni sistema de estilos elegido todavía.
- Al elegir stack, registrar la decisión aquí y en `00-contexto-general.md`.

## Principios

- Consistencia antes que creatividad: reutilizar tokens y componentes existentes.
- Accesibilidad como requisito, no como extra.
- Mobile first y diseño responsivo por defecto.
- Separar estructura, estilos y comportamiento.
- Evitar estilos mágicos o valores hardcodeados repetidos.

## Design tokens

Documentar aquí los tokens una vez definidos:

| Token | Valor | Uso |
| --- | --- | --- |
| `color.primary` | pendiente | Acciones principales |
| `color.surface` | pendiente | Fondos de superficies |
| `color.text` | pendiente | Texto principal |
| `space.*` | pendiente | Escala de espaciado |
| `radius.*` | pendiente | Bordes redondeados |
| `font.family` | pendiente | Tipografía base |

## Convenciones de nombres

- Componentes: `PascalCase` (por ejemplo `UserCard`).
- Archivos de estilo: mismo nombre que el componente o módulo.
- Clases CSS: definir una convención única (BEM, utilidades o CSS Modules) y no mezclar.
- Variables: describir rol, no apariencia (`--color-danger`, no `--color-red`).

## Espaciado y layout

- Usar una escala fija (por ejemplo 4, 8, 12, 16, 24, 32, 48).
- Evitar márgenes negativos salvo casos justificados.
- Definir breakpoints una sola vez y reutilizarlos.

## Tipografía

- Documentar familia, tamaños, pesos y alturas de línea.
- Mantener una jerarquía limitada de encabezados.
- No usar tamaños arbitrarios fuera de la escala.

## Accesibilidad

- Contraste mínimo AA (4.5:1 para texto normal).
- Todo control interactivo debe ser accesible por teclado.
- Usar HTML semántico antes que roles ARIA.
- Imágenes con `alt` significativo o `alt=""` si son decorativas.
- No depender solo del color para transmitir estado.
- Respetar `prefers-reduced-motion`.

## Estados de componentes

Cada componente interactivo debe contemplar: default, hover, focus visible, active, disabled, loading y error (si aplica).

## Checklist antes de entregar UI

- [ ] Reutiliza tokens y componentes existentes.
- [ ] Funciona en los breakpoints definidos.
- [ ] Navegable por teclado y con foco visible.
- [ ] Contraste verificado.
- [ ] Sin estilos duplicados o valores hardcodeados evitables.
- [ ] Captura o descripción del cambio visual para revisión.

## Pendientes

- Elegir enfoque de estilos (CSS Modules, Tailwind, styled-components, etc.).
- Definir paleta, tipografía y escala de espaciado.
- Definir librería de componentes base.
