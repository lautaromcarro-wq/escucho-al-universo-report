# Plan de Implementación V2 · Landing Escucho al Universo

**Para:** Claude Code
**Contexto:** Landing ya desplegada en Vercel con 8 pestañas. Este plan agrega 2 features nuevas y retira un accionable.

---

## Contexto de producto

El reporte es un diagnóstico de Paid Media + Retención que la clienta ya vio. El equipo de Nebulab lo usa como:

1. **Disparador de la reunión creativa** — el output principal del reporte es alimentar de ideas al brief creativo, no una lista larga de accionables de performance. En performance los movimientos son pocos (sostener scalers, rotar hooks, redistribuir budget); el grueso del valor está en retención y en producción creativa nueva para alimentar el algoritmo de Meta.
2. **Material de seguimiento** — el reporte se consulta durante el trimestre. Por eso las tablas tienen que ser navegables (filtrables/ordenables) y tiene que haber un roadmap temporal claro.

**Archivo único:** `index.html` (vanilla HTML + CSS + Chart.js via CDN, sin build step). Mantener esa filosofía — no introducir frameworks ni bundlers.

---

## Cambios pedidos

### 1. Retirar acción "Apagar Video / Contenidos CORTO"

**Estado:** Ya aplicado en el último commit local (pendiente de push). Verificar que `index.html` no contenga ese item en el array `ACTIONS` y que el título de la pestaña Plan diga "9 movimientos" (no 10).

### 2. Nueva pestaña "Roadmap" — plan mes a mes Abr → Dic 2026

**Objetivo:** Visualizar la cadencia de inversión, producción creativa y activación de retención contra el calendario comercial y espiritual del año.

**Estructura de datos sugerida (array en JS al estilo de `ACTIONS`):**

```js
const ROADMAP = [
  {
    mes: 'Abril 2026',
    foco: 'Consolidar base + preparar Hot Sale',
    efemerides: ['Luna llena 21/04', 'Equinoccio de otoño (cerrar ciclo verano)'],
    comercial: [],
    performance: ['Sostener 02_VID_COL_DIC', 'Reactivar Imagen // UPC', 'Subir budget combos a 15%'],
    creativo: ['Brief reunión creativa', 'Producir 3 variantes hook sobre colección'],
    retencion: ['Subir custom audience 1,768', 'Flujo 1 email día 10'],
    budget: 'ARS ~250K · blended',
    roas_target: '6.5x+'
  },
  {
    mes: 'Mayo 2026',
    foco: 'Hot Sale AR (1ra ola)',
    efemerides: ['Hot Sale AR (3 días ~mediados de mayo)', 'Luna llena 20/05'],
    comercial: ['Hot Sale — pico comercial de Q2'],
    performance: ['Capa 1 frío con creative testeado', 'Retargeting agresivo Capa 2', 'Capa 3 retención con descuento exclusivo'],
    creativo: ['Lanzar 2-3 ads nuevos de la reunión creativa', 'Videos con hook de ritual + ahorro'],
    retencion: ['Winback (Flujo 2) activa 48h antes del Hot Sale', 'WhatsApp a los 13 Campeones con preventa'],
    budget: 'ARS ~450K (1.8x mes base)',
    roas_target: '7-9x'
  },
  // Junio: normalización post hot sale + preparación día del padre / día del amigo
  // Julio: Día del Amigo (20/7) · ticket regalo · combos protagonistas
  // Agosto: valle histórico (ROAS 5.1x) · freno de budget · Día de la Niñez
  // Septiembre: Día de la Primavera (21/9) + Día del Estudiante · reactivación
  // Octubre: Día de la Madre (3er domingo) · pico octubre · preventa navidad
  // Noviembre: Cyber Monday + Black Friday · pico del año (ROAS histórico 15.1x) · 11/11 (fecha espiritual)
  // Diciembre: Navidad + preventa Agenda 2027 · cierre de año
];
```

**Efemérides relevantes para esta marca (mezcla comercial + espiritual):**

| Mes | Comercial | Espiritual / energético |
|---|---|---|
| Abril | — | Equinoccio otoño, luna llena |
| Mayo | Hot Sale AR | Luna llena, eclipses si aplica |
| Junio | Día del Padre (3er dom) | Solsticio invierno 21/6 |
| Julio | Día del Amigo 20/7 | Luna llena |
| Agosto | Día de la Niñez (3er dom) | — |
| Septiembre | Día del Estudiante 21/9 | Equinoccio primavera 21/9 (energéticamente fuerte) |
| Octubre | Día de la Madre (3er dom) | Luna llena |
| Noviembre | Cyber Monday, Black Friday | 11/11 (portal energético) |
| Diciembre | Navidad, preventa Agenda 27 | Solsticio verano 21/12, fin de ciclo |

**UI sugerida:**

- Tabla-grilla tipo "calendario vertical" — cada fila = 1 mes, columnas: `Mes · Foco · Efemérides · Performance · Creativo · Retención · Budget · ROAS target`
- Usar los colores de la paleta existente para distinguir celdas de alta intensidad (Nov-Dic) vs valles (Ago)
- Opcional: un mini bar-chart arriba mostrando curva de budget mes a mes (puede usar Chart.js ya incluido)
- Agregar tab al `<nav>` principal entre "Oportunidades" y "Plan de acción" (o después de "Plan"). Nombre: `Roadmap`.

**Dónde insertarla:**

Buscar el patrón `<section class="tab-panel" id="...">` en `index.html`. El id nuevo debería ser `#roadmap`. Agregar también el botón correspondiente en la `<nav>` de tabs (buscar los otros `data-tab="..."`).

### 3. Tablas filtrables + ordenables en TODAS las pestañas

**Alcance:** Todas las `<table>` del documento deben:

1. **Ordenar al clickear el header de columna** — click = ordenar ascendente, 2do click = descendente, 3er click = reset al orden original
2. **Tener un input de filtro** arriba de cada tabla que filtra filas en vivo (debounce 150ms)
3. **Opcionalmente** un `<select>` por columna categórica (por ejemplo: Formato, Tipo, Acción/badge) que filtre por valor

**Tablas a cubrir (identificarlas por sección):**

| Pestaña | Tabla | Columnas relevantes |
|---|---|---|
| Overview | Alertas destacadas (si hay tabla) | — |
| Performance mensual | Tabla evolución ROAS/Spend/Revenue | todas numéricas ordenables |
| Meta Ads | Formatos (Contenido corto, Secuencias, etc.) | Revenue, share, CPM |
| Meta Ads | Top ads por ROAS real (15 filas) | ROAS, CPA, Spend, Compras |
| Productos | Top 10 productos | Revenue, Unidades, Precio avg |
| Retención | LTV por segmento | LTV, órdenes, AOV |
| Retención | Mapa cross-sell | — |
| Alertas | (si tabla) | — |
| Oportunidades | — (son cards, no tabla) | no aplica |
| Plan de acción | — (son cards) | no aplica |
| **Roadmap (nuevo)** | Tabla mes-a-mes | Mes, Budget, ROAS target |

**Implementación técnica sugerida (vanilla JS, genérica):**

```js
// Aplicable a cualquier <table class="sortable filterable">
// Uso:
//   <div class="table-controls">
//     <input type="search" data-filter-for="#tbl-top-ads" placeholder="Filtrar…">
//     <select data-filter-for="#tbl-top-ads" data-col="7"><!-- acción --></select>
//   </div>
//   <table id="tbl-top-ads" class="sortable filterable"> ... </table>

function enhanceTable(table) {
  const headers = table.tHead.rows[0].cells;
  const rows = Array.from(table.tBodies[0].rows);
  const original = rows.slice();
  const state = { col: null, dir: 0 };

  [...headers].forEach((th, i) => {
    th.style.cursor = 'pointer';
    th.addEventListener('click', () => {
      if (state.col !== i) { state.col = i; state.dir = 1; }
      else { state.dir = state.dir === 1 ? -1 : state.dir === -1 ? 0 : 1; }
      render();
    });
  });

  function getVal(tr, i) {
    const txt = tr.cells[i].textContent.trim();
    // Detect number (strip ARS, commas, %, x)
    const num = parseFloat(txt.replace(/[^\d.,-]/g, '').replace(/,/g, ''));
    return isNaN(num) ? txt.toLowerCase() : num;
  }

  function render() {
    let out = state.dir === 0 ? original.slice() : rows.slice().sort((a, b) => {
      const va = getVal(a, state.col), vb = getVal(b, state.col);
      if (va < vb) return -1 * state.dir;
      if (va > vb) return  1 * state.dir;
      return 0;
    });
    // Apply filter (text input)
    const filter = document.querySelector(`[data-filter-for="#${table.id}"]`);
    if (filter && filter.value.trim()) {
      const q = filter.value.toLowerCase().trim();
      out = out.filter(tr => tr.textContent.toLowerCase().includes(q));
    }
    // Apply dropdown filter (if any)
    document.querySelectorAll(`select[data-filter-for="#${table.id}"]`).forEach(sel => {
      if (sel.value) {
        const col = parseInt(sel.dataset.col, 10);
        out = out.filter(tr => tr.cells[col].textContent.trim() === sel.value);
      }
    });
    // Update indicator
    [...headers].forEach((th, i) => th.dataset.sort = i === state.col ? (state.dir === 1 ? 'asc' : state.dir === -1 ? 'desc' : '') : '');
    // Re-render rows
    const tb = table.tBodies[0];
    tb.innerHTML = '';
    out.forEach(tr => tb.appendChild(tr));
  }

  // Wire filter input + selects
  document.querySelectorAll(`[data-filter-for="#${table.id}"]`).forEach(el => {
    el.addEventListener('input', debounce(render, 150));
    el.addEventListener('change', render);
  });
}

function debounce(fn, ms) { let t; return (...a) => { clearTimeout(t); t = setTimeout(() => fn(...a), ms); }; }

// Auto-init
document.querySelectorAll('table.sortable').forEach(enhanceTable);
```

**CSS a agregar:**

```css
.table-controls { display:flex; gap:8px; margin-bottom:10px; flex-wrap:wrap }
.table-controls input[type="search"],
.table-controls select {
  background: var(--surface2);
  color: var(--text);
  border: 1px solid rgba(212,180,131,.2);
  padding: 8px 12px;
  border-radius: 6px;
  font-family: inherit;
  font-size: 13px;
}
table.sortable th { user-select:none; position:relative }
table.sortable th[data-sort="asc"]::after  { content: ' ▲'; color: var(--accent) }
table.sortable th[data-sort="desc"]::after { content: ' ▼'; color: var(--accent) }
```

**Definición de columnas filtrables tipo dropdown por tabla (pensar caso por caso):**

- Top ads por ROAS → dropdown en "Acción" (Escalar/Sostener/Apagar/Reactivar)
- Top productos → dropdown en "Tipo" (Caballo batalla/Gateway/Cross-sell/Renovación/Combo)
- Formatos → dropdown en "Prioridad" (ALTA/MEDIA/BAJA)
- Tabla mensual → dropdown por Año, Clasificación (Q1/Q2/Q3/Q4)
- Roadmap → dropdown por Trimestre

**Agregar la clase `sortable` a todas las `<table>` existentes** + agregar el bloque `<div class="table-controls">` con los inputs/selects correspondientes arriba de cada una.

---

## Orden de ejecución sugerido

1. **Pull del último estado del repo local** (`git pull origin main`) — trae el commit `4f4f4e5` con el ranking por ROAS
2. **Hacer commit de la remoción del item "Contenidos CORTO"** (si no está ya aplicada)
3. **Implementar sortable/filterable genérico** — probar primero en una tabla (ej: Top ads por ROAS), validar UX, luego aplicar en todas
4. **Crear pestaña Roadmap** — estructura de datos + markup del tab + render
5. **QA en Vercel preview** antes de mergear a main

## Consideraciones UX/diseño

- La paleta cósmica/esotérica tiene que sobrevivir a estos cambios. Inputs y dropdowns deben respetar `--surface2` / `--text` / `--accent`
- El roadmap debería *sentirse* como un mapa estelar o línea temporal energética — no un Gantt de proyect management corporativo. La tipografía (Cormorant Garamond para meses, Inter para detalle) ya ayuda
- Los eventos comerciales y los energéticos deberían convivir visualmente — quizás un ícono/marca distinta para cada tipo (comercial = ●, energético = ✦)

## Deliverable

Single PR al repo `escucho-al-universo-report` con:
- `index.html` actualizado (las 3 secciones + el sortable)
- Un screenshot/preview en la descripción del PR
- Commit messages claros por feature (no un commit gigante)

## Testing manual

Antes de mergear, verificar en el preview de Vercel:
- [ ] Click en cada header de cada tabla ordena correctamente (ASC → DESC → reset)
- [ ] Filtro de texto es case-insensitive y funciona en todas las columnas
- [ ] Dropdowns muestran las opciones únicas de la columna y filtran
- [ ] Filtro + sort se combinan (orden se preserva al filtrar)
- [ ] Pestaña Roadmap aparece en la nav, click funciona, contenido renderiza
- [ ] Chart.js sigue renderizando en las pestañas que lo usan (sin conflictos)
- [ ] Mobile / responsive — las tablas grandes deben mantener `tbl-scroll`

## Nota sobre performance data

El reporte ahora muestra ROAS real por ad, pero la mayoría de los accionables de performance son pocos. Confirmar con Lauti qué accionables concretos sí quedan pendientes después de la reunión con la clienta — quizás el Plan de acción se acorte más, y el peso del reporte se corra hacia Retención + Creativo + Roadmap.
