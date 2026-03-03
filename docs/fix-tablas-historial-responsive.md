# Fix Responsive - Tablas en Historial (Medicheck)

## Objetivo
Aplicar en `history.html` el mismo patron responsive usado en dashboard:
- Movil: tabla compacta y usable sin scroll horizontal.
- Desktop/Tablet: tabla completa.
- Sin JavaScript.

## Archivos modificados
- `pages/history.html`
- `css/styles.css`

## Cambios implementados

### 1) `pages/history.html`
Se separo el historial en dos secciones:

1. `only-mobile`
- Titulo visible: **Historial reciente**.
- Tabla compacta (`compact-table`) con 3 columnas:
  - Fecha
  - Medicamento
  - Estado
- Semantica completa: `caption`, `thead`, `tbody`, `th scope="col"`, `th scope="row"`.

2. `only-desktop`
- Mantiene la tabla completa original (Fecha, Medicamento, Franja, Estado).
- Se mantiene semantica y se agrega `tabindex="0"` al contenedor para navegacion por teclado.

### 2) `css/styles.css`
Se reutilizo el sistema responsive ya existente:
- `only-mobile` visible por defecto.
- `only-desktop` oculto por defecto.
- Inversion a partir de `@media (min-width: 720px)`.

Ademas, se generalizo la tabla compacta para que sirva tanto en dashboard como historial:
- Nuevas clases reutilizables:
  - `.compact-wrap`
  - `.compact-table`
- Mismas reglas de tabla compacta sin scroll horizontal:
  - `width: 100%`
  - `table-layout: fixed`
  - `overflow-x: hidden` en el wrapper compacto

## Snippets clave

### Visibilidad responsive
```css
.only-mobile { display: block; }
.only-desktop { display: none; }

@media (min-width: 720px) {
  .only-desktop { display: block; }
  .only-mobile { display: none; }
}
```

### Tabla compacta reutilizable
```css
.today-wrap,
.compact-wrap {
  overflow-x: hidden;
}

.today-table,
.compact-table {
  width: 100%;
  min-width: 0;
  table-layout: fixed;
}
```

### Estructura en historial
```html
<section class="week only-mobile"> ... <table class="compact-table"> ... </table> ... </section>
<section class="week only-desktop"> ... <table class="week-table"> ... </table> ... </section>
```

## Validacion rapida
1. En movil (<720px), abrir `pages/history.html`:
- Solo debe verse la tabla compacta.
- No debe aparecer scroll horizontal.

2. En desktop/tablet (>=720px):
- Debe ocultarse la compacta.
- Debe mostrarse la tabla completa.

3. Accesibilidad:
- Verificar `caption`, `thead`, `tbody`, `scope` en ambas tablas.
- Navegar con teclado y confirmar foco visible en interactivos.

## Commit sugerido
```bash
git add pages/history.html css/styles.css docs/fix-tablas-historial-responsive.md
git commit -m "feat(history): add mobile compact table and desktop full table responsive split"
```
