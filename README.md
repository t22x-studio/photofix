# Photo Helper 📷

A fully offline, privacy-first browser-based photo editor. No uploads, no server, no account. Your photos never leave your device.

**[→ Open Photo Helper](https://t22x-studio.github.io/photofix/)**

---

## Features

**Adjustments**
- Light: Brightness, Contrast, Highlights, Shadows, Exposure
- Colour: Warmth, Tint, Saturation, Red, Green, Blue, Hue Shift
- Detail: Clarity, Sharpen, Fade, Grain
- Effects: Blur, Vignette
- Tonal: Levels (Black point, Gamma, White point)

**Filters**
- Oil Paint, Watercolor, Anime, Bright, B&W, Noir, Sketch, Comic, Pixel, Pixel Game
- Filter strength slider (0–100%)
- Pixel filters: adjustable palette size (8 / 16 / 32 / 64 / Full colours)

**Tools**
- Crop with drag handles + arrow key fine-tune + Escape to cancel
- Flip horizontal
- Rotate 90° clockwise (cycle)
- Frame: external (shrinks photo to fit) or internal (overlays on edges), colour picker, 0–15%
- Aspect ratio pad: 1:1, 4:5, 2:3, 3:4, 3:2, 4:3, 16:9, 9:16

**Export**
- PNG (lossless) or JPG (quality slider 80–100%, default 92%)
- Export sizes: 1080px / 2048px / Full resolution / Custom px
- EXIF metadata preserved on JPG export (toggle to strip)
- Auto-generated filename: `IMG_0281_oilpaint_2048_edit.jpg`
- Editable filename field before export
- JSON settings export/import for batch consistency

**Workflow**
- Undo / Redo — Multiple steps (Cmd/Ctrl+Z, Cmd/Ctrl+Shift+Z)
- Before/After toggle — press `\` or tap and hold
- LocalStorage: remembers last slider settings between sessions
- RGB Histogram with level markers
- Zoom 10–200% with click-drag pan
- Drag photo onto "Upload new" button to replace
- iOS Safari compatible export

---

## Privacy

- 100% client-side — no data sent anywhere
- No analytics, no tracking, no cookies
- Works fully offline after first page load
- EXIF GPS data is included in EXIF-keep mode — toggle EXIF off if you want to strip location

---

## Usage

**Online (GitHub Pages):** Open the link above in any modern browser.

**Offline / Local:** Download `index.html` → open directly in Chrome, Firefox, or Safari. No server needed.

**Mobile:** Works on iOS Safari and Android Chrome. For best experience on iPhone, use landscape orientation for the editing panel.

---

## Known Limitations

- EXIF preserved on JPG export only (PNG export strips metadata — this is a browser canvas limitation)
- Oil Paint filter at full export resolution on large photos (4032px+) may take 5–10 seconds — this is expected
- Pixel filters work best on photos with simple subjects and clear backgrounds
- Crop selection box may appear slightly offset at zoom below 75% — cosmetic only, crop applies correctly

---

## Keyboard Shortcuts

| Key | Action |
|---|---|
| `\` | Toggle before / after |
| `Cmd/Ctrl + Z` | Undo |
| `Cmd/Ctrl + Shift + Z` | Redo |
| `Escape` | Cancel crop |
| Arrow keys | Nudge crop selection |

---

## Tech

Single `.html` file. Vanilla JS, Canvas 2D API, Web Audio API. Zero dependencies, zero frameworks, zero CDN calls.

---

*Built for photographers who want a fast, private, offline-capable editing tool for quick edits on the go.*
