# MedContractIntel — Legal Pages Draft v1

**Purpose:** MedCI-branded ports of the five launch-critical legal pages EMCI ships. Drafted Day 0 (2026-04-22 late evening) by Claude Code. Goes into `med-contract-site/public/pages/` and `/public/refund/` once the site scaffolds on Day 2.

**Lesson #19 note:** This copy is **legal/compliance text**, not marketing content, so it sits outside the Day 3 Perplexity + Claude-chat-opus review loop. However, before launch on Day 5, owner should have a lawyer or a Claude chat (opus mode) compliance pass eyeball it — specifically the "Not Medical / Not Legal Advice" disclaimers and the refund terms. Gate 18 in the blueprint applies to content artifacts; this draft falls under owner-review-before-Day-5 as a separate checkpoint.

**Adaptation rules applied:**
- "Emergency Medicine" / "ED" / "EM physician" → "Internal Medicine / Hospitalist" / "IM-Hospitalist" / "hospitalist or IM physician"
- "EM Contract Intel™" → "MedContractIntel™" / "MedCI"
- Domain `emcontractintel.com` → `medcontractintel.com`
- Email `service@emcontractintel.com` → `service@medcontractintel.com`
- Benchmark sources: ACEP → (removed; not IM-relevant). Kept MGMA + CMS. Added AAMC Physician Compensation Survey, SCP (Society of Hospital Medicine / SHM) State of Hospital Medicine Report, Doximity Physician Compensation Report, AMGA Medical Group Compensation & Productivity Survey.
- Operating entity stays **AEBMD LLC** (Delaware). NJ DBA for "MedContractIntel" is owner-in-flight (ESCALATED item #2). Once filed, change attribution line to "AEBMD LLC dba MedContractIntel" in New Jersey footprint. For launch, attribution is **AEBMD LLC** operating the brand **MedContractIntel™**.
- Mailing address: same DE registered agent address as EMCI → `2803 Philadelphia Pike, Suite B #1447, Claymont, DE 19703`. If NJ mailing address is preferred post-DBA, owner swaps in ESCALATED.
- "Last updated" date: **2026-04-27** (launch day; owner confirms on Day 4 final pass).

---

## 1. /pages/privacy.html — Privacy Policy

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Privacy Policy | MedContractIntel™</title>
  <style>
    body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif; color: #1f2937; max-width: 760px; margin: 0 auto; padding: 2rem 1.5rem 4rem; line-height: 1.7; }
    h1 { color: #0f1e3d; font-size: 1.75rem; margin-bottom: 0.25rem; }
    h2 { color: #0f1e3d; font-size: 1.125rem; margin-top: 2rem; margin-bottom: 0.5rem; }
    p, li { font-size: 0.9375rem; color: #374151; }
    a { color: #1a9090; }
    .updated { font-size: 0.85rem; color: #6b7280; margin-bottom: 2rem; }
    .back { display: inline-block; margin-bottom: 2rem; font-size: 0.85rem; color: #6b7280; text-decoration: none; }
    .back:hover { color: #1a9090; }
  </style>
</head>
<body>
  <a href="https://medcontractintel.com" class="back">← MedContractIntel</a>
  <h1>Privacy Policy</h1>
  <p class="updated">Last updated: April 27, 2026</p>

  <p>MedContractIntel™ is operated by AEBMD LLC ("we," "us," or "our"). This Privacy Policy explains how we collect, use, and protect information when you use our website and services at medcontractintel.com.</p>

  <h2>Information We Collect</h2>
  <p>We collect information you provide directly:</p>
  <ul>
    <li><strong>Contract text:</strong> When you submit a hospitalist or internal medicine employment contract for analysis, we receive and process the text you provide. We strongly recommend redacting personal identifying information (name, address, employer-specific identifiers) before submitting.</li>
    <li><strong>Context data:</strong> Employer type (hospital-employed, private group, locums, CMG), state, region, compensation model (salaried, RVU-based, hybrid, nocturnist differential), years of experience, practice setting (community, academic, critical-access, teaching), panel size / census, and APC supervision status — used solely to generate your analysis.</li>
    <li><strong>Email address:</strong> If you subscribe to receive our IM/Hospitalist Red Flag Checklist or communications via our email provider (Kit/ConvertKit).</li>
    <li><strong>Phone number:</strong> Optional field on the analyzer, used only to contact you about your analysis if needed.</li>
    <li><strong>Payment information:</strong> Collected and processed by Stripe. We do not store credit card numbers or payment details on our servers.</li>
  </ul>

  <h2>How We Use Your Information</h2>
  <ul>
    <li>To perform and deliver your contract analysis</li>
    <li>To send you the educational resources you requested</li>
    <li>To improve our analysis accuracy and benchmark data</li>
    <li>To communicate with you about your order or analysis</li>
  </ul>

  <h2>Contract Text and Confidentiality</h2>
  <p>We treat submitted contract text as confidential. Contract text is used only to generate your analysis. We do not sell, share, or disclose your contract text to third parties. Analysis results are stored temporarily to allow you to retrieve your report. We do not use submitted contract text to train AI models.</p>

  <h2>Data Retention</h2>
  <p>Analysis records are retained for up to 90 days to allow report retrieval. Email subscribers may unsubscribe at any time. We honor all deletion requests sent to service@medcontractintel.com.</p>

  <h2>Third-Party Services</h2>
  <ul>
    <li><strong>Stripe:</strong> Payment processing. Subject to Stripe's privacy policy.</li>
    <li><strong>Kit (ConvertKit):</strong> Email delivery. Subject to Kit's privacy policy.</li>
    <li><strong>Anthropic Claude API:</strong> Powers the contract analysis engine. Contract text is processed via Anthropic's API under their data use policies. Anthropic does not use API inputs to train models per their current policies.</li>
  </ul>

  <h2>Your Rights</h2>
  <p>You may request deletion of your data, a copy of data we hold about you, or correction of inaccurate data by emailing service@medcontractintel.com. We will respond within 30 days.</p>

  <h2>Contact</h2>
  <p>AEBMD LLC<br>2803 Philadelphia Pike, Suite B #1447<br>Claymont, DE 19703<br>service@medcontractintel.com</p>
</body>
</html>
```

---

## 2. /pages/terms.html — Terms of Service

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Terms of Service | MedContractIntel™</title>
  <style>
    body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif; color: #1f2937; max-width: 760px; margin: 0 auto; padding: 2rem 1.5rem 4rem; line-height: 1.7; }
    h1 { color: #0f1e3d; font-size: 1.75rem; margin-bottom: 0.25rem; }
    h2 { color: #0f1e3d; font-size: 1.125rem; margin-top: 2rem; margin-bottom: 0.5rem; }
    p, li { font-size: 0.9375rem; color: #374151; }
    a { color: #1a9090; }
    .updated { font-size: 0.85rem; color: #6b7280; margin-bottom: 2rem; }
    .back { display: inline-block; margin-bottom: 2rem; font-size: 0.85rem; color: #6b7280; text-decoration: none; }
    .back:hover { color: #1a9090; }
  </style>
</head>
<body>
  <a href="https://medcontractintel.com" class="back">← MedContractIntel</a>
  <h1>Terms of Service</h1>
  <p class="updated">Last updated: April 27, 2026</p>

  <p>These Terms of Service ("Terms") govern your use of MedContractIntel™, operated by AEBMD LLC ("Company," "we," "us"). By using our website or purchasing our products, you agree to these Terms.</p>

  <h2>Not Legal or Medical Advice</h2>
  <p>MedContractIntel provides educational information and data-driven analysis tools for informational purposes only. Nothing on this site constitutes legal, medical, tax, or financial advice, and no attorney-client or clinical relationship is formed by using our services. We strongly recommend consulting a licensed healthcare attorney before signing any employment contract and, where relevant, a tax or financial advisor regarding compensation structure. Our analysis reflects general benchmark data for internal medicine and hospitalist contracts and should be used as one input among many in your contract review process.</p>

  <h2>Products and Services</h2>
  <p>We offer PDF educational resources (Hospitalist Compensation Playbook, IM/Hospitalist Red Flag Checklist, Negotiation Script Pack) and an AI-powered Contract Analyzer tuned for internal medicine and hospitalist employment agreements. Digital products are delivered instantly upon payment confirmation.</p>

  <h2>Payment and Refund Policy</h2>
  <p>All purchases are processed securely by Stripe. We offer a refund only in the event of a technical failure — specifically, if the Contract Analyzer fails to deliver a completed analysis report after payment. In that event, contact service@medcontractintel.com within 30 days with your order details and we will issue a full refund. We do not offer refunds for change of mind on digital products once delivered. Full details: see <a href="/refund">Refund Policy</a>.</p>

  <h2>Intellectual Property</h2>
  <p>All content, analysis frameworks, benchmarking methodologies, and written materials on this site are the property of AEBMD LLC and are protected by copyright. You may use purchased materials for your own personal contract review. You may not reproduce, distribute, resell, or share purchased materials with third parties.</p>

  <h2>Accuracy of Benchmark Data</h2>
  <p>Compensation benchmarks are sourced from publicly available and licensed datasets including the MGMA Provider Compensation Survey, AAMC Faculty Salary Report, SHM State of Hospital Medicine Report, AMGA Medical Group Compensation & Productivity Survey, Doximity Physician Compensation Report, and CMS public datasets. We update data annually. Actual compensation varies by market, employer, subspecialty (nocturnist, swing, teaching, observation, post-acute, etc.), and individual negotiation. We make no guarantee that the benchmarks reflected in our tools represent the specific market conditions applicable to your contract.</p>

  <h2>Limitation of Liability</h2>
  <p>To the maximum extent permitted by law, AEBMD LLC shall not be liable for any indirect, incidental, special, or consequential damages arising from your use of our products or services, including any contract decisions made in reliance on our analysis. Our total liability for any claim shall not exceed the amount you paid for the specific product or service giving rise to the claim.</p>

  <h2>Governing Law</h2>
  <p>These Terms are governed by the laws of the State of Delaware, without regard to conflict of law principles.</p>

  <h2>Contact</h2>
  <p>AEBMD LLC<br>2803 Philadelphia Pike, Suite B #1447<br>Claymont, DE 19703<br>service@medcontractintel.com</p>
</body>
</html>
```

---

## 3. /refund/index.html — Refund Policy (full page with nav/footer)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Refund Policy — MedContractIntel™</title>
  <meta name="description" content="MedContractIntel 30-day refund policy. Refunds are available if your analysis fails to complete due to a technical error." />
  <meta property="og:type" content="website" />
  <meta property="og:site_name" content="MedContractIntel™" />
  <meta property="og:url" content="https://medcontractintel.com/refund" />
  <meta property="og:title" content="Refund Policy — MedContractIntel™" />
  <meta property="og:description" content="MedContractIntel 30-day refund policy. Refunds are available if your analysis fails to complete due to a technical error." />
  <meta property="og:image" content="https://medcontractintel.com/assets/images/brand_symbol.png" />
  <meta name="twitter:card" content="summary_large_image" />
  <link rel="icon" type="image/png" href="/assets/images/brand_symbol.png" />
  <!-- STYLE BLOCK: copy from site design system once scaffolded; match /about /checklist pattern -->
</head>
<body>

<!-- NAV: reuse site-wide component pattern -->
<nav id="main-nav">
  <div class="nav-banner-inner">
    <a href="/" class="nav-brand">
      <img src="/images/brand-icon.png" height="48" width="48" alt="MedContractIntel" style="border-radius:4px;">
      <div class="nav-brand-text">
        <span class="nav-wordmark nav-wordmark-full">Internal Medicine · Hospitalist Contract Intel</span>
        <span class="nav-wordmark nav-wordmark-short">MedContractIntel<sup style="font-size:0.5em;vertical-align:super;">™</sup></span>
        <span class="nav-tagline">DATA · LEVERAGE · FAIR PAY.</span>
        <span class="nav-sub-text">Physician Compensation for Internal Medicine &amp; Hospitalists</span>
      </div>
    </a>
    <nav class="nav-links" id="nav-links">
      <a href="/analyzer" class="nav-link">Analyzer</a>
      <a href="/#products" class="nav-link">Products</a>
      <a href="/checklist" class="nav-link">Checklist</a>
      <a href="/about" class="nav-link">About</a>
    </nav>
  </div>
</nav>

<!-- PAGE HERO -->
<section class="page-hero">
  <div class="container">
    <p class="eyebrow" style="margin-bottom:0.75rem;">Policies</p>
    <h1>Refund Policy</h1>
    <div class="divider"></div>
    <p style="color:rgba(255,255,255,0.65); font-size:1rem;">Last updated: April 2026</p>
  </div>
</section>

<!-- CONTENT -->
<div class="prose">
  <div class="container">
    <div class="policy-box">
      <h2>30-Day Refund for Failed Analyses</h2>
      <p>
        MedContractIntel offers a <strong>30-day refund</strong> if your analysis fails to complete due to a technical error on our end. This includes cases where:
      </p>
      <ul style="list-style:disc; padding-left:1.25rem; margin-bottom:1.125rem;">
        <li>The analysis fails to return results after more than 15 minutes</li>
        <li>The system encounters an error processing your uploaded file</li>
        <li>The report is not delivered by email or download after completion</li>
      </ul>
      <p>
        To request a refund, email <a href="mailto:service@medcontractintel.com">service@medcontractintel.com</a> with your order number. We process refunds within 2 business days.
      </p>
    </div>

    <h2>Completed Analyses</h2>
    <p>
      Refunds are not available for completed analyses. If you are unsatisfied with the quality of a completed analysis — including concerns about the accuracy of benchmarks, the depth of clause analysis (RVU thresholds, nocturnist differential, census/panel-size commitments, non-compete radius, tail coverage, etc.), or the counter-proposal letter — please contact us at <a href="mailto:service@medcontractintel.com">service@medcontractintel.com</a> and we will work to make it right.
    </p>
    <p>
      This may include re-running your analysis with additional context, answering follow-up questions about your report, or providing supplemental information relevant to your hospitalist or internal medicine contract.
    </p>

    <h2>Contact</h2>
    <p>
      For all refund requests and billing questions: <a href="mailto:service@medcontractintel.com">service@medcontractintel.com</a>
    </p>
    <p>
      Please include your order number or the email address used at checkout so we can locate your analysis quickly.
    </p>
  </div>
</div>

<!-- FOOTER: reuse site-wide component pattern -->
<footer>
  <div class="container-wide footer-inner">
    <div>
      <p style="color:rgba(255,255,255,0.6); font-weight:600; margin-bottom:0.25rem;">MedContractIntel™</p>
      <p>© 2026 MedContractIntel™ &nbsp;·&nbsp; <a href="mailto:service@medcontractintel.com">service@medcontractintel.com</a></p>
    </div>
    <div class="footer-links">
      <a href="/analyzer">Analyzer</a>
      <a href="/#products">Products</a>
      <a href="/checklist">Checklist</a>
      <a href="/about">About</a>
      <a href="/pages/privacy.html">Privacy</a>
      <a href="/pages/terms.html">Terms</a>
      <a href="/pages/disclaimer.html">Disclaimer</a>
      <a href="/pages/dmca.html">DMCA</a>
    </div>
  </div>
  <div class="container-wide" style="margin-top:1.25rem; padding-top:1.25rem; border-top:1px solid rgba(255,255,255,0.07);">
    <p>This tool provides educational and informational analysis only. It does not constitute legal, financial, medical, or professional advice.</p>
  </div>
</footer>

</body>
</html>
```

---

## 4. /pages/disclaimer.html — Medical/Legal/Financial Disclaimer (NEW — EMCI didn't ship this as a standalone)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Disclaimer | MedContractIntel™</title>
  <style>
    body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif; color: #1f2937; max-width: 760px; margin: 0 auto; padding: 2rem 1.5rem 4rem; line-height: 1.7; }
    h1 { color: #0f1e3d; font-size: 1.75rem; margin-bottom: 0.25rem; }
    h2 { color: #0f1e3d; font-size: 1.125rem; margin-top: 2rem; margin-bottom: 0.5rem; }
    p, li { font-size: 0.9375rem; color: #374151; }
    a { color: #1a9090; }
    .updated { font-size: 0.85rem; color: #6b7280; margin-bottom: 2rem; }
    .back { display: inline-block; margin-bottom: 2rem; font-size: 0.85rem; color: #6b7280; text-decoration: none; }
    .back:hover { color: #1a9090; }
  </style>
</head>
<body>
  <a href="https://medcontractintel.com" class="back">← MedContractIntel</a>
  <h1>Disclaimer</h1>
  <p class="updated">Last updated: April 27, 2026</p>

  <h2>Not Legal Advice</h2>
  <p>MedContractIntel is not a law firm. Nothing on this website, in any PDF resource, or in any analysis report should be interpreted as legal advice. Using our tools does not create an attorney-client relationship. Before signing any employment, locum, independent contractor, or partnership agreement, consult a healthcare-focused attorney licensed in your state.</p>

  <h2>Not Medical Advice</h2>
  <p>Although MedContractIntel's content addresses physician employment in internal medicine and hospitalist medicine, nothing on this site constitutes medical advice, credentialing advice, scope-of-practice advice, or clinical guidance. Clinical decisions remain the responsibility of licensed clinicians and their employers.</p>

  <h2>Not Financial or Tax Advice</h2>
  <p>Our analyses address compensation structure, RVU benchmarks, bonus mechanics, and similar economic features of physician contracts. This is educational information, not financial or tax advice. For decisions about compensation structure, S-corp vs. W-2 treatment, 1099 considerations, retirement vehicles, or tax planning, consult a CPA or financial advisor.</p>

  <h2>Accuracy</h2>
  <p>We update benchmark data annually from reputable public and licensed sources (MGMA, AAMC, SHM, AMGA, Doximity, CMS). We make no representation that a specific benchmark figure reflects your exact market. Individual contract outcomes depend on local market dynamics, employer structure, sub-specialty, and negotiation.</p>

  <h2>Third-Party Links</h2>
  <p>Our site may link to third-party resources (professional societies, surveys, legal reference materials). We are not responsible for the content, privacy practices, or accuracy of third-party sites.</p>

  <h2>No Guarantee of Outcome</h2>
  <p>We do not guarantee that use of our analyses or templates will result in any particular contract outcome, compensation increase, or negotiation result.</p>

  <h2>Contact</h2>
  <p>AEBMD LLC<br>2803 Philadelphia Pike, Suite B #1447<br>Claymont, DE 19703<br>service@medcontractintel.com</p>
</body>
</html>
```

---

## 5. /pages/dmca.html — DMCA / Copyright Policy

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>DMCA &amp; Copyright Policy | MedContractIntel™</title>
  <style>
    body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif; color: #1f2937; max-width: 760px; margin: 0 auto; padding: 2rem 1.5rem 4rem; line-height: 1.7; }
    h1 { color: #0f1e3d; font-size: 1.75rem; margin-bottom: 0.25rem; }
    h2 { color: #0f1e3d; font-size: 1.125rem; margin-top: 2rem; margin-bottom: 0.5rem; }
    p, li { font-size: 0.9375rem; color: #374151; }
    a { color: #1a9090; }
    .updated { font-size: 0.85rem; color: #6b7280; margin-bottom: 2rem; }
    .back { display: inline-block; margin-bottom: 2rem; font-size: 0.85rem; color: #6b7280; text-decoration: none; }
    .back:hover { color: #1a9090; }
  </style>
</head>
<body>
  <a href="https://medcontractintel.com" class="back">← MedContractIntel</a>
  <h1>DMCA &amp; Copyright Policy</h1>
  <p class="updated">Last updated: April 27, 2026</p>

  <p>MedContractIntel™ respects the intellectual property rights of others and expects users of our services to do the same. This policy describes how we respond to notices of alleged copyright infringement under the Digital Millennium Copyright Act (DMCA), 17 U.S.C. § 512.</p>

  <h2>Filing a DMCA Notice</h2>
  <p>If you believe content accessible through our services infringes your copyright, please submit a written notice including all of the following:</p>
  <ul>
    <li>A physical or electronic signature of the copyright owner or authorized agent.</li>
    <li>Identification of the copyrighted work claimed to have been infringed.</li>
    <li>Identification of the allegedly infringing material, with information reasonably sufficient to permit us to locate it (URL recommended).</li>
    <li>Your contact information (name, mailing address, telephone, email).</li>
    <li>A statement that you have a good-faith belief that use of the material is not authorized by the copyright owner, its agent, or the law.</li>
    <li>A statement, under penalty of perjury, that the information in the notice is accurate and that you are the copyright owner or are authorized to act on the owner's behalf.</li>
  </ul>

  <h2>Designated Agent</h2>
  <p>Send DMCA notices to our Designated Copyright Agent:</p>
  <p>DMCA Agent, AEBMD LLC<br>2803 Philadelphia Pike, Suite B #1447<br>Claymont, DE 19703<br>dmca@medcontractintel.com</p>

  <h2>Counter-Notification</h2>
  <p>If you believe material you posted was removed or disabled by mistake or misidentification, you may submit a counter-notification including the elements required under 17 U.S.C. § 512(g)(3). Send counter-notifications to the same address above.</p>

  <h2>Repeat Infringers</h2>
  <p>In appropriate circumstances, we will terminate access for users who are repeat infringers.</p>

  <h2>Misrepresentation</h2>
  <p>Any person who knowingly materially misrepresents that material or activity is infringing, or that material or activity was removed or disabled by mistake, may be liable for damages under 17 U.S.C. § 512(f).</p>
</body>
</html>
```

---

## Implementation notes (for Day 2 site-scaffold step)

1. **Directory layout on `med-contract-site/public/`:**
   - `/public/pages/privacy.html`
   - `/public/pages/terms.html`
   - `/public/pages/disclaimer.html`
   - `/public/pages/dmca.html`
   - `/public/refund/index.html`

2. **Routing:** the EMCI site serves `/refund` via `public/refund/index.html`. Same pattern here. For `/privacy`, `/terms`, `/disclaimer`, `/dmca` we keep the `.html` paths exposed and add route rewrites if we want clean URLs in `server/routes.ts` (copy EMCI pattern).

3. **Footer on every page** must include links to Privacy, Terms, Disclaimer, DMCA, Refund. EMCI footer only had Privacy + Terms — MedCI adds Disclaimer + DMCA at launch (cleaner compliance posture).

4. **Reference in Stripe checkout / Kit welcome emails:** link to `/terms`, `/privacy`, `/refund` in mandatory positions.

5. **Open questions to resolve before Day 5 launch:**
   - NJ DBA status — if registered, change footer attribution to "AEBMD LLC dba MedContractIntel, NJ".
   - Whether to add a standalone `/accessibility.html` (WCAG 2.1 AA claim). EMCI didn't ship one; deferrable.
   - Whether `dmca@medcontractintel.com` alias will be live by launch (owner Google Workspace action, ESCALATED item #1). If not, temporarily route DMCA to `service@medcontractintel.com`.

---

**Draft author:** Claude Code (thread session)
**Drafted:** 2026-04-22 late evening EDT
**Pre-launch owner review required:** Yes — Day 4 ≈ 4:00 PM EDT per blueprint §10, as part of final legal-page sanity check by a Claude chat (opus mode) session or a lawyer.
