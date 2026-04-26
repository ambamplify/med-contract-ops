# MedContractIntel — Brand Color Palette

**Ratified:** 2026-04-22 by owner (v1 green + gold + trust-blue).
**Revised:** 2026-04-23 by owner — remove all blue; site is **dark green + dark gold + teal accents**.
**Revised:** 2026-04-23 PM — v3: collapsed two-tier green to single near-black forest primary; bronzed gold; vivid teal.
**Revised:** 2026-04-24 PM — v3.1 (current): owner directive — "I wanted the banner changed to the logo green. We need a darker primary green." Primary darkened from `#0a2d20` to `#061e15` to match the logo's dominant pixel.

---

## Palette (authoritative — v3.1)

| Role | Hex | RGB | Usage |
|---|---|---|---|
| **Primary — Near-Black Forest** | `#061e15` | 6, 30, 21 | All primary chrome: nav, hero bg, H1/H2, primary CTAs, brand mark interior, dark cards, footer. |
| **Primary-Dark** | `#02110a` | 2, 17, 10 | Deepest tier — hover on dark backgrounds, deepest trust moments. |
| **Primary-Mid (hero center-lift)** | `#0a2f1f` | 10, 47, 31 | Radial gradient highlight in hero only — never a flat fill. |
| **Secondary — Bronzed Heritage Gold** | `#9c7e2e` | 156, 126, 46 | Main gold: brand accents, primary CTA fill, section headers, pull-quotes, logo ring. Less yellow, more metallic. |
| **Gold-Bright** | `#b89a3e` | 184, 154, 62 | Display-only accent — large headers, hero eyebrow text, pull-quote openers. Never body. |
| **Gold-Dark / Hover** | `#6e5a20` | 110, 90, 32 | Gold CTA hover / pressed states. |
| **Teal Accent** | `#1db5b5` | 29, 181, 181 | Decorative teal: checkmarks, divider accents, data-viz highlights, accent on dark backgrounds. Vivid by design. |
| **Teal-Dark (a11y CTA)** | `#189696` | 24, 150, 150 | Teal CTAs on white/cream — passes WCAG 1.4.11 3:1. Use this for any teal-on-white interactive element. |
| **Teal-Light** | `#2dd4bf` | 45, 212, 191 | Subtle accents on dark backgrounds only. |
| **Warm Cream** | `#f7f4ec` | 247, 244, 236 | Body background — warm, not sterile. |
| **Ink** | `#0a1f14` | 10, 31, 20 | Primary body text (green-shifted near-black). |
| **Muted** | `#5a6b60` | 90, 107, 96 | Secondary text. |
| **List Divider** | `#efe9d8` | 239, 233, 216 | Hairline rules between checklist items, table rows. |

## Contrast rules (WCAG AA)

Audited 2026-04-24 against v3.1 primary `#061e15`:

| Pair | Ratio | AA-normal | AA-large | Use |
|---|---|---|---|---|
| White on primary `#061e15` | 15.83:1 | PASS AAA | PASS AAA | Header text, button labels, hero copy |
| Cream `#f7f4ec` on primary | 13.76:1 | PASS AAA | PASS AAA | Body copy on dark backgrounds |
| White on primary-dark `#02110a` | 19.21:1 | PASS AAA | PASS AAA | Deepest tier |
| Gold `#9c7e2e` on primary `#061e15` | 4.52:1 | PASS | PASS | Eyebrow text, pull-quotes, badges |
| Gold-bright `#b89a3e` on primary | 5.92:1 | PASS | PASS | Display headers on dark |
| Primary `#061e15` on gold `#9c7e2e` | 4.52:1 | PASS | PASS | Gold CTA with primary text |
| White on gold `#9c7e2e` | 3.50:1 | LARGE-ONLY | PASS | Gold CTA labels — use ≥18px bold or use primary text |
| White on teal-dark `#189696` | 3.59:1 | LARGE-ONLY | PASS | Teal CTA on white — use ≥18px bold or icon-only ≥3:1 |
| White on teal `#1db5b5` | 2.52:1 | FAIL | FAIL | NEVER use teal `#1db5b5` for interactive surfaces with white content. Decorative on dark only. |
| Ink `#0a1f14` on cream | 15.6:1 | PASS AAA | PASS AAA | Body text |
| Muted `#5a6b60` on cream | 5.20:1 | PASS | PASS | Secondary text |
| Primary `#061e15` on cream | 14.34:1 | PASS AAA | PASS AAA | Headings on light backgrounds |

### Hard rules
1. **No blue hex values anywhere.** If a hex starts with a blue-dominant channel pattern (e.g. `#0f..75`, `#2b..c9`), it's a bug.
2. Gold is NEVER body text.
3. Gold is NEVER small UI (buttons <24px tall, form labels, table cells).
4. **Teal `#1db5b5` is decorative-only.** Any teal interactive element (button, link, icon-button) must use teal-dark `#189696` to clear WCAG 1.4.11.
5. Severity bands below are universal — do NOT substitute brand tokens.

---

## Severity bands (universal — unchanged)
- Red / critical / high: `#dc3545` border, `#fef2f2` bg
- Yellow / moderate: `#ffc107` border, `#fffbeb` bg
- Green / low / favorable: `#28a745` border, `#f0fdf4` bg

Severity-green differs from brand primary-green intentionally — severity greens are universal "safe/favorable" signals, not brand identity.

---

## Typography

- **Display / H1–H2:** system-ui (`-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto`), 800 weight
- **Body:** same stack, 400/500 weight, line-height 1.6
- **Mono / data callouts:** SF Mono / Menlo / monospace
- **PDF substitute (when system-ui isn't available):** Inter (Google Fonts) for body + display, JetBrains Mono for code/data

---

## PDF / print design guidance

- **Page background:** cream `#f7f4ec`
- **Cover / section dividers / footer band:** primary `#061e15`
- **Body text:** ink `#0a1f14` on cream (15.6:1)
- **Headings on cream:** primary `#061e15`
- **Headings on dark:** gold `#9c7e2e` or white
- **Pull quotes / callouts:** gold `#9c7e2e` background with primary `#061e15` text (passes AA)
- **Checkmarks / data callouts:** teal `#1db5b5` for the mark, ink for the text
- **Hairline dividers:** `#efe9d8`
- **Tables:** cream bg, primary `#061e15` header row with cream text, ink body text, `#efe9d8` row dividers

---

## Migration history

### v2 → v3 (2026-04-23 PM)
| v2 | v3 | Role |
|---|---|---|
| `#0f3d2e` | `#0a2d20` | Primary — collapsed two-tier green to single forest |
| `#1f6e43` | `#0a2d20` | Primary-mid → folded into single primary |
| `#0a2d20` | `#051a12` | Primary-dark |
| `#b8973b` | `#9c7e2e` | Gold — bronzed (less yellow) |
| `#c9a84c` | `#b89a3e` | Gold-bright |
| `#8f7020` | `#6e5a20` | Gold-dark / hover |
| `#1a9090` | `#1db5b5` | Teal — vivid |
| `#25b0a3` | `#2dd4bf` | Teal-light |
| `#faf7f0` | `#f7f4ec` | Cream — warmer, slightly darker |

### v3 → v3.1 (2026-04-24 PM)
| v3 | v3.1 | Role |
|---|---|---|
| `#0a2d20` | `#061e15` | Primary — darkened to match logo dominant |
| `#051a12` | `#02110a` | Primary-dark |
| `#153d2d` | `#0a2f1f` | Hero center-lift (radial gradient highlight) |
| `rgba(10,45,32, …)` | `rgba(6,30,21, …)` | RGBA primary references |

Applied via sed across 23 files. Logos re-recolored from `.v1.bak` originals with `recolor_logo.py` TARGET=DARK=`#061e15`.

---

## Rationale

- **Near-black forest primary (`#061e15`)** — Owner directive: banner must match the green of the logo, and the logo green must be the deeper one. Pulls the brand toward "private banking / heritage law firm" rather than "wellness startup." Cleveland Clinic, JPMorgan, Whole Foods all use deep-green primaries; ours sits at the darker end of that range.
- **Bronzed heritage gold (`#9c7e2e`)** — Less yellow, more metallic. Pairs with near-black green to read "established / authoritative" rather than "trophy / flashy". Bright variant (`#b89a3e`) reserved for display-only.
- **Teal accent (not blue)** — Owner removed blue per v2 directive. Teal retains the clinical-authority signal without being blue and appears in the brand-mark EKG trace. Vivid `#1db5b5` is decorative; interactive teal uses `#189696` for WCAG compliance.
- **Warm cream background** — Softens the very dark primary without sacrificing professional feel.

---

## Where the palette is enforced

- `med-contract-site/tailwind.config.js` — `colors.brand.*`, `gold.*`, `teal.*` extend
- `med-contract-site/client/src/index.css` — body bg, ink, severity bands, scrollbar
- `med-contract-site/public/**/*.html` — inline styles on all pages
- `med-contract-site/server/email-service.ts` — transactional email chrome
- `med-contract-site/server/stripe-webhook.ts` + `server/routes.ts` — server-rendered fragments
- `med-contract-site/make_og_image.py` + `make_thumbnail.py` — social share images
- `med-contract-site/recolor_logo.py` — TARGET=DARK=`#061e15` for logo recolor
- `med-contract-site/public/images/brand-mark-approved.jpg` + `brand-icon.png` + `public/assets/images/brand_symbol.png` + `brand_mark.png` — logo files (navy interior recolored to `#061e15`)

If any file uses a hex not in this palette, it's a bug. Update here first, then code.
