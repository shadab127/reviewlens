# Privacy Policy — ReviewLens

**Last updated: 2026-04-21**

**Contact: reviewlens.support@gmail.com**

---

## What ReviewLens Does

ReviewLens is a Chrome extension that reads product reviews from Amazon and Steam, sends them to the Google Gemini AI API for summarization, and displays a structured summary (pros, cons, common complaints, and a verdict) directly on the product page.

---

## What Data Leaves Your Browser

**Review text is sent to Google Gemini.**

When you click "Summarize Reviews", the extension collects review text from the current Amazon or Steam page and sends it to the Google Gemini API (`generativelanguage.googleapis.com`) for summarization. This review text is user-generated content from the product page — it is not your personal data, your name, your location, or any information about you.

Your Gemini API key is transmitted as an HTTP request header (`x-goog-api-key`) on that same call — solely to authenticate the request with Google. It is never sent anywhere else.

No other data leaves your browser.

---

## What Is Stored Locally

All storage is in your browser's local extension storage (`chrome.storage.local`) and never leaves your device:

- **Your Gemini API key** — stored after you save it in Settings. Displayed masked (last 4 characters only). Cleared when you click "Clear Key".
- **Cached summaries** — the AI-generated summary for a product is cached locally (keyed by ASIN or Steam App ID, not by URL). Cache entries expire after 24 hours and are evicted automatically when storage exceeds 5 MB. Raw review text is **never** persisted — only the final summary is cached.
- **Local usage counters** — counts of summaries generated, cache hits, and scrape success/failure rates. These are displayed in the extension popup. They are stored only on your device and never transmitted anywhere.
- **Error log** — a short rolling log of the last few error types (e.g. "network_error", "invalid_api_key") and the hostname where they occurred. Stored locally, never transmitted.

---

## What Is Not Collected

- No personal information is collected.
- No browsing history is collected.
- No data is sent to any server operated by the extension developer.
- No data is sold or shared with third parties.
- No analytics, telemetry, or crash reporting services are used.
- No advertising or tracking of any kind.

---

## Third-Party Services

The only external service this extension communicates with is:

- **Google Gemini API** (`generativelanguage.googleapis.com`) — to generate summaries. Google's privacy policy applies to data processed by Gemini: https://policies.google.com/privacy

The extension also attempts to fetch a remote selector configuration from GitHub Pages once per 24 hours. This fetch contains no user data — it is a plain HTTP GET request for a JSON configuration file used to keep Amazon/Steam CSS selectors up to date without requiring an extension update. If the fetch fails, the extension silently falls back to the selectors bundled inside the extension package.

---

## Your Control

- You can clear all cached summaries at any time via the Settings page.
- You can remove your API key at any time via the Settings page.
- Uninstalling the extension removes all locally stored data.

---

## Changes to This Policy

If this policy changes materially, the updated version will be posted at the same URL. The "Last updated" date at the top will reflect the change.

---

## Contact

Questions or concerns: **reviewlens.support@gmail.com**
