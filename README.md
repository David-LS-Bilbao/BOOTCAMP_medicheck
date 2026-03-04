# Medicheck (MVP)

Hola, este proyecto es mi MVP de HTML/CSS del modulo 1.
La idea es simular una app para llevar control de medicamentos, pero por ahora es solo maqueta visual.

## Importante
- No usa JavaScript
- No tiene base de datos
- No tiene backend
- Es para demo/presentacion

> Aviso: esto NO reemplaza consejo medico profesional.

## Que pantallas tiene
1. `index.html` -> Dashboard
2. `pages/tratamientos.html` -> Lista de tratamientos
3. `pages/tratamiento-form.html` -> Formulario (solo interfaz)
4. `pages/history.html` -> Historial
5. `pages/needDBs.html` -> Pantalla cuando algo necesita base de datos
6. `pages/needAPI.html` -> Pantalla cuando algo necesita API
7. `pages/needJavaScript.html` -> Pantalla cuando algo necesita JS real

## Como esta hecho
- HTML5 semantico
- CSS3
- Layout con Flex y Grid
- Responsive (mobile-first)

## Responsive
- En movil se ven tablas compactas
- En desktop se ven tablas completas
- Se usan clases `only-mobile` y `only-desktop`
- Breakpoint principal: `720px`

## Acciones que redirigen a placeholders
Como es un MVP estatico, algunas acciones no hacen logica real y te mandan a una pantalla explicativa:

- `needDBs.html`:
  guardar, editar, pausar tratamientos

- `needAPI.html`:
  consulta de ficha de medicamento

- `needJavaScript.html`:
  cambiar estados con click, recordatorios, actualizaciones dinamicas

## Estructura de carpetas
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
  docs/
    informe-mvp-html-css.md
    fix-tablas-movil.md
    fix-tablas-historial-responsive.md
```

## Como abrirlo
### Opcion rapida
Abrir `index.html` en el navegador.

### Opcion recomendada
Usar Live Server desde VS Code.

## Estado actual
- [x] Navegacion funcionando
- [x] Vistas responsive
- [x] Placeholders DB/API/JS
- [ ] Persistencia real
- [ ] API real
- [ ] Logica JS real

## Siguientes pasos (cuando toque)
1. Meter JavaScript para estados y recordatorios
2. Guardar datos de verdad (localStorage o backend)
3. Conectar API de medicamentos
