---
version: "0.1"
name: "A3Data Design System"
source: "Figma REST API"
figma_source: "https://www.figma.com/design/LmV1BuT3zPufCKMOoCsbiM/A3Data---Manual-AD?node-id=2-21"
file_key: "LmV1BuT3zPufCKMOoCsbiM"
node_id: "2:21"
node_name: "Manual de Identidade / DataViz Guide"
method: "Figma REST API (GET /v1/files/{key}/nodes?ids=2:21)"
generated_at: "2026-06-15"
status: "draft – derived from the A3Data DataViz manual; UI-app tokens partially needs-review"

brand:
  name: "A3Data"
  description: "Data consultancy. Manual analyzed is the DataViz Guide focused on dashboards and data visualization."
  visual_principles:
    - "Clarity first: simplify complex information so patterns, trends and relationships are easy to read."
    - "Clean and professional look using a sans-serif type system."
    - "Consistent, standardized spacing and color to keep dashboards uncluttered."
    - "Protect the brand mark: use only original logo files, never redraw or alter it."

colors:
  primary:
    deep_sea:
      value: "#001863"
      usage: "Institutional primary / dark background base"
      source: "Figma REST API"
    tech_blue:
      value: "#0033FF"
      usage: "Primary accent blue"
      source: "Figma REST API"
    pink_nic:
      value: "#F53199"
      usage: "Primary accent magenta/pink"
      source: "Figma REST API"
  secondary:
    summer_time:
      value: "#FFEE00"
      usage: "Secondary accent yellow"
      source: "Figma REST API"
    amethyst_velvet:
      value: "#7B4AAF"
      usage: "Secondary accent purple"
      source: "Figma REST API"
    sky_frost:
      value: "#39D0FF"
      usage: "Secondary accent cyan"
      source: "Figma REST API"
  background:
    light:
      value: "#F5F5F5"
      usage: "Light theme background (Cor Background / BG)"
      source: "Figma REST API"
    dark:
      value: "#001863"
      usage: "Dark theme background"
      source: "Figma REST API"
  surface:
    value: "#FFFFFF"
    usage: "Cards/surfaces over light backgrounds (inferred from Branco token)"
    source: "Figma REST API (inferred)"
  text:
    primary: "#00083D"        # on light backgrounds
    secondary: "#F5F7FF"      # on dark backgrounds
    muted: "#A3A3A3"          # inferred from Gray 500
  border:
    default: "#EBEBEB"        # Gray 100; inferred as default divider/border
  semantic:
    success: "#35B769"        # Positivo
    warning: "#FF822E"        # Atenção
    danger: "#F91C1C"         # Negativo
    info: "needs-review"      # No explicit info token; Sky Frost #39D0FF is a candidate

typography:
  font_family:
    primary: "Segoe UI"
    secondary: "Segoe UI Light"
    data_labels: "DIN"
  headings:
    dashboard_title: "Segoe UI, Bold, 11px"
    chart_title: "Segoe UI, Bold, 10px"
    table_title: "Segoe UI, Bold, 14px"
    h1: "needs-review"   # general web/product scale not defined in manual
    h2: "needs-review"
    h3: "needs-review"
  body:
    default: "needs-review"   # general body scale not defined in manual
    small: "Segoe UI, Normal, 8px"   # chart categories/legends/axes
  labels:
    card_value: "DIN, Normal, 17px"
    data_label: "DIN, Normal, 9px"
    table_column_header: "Segoe UI, Semibold, 8px"

spacing:
  base_unit: "8px"
  rule: "Every spacing value must be a multiple of 8."
  scale:
    xs: "needs-review"   # below base-8; not defined
    sm: "8px"
    md: "16px"
    lg: "24px"
    xl: "needs-review"   # extend in multiples of 8 (32, 40...) and document

radius:
  sm: "needs-review"
  md: "needs-review"
  lg: "needs-review"
  full: "999px"

shadows:
  sm: "needs-review"
  md: "needs-review"
  lg: "needs-review"

components:
  buttons: "needs-review"      # not defined in node 2:21
  cards: "kpi cards documented (title + value typography); states needs-review"
  forms: "needs-review"
  tables: "documented (title/header/value/total typography)"
  navigation: "needs-review"
  badges: "needs-review"
  modals: "needs-review"

data_visualization:
  kpi_cards: "Title Segoe UI Light Bold 9px; Value DIN Normal 17px"
  charts: "12 chart types documented; categorical palette + divergent scale defined"
  tables: "Title 14px Bold; column header 8px Semibold; values 8px Normal; total 8px Bold"
  heatmaps: "documented as 'Gráfico de Calor'; use divergent scale (max/mid/min)"
  tooltips: "needs-review"

ai_rules:
  - "Use this DESIGN.md as the visual source of truth before implementing UI."
  - "Do not introduce new colors, typography or spacing without documenting the reason."
  - "If Figma and code diverge, report the divergence before changing implementation."
  - "When a token is marked as needs-review, ask for validation or preserve the closest existing implementation."
  - "This manual targets data visualization (Power BI). For general web/product UI, treat undefined scales as needs-review."
---

# A3Data Design System

## 1. Overview

This document is the human- and AI-readable source of truth for A3Data's visual language, derived from the company's **DataViz Guide / Manual de Identidade** in Figma (file `LmV1BuT3zPufCKMOoCsbiM`, node `2:21`), read through the Figma REST API.

Intended audiences:

- **Designers** – reference for color, type, spacing and chart patterns.
- **Developers** – tokenized values to implement dashboards and supporting UI.
- **QA** – a checklist to verify visual conformance.
- **Product** – shared vocabulary for visual decisions.
- **AI agents** – machine-readable tokens in the front matter and in `tokens/*.json`, plus explicit rules in section 12 and `docs/ai-implementation-rules.md`.

Scope note: the analyzed manual is primarily about **data visualization** (charts, KPI cards, tables, Power BI theming). General web/product UI components (buttons, forms, modals, navigation) are **not** defined in this node and are marked `needs-review`.

## 2. Brand Identity

A3Data is a data consultancy. The DataViz Guide exists to help analysts build clearer, more elaborate dashboards by applying consistent design choices (color, typography, iconography, spacing). The guiding idea, paraphrased from the manual, is that effective visualization simplifies complex information and makes patterns and trends easier to understand, while keeping a clean and professional appearance.

Brand mark rules (paraphrased):

- Use only the original brand files.
- Do not redraw, alter, extend, or recreate the drawing or typography of the mark.
- Two primary lockups exist: **main mark for light backgrounds** and **main mark for dark backgrounds**, plus approved variations (`needs-review` for the full variation list).

## 3. Color System

All hex values below are read from the manual's color sections (04–07) and cross-checked against the published Figma FILL styles (`A3Data/...`). Full scales (100–900) live in `tokens/colors.json`.

### Primary

| Token | Hex | Usage |
|-------|-----|-------|
| Deep Sea | `#001863` | Institutional primary / dark background base |
| Tech Blue | `#0033FF` | Primary accent blue |
| Pink Nic | `#F53199` | Primary accent magenta/pink |

### Secondary

| Token | Hex | Usage |
|-------|-----|-------|
| Summer Time | `#FFEE00` | Secondary accent yellow |
| Amethyst Velvet | `#7B4AAF` | Secondary accent purple |
| Sky Frost | `#39D0FF` | Secondary accent cyan |

### Neutrals

- Grayscale `Gray 100 → 900`: `#EBEBEB`, `#E0E0E0`, `#E8DEF6` *(needs-review – purple value inside grayscale)*, `#B8B8B8`, `#A3A3A3`, `#8F8F8F`, `#7A7A7A`, `#525252`, `#3D3D3D`.
- Off-White: `#F5F5F5`
- Branco (white): `#FFFFFF`
- Preto (black): `needs-review` (style exists; exact hex not shown in swatches).

### Backgrounds

- Light: `#F5F5F5`
- Dark: `#001863`

### Text colors

- Over light background: `#00083D`
- Over dark background: `#F5F7FF`

### Semantic (Cores por sentimento)

| Role | Base | Light | Dark |
|------|------|-------|------|
| Positivo (success) | `#35B769` | `#92E3B2` | `#217443` |
| Negativo (danger) | `#F91C1C` | `#FF5C5C` | `#AD0707` |
| Atenção (warning) | `#FF822E` | `#FFB371` | `#EF4C07` |
| Info | `needs-review` | – | – |

### Known color inconsistencies (needs-review)

- `DS 900 = #6EC400` (green) sits inside the navy "Deep Sea" scale — likely a labeling error.
- `TB 500 = #516EE0` is identical to `DS 500` — confirm if intentional.
- `Gray 300 = #E8DEF6` (purple) equals `AV 300` — likely a copy error.

## 4. Typography System

The manual defines typography for the **"Padrão do Power BI"** theme.

- **Primary family:** Segoe UI (titles, subtitles, legends, tables) — chosen for a clean, legible, professional look.
- **Card titles:** Segoe UI Light.
- **Data labels & card values:** DIN — chosen for legibility in data visualization.

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

Line-height and letter-spacing are not declared for these spec cards → `needs-review`. A general web/product scale (H1–H6, body, caption) is **not** in this node → `needs-review`.

## 5. Layout and Spacing

- **Base unit:** 8px. Every spacing value must be a multiple of 8.
- **Declared legend:** 8px, 16px, 24px.
- Mapped scale: `sm = 8px`, `md = 16px`, `lg = 24px`. `xs` and `xl` are `needs-review`.
- **Grids, containers, gutters, margins:** not declared as numeric tokens in node 2:21 → `needs-review`. Composition is shown by example only.

## 6. Radius, Borders and Shadows

- **Border-radius:** no named radius tokens in this manual → `needs-review`. `full = 999px` is a safe convention for pills/avatars.
- **Borders / dividers:** no dedicated token; `#EBEBEB` (Gray 100) is the inferred default separator.
- **Shadows / elevation:** no elevation tokens declared → `needs-review`.

## 7. Component Guidelines

This manual documents **DataViz patterns**, not an interactive UI kit. Items not present are `needs-review`.

### Buttons
`needs-review` — no button component in node 2:21.

### Cards
KPI cards are documented: title (Segoe UI Light, Bold, 9px) and value (DIN, Normal, 17px). Interaction states `needs-review`.

### Forms
`needs-review`.

### Tables
Documented typography: title 14px Bold, column header 8px Semibold, value 8px Normal, total 8px Bold (all Segoe UI). Row/zebra/border styling `needs-review`.

### Navigation
`needs-review`.

### Badges and Tags
`needs-review`.

### Modals and Overlays
`needs-review`.

## 8. Interface States

No explicit interaction-state specs (hover/active/focus/disabled/loading/error/empty) are declared in node 2:21. All states are `needs-review`. Until validated, derive states from existing tokens (e.g., use semantic colors for error/success, Gray scale for disabled) and document each decision.

## 9. Data Visualization Guidelines

A3Data works heavily with data, so this is the most developed area of the manual.

### Power BI categorical palette (apply in this order)

`#001863` → `#516EE0` → `#0033FF` → `#ADD3FF` → `#F53199` → `#FFADD9` → `#FFEE00` → `#FFBB00`.

- **Font color:** `#00083D`
- **Background:** `#F5F5F5`

### Divergent scale (for comparisons / heatmaps)

- Max: `#FFAA00`
- Mid: `#A3A3A3`
- Min: `#39D0FF`

### Sentiment in charts

Positivo `#35B769`, Negativo `#F91C1C`, Atenção `#FF822E`.

### Documented chart types

Lines, columns, stacked columns, columns + lines, bars, positive/negative, pie, donut, scatter, heatmap (calor), Sankey, map.

### Anti-clutter rules (paraphrased from the manual's intent)

- Keep spacing on the base-8 system to avoid visual noise.
- Use the categorical palette consistently and in order; reserve sentiment colors for meaning, not decoration.
- KPI cards: short title + prominent DIN value.

Tooltips, filters and slicers are not specified → `needs-review`.

## 10. Responsiveness

The manual does not define desktop/tablet/mobile breakpoints (it targets Power BI dashboards) → all responsive rules are `needs-review`. Validate with the brand/product team before assuming breakpoints.

## 11. Accessibility

Recommendations (general best practice; not all validated against the manual):

- **Contrast:** verify text/background pairs meet WCAG AA. `#00083D` on `#F5F5F5` is strong; small 8px chart text needs extra contrast care.
- **Minimum text size:** 8px chart labels are small — ensure adequate zoom/contrast; prefer larger sizes for non-chart UI.
- **Color + text/icon:** never rely on color alone for sentiment (positivo/negativo/atenção) — pair with labels or icons.
- **Focus visible & keyboard navigation:** `needs-review` (not specified).
- **Dashboard reading order:** provide logical reading order and labels for screen readers.

Full WCAG compliance requires manual testing with assistive technologies and expert review.

## 12. AI Implementation Rules

- Always consult `a3-design/DESIGN.md` (and `tokens/*.json`) before implementing UI.
- Respect existing tokens; do not invent colors, fonts, spacing or components.
- Flag inconsistencies (see section 3 known issues) instead of silently "fixing" them.
- When a value is `needs-review`, request validation or preserve the closest existing implementation.
- Do not change brand identity without documented justification.
- Document any divergence between Figma and code before changing implementation.

See `docs/ai-implementation-rules.md` for the full ruleset.

## 13. Figma Source

- **Link analyzed:** https://www.figma.com/design/LmV1BuT3zPufCKMOoCsbiM/A3Data---Manual-AD?node-id=2-21
- **File key:** `LmV1BuT3zPufCKMOoCsbiM`
- **Node id:** `2:21` (Manual de Identidade / DataViz Guide)
- **Method:** Figma REST API — `GET /v1/files/{file_key}/nodes?ids=2:21`
- **Generated at:** 2026-06-15
- See `docs/figma-audit.md` for endpoints, frames, and limitations.

## 14. Open Questions and Needs Review

- `info` semantic color (candidate: Sky Frost `#39D0FF`).
- `Preto` exact hex.
- Color inconsistencies: `DS 900` green, `TB 500`/`DS 500` duplicate, `Gray 300` purple.
- Line-height & letter-spacing for all type roles.
- General web/product type scale (H1–H6, body, caption).
- `xs`/`xl` spacing, grid, containers, gutters, margins.
- Radius and shadow/elevation tokens.
- Interaction states (hover/active/focus/disabled/loading/error/empty).
- UI components: buttons, forms, navigation, badges, modals.
- Tooltips, filters, slicers for dashboards.
- Responsive breakpoints.
