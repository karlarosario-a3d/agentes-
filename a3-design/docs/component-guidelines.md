# Component Guidelines

Component patterns derived from Figma node `2:21`. This node is a **DataViz / identity manual**, so it defines visualization patterns (cards, tables, charts) but not a full interactive UI kit. Undefined components are `needs-review` and must be validated before implementation.

## How to read this

- Use real tokens from `tokens/*.json` and `DESIGN.md`.
- Where a spec is missing, derive from existing tokens and flag the decision — do not invent.

## Buttons

`needs-review` — no button component is defined in node 2:21. A button instance exists elsewhere in the file (node `2731:3414`, naming pattern `Contained / Medium|Large / Normal / Text / Secondary`) but it is **not** authoritative for this round. Do not derive button specs from it without validation.

## Cards (KPI cards)

Documented for dashboards:

- **Title:** Segoe UI Light, Bold, 9px.
- **Value:** DIN, Normal, 17px.
- **Padding/gap:** use base-8 (8 / 16 / 24px).
- **Surface:** white `#FFFFFF` on light background `#F5F5F5` (surface inferred).
- **States** (hover/selected/loading): `needs-review`.

## Forms

`needs-review` — no input, select, checkbox, or validation specs in this node. When required, build from tokens: text `#00083D`, borders `#EBEBEB`, error `#F91C1C`, success `#35B769`, base-8 spacing — and document each choice.

## Tables

Documented typography (all Segoe UI unless noted):

| Element | Weight | Size |
|---------|--------|------|
| Title | Bold | 14px |
| Column header | Semibold | 8px |
| Value | Normal | 8px |
| Total | Bold | 8px |

Row height, zebra striping, borders, and sorting affordances are `needs-review`. Suggested defaults: dividers `#EBEBEB`, totals emphasized with weight (already Bold).

## Navigation

`needs-review` — no navbar/sidebar/tabs/breadcrumb specs.

## Badges and Tags

`needs-review` — no badge/tag component. If needed, map status to sentiment colors (success/danger/warning) with text labels, full radius `999px` for pills.

## Modals and Overlays

`needs-review` — no modal/dialog/drawer/tooltip specs.

## Interface states

No explicit state specs exist in node 2:21. Treat the full set as `needs-review`:

| State | Guidance (until validated) |
|-------|----------------------------|
| default | Base tokens. |
| hover | `needs-review` (derive a subtle tonal shift from the color scale). |
| active | `needs-review`. |
| focus | `needs-review` — ensure a visible focus ring for accessibility. |
| disabled | `needs-review` — use Gray scale, reduced emphasis. |
| loading | `needs-review`. |
| error | Use Negativo `#F91C1C` + text/icon. |
| empty | `needs-review` — provide clear empty-state messaging. |
| success | Use Positivo `#35B769` + text/icon. |
| warning | Use Atenção `#FF822E` + text/icon. |

## Iconography in components

- Library: Phosphor Icons 2.1, Stroke / Regular.
- Keep one icon family and weight across components.

## Needs-review summary

Buttons, forms, navigation, badges, modals, tooltips, all interaction states, radius, shadows, and table row styling.
