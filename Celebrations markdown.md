# Celebration | Premium Event Management Landing Page Guide
Welcome to the **Celebration** Luxury Event Management Landing Page project documentation. This file provides an in-depth overview of the website's architecture, premium styling tokens, interactive scripts, and guidelines for custom editing.
---
## 💎 Design System & Aesthetic Specifications
This landing page employs a **Modern Glassmorphism UI** tailored for luxury, high-end SaaS-style branding.
### 🎨 Color Palette & Visual Spec (CSS Custom Properties)
- **Background Base**: Deep rich violet-black (`#06040d`) with a secondary overlay card theme (`#0a0815`).
- **Gradients**:
  - **Primary**: Hot Pink (`#FF4FD8`) to Purple (`#7B4DFF`) to Violet (`#A855F7`).
  - **Accent**: Purple (`#7B4DFF`) to Soft Blue (`#4CC9F0`).
- **Frosted Glass Cards (`.glass-card`)**:
  - Background: `rgba(255, 255, 255, 0.03)`
  - Border: `1px solid rgba(255, 255, 255, 0.08)`
  - Backdrop Blur: `blur(16px) saturate(180%)`
  - Shadow: Elegant dark drop shadows blended with a subtle ultraviolet glow shadow.
### 🌌 Floating Ambient Blobs & Starry Background
- **Ambient Blobs**: Four slow-pulsing background gradient blobs created via pure CSS keyframe animations float organically, adding a modern sense of movement.
- **HTML5 Starry Canvas (`#particle-canvas`)**: A lightweight canvas drawing loop that seeds and animates pink and blue glowing particles that drift behind sections, reacting dynamically to browser window resizes.
---
## 📂 Project Directory Structure
The project files are modular, structured, and located under `C:\Users\Admin\.gemini\antigravity\scratch\celebration-events`:
```yaml
celebration-events/
├── index.html            # Main markup & structured semantic segments
├── package.json          # Node script dependencies (local http-server script)
├── Gemini.md             # This comprehensive developer guide
├── css/
│   └── style.css         # Complete design system styles & animations
└── js/
    └── main.js           # Multi-interactive scripts & component engines
```
---
## ⚙️ Interactive Component Anatomy
### 1. Interactive 3D Card Tilt & Tracking Glow
*Located in:* `js/main.js` & `css/style.css`
- **Logic**: Attaches mouse-movement event listeners to `.glass-card` elements. It computes the normalized coordinates of the cursor relative to the card's bounding rectangle.
- **Visuals**: Applies 3D rotation (`rotateX` & `rotateY`) while updating CSS variables `--glow-x` and `--glow-y`. The CSS uses these coordinates inside a `radial-gradient` overlay block to create a soft, tracking spotlight effect beneath the mouse.
### 2. Live Portfolio Filter Grid & Lightbox modal
*Located in:* `index.html` & `js/main.js`
- **Filtering**: Hides/shows portfolio masonry items based on `data-category` matching with dynamic CSS transitions.
- **Lightbox**: Captures clicked grid images, copies details (Source, Alt, Title, and Description), opens a full-screen blurred modal backdrop, and locks body scrolling. Keyboard listeners bind `Escape` for rapid closing.
### 3. Stat Count-Up Engine
*Located in:* `js/main.js`
- **Logic**: Leverages the browser `IntersectionObserver` API. When the statistic dashboard is scrolled into view, it runs a counting function from `0` to your specific targets (500+, 98%, 10+, 100+) using `requestAnimationFrame` for a highly fluid 60fps counter transition.
---
## 🚀 How to Run the Website
### Option A: Local Dev Server (Recommended)
You can run a local web server to bypass strict browser local security blocks (CORS) on fonts and dynamic SVG files:
1. Open PowerShell or Command Prompt.
2. Navigate to your project workspace:
   ```powershell
   cd C:\Users\Admin\.gemini\antigravity\scratch\celebration-events
   ```
3. Boot the local server:
   ```powershell
   npm run dev
   ```
4. Access the site in your browser at: **[http://127.0.0.1:3000](http://127.0.0.1:3000)**
### Option B: Standalone File Launch
If you aren't using a terminal, you can double-click **`index.html`** in your file explorer to open the page directly.
---
## 🛠️ Guidelines for Customization
### Changing Text and Services
- To change descriptions or services headings, modify the respective content fields inside [index.html](file:///C:/Users/Admin/.gemini/antigravity/scratch/celebration-events/index.html).
- To add a new service, copy a `glass-card service-card` block inside `index.html` and reference your chosen icon ID inside the SVG `<use>` tag.
### Customizing Design Tokens & Theme Colors
- To modify colors, change the HSL/HEX properties declared inside the `:root` block of [css/style.css](file:///C:/Users/Admin/.gemini/antigravity/scratch/celebration-events/css/style.css).
- Standard variables `--color-pink`, `--color-purple`, `--color-violet`, and `--color-blue` control the entire site's ambient blobs, gradient buttons, tracking card glows, and text decorations.