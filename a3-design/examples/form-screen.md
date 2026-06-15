# Example: Form Screen

A textual reference for a form screen. The A3Data manual (node `2:21`) does **not** define form components, so most field specs are `needs-review` and derived from existing tokens with that flag.

## Intent

A simple "create/edit record" form, consistent with A3Data colors and spacing.

## Canvas

- **Background:** light `#F5F5F5`.
- **Text:** `#00083D`.
- **Spacing:** base-8 — field gap `16px`, group gap `24px`, inner padding `8px`.
- **Form/container width:** `needs-review`.

## Header

- **Title:** Segoe UI, Bold — size `needs-review` (no general H1 scale; 14px table-title or 11px dashboard-title can be reused with a note). Color `#00083D`.

## Fields (all field specs needs-review)

For each field, until validated, derive from tokens:

- **Label:** Segoe UI — size `needs-review`, color `#00083D`.
- **Input text:** `#00083D` on `#FFFFFF` surface (inferred).
- **Input border:** `#EBEBEB` (Gray 100, inferred default).
- **Focus state:** `needs-review` — must be a visible focus ring (accessibility).
- **Disabled:** `needs-review` — use Gray scale (e.g., `#B8B8B8` text, `#EBEBEB` border).
- **Radius:** `needs-review`.

## Validation messaging

- **Error:** Negativo `#F91C1C` + message text + icon (never color alone).
- **Success:** Positivo `#35B769` + message + icon.
- **Warning:** Atenção `#FF822E` + message + icon.

## Actions (buttons)

- Buttons are `needs-review` (no button component in node 2:21).
- Until validated, use brand colors for emphasis (e.g., Tech Blue `#0033FF` or Deep Sea `#001863`) with accessible text contrast, base-8 padding, and a documented note. Do **not** finalize without validation.

## Accessibility notes

- Visible focus on every field and action.
- Associate labels with inputs; provide error text, not just color.
- Keyboard navigation order top-to-bottom.

## Needs-review for this screen

Field sizing, label/input/help-text type scale, focus/disabled/hover states, radius, button specs, spacing of action bar.
