# DuoDiary Legal & Support

Support portal, terms of use, and privacy policy sources for **DuoDiary** (`app.duodiary.ios`).

Hosted via GitHub Pages at: `https://gitmaster25.github.io/duodiary-legal/`

Local copy updated October 2, 2026. Editing this directory does not publish the legal website or apply App Store Connect metadata. Verify the published pages and CloudKit Production permissions separately before release.

---

## 📱 App Store Connect Configuration

| Field in App Store Connect | Intended Value | Purpose |
| :--- | :--- | :--- |
| **Support URL** (Required) | `https://gitmaster25.github.io/duodiary-legal/` | Guideline 1.5: Direct contact info, email link, and FAQs |
| **Marketing URL** (Optional) | *(Leave empty)* | Not required |
| **Privacy Policy URL** (App Privacy Section) | `https://gitmaster25.github.io/duodiary-legal/privacy` | Guideline 5.1.1: Complete data collection, retention, deletion disclosure |
| **Terms of Use (EULA)** | `https://www.apple.com/legal/internet-services/itunes/dev/stdeula/` | Apple Standard EULA; local `/terms` supplements it with content and safety rules |

---

## 🛡️ Zero-Tolerance Policy (Apple Guideline 1.2)

DuoDiary prohibits objectionable content and abusive behavior. Its implemented safety controls are in-app CloudKit reports, participant blocking, removal from owned books, and leaving partner-owned shares. The developer cannot directly inspect or erase another person's private iCloud memories, and no developer-wide permanent account-ban service has been established. Apple requires timely responses; a fixed 24-hour response guarantee is not documented.

Reports go to `DDAbuseReport` in the public CloudKit database for developer review in CloudKit Console. They contain book/reporter identifiers, category, optional details and offender identifier, status, and timestamps, with no automatic photo/page/journal attachments. Runtime app clients create reports without report-read rights. Reports and support messages are retained only as needed for handling, abuse prevention, or legal obligations; users can request deletion through the support address.

Minimal `DDContributorRemovalMarkerV3` records are separate from reports. Each uses a 256-bit unguessable per-contributor/book lookup identifier and contains only a removal flag in app fields. CloudKit adds creator and timestamp metadata. Authenticated clients holding the lookup key can fetch a marker directly; DuoDiary shares the key through private/shared topology with invited participants. The app has no browsing/list feature. Markers may remain after account deletion to prevent resurrection. Account-generation, contribution-directory, and other private cleanup records remain in the user's private CloudKit database as described in the policy.

---

## 📬 Contact & Support

- **Email**: [duodiaryadmin@gmail.com](mailto:duodiaryadmin@gmail.com)
- **Direct Mail Link**: [Contact Support](mailto:duodiaryadmin@gmail.com?subject=DuoDiary%20Support)

---

## 🗂 Repository Structure

```text
├── .nojekyll           # Static GitHub Pages content
├── index.html          # Main Support & Help Center (Root URL: /)
├── support.html        # Support page (/support), kept consistent with index.html
├── privacy.html        # Official Privacy Policy (/privacy)
├── terms.html          # Terms of Use with Zero-Tolerance clause (/terms)
└── README.md           # Documentation & App Store Connect reference
```
