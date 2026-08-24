# Amana Field Form
A lightweight, mobile-first web application designed for field agents to track sales leads, door knocks, and policy conversions offline without requiring server infrastructure or database hosting.
Not Made by Me, I hosted and upgraded it!

---

## Key Features
* **Offline-First Storage:** Data is stored directly in the device's local browser storage (`localStorage`) and cached using an inline Progressive Web App (PWA) Service Worker.
* **Zero Backend Required:** Runs as a static single-page application directly from any host.
* **Multi-Partner Support (Trios):** Allows agents to select up to two partners simultaneously for trio field work.
* **Dedicated Log History:** Full historical log review screen enabling agents to view, re-export, or delete past daily logs.
* **Smart Lead Suggestions:** Auto-suggests recently entered customer/house names via quick-fill chip buttons.
* **Exporting & Sharing:** Generates structured summary reports ready to copy or share directly to WhatsApp.
* **Persistent Configuration:** Remembers agent identity, daily zones, and team roster setup across sessions.

---

## My Contributions & Upgrades
* **Storage Engine Migration:** Replaced custom asynchronous `window.storage` calls with standard `localStorage` methods (`getItem`, `setItem`, `clear`).
* **Multi-Partner Workflow:** Expanded single-partner selection to support multi-select for up to two partners (trios).
* **Dedicated History (`scHistory`):** Built a full history review screen allowing agents to view past entries, share historical summaries directly to WhatsApp, copy text, or delete specific day logs.
* **Recent Name Auto-Suggestions:** Added a `recentNames()` function and rendered quick-fill chips under the name input for rapid lead entry.
* Fixed overlay issues by adjusting `#toast` z-index layering.

---

## Deployment
### Mobile Usage Guidelines
* **Browser Requirement:** Always open the link in the native system browser (Google Chrome on Android, Safari on iOS).
* **Avoid In-App Previewers:** Avoid using webview previewers (such as opening links inside WhatsApp or Telegram directly) as they may flush storage upon closing.
* **PWA Installation:** Tap **Add to Home Screen** in Chrome or Safari to run the application like a native app with full offline capabilities.

---

## Application Structure
### Screens & Views
| Screen | Description |
| --- | --- |
| **Setup (`⚙`)** | Configure team roster names, select active agent identity, and perform system resets.|
| **Add Lead (`＋`)** | Main entry form for logging leads, tracking door knock counts, selecting locations/zones, quick-filling names, and recording policy sales.|
| **Today (`☰`)** | View current day entries, review logged sales, and access historical logs.|
| **History** | Dedicated view for inspecting, re-exporting, sharing, or deleting specific past daily entries.|
| **Send (`➤`)** | Format today's or past days' collected data into plain text for WhatsApp sharing and supervisor reporting.|

---

## Export Format
Data exported via the **Send** or **History** tabs generates the following structured text format:
```text
Daily leads — [Agent Name] with [Partner's Name] — [YYYY-MM-DD]
Zone: [Zone ID]
Location: [Location Name]

[Customer Name], [Phone], [Product], [Location (If changed) — Note — Outcome]
...

Doors knocked: [Count]
Policy sold: [Customer Name] — [Product] — MVR [Amount]
```