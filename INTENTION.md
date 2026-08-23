# RETIRED

**Successor: [prim.brand](https://github.com/eidos-agi/prim.brand).** Do not extend this document.

---

# OBIF Intention

**Status:** load-bearing product intention for the public format  
**Instance dogfood:** real brand packs must share this intention

---

## One sentence

OBIF is the open format for **self-contained, evidence-backed packages that make a brand’s identity system — foundations, logo, color, type, imagery, voice, assets, and governance — machine-readable and agent-usable**, so both humans and agents treat the brand Prim as the source of truth and generate brand-standards views on demand.

---

## Why this exists

Brand identity today usually lives in:

- PDF brand books that agents cannot reliably parse
- Figma files and locked design systems
- Scattered Drive folders of logos and “final_final_v3” assets
- Slack threads and tribal knowledge about “what we say / don’t say”
- Marketing decks that drift from the “official” guide

Agents cannot reliably answer:

- What is the primary logo on a dark background, and what is the minimum size?
- Which HEX values are canonical primary vs accent, and which pairings are forbidden?
- What voice rules apply to a support email vs a launch post?
- Which asset file is approved, and who signed off?

OBIF turns those questions into first-class, dated, evidence-backed objects with fail-closed validators where rules are hard.

---

## Design commitments

1. **Additive OKF v0.2 profile** — every document remains a valid OKF document. Trust tiers, provenance, and `log.md` come for free.
2. **Identity-first, not PDF-first** — structured identity data is the semantic authority. Brand books and style PDFs are projections or exports.
3. **Visual + verbal together** — logo, color, and type are not separated from voice and messaging. A brand Prim holds both.
4. **Assets are referenced, not only described** — logo and font files live in the pack (or are content-addressed) with hashes and approval provenance.
5. **Rules are explicit** — clear space, minimum size, forbidden pairings, misuse examples, and tone constraints are structured enough for agents to check, not only humans to skim.
6. **No fixed UX** — a brand-standards viewer is generated on demand from the Prim (Prim category rule). The format does not ship a canonical GUI.
7. **Interoperable hooks** — color and type should be exportable toward design tokens (e.g. W3C DTCG-style) without making tokens the only representation.
8. **Public repo owns only the protocol** — real packs with live brand IP stay private or org-controlled.

---

## What OBIF is not

- Not a replacement for design tools (Figma, etc.)
- Not a mandatory replacement for every marketing asset pipeline
- Not a full design-system component library (buttons, grids) — those may reference OBIF tokens
- Not a CMS or DAM product
- Not a claim that every organization must publish its brand Prim publicly

---

## Success criteria

An agent that has never seen the brand before can:

1. Load an OBIF pack
2. Validate it
3. Answer “what is the primary mark, palette, type role, and voice rule for context X?”
4. Resolve the approved asset file for a given logo variant
5. Support generation of a brand-standards view (logo board, color, type, voice) that a human brand owner would recognize as consistent with the Prim

If those five hold, the format has succeeded.

---

## Relationship to Prim

OBIF packs are Prims. Everyday language:

> “Send me the brand prim.”

Profile name **OBIF** stays for technical and agent contexts.
