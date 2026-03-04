# Medicheck

Medicheck es un MVP estatico para demo de seguimiento de tratamientos.
No usa JavaScript, backend ni base de datos.

> Aviso: esta app no ofrece consejos medicos ni sustituye a profesionales de salud.

## Estado actual (2026-03-04)
- Navegacion completa en 7 pantallas.
- Dashboard e historial con tablas responsive (movil y desktop/tablet).
- Acciones no implementadas redirigen a placeholders de alcance tecnico.
- Footer y estilos compartidos en todas las vistas.

## Stack
- HTML5 semantico
- CSS3 (variables, Flexbox, Grid, media queries)
- Sin JavaScript
- Sin backend

## Estructura del proyecto
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
    needDBs.html
    needAPI.html
    needJavaScript.html
  images/
    index1.png
  docs/
    informe-mvp-html-css.md
    fix-tablas-movil.md
    fix-tablas-historial-responsive.md
    proyecto_html_css.pdf
```

## Pantallas incluidas
1. `index.html`: dashboard (tabla "Plan de hoy" en movil + tabla semanal en desktop/tablet).
2. `pages/tratamientos.html`: listado visual de tratamientos.
3. `pages/tratamiento-form.html`: formulario de alta/edicion (solo UI).
4. `pages/history.html`: historial de tomas (tabla compacta movil + tabla completa desktop/tablet).
5. `pages/needDBs.html`: placeholder para acciones que requieren base de datos.
6. `pages/needAPI.html`: placeholder para acciones que requieren consumo de API.
7. `pages/needJavaScript.html`: placeholder para acciones que requieren logica JavaScript.

## Flujos placeholder de demo
- `needDBs.html`: guardar/editar/pausar tratamientos e historial persistente.
- `needAPI.html`: consulta de fichas de medicamento y validacion externa.
- `needJavaScript.html`: cambio dinamico de estados, recordatorios y actualizaciones en tiempo real.

## Responsive y accesibilidad
- Enfoque mobile-first.
- Alternancia de vistas con `only-mobile` y `only-desktop`.
- Breakpoint principal en `720px`.
- Tablas semanticas con `caption`, `thead`, `tbody` y `th scope`.
- Focus visible para teclado con `:focus-visible`.
- Formularios con `label for`, `fieldset` y `legend`.

## Alcance actual del MVP
- [x] Navegacion y rutas relativas funcionales.
- [x] UI responsive en dashboard, tratamientos, formulario e historial.
- [x] Placeholders para funcionalidades fuera de alcance (DB/API/JS).
- [ ] Persistencia real de datos.
- [ ] Integracion API real.
- [ ] Logica dinamica en cliente (sin JS en este modulo).

## Como ejecutar
### Opcion 1
Abrir `index.html` en navegador.

### Opcion 2 (recomendada)
Usar Live Server en VS Code sobre `index.html`.

## Proximos pasos
1. Implementar logica JS para estados y recordatorios.
2. Conectar almacenamiento persistente (backend o localStorage segun alcance).
3. Integrar API de medicamentos para autocompletado y validaciones.
4. Añadir pruebas manuales guiadas por flujos de usuario.
