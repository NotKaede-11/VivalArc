# VivalArc Enhancement Documentation

## Helium-Style Overlay Auto-Hide Top Bar

### 📌 Overview
This fork enhances [VivalArc](https://github.com/tovifun/VivalArc) by integrating a floating Helium-style auto-hiding top bar directly into `vivalarc.css`. All original sidebar tabs, theme variables, and layout behaviors are preserved, while reclaiming vertical screen space with a smooth, distraction-free top bar that stays hidden until hovered.

---

### 🛠️ What Was Added

#### Floating Overlay Top Bar (`#header`)
* **Fixed Overlay Positioning**:
  - `position: fixed !important; top: 0; left: 0; right: 0; height: 38px !important; z-index: 99999 !important;`.
  - Floats above the viewport without displacing the webpage or sidebar downwards.
* **Smooth Auto-Hide with Anti-Flicker Debounce**:
  - Hidden by default with a subtle 7px peek edge (`transform: translateY(calc(-100% + 7px)); opacity: 0;`).
  - Instantly reveals on hover or focus (`transform: translateY(0); opacity: 1; transition-delay: 0s;`).
  - **140ms debounce delay** (`transition-delay: 0.14s;`) on mouse-out to eliminate cursor stutter or flicker.
* **14px Invisible Bottom Apron**:
  - Implemented via `#header::after` (`height: 14px; top: 100%; pointer-events: auto;`), ensuring continuous hover registration during rapid cursor passes.
* **Spacious Layout & Native Controls**:
  - Centered draggable window title with dragging isolated strictly to the title text.
  - Helium-style pill button for the Vivaldi menu and clean Windows 11 window controls (minimize, maximize, red hover on close).
  - 3px top gutter alignment on webview and tab container.

---

### 📂 File Structure
* **[`vivalarc.css`](file:///C:/Users/Beo/Downloads/03_Personal/05_Misc/VivalArc/vivalarc.css)**: The unified stylesheet containing base VivalArc + Helium auto-hide top bar.
