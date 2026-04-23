# Legal Pages — Drop-In Staging

5 HTML files ready to `cp` into `med-contract-site/public/` during the Day 2 site scaffold step.

## Files

| Source (this dir) | Destination on med-contract-site |
|---|---|
| `privacy.html` | `public/pages/privacy.html` |
| `terms.html` | `public/pages/terms.html` |
| `disclaimer.html` | `public/pages/disclaimer.html` |
| `dmca.html` | `public/pages/dmca.html` |
| `refund/index.html` | `public/refund/index.html` |

## Day 2 drop-in command (paste into shell after fork + find-replace)

```bash
SITE=/Users/ambamplify/MedContractIntel/med-contract-site
SRC=/Users/ambamplify/MedContractIntel/med-contract-ops/INBOX/legal-pages

mkdir -p "$SITE/public/pages" "$SITE/public/refund"
cp "$SRC/privacy.html"     "$SITE/public/pages/privacy.html"
cp "$SRC/terms.html"       "$SITE/public/pages/terms.html"
cp "$SRC/disclaimer.html"  "$SITE/public/pages/disclaimer.html"
cp "$SRC/dmca.html"        "$SITE/public/pages/dmca.html"
cp "$SRC/refund/index.html" "$SITE/public/refund/index.html"
```

## Open items before Day 5 launch

- **Refund page nav/footer styles**: the `refund/index.html` uses class names from the EMCI design system (`.nav-banner-inner`, `.page-hero`, `.policy-box`, etc.). Those class definitions ship with the site CSS in Day 2 fork. Verify all classes resolve in `dist/` after first build.
- **Footer on every other page**: privacy/terms/disclaimer/dmca are standalone minimalist pages (no nav/footer) — they inherit root `/` trust via the `← MedContractIntel` back link. EMCI ships them the same way. If you want consistent footer on all legal pages, port the `refund/index.html` nav+footer block to the four minimalist pages during Day 2.
- **NJ DBA**: footer currently shows `© 2026 MedContractIntel™`. If owner completes the NJ DBA filing before launch, swap footer copy to `© 2026 AEBMD LLC dba MedContractIntel, New Jersey`.
- **dmca@medcontractintel.com alias**: depends on Google Workspace secondary domain (owner ESCALATED #1). If not live by Day 5, temporarily point dmca@ → service@ in the Workspace admin.
- **Last-updated date**: all pages say "April 27, 2026" (launch day). If launch slips, owner updates the date on Day 4 final pass.

## Source of truth

Full rationale + adaptation rules are in the parent `../legal-pages-draft.md`. These files are the machine-readable split of that draft.

Drafted: 2026-04-22 late evening EDT
Split: 2026-04-22 late evening EDT (Day 0 autonomous push)
Review status: **draft** — Day 4 ~ 4:00 PM EDT owner/lawyer/Claude-chat-opus review checkpoint before Day 5 launch.
