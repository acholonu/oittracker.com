# OIT Tracker — Legal & Privacy Decision Log

**Purpose:** Record the key legal/privacy decisions and open questions, with reasoning, so future-you (and any attorney or advisor) can see *why* things are the way they are — and so open questions don't get lost. Update this whenever a decision is made or revisited.

---

## ⏳ Open — needs attorney sign-off

### Future parent-authorized accounts for children under 13

**Launch decision:** Direct use by children under 13 is not offered at initial launch. Parents and authorized caregivers may enter information about children of any age, but a child under 13 may not sign in, accept an invitation, operate the App, enter information, or generate product telemetry. Client and server enforcement for v1.1.0 is tracked in [oit-tracker#672](https://github.com/acholonu/oit-tracker/issues/672).

**Post-launch intent:** Parent-authorized child accounts remain a desired feature because they can let the child participate in their care team. The complete future scope is tracked in [oit-tracker#671](https://github.com/acholonu/oit-tracker/issues/671), including direct parent notice, verifiable parental consent, parent controls, a child-specific role, document storage and access, child-data retention, processor assurances, and telemetry disabled for children under 13.

**Attorney review needed later:** The future feature must not ship until qualified privacy counsel or a COPPA compliance provider confirms the notice, consent-verification method, processor disclosures, retention, deletion, and parent-control design. A parent invitation or Sign in with Apple alone must not be treated as sufficient verification.

**Revisit when:** Work begins on issue #671 or any other feature would collect information directly from a child under 13. | *Originally logged 2026-06-23; launch decision updated 2026-07-10.*

---

## ✅ Decided

| Date | Decision | Reasoning | Revisit when |
|------|----------|-----------|--------------|
| 2026-07-10 | **No direct use by children under 13 at initial launch.** Parents and authorized caregivers may maintain profiles and enter information about children of any age. Parent-authorized under-13 accounts are deferred to issue #671. | Keeps the launch behavior aligned with the product's current lack of a COPPA notice, verifiable-parental-consent, parent-control, and child-role implementation while preserving the future product vision. | Before enabling issue #671 or otherwise collecting information directly from a child under 13. |
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
| **Attorney review of the full document set** | A licensed attorney should still review the launch documents given this is a children's health-tracking product. Future under-13 accounts require a separate review before issue #671 is enabled. |
