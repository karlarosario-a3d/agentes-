# Example: Dashboard Screen

A textual reference for a dashboard built with A3Data tokens. Values come from `tokens/*.json`; anything not defined in the manual is flagged `needs-review`.

## Intent

An executive dashboard summarizing KPIs and trends, optimized for clarity (A3Data's DataViz priority).

## Canvas

- **Background:** light `#F5F5F5`.
- **Text:** `#00083D` on light.
- **Spacing:** base-8 grid — section gaps `24px`, card gaps `16px`, inner padding `8–16px`.
- **Grid / container width:** `needs-review` (use a multiple-of-8 layout until defined).

## Header

- **Dashboard title:** Segoe UI, Bold, 11px, `#00083D`.
- Optional logo (light-background lockup), original file only.

## KPI row (cards)

Four KPI cards in a row, `16px` gap:

- **Surface:** `#FFFFFF` (inferred), `16px` padding.
- **Card title:** Segoe UI Light, Bold, 9px, `#00083D`.
- **Card value:** DIN, Normal, 17px.
- **Trend indicator:** sign + sentiment color + icon —
  - up/good → Positivo `#35B769`
  - down/bad → Negativo `#F91C1C`
  - attention → Atenção `#FF822E`
- **Card states (hover/selected):** `needs-review`.

## Charts area

Two-column chart grid, `24px` gap:

- **Line chart** (trend) — categorical palette in order (Cor 1 `#001863`, Cor 2 `#516EE0`, …).
- **Stacked columns** (composition) — same palette order.
- **Chart title:** Segoe UI, Bold, 10px.
- **Axes / categories / legend:** Segoe UI, Normal, 8px.
- **Data labels:** DIN, Normal, 9px.

## Heatmap panel

- Use the divergent scale: max `#FFAA00`, mid `#A3A3A3`, min `#39D0FF`.
- Keep cell labels legible; verify contrast.

## Table panel

- **Title:** Segoe UI, Bold, 14px.
- **Column header:** Segoe UI, Semibold, 8px.
- **Values:** Segoe UI, Normal, 8px.
- **Total row:** Segoe UI, Bold, 8px.
- **Dividers:** `#EBEBEB` (inferred).

## Accessibility notes

- Pair every sentiment color with a label/icon.
- Ensure focus states for interactive filters (`needs-review`).
- 8px chart text: confirm contrast and offer zoom.

## Needs-review for this screen

Grid/container widths, filter/slicer styling, card and filter interaction states, tooltip styling, responsive behavior.
