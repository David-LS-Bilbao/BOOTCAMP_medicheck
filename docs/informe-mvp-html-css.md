# Informe técnico MVP HTML/CSS - Medicheck

## 1) Resumen ejecutivo (10 líneas)
1. El MVP cumple bien la base de **HTML/CSS de fundamentos** para una presentación sin JavaScript.
2. La navegación interna entre `index.html` y `pages/*` usa rutas relativas correctas (`./` y `../`).
3. El calendario semanal está bien modelado como tabla con `caption`, `thead`, `tbody` y encabezados con `scope`.
4. El formulario principal cumple accesibilidad básica: `label for`, controles asociados y `fieldset` + `legend`.
5. En CSS hay buena base: cascada clara, `box-sizing: border-box` global, uso de Flex/Grid y media queries.
6. Se detecta foco visible con `:focus-visible` en navegación, botones y campos de formulario.
7. Riesgo importante: falta `footer` semántico en todas las páginas (criterio de estructura semántica incompleto).
8. Riesgo importante: `README.md` no refleja la estructura real de carpetas/archivos actual.
9. Riesgo menor: existen botones visuales sin funcionalidad real en página de tratamientos (puede confundir en demo estática).
10. Con ajustes pequeños de semántica/documentación, el MVP queda sólido y alineado al módulo.

## 2) Checklist de cumplimiento

### HTML
- ✅ `<!DOCTYPE html>`, `lang`, `meta charset` y `meta viewport` presentes.
- ⚠️ Estructura semántica parcial: hay `main/header/nav/section/article`, pero falta `footer` en todas las vistas.
- ✅ Rutas relativas correctas entre `index.html` y `pages/*`.
- ✅ Enlaces externos seguros (`target="_blank"` + `rel`) **N/A**: no hay enlaces externos.
- ✅ Tabla de calendario con `table`, `caption`, `thead`, `tbody` y `th` con `scope`.
- ✅ Formulario accesible con `label for` y agrupación con `fieldset` + `legend`.

### CSS
- ✅ Unidades de fuente en `rem` (sin `font-size` en `px`).
- ✅ `box-sizing: border-box` global aplicado.
- ✅ Layout con Flexbox/Grid en navegación, acciones, cards y formulario.
- ✅ Responsive con media queries (`720px`, `760px`, `1024px`) y tabla con scroll horizontal.
- ✅ Foco visible en interactivos (`.btn`, `.top-nav a`, campos de formulario).

### MVP
- ✅ Alcance de 3 funcionalidades core respetado a nivel **UI** (sin JS).
- ⚠️ Documentación del MVP desactualizada respecto a estructura real (`README.md`).
- ⚠️ Algunos CTAs de acción (`Pausar`) sugieren comportamiento no implementado en maqueta estática.

## 3) Hallazgos por severidad

### P0 (bloqueante)
- ✅ No se detectan P0.

### P1 (importante)

1. **Falta `footer` semántico en todas las páginas**
- Archivo/línea aprox.: `index.html` (10-107), `pages/tratamientos.html` (10-68), `pages/tratamiento-form.html` (10-81), `pages/history.html` (10-60).
- Impacto: incumple criterio semántico solicitado (`header/nav/main/footer`) y reduce consistencia estructural.
- Corrección mínima sugerida:
```html
<footer class="site-footer">
  <p>Medicheck MVP - The Bridge 2026</p>
</footer>
```

2. **`README.md` no coincide con estructura real del proyecto**
- Archivo/línea aprox.: `README.md` líneas 24-32.
- Impacto: complica evaluación/docencia y onboarding; menciona archivos en raíz que hoy están en `pages/` y usa `historial.html` en lugar de `history.html`.
- Corrección mínima sugerida:
```md
medicheck/
  index.html
  pages/
    tratamientos.html
    tratamiento-form.html
    history.html
  css/
    styles.css
```

3. **Botones de acción sin funcionalidad en MVP estático (`Pausar`)**
- Archivo/línea aprox.: `pages/tratamientos.html` líneas 40, 51, 62.
- Impacto: en demo sin JS puede generar expectativa de interacción real.
- Corrección mínima sugerida (si se mantiene 100% estático):
```html
<span class="btn" aria-disabled="true">Pausar (demo)</span>
```

### P2 (mejora)

1. **No hay `.gitignore` local en el proyecto (opcional)**
- Archivo/línea aprox.: `PROGRAMS/medicheck/.gitignore` no existe.
- Impacto: riesgo de subir artefactos locales si crece el proyecto.
- Corrección mínima sugerida:
```gitignore
.DS_Store
.vscode/
```

2. **Checklist de verificación en README sin estado actualizado**
- Archivo/línea aprox.: `README.md` líneas 49-53.
- Impacto: menor, pero resta trazabilidad al cierre de MVP.
- Corrección mínima sugerida:
```md
- [x] El CSS se carga correctamente
- [x] El dashboard se ve en desktop y móvil
```

## 4) Acciones recomendadas

### Fix hoy (MVP)
1. Añadir `footer` simple en las 4 páginas para cerrar semántica.
2. Actualizar `README.md` con estructura/rutas reales.
3. Etiquetar como “demo” o desactivar semánticamente acciones no implementadas (`Pausar`).

### Mejoras para destacar
1. Añadir enlace “Saltar al contenido” al inicio para accesibilidad de teclado.
2. Ajustar consistencia de textos (`Manana`/`Días`) y acentos para presentación.
3. Crear `.gitignore` básico del proyecto.

## 5) Validación manual (pasos concretos)
1. Abrir `index.html` y navegar a `Tratamientos`, `Nuevo tratamiento` e `Historial`; confirmar que todas las rutas funcionen.
2. Desde cada página, usar menú superior para volver a `Dashboard`; verificar `aria-current="page"` visualmente.
3. En móvil (DevTools), validar scroll horizontal de tabla semanal e historial.
4. Recorrer con `Tab` toda la interfaz; confirmar foco visible en links/botones/inputs/select/textarea.
5. Revisar tabla semanal e historial: presencia de `caption`, `thead`, `tbody` y `th scope`.
6. Revisar formulario: asociación `label for` + `id`, `fieldset` y `legend` en “Días de toma”.

## 6) Propuesta de commits y ramas

### Rama sugerida principal
- `fix/p0-p1-mvp-html-css` (aunque no hay P0, sirve para agrupar hallazgos críticos de revisión)

### Commits pequeños (3-5)
1. `chore/docs: alinear README con estructura real de medicheck`
2. `fix(html): añadir footer semántico en todas las vistas`
3. `fix(ui): marcar acciones no funcionales como demo estática`
4. `chore: agregar .gitignore base para entorno local`
5. `docs: actualizar checklist de validación MVP`

---

**Nota de alcance:** informe realizado sin modificar código funcional; evaluación centrada en HTML/CSS del Módulo 1 y MVP estático sin JavaScript.
