# Figma Audit

Record of the extraction performed against the A3Data Figma manual using the Figma REST API.

## Source

- **File key:** `LmV1BuT3zPufCKMOoCsbiM`
- **File name:** *A3Data – Manual AD*
- **Primary node analyzed:** `2:21` — "Manual de Identidade" / DataViz Guide
- **Last modified (file):** 2025-12-03
- **Extracted at:** 2026-06-15
- **Auth:** `X-Figma-Token` header sourced only from the `FIGMA_TOKEN` environment variable (value never logged or stored).

## Endpoints used

| Endpoint | Purpose | Result |
|----------|---------|--------|
| `GET /v1/files/LmV1BuT3zPufCKMOoCsbiM/nodes?ids=2731:3414` | Initial access validation (a glossary frame) | OK (200) |
| `GET /v1/files/LmV1BuT3zPufCKMOoCsbiM/nodes?ids=2:21` | Main extraction: identity/DataViz manual | OK (200) |

The node response also returned the embedded `styles`, `components`, and `componentSets` maps, which were used to confirm token names and the icon library.

## Frames analyzed (children of node 2:21)

| Frame | id |
|-------|----|
| 01. Capa-manual | `2008:1984` |
| 02. Introdução | `2008:1914` |
| 03. Logotipo | `2008:1836` |
| 04. Cores principais | `2015:2415` |
| 05. Cores secundárias | `2008:1349` |
| 06. Cores por tema | `2027:832` |
| 07. Personalização BI | `2031:1723` |
| 08. TIPOGRAFIA | `2008:1705` |
| 09. Iconografia | `2049:792` |
| 10. Espaçamento | `2367:1405` |
| 10/11/12. Exemplos de gráficos | `2059:1414`, `2059:2955`, `2060:1380` |

## Tokens found

- **Primary colors:** Deep Sea `#001863`, Tech Blue `#0033FF`, Pink Nic `#F53199` (each with a 100–900 scale).
- **Secondary colors:** Summer Time `#FFEE00`, Amethyst Velvet `#7B4AAF`, Sky Frost `#39D0FF` (each with a 100–900 scale).
- **Neutrals:** Gray 100–900, Off-White `#F5F5F5`, Branco `#FFFFFF`, Preto (hex not shown).
- **Semantic:** Positivo `#35B769`, Negativo `#F91C1C`, Atenção `#FF822E` (each with light/dark variants).
- **Text:** on-light `#00083D`, on-dark `#F5F7FF`.
- **Background:** light `#F5F5F5`, dark `#001863`.
- **Power BI palette:** Cor 1–8 + divergent (max `#FFAA00`, mid `#A3A3A3`, min `#39D0FF`).
- **Typography:** Segoe UI, Segoe UI Light, DIN; role sizes 8–17px (see `tokens/typography.json`).
- **Spacing:** base-8 system; legend 8 / 16 / 24px.

Published Figma FILL styles confirm the names above (e.g., `A3Data/Deep Sea`, `A3Data/TB 600`, `A3Data/Positivo`). Full lists are in `tokens/colors.json` and `tokens/typography.json`.

## Components / patterns identified

- **Logo:** `LOGO - A3DATA` plus light/dark lockups and "Variações".
- **Iconography:** **Phosphor Icons 2.1**, Stroke / Regular weight (confirmed by component metadata `Format=Stroke, Weight=Regular`). Hundreds of icon component sets present (communication, weather, maps, media, finance, people, security, education, etc.).
- **KPI cards, tables, and 12 chart types** documented as DataViz patterns (see `tokens/components.json`).
- **No interactive UI-app components** (buttons, forms, modals, navigation) in this node.

## API / plan limitations

- **Local variables endpoint** (`GET /v1/files/{key}/variables/local`) was **not** queried in this round; it typically requires an Enterprise plan and a token with the right scope. Several fills reference `VARIABLE_ALIAS` IDs, so semantic variable names could not be fully resolved from variables — names were instead derived from published FILL styles.
- **Rate limiting (HTTP 429)** was hit during exploration; extraction continued from the locally saved node JSON to avoid further calls.
- **Image/render endpoints** were not required for token extraction and were not used.

## Inconsistencies / needs-review

- `DS 900 = #6EC400` (green) inside the navy "Deep Sea" scale — likely a labeling error.
- `TB 500 = #516EE0` identical to `DS 500` — confirm if intentional.
- `Gray 300 = #E8DEF6` (purple) equals `AV 300` — likely a copy error.
- `Preto` hex not shown in swatches.
- No explicit `info` semantic color.
- Line-height / letter-spacing not declared for type roles.
- No radius, shadow, grid, container, breakpoint, or interaction-state tokens in node 2:21.

## Provenance / working files

Raw extraction artifacts retained in `a3-design/`: `figma_node_2_21.json`, `colors_raw.txt`, `extract1.txt`, `meta2.txt`, `structure.txt`, `sec_text_*.txt`.
