# Proposed Clause Revisions — OIT Tracker

**Created:** June 21, 2026
**Status:** DRAFTS. Read the gating note on each before publishing.

This file holds the clause changes that **must not go live until the underlying in-app features exist.** Publishing a privacy policy or Terms that describe a feature you haven't shipped is itself a legal risk — the FTC treats "we say X, the app does Y" as a deceptive practice, and has fined health apps for exactly this. So the order of operations is: **(1) build the in-app feature → (2) paste the matching clause below into the live document.**

The **breach-notification section is already live** in `privacy-policy.md` §4.5 — it's a commitment, not a feature claim, so it didn't need gating. The internal checklist at the bottom of this file is what makes that commitment real; it's internal-only and should **not** be published.

---

## A. In-app account deletion — ✅ APPLIED LIVE June 21, 2026

**Why:** Apple Guideline 5.1.1(v) requires apps with account creation to let users *initiate deletion inside the app* (in force since June 30, 2022). An email-only flow is insufficient.

> ✅ **DONE.** The founder confirmed the in-app Delete Account flow already exists, so the clauses below were applied live to `privacy-policy.md` §6.3 and `terms-of-service.md` §10.1. Kept here for the record. The build notes remain useful as a compliance checklist for the existing feature.

### A1. Privacy Policy §6.3 — replace existing text

> ### 6.3 Deletion
>
> You can delete your account and all associated data at any time from within the App, under **Account → Delete Account**. Deleting your account removes your child profiles, dose and reaction logs, notes, sickness-mode history, and caregiver-share records, subject to the 90-day recovery window described in Section 4.3 (after which the data is permanently deleted). You may also request deletion by contacting us at support@oittracker.com.

### A2. Terms of Service §10.1 — replace existing text

> ### 10.1 By You
>
> You may stop using the App at any time. You can delete your account and all associated data from within the App, under **Account → Delete Account**; deletion is subject to the 90-day recovery period described in Section 10.3. You may also contact support@oittracker.com if you need assistance.

**Build notes (not for publication):**
- Put "Delete Account" in account settings, easy to find — Apple expects it there.
- It must delete the *entire* account and personal data, not just deactivate. A 90-day soft-delete/recovery window before permanent deletion is acceptable as long as the user genuinely initiated deletion.
- Handle the family-sharing case: deleting an owner account must also remove the child records shared to caregivers (Apple expects user-generated content shared with others to be deleted).
- The "highly regulated industry" exception may let you add a confirmation step, but still allow in-app *initiation*. Don't rely on the exception to skip the feature.

---

## B. In-app analytics opt-out — ✅ APPLIED LIVE June 21, 2026

**Why:** PP §6.4 made opt-out email-only, and telemetry is on by default in a *children's* product — the pattern the FTC's 2025 COPPA amendments specifically target. An in-app toggle is the fix.

> ✅ **DONE.** The founder confirmed the in-app analytics toggle now exists, so the clause below was applied live to `privacy-policy.md` §6.4 (and the section was retitled "Control Over Analytics," with a line clarifying the telemetry is optional and not required to use the App). Kept here for the record. The default-state decision below is still worth a conscious choice.

### B1. Privacy Policy §6.4 — replace existing text

> ### 6.4 Control Over Analytics
>
> You can turn the anonymous product-telemetry described in Section 1.2 on or off at any time from within the App, under **Settings → Privacy → Product Analytics**. Turning it off stops new telemetry from being collected for your installation. You may also contact us at support@oittracker.com.

**Decision to make (recommended, not just wording):** Consider making telemetry **off by default** — or presenting a clear first-run choice — for a children's health app. Default-on collection of kids' usage data, even when de-identified, is the highest-scrutiny configuration under the amended COPPA Rule. If you keep it on by default, document why in your internal records. **[VERIFY w/ attorney]**

---

## C. Data-retention limit — ✅ APPLIED LIVE June 23, 2026 (36 months)

**Why (not a COPPA argument):** Even if COPPA does not apply to you, an open-ended "we keep it as long as your account is active" (current PP §4.3) means you hold sensitive children's health data on dormant accounts indefinitely. A defined limit is plain **data minimization**: less retained data = smaller breach exposure (and breach *is* a risk that clearly applies to you via the FTC Health Breach Notification Rule). It's also a trust signal for parents. The only cost: dormant accounts' data is deleted after notice.

> ⏸️ **NOT YET APPLIED.** Founder is deciding whether to include it. Number set to **36 months** per founder input. If you want it in, say so and I'll apply C1 live.

### C1. Privacy Policy §4.3 — replace the "Active Accounts" bullet

> - **Active Accounts:** We retain your account and health data while your account is active. If your account becomes inactive — no sign-in and no data activity for **36 months** — we will notify you at your contact address and then delete the associated data unless you sign in to keep the account active.

---

## D. Internal — Data-Breach Incident Response Checklist (DO NOT PUBLISH)

This backs the public commitment in PP §4.5. Keep it internal.

1. **Detect & log** — Record discovery date/time. The 60-day clock starts at discovery.
2. **Contain** — Revoke compromised credentials/keys; isolate affected systems (GCP, Kit, any analytics SDK).
3. **Assess scope** — What data, how many users, which children, was it health-identifiable info? Was it unauthorized *access* or unauthorized *disclosure* (e.g., a misconfigured SDK)? Both count under the amended HBNR.
4. **Notify users** — Plain-language notice: what happened, data involved, what you're doing, what they should do. No later than 60 calendar days after discovery.
5. **Notify FTC** — Via the FTC's HBNR notice process. If 500+ individuals: notify the FTC within 60 days *and* notify prominent media in affected areas.
6. **Notify states** — Most states have their own breach laws with their own triggers/timelines; check the states of affected users (or notify all).
7. **Document** — Keep a written record of the incident, decisions, and notifications. Regulators ask for this.
8. **Remediate & review** — Root-cause fix; update the security program (also a COPPA requirement).

**Pre-empt the most likely trigger:** before wiring in *any* new analytics, push, or third-party SDK, confirm whether it receives health-identifiable data and whether you need user authorization first. Sending health-adjacent data to a new SDK without authorization is itself a reportable "unauthorized disclosure" under the 2024 HBNR amendment — this is the pattern behind the GoodRx / BetterHelp / Flo enforcement actions.

---

## E. Apple App Store Terms — ✅ APPLIED LIVE June 23, 2026 (ToS §13.5)

**Why:** Your ToS does not contain Apple's required EULA terms. The safe, low-effort path is to **rely on Apple's standard Licensed Application EULA** (don't upload a custom EULA in App Store Connect) and add this short section so your ToS aligns with it and names Apple as a third-party beneficiary. These are Apple's standard "minimum terms" acknowledgments.

> ✅ **Safe to apply now.** Recommend adding as a new section (suggested placement: new **§13.5** under General Provisions, or a standalone "Apple App Store Terms" section before §14). First confirm your App Store Connect License Agreement is set to **"Apple's Standard License Agreement"** (App Information → License Agreement).

> ### Apple App Store Terms
>
> OIT Tracker is distributed through the Apple App Store. Your license to use the App is also governed by Apple's standard **Licensed Application End User License Agreement (EULA)**, available at https://www.apple.com/legal/internet-services/itunes/dev/stdeula/. If there is any conflict between these Terms and Apple's standard EULA regarding your license to use the App, Apple's EULA governs that license. In addition:
>
> - These Terms are an agreement between you and Jones Technical Enterprises, LLC only, **not with Apple.** Apple is not responsible for the App or its content.
> - Apple has no obligation to provide maintenance or support for the App; we are solely responsible for support, as described in these Terms.
> - Apple is not responsible for any product warranties. If the App fails to conform to any applicable warranty, you may notify Apple, and Apple may refund the purchase price (if any); to the maximum extent permitted by law, Apple has no other warranty obligation regarding the App.
> - We, not Apple, are responsible for addressing any claims relating to the App, including product-liability, regulatory, and intellectual-property claims.
> - You represent that you are not located in a country subject to a U.S. Government embargo or designated "terrorist-supporting," and that you are not on any U.S. Government prohibited-party list.
> - **Apple and Apple's subsidiaries are third-party beneficiaries of these Terms, and Apple has the right to enforce these Terms against you as a third-party beneficiary.**

---

## F. California Residents (CCPA/CPRA) — ✅ APPLIED LIVE June 23, 2026 (PP §10)

**Why:** The current §10 omits the **right to correct** and the **right to limit use of sensitive personal information** (your child's health data is "sensitive PI" under California law). This version is complete and accurate, and is honest that some rights apply only above CCPA size thresholds you likely don't meet yet.

> ✅ **Safe to apply now** (wording only).

> ## 10. California Residents (CCPA/CPRA)
>
> If you are a California resident, the California Consumer Privacy Act, as amended by the California Privacy Rights Act (CCPA/CPRA), gives you certain rights regarding your personal information. Some of these obligations apply only to businesses that meet the CCPA's size thresholds; we extend the following to you regardless, as a matter of good practice.
>
> The personal information we collect is described in Section 1. It includes **"sensitive personal information"** under the CCPA — specifically your child's health information (dose logs, reactions, allergen and treatment details). We collect it only to provide and improve the App as described in Section 2.
>
> Your rights:
>
> - **Right to Know / Access:** Request the categories and specific pieces of personal information we have collected about you.
> - **Right to Delete:** Request deletion of your personal information. You can also delete your account and all associated data directly in the App (see Section 6.3).
> - **Right to Correct:** Request correction of inaccurate personal information. You can also edit your data directly in the App.
> - **Right to Limit Use of Sensitive Personal Information:** We use sensitive personal information only to provide the App and its core features — never to infer characteristics about you and never for advertising. That use already falls within the CCPA's permitted purposes, and we do not use or disclose it for any other purpose.
> - **Right to Opt Out of Sale or Sharing:** We do **not** sell or "share" (as the CCPA defines those terms) your personal information, so there is nothing to opt out of.
> - **Right to Non-Discrimination:** We will not discriminate against you for exercising any of these rights.
>
> To exercise these rights, contact us at support@oittracker.com. We will take reasonable steps to verify your request and respond within the timeframes required by law. You may use an authorized agent to submit a request on your behalf.

---

## G. Scope down international/GDPR — ✅ APPLIED LIVE June 23, 2026 (PP §11; App Store confirmed US-only)

**Why:** The current §11 states the legal basis is "consent and legitimate interest." For **special-category (health) data of children**, GDPR generally requires *explicit consent*, not legitimate interest — so the current claim is inaccurate. Since you sell US-only, the honest fix is to scope the section to the US rather than half-claim GDPR compliance.

> ✅ **Safe to apply now**, *but* first confirm your **App Store territory availability is US-only** (App Store Connect → Pricing and Availability). If you actually distribute in the EEA/UK, this scope-down would be inaccurate and GDPR needs real work instead — **[VERIFY: your App Store territories]**.

> ## 11. Users Outside the United States
>
> OIT Tracker is intended for use in the United States. We do not target or market the App to users in the European Economic Area (EEA), the United Kingdom, or other regions, and our data practices are built around U.S. law. If you access the App from outside the United States, you do so on your own initiative, you are responsible for compliance with your local laws, and you consent to your information being processed and stored in the United States as described in this policy.
>
> If we expand availability to the EEA or UK in the future, we will update this policy to address the General Data Protection Regulation (GDPR) and UK GDPR — including identifying a lawful basis for processing children's health data (explicit consent) and appointing a representative where required.

---

## Source anchors

- Apple — [Offering account deletion in your app (5.1.1(v))](https://developer.apple.com/support/offering-account-deletion-in-your-app/)
- FTC — [Health Breach Notification Rule guidance](https://www.ftc.gov/business-guidance/resources/complying-ftcs-health-breach-notification-rule-0)
- FTC — [2025 COPPA final amendments](https://www.federalregister.gov/documents/2025/04/22/2025-05904/childrens-online-privacy-protection-rule)
- Apple — [Standard Licensed Application EULA](https://www.apple.com/legal/internet-services/itunes/dev/stdeula/)
- Apple — [Minimum Terms of Developer's EULA (custom EULA requirements)](https://www.apple.com/legal/internet-services/itunes/dev/minterms/)
