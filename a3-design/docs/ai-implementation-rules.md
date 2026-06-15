# AI Implementation Rules

Rules for AI agents (Kiro, Codex, Gemini, ChatGPT, Claude, and others) when implementing or modifying UI for A3Data.

## 1. Source of truth

- Always read `a3-design/DESIGN.md` and `a3-design/tokens/*.json` **before** implementing or changing any UI.
- Figma is upstream. This documentation reflects Figma node `2:21` of file `LmV1BuT3zPufCKMOoCsbiM`.

## 2. Respect existing tokens

- Use only documented colors, typography, spacing, and patterns.
- Do **not** invent colors, fonts, font sizes, spacing values, radii, shadows, or components.
- Keep spacing on the base-8 system (8 / 16 / 24px; extend only in multiples of 8 and document it).
- Use the Power BI categorical palette in order for charts; reserve sentiment colors for meaning.

## 3. Handle `needs-review`

- If a needed value is `needs-review`, **stop and ask for validation**, or preserve the closest existing implementation and clearly flag it.
- Never replace a `needs-review` with a guessed value.
- Examples currently `needs-review`: buttons, forms, navigation, badges, modals, interaction states, radius, shadows, grids/containers, breakpoints, line-height/letter-spacing, `info` color, `Preto` hex.

## 4. Flag inconsistencies

- Known issues must be surfaced, not silently "fixed":
  - `DS 900 = #6EC400` (green inside navy scale).
  - `TB 500 = #516EE0` duplicate of `DS 500`.
  - `Gray 300 = #E8DEF6` (purple inside grayscale).
- If you spot a new inconsistency, report it and add it to `docs/figma-audit.md` under needs-review.

## 5. Do not change brand identity

- Do not alter, redraw, or recreate the logo; use original files only.
- Do not change the palette or type system without documented justification approved by the brand/product team.

## 6. Report Figma ↔ code divergence

- If implementation diverges from Figma, **report the divergence first** with: the token, the Figma value, the code value, and a recommendation. Do not change code before reporting.

## 7. Scope boundaries

- Documentation tasks must only create/edit files inside `a3-design/`.
- Do not modify application code, CSS, React/Svelte/Tailwind, `package.json`, or any file outside `a3-design/`.
- Do not run Code Connect or design-to-code onboarding as part of documentation work.

## 8. Accessibility

- Never use color alone to convey meaning — pair with text/icon.
- Ensure visible focus states and adequate contrast (target WCAG AA).
- Treat very small text (8px chart labels) carefully; prefer larger sizes for non-chart UI.

## 9. Security & secrets

- Read the Figma token only from the `FIGMA_TOKEN` environment variable.
- Never print the token, never write it to any file.

## 10. Updating the system

- When Figma changes, follow the update flow in `docs/spec.md`, refresh `tokens/*.json`, bump `version`, and update `figma-audit.md`.

## Quick checklist (before shipping UI)

- [ ] Read `DESIGN.md` + relevant `tokens/*.json`.
- [ ] All values trace to documented tokens.
- [ ] No `needs-review` value silently guessed.
- [ ] Inconsistencies flagged.
- [ ] Spacing on base-8.
- [ ] Sentiment color paired with text/icon.
- [ ] No files changed outside `a3-design/` (for docs tasks).
