# Estrategia Paid Media — Escucho al Universo
**Elaborado por:** Nebulab  
**Fecha:** 2026-04-09  
**Horizonte:** Q2-Q4 2026

---

## PUNTO DE PARTIDA

La cuenta tiene ROAS 9.2x. No hay nada roto en el paid media. El problema es que el negocio está en un loop de adquisición pura: gasta ARS 5,094 para traer un cliente que en el 94% de los casos no vuelve jamás. Cada mes hay que re-financiar el pipeline desde cero.

La estrategia apunta a dos cosas: **defender el ROAS mientras el CPM sube** y **construir el sistema que hace que los clientes vuelvan**, porque ahí está el verdadero leverage.

---

## OBJETIVOS Y KPIs

| KPI | Actual | Meta 6 meses | Meta 12 meses |
|---|---|---|---|
| ROAS blended mensual | 9.2x (promedio) | ≥ 9x | ≥ 10x |
| CAC | ARS 5,094 | ARS 5,500* | ARS 5,000 |
| Tasa de segunda compra | 5.9% | 10% | 15% |
| AOV | ARS 40,033 | ARS 50,000 | ARS 55,000 |
| CPM promedio | ARS 3,157 | ARS 2,500 | ARS 2,200 |
| Revenue mensual promedio | ARS 4.1M | ARS 5.5M | ARS 7M |

*El CAC puede subir en el corto plazo mientras se optimiza el mix de campañas. Lo que importa es el LTV/CAC.

---

## ESTRUCTURA DE CAMPAÑAS

### Arquitectura recomendada (3 capas)

```
CAPA 1 — PROSPECCIÓN (público frío)
├── [PROD] Campaña Coloreá y Aprendé
├── [PROD] Campaña Diario Gratitud
├── [PROD] Campaña UPC
└── [PROD] Campaña Combos

CAPA 2 — RETARGETING (interactuaron, visitaron, ATC)
└── [RT] Campaña Retargeting Dinámico / Catálogo

CAPA 3 — RETENCIÓN (ya compraron)
└── [RET] Campaña Compradores anteriores (cross-sell)
```

### Desglose por campaña

#### CAPA 1A — Prospección Coloreá y Aprendé
- **Objetivo:** Ventas
- **Presupuesto:** 25% del budget total
- **Ad sets:**
  - `OPEN_VID` — Audience abierta, video corto
  - `OPEN_SECUENCIA` — Audience abierta, secuencia de catálogo
  - `INT_ESPIRITUAL` — Intereses: tarot, espiritualidad, journaling
- **Por qué primero:** Es el producto con más revenue histórico (ARS 11M) y tiene el naming más claro para creative. Funciona en top y mid funnel.

#### CAPA 1B — Prospección Diario Gratitud
- **Objetivo:** Ventas
- **Presupuesto:** 25% del budget total
- **Ad sets:**
  - `OPEN_VID` — Video contenido corto (el "Video / Contenidos CORTO" tuvo CPM 851)
  - `OPEN_CARR` — Carrusel de uso/páginas del diario
  - `LOOK_VSW` — Lookalike VSW 180D
- **Nota:** Este producto tiene la mayor cantidad de compradores (319) — la audiencia lookalike va a ser muy precisa.

#### CAPA 1C — Prospección UPC
- **Objetivo:** Ventas
- **Presupuesto:** 15% del budget total
- **Ad sets:**
  - `OPEN_VID` — Video marca personal (la creadora hablando del libro)
  - `OPEN_IMG` — Imagen estática (el `Imagen // UPC` tuvo CPM 1,091 — el mejor de imagen)
- **Nota:** UPC está sub-invertido. Tercer producto más grande (ARS 7.7M) con solo 9.6% del spend histórico.

#### CAPA 1D — Prospección Combos
- **Objetivo:** Ventas
- **Presupuesto:** 15% del budget total
- **Ad sets:**
  - `OPEN_SECUENCIA` — Secuencia mostrando qué trae el combo (la `secuencia_combos` tuvo CPM 1,260)
  - `INT_REGALO` — Intereses + comportamiento de regalo
- **Por qué prioridad:** CPM más bajo (ARS 1,341) + AOV más alto (ARS 60-65K). Es el mejor ratio del negocio para escalar ROAS.

#### CAPA 2 — Retargeting
- **Objetivo:** Ventas
- **Presupuesto:** 10% del budget total
- **Ad sets:**
  - `RT_ATC_30D` — Agregaron al carrito, últimos 30 días
  - `RT_PV_30D` — Visitaron producto, últimos 30 días
  - `RT_IG_FB_60D` — Interactuaron con perfil IG/FB, últimos 60 días
- **Creative:** Urgencia suave + testimonios + mostrar el producto en uso

#### CAPA 3 — Retención / Cross-sell
- **Objetivo:** Ventas
- **Presupuesto:** 10% del budget total
- **Audiencia:** Custom audience de compradores de TiendaNube (lista de emails) con ventana 365D
- **Lógica:** Si compraste el Diario Gratitud → te muestro el combo con AmarMe. Si compraste UPC → te muestro Coloreá.
- **Creative:** "Ya conocés la marca, este es el siguiente paso"
- **Por qué:** Esta audiencia ya convirtió. CAC es casi cero. El ROAS de esta capa debería ser 20x+.

---

## BUDGET ALLOCATION

### Distribución recomendada del budget mensual

| Capa | Campaña | % | Budget ARS 500K/mes |
|---|---|---|---|
| Prospección | Coloreá y Aprendé | 25% | ARS 125,000 |
| Prospección | Diario Gratitud | 25% | ARS 125,000 |
| Prospección | UPC | 15% | ARS 75,000 |
| Prospección | Combos | 15% | ARS 75,000 |
| Retargeting | RT dinámico | 10% | ARS 50,000 |
| Retención | Cross-sell compradores | 10% | ARS 50,000 |

*Ajustar el total según el mes (ver calendario estacional abajo)*

---

## CALENDARIO ESTACIONAL — BUDGET MENSUAL RECOMENDADO

Basado en el patrón histórico de ROAS:

| Mes | Índice ROAS histórico | Budget recomendado | Foco |
|---|---|---|---|
| Abr-26 | Alto (12.9x) | ARS 500K | Coloreá + Combos |
| May-26 | Medio (8.8x) | ARS 450K | Diario Gratitud + UPC |
| Jun-26 | Medio (8.7x) | ARS 450K | Diario Gratitud + UPC |
| Jul-26 | Medio (8.5x) | ARS 500K | Iniciar teaser Agendas 2027 |
| Ago-26 | Bajo (5.1x) | ARS 250K | Solo retargeting + retención |
| Sep-26 | Medio (8.8x) | ARS 500K | Lanzamiento Agendas + Coloreá |
| Oct-26 | Medio (7.7x) | ARS 500K | Agendas + Combos regalo |
| Nov-26 | MUY ALTO (15.1x) | ARS 800K | TODO encendido — navidad |
| Dic-26 | Alto (8.3x-14.1x) | ARS 1,000K | Pico máximo — regalar |
| Ene-27 | MUY ALTO (13x) | ARS 1,000K | Año nuevo — Diario Gratitud |

**Agosto es el mes para bajar el pie del acelerador.** ROAS históricamente 5.1x — la mitad que noviembre. No tiene sentido invertir lo mismo en agosto que en noviembre.

**Noviembre-Enero es la temporada dorada.** El presupuesto de esos 3 meses debería ser el 40% del gasto anual.

---

## ESTRATEGIA CREATIVA

### El problema central del creative actual

El CPM subió de ARS 1,258 a ARS 3,157 (+151% en 2 años). Eso significa que con el mismo budget, hoy llegás a la mitad de personas que hace 2 años. La única forma de compensarlo sin subir el budget es mejorar la eficiencia del creative — que la gente pare el scroll.

### Los formatos que funcionan (por datos reales de CPM)

**Tier 1 — CPM < ARS 1,200 (usar más)**
| Formato | CPM | Ejemplo en cuenta |
|---|---|---|
| Video contenido corto | ARS 851 | "Video / Contenidos CORTO" |
| Carrusel estilo individual | ARS 948 | "Carr / Estilo INDIVIDUAL" |
| Imagen UPC | ARS 1,091 | "Imagen // UPC" |
| Video contenido agenda | ARS 1,091 | "Video / Contenidos de la Agenda" |

**Tier 2 — CPM ARS 1,200-1,600 (mantener)**
| Formato | CPM | Ejemplo en cuenta |
|---|---|---|
| Secuencia combos | ARS 1,260 | "secuencia_combos" |
| Imagen GRAT | ARS 1,351 | "01.IMG.GRAT" |
| Secuencia catálogo | ARS 1,482 | "secuencia_catálogo" |

**Tier 3 — CPM > ARS 1,800 (revisar, rotar)**
Los videos de colección (`01_VID_COL_DIC`, CPM 1,961; `01_VID_COL_NOV`, CPM 2,268) llevan el mayor spend de la cuenta (ARS 836K y ARS 471K respectivamente) pero tienen el CPM más alto. Pueden estar en fatiga o el formato está perdiendo eficiencia.

### Principios creativos

**1. Marca personal > producto**
La creadora ES la marca. Los ads donde ella aparece o habla tienen mejor engagement que los de producto solo. Priorizar UGC y testimonios en primera persona.

**2. Contenido corto > producción elaborada**
Los "Contenidos CORTO" tienen CPM de ARS 851 — el más bajo de todos los videos con escala. El CPM de los videos de colección (más producidos) es 2-3x mayor. Menos producción, más autenticidad.

**3. Secuencias para escala**
Las secuencias de combos y catálogo son el único formato que escala a CPM bajo (ARS 1,260-1,482) con budget alto (ARS 453K y ARS 312K respectivamente). Para meses de alto budget, las secuencias son el vehículo.

**4. El carrusel de estilo individual es un hallazgo**
CPM de ARS 948 con ARS 65K spend. No está en rotación principal. Vale la pena escalar este formato.

### Plan de producción de creative (por cuatrimestre)

**Q2-26 (Abr-Jun):**
- 3 videos cortos estilo contenido (30-60 seg, sin producción) para Coloreá, Diario Gratitud, Combos
- 2 secuencias nuevas (combo regalo + colección temporada)
- 1 carrusel "estilo individual" por producto top 3
- Reactivar `Imagen // UPC` — tuvo CPM 1,091 con ARS 151K spend

**Q3-26 (Jul-Sep) — Preparación temporada:**
- Teaser agendas 2027 desde agosto
- Video de la creadora presentando el nuevo producto (preventa)
- Secuencia de catálogo completa con todos los productos nuevos

---

## AUDIENCIAS

### Públicos fríos (prospección)

**Abierto + Advantage+**
Dejar que Meta optimice. Funciona especialmente bien para Diario Gratitud y UPC donde ya hay historial de conversiones.

**Intereses (segmentación detallada)**
Para usar en paralelo con abierto, no en lugar de:
- Tarot, Astrología, Carta astral
- Espiritualidad, Meditación
- Journaling, Papelería, Bujo
- Desarrollo personal, Autoconocimiento
- Luna llena, Rituales, Chakras

**Lookalikes**
- LAL 1-3% Compradores TiendaNube (lista completa)
- LAL 1-3% VSW 180D
- LAL 1-3% Seguidores IG

**Test recomendado: segmento 18-24**
CPM de ARS 905 — 3.4x más barato que 35-44. Actualmente recibe solo 4.8% del budget. Propuesta: destinar ARS 50K a un test en 18-24 con el creative de "Video / Contenidos CORTO" para ver si convierte. Si el CVR es al menos 40% del 25-34, el CAC sigue siendo mejor.

### Retargeting

**Ventanas recomendadas:**
- Visitaron producto últimos 30D (mayor intención)
- Agregaron al carrito sin comprar (30D)
- Vieron video 75%+ (60D)
- Interactuaron con perfil IG/FB (60D)

**Excluir siempre:** compradores últimos 30D del ad set de retargeting, compradores últimos 60D del ad set de frío.

### Retención / Cross-sell

Subir lista de clientes de TiendaNube mensualmente como Custom Audience (email + teléfono). Segmentar por producto comprado para mostrar el siguiente paso lógico:

| Compraron | Mostrar |
|---|---|
| Diario Gratitud | Combo Diario + AmarMe, UPC |
| Coloreá y Aprendé | Diario Gratitud, Oráculo AmarMe |
| UPC | Oráculo AmarMe, Combo UPC + AmarMe |
| Agenda sola | Combo con Diario, UPC |
| 1 producto solo | Combo del producto que compraron |

---

## RETENCIÓN — EL LEVER QUE MÁS MUEVE LA AGUJA

Esto va más allá del paid media pero el paid media no puede ignorarlo.

**El dato:** 94.2% compra una vez. LTV a 1 compra: ARS 39,370. LTV a 3+ compras: ARS 282,813.

Mover la tasa de retención del 5.9% al 15% implica:
- ~185 clientes adicionales que llegan a 2 compras
- Revenue adicional estimado: ~ARS 7.5M anuales
- Sin un peso más de inversión en adquisición

**Lo que hace el paid media para ayudar:**

1. **Campaña de retención en Meta** (Capa 3, 10% del budget): mostrar el siguiente producto a quienes ya compraron. Costo marginal bajo, ROAS altísimo.

2. **Excluir compradores recientes de prospección**: si alguien compró en los últimos 60D, no gastar en mostrarte el mismo ad de adquisición. Es plata tirada.

3. **Lookalike de compradores de 2+ veces**: esta audiencia es oro. Son los perfiles que tienen más probabilidad de volver. Crear una LAL específica de los 114 clientes que compraron 2+ veces.

**Lo que necesita resolver fuera del paid:**
- Flujo de email post-compra (mínimo 3 emails en 30 días)
- WhatsApp o push para lanzamientos nuevos a base de clientes
- Programa de preventa para compradores anteriores

---

## SEÑALES DE ALERTA A MONITOREAR

### 1. Descuentos (39% de órdenes)
ARS 3.35M en descuentos aplicados. Antes de escalar el budget, entender si el descuento es una palanca de conversión real o si se está regalando margen a gente que hubiera comprado igual. Testear: misma audiencia, un ad set con cupón y uno sin.

### 2. CPM en escalada
Si el CPM supera ARS 3,500 sostenidamente, hay que revisar la estrategia de puja (considerar cambiar de menor costo a costo objetivo) y acelerar la rotación de creative.

### 3. ROAS de los últimos 3 meses
Feb-26 (6.7x), Mar-26 (7.2x) están por debajo del promedio histórico (9.2x). Puede ser estacionalidad normal (son meses de baja histórica) pero si Abr-Jun no rebota a 9x+, hay que revisar la estructura de campañas.

### 4. Export de Meta sin conversiones
Los dos exports recibidos tienen breakdown demográfico, lo que elimina los datos de CTR, ROAS y compras por ad. Para medir qué creativo convierte mejor se necesita el export sin breakdown (campaña/adset/ad solamente). Solicitarlo para el siguiente ciclo.

---

## QUICK WINS (ejecutar en las próximas 2 semanas)

1. **Subir budget a Combos** — Pasar de 6.3% a 15% del spend. Mejor ratio CPM/AOV de toda la cuenta. No requiere nuevo creative — la `secuencia_combos` ya existe y funciona.

2. **Activar Capa 3 (retención)** — Subir lista de clientes de TiendaNube a Meta y crear un ad set de cross-sell. Creative mínimo viable: imagen + copy "Completá tu kit / El siguiente paso".

3. **Reactivar `Imagen // UPC`** — CPM 1,091, ARS 151K historial. No está activo actualmente. Prender y asignar ARS 30-50K.

4. **Escalar `secuencia_combos`** — ARS 453K gastados, CPM 1,260. Es el ad más eficiente de toda la cuenta a escala. Subir budget y testear en nuevos ad sets de intereses.

5. **Apagar o rotar `01_VID_COL_NOV` y `01_VID_COL_DIC`** — Juntos llevan ARS 1.3M de spend con CPM 2,268 y 1,961 respectivamente. Los videos más caros de la cuenta en CPM. Probable fatiga de audience. Reemplazar con nuevo creative.

6. **Segmentar geográficamente Córdoba y Santa Fe** — Son el 21.4% del revenue combinados. Crear ad sets específicos para esas provincias con budget dedicado puede mejorar relevancia y bajar CPM.

---

## PRÓXIMOS PASOS

**Semana 1:**
- [ ] Implementar quick wins 1-4
- [ ] Subir lista de clientes TiendaNube a Meta (Custom Audience)
- [ ] Solicitar export de Meta sin breakdown demográfico

**Semana 2:**
- [ ] Crear estructura de 3 capas si no está implementada
- [ ] Brief de creative para Q2: 3 videos cortos + 2 secuencias
- [ ] Definir flujo de email/WhatsApp post-compra con el cliente

**Mes 1-2:**
- [ ] Lanzar test segmento 18-24 (ARS 50K)
- [ ] Lanzar Capa 3 retención con primera versión de cross-sell
- [ ] Medir AOV con y sin descuento para decidir política de cupones

**Q3 (preparación temporada):**
- [ ] Teaser agendas 2027 desde agosto
- [ ] Construir audiencia de preventa (compradores históricos)
- [ ] Escalar budget a partir de septiembre siguiendo curva estacional
