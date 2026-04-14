# Escucho al Universo · Diagnóstico Paid Media & Retención

Landing de diagnóstico para presentación al cliente. Análisis del período **Sep 2024 — Abr 2026** sobre datos de Meta Ads + TiendaNube.

**Preparado por:** [Nebulab](https://nebulab.studio)

---

## Qué contiene

Landing single-file (`index.html`) con 8 pestañas navegables:

- **Overview** — KPIs macro + alertas destacadas (recompra 5.9% · CPM +151%)
- **Performance mensual** — evolución ROAS/Spend/Revenue con filtros por año y clasificación
- **Meta Ads** — breakdown de formatos, top ads por eficiencia de CPM, demografía, geografía
- **Productos** — top 10 por revenue + paradoja de combos + UPC sub-invertido
- **Retención** — LTV por segmento, segmentación de la base (1,965 clientes), mapa de cross-sell, escenarios de impacto, 5 flujos propuestos
- **Alertas** — 8 ineficiencias detectadas ordenadas por urgencia
- **Oportunidades** — 5 palancas priorizadas por impacto
- **Plan de acción** — 10 movimientos accionables con prioridad y timing

## Stack

HTML + CSS vanilla + Chart.js (via CDN). Sin build step. Fonts: Cormorant Garamond + Inter.

## Deploy (Vercel)

```
cleanUrls: true
trailingSlash: false
```

La landing se sirve desde `index.html` en la raíz. No requiere configuración adicional.

## Datos sensibles

Los CSVs de Meta Ads y TiendaNube están excluidos vía `.gitignore`. El repo solo contiene:
- Landing HTML (sin PII)
- Análisis en Markdown (sin PII)
- Config de deploy

## Brand note

La paleta actual es una propuesta cósmica/esotérica (índigo profundo + dorado brass + amatista) pensada para la identidad de Escucho al Universo. Pendiente de aplicar Design System definitivo vía Figma API cuando esté disponible.
