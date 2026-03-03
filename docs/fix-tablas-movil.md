# Fix MVP - Tablas en movil (Medicheck)

## Diagnostico

Problemas detectados en la tabla semanal (dashboard):

1. El `position: sticky` estaba activo en **todas** las pantallas dentro de `.table-wrap` con `overflow`.
2. Esa combinacion (`sticky` + `overflow`) da fallos en iOS Safari (cabeceras/celdas pegadas que se solapan o no se repintan bien).
3. En movil, `min-width: 820px` + `padding` relativamente grande hacia que la tabla se sintiera "dura" de usar aunque tuviera scroll.
4. El contenedor tenia scroll, pero faltaban ajustes para una experiencia mas estable en touch (especialmente iOS).

## Cambios propuestos (MVP, sin JavaScript)

### 1) `styles.css` (scroll horizontal estable + sticky solo en desktop)

```css
.table-wrap {
  max-width: 100%;
  overflow-x: auto;
  overflow-y: hidden;
  overscroll-behavior-x: contain;
  -webkit-overflow-scrolling: touch;
  border: var(--line);
  border-radius: var(--radius);
  background: var(--surface);
}

/* Por defecto (movil) sin sticky para evitar bugs de iOS Safari con overflow. */
.week-table thead th {
  background: #a7adb6;
}

.week-table th:first-child {
  min-width: 130px;
  background: #f2f5fa;
}

/* Sticky solo en pantallas medias/grandes para mantener desktop sin romper movil. */
@media (min-width: 761px) {
  .week-table thead th {
    position: sticky;
    top: 0;
    z-index: 1;
  }

  .week-table th:first-child {
    position: sticky;
    left: 0;
    z-index: 2;
  }
}

@media (max-width: 760px) {
  .week-table { min-width: 680px; }

  .week-table th,
  .week-table td { padding: 8px; }

  .week-table th:first-child { min-width: 96px; }

  .cell {
    min-height: 72px;
    gap: 8px;
  }

  .pill {
    font-size: 0.86rem;
    padding: 6px 9px;
  }

  .btn {
    font-size: 0.95rem;
    padding: 8px 10px;
  }
}
```

### 2) `index.html` (mejora de usabilidad por teclado)

```html
<div class="table-wrap" role="region" aria-label="Calendario semanal de tomas" tabindex="0">
```

Con `tabindex="0"`, el contenedor se puede enfocar y desplazar horizontalmente con teclado en desktop.

## Checklist de pruebas (manual)

### Chrome movil (Android)

1. Abrir `index.html` en viewport movil (ej. 390x844).
2. Verificar que la tabla **no rompe el layout** y que hay scroll horizontal dentro de `.table-wrap`.
3. Deslizar horizontalmente y comprobar que el scroll es fluido.
4. Revisar legibilidad: pills y botones no deben desbordar celdas.
5. Confirmar que desktop (>761px) mantiene cabecera/primera columna sticky.

### Safari iOS

1. Abrir dashboard en iPhone real (o simulador).
2. Hacer scroll horizontal dentro de la tabla.
3. Confirmar que en movil no hay artefactos de sticky (solapes/parpadeos/celdas "pegadas").
4. Rotar a landscape y repetir scroll.
5. Validar que el resto de la pagina sigue haciendo scroll vertical normal.

### Accesibilidad rapida

1. Foco visible en enlaces/botones/campos.
2. La tabla mantiene `caption`, `thead`, `tbody`, `th scope`.
3. Con `Tab`, llegar al contenedor de tabla y validar foco del region scrollable.

## Resumen de archivos afectados

- `index.html`
- `css/styles.css`

## Commit sugerido

```bash
git add index.html css/styles.css docs/fix-tablas-movil.md
git commit -m "fix(css): improve mobile table usability and iOS sticky behavior"
```

