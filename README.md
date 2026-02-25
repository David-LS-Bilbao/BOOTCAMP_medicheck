# Medicheck

App web (Fundamentos) para **recordar y registrar tomas** de medicamentos o suplementos mediante una **vista semanal** (L–D) con franjas del día.

> ⚠️ **Aviso importante:** Medicheck **no ofrece consejos médicos** ni sustituye la opinión de profesionales sanitarios. Es una herramienta de **registro y recordatorio**.

---

## 🎯 Problema
Personas con tratamientos crónicos o puntuales olvidan si han tomado la medicación, cuándo fue la última toma y se les desordena el seguimiento diario.

## 👤 Público objetivo
Adultos con medicación recurrente o temporal que necesitan **recordatorio + registro**.

---

## ✅ MVP (3 funcionalidades core)
1. **Gestión de tratamientos (UI)**: añadir/editar medicamento/suplemento con dosis y horarios.
2. **Dashboard semanal (UI)**: calendario L–D × mañana/mediodía/tarde/noche.
3. **Registro de tomas (UI)**: marcar “Tomado / Omitido” (estado visual).

---

## 🧩 Estructura del proyecto
medicheck/
index.html
tratamientos.html
tratamiento-form.html
historial.html
css/
styles.css
assets/


---

## ▶️ Cómo ejecutar
### Opción 1: abrir en navegador
- Abre `index.html` con doble click o:
  - macOS:
    - `open index.html`

### Opción 2: Live Server (recomendado)
1. Instala la extensión **Live Server** en VS Code
2. Click derecho en `index.html` → **Open with Live Server**

---

## 🧪 Checklist de verificación
- [ ] El CSS se carga correctamente (`styles.css`)
- [ ] El dashboard se ve en desktop y se puede hacer scroll horizontal en móvil
- [ ] Navegación por teclado: foco visible en botones
- [ ] Texto legible y botones grandes (tacto)

---

## 🚀 Mejoras (Nice-to-have)
- Toggle **Rejilla / Lista** (mejor para móvil)
- Modo **alto contraste** y **texto grande**
- Login + sincronización en la nube
- Base de datos/API de medicamentos (solo lectura: ficha oficial)
- FAQ predefinida con enlaces a fuentes oficiales

---

## 🧾 Decisiones de diseño (rápidas)
- Se usa `<table>` para representar una rejilla 2D (días × franjas).
- Diseño **mobile-first** con scroll horizontal en el calendario.
- Botones con tamaño táctil mínimo (≈44px) para accesibilidad.