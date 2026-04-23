# MedContractIntel — Brand Color Palette

**Ratified:** 2026-04-22 by owner.
**Directive:** "the colors for medcontract intel should be green and gold, with an accent color that increases trust."

---

## Palette (authoritative)

| Role | Hex | RGB | Usage |
|---|---|---|---|
| **Primary — Medical Green** | `#1f6e43` | 31, 110, 67 | Headers, primary CTAs, brand mark, page chrome (replaces EMCI navy). |
| **Primary-Dark** | `#154d2f` | 21, 77, 47 | Hover states on green buttons, deep text on cream bg. |
| **Secondary — Insight Gold** | `#c9a84c` | 201, 168, 76 | Premium accents, section headers, pull-quotes, section nav scrollbar. (Shared token with EMCI — signals product family.) |
| **Gold-Dark** | `#a58838` | 165, 136, 56 | Gold hover / pressed states. |
| **Trust Accent — Clinical Blue** | `#0f4c75` | 15, 76, 117 | Authority moments: credentials, guarantee seals, testimonial attributions. Deep blue = strongest trust signal in medical contexts. (Replaces EMCI teal.) |
| **Trust-Blue-Light** | `#2b8ac9` | 43, 138, 201 | Interactive trust-blue (links, hovers, icon highlights). (Replaces EMCI teal-light `#2ec4b6`.) |
| **Warm Cream** | `#faf7f0` | 250, 247, 240 | Body background — warm, not sterile. Replaces `#f8f9fa`. |
| **Ink** | `#0a1f14` | 10, 31, 20 | Primary body text (green-shifted near-black for harmony with primary). |
| **Muted** | `#5a6b60` | 90, 107, 96 | Secondary text. |

## Contrast rules (WCAG AA enforcement)

Audited 2026-04-22:

| Pair | Ratio | AA-normal | Use |
|---|---|---|---|
| White on primary-green `#1f6e43` | 6.23:1 | PASS | Header text, button labels |
| White on primary-dark `#154d2f` | 9.84:1 | PASS | Hover states |
| White on trust-blue `#0f4c75` | 9.09:1 | PASS | Trust-block labels, CTAs |
| Ink on cream | 16.10:1 | PASS | Body text (primary pairing) |
| Muted on cream | 5.30:1 | PASS | Secondary text |
| Trust-light on cream | 3.52:1 | **LARGE-ONLY** | Links ≥18px bold / ≥24px regular ONLY. Small links must use trust-DEFAULT. |
| **Gold on primary-green** | 2.73:1 | **FAIL for body** | Gold badges / large accents on green headers only. Never body. |
| **Gold on cream** | 2.14:1 | **FAIL for body** | Gold on cream ONLY for large display (≥24px). Never body text or small UI. |

### Hard rules
1. Gold is NEVER body text.
2. Gold is NEVER small UI (buttons <24px tall, form labels, table cells).
3. Small links on cream backgrounds use trust-DEFAULT `#0f4c75` (contrast 8.74:1). Trust-light `#2b8ac9` is for hover/large display only.
4. Severity bands below are universal — do NOT substitute brand tokens.

---

## Severity bands (universal — unchanged)
- Red / critical / high: `#dc3545` border, `#fef2f2` bg
- Yellow / moderate: `#ffc107` border, `#fffbeb` bg
- Green / low / favorable: `#28a745` border, `#f0fdf4` bg

Severity-green differs from brand-primary-green intentionally — severity greens are universal "safe/favorable" signals, not brand identity.

---

## Migration map from EMCI-inherited colors

Applied 2026-04-22 via sed batch across `med-contract-site/`.

| Old (EMCI-inherited) | New (MedCI) | Notes |
|---|---|---|
| `#0f1e3d` | `#1f6e43` | Navy header → medical green header |
| `#1a2744` | `#1f6e43` | Navy alt → medical green |
| `#1a6b6b` | `#0f4c75` | Teal → trust blue |
| `#2ec4b6` | `#2b8ac9` | Teal-light → trust-blue-light |
| `#c9a84c` | `#c9a84c` | Gold KEPT (sibling-product signal) |
| `#f8f9fa` | `#faf7f0` | Cool off-white → warm cream |
| `#1a1a2e` | `#0a1f14` | Ink adjusted to green-shifted |

## Rationale

- **Green primary** — MedCI is a sibling to EMCI but targeting a different physician audience. Green primary (vs EMCI navy primary) creates immediate visual differentiation while gold stays as the shared "premium insight" marker.
- **Gold retained** — Two products with matching gold = "family of tools for contract professionals." Reinforces trust through recognition.
- **Deep clinical blue (not teal)** — User directive was "an accent color that increases trust." Deep blue is the universal medical trust color (Mayo, Cleveland Clinic, major insurers). Teal reads "startup wellness brand" — wrong tone for a contract-negotiation product targeting internists + hospitalists.
- **Warm cream bg** — Clinical/professional design often feels sterile. Warm cream softens without compromising authority. Matches "I'm on your side, doctor" brand voice.

---

## Where the palette is enforced

- `med-contract-site/tailwind.config.js` — `colors.brand.*` extend
- `med-contract-site/client/src/index.css` — body bg, ink, severity bands, scrollbar
- `med-contract-site/public/**/*.html` — inline styles on legal pages, product pages, analyzer, checklist, calculator, thank-you flows
- `med-contract-site/server/email-service.ts` — transactional email chrome
- `med-contract-site/server/pdf-report.ts` + `letter-docx.ts` — branded PDF/DOCX exports
- `med-contract-site/make_og_image.py` + `make_thumbnail.py` — social share images

If any file uses a hex not in this palette, it's a bug. Update here first, then code.
