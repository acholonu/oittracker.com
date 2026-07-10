# OIT Tracker — Information Security Program (Internal)

**Owner:** Ugochi — Jones Technical Enterprises, LLC
**Status:** DRAFT TEMPLATE — fill in the `[bracketed]` items
**Last reviewed:** June 23, 2026
**Review cadence:** at least annually, and after any material change to data flows or vendors

> **Internal document — do NOT publish.** This is the written security program referenced by the Privacy Policy's safeguards (PP §4.2) and breach-notification commitment (PP §4.5). It exists so you have a documented program if a regulator, partner, or insurer ever asks — and to satisfy the written-security-program expectation that applies to children's data. One page is fine; keep it current rather than long.

## 1. Data inventory & sensitivity

| Data | Where it lives | Sensitivity |
|------|----------------|-------------|
| Child profile (first name/nickname, optional DOB) | On-device (Core Data) + Google Cloud (US) | Elevated (about a child) |
| Health data (dose logs, reactions, sickness periods, notes) | On-device + Google Cloud (US) | **Sensitive** (children's health) |
| Allergen / treatment info | On-device + Google Cloud (US) | Sensitive |
| Apple Sign-In identifier; optional email | Google Cloud (US) | Identifier |
| Device identifier (offline sync) | On-device + Google Cloud (US) | Low |
| Anonymous product telemetry | Google Cloud (US) / [analytics backend] | De-identified |
| Child photos | **On-device only — never uploaded** | Sensitive (contained on-device) |
| Waitlist email | Kit (ConvertKit) | Identifier |

## 2. Access control
- Production data access is limited to: `[list people — likely just you]`.
- Admin authentication to Google Cloud uses `[Google account + 2FA / MFA — confirm enabled]`.
- Principle of least privilege; no shared admin credentials.
- End users authenticate via Sign in with Apple; caregiver access is permission-checked on every read/write.

## 3. Encryption
- **In transit:** TLS/SSL for all client-server traffic.
- **At rest:** encrypted on Google Cloud; on-device data protected by iOS device encryption.

## 4. Service providers (sub-processors)
- **Google Cloud Platform** — hosting (US region). DPA/terms: `[reviewed? link]`.
- **Apple** — Sign in with Apple, App Store payments. Covered by Apple Developer agreements.
- **Kit (ConvertKit)** — waitlist email only. DPA/terms: `[reviewed? link]`.
- `[Any analytics/push SDK — add here when introduced]`.

## 5. Retention & deletion
- Active accounts: retained while active; inactive 36 months → notify, then delete (PP §4.3).
- Account deletion: 90-day recovery window, then permanent deletion (PP §6.3).
- Telemetry: retained ≤ 18 months, then deleted or aggregated (PP §4.3).

## 6. Vulnerability & patch management
- Keep app dependencies, SDKs, and server packages updated. Cadence: `[e.g., monthly review + critical patches ASAP]`.
- Monitor Google Cloud and Apple security advisories.

## 7. Logging & monitoring
- Server access is restricted and logged.
- Review logs for anomalies `[cadence]`; investigate unexpected access.

## 8. Incident response
- Follow the **Data-Breach Incident Response Checklist** in `proposed-clause-revisions.md` §D.
- Key obligation: under the FTC Health Breach Notification Rule, notify affected users and the FTC within **60 days** of discovery (media too, if 500+).
- Incident owner: `[you / contact]`.

## 9. New-vendor / new-SDK gate
- Before adding **any** analytics, push, or third-party SDK: confirm whether it will receive health-identifiable data and whether user authorization is required first. Sending health-adjacent data to a new SDK without authorization is itself a reportable "unauthorized disclosure" under the HBNR.

## 10. Review log
| Date | Reviewed by | Changes since last review |
|------|-------------|---------------------------|
| 2026-06-23 | Ugochi | Initial program created |
| | | |
