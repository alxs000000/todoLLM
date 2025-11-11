# Privacy Policy for LLM Todo Manager

_Last updated: 2025-11-12_

LLM Todo Manager (“the App”) is developed and maintained by Ryota Kando (“we”, “our”, “us”). This policy describes how we handle data when you use the App, its companion widget, and any related services (such as our Firebase backend and GitHub pages).

This document is intended for publication on GitHub (and optionally GitHub Pages) so that the same URL can be supplied inside the app’s **Settings** screen and on the App Store.

---

## 1. Data We Collect

| Category | Examples | Purpose | Linked? | Used for Tracking? |
| --- | --- | --- | --- | --- |
| **App settings & preferences** | Theme, language override, notification toggle, task retention setting, day-start time | Persist your personalized experience across launches and between the app and widget | No | No |
| **Todo content** | Task titles, notes, icons, deadlines, completion status, completion history | Core functionality: managing todos, syncing with the Focus Today widget, generating statistics | No | No |
| **Voice & transcription data** | Microphone input, intermediate speech-recognition transcripts | Converting spoken commands into todos | No | No |
| **Firebase identifiers** | Anonymous Firebase Authentication UID, temporary App Check tokens | Authenticate securely with our Firebase Functions endpoint and prevent abuse | No | No |
| **AI prompts** | The text you send to the in-app assistant, including the last few turns of conversation | Generate todos through our Firebase-hosted Gemini integration | No | No |

We do **not** collect contact information, payment data, precise location, or advertising identifiers. We also do not use data for cross-app tracking.

## 2. How Data Is Stored

- **On-device:** Todos, settings, and statistics are stored in Core Data and `UserDefaults` inside the App Group container shared with the widget.
- **Remote services:** When you invoke the AI assistant, your prompt (and the recent conversation context) plus an anonymous Firebase UID are transmitted via HTTPS to our Firebase Cloud Functions endpoint hosted in the `asia-northeast1` region. The function forwards the prompt to Google’s Gemini API, receives structured todos, and returns them to the device. We do not build long-term profiles or analytics from this traffic.

## 3. Third-Party Services

| Service | Purpose | Shared Data |
| --- | --- | --- |
| **Firebase Authentication (Google LLC)** | Provides anonymous auth so each device has a stable, non-personal identifier | Anonymous UID only |
| **Firebase App Check (Google LLC)** | Issues attestation tokens so only legitimate app instances reach our backend | Device/app integrity signal, no user data |
| **Firebase Cloud Functions (Google LLC)** | Hosts the `generateTodos` callable function that formats prompts for Gemini and returns structured todos | Anonymous UID + prompt payload |
| **Google Gemini API** | Converts natural language prompts into todo lists | Prompt text (may include user-generated todo descriptions) |

Each provider processes data under its own privacy policy; however, we only transmit what is needed for the features you request.

## 4. Data Retention & Deletion

- **On-device data** remains until you delete it via the Settings screen (“Clear All”, “Purge Completed Todos”, or “Reset Statistics”) or uninstall the app.
- **AI prompts on Firebase** are logged temporarily for debugging and are automatically removed after 30 days.
- We retain no server-side backups that could re-identify you once the retention period ends.

## 5. Security

- All communications with Firebase and Gemini occur over TLS.
- App Check ensures only valid builds interact with the backend.
- Anonymous authentication avoids storing any personal identifiers.

## 6. Your Choices

- **Notifications & microphone access:** Managed through iOS settings and the in-app toggles.
- **Data deletion:** Use the actions under _Settings ▸ Data Management_.
- **Opting out of AI:** You can use the app purely as a manual todo list without invoking the assistant.

## 7. Children’s Privacy

The App is not directed to children under 13. We do not knowingly collect personal information from children. If you believe a child has provided us data, please contact us so we can delete it.

## 8. Updates to This Policy

We may revise this policy as Apple, Firebase, or regulatory requirements evolve. The “Last updated” date at the top reflects the latest version. Significant changes will be highlighted in the GitHub repository and via release notes.

## 9. Contact

For privacy questions or requests, please email: **ryouta20040817@gmail.com**

---

### 日本語での概要

- アプリは設定やタスク情報を端末内（App Group コンテナ）に保存します。
- 音声入力や AI 生成依頼時に送信されるテキスト／音声は、機能提供のためにのみ Firebase／Gemini へ送信されます。
- 収集データは個人と紐付けておらず、トラッキング目的では利用しません。
- データ削除は設定画面の「データ管理」から実行できます。

詳細は上記の英語版本文をご確認ください。
