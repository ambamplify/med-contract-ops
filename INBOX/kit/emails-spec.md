# Kit (ConvertKit) Email Sequence Drop-Ins — Day 3 Kit Setup

**Drafted:** 2026-04-22 20:48 EDT (Day 0 autonomous push)
**Executes:** Day 3 Friday 2026-04-25 after owner creates Kit account on admin@medcontractintel.com and disables double opt-in (D1-16).
**Review:** Lesson #19 — `site-email-welcome` + `site-email-twoweek` rows in `state/content-review-day3.md`. Perplexity factcheck + Claude-chat-opus voice pass before these automations fire.

---

## 0. Kit account setup (owner, Day 3 AM)

Before any of this copy ships:
1. Sign up at kit.com with `admin@medcontractintel.com` (depends on D1-7 alias creation + D1-16).
2. **Disable double opt-in** — Settings → Account → Communication Preferences → turn OFF double opt-in. Critical; Lesson #X from EMCI.
3. Verify sending domain: add the DKIM TXT records Kit provides to Cloudflare via signed-in JS POST (same path EMCI used).
4. Create form: "IM/Hospitalist Red Flag Checklist" — single-step opt-in, returns PDF download link immediately.
5. Create tag: `med-checklist-download`, `med-analyzer-purchased`, `med-bundle-purchased`.

---

## 1. Checklist-download welcome email (delivered immediately)

**Subject:** Your IM/Hospitalist Red Flag Checklist — 15 clauses to verify before you sign

**From:** `MedContractIntel <service@medcontractintel.com>`

**Body (HTML):**

```html
<!DOCTYPE html>
<html>
<body style="font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif; color: #1f2937; max-width: 600px; margin: 0 auto; padding: 1.5rem; line-height: 1.7;">

  <div style="background: #0f1e3d; padding: 1.5rem; color: #fff; border-radius: 4px; margin-bottom: 1.5rem;">
    <p style="color:#c9a84c;font-size:0.7rem;font-weight:700;letter-spacing:0.2em;text-transform:uppercase;margin:0 0 0.25rem;">MedContractIntel&trade;</p>
    <h1 style="color:#fff;font-size:22px;margin:0;">Your IM/Hospitalist Red Flag Checklist</h1>
  </div>

  <p>Hi,</p>

  <p>Attached is the <strong>15-clause Red Flag Checklist</strong> for internal medicine and hospitalist employment contracts. These are the clauses we see misconfigured most often in the contracts we analyze.</p>

  <p style="background: #f9fafb; padding: 1rem; border-left: 3px solid #1a9090; margin: 1.5rem 0;">
    <a href="{{checklist_download_url}}" style="color:#1a9090; font-weight:600;">&rarr; Download the checklist (PDF)</a>
  </p>

  <h2 style="color:#0f1e3d;font-size:18px;margin-top:2rem;">What to do with it</h2>
  <p>Before you sign, walk through all 15 items against your contract. Mark anything you can't find or don't understand. Those are your negotiation leverage points.</p>

  <p>The most common misses we see:</p>
  <ul>
    <li><strong>Panel size commitment without pay adjustment</strong> &mdash; MGMA median IM panel is ~1,800 patients; many contracts lock in 2,300+ at the same pay.</li>
    <li><strong>Nocturnist differential below 20%</strong> &mdash; SHM industry standard is ~25%; below 20% is a clear below-market signal for any night-heavy schedule.</li>
    <li><strong>Tail coverage split unclear</strong> &mdash; the clause is worth ~$35K of risk. If the contract is ambiguous on who pays, the physician often ends up paying.</li>
  </ul>

  <h2 style="color:#0f1e3d;font-size:18px;margin-top:2rem;">Next step &mdash; if you want depth</h2>
  <p>The checklist tells you what to look for. Our <strong>AI Contract Analyzer</strong> reads your actual contract and grades every clause against MGMA / AAMC / SHM / AMGA / Doximity benchmarks, then drafts a counter-proposal letter for your top negotiation priorities.</p>

  <p style="margin: 1.5rem 0;">
    <a href="{{analyzer_launch_discount_url}}" style="display:inline-block; background:#1a9090; color:#fff; padding:0.75rem 1.5rem; border-radius:4px; text-decoration:none; font-weight:600;">Try the Contract Analyzer &mdash; launch week, 20% off the bundle</a>
  </p>

  <p>Launch-week promo expires {{launch_promo_expires}}. Use code <strong>MEDCI-LAUNCH-20</strong> at checkout.</p>

  <p>&mdash; MedContractIntel team</p>

  <hr style="border:none; border-top:1px solid #e5e7eb; margin: 2rem 0;">

  <p style="font-size: 0.8rem; color: #9ca3af;">
    MedContractIntel&trade; &middot; <a href="mailto:service@medcontractintel.com" style="color:#1a9090;">service@medcontractintel.com</a><br>
    AEBMD LLC &middot; 2803 Philadelphia Pike, Suite B #1447, Claymont, DE 19703<br>
    Not legal, medical, or financial advice. See <a href="https://medcontractintel.com/pages/disclaimer.html" style="color:#1a9090;">disclaimer</a>.<br>
    <a href="{{unsubscribe_url}}" style="color:#9ca3af;">Unsubscribe</a>
  </p>

</body>
</html>
```

**Plaintext version:** Auto-generate from HTML via Kit's strip-tags feature.

**Merge-tag dependencies:**
- `{{checklist_download_url}}` — uploaded to Cloudflare R2 `medci-social-media` bucket or a dedicated docs bucket; public URL.
- `{{analyzer_launch_discount_url}}` — Stripe Payment Link for `bundle` slug with `coupon=MEDCI-LAUNCH-20` appended (from `INBOX/stripe/products-prices-spec.json` `payment_links[]` index 5).
- `{{launch_promo_expires}}` — Day 12 = "May 7, 2026".
- `{{unsubscribe_url}}` — Kit default.

---

## 2. Two-week analyzer follow-up (delivered 14 days after analysis purchase)

**Trigger:** Kit automation — tagged `med-analyzer-purchased` OR `med-bundle-purchased`. 14-day delay after tag applied.

**Subject:** How did the contract negotiation go?

**From:** `MedContractIntel <service@medcontractintel.com>`

**Body (HTML):**

```html
<!DOCTYPE html>
<html>
<body style="font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif; color: #1f2937; max-width: 600px; margin: 0 auto; padding: 1.5rem; line-height: 1.7;">

  <div style="background: #0f1e3d; padding: 1.5rem; color: #fff; border-radius: 4px; margin-bottom: 1.5rem;">
    <p style="color:#c9a84c;font-size:0.7rem;font-weight:700;letter-spacing:0.2em;text-transform:uppercase;margin:0 0 0.25rem;">MedContractIntel&trade;</p>
    <h1 style="color:#fff;font-size:22px;margin:0;">Two weeks later &mdash; checking in</h1>
  </div>

  <p>Hi,</p>

  <p>Two weeks ago you analyzed your {{employer_type}} contract with MedContractIntel&trade;.</p>

  <p>We're curious:</p>
  <ul>
    <li>Did you send the counter-proposal letter, or modify it first?</li>
    <li>What did the employer come back with?</li>
    <li>Any clauses your attorney flagged that we missed?</li>
  </ul>

  <p>No obligation to reply &mdash; but if you have 2 minutes, we'd love to know how it went. The data from each negotiation makes the next analysis sharper.</p>

  <p style="background: #f9fafb; padding: 1rem; border-left: 3px solid #1a9090; margin: 1.5rem 0;">
    <strong>Quick reply works:</strong> Signed as-is / Got X concessions / Walked away / Still negotiating. One line is enough.
  </p>

  <p>If you're still mid-negotiation and want a second analysis (e.g., counter-offer from employer), reply to this email and we'll give you a free re-analyze within 30 days of your original purchase.</p>

  <p>&mdash; MedContractIntel team</p>

  <hr style="border:none; border-top:1px solid #e5e7eb; margin: 2rem 0;">

  <p style="font-size: 0.8rem; color: #9ca3af;">
    MedContractIntel&trade; &middot; <a href="mailto:service@medcontractintel.com" style="color:#1a9090;">service@medcontractintel.com</a><br>
    <a href="{{unsubscribe_url}}" style="color:#9ca3af;">Unsubscribe</a>
  </p>

</body>
</html>
```

**Merge-tag dependencies:**
- `{{employer_type}}` — from purchase metadata (Stripe customer → Kit subscriber mapping).
- `{{unsubscribe_url}}` — Kit default.

---

## 3. Post-purchase bundle welcome (delivered immediately on bundle purchase)

**Trigger:** Kit automation — tagged `med-bundle-purchased`. 0-minute delay.

**Subject:** Welcome to MedContractIntel — here's how to use everything you just bought

**From:** `MedContractIntel <service@medcontractintel.com>`

**Body (HTML):**

```html
<!DOCTYPE html>
<html>
<body style="font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif; color: #1f2937; max-width: 600px; margin: 0 auto; padding: 1.5rem; line-height: 1.7;">

  <div style="background: #0f1e3d; padding: 1.5rem; color: #fff; border-radius: 4px; margin-bottom: 1.5rem;">
    <p style="color:#c9a84c;font-size:0.7rem;font-weight:700;letter-spacing:0.2em;text-transform:uppercase;margin:0 0 0.25rem;">MedContractIntel&trade;</p>
    <h1 style="color:#fff;font-size:22px;margin:0;">Your bundle is ready</h1>
  </div>

  <p>Thanks for purchasing the full MedContractIntel bundle. Here's what you have and the order we recommend using it:</p>

  <h2 style="color:#0f1e3d;font-size:18px;margin-top:1.5rem;">1. Start: Run the analyzer on your current contract</h2>
  <p><a href="https://medcontractintel.com/analyzer" style="color:#1a9090;font-weight:600;">Launch the analyzer &rarr;</a></p>
  <p>Upload your employment contract PDF. You'll get a benchmark-graded analysis covering RVU multiplier, panel size, nocturnist differential, census, non-compete, tail coverage, and termination &mdash; plus a counter-proposal letter draft.</p>

  <h2 style="color:#0f1e3d;font-size:18px;margin-top:1.5rem;">2. Verify: Red Flag Checklist</h2>
  <p><a href="{{checklist_download_url}}" style="color:#1a9090;">Download the checklist (PDF) &rarr;</a></p>
  <p>Use the 15-clause checklist to spot anything the analyzer might have downweighted based on setting. Belt-and-suspenders.</p>

  <h2 style="color:#0f1e3d;font-size:18px;margin-top:1.5rem;">3. Negotiate: Script Pack</h2>
  <p><a href="{{scripts_download_url}}" style="color:#1a9090;">Download the Negotiation Script Pack (PDF) &rarr;</a></p>
  <p>8 ready-to-use scripts for the most common hospitalist / IM negotiation moments: compensation floor, RVU threshold push, nocturnist premium, tail coverage, non-compete reduction, CME increase, signing bonus clawback, offer timeline.</p>

  <h2 style="color:#0f1e3d;font-size:18px;margin-top:1.5rem;">4. Calculators</h2>
  <p>
    <a href="{{wrvu_calculator_url}}" style="color:#1a9090;">wRVU Compensation Calculator &rarr;</a><br>
    <a href="{{shift_economics_calculator_url}}" style="color:#1a9090;">Shift Economics Analyzer (hospitalist) &rarr;</a>
  </p>
  <p>Model scenarios: what does the offer look like at 4,200 vs. 4,800 wRVU? What's the true $/hr on 7-on/7-off with a 15% nocturnist premium vs. 25%?</p>

  <h2 style="color:#0f1e3d;font-size:18px;margin-top:1.5rem;">Questions</h2>
  <p>Reply to this email. We read and respond within a business day.</p>

  <p>&mdash; MedContractIntel team</p>

  <hr style="border:none; border-top:1px solid #e5e7eb; margin: 2rem 0;">

  <p style="font-size: 0.8rem; color: #9ca3af;">
    MedContractIntel&trade; &middot; <a href="mailto:service@medcontractintel.com" style="color:#1a9090;">service@medcontractintel.com</a><br>
    AEBMD LLC &middot; 2803 Philadelphia Pike, Suite B #1447, Claymont, DE 19703<br>
    Not legal, medical, or financial advice. See <a href="https://medcontractintel.com/pages/disclaimer.html" style="color:#1a9090;">disclaimer</a>.<br>
    <a href="{{unsubscribe_url}}" style="color:#9ca3af;">Unsubscribe</a>
  </p>

</body>
</html>
```

**Merge-tag dependencies:**
- All `*_download_url` / `*_calculator_url` — paths on the live site (Day 2 scaffold will publish to `/downloads/` or use signed URLs). Placeholder values until site is live.

---

## 4. Kit automation wiring (Day 3 afternoon setup steps)

1. **Form: IM/Hospitalist Red Flag Checklist** — single-field (email), tag on submit: `med-checklist-download`. Trigger automation #1.
2. **Automation #1 (Welcome after checklist download):**
   - Trigger: tag `med-checklist-download` added.
   - Action: send Email #1 (checklist welcome) immediately.
3. **Automation #2 (Bundle welcome):**
   - Trigger: tag `med-bundle-purchased` added (via Stripe webhook → Kit API integration).
   - Action: send Email #3 (bundle welcome) immediately.
4. **Automation #3 (2-week follow-up):**
   - Trigger: tag `med-analyzer-purchased` OR `med-bundle-purchased` added.
   - Delay: 14 days.
   - Action: send Email #2 (2-week follow-up).

**Stripe → Kit tagging:** wired via `server/stripe-webhook.ts` (forked from EMCI). On checkout.session.completed, webhook reads product metadata.slug and calls Kit API to tag the subscriber.

---

## 5. Lesson #19 review before automations go live

- `site-email-welcome` row in ledger — covers Email #1 above. Perplexity verifies the 3 data points cited (MGMA panel median ~1,800 / SHM nocturnist ~25% / tail ~$35K) against IM_DATA_2026.md before Gate 1 PASS.
- `site-email-twoweek` row in ledger — covers Email #2 above. Softer review — just voice/compliance. Perplexity confirms no factual claims in the follow-up that require verification.
- Email #3 (bundle welcome) — no separate row; operational copy only. Add row `site-email-bundle-welcome` if reviewer prefers explicit tracking.

Email #3 bundle welcome row is recommended to add to ledger before Day 3 review — adding autonomously now.

---

**Drafted:** 2026-04-22 20:48 EDT
**Executes:** Day 3 Friday 2026-04-25 afternoon after Kit account is created (D1-16 + owner Kit signup)
**Owner dependencies:** Kit account, Kit API key, Stripe webhook → Kit integration, download-asset URLs on site
