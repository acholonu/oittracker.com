---
layout: default
title: "Privacy Policy"
---

# Privacy Policy

**Effective Date:** January 2, 2026
**Last Updated:** July 2, 2026

Jones Technical Enterprises, LLC ("we," "us," or "our") operates the OIT Tracker mobile application (the "App"). This Privacy Policy explains how we collect, use, disclose, and safeguard your information when you use our App.

**Please read this Privacy Policy carefully.** By using the App, you agree to the collection and use of information in accordance with this policy.

---

## 1. Information We Collect

### 1.1 Information You Provide

When you use the App, you may provide us with:

- **Child Profile Information:** Your child's first name (nickname acceptable), date of birth (optional), photo (optional, stored on your device only — never uploaded to our servers), allergen information, and treatment details
- **Doctor/Clinic Contact Information (optional):** Your child's allergist or clinic contact details — doctor name, office and after-hours phone numbers, email, clinic name, and clinic address. You enter these so you can quickly call the office and view the clinic address from the Doctor tab.
- **Health Data:** Dose logs (amount, date/time), reaction logs (symptoms, severity), sickness mode periods, notes you add, and **care instructions** — freeform standing-care text you write for a child's caregivers (for example, the dose ritual, what to watch for, or an emergency contact), which may contain phone numbers or medication guidance. Care instructions are stored on our servers and synced to your account's devices and to caregivers you share the child with.
- **Derived Treatment-Progress Metrics:** The App computes and stores server-side a set of derived metrics from your already-collected dose logs: per-allergen dose multipliers, dose counts, consistency dates, treatment milestone events (such as "first dose" or "reached a dose threshold"), and the associated dates. These are derived quantities — the App calculates them from dose logs you have already provided; they are not a new data source. We store them server-side and sync them across your account's devices for backup, cross-device continuity, and in-app progress trends. The fields carried are identifiers (UUIDs), numbers, enums, and dates only — no names, no free text.
- **Apple Sign-In Identifier:** When you sign in with Apple, we receive a stable Apple-issued user identifier ("Apple `sub`") that we use to associate your account across your devices. We do not receive your Apple ID password.
- **Email Address (optional):** When you sign in with Apple, you may choose to share your email address (real or an Apple private-relay address). If shared, we use it only for account-related communication. Apple's Sign in with Apple is governed by [Apple's Privacy Policy](https://www.apple.com/legal/privacy/).
- **Display Name (optional):** A name you set in the App's Settings, shown as the author byline on care instructions you write so other caregivers know who authored them. You can change or clear it at any time.
- **Device Identifier:** A device-generated identifier used to coordinate offline sync between your devices and our servers. This identifier is created locally and is not derived from any hardware ID.

### 1.2 Information Collected Automatically

When you use the App, we automatically collect:

- **Device Information:** Device type, operating system version, and app version
- **Anonymous Product Telemetry:** Beginning with v1.1.0, the App sends anonymous product-usage events to our backend so we can understand which features are used, fix bugs, and prioritize improvements. Each event:
  - Is tied only to a randomly generated, per-install **anonymous identifier**. This identifier is not linked to your name, your child's name, your Apple Sign-In identifier, your email address, or the offline-sync device identifier described above.
  - Includes the event name (for example, `dose_logged`, `paywall_viewed`, `sickness_mode_entered`), a timestamp, the App version, the iOS version, the device model (e.g., "iPhone"), and your subscription tier (e.g., "free" or "subscriber").
  - May include structured properties such as durations, counts (allergen count, taps to log), an internal allergen identifier (UUID — not the allergen's name), the milligram amount of a logged dose, whether sickness mode was active, or the placement that triggered a paywall.
  - **Never** includes free-text fields (notes, dose-log notes), child names, email addresses, photos, precise location, or any other directly identifying information.
  - Is buffered on your device and sent only when the App has network access (the App is offline-first; events are queued locally and flushed when online).
- **Feature Configuration:** The App periodically requests a configuration document from our backend to determine which optional or in-rollout features are enabled for your installation. This request includes the anonymous identifier above, the App version, and the iOS version, and returns only feature on/off settings — no personal data is sent or received.

### 1.3 Website Waitlist

If you sign up for our launch waitlist at oittracker.com, we collect your **email address only**. This email is stored and processed by Kit (ConvertKit), a third-party email service provider. We use it solely to notify you when the App is available. No health data, child information, or other personal details are collected through the waitlist form. You may unsubscribe at any time using the link in any email we send. Kit's privacy policy is available at [https://kit.com/privacy](https://kit.com/privacy).

### 1.4 Information We Do NOT Collect

We do **not** collect:

- Your child's full legal name or location
- Social Security numbers or government IDs
- Financial or payment information (handled by Apple via App Store)
- Precise geolocation data

---

## 2. How We Use Your Information

We use the information we collect to:

- **Provide the Service:** Store and display your dose logs, reactions, and treatment history
- **Sync Across Devices:** Synchronize your dose logs, reactions, notes, sickness-mode history, and account information across your devices and with caregivers you have authorized (Section 3.3)
- **Improve the App:** Analyze anonymous product-telemetry events (Section 1.2) to understand how features are used, find bugs, and prioritize improvements. Telemetry is never combined with your child's profile or health data.
- **Configure Features Remotely:** Use the feature-configuration request (Section 1.2) to gradually roll out new features, disable a feature that is misbehaving, or enable a feature for a specific App version without requiring you to update the App.
- **Communicate With You:** Respond to support requests you send us
- **Ensure Safety:** Monitor for security threats and abuse

We do **not** use your health data to:

- Target advertising to you
- Sell to third parties
- Make automated decisions about you or your child

---

## 3. How We Share Your Information

### 3.1 We Never Sell Your Data

We will **never** sell, rent, or trade your personal information or health data to third parties for marketing purposes.

### 3.2 Service Providers

We share limited information with trusted service providers who help us operate the App:

| Provider | Purpose | Data Shared |
|----------|---------|-------------|
| Google Cloud Platform | Backend hosting | Encrypted health data |
| Apple (Sign in with Apple) | Account authentication and identity | Apple-issued user identifier; email address only if you choose to share it |
| Apple (App Store) | Payment processing, subscription management | Purchase and subscription status (no financial details shared with us) |
| Kit (ConvertKit) | Waitlist email collection | Email address only |
| Amazon Web Services (SES) | Delivery of caregiver-invitation emails | Recipient email address and the invite code only — never health data or names |

As we integrate additional service providers (such as analytics or push notifications), this table will be updated accordingly.

These providers are contractually obligated to protect your data and use it only for the purposes we specify.

### 3.3 Family Sharing

The App lets you invite family members and other caregivers (a co-parent, grandparent, nanny, or self-managing teen) to share access to your child's data on their own Apple ID. Family sharing is opt-in: it does not transmit any data until you explicitly create an invitation.

**How invitations work.** From the in-App Account screen, you choose the recipient's email address, the children to share, and a **role** — **View** (read-only), **Edit** (read and write), or **Co-Owner** (a second full owner of the family; see "Co-owners" below). The App generates a 16-character invite code valid for 7 days and emails it to the address you entered (delivered via Amazon Web Services SES — see Section 3.2). The invitation email contains only the invite code and instructions to accept it — never your name, your child's name, or any health information. The code is also shown to you in the App so you can share it yourself through any channel (email, message, or in person) — for example, if the email doesn't arrive. No data is shared with the recipient until they accept the invitation.

**What data flows.** Once a caregiver accepts an invitation on their device, they see the same dose history, reactions, notes, sickness-mode periods, and treatment information you see for the children you shared — unless you have limited a View-only caregiver's visibility (see "Visibility controls" below). Photos remain on the device that captured them and are never shared. The caregiver's role is checked on every read and every write — a View-only caregiver cannot log doses, edit treatments, or modify any record.

**Visibility controls for View-only caregivers.** For a **View** (read-only) caregiver — a babysitter or school nurse, say — you can additionally choose *which* record types they can see: **notes**, **dose history**, **reactions**, and the **updose schedule** are each independently hideable, per share. You choose at invite time and can change your choice later from the same Account screen. Safety information is never hideable: an accepted caregiver always sees the child's emergency action plan and its document, the doctor/clinic contact, the current sickness status, and the treated allergens — a caregiver who can't see what the child is allergic to can't keep them safe. These limits are enforced by our servers on every read (hidden records are also excluded from the caregiver's device sync), not merely hidden in the caregiver's app. If the same caregiver holds more than one share covering a child, they can see everything at least one of those shares allows. Edit caregivers and co-owners always see everything — hiding records from someone who can edit them would be incoherent.

**Co-owners (a second full owner).** Unlike a View or Edit caregiver, a co-owner is a *second full owner* of your family's records. A co-owner can see and manage **every child in your family — existing children and any you add later — with the same access you have**, including editing and deleting records. A family can have **at most two adult owners** (you plus one co-owner). Only you (the family's creator) can invite a co-owner, and doing so does not use up a caregiver slot. A co-owner can choose to leave the family at any time, which removes their own access. Inviting a second full owner of your child's record is a meaningful sharing decision — we treat it the same way we treat any caregiver invitation: opt-in, never automatic, and revocable.

**Owner controls.** You are the family's creator (the "primary owner"). From the same Account screen you can:

- See every caregiver and co-owner you have invited, and every share you have accepted from someone else
- Choose — and later change — which record types a View-only caregiver can see (the "Visibility controls" above)
- Revoke any caregiver's or co-owner's access at any time. **Revocation is immediate and silent** — the removed person loses access on their next request to our servers and receives no advance warning. Revocation removes future access; it cannot recall data the person already viewed, downloaded, or printed.
- Leave any share that someone else granted to you (the "leave" action is functionally the same as the owner revoking).
- **Transfer ownership** of your family to your co-owner. After a transfer, the co-owner becomes the primary owner and you become the co-owner; the children's records move with the transfer. Transfer is explicit and can only be started by the current primary owner.

**No automatic inheritance.** If you delete your account without first transferring ownership, your family's records follow the normal account-deletion path in Section 4.3 (90-day retention, then permanent deletion). A co-owner does **not** automatically inherit your children's records — ownership only ever moves through the explicit transfer above.

**What we share with whom.** Caregiver and co-owner invitations are stored on our servers along with the email address you provided, the invite code, the chosen role, and timestamps for creation, acceptance, and revocation. To deliver the invitation email, the recipient's email address and the invite code pass through Amazon Web Services SES (our transactional email provider — see Section 3.2); no health data, child names, or other personal details are included in that email. Beyond that delivery step, we do not share data with any third party as part of family sharing. The accepting person authenticates via Sign in with Apple just like the inviting parent; the same data-protection commitments in this policy apply to every adult with access.

### 3.4 Legal Requirements

We may disclose your information if required by law, such as in response to a court order or legal process.

---

## 4. Data Storage and Security

### 4.1 Where Your Data is Stored

- **On Your Device:** The App is offline-first. Your data is stored locally on your device using Apple's Core Data framework so the App works without a network connection.
- **In the Cloud:** Your tracking data (dose logs, reactions, notes, sickness-mode history) and account information are also stored on Google Cloud Platform servers in the United States, so your data can sync across your devices and with caregivers you authorize. This data is **encrypted in transit and at rest** (Section 4.2).
- **Photos — device only:** Any child photo you add stays on the device that captured it and is **never** uploaded to our servers.

### 4.2 How We Protect Your Data

We implement industry-standard security measures:

- Data is encrypted in transit using TLS/SSL
- Data is encrypted at rest on our servers
- Access to servers is restricted and logged
- We use secure authentication tokens

### 4.3 Data Retention

- **Active Accounts:** We retain your account and health data while your account is active. If your account becomes inactive — no sign-in and no data activity for **36 months** — we will notify you at your contact address and then delete the associated data unless you sign in to keep the account active
- **After Deletion:** If you delete your account, we retain your data for 90 days (to allow recovery if you change your mind), then permanently delete it
- **Derived Treatment-Progress Metrics:** The derived metrics described in Section 1.1 follow the same lifecycle as your dose logs. They are retained while your account is active. On account deletion, they are soft-deleted and permanently purged within the same 90-day window as the rest of your account data.
- **Anonymous Product Telemetry:** Because telemetry events (Section 1.2) are tied to an anonymous per-install identifier rather than to your account, they are not removed by account deletion. We retain individual telemetry events only as long as needed for product analytics — in any case, no longer than 18 months — after which they are deleted or aggregated.

### 4.4 Family-Share Revocation

When you revoke a caregiver's or co-owner's access (Section 3.3), the change takes effect immediately on our servers. The removed person receives no advance warning and no notification — their next read or write to your child's records returns an authorization error and the records disappear from their device on the next sync. Revocation removes future access only; it cannot recall data the person already viewed on their device, exported, or shared elsewhere. The same behaviour applies when a caregiver or co-owner leaves a share you granted them; removing a co-owner also dissolves the co-ownership link so they revert to having no access. We retain the share record (status flipped to "revoked") for the standard 90-day account retention window so revocation is auditable for both parties; the underlying child data is unaffected by the revocation.

### 4.5 Data Breach Notification

We maintain administrative, technical, and physical safeguards designed to protect your information (Section 4.2). No system is perfectly secure, however. If we discover a breach of security involving your or your child's identifiable health information — including unauthorized access to, acquisition of, or disclosure of that information — we will:

- Investigate promptly and take steps to contain and remediate the incident;
- Notify affected users without undue delay, and in no case later than **60 calendar days** after we discover the breach;
- Notify the U.S. Federal Trade Commission, and — where a breach affects 500 or more individuals — notify prominent media, as required by the **FTC Health Breach Notification Rule**;
- Notify other authorities or take additional steps where required by applicable state or international law.

Our notice will describe, to the extent known at the time, what happened, the types of information involved, the steps we are taking in response, and steps you can take to protect yourself. Because OIT Tracker is not a HIPAA-covered entity, breaches of health information in the App are governed by the FTC Health Breach Notification Rule and applicable state breach-notification laws rather than by HIPAA.

---

## 5. Children's Privacy (COPPA Compliance)

The App is designed for **parents and guardians** to track their child's oral immunotherapy treatment. We take children's privacy seriously.

### 5.1 Parental Control

- The App is designed for use by parents and guardians. All account creation and data entry is performed by parents — we do not collect personal information directly from children
- Children under 13 may only access the App through a parent-initiated invitation (Section 3.3), which serves as **verifiable parental consent** under COPPA: the parent originates the invite from inside their authenticated account, names the email address that will receive the invite code, and remains in control of the share — they can revoke access at any time and the invite itself expires after 7 days if unused. The child cannot self-enroll, and we do not collect any information directly from the child during invitation, acceptance, or use.
- Parents control all data and can delete it at any time

### 5.2 What We Collect About Children

We collect only the minimum information necessary to provide the service:

- First name or nickname (not full legal name)
- Date of birth (optional)
- Photo (optional, stored on your device only — never uploaded to our servers)
- Allergen and treatment information
- Dose and reaction logs
- Derived treatment-progress metrics computed from the above dose logs (see Section 1.1)
- Care instructions you write for the child's caregivers (freeform text, which may include contact or medication details — see Section 1.1)

We do **not** collect children's:

- Full names or addresses
- Location information
- Social media accounts
- Any information directly from children without parental consent

### 5.3 Parental Rights

Parents can at any time:

- Review their child's data within the App
- Delete their child's profile and all associated data
- Contact us at support@oittracker.com with questions

---

## 6. Your Rights

Depending on your location, you may have the following rights:

### 6.1 Access and Portability

You can view all your data within the App. To request a copy of your data in a portable format, contact us at support@oittracker.com.

### 6.2 Correction

You can update or correct your data directly in the App.

### 6.3 Deletion

You can delete your account and all associated data directly in the App: go to **Settings → Account** and tap **Delete Account** in the Danger Zone. Deleting your account removes your child profiles, dose and reaction logs, notes, sickness-mode history, and caregiver-share records, subject to the 90-day recovery window described in Section 4.3 (after which the data is permanently deleted). You may also request deletion by contacting us at support@oittracker.com.

### 6.4 Control Over Analytics

The anonymous product-telemetry described in Section 1.2 is on by default, but it is optional and is **not** required to use the App. You can turn it off at any time in the App: go to **Settings → Privacy & Data** and switch off **Share Anonymous Analytics**. Turning it off stops the App from collecting any further telemetry and discards any events still queued on your device that have not yet been sent. (Telemetry already transmitted before you opted out is anonymous and is retained as described in Section 4.3.) If you need help, contact us at support@oittracker.com.

---

## 7. Third-Party Links

The App may contain links to third-party websites (such as allergy resources). We are not responsible for the privacy practices of these external sites. We encourage you to read their privacy policies.

---

## 8. Changes to This Privacy Policy

We may update this Privacy Policy from time to time. We will notify you of any changes by:

- Updating the "Last Updated" date at the top of this policy
- Sending a notification within the App for material changes

Your continued use of the App after changes constitutes acceptance of the updated policy.

---

## 9. Contact Us

If you have questions about this Privacy Policy or our privacy practices, please contact us:

**Jones Technical Enterprises, LLC**
Email: support@oittracker.com

For privacy-specific inquiries, please include "Privacy" in the subject line.

---

## 10. California Residents (CCPA/CPRA)

If you are a California resident, the California Consumer Privacy Act, as amended by the California Privacy Rights Act (CCPA/CPRA), gives you certain rights regarding your personal information. Some of these obligations apply only to businesses that meet the CCPA's size thresholds; we extend the following to you regardless, as a matter of good practice.

The personal information we collect is described in Section 1. It includes **"sensitive personal information"** under the CCPA — specifically your child's health information (dose logs, reactions, allergen and treatment details). We collect it only to provide and improve the App as described in Section 2.

Your rights:

- **Right to Know / Access:** Request the categories and specific pieces of personal information we have collected about you.
- **Right to Delete:** Request deletion of your personal information. You can also delete your account and all associated data directly in the App (see Section 6.3).
- **Right to Correct:** Request correction of inaccurate personal information. You can also edit your data directly in the App.
- **Right to Limit Use of Sensitive Personal Information:** We use sensitive personal information only to provide the App and its core features — never to infer characteristics about you and never for advertising. That use already falls within the CCPA's permitted purposes, and we do not use or disclose it for any other purpose.
- **Right to Opt Out of Sale or Sharing:** We do **not** sell or "share" (as the CCPA defines those terms) your personal information, so there is nothing to opt out of.
- **Right to Non-Discrimination:** We will not discriminate against you for exercising any of these rights.

To exercise these rights, contact us at support@oittracker.com. We will take reasonable steps to verify your request and respond within the timeframes required by law. You may use an authorized agent to submit a request on your behalf.

---

## 11. Users Outside the United States

OIT Tracker is intended for use in the United States. We do not target or market the App to users in the European Economic Area (EEA), the United Kingdom, or other regions, and our data practices are built around U.S. law. If you access the App from outside the United States, you do so on your own initiative, you are responsible for compliance with your local laws, and you consent to your information being processed and stored in the United States as described in this policy.

If we expand availability to the EEA or UK in the future, we will update this policy to address the General Data Protection Regulation (GDPR) and UK GDPR — including identifying a lawful basis for processing children's health data (explicit consent) and appointing a representative where required.

---

*This Privacy Policy is governed by the laws of the State of Illinois, United States.*
