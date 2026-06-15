# Documentation Spec

How this design system documentation is organized, how tokens are named, and how to keep it in sync with Figma.

## Goals

- Be the single source of truth for A3Data's visual language.
- Be readable by humans **and** machines (front matter + JSON tokens).
- Never invent values: every token traces back to the Figma manual.

## File responsibilities

| File | Responsibility |
|------|----------------|
| `DESIGN.md` | Canonical tokens (YAML front matter) + explanatory guide. |
| `README.md` | Entry point and structure overview. |
| `tokens/*.json` | Machine-readable tokens for import. |
| `docs/figma-audit.md` | Provenance: endpoints, frames, limitations. |
| `docs/brand-guidelines.md` | Identity, logo, color, principles. |
| `docs/component-guidelines.md` | Component patterns and states. |
| `docs/data-visualization-guidelines.md` | Dashboard/chart/KPI patterns. |
| `docs/ai-implementation-rules.md` | Rules for AI agents. |
| `examples/*.md` | Textual reference screens. |

## Token naming conventions

- **Source families keep Figma names**, lowercased and snake_cased: `deep_sea`, `tech_blue`, `pink_nic`, `summer_time`, `amethyst_velvet`, `sky_frost`.
- **Numeric scales** preserve the manual's steps `100`–`900` (e.g., `deep_sea.scale.300`). `base` is the headline swatch.
- **Semantic tokens** use the manual's Portuguese intent mapped to English roles: `positivo→success`, `negativo→danger`, `atenção→warning`. Keep the original name in a note when helpful.
- **Spacing** uses t-shirt sizes mapped to the base-8 legend: `sm=8`, `md=16`, `lg=24`.
- **Typography roles** describe usage, not size: `dashboard_title`, `card_value`, `table_column_header`.
- Avoid inventing new families/roles. If a new one is unavoidable, add it with `status: "inferred"` and a `note`.

## Status field

Every token carries a status:

- `ok` — read directly from the manual or a published Figma style.
- `inferred` — derived by reasoning; must include a `note` explaining the inference.
- `needs-review` — missing, ambiguous, or contradictory; requires human validation. Must include a `note`.

## Handling `needs-review`

1. Do not replace a `needs-review` with a guessed value.
2. In implementation, preserve the closest existing token and flag it.
3. Collect open items in `DESIGN.md` §14 and in `figma-audit.md`.
4. Resolve only after human/brand-team confirmation, then change status to `ok` and record the source.

## Updating when Figma changes

1. Re-run the REST audit (`docs/figma-audit.md`) against node `2:21` (and any new relevant nodes).
2. Diff extracted values against `tokens/*.json`.
3. For each change: update the token, set its `status`, and note the date.
4. Bump `version` in `DESIGN.md` front matter (semantic-ish: patch for value fixes, minor for new tokens, major for restructuring).
5. Update `figma-audit.md` with the new `extracted_at` and any new limitations.
6. If Figma and code diverge, report before changing code (see `ai-implementation-rules.md`).

## Non-goals

- No frontend code, CSS, framework config, or package changes are produced from this documentation.
- This spec does not redefine the brand; it documents it.
