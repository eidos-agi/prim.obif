# OBIF — Open Brand and Identity Format

**A protocol / standard — not a brand asset CDN.**  
This repository is the **spec + intention + examples**.  
Real brand packs live next to the work (or in org-private repos); this repository does not own live brand data.

**OBIF v0.1.0-draft** is an additive profile of OKF v0.2.  
Every OBIF document is a valid OKF document.  
Renderers that know only OKF (e.g. [okflify](https://github.com/eidos-agi/okflify)) display it correctly and ignore profile keys.

OBIF packs are **Prims** — the primitive unit of knowledge and memory for AI.  
See [eidos-agi/prim](https://github.com/eidos-agi/prim).

```
OKF  — knowledge and trust                 https://github.com/eidos-agi/okflify
EMF  — human intent and durable memory     https://github.com/eidos-agi/emf
ORF  — research / investigation packs      https://github.com/eidos-agi/orf
OPF  — product graph                       https://github.com/eidos-agi/opf
ODFW — spreadsheet → bronze proof          https://github.com/eidos-agi/odwf
OPFF — personal finance packs              https://github.com/eidos-agi/opff
OMF  — meeting occurrences                 https://github.com/eidos-agi/omf
OCSF — corporate structure & capital       https://github.com/eidos-agi/ocsf
OBIF — brand & identity                    (this repo)
Prim — category name for all of the above  https://github.com/eidos-agi/prim
```

**Read [INTENTION.md](INTENTION.md) first.** It is load-bearing.

## What it models

- Brand foundations (name, positioning, personality, promise)
- Logo system (variants, clear space, minimum size, misuse rules)
- Color system (roles, values across color spaces, constraints, accessibility)
- Typography system (families, roles, hierarchy, fallbacks)
- Imagery and iconography direction
- Voice and verbal identity (tone by context, messaging pillars, do/don’t)
- Asset inventory with hashes and provenance
- Governance (approval rights, co-branding, supersession)

## Brand standards viewer

Consistent with Prim: **no fixed UX ships with the pack.**

A brand-standards view (logo board, color chips, type specimens, voice cards, do/don’t galleries) is a **generated projection** from the OBIF Prim — the same way a capitalization waterfall is a projection from an OCSF Prim.

Tools may render a rich brand board on demand. The Prim remains the source of truth; the PDF brand book is an export, not the store.

## Install (when validator ships)

```bash
git clone https://github.com/eidos-agi/obif.git
cd obif
# python3 -m pip install -e .   # when packaged
```

## Status

**v0.1.0-draft.** INTENTION and SPEC skeleton exist. Validator and richer examples next.

## License

MIT — Eidos AGI
