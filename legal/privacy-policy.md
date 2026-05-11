---
layout: default
title: "Privacy Policy"
---

# Privacy Policy

**Effective Date:** January 2, 2026
**Last Updated:** May 10, 2026

Jones Technical Enterprises, LLC ("we," "us," or "our") operates the OIT Tracker mobile application (the "App"). This Privacy Policy explains how we collect, use, disclose, and safeguard your information when you use our App.

**Please read this Privacy Policy carefully.** By using the App, you agree to the collection and use of information in accordance with this policy.

---

## 1. Information We Collect

### 1.1 Information You Provide

When you use the App, you may provide us with:

- **Child Profile Information:** Your child's first name (nickname acceptable), date of birth (optional), photo (optional, stored on your device only — never uploaded to our servers), allergen information, and treatment details
- **Health Data:** Dose logs (amount, date/time), reaction logs (symptoms, severity), sickness mode periods, and notes you add
- **Apple Sign-In Identifier:** When you sign in with Apple, we receive a stable Apple-issued user identifier ("Apple `sub`") that we use to associate your account across your devices. We do not receive your Apple ID password.
- **Email Address (optional):** When you sign in with Apple, you may choose to share your email address (real or an Apple private-relay address). If shared, we use it only for account-related communication. Apple's Sign in with Apple is governed by [Apple's Privacy Policy](https://www.apple.com/legal/privacy/).
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
- **Sync Across Devices:** If you use cloud sync (available in a future update), synchronize your data across your devices
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

As we integrate additional service providers (such as analytics or push notifications), this table will be updated accordingly.

These providers are contractually obligated to protect your data and use it only for the purposes we specify.

### 3.3 Family Sharing

The App lets you invite family members and other caregivers (a co-parent, grandparent, nanny, or self-managing teen) to share access to your child's data on their own Apple ID. Family sharing is opt-in: it does not transmit any data until you explicitly create an invitation.

**How invitations work.** From the in-App Account screen, you choose the caregiver's email address, the children to share, and a permission level — **View** (read-only) or **Edit** (read and write). The App generates a 16-character invite code valid for 7 days and shows it to you so you can share it through any channel (email, message, or in person). Until SMTP-based delivery ships, no data leaves the App without your action.

**What data flows.** Once a caregiver accepts an invitation on their device, they see the same dose history, reactions, notes, sickness-mode periods, and treatment information you see for the children you shared. Photos remain on the device that captured them and are never shared. The caregiver's permission level is checked on every read and every write — a View-only caregiver cannot log doses, edit treatments, or modify any record.

**Owner controls.** You remain the sole owner of your child's data. From the same Account screen you can:

- See every caregiver you have invited and every share you have accepted from someone else
- Revoke any caregiver's access at any time. **Revocation is immediate and silent** — the revoked caregiver loses access on their next request to our servers and receives no advance warning. Revocation removes future access; it cannot recall data the caregiver already viewed, downloaded, or printed.
- Leave any share that someone else granted to you (the "leave" action is functionally the same as the owner revoking).

**What we share with whom.** Caregiver invitations are stored on our servers along with the email address you provided, the invite code, the chosen permission level, and timestamps for creation, acceptance, and revocation. We do not share data with any third party as part of family sharing. The accepting caregiver authenticates via Sign in with Apple just like the inviting parent; the same data-protection commitments in this policy apply to both.

### 3.4 Legal Requirements

We may disclose your information if required by law, such as in response to a court order or legal process.

---

## 4. Data Storage and Security

### 4.1 Where Your Data is Stored

- **On Your Device:** Health data is stored locally on your device using Apple's Core Data framework
- **In the Cloud:** If you enable cloud sync (available in a future update), your data will be stored on Google Cloud Platform servers in the United States

### 4.2 How We Protect Your Data

We implement industry-standard security measures:

- Data is encrypted in transit using TLS/SSL
- Data is encrypted at rest on our servers
- Access to servers is restricted and logged
- We use secure authentication tokens

### 4.3 Data Retention

- **Active Accounts:** We retain your data as long as your account is active
- **After Deletion:** If you delete your account, we retain your data for 90 days (to allow recovery if you change your mind), then permanently delete it
- **Anonymous Product Telemetry:** Because telemetry events (Section 1.2) are tied to an anonymous per-install identifier rather than to your account, they are not removed by account deletion. We retain individual telemetry events only as long as needed for product analytics — in any case, no longer than 18 months — after which they are deleted or aggregated.

### 4.4 Family-Share Revocation

When you revoke a caregiver's access (Section 3.3), the change takes effect immediately on our servers. The revoked caregiver receives no advance warning and no notification — their next read or write to your child's records returns an authorization error and the records disappear from their device on the next sync. Revocation removes future access only; it cannot recall data the caregiver already viewed on their device, exported, or shared elsewhere. The same behaviour applies when a caregiver leaves a share you granted them. We retain the share record (status flipped to "revoked") for the standard 90-day account retention window so revocation is auditable for both parties; the underlying child data is unaffected by the revocation.

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

You can request deletion of your account and all associated data by contacting us at support@oittracker.com. A self-service delete feature will be available in a future update.

### 6.4 Opt-Out of Analytics

The anonymous product-telemetry described in Section 1.2 is on by default. A self-service in-App control to disable telemetry will be available in a future update. In the meantime, contact us at support@oittracker.com to opt out, and we will disable telemetry collection for your installation.

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

## 10. California Residents (CCPA)

If you are a California resident, you have additional rights under the California Consumer Privacy Act (CCPA):

- **Right to Know:** You can request information about the categories of personal information we collect
- **Right to Delete:** You can request deletion of your personal information
- **Right to Non-Discrimination:** We will not discriminate against you for exercising your privacy rights

We do not sell personal information as defined by the CCPA.

---

## 11. European Users (GDPR)

If you are located in the European Economic Area (EEA), you have additional rights under the General Data Protection Regulation (GDPR):

- **Legal Basis:** We process your data based on your consent and our legitimate interest in providing the service
- **Data Controller:** Jones Technical Enterprises, LLC is the data controller
- **Right to Lodge a Complaint:** You have the right to lodge a complaint with a supervisory authority

---

*This Privacy Policy is governed by the laws of the State of Illinois, United States.*
