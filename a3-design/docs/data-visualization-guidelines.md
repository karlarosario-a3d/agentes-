# Data Visualization Guidelines

The core of the A3Data manual. Derived from sections 06–12 of Figma node `2:21` (Power BI / DataViz).

## Theme palette (Power BI)

When starting a dashboard, apply the categorical palette **in this order**:

| Slot | Hex |
|------|-----|
| Cor 1 | `#001863` |
| Cor 2 | `#516EE0` |
| Cor 3 | `#0033FF` |
| Cor 4 | `#ADD3FF` |
| Cor 5 | `#F53199` |
| Cor 6 | `#FFADD9` |
| Cor 7 | `#FFEE00` |
| Cor 8 | `#FFBB00` |

- **Font color:** `#00083D`
- **Background:** `#F5F5F5`

## Divergent scale (comparisons & heatmaps)

- **Max:** `#FFAA00`
- **Mid:** `#A3A3A3`
- **Min:** `#39D0FF`

Use for sequential/divergent encodings such as heatmaps and positive-to-negative comparisons.

## Sentiment encoding

- Positivo (good): `#35B769`
- Negativo (bad): `#F91C1C`
- Atenção (attention): `#FF822E`

Always pair sentiment color with a label, sign, or icon — never color alone.

## Typography for DataViz

| Role | Family | Weight | Size |
|------|--------|--------|------|
| Dashboard title | Segoe UI | Bold | 11px |
| Card title | Segoe UI Light | Bold | 9px |
| Card value | DIN | Normal | 17px |
| Chart title | Segoe UI | Bold | 10px |
| Categories / Legend / Axis X / Axis Y | Segoe UI | Normal | 8px |
| Data label | DIN | Normal | 9px |
| Table title | Segoe UI | Bold | 14px |
| Table column header | Segoe UI | Semibold | 8px |
| Table value | Segoe UI | Normal | 8px |
| Table total | Segoe UI | Bold | 8px |

- **DIN** is used for numbers (card values, data labels) for legibility.
- **Segoe UI** is used for everything else.

## KPI cards

- Short title (Segoe UI Light, Bold, 9px) above a prominent value (DIN, Normal, 17px).
- Spacing on the base-8 system (8 / 16 / 24px).
- Avoid stacking too many KPIs; keep each card focused on one metric.

## Tables

- Title 14px Bold; column headers 8px Semibold; values 8px Normal; totals 8px Bold.
- Emphasize totals with weight; keep dividers subtle (`#EBEBEB`, inferred).

## Chart types documented

Lines, columns, stacked columns, columns + lines, bars, positive/negative, pie, donut, scatter, **heatmap (gráfico de calor)**, **Sankey**, and **map**.

### Heatmaps

- Use the divergent scale (max `#FFAA00` → mid `#A3A3A3` → min `#39D0FF`).
- Keep cell labels legible; ensure sufficient contrast at small sizes.

## Anti-clutter rules (paraphrased)

- Keep all spacing on the base-8 grid to maintain rhythm and reduce noise.
- Apply the categorical palette consistently and in order.
- Reserve sentiment colors strictly for meaning.
- Prefer fewer, clearer visuals over dense, decorative ones.

## Tooltips, filters, slicers

`needs-review` — not specified in node 2:21. When implementing, reuse the theme palette, text color `#00083D`, and base-8 spacing, and document the choices.

## Needs-review

- Tooltip, filter, and slicer styling.
- Gridline/axis styling details, legend placement rules.
- Exact divergent stops beyond max/mid/min.
- Accessibility validation for 8px chart text.
