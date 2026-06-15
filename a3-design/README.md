# A3Data Design System

Documentation for A3Data's visual language, extracted from the company's Figma manual via the **Figma REST API**.

- **Figma file:** `LmV1BuT3zPufCKMOoCsbiM` — *A3Data – Manual AD*
- **Node analyzed:** `2:21` (Manual de Identidade / DataViz Guide)
- **Method:** Figma REST API (`GET /v1/files/{key}/nodes?ids=2:21`)
- **Generated:** 2026-06-15

## What this is

A single source of truth for colors, typography, spacing and data-visualization patterns used by A3Data. It is written to be useful for **designers, developers, QA, product, and AI agents**. The analyzed manual focuses on **data visualization** (dashboards / Power BI); general web/product UI is partially undefined and marked `needs-review`.

## Structure

```
a3-design/
├── DESIGN.md                         # Main spec (YAML front matter + Markdown)
├── README.md                         # This file
├── docs/
│   ├── spec.md                       # Internal documentation spec & conventions
│   ├── figma-audit.md                # API audit: endpoints, frames, limitations
│   ├── brand-guidelines.md           # Identity, logo, color, principles
│   ├── component-guidelines.md       # Buttons, cards, forms, tables, states...
│   ├── data-visualization-guidelines.md  # Dashboards, charts, KPI, heatmaps...
│   └── ai-implementation-rules.md    # Rules for Kiro/Codex/Gemini/ChatGPT etc.
├── examples/
│   ├── dashboard-screen.md           # Textual example: dashboard screen
│   ├── form-screen.md                # Textual example: form screen
│   └── landing-page.md               # Textual example: institutional/product page
└── tokens/
    ├── colors.json                   # Color tokens (full 100–900 scales)
    ├── typography.json               # Families, sizes, weights, roles
    ├── spacing.json                  # Base-8 spacing system
    └── components.json               # Patterns, states, recommended usage
```

## How to use

1. Read `DESIGN.md` first — it holds the canonical tokens (front matter) and the explanatory guide.
2. For machine consumption, import `tokens/*.json`.
3. Before building UI, follow `docs/ai-implementation-rules.md`.
4. If you find a value marked `needs-review`, do not guess — request validation or preserve the closest existing implementation.

## Status & conventions

- `ok` – value read directly from the manual / Figma styles.
- `inferred` – reasonable inference, explicitly flagged.
- `needs-review` – missing, ambiguous, or contradictory; requires human validation.

## Source of truth

Figma is upstream. If code and Figma diverge, report the divergence (see `docs/ai-implementation-rules.md`) before changing implementation. To refresh, re-run the REST audit in `docs/figma-audit.md`.
