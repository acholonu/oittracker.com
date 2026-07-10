# Legal Review — OIT Tracker Privacy Policy & Terms of Service

**Date:** June 21, 2026
**Reviewer:** Claude (Cowork), using the `legal` plugin's compliance, risk-assessment, and contract-review skills
**Documents reviewed:** `legal/privacy-policy.md`, `legal/terms-of-service.md` (both "Last Updated" May 10, 2026)
**Audience for this memo:** Ugochi (founder, non-attorney)
**Not legal advice.** This is a structured self-review to help you prioritize. A licensed attorney should sign off before launch — flagged items are marked **[VERIFY w/ attorney]**. Because this is a *children's health* product, that sign-off matters more than it would for a typical app.

---

## BLUF — Bottom Line Up Front

These two documents are **well above average for a solo-founder product.** Whoever drafted them thought carefully about the medical context, family sharing, and subscription mechanics, and the liability scaffolding (caps, disclaimers, indemnification) is sound. So the work here is not a rewrite — it's closing a short list of specific gaps before you submit to the App Store and before you take real user data.

As of the June 23, 2026 updates below, nearly everything is closed. **Resolved:** sickness-mode wording, in-app account deletion, breach notification, cloud-storage accuracy, analytics opt-out (live in-app toggle), a 36-month data-retention limit, the CCPA/CPRA section (now complete and accurate), the GDPR section (scoped to US-only, App Store confirmed US-only), and the Apple App Store / EULA terms (third-party-beneficiary section added). The "Last Updated" date on both documents was bumped to June 23, 2026.

**What actually remains is small:** (1) **complete** the internal **information-security program** — a fill-in template now exists at `security-program.md` (not public, just has to exist); and (2) the one open *legal-judgment* question — whether COPPA's verifiable-parental-consent machinery binds you given your parent-directed design — now logged in `decisions-log.md` for the attorney. The Apple standard-license setting is **confirmed** (you're on Apple's Standard License Agreement), and ToS §13.5 backs it up. Optional polish: analytics on- vs. off-by-default (toggle exists, so low stakes), and adding an arbitration clause (a tradeoff, your call) — both captured in the decision log.

**Companion files:** `proposed-clause-revisions.md` (clause drafts + applied status), `security-program.md` (internal WISP template), `decisions-log.md` (decisions + open COPPA question for the attorney).

> **Update (June 21, 2026):** The original draft of this memo flagged "sickness mode" as the highest-exposure item, on the assumption it provided dosing *guidance*. The founder confirmed it is a **tracking-only** feature — it records illness periods and logs doses during them, and offers no advice on whether/when/why/how to adjust dosing. ToS §1.2 has been corrected to say so explicitly. That removes the "unregulated medical device / medical advice" theory and drops this item from ORANGE→RED to **GREEN.** The general advice to carry tech E&O / product-liability insurance still stands — sensible for any health-adjacent product — but it is no longer an urgent, feature-specific exposure. Finding #1 below is retained for the record, marked resolved.

**Top priorities, in order:**

| # | Issue | Lens | Risk | Do this before… |
|---|-------|------|------|-----------------|
| 1 | Complete the internal information-security program (template ready at `security-program.md`) | Privacy | **YELLOW** | Holding real user data |
| 2 | COPPA applicability — does verifiable-parental-consent bind you? (logged in `decisions-log.md`) | Privacy | **YELLOW** | Attorney sign-off |
| — | ~~Apple standard-license setting unconfirmed~~ — **RESOLVED June 23, 2026:** founder confirmed Apple Standard License Agreement; ToS §13.5 aligns | Apple | **GREEN** | Done |
| — | ~~CCPA section incomplete~~ — **RESOLVED June 23, 2026:** PP §10 rewritten (adds right to correct + limit sensitive PI) | Privacy | **GREEN** (was YELLOW) | Done |
| — | ~~GDPR legal basis wrong~~ — **RESOLVED June 23, 2026:** PP §11 scoped to US-only (App Store confirmed US-only) | Privacy | **GREEN** (was YELLOW) | Done |
| — | ~~Apple EULA terms missing~~ — **RESOLVED June 23, 2026:** ToS §13.5 added (Apple third-party beneficiary + minimum terms) | Apple | **GREEN** (was YELLOW) | Done |
| — | ~~Open-ended data retention~~ — **RESOLVED June 23, 2026:** PP §4.3 set to 36-month inactivity limit | Privacy | **GREEN** (was ORANGE) | Done |
| — | ~~In-app analytics opt-out~~ — **RESOLVED June 23, 2026:** live in-app toggle (Settings → Privacy → Product Analytics); PP §6.4 corrected | Privacy/Apple | **GREEN** (was YELLOW) | Done |
| — | ~~Cloud-storage contradiction~~ — **RESOLVED June 23, 2026:** confirmed tracking + account data is cloud-stored (encrypted in transit & at rest); PP §2 + §4.1 corrected | Consistency | **GREEN** (was ORANGE) | Done |
| — | ~~No in-app account deletion~~ — **RESOLVED June 21, 2026:** feature exists; PP §6.3 + ToS §10.1 corrected | Apple | **GREEN** (was ORANGE) | Done |
| — | ~~No breach-notification process~~ — **RESOLVED June 21, 2026:** PP §4.5 added (HBNR-aligned) | Privacy | **GREEN** (was ORANGE) | Done |
| — | ~~"Sickness mode" gives guidance~~ — **RESOLVED June 21, 2026:** confirmed tracking-only; ToS §1.2 corrected | Risk | **GREEN** (was ORANGE→RED) | Done |

Risk labels use the `legal` skill's Severity × Likelihood framework (GREEN 1-4 / YELLOW 5-9 / ORANGE 10-15 / RED 16-25).

---

## Findings (severity-ranked)

*Note: the detailed findings below keep their original numbering for the record. The current priority order is the BLUF table above — finding #1 here has since been resolved.*

### 1. ~~"Sickness mode" guidance~~ — **RESOLVED June 21, 2026** (was ORANGE→RED, now GREEN)

**Original concern:** ToS §1.2 said *"The App's 'sickness mode' feature provides general guidance…"* — language that risked recharacterizing the app as an unregulated medical device / medical advice, weakening the "tracking tool only" position in an anaphylaxis context.

**Resolution:** The founder confirmed sickness mode is **tracking-only** — it records illness periods and logs doses during them, with no advice on whether/when/why/how to adjust dosing. ToS §1.2 has been rewritten to state this explicitly:

> *"The App's 'sickness mode' is a tracking feature only. It lets you record periods of illness and log doses during those periods. It does not tell you whether, when, why, or how to adjust dosing during illness, and it provides no medical guidance of any kind — those decisions are entirely yours, in consultation with your child's allergist or healthcare provider."*

This removes the medical-device/advice theory. **Residual advice (still sensible, not urgent):** carry tech E&O / product-liability insurance as a general matter for any health-adjacent product; a liability cap (ToS §8.1) does not stop a tort claim from an injured child who never agreed to the Terms. But this is now ordinary prudence, not a feature-specific red flag.

### 2. ~~No in-app account deletion~~ — **RESOLVED June 21, 2026** (was ORANGE, now GREEN)

**Original concern:** Apple Guideline 5.1.1(v) has required in-app *initiation* of account deletion since June 30, 2022, and the documents routed deletion through email only ("self-service in a future update"), which Apple deems insufficient.

**Resolution:** The founder confirmed the App already has an in-app account-deletion flow. PP §6.3 and ToS §10.1 were corrected to describe it (Account → Delete Account, with the 90-day recovery window). The earlier "future update" wording actually *understated* the built feature, which was its own accuracy problem — now fixed.

**Still open (separate, smaller):** the **analytics opt-out** is still email-only (PP §6.4). That's a YELLOW item (BLUF row 5), not an App-Store blocker, and is gated on building an in-app toggle. See also the COPPA finding below.

### 3. ~~Cloud-storage contradiction~~ — **RESOLVED June 21, 2026** (was ORANGE, now GREEN)

**Original concern:** The documents disagreed about where health data lives — PP §3.2 listed Google Cloud as a current provider of "encrypted health data," while PP §2/§4.1 said cloud sync was a "future update" and data was stored "locally on your device," yet family sharing (PP §3.3) and ToS §5.1 only work if data is on the server. An inaccurate privacy policy is itself an FTC deception risk for health apps (cf. GoodRx, BetterHelp, Flo).

**Resolution:** The founder confirmed tracking data and account information **are stored in the cloud** (Google Cloud Platform, US), **encrypted in transit and at rest**, with the local Core Data store acting as an offline-first cache, and photos remaining device-only. PP §2 and §4.1 were rewritten to say exactly this, so all locations now agree (PP §2, §3.2, §3.3, §4.1, §4.2 and ToS §5.1 are consistent).

**Downstream confirmation:** Because health data is cloud-stored and drawn from multiple sources (your devices + authorized caregivers), the **FTC Health Breach Notification Rule almost certainly applies** — which is exactly why the new breach-notification section (PP §4.5) belongs there. Make sure your **Apple privacy nutrition label** declares cloud-stored health data accordingly.

### 4. No breach-notification process — FTC Health Breach Notification Rule — **ORANGE** [VERIFY w/ attorney]

*Severity 4 × Likelihood 3 = 12.*

OIT Tracker is a health app that is **not** covered by HIPAA (you're not a healthcare provider or covered entity). That puts it under the **FTC Health Breach Notification Rule (HBNR)**, which the FTC amended effective **July 29, 2024** specifically to cover health apps. The Rule applies to a "vendor of personal health records" — broadly, a non-HIPAA app that holds identifiable health info **and has the technical capacity to draw it from more than one source.** Your family-sharing feature (multiple caregivers logging into one child's record) plus Apple Sign-In plausibly meets the "multiple sources" test — **[VERIFY w/ attorney]**, but it's a real risk, not a remote one.

If the HBNR applies, two things follow that your documents don't address **at all**:
- You must notify affected users, the FTC, and (for breaches of 500+) the media, generally within **60 days**.
- Critically, the 2024 amendment treats an **unauthorized *disclosure*** — not just a hack — as a breach. So if you later wire in an analytics or push-notification SDK (which PP §3.2 says you plan to: *"As we integrate additional service providers such as analytics…"*) and health-adjacent data flows to it without proper user authorization, **that itself is a reportable breach.** This is exactly the pattern the FTC has been enforcing against health apps.

**What to do:** Add a short breach-notification commitment to the Privacy Policy (what you'll do, the timeline). Build an internal incident-response checklist. Before adding *any* analytics/SDK, confirm whether it receives health-identifiable data and whether you need user authorization first.

### 5. COPPA 2025 amendments — compliance deadline has passed — **ORANGE**

*Severity 4 × Likelihood 3 = 12.*

You've placed yourself squarely in COPPA's scope by design (PP §5 describes children under 13 accessing data via parent invitation and claims COPPA compliance). The FTC **finalized major COPPA amendments**; the Rule took effect June 23, 2025, with a **full-compliance deadline of April 22, 2026 — already past** as of today. Key new obligations relevant to you:

- **Written data retention policy** that does *not* allow indefinite retention. Your current retention language (PP §4.3: *"retain your data as long as your account is active"*) is open-ended and would need a defined maximum.
- **Written information security program.** You should have one documented (it doesn't have to be public, but it must exist).
- **Separate verifiable parental consent for third-party disclosures** (e.g., targeted advertising or sharing with analytics partners). This reinforces #4 — your planned analytics integration needs its own consent gate for child data.
- Expanded definition of "personal information" (now includes biometric and government identifiers — probably not applicable to you, but worth knowing).

Separately: your **anonymous telemetry is on by default** (PP §1.2, §6.4) for a children's product, with opt-out only by email. Even if technically de-identified, default-on data collection in a kids' app is exactly the "monetizing kids' data" pattern the 2025 amendments target. Pair this with the in-app toggle from #2.

**What to do:** Document a retention policy with hard limits and an information-security program; add a child-specific consent step before any third-party data sharing; make telemetry opt-out (or off-by-default) in-app.

### 6. CCPA sensitive-PI rights incomplete; GDPR legal basis questionable — **YELLOW** [VERIFY w/ attorney]

*Severity 3 × Likelihood 2 = 6.*

- **CCPA/CPRA (PP §10):** Children's health data is **"sensitive personal information"** under California law. Your CCPA section lists Right to Know / Delete / Non-Discrimination but **omits** the CPRA additions: the **right to correct** and the **right to limit use of sensitive PI**. Note the threshold question too — as a small startup you very likely **don't yet meet** CCPA's applicability thresholds (≈$25M revenue / 100k consumers / 50%+ revenue from data sales), so you may not be legally *required* to comply at all. But if you're going to claim CCPA compliance, the list should be complete and accurate.
- **GDPR (PP §11):** You state the legal basis is *"consent and our legitimate interest."* For **special-category (health) data of children**, GDPR generally requires **explicit consent** under Art. 9(2)(a); "legitimate interest" is not a valid basis for processing child health data. The section also omits an EU representative (Art. 27) and the children's-consent-age rules (Art. 8). **The cleaner move for a US-only launch:** state that the app is intended for US users and that you don't target the EEA, and scale back the GDPR claims — *unless* you actually intend to serve EEA users, in which case this needs real work.

**What to do:** Either complete these sections accurately or scope them to where you actually operate. Don't claim compliance with a regime you haven't fully implemented — an incomplete claim is worse than a narrower, accurate one.

### 7. Apple-required EULA terms; arbitration tradeoff; smaller items — **YELLOW / GREEN**

*Severity 2-3 × Likelihood 2-3 = 4-9.*

- **Apple "Licensed Application" EULA terms (YELLOW) [VERIFY w/ attorney].** If this ToS *is* your end-user license (rather than relying on Apple's standard EULA), Apple requires certain terms — most notably that **Apple is a third-party beneficiary** entitled to enforce the EULA, plus specific maintenance/warranty/liability acknowledgments. I don't see those. Either adopt Apple's standard EULA or add the required clauses. (Reasoning from Apple's standard licensing schedule — **[VERIFY w/ attorney]**.)
- **Arbitration (YELLOW, optional).** You have a class-action waiver (ToS §11.4) but **no mandatory-arbitration clause**. A class waiver is generally most enforceable when paired with arbitration; standalone class waivers are weaker. Adding arbitration is the more founder-protective combination — but it's a genuine tradeoff (some founders prefer to keep courts available, and arbitration has its own costs). Your call; flagging the option.
- **"Family" tier says "5 or more" children (GREEN).** ToS §5.1 caps caregiver seats at 5 but lists children as "5 or more" — unbounded. Probably should be a defined cap.
- **Relative link (GREEN).** ToS §4.1 links to `privacy-policy.md`; confirm that resolves correctly on the published site (e.g., `/privacy-policy`).
- **Telemetry survives deletion (GREEN, but disclose clearly).** PP §4.3 keeps anonymous telemetry after account deletion. Defensible if truly de-identified, but make sure users aren't surprised — the current wording is actually pretty clear, so this is just a "keep an eye on it."

---

## What's working well (so you don't second-guess it)

- The **medical disclaimer** (ToS §1) is prominent, repeated, and appropriately emphatic — good instinct.
- The **liability cap and indemnification** (ToS §8, §9) are drafted in your favor and are commercially standard.
- The **family-sharing and revocation** descriptions (PP §3.3, §4.4) are unusually transparent — the "revocation is immediate and silent; cannot recall already-viewed data" honesty is exactly right.
- The **subscription / read-only-on-lapse** design (ToS §5.5) is thoughtful and user-friendly for a medical product, and the auto-renewal disclosures (ToS §5.3) are solid.
- The **telemetry disclosure** (PP §1.2) is more detailed and honest than most apps' — that detail is an asset for your Apple privacy label.

---

## Methodology

I read both documents in full, then assessed them through four lenses you selected: **Apple App Store readiness, internal consistency, risk/liability, and privacy compliance.** Issues are scored with the `legal` skill's Severity × Likelihood matrix and classified GREEN/YELLOW/ORANGE/RED.

I **web-verified the four time-sensitive external requirements** (rather than relying on training knowledge), because each changed after my knowledge cutoff and each is decisive here:

- FTC's 2025 COPPA amendments and their April 22, 2026 compliance deadline.
- The FTC Health Breach Notification Rule's July 29, 2024 expansion to health apps.
- Apple's in-app account-deletion requirement (Guideline 5.1.1(v)).
- Apple's privacy-label / App Tracking Transparency framework.

Sources are listed below.

## Limitations

- **I am not a lawyer and this is not legal advice.** For a children's medical-adjacent product, please have a licensed attorney review — especially items marked **[VERIFY w/ attorney]** (#1, #4, #6, and the Apple EULA point in #7).
- Several conclusions depend on **facts I can't see in the documents** — most importantly, whether health data is actually stored server-side today (drives #3, #4, #5) and what "sickness mode" literally tells users (drives #1). Resolve those facts first.
- I reviewed only the two `.md` files. I did not see the app itself, your Apple privacy-label entries, any DPA with Google Cloud or Kit, or your actual data flows.
- COPPA, CCPA, and GDPR **applicability thresholds** are fact-specific; you may not currently be subject to all of them. Where I note that, treat it as a reason to make claims *accurate*, not necessarily to do more.

## Sources

- FTC — [FTC Finalizes Changes to Children's Privacy Rule](https://www.ftc.gov/news-events/news/press-releases/2025/01/ftc-finalizes-changes-childrens-privacy-rule-limiting-companies-ability-monetize-kids-data)
- Federal Register — [Children's Online Privacy Protection Rule (final amendments)](https://www.federalregister.gov/documents/2025/04/22/2025-05904/childrens-online-privacy-protection-rule)
- FTC — [Updated Health Breach Notification Rule protects users of health apps](https://www.ftc.gov/business-guidance/blog/2024/04/updated-ftc-health-breach-notification-rule-puts-new-provisions-place-protect-users-health-apps)
- FTC — [Complying with the Health Breach Notification Rule](https://www.ftc.gov/business-guidance/resources/complying-ftcs-health-breach-notification-rule-0)
- Apple Developer — [Offering account deletion in your app (Guideline 5.1.1(v))](https://developer.apple.com/support/offering-account-deletion-in-your-app/)
- Apple Developer — [App Privacy Details (privacy nutrition labels)](https://developer.apple.com/app-store/app-privacy-details/)
- Apple Developer — [User Privacy and Data Use / App Tracking Transparency](https://developer.apple.com/app-store/user-privacy-and-data-use/)
