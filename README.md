# Medicheck

Medicheck es un MVP estatico para visualizar seguimiento de tratamientos (sin JS ni backend).

> Aviso: esta app no ofrece consejos medicos ni sustituye a profesionales de salud.

## Estado actual (2026-03-03)
- Interfaz navegable en 4 pantallas: dashboard, tratamientos, formulario e historial.
- Dashboard con vista movil de "Plan de hoy" y vista desktop/tablet de calendario semanal.
- Historial con tabla compacta en movil y tabla completa en desktop/tablet.
- Listado de tratamientos y formulario listos como maqueta UI.
- Footer comun y estilos compartidos en todas las vistas.

## Stack
- HTML5 semantico.
- CSS3 (variables, Flexbox, Grid, media queries).
- Sin JavaScript, sin base de datos y sin backend.

## Estructura actual del proyecto
```text
medicheck/
  index.html
  README.md
  css/
    styles.css
  pages/
    tratamientos.html
    tratamiento-form.html
    history.html
  images/
    index1.png
  docs/
    informe-mvp-html-css.md
    fix-tablas-movil.md
    fix-tablas-historial-responsive.md
    proyecto_html_css.pdf
```

## Pantallas incluidas
1. `index.html`: dashboard semanal (tabla compacta en movil + tabla completa en desktop/tablet).
2. `pages/tratamientos.html`: listado visual de tratamientos activos.
3. `pages/tratamiento-form.html`: formulario para alta/edicion (solo UI).
4. `pages/history.html`: historial de tomas con version movil y desktop/tablet.

## Responsive y accesibilidad implementados
- Enfoque mobile-first.
- `only-mobile` y `only-desktop` para alternar vistas segun ancho.
- Breakpoints principales en `720px` y `1024px`.
- `table-wrap` con scroll horizontal cuando aplica.
- Semantica de tablas: `caption`, `thead`, `tbody`, `th scope`.
- Formulario con `label for`, `fieldset` y `legend`.
- Foco visible con `:focus-visible` para navegacion por teclado.

## Alcance actual del MVP
- [x] Navegacion entre pantallas con rutas relativas correctas.
- [x] UI responsive en dashboard, tratamientos, formulario e historial.
- [x] Datos mock para demo visual.
- [ ] Persistencia de datos.
- [ ] Logica de negocio (guardar, editar, pausar, marcar tomado).
- [ ] Integracion con API/backend.

## Como ejecutar
### Opcion 1
Abrir `index.html` directamente en el navegador.

### Opcion 2 (recomendada)
Usar Live Server en VS Code sobre `index.html`.

## Proximos pasos recomendados
1. Conectar formulario y tablas a estado real con JavaScript.
2. Persistir datos (localStorage o backend).
3. Implementar acciones reales de tratamientos e historial.
4. Anadir pruebas manuales guiadas por casos de uso.
