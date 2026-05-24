# Virtual Lab PC Assembly

An interactive drag-and-drop learning experience designed to teach users how to assemble a PC. 

## Features
- **Drag & Drop Interface:** Learn standard PC component placements with intuitive drag-and-drop interaction.
- **Accessible Design:** Full keyboard flow (Enter/Space to select, Enter to place) for accessibility.
- **Progress Tracking:** Tracks your attempts, mistakes, and automatically saves progress to `localStorage`.
- **Responsive Animations:** Polished UI feedback using `motion/react`.
- **Responsive Layout:** Adjusts gracefully between desktop and mobile devices.

## Tech Stack
- Frontend: React 19, TypeScript, Vite
- Styling: Tailwind CSS
- Icons: Lucide React
- Animations: Motion (Framer Motion)

## Performance & Optimization Checklist (Lighthouse)

To achieve a 100/100 Lighthouse score for the production deployment, refer to the following checklist:

### 1. Image Optimization
- ✅ **Use SVGs/Icons:** We use Lucide React (SVG-based) icons minimizing asset footprint.
- ⬜ **WebP Formats:** If introducing real hardware imagery, provide `WebP/AVIF` with responsive `<picture>` tags.
- ⬜ **Lazy Loading:** Add `loading="lazy"` to below-the-fold images if expanding the inventory beyond 5 parts.

### 2. CSS/JS Minification & Delivery
- ✅ **Vite Bundler:** Handled automatically. Vite uses `esbuild` for minification by default in standard build mode.
- ✅ **Code Splitting:** Rely on Vite's default chunking strategy for vendor files.
- ⬜ **Critical CSS:** For larger React apps, consider using tools like `critters` or SSG/SSR frameworks (Next.js) to inline critical styling.

### 3. Setup & Caching Headers
- ⬜ **Aggressive Caching:** On production servers (Nginx/Vercel/Netlify), set `Cache-Control: public, max-age=31536000, immutable` headers for JS/CSS assets under `/assets`.
- ⬜ **Compression:** Enable Gzip/Brotli compression at the web server layer.

### 4. Accessibility (A11y)
- ✅ **Semantic HTML & Focus State:** Handled natively via custom tab indexes and click interceptors.
- ✅ **Keyboard Parity:** Every drag action has a keyboard equivalent.
- ✅ **ARIA Labels:** Explicit labels applied to pseudo-interactive DOM elements.

## Setup Instructions

Provide standard node instructions:
1. Ensure Node.js 18+ is installed.
2. Clone the repository and navigate into the folder.
3. Install dependencies:
   ```bash
   npm install
   ```
4. Start the local server:
   ```bash
   npm run dev
   ```
5. Open your browser to `http://localhost:3000` (or as standard specified).

## Contribution Guidelines
1. Fork the repo and create your feature branch (`git checkout -b feature/amazing-feature`).
2. Adhere to TypeScript `strict` typing and standard ES lint rules.
3. Commit your changes logically (see commit message history for examples).
4. Push to the branch (`git push origin feature/amazing-feature`).
5. Open a Pull Request!
