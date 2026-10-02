---
title: Privacy Policy — ToBeVPN
---

# ToBeVPN Privacy Policy

**Effective date:** July 13, 2026

[Русская версия](privacy.html)

ToBeVPN ("we", "the app") is a VPN service with apps for Android, Android TV and Windows. Phone/tablet and Android TV variants are distributed under the `com.tobevpn.app` application identifier; the Windows app is distributed through the Microsoft Store. This policy applies to all variants and describes what data we collect, why, and with whom we share it.

## Personal data database owner and operator

- **Owner and operator:** Individual Entrepreneur Ivan Zaichenko
- **Jurisdiction:** Republic of Kazakhstan
- **Applicable law:** [Law of the Republic of Kazakhstan On Personal Data and their Protection](https://adilet.zan.kz/eng/docs/Z1300000094)
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
| Email (optional, if you provide it) | Account recovery, notifications | Locally in an encrypted database (SQLCipher), bot backend, and VPN panel |
| Hardware ID (HWID) | Device tracking in the VPN panel | VPN panel |
| OS version, device model, app version | HTTP headers when requesting subscription | VPN panel |
| Inbound and outbound traffic in bytes | Plan quota calculation | Bot backend and VPN panel |
| Connection IP address | Briefly — for VPN technical operation | VPN panel and VPN nodes |
| QR code image (phone scans TV's QR, or TV renders a QR for the phone to scan) | Linking a TV device to your Telegram account | On the device only, not sent to our servers |

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

The Android TV version instead **renders a QR code locally** using the open-source ZXing library. The QR encodes a `https://t.me/<bot>?start=<auth_token>` URL that the user scans with their phone to complete Telegram sign-in. The TV app does not request `CAMERA` permission either; the image is generated and displayed entirely on the TV.

The deep link `tobevpn://auth_callback` (mobile only) is used only to return to the app after a successful Telegram authentication.

## 3.1.1. Windows app

The Windows app uses the built-in Windows VPN platform (`Windows.Networking.Vpn`, the `networkingVpnProvider` capability) and installs no network drivers or services. It sends the same kinds of data as listed above, with Windows equivalents:

| Data | Purpose |
| --- | --- |
| Windows installation ID (`MachineGuid`) as the hardware ID (HWID) | Linking the subscription to the device |
| Computer manufacturer and model, Windows version | Display in your devices list and HTTP headers when requesting subscription |

The app registers only its own VPN profile ("ToBeVPN") and does not read or change VPN profiles of other apps. A connection starts only when you press the connect button.

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
- **Open Exchange Rates** (`open.er-api.com`) — public exchange-rate API used to show subscription prices in your local currency. Only your device's IP address is sent; no personal data.
- **Maven Central** (`repo1.maven.org`) — public repository used as the endpoint for the internet speed test. Only your device's IP address is sent; no personal data.
- **Google Play** — for app distribution and in‑app purchases (if applicable).

We do not sell your data to advertisers and do not share it for marketing purposes.

Some processors and VPN nodes may be located outside the Republic of Kazakhstan. This may involve a cross-border transfer of the personal data necessary to provide the service, where the user has consented or another basis permitted by applicable law exists.

## 5. Storage and deletion

Retention periods by data type:

| Data | Retention |
| --- | --- |
| Telegram ID, email, device name, HWID, device→account link | Until you delete the account or unlink the device |
| Subscription traffic counters | For the subscription period + up to 12 months in anonymized form for statistics |
| Server technical logs (IP, timestamps) | Up to 90 days |
| Financial and tax records of payments | For the period required by the laws of the Republic of Kazakhstan |

The app's local database is encrypted (SQLCipher) and stays only on your device.

**How to delete your account:** see the dedicated [Account deletion](delete-account-en.html) page. Request-processing periods are set out in section 8 below.

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

To exercise these rights, email the address below. Information about stored personal data, or a reasoned response, will be provided within **3 working days** after receipt of the request. If consent is withdrawn, processing will stop within **15 working days**, unless storage or processing is required by the laws of the Republic of Kazakhstan or an obligation remains unfulfilled; otherwise, a reasoned refusal will be provided.

Users may challenge actions or omissions relating to personal data processing before the competent authority of the Republic of Kazakhstan or a court. Where GDPR applies to a request, its requirements and time limits also apply.

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
