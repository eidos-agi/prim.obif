# OBIF v0.1.0-draft — Open Brand and Identity Format

**An additive profile of OKF v0.2.**  
Every OBIF document preserves OKF provenance and trust.  
OKF renderers may ignore OBIF fields and still display the documents.

**Product intention (load-bearing):** see [INTENTION.md](INTENTION.md).

In one line: OBIF packages brand foundations, logo system, color, typography, imagery, voice, assets, and governance as a self-contained, evidence-backed, agent-validatable Prim.

```
OKF  — knowledge and trust
…
OCSF — corporate structure & capital
OBIF — brand & identity   (this profile)
Prim — category name for OKF-family packs
```

OBIF composes with these formats; it does not merge them.  
Corporate ownership stays OCSF. Product surfaces stay OPF. Research stays ORF. OBIF owns identity expression and brand rules.

---

## 1. Pack

```
obif-pack/
  index.md              # required face (type: brand)
  log.md                # append-only timeline
  identity.json         # canonical structured identity — semantic authority
  foundations/          # optional human-readable projections
  logo/
  color/
  type/
  imagery/
  voice/
  assets/               # binary assets (SVG, font files, etc.)
  evidence/             # approvals, decision records, source PDFs
  docs.json             # optional presentation settings for renderers
```

`identity.json` (or equivalent declared in the face) is the **semantic authority** for structured brand claims.  
Markdown projections and folder names do not override it.

Minimal face frontmatter (`index.md`):

```yaml
okf_version: "0.2"
obif_version: "0.1.0"
profile: obif
type: brand
title: Example Brand
status: active
```

Interchange forms follow the Prim packaging rules: directory pack canonical; `.prim.zip` / `.prim` / `.prim.tar.gz` for sharing.

---

## 2. Core kinds (nodes)

| Kind | Purpose |
|------|---------|
| `brand` | The identity being defined (may be master, sub-brand, or product brand) |
| `logo_variant` | Primary, secondary, icon, wordmark, lockup, mono, reverse, etc. |
| `color_token` | Named color with role and values |
| `type_role` | Display, body, UI, mono, etc., with family and hierarchy rules |
| `typeface` | Font family reference + licensing / file pointer |
| `imagery_rule` | Photography, illustration, or iconography direction |
| `voice_rule` | Voice attribute or contextual tone constraint |
| `message_pillar` | Core message or narrative pillar |
| `asset` | File asset with path/URL and content hash |
| `usage_rule` | Clear space, min size, pairing, co-brand, forbidden use |
| `approval` | Governance act (who approved what, when) |

Every entity has a stable `id`, `type`, lifecycle `status`, and `provenance` where material.

---

## 3. Domains inside identity.json (draft shape)

### 3.1 Foundations

- Legal / display names
- Positioning statement / promise (short)
- Personality traits (structured list, not only adjectives in prose)
- Relationship to parent brand or house (if any)

### 3.2 Logo system

- Variants with roles (`primary`, `icon`, `wordmark`, …)
- Color modes (`full`, `mono`, `reverse`)
- Clear space (expressible as ratio or absolute)
- Minimum size per medium class (digital / print / signage)
- Misuse rules (structured list: no stretch, no recolor, no shadow, …)
- Links to `asset` records

### 3.3 Color system

- Tokens with roles: `primary`, `secondary`, `neutral`, `accent`, `semantic` (success/warn/error optional)
- Values: at least HEX for digital; RGB/CMYK/Pantone as applicable
- Constraints: forbidden backgrounds, never-pair rules, accent-only flags
- Accessibility notes (contrast targets) where claimed

### 3.4 Typography system

- Roles: display, body, UI, caption, mono, …
- Families + weights used per role
- Hierarchy (scale / relative size guidance)
- Fallbacks
- Links to licensed font assets when distributed in-pack

### 3.5 Imagery & iconography

- Direction (do / don’t, subject, lighting, treatment)
- Icon style rules
- Optional references to example assets

### 3.6 Voice & verbal

- Voice attributes (operational, not only three adjectives)
- Tone by context (e.g. support, social, legal, launch)
- Messaging pillars
- Explicit do-say / don’t-say pairs where available

### 3.7 Governance

- Approval records for material changes
- Co-branding / partner lockup rules
- Supersedes links for retired variants

Exact JSON schema will harden with the validator. This section defines required *domains*, not a frozen schema.

---

## 4. Validation gates (draft — fail-closed where marked)

| Rule | Level |
|------|--------|
| `okf_version: "0.2"` + `profile: obif` + valid `obif_version` | error |
| Face `type: brand` (or declared brand face) present | error |
| At least one `logo_variant` with an `asset` reference when logo claims are made | error |
| Color tokens used as primary must include HEX (or equivalent digital value) | error |
| Material logo/color/type claims require provenance; asset files SHOULD have content hashes | error / warn |
| Superseded variants must not be marked `status: active` without justification | error |
| Secret-shaped strings (private keys, live credentials) | error |
| Agent-only approval of final brand lock without human tier | warn / error under `--strict` |

Additional gates (contrast math, clear-space completeness) will be added as the format hardens.

---

## 5. Evidence & trust

Material brand claims (approved primary mark, locked palette, voice rules in force) carry:

```yaml
provenance:
  by: human:... | agent:... | job:...
  method: "brand committee 2026-08-01" | "design lock"
  at: "2026-08-01"
verified:
  by: human:...
  at: ...
evidence:
  - path: evidence/approval-2026-08-01.pdf
    content_hash: sha256:...
```

Trust ladder follows OKF v0.2: `human:` > `job:` > `agent:`.

---

## 6. Brand standards viewer (projection)

OBIF does **not** define a fixed application UI.

A **brand standards viewer** is any renderer that:

1. Reads a valid OBIF pack
2. Projects logo boards, color chips, type specimens, voice cards, and do/don’t galleries
3. Leaves the Prim as the source of truth

PDF brand books, Figma libraries, and web style pages are exports or parallel tools. They must not silently become a second source of truth without updating the Prim.

This matches the Prim category rule: no fixed UX; interfaces generated on demand.

---

## 7. Interoperability

- Export color/type subsets toward design-token formats (e.g. W3C DTCG-style JSON) as a projection
- Reference web-safe asset URLs when packs are published; prefer in-pack assets + hashes for offline/agent use
- Compose with OCSF when legal entity and brand house must be linked; do not merge ownership into OBIF
- Compose with OPF when product surfaces need brand application rules

---

## 8. Status

**v0.1.0-draft.**  
INTENTION and this SPEC skeleton exist.  
Validator, JSON schema, and a richer example pack are next.

---

## License

MIT — Eidos AGI
