---
title: Privacy Policy — ToBeVPN
---

# ToBeVPN Privacy Policy

**Effective date:** April 21, 2026

[Русская версия](privacy.html)

ToBeVPN ("we", "the app") is a VPN service for Android devices. This policy describes what data we collect, why, and with whom we share it.

## Data controller

- **Controller:** Ivan Zaichenko (natural person)
- **Jurisdiction:** Russian Federation
- **Contact for personal data inquiries:** [iv.zai4k@gmail.com](mailto:iv.zai4k@gmail.com)

## 1. Principles

- We **do not log your internet traffic**: visited sites, domain names, request and response contents are not recorded and not shared with third parties.
- We **do not collect location**, contacts, photos, files, browsing history, messages, or any other personal materials from your device.
- We collect only the minimum data required to operate the app: identifying the device, issuing a subscription, and counting traffic usage.

## 2. Data we collect

| Data | Purpose | Stored at |
| --- | --- | --- |
| Android device ID (`Settings.Secure.ANDROID_ID`) | Linking the subscription to a specific device | Bot backend |
| Device name (`Build.MANUFACTURER` + `Build.MODEL`) | Display in your devices list | Bot backend |
| Telegram ID | Authentication and subscription management | Bot backend and VPN panel |
| Email (optional, if you provide it) | Account recovery, notifications | Bot backend and VPN panel |
| Hardware ID (HWID) | Device tracking in the VPN panel | VPN panel |
| OS version, device model, app version | HTTP headers when requesting subscription | VPN panel |
| Inbound and outbound traffic in bytes | Plan quota calculation | Bot backend and VPN panel |
| Connection IP address | Briefly — for VPN technical operation | VPN panel and VPN nodes |
| QR code image (mobile app only, on user request) | Linking a TV device via Google Code Scanner | On the device only, not sent to our servers |

## 3. What we do NOT collect

- VPN traffic content and DNS queries
- Browsing history of sites or apps
- Device location
- Contacts, SMS, calls
- Photos, files, media
- Biometric data
- Advertising identifiers

## 3.1. Android permissions and their purpose

| Permission | Purpose |
| --- | --- |
| `INTERNET`, `ACCESS_NETWORK_STATE` | Establishing the VPN tunnel and tracking network state |
| `BIND_VPN_SERVICE` | Using the system `VpnService` API to build the VPN tunnel |
| `FOREGROUND_SERVICE`, `FOREGROUND_SERVICE_SPECIAL_USE` | Keeping the VPN connection alive while the app is in the background |
| `POST_NOTIFICATIONS` | Showing the VPN status indicator. Notifications are **not used** for marketing, advertising, or analytics. |

The mobile version additionally uses the built-in **Google Code Scanner** module to link a TV device by scanning a QR code. The scanner runs locally; the app does not request `CAMERA` permission, and images are not stored or sent to our servers.

The deep link `tobevpn://auth_callback` is used only to return to the app after a successful Telegram authentication.

## 3.2. VPN service declaration

In accordance with Google Play policies for apps that use the `VpnService` API, we declare:

- VPN functionality is the **core, prominently advertised** feature of the app, not a side feature.
- `VpnService` is used **solely** to build a VPN tunnel from your device to our VPN nodes.
- We **do not modify** VPN traffic content, **do not inject** advertising, analytics, or trackers into it.
- We **do not redirect** user traffic to third parties for commercial purposes.
- We **do not use** `VpnService` as a library inside other apps.
- The VPN protocols are open source (XRay/Sing-box). The connection configuration is built solely based on your subscription.

## 4. Sharing with third parties

Data is shared only with the following processors required for the service:

- **Telegram** (telegram.org) — for authentication confirmation.
- **ToBeVPN server infrastructure** (bot, VPN panel, and VPN nodes) — for subscription delivery and VPN operation.
- **Payment processors** (Telegram Stars, Cryptomus) — handled on the Telegram bot side; the app does not receive card or wallet data.
- **Google Play** — for app distribution and in‑app purchases (if applicable).

We do not sell your data to advertisers and do not share it for marketing purposes.

## 5. Storage and deletion

Retention periods by data type:

| Data | Retention |
| --- | --- |
| Telegram ID, email, device name, HWID, device→account link | Until you delete the account or unlink the device |
| Subscription traffic counters | For the subscription period + up to 12 months in anonymized form for statistics |
| Server technical logs (IP, timestamps) | Up to 90 days |
| Financial and tax records of payments | Up to 5 years (regulatory requirement) |

The app's local database is encrypted (SQLCipher) and stays only on your device.

**How to delete your account:** see the dedicated [Account deletion](delete-account-en.html) page. Email requests are processed within 30 days.

Uninstalling the app clears local data but does not break the device→Telegram link on the server — use the deletion instructions for that.

## 6. Security

- All requests to our servers use HTTPS (TLS 1.2+).
- The local database is encrypted (SQLCipher).
- The server API uses token authentication.
- In the event of an incident posing a risk to the rights and freedoms of data subjects, we will notify affected users and the competent supervisory authority within the timeframes required by applicable law (for GDPR — within 72 hours of becoming aware, Art. 33–34).

## 7. Children

The service is not directed at:
- persons under **16** if you are located in the European Economic Area or another jurisdiction where this is the minimum age of consent for personal data processing;
- persons under **13** in other jurisdictions.

We do not knowingly collect data from minors. If you become aware that a child has provided personal data to us, please contact us and we will delete it.

## 8. Your rights

You have the right to:
- Request a copy of the data we hold about you
- Request correction of inaccurate data
- Request deletion of your data
- Withdraw consent to processing
- Receive your data in a machine-readable format (data portability)
- Object to processing

To exercise these rights, email the address below. We will respond within 30 days.

We **do not use** automated decision-making producing legal or similarly significant effects on the user, including profiling (Art. 22 GDPR).

## 9. EU/EEA users (GDPR)

If you are located in the European Union or EEA, GDPR applies to you.

- **Legal basis for processing:** performance of the VPN service contract (Art. 6(1)(b) GDPR) and our legitimate interest in protecting against abuse (Art. 6(1)(f) GDPR).
- **International data transfers:** our infrastructure is located outside the EEA. Data is transferred under your rights pursuant to Art. 49(1)(b) GDPR (performance of a contract).
- **Right to lodge a complaint:** you have the right to lodge a complaint with the data protection supervisory authority in your country of residence.
- **EU representative:** not appointed. The service is not primarily directed at EU users, but you may contact us directly via the email below.

## 10. California users (CCPA/CPRA)

If you are a California resident, CCPA/CPRA applies to you.

- **Categories of data collected:** see section 2 above (identifiers, technical data).
- **Purposes of processing:** see the "Purpose" column in section 2.
- **Sale and sharing of data:** we **do not sell** your personal data and **do not share it for advertising purposes** (no sale, no sharing for cross-context behavioral advertising).
- **Sensitive data:** we do not collect sensitive categories of personal data within the meaning of CPRA.
- **Your rights:** right to know, right to delete, right to correct, right to limit use of sensitive data (the last does not apply, as we do not collect such data). Requests via the email below.
- **Non-discrimination:** we will not deny service or degrade your experience for exercising these rights.

## 11. Changes to this policy

For material changes we will update the effective date and try to notify you in the app. The current version is always available at this URL.

## 12. Contact

Email: [iv.zai4k@gmail.com](mailto:iv.zai4k@gmail.com)
