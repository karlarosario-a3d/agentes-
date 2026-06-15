# Review Checklist

Use this checklist before relying on the A3Data design system or before committing changes. Tick each item; flag anything that fails instead of guessing.

## Color tokens
- [ ] Primary colors present and match Figma (Deep Sea `#001863`, Tech Blue `#0033FF`, Pink Nic `#F53199`).
- [ ] Secondary colors present (Summer Time `#FFEE00`, Amethyst Velvet `#7B4AAF`, Sky Frost `#39D0FF`).
- [ ] Neutrals, backgrounds, and text colors documented.
- [ ] Semantic colors mapped (success/warning/danger); `info` still `needs-review`.
- [ ] Known inconsistencies flagged (`DS 900`, `TB 500`/`DS 500`, `Gray 300`), not silently fixed.

## Typography
- [ ] Families documented (Segoe UI, Segoe UI Light, DIN).
- [ ] Role sizes/weights match the manual (dashboard/card/chart/table).
- [ ] Line-height & letter-spacing remain `needs-review` (not invented).
- [ ] General web type scale (H1–H6/body) remains `needs-review`.

## Spacing
- [ ] Base-8 rule stated; scale `sm=8 / md=16 / lg=24`.
- [ ] `xs`/`xl`, grid, containers remain `needs-review`.

## Brand guidelines
- [ ] Visual principles paraphrased (no long institutional copy reproduced).
- [ ] Logo rules present (original files only; do not recreate the mark).
- [ ] Iconography noted (Phosphor Icons 2.1, Stroke/Regular).

## Components
- [ ] KPI cards and tables documented from real specs.
- [ ] Buttons/forms/navigation/badges/modals remain `needs-review`.
- [ ] Interaction states remain `needs-review` with safe-derivation notes.

## Data visualization
- [ ] Power BI categorical palette (Cor 1–8) in correct order.
- [ ] Divergent scale (max `#FFAA00` / mid `#A3A3A3` / min `#39D0FF`).
- [ ] Sentiment encoding paired with text/icon.
- [ ] 12 chart types listed; heatmap uses divergent scale.

## Needs-review items
- [ ] All `needs-review` items collected in `DESIGN.md` §14.
- [ ] No `needs-review` value replaced by a guess anywhere.

## Security
- [ ] No Figma token / secret in any file (`DESIGN.md`, docs, tokens, raw).
- [ ] `FIGMA_TOKEN` used only from the environment variable.
- [ ] `raw/` reviewed before any public commit.

## Scope integrity
- [ ] Nothing outside `a3-design/` was created, edited, or deleted.
- [ ] No frontend code / CSS / framework config / `package.json` changes.
- [ ] Documentation (`DESIGN.md`, `README.md`, `docs/`, `examples/`) and `tokens/*.json` preserved unless intentionally updated.

## Structure
- [ ] `a3-design/` contains `DESIGN.md`, `README.md`, `docs/`, `examples/`, `raw/`, `tokens/`.
- [ ] `raw/` contains `figma/`, `text-sections/`, `metadata/`, and `raw/README.md`.

## How to use
- Run this checklist after any update to the system or before publishing.
- For any failed item: stop, flag it (see `ai-implementation-rules.md` §4 and §6), and request validation.
