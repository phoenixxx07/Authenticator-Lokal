# Privacy Policy for Authenticator Lokal

**Last Updated:** October 12, 2026

**Authenticator Lokal** ("the Extension") is committed to protecting your privacy. This Privacy Policy explains our practices regarding user data, permissions, and security.

---

## 1. Zero Data Collection & Offline Operation

* **No Remote Data Transmission:** The Extension operates 100% locally within your Google Chrome browser. It does not transmit any information to external servers, cloud storage, or third-party services.
* **No Telemetry or Tracking:** The Extension contains zero telemetry, analytics, tracking pixels, or third-party monitoring libraries.
* **Network Enforced Policy:** The Extension enforces a strict Content Security Policy (`connect-src 'none'`), technically preventing outbound network connections from the extension pages.

---

## 2. Local Data Storage & Encryption

* **Master Password & Web Crypto API:** All your 2FA credentials (OTP seeds, accounts, and labels) are encrypted locally using industry-standard **AES-GCM 256-bit** encryption with keys derived via **PBKDF2 (SHA-256, 100,000 iterations)**.
* **Storage Location:** Encrypted vaults are stored strictly on your local device via `chrome.storage.local`. The unencrypted master password is never stored on disk.
* **Session Security:** Temporary decryption keys in RAM are automatically cleared after an inactivity timeout (auto-lock).

---

## 3. Chrome Permissions Usage

* **`storage`**: Used solely to persist your encrypted vault locally on your device.
* **`alarms`**: Used exclusively to trigger the idle auto-lock countdown timer to lock the vault.
* **`activeTab`**: Used to identify the hostname of your currently active tab so that matching 2FA accounts can be suggested when you interact with the extension.
* **Host Permissions (`https://*/*`) & Content Scripts**: Used strictly to detect one-time password input elements (`autocomplete="one-time-code"`) on HTTPS login pages. The content script operates passively:
  * It **does not** read passwords, usernames, or text entered in other form fields.
  * It **does not** record keystrokes (no keylogger).
  * It **does not** send DOM content off your device.
  * OTP codes are only injected when you deliberately click the autofill action.

---

## 4. Third-Party Disclosures & Data Sharing

* We do not sell, rent, trade, or transfer any user data to third parties.
* We do not use user data for creditworthiness or advertising purposes.

---

## 5. Contact & Open Source Verification

The source code and cryptographic implementation can be reviewed directly in the extension bundle or repository:
* **Repository:** [https://github.com/phoenixxx07/Authenticator-Lokal](https://github.com/phoenixxx07/Authenticator-Lokal)
* **Developer:** phoenixxx07
