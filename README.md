# Premium Guitar Playable Ad - Learn Guitar (Happy Birthday)

A high-fidelity, highly interactive, and responsive Playable Ad built for mobile advertising networks, fully compatible with **Unity Ads (MRAID)** and **Mintegral**.

## 🎮 Core Features

*   **Vibrant Cyber-Neon Visuals**: High-end styling with ambient radial glows, floating background music particles, and neon highlight borders.
*   **Multi-Color Interactive Strings**: Each guitar string glows with its own unique neon shade and vibrates physically via CSS animations when plucked.
*   **Dynamic Note Orbs**: Large, responsive, color-coded touch targets corresponding to specific notes (e.g. Cyan for G4, Pink for C5) with visual ripple and sparkling star physics on tap.
*   **HTML5 Canvas Fireworks**: A custom high-performance particle firework system triggered upon completing the song.
*   **Hybrid SDK Integration**: Injected MRAID script with active state listeners:
    *   Tracks advertisement focus changes via global `window.gameStart()` and `window.gameClose()` to automatically play/suspend audio.
    *   Fires `window.gameReady()` on startup and `window.gameEnd()` on finishing.
    *   Redirects CTA click through `window.install()` or `mraid.open(STORE_URL)` depending on the network context.

---

## 📁 Repository Structure

```
├── data/
│   ├── index.html            # The final, single-file self-contained playable ad (Dist)
│   ├── index_template.html   # Source HTML template (clean source code)
│   ├── assets_base64.js      # Automatically generated base64 strings of assets
│   ├── img_logo_app.webp     # Application WebP logo
│   └── tuned_*.wav           # Raw audio tracks for the guitar strings
├── .gitignore                # Git ignore files
└── README.md                 # Project documentation
```

---

## 🛠️ Assets Merging (Build Process)

If you modify the raw WAV files, logo, or the source template (`data/index_template.html`), you can rebuild the final single-file advertisement using Python:

1. **Re-encode Assets to Base64**:
   Run a script to update `data/assets_base64.js` with your new assets.
2. **Merge Assets with Template**:
   Replace the placeholder `/* INSERT_BASE64_ASSETS */` in `index_template.html` with the contents of `assets_base64.js` and write to `index.html`.
