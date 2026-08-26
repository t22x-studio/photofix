# Photo Helper 📷

[English](#english) | [繁體中文](#繁體中文)

---

## English

A lightning-fast, privacy-first, web-based photo editor that runs **100% in your browser**. No AI hype, no server uploads, no cloud tracking, and no ads.

👉 **[Live Demo / Launch App](https://t22x-studio.github.io/photofix/)**

### ✨ Key Features
*   🔒 **Absolute Privacy:** 100% client-side. Your photos never leave your device. Works completely offline.
*   📥 **Flexible Photo Import:** Drag-and-drop images anywhere or use the standard file picker for seamless mobile and desktop workflows.
*   🎨 **Selective Color Pop (Two-Way Isolation):**
    *   Target any color with the live canvas eye-dropper.
    *   **Pop Slider (-100 to +100):** Boost saturation of the chosen color or selectively mute/desaturate it down to grey.
    *   **Background Saturation (-100 to +100):** Desaturate the background to black-and-white (selective color) or boost background vibrancy while protecting subject skin tones.
*   🖼️ **Artistic Filters:** Includes adjustable-strength **Watercolor**, **Oil Paint**, Anime, Sketch, Comic, Color Comic, B&W, and Noir filters.
*   👾 **8-Bit Retro Pixel Game:** Configurable palette sizes (8 / 16 / 32 / 64 / Full) with optional CRT sprite grid lines.
*   🎛️ **Full Tuning Suite & DSP:**
    *   **Surface Smooth:** Edge-preserving spatial filter for skin smoothing, blemish cleanup, and noise removal.
    *   Brightness, Contrast, Highlights, Darkness (Shadows), Saturation, Warmth, Red, Green, Blue, Tint, Clarity, Blur, Fade, Vignette, and Grain.
    *   Logarithmic RGB + Luminance live histogram with **Auto Levels** and interactive Black Point, Midtones (Gamma), and White Point controls.
*   📐 **Pro Layouts & Framing:**
    *   Interactive crop with Apple-style corner handles, snap-to-boundary logic, and arrow key fine-tuning.
    *   Non-destructive **Border Padding (0–20%)** with color picker and aspect ratio presets (Original, 1:1, 4:5, 2:3, 3:2, 16:9, 9:16).
    *   90° clockwise rotation and horizontal flipping.
    *   High-contrast checkerboard Frame Mode canvas toggle.
*   💾 **Smart EXIF & High-Res Export:**
    *   Export as JPG (80–100% quality) or lossless PNG.
    *   Scaling: 1080px / 2048px / Full Original Resolution / Custom px on long edge (with stepped sharp upscaling).
    *   Preserves camera EXIF metadata on JPG export with surgical binary orientation tag correction (toggle to strip metadata for privacy).
    *   Dynamic smart filename generation with editable field.
    *   Save and load `.json` adjustment presets for consistent batch editing.
*   ⚡ **Workflow & Navigation:**
    *   **Bilingual Interface:** Instant one-click toggle between **English** and **Traditional Chinese (繁體中文)**.
    *   **Desktop Quick-Jump Tabs:** Smooth-scrolling navigation bar on desktop screens.
    *   **Hold to Peek:** Hold `\` on keyboard, click & hold on desktop, or touch & hold on mobile to view the unedited original.
    *   **Deep Undo / Redo:** Full history tracking across non-destructive adjustments, crops, flips, rotates, and canvas settings (preserves zoom level on adjustment undos).
    *   **Fast-Path Interaction:** Zero-lag responsive adjustment sliding with high-precision background DSP commit on release.
    *   Viewport zoom (10–200%) with single-touch/click-drag panning.
    *   Session memory: Remembers last slider settings via LocalStorage.

### 🚀 Quick Start
No installation. No build steps. No node_modules.
1. Download the `index.html` file.
2. Double-click it to run it locally in any modern browser (Chrome, Safari, Firefox, Edge).

### 🛠️ Technical Architecture (For Developers)
This entire application is self-contained within a **single `index.html` file** with **zero external dependencies** (no CDN, no frameworks, no libraries). High performance is achieved via raw CPU mathematical optimization:
*   **Engine:** Built on the HTML5 Canvas 2D API using direct pixel buffer manipulation (`ImageData` / `Uint8ClampedArray`). No WebGL or GPU shaders required.
*   **O(1) Look-Up Tables (LUTs):** 256-entry precomputed integer arrays for lightning-fast gamma, levels, and contrast curves.
*   **Separable 2-Pass Blurs:** Linear $O(N)$ box blurs that process horizontal and vertical passes separately, avoiding slow $O(N \times R^2)$ 2D matrix convolutions.
*   **Interaction Decoupling:** Heavy algorithms (like Surface Smoothing) decouple during active slider dragging, rendering fluidly via `requestAnimationFrame` and committing full-precision DSP calculations on slider release.
*   **Zero-Floating-Point Overhead:** Uses squared color distances to eliminate heavy `Math.sqrt` calls and implements bitwise integer luminance calculations: `((r*77 + g*150 + b*29) >> 8)`.
*   **Custom Binary EXIF Engine:** Built with a handcrafted binary parser operating directly on raw `Uint8Array` / `ArrayBuffer` byte streams to parse JPEG APP1 markers and surgically handle EXIF data.

### ⌨️ Keyboard Shortcuts

| Key | Action |
|---|---|
| `\` (Hold) | View original unedited photo (Release to view edited) |
| `Cmd / Ctrl + Z` | Undo |
| `Cmd / Ctrl + Shift + Z` or `Cmd / Ctrl + Y` | Redo |
| `Arrow Keys` | Nudge crop selection (1px step) |
| `Shift + Arrow Keys` | Nudge crop selection (10px step) |
| `Escape` | Cancel active crop |

### 📄 License
This project is open-source and protected under the **MIT License**.

---

## 繁體中文

一個極速、隱私安全、基於網頁的相片編輯器，**100% 在您的瀏覽器本地運行**。無 AI 炒作、無伺服器上傳、無雲端追蹤、零廣告。

👉 **[線上立即使用](https://t22x-studio.github.io/photofix/)**

### ✨ 核心特性
*   🔒 **絕對隱私:** 100% 客戶端本地運行。您的相片永遠不會離開您的裝置，完全支援離線使用。
*   📥 **彈性匯入機制:** 支援拖放相片至視窗任意處或點擊「開啟」選取檔案，完美適配手機與桌面端操作。
*   🎨 **色彩突出 (雙向色彩隔離):**
    *   使用即時畫面滴管／取色器精準鎖定任意目標色相。
    *   **色彩突出滑桿 (-100 至 +100):** 可增強選定顏色的飽和度，或反向將選定顏色單獨去色為灰階。
    *   **背景飽和度 (-100 至 +100):** 可將背景去色為黑白（單色留彩效果），或在增強背景風景色彩的同時保護主體人物膚色不偏色。
*   🖼️ **藝術濾鏡:** 內建支援強度調節的 **水彩風**、**油畫風**、動畫風、素描風、漫畫風、彩色漫畫風、灰階及黑白濾鏡。
*   👾 **8-Bit 復古像素遊戲風:** 支援可選調色盤色彩數（8 / 16 / 32 / 64 / 全彩）與復古格線效果。
*   🎛️ **全功能參數微調 & DSP 處理:**
    *   **表面平滑 (Surface Smooth):** 邊緣保留空間濾波技術，專用於平滑膚質、去除瑕疵與濾鏡噪點。
    *   亮度、對比、高光、陰影、飽和度、色溫、紅、綠、藍、色調 (Tint)、清晰度、模糊、褪色、暈影與粗糙顆粒感。
    *   對數 RGB + 亮度即時直方圖，配備 **自動色階** 及互動式黑點、中間調 (Gamma)、白點控制。
*   📐 **專業裁切與版面設計:**
    *   專業級裁切手柄，具備邊界吸附邏輯與方向鍵微調（支援 Shift 鍵 10px 步進）。
    *   非破壞性 **邊框邊距 (0–20%)** 與取色盤，支援標準比例（原始、1:1、4:5、2:3、3:2、16:9、9:16）。
    *   90° 順時針旋轉與水平翻轉。
    *   高對比棋盤格邊框預覽模式切換。
*   💾 **智慧 EXIF 與高解析度匯出:**
    *   支援匯出為 JPG（畫質 80–100%）或無損 PNG。
    *   尺寸選擇：1080px / 2048px / 原始完整解析度 / 自訂長邊像素（內建多階銳利升採樣演算法）。
    *   JPG 匯出時完整保留相機 EXIF 中繼資料並精確修正方向標記（可隨時切換關閉以保護個人隱私）。
    *   智慧動態檔名生成與手動自訂命名欄位。
    *   支援儲存與載入 `.json` 調色預設檔案。
*   ⚡ **工作流與介面:**
    *   **雙語介面:** 一鍵即時切換 **English** 與 **繁體中文**。
    *   **桌面快速導覽標籤:** 桌面端頂部導航列支援平滑捲動至各調整區塊。
    *   **即時修改前預覽:** 電腦端按住 `\` 鍵或按住圖片，手機端長按圖片即可查看未修改原圖。
    *   **深度復原 / 重做:** 支援跨幾何裁切、旋轉、翻轉與滑桿調整的完整歷史紀錄（調整滑桿時復原不重設縮放視野）。
    *   **流暢無延遲互動:** 滑桿拖動時採用快速路徑渲染，釋放滑桿時沉澱高精度 DSP 運算。
    *   10–200% 視圖縮放與單指/點擊拖曳平移。
    *   本機記憶：透過 LocalStorage 自動記住上次編輯參數。

### 🚀 快速開始
無需安裝，無需任何建置步驟，無 `node_modules`。
1. 下載 `index.html` 檔案。
2. 雙擊檔案即可在任何現代瀏覽器（Chrome、Safari、Firefox、Edge）中直接本機執行。

### 🛠️ 技術架構 (面向開發者)
整個應用完全濃縮在**單個 `index.html` 檔案**中，**零第三方依賴**（無 CDN、無框架、無外部函式庫）。高效能純靠原生的 CPU 數學演算法最佳化實現：
*   **渲染引擎:** 基於 HTML5 Canvas 2D API，直接操作像素緩衝區 (`ImageData` / `Uint8ClampedArray`)，無需 WebGL 或 GPU 著色器。
*   **O(1) 查找表 (LUT):** 採用 256 項預計算整數陣列，讓每像素的 Gamma、色階與對比度曲線計算變成瞬間完成的陣列查找。
*   **可分離雙通道模糊:** 線性 $O(N)$ 複雜度的方框模糊演算法，將水平與垂直通道拆開處理，避開了傳統 $O(N \times R^2)$ 慢速二維矩陣卷積。
*   **互動行為解耦:** 拖動滑桿時自動解耦高負載演算法（如表面平滑），優先利用 `requestAnimationFrame` 保證 UI 流暢渲染，釋放滑桿時再執行高精度 DSP 處理。
*   **規避浮點開銷:** 使用平方色彩距離消除高耗能的 `Math.sqrt` 呼叫，並採用位移整數亮度計算：`((r*77 + g*150 + b*29) >> 8)`。
*   **原生二進位 EXIF 引擎:** 直接在原始 `Uint8Array` / `ArrayBuffer` 位元組流上操作，解析 JPEG APP1 標記並精確控制 EXIF 數據的保留與寫入。

### ⌨️ 快捷鍵清單

| 按鍵 | 動作 |
|---|---|
| `\` (按住) | 查看未修改原圖（放開後返回編輯效果） |
| `Cmd / Ctrl + Z` | 復原 (Undo) |
| `Cmd / Ctrl + Shift + Z` 或 `Cmd / Ctrl + Y` | 重做 (Redo) |
| `方向鍵` | 1px 微調裁切選區 |
| `Shift + 方向鍵` | 10px 快速微調裁切選區 |
| `Escape` | 取消當前裁切模式 |

### 📄 開源協議
本專案基於 **MIT License** 開源協議保護。