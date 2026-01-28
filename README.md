# brand-assets

This repository contains **canonical brand assets** (logos only) used by multiple digital products.

It is designed to work together with:
- the Brand Identity PDF (visual source)
- the `brand-identity.md` file (AI / Cursor single source of truth)

This repo provides **stable, deterministic URLs** to vector assets, so that:
- humans
- design systems
- AI tools (Cursor / LLMs)

can reference the **exact same source** without ambiguity.

---

## What this repo is for

- Store **official logo files** for each product
- Provide a **single canonical URL** for each logo
- Ensure logos are:
  - not reinterpreted
  - not recolored
  - not regenerated
  - not resized arbitrarily

This repo is **read-only by design intent** for consumers.

---

## What this repo is NOT for

- ❌ No UI components
- ❌ No design tokens
- ❌ No Tailwind config
- ❌ No color extraction from logos
- ❌ No auto-generated assets

Logos are **authoritative assets**, not inputs for token generation.

---

## Folder structure
brands/
└── <brand-name>/
└── logo/
└── logo-primary.svg


Example:
brands/
├── carcare/
│ └── logo/
│ └── logo-primary.svg
└── anamneasy/
└── logo/
└── logo-primary-anamneasy.svg

---

## Logo rules (important)

- Preferred format: **SVG**
- PNG allowed **only as fallback**
- Logos MUST:
  - preserve aspect ratio
  - not be recolored
  - not be stretched or cropped
- Logo colors are **informational only**
  - they MUST NOT be used to generate color tokens

All usage rules are defined in the Brand Identity Markdown.

---

## Canonical URLs

Each logo must be referenced using its **raw GitHub URL**.

Example:
https://raw.githubusercontent.com/
<ORG>/brand-assets/main/brands/<brand>/logo/<file>.svg


These URLs are intended to be used in:
- Brand Identity PDFs
- `brand-identity.md`
- Cursor prompts
- Documentation

---

## How this works with Cursor / AI

1. The Brand Identity PDF describes **how the logo should be used**
2. The `brand-identity.md` file defines **strict logo rules**
3. This repo provides the **actual vector source**

The AI:
- MUST NOT recreate the logo
- MUST NOT infer colors from it
- MUST ONLY reference the provided URL

If no valid logo URL is provided, the AI must STOP and ask for one.

---

## Adding a new brand

1. Create a new folder under `brands/`
2. Add the primary logo as SVG
3. Commit to `main`
4. Use the raw GitHub URL in:
   - the Brand Identity PDF
   - the `brand-identity.md` file

That’s it.

---

## Ownership

This repo is shared across projects.
Changes should be minimal, explicit, and intentional.


