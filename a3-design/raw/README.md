# Raw Extraction Data

This folder holds the **raw extraction artifacts** captured from the A3Data Figma manual (file `LmV1BuT3zPufCKMOoCsbiM`, node `2:21`) via the Figma REST API.

## Contents

- `figma/` — raw JSON returned directly by the Figma REST API (node trees).
- `text-sections/` — plain-text dumps of the manual's section content and intermediate extractions.
- `metadata/` — structure, styles, components, color and diagnostic dumps.

## Purpose

These files are kept for **traceability**: they let anyone verify how the tokens and documentation in `a3-design/` were derived from Figma.

## Rules

- **Do not edit these files manually.** They represent a point-in-time capture; editing breaks provenance. Regenerate them only by re-running the audit described in `../docs/figma-audit.md`.
- **Do not store tokens or secrets here.** The Figma access token (`FIGMA_TOKEN`) must never be written to any file; it is used only from the environment variable.
- **Public repositories:** if this repo is or becomes public, **review this folder before committing**. Raw API dumps can contain internal names, IDs, or institutional text that may not be intended for public release.
- Treat everything here as **derived input**, not as the source of truth. The source of truth is `../DESIGN.md` and `../tokens/*.json`.

## Provenance

See `../docs/figma-audit.md` for the endpoints used, frames analyzed, and known limitations.
