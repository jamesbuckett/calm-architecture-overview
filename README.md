# CALM — A Structured Primer in Architecture-as-Code

A single-file HTML tutorial on the FINOS **Common Architecture Language Model** (CALM), written for product and architecture leaders working in regulated financial-services environments.

The rendered tutorial is [`index.html`](./index.html). Open it directly in a browser — there is no build step.

---

## What it covers

Five modules that take the reader from "never heard of CALM" to "can write, validate, and visualise a CALM document in a home lab", followed by a one-page printable cheat sheet.

| # | Module | Covers |
|---|--------|--------|
| 01 | Origin & Motivation | History, problem space, FINOS governance, where CALM sits in the Architecture-as-Code movement |
| 02 | Conceptual Overview | The six primitives (Nodes, Relationships, Interfaces, Controls, Flows, Metadata), the JSON Schema foundation, Pattern vs Architecture, and a side-by-side comparison with C4, ArchiMate, and plain Mermaid |
| 03 | Anatomy of a Document | Minimal valid file, evolution into a three-tier web app with database and external IdP, rendered SVG diagram, CLI validation output |
| 04 | Patterns, Controls, Governance | Opinionated reference architectures, controls mapped to NIST SP 800-207, drift detection, automated ADR generation, worked Zero Trust pattern |
| 05 | Practical Use & Tooling | The `@finos/calm-cli` install and command set, CI workflow integration, role split (architect / platform / app engineer), home-lab starter exercise |
| — | Cheat Sheet | Key terms, minimal document structure, CLI command reference, decision guide, common anti-patterns, authoritative sources |

Each module ends with a **Key Takeaways** box and two **Checkpoint** questions a reader can use to self-test before moving on.

## Viewing it

```bash
xdg-open index.html        # Linux
open      index.html       # macOS
start     index.html       # Windows
```

The file is self-contained and can also be served from any static host (GitHub Pages, S3, plain Nginx).

## Repository layout

```
.
├── CLAUDE.md      Project conventions for Claude Code — single-file rules, design standards
├── PROMPT.md      The source brief used to generate the tutorial
├── index.html     The rendered tutorial — single self-contained file
└── README.md      This file
```

## How it was built

A deliberate set of constraints, all encoded in [`CLAUDE.md`](./CLAUDE.md):

- **Single self-contained file.** All HTML, CSS, and JavaScript live in `index.html`. No build step, no framework bundles, no external stylesheets.
- **No CDNs** other than Google Fonts for Noto Sans and Noto Sans Mono. If Google Fonts is unreachable, the page falls back to a system sans-serif stack.
- **Light theme primary, dark theme available.** Toggleable from the header; the choice persists in `localStorage` and respects `prefers-color-scheme` on first load.
- **One accent colour.** A restrained deep teal (`#0E5E57` in light theme, `#5EEAD4` in dark). No gradients.
- **Hand-drawn diagrams.** Every figure is inline SVG drawn against the same CSS variables as the rest of the page, so the diagrams theme-switch with the document.
- **Disciplined spacing scale.** `4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 96 / 128` — exposed as CSS custom properties.
- **Accessible by default.** Skip link, focus-visible outlines, `prefers-reduced-motion` respected on reveal animations, semantic landmark elements throughout.

## Source verification

CALM is an evolving specification. This tutorial paraphrases public FINOS material; before using any claim inside a regulated environment, verify against:

- [`finos/architecture-as-code`](https://github.com/finos/architecture-as-code) — schema, CLI, hub UI, and reference patterns
- [`@finos/calm-cli`](https://www.npmjs.com/package/@finos/calm-cli) — the official command-line tool on npm
- [finos.org](https://www.finos.org/) — project page, governance, and charter

Schema URLs and CLI flags can change between releases. The tutorial flags this in two places (Modules 03 and 05); always confirm against your installed CLI version.

## Author

**James Buckett** — Executive Director, Product Management, Infrastructure Platforms.

- GitHub — [@jamesbuckett](https://github.com/jamesbuckett)
- LinkedIn — [in/jamesbuckett](https://www.linkedin.com/in/jamesbuckett)
- X / Twitter — [@jamesbuckett](https://twitter.com/jamesbuckett)
