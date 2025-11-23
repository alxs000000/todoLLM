# Privacy Policy for LLM Todo Manager

_Last updated: 2025-11-23_

LLM Todo Manager (the “App”) is provided by Ryota Kando (“we”, “our”, “us”). This notice describes what data we collect, how we use it, where it flows (including Firebase and Google Gemini), and the controls available to you.

This document is intended to be shown in the App Store listing and inside the app (Settings ▸ Privacy Policy).

---

## 1. Data We Collect and Why

| Category | Examples | Purpose | Linked to you? | Used for tracking? |
| --- | --- | --- | --- | --- |
| App settings & preferences | Theme, language override, notification toggle, day-start time, task retention | Persist your customization across launches and in the widget | No (stored locally) | No |
| Todo content | Task titles, notes, deadlines, icons, completion status, completion history | Core functionality: manage tasks, show stats, power the widget | No (stored locally) | No |
| Voice input & transcription | Microphone audio and temporary speech-to-text results | Convert spoken instructions into todos | No (processed for the request only) | No |
| AI prompts | Text you send to the assistant and a short recent history | Generate todos via our Gemini-based assistant | No (sent with anonymous UID) | No |
| Anonymous identifiers | Firebase anonymous UID; App Check attestation token | Authenticate requests and protect the backend from abuse | Not linked to personal identity | No |
| Purchase state | In-app purchase transactions managed by Apple | Determine subscription entitlement | Handled by Apple; we store only a boolean flag | No |

We do **not** collect contact information, precise location, advertising identifiers, or analytics profiles. We do not use data for cross-app or cross-site tracking.

## 2. Where Data Is Stored and Processed

- **On-device (App Group container):** Todos, settings, completion stats, and notification preferences are saved locally using Core Data and UserDefaults. The widget reads from the same container.
- **Firebase (Google LLC):** When you use the assistant, we send your prompt, recent conversation context, and anonymous Firebase UID over HTTPS to a Callable Cloud Function in the `asia-northeast1` region. App Check ensures the caller is a legitimate app build.
- **Google Gemini API:** Our Cloud Function forwards the prompt to Gemini and returns structured todos. We do not attach names, emails, or advertising IDs.
- **Speech recognition:** Performed via Apple’s Speech framework. Audio and intermediate transcripts are used only to produce text for your request.
- **Payments:** Subscriptions are processed by Apple. We do not receive card numbers or billing addresses; we only store whether a purchase is active.

## 3. Third-Party Services

| Service | Purpose | Data shared |
| --- | --- | --- |
| Firebase Authentication | Issue an anonymous UID per device/session | Anonymous UID |
| Firebase App Check | Attestation to block modified/abusive clients | Integrity token |
| Firebase Cloud Functions | Host the `generateTodos` endpoint | Prompt text + anonymous UID |
| Google Gemini API | Convert natural language into structured todos | Prompt text |
| Apple Speech framework | Convert voice to text | Audio stream & transcripts for the request |
| Apple In‑App Purchase | Manage subscriptions | Transaction metadata handled by Apple |

Each provider processes data under its own privacy policy. We transmit only what is required to deliver the requested feature.

## 4. Data Retention & Deletion

- **On-device data:** Remains until you delete it via Settings (e.g., “Clear All Todos”, “Reset Statistics”) or uninstall the app.
- **Assistant prompts:** Stored transiently in Firebase logs for reliability/abuse investigation and auto-deleted within 30 days. We do not build user profiles from prompts.
- **Speech input:** Held only for the duration of recognition; not stored by us.
- **Purchase state:** The local subscription flag can be cleared by deleting the app.

## 5. Security Measures

- All network traffic to Firebase and Gemini uses TLS.
- Firebase App Check limits backend access to valid app builds.
- Anonymous auth avoids collecting personally identifiable information.
- Local data is stored in the app sandbox / App Group container.

## 6. Your Choices and Controls

- **Notifications, Microphone, Speech Recognition:** iOS permission prompts and system Settings control access. The app only functions with microphone/speech when you explicitly allow it.
- **Manual use without AI:** You can create and manage todos entirely offline without invoking the assistant.
- **Data deletion:** Use in-app options under Settings ▸ Data Management to clear todos and stats; uninstall the app to remove all local data.

## 7. Children’s Privacy

The App is not directed to children under 13. We do not knowingly collect personal information from children. If you believe a child has provided data, contact us to request deletion.

## 8. Changes to This Policy

We may update this policy to reflect product or regulatory changes. The “Last updated” date will change, and significant updates will be noted in release notes.

## 9. Contact

For privacy questions or requests, email: **ryouta996445@gmail.com**
　
---
