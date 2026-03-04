# Fix Responsive - Tablas en Historial

## Objetivo
Alinear `pages/history.html` con el mismo patron responsive del dashboard:
- Movil: tabla compacta.
- Desktop/tablet: tabla completa.
- Sin JavaScript.

## Cambios aplicados

### 1) Split de vistas por breakpoint
- `only-mobile`: tabla compacta `compact-table` (Fecha, Medicamento, Estado).
- `only-desktop`: tabla completa `week-table` (Fecha, Medicamento, Franja, Estado).
- Cambio de visibilidad en `@media (min-width: 720px)`.

### 2) Semantica y accesibilidad
- Ambas tablas mantienen `caption`, `thead`, `tbody` y `scope`.
- Wrapper de tabla completa con `tabindex="0"` para navegacion con teclado.

### 3) Acciones fuera de alcance
- Los estados de toma (`Tomado/Pendiente/Omitido`) se muestran como enlaces que redirigen a `needJavaScript.html`.
- Se evita simular una accion dinamica que el MVP no implementa.

## Archivos implicados
- `pages/history.html`
- `css/styles.css`
- `pages/needJavaScript.html`

## Validacion manual
1. Abrir `pages/history.html` en movil (<720px): debe mostrarse solo la tabla compacta.
2. Pulsar cualquier estado: debe abrir `pages/needJavaScript.html`.
3. Abrir en desktop/tablet (>=720px): debe mostrarse solo la tabla completa.
4. Comprobar foco visible en enlaces y navegacion superior.

## Resultado
Historial consistente con dashboard, usable en movil y sin expectativas de funcionalidad dinamica real (porque sigue siendo MVP estatico).
