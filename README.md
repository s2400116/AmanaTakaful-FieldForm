# Amana Field Form

A lightweight, mobile-first web application designed for field agents to track sales leads, door knocks, and policy conversions offline without requiring server infrastructure or database hosting.

---

## Key Features

* **Offline-First Storage:** Data is stored directly in the device's local browser storage (`localStorage`) and cached using a Progressive Web App (PWA) Service Worker.
* **Zero Backend Required:** Runs as a static single-page application directly from any host (e.g., GitHub Pages).
* **Exporting & Sharing:** Generates structured summary reports ready to copy or share directly to WhatsApp.
* **Persistent Configuration:** Remembers agent identity, daily zones, and team roster setup across sessions.

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
| :--- | :--- |
| **Setup (`⚙`)** | Configure team roster names, select active agent identity, and perform hard system resets. |
| **Add Lead (`＋`)** | Main entry form for logging leads, tracking door knock counts, selecting location/zones, and recording policy sales. |
| **Today (`☰`)** | View and manage current day entries, review sales, and inspect log history from previous days. |
| **Send (`➤`)** | Format today's or past days' collected data into plain text for WhatsApp sharing and supervisor reporting. |

---

## Export Format

Data exported via the **Send** tab generates the following structured text format:

```text
Daily leads — [Agent Name] with [Partner Name] — YYYY-MM-DD
Zone: [Zone ID]
Location: [Location Name]

[Customer Name], [Phone], [Product], [Location Override — Note — Outcome]
...

Doors knocked: [Count]
Policy sold: [Customer Name] — [Product] — MVR [Amount]