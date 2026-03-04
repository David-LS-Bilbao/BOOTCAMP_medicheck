# Fix MVP - Tablas en movil (Dashboard)

## Contexto
Este documento resume la solucion aplicada en `index.html` para que la tabla del dashboard sea usable en movil sin JavaScript.

## Diagnostico original
Problemas detectados en la version inicial:
1. Tabla semanal demasiado ancha para movil.
2. Comportamiento irregular con `sticky` dentro de contenedores con `overflow` en iOS Safari.
3. Celdas y pills con densidad alta en pantallas pequenas.
4. Interacciones de estado sin logica real podian confundir durante la demo.

## Solucion implementada

### 1) Split responsive de tablas
- En movil se muestra solo `Plan de hoy` (`.only-mobile`) con tabla compacta (`.today-table`).
- En desktop/tablet se mantiene la tabla semanal (`.only-desktop`) con `week-table`.

### 2) Scroll y sticky seguros
- El wrapper comun de tablas usa:
  - `overflow-x: auto`
  - `-webkit-overflow-scrolling: touch`
  - `overscroll-behavior-x: contain`
- El sticky de cabeceras/primera columna queda limitado a desktop/tablet.

### 3) Interacciones fuera de alcance (sin JS)
- Los estados clicables del dashboard redirigen a `pages/needJavaScript.html`.
- Se evita aparentar funcionalidad real no implementada.

## Archivos implicados
- `index.html`
- `css/styles.css`
- `pages/needJavaScript.html` (flujo placeholder)

## Resultado esperado
- En movil: tabla de hoy legible y sin scroll horizontal principal.
- En desktop/tablet: tabla semanal completa y estable.
- En ambos: interacciones no implementadas van a placeholder tecnico.

## Validacion manual
1. Abrir `index.html` en viewport movil (<720px).
2. Verificar que aparece solo la tabla "Plan de hoy".
3. Pulsar un estado (`Tomado/Pendiente/Omitido`) y comprobar redireccion a `pages/needJavaScript.html`.
4. Abrir en >=720px y verificar que aparece la tabla semanal.
5. Probar foco con teclado en enlaces y tabla (`tabindex` en wrapper).

## Nota
Este fix mantiene alcance de Modulo 1: HTML/CSS puro, sin logica JavaScript.
