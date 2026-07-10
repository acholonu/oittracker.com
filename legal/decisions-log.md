# OIT Tracker — Legal & Privacy Decision Log

**Purpose:** Record the key legal/privacy decisions and open questions, with reasoning, so future-you (and any attorney or advisor) can see *why* things are the way they are — and so open questions don't get lost. Update this whenever a decision is made or revisited.

---

## ⏳ Open — needs attorney sign-off

### COPPA applicability — does verifiable-parental-consent bind us?

**The question:** Is OIT Tracker an "operator" subject to COPPA's verifiable-parental-consent (VPC) obligations, given that the app is **directed to parents** and parents (not children) enter the child's data?

**Why it's genuinely unsettled:**
- **Cuts toward "not fully covered":** COPPA regulates personal information collected *from a child under 13*. Here an adult creates the account and enters data *about* a child — a different posture than a kids' service collecting from children directly. A parent-directed health tracker has a real argument that the heavy VPC machinery doesn't squarely apply.
- **Cuts toward "covered":** (a) the self-managing-teen / child-as-caregiver path could involve an under-13 child using the app directly; (b) our own Privacy Policy §5 affirmatively claims COPPA compliance and describes under-13 access via invitation — we've partly described ourselves into the regime.

**Current posture (interim):** We do the cheap, do-anyway hygiene regardless (36-month retention limit, written security program, in-app analytics opt-out, breach process). We have **not** built a formal VPC flow.

**Decision needed from attorney:** "Given we're parent-directed and parents enter the data, are we a COPPA 'operator,' and does the self-managing-teen feature change that?"

**Revisit when:** before adding any child self-use feature, or any third-party data sharing of child data. | *Logged 2026-06-23.*

---

## ✅ Decided

| Date | Decision | Reasoning | Revisit when |
|------|----------|-----------|--------------|
| 2026-06-23 | **Geography: US-only.** App Store availability is US-only; Privacy Policy §11 scoped to the US; GDPR not implemented. | Selling US-only; honest scope-down beats half-claiming GDPR compliance. | Expanding to EEA/UK (then GDPR/UK-GDPR work needed). |
| 2026-06-23 | **Apple license: standard.** Using Apple's Standard Licensed Application EULA (no custom EULA uploaded). ToS §13.5 aligns to it and names Apple a third-party beneficiary. | Lowest-effort, well-protected path for a solo founder; standard EULA already contains required terms. | Only if custom license terms become necessary. |
| 2026-06-23 | **Data retention: 36-month inactivity limit** (PP §4.3). | Data minimization — shrinks breach exposure on dormant accounts and builds parent trust. Not dependent on COPPA applying. | Annual review. |
| 2026-06-23 | **Analytics: ON by default, with in-app opt-out toggle** (PP §6.4). | Keeps analytics coverage while giving an easy, in-app control. | If FTC posture on kids' data tightens, or to improve trust — consider off-by-default / first-run opt-in. |
| 2026-06-23 | **Cloud storage: tracking + account data on Google Cloud (US), encrypted in transit & at rest; photos device-only.** | Required to deliver sync + family sharing; storing it is intrinsic to the service. | Vendor/region change. |

---

## 📝 Recommended / not yet done (not feature or document blockers)

| Item | Note |
|------|------|
| **Tech E&O / product-liability insurance** | Recommended for any health-adjacent product. A liability cap doesn't stop a tort claim from an injured child who never agreed to the Terms. Get quotes before scaling. |
| **Arbitration clause** | ToS has a class-action waiver but no mandatory arbitration. Pairing them is more founder-protective, but it's a genuine tradeoff (some prefer keeping courts available). Founder to decide. |
| **Attorney review of the full document set** | Especially the COPPA question above. Everything document-level is done; a licensed attorney should still sign off given this is a children's health product. |
