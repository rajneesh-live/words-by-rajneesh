<p align="center">
  <img src="icon.svg" alt="Osho Discourses Icon" width="128" height="128">
</p>

<h1 align="center">Osho Discourses Offline Reader</h1>

<p align="center">
  A lightning-fast, privacy-first Progressive Web App (PWA) to search, explore, and read thousands of Osho discourses completely offline.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/PWA-Enabled-orange.svg" alt="PWA Enabled">
  <img src="https://img.shields.io/badge/Offline-IndexedDB-blue.svg" alt="Offline IndexedDB">
  <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License MIT">
</p>

---

## 🌟 Key Features

- ⚡ **Instant Full-Text Search:** Query across thousands of discourses in real-time right inside your browser.
- ✈️ **100% Offline Capability:** Download once, read anywhere. Uses `IndexedDB` and WebAssembly (`brotli-wasm`) to decompress and cache the database locally.
- 📱 **Installable PWA:** Install directly to your iOS/Android home screen or desktop. Uses smart prompting—the install option appears seamlessly after your first reading session.
- 🎯 **Context Highlighting & Keyword Navigation:** Effortlessly jump between keyword matches using a integrated capsule control UI.
- 🧭 **Native Mobile Gestures:** Fully supports Android back buttons, browser history, and swipe navigation.
- 💾 **Export Research:** Download search snippets or full discourses as `.txt` files directly to your device.
- 📚 **Explore & Browse:** Search by specific master, popular themes (Zen, Tantra, Meditation, Buddha), or browse full books.

---

## 🛠️ How It Works (Architecture)

1. **First-Time Load:** The app fetches a highly compressed dataset (`discourses.ndjson.br`) from GitHub.
2. **In-Browser Decompression:** Decompresses the data client-side using `brotli-wasm` without needing a backend server.
3. **Local Storage:** Saves the full text database into the browser's native `IndexedDB`.
4. **Service Worker (`sw.js`):** Caches the application shell (HTML, manifest, icons) so the app works seamlessly without an internet connection.

---

## 📁 Repository Structure

```text
├── index.html       # Single-Page Application (UI, Logic, DB Manager)
├── sw.js            # Service Worker for offline asset caching
├── manifest.json    # Web App Manifest for PWA installation
├── icon.svg         # High-resolution vector app icon
└── README.md        # Project documentation