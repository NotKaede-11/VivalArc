# VivalArc Enhancement Documentation

## Latest Updates

### 🎨 Visual Polish, Snappy Motion & Panel Fixes (via KazmirBO)
*Credit to [@KazmirBO](https://github.com/KazmirBO/VivalArc) for the design patterns and fixes adapted into our fork.*

#### 1. Multi-Layered Webview Shadows & Accent URL Focus Ring
* **3-Tier Card Depth**: Replaced flat drop-shadows with multi-layered depth tokens (`--webview-shadow-light` and `--webview-shadow-dark`):
  - Tight contact shadow directly below the edge.
  - Soft ambient diffusion blur.
  - Subtle hairline border rim for crisp delineation against background wallpaper in both light and dark themes.
* **Modern URL Focus Ring**: Added `--urlbar-focus-ring` to `.UrlBar-AddressField:focus-within` using modern CSS `color-mix()` matching the current theme's accent color.

#### 2. Snappy Motion Deceleration Curve
* **Responsive Physics**: Replaced standard sluggish `ease` with `cubic-bezier(0.2, 0, 0, 1)` via `--transition-easing` and `--transition-duration: 0.18s`.
* **Smooth Micro-Interactions**: Integrated into the Helium overlay top bar drop-down and toolbar button hover animations (respects `prefers-reduced-motion`).

#### 3. Floating Panel Overlay & Icons-Only Mode Bugfixes
* **Clean Floating Drawers**: Fixed transparency, border, and backdrop-filter clipping issues on `#panels-container` and `#switch` when using Vivaldi's side panels in floating overlay or icons-only mode.

---

## Previous Updates

### 📌 Helium-Style Overlay Auto-Hide Top Bar
This fork enhances [VivalArc](https://github.com/tovifun/VivalArc) by integrating a floating Helium-style auto-hiding top bar directly into `vivalarc.css`. All original sidebar tabs, theme variables, and layout behaviors are preserved, while reclaiming vertical screen space with a smooth, distraction-free top bar that stays hidden until hovered.

#### What Was Added
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
* **[`vivalarc.css`](file:///C:/Users/Beo/Downloads/03_Personal/05_Misc/VivalArc/vivalarc.css)**: The unified stylesheet containing base VivalArc + Helium auto-hide top bar + KazmirBO visual/motion enhancements.
