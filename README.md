# Medicheck

Medicheck es un MVP de Fundamentos (Modulo 1) para presentar una interfaz de seguimiento de tratamientos.

> Aviso: esta app no ofrece consejos medicos ni sustituye a profesionales de salud.

## Objetivo del MVP
1. Gestion visual de tratamientos.
2. Dashboard semanal (L-D x manana/mediodia/tarde/noche).
3. Historial visual de tomas.

## Estado actual
- Proyecto 100% HTML + CSS.
- Sin JavaScript funcional (maqueta de presentacion).
- Navegacion entre paginas con rutas relativas.
- Footer semantico y alineado al layout en todas las vistas.

## Estructura real del proyecto
```text
medicheck/
  index.html
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
```

## Como ejecutar
### Opcion 1
Abrir `index.html` directamente en el navegador.

### Opcion 2 (recomendada)
Usar Live Server en VS Code sobre `index.html`.

## Checklist rapido
- [x] CSS cargando en todas las paginas.
- [x] Rutas relativas funcionando (`./` y `../`).
- [x] Tabla semanal con estructura semantica (`caption`, `thead`, `tbody`, `th scope`).
- [x] Formulario con `label for` y `fieldset/legend`.
- [x] Foco visible para navegacion por teclado.
- [x] Layout responsive (Flex/Grid + media queries + scroll horizontal en tablas).

## Decisiones tecnicas
- Se usa `<table>` para datos tabulares del calendario e historial.
- Enfoque mobile-first con breakpoints en CSS.
- Tamaño tactil minimo de controles: `44px`.
- Sticky footer con `body.layout` + `main { flex: 1; }`.

## Alcance y siguientes pasos
- Alcance actual: presentacion MVP de UI sin logica de negocio.
- Siguiente paso: cerrar commit de documentacion y ajustes de maquetacion.
