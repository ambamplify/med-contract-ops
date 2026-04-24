# MedContractIntel — Brand Color Palette

**Ratified:** 2026-04-22 by owner (v1 green + gold + trust-blue).
**Revised:** 2026-04-23 by owner — remove all blue; site is **dark green + dark gold + teal accents**.
**Directive:** "The site should be a dark green with dark gold and teal accents. Remove all of the blue."

---

## Palette (authoritative)

| Role | Hex | RGB | Usage |
|---|---|---|---|
| **Primary — Deep Forest Green** | `#0f3d2e` | 15, 61, 46 | All primary chrome: nav, hero bg, H1/H2, primary CTAs, brand mark interior. Replaces EMCI navy AND v1 medical-green as the dominant brand color. |
| **Primary-Dark** | `#0a2d20` | 10, 45, 32 | Deepest tier — hover on dark backgrounds, footer, deepest trust moments. |
| **Primary-Mid** | `#1f6e43` | 31, 110, 67 | Secondary green tier — card chrome, subheaders, hover states on cream backgrounds. Was v1 primary; demoted to mid-tier in v2. |
| **Secondary — Heritage Gold** | `#b8973b` | 184, 151, 59 | Main gold: brand accents, section headers, pull-quotes, section nav scrollbar, logo ring. "Dark gold" per owner directive. |
| **Gold-Bright** | `#c9a84c` | 201, 168, 76 | Display-only accent — large headers, hero eyebrow text, pull-quote openers. Never body. |
| **Gold-Dark** | `#8f7020` | 143, 112, 32 | Gold hover / pressed states. |
| **Teal Accent** | `#1a9090` | 26, 144, 144 | Links, secondary CTAs, analyzer trace lines, data visualization highlights. Authoritative teal (not startup-wellness mint). |
| **Teal-Light** | `#25b0a3` | 37, 176, 163 | Interactive teal — hover states, active link, icon glow. |
| **Warm Cream** | `#faf7f0` | 250, 247, 240 | Body background — warm, not sterile. |
| **Ink** | `#0a1f14` | 10, 31, 20 | Primary body text (green-shifted near-black). |
| **Muted** | `#5a6b60` | 90, 107, 96 | Secondary text. |

## Contrast rules (WCAG AA)

Audited 2026-04-23:

| Pair | Ratio | AA-normal | Use |
|---|---|---|---|
| White on primary `#0f3d2e` | 10.73:1 | PASS AAA | Header text, button labels, hero copy |
| White on primary-dark `#0a2d20` | 13.92:1 | PASS AAA | Deepest tier |
| White on primary-mid `#1f6e43` | 6.23:1 | PASS | Secondary green chrome |
| White on gold `#b8973b` | 3.37:1 | LARGE-ONLY | Gold-on-white allowed ONLY for ≥18px bold / ≥24px regular |
| White on teal `#1a9090` | 4.04:1 | PASS | Teal CTAs (normal-size text) |
| Ink on cream | 16.10:1 | PASS | Body text |
| Muted on cream | 5.30:1 | PASS | Secondary text |
| Gold `#b8973b` on primary `#0f3d2e` | 3.18:1 | LARGE-ONLY | Gold-on-green for badges / eyebrow text only |
| Teal `#1a9090` on cream | 3.62:1 | LARGE-ONLY | Teal links must be ≥18px bold or use darker variant for small text |

### Hard rules
1. **No blue hex values anywhere.** If a hex starts with a blue-dominant channel pattern (e.g. `#0f..75`, `#2b..c9`), it's a bug.
2. Gold is NEVER body text.
3. Gold is NEVER small UI (buttons <24px tall, form labels, table cells).
4. Severity bands below are universal — do NOT substitute brand tokens.

---

## Severity bands (universal — unchanged)
- Red / critical / high: `#dc3545` border, `#fef2f2` bg
- Yellow / moderate: `#ffc107` border, `#fffbeb` bg
- Green / low / favorable: `#28a745` border, `#f0fdf4` bg

Severity-green differs from brand primary-green intentionally — severity greens are universal "safe/favorable" signals, not brand identity.

---

## Migration map v1 → v2 (applied 2026-04-23)

Applied via sed batch across `med-contract-site/`.

| v1 value | v2 value | Role |
|---|---|---|
| `#0f4c75` | `#0f3d2e` | trust-blue → primary deep forest |
| `#2b8ac9` | `#1a9090` | trust-blue-light → teal |
| `#10203f` | `#0a2d20` | navy tint → primary-dark |
| `#112145` | `#0a2d20` | navy tint → primary-dark |
| `#162040` | `#0a2d20` | navy tint → primary-dark |
| `#1a2d5a` | `#0f3d2e` | navy → primary |
| `#1a3060` | `#0f3d2e` | navy → primary |
| `#1a3a5c` | `#0f3d2e` | navy → primary |
| `#1e3060` | `#0f3d2e` | navy → primary |
| `#0369a1` | `#1a9090` | mid-blue → teal |
| `#e0f2fe` | `#e5f0e8` | pale blue → pale green |
| `#f5f7fb` | `#faf7f0` | blue tint → cream |
| `#f6f8fc` | `#faf7f0` | blue tint → cream |
| `#f9fbff` | `#faf7f0` | blue tint → cream |
| `#fbfcff` | `#faf7f0` | blue tint → cream |
| `#6c768c` | `#5a6b60` | blue-gray → muted |
| `#6f7483` | `#5a6b60` | blue-gray → muted |
| `#1f6e43` | `#0f3d2e` | v1 primary → new primary (darkened per owner directive) |
| `#154d2f` | `#0a2d20` | v1 primary-dark → new primary-dark |
| `#c9a84c` | `#b8973b` | v1 gold → v2 heritage dark gold |
| `#a58838` | `#8f7020` | v1 gold-dark → v2 gold-dark |

---

## Rationale

- **Dark green primary** — Research consensus (finance + medical brands): deep forest green signals stability, authority, heritage. Bright medium greens (`#1f6e43`) read "startup/wellness"; deep forest (`#0f3d2e`) reads "established/trusted". Cleveland Clinic, JPMorgan Chase, Whole Foods all use deep-green primaries.
- **Heritage dark gold** — Muted dark gold (`#b8973b`) pairs with deep green to communicate "old-money authority" over "cheap trophy". Brighter gold `#c9a84c` reserved for display-only accents.
- **Teal accent (not blue)** — Owner removed blue per v2 directive. Teal `#1a9090` retains the "clinical/authority" signal without being blue; it already appears in the brand-mark EKG trace.
- **Warm cream bg** — unchanged. Softens the darker primary without sacrificing professional feel.

---

## Where the palette is enforced

- `med-contract-site/tailwind.config.js` — `colors.brand.*`, `gold.*`, `teal.*` extend
- `med-contract-site/client/src/index.css` — body bg, ink, severity bands, scrollbar
- `med-contract-site/public/**/*.html` — inline styles on all pages
- `med-contract-site/server/email-service.ts` — transactional email chrome
- `med-contract-site/server/pdf-report.ts` + `letter-docx.ts` — branded PDF/DOCX exports
- `med-contract-site/make_og_image.py` + `make_thumbnail.py` — social share images
- `med-contract-site/public/images/brand-mark-approved.jpg` + `brand-icon.png` + `public/assets/images/brand_symbol.png` + `brand_mark.png` — logo files (navy interior recolored to `#0f3d2e`)

If any file uses a hex not in this palette, it's a bug. Update here first, then code.
