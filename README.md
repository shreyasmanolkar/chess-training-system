# ♚ Grandmaster Blueprint — Elite Chess Training System

A **single-page, offline-friendly** training dashboard that lays out a structured, multi-year chess improvement program (tactics, openings, patterns, endgames, schedules, calculation, tournament prep, and curated resources).

This repository is intentionally simple: it’s primarily a single static file, `index.html`.

## What’s in this repo

- **`index.html`**: The entire app (HTML + CSS + JavaScript in one file).
- **No build tools**: No Node, no bundlers, no dependencies to install.

## Quick start

### Option A: Open the file directly (fastest)

1. Download/clone the repo.
2. Open `index.html` in your browser (Chrome/Firefox/Brave).

That’s it.

### Option B: Run a local web server (recommended)

Some browsers apply tighter rules when opening `file://` pages. Running a tiny local server is more consistent.

#### Python (installed on most systems)

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000` and click `index.html` (or it may load automatically).

#### Node (if you already have it)

```bash
npx serve .
```

#### PHP (if you have it)

```bash
php -S localhost:8000
```

## How to use the dashboard

### Navigation (tabs)

At the top there’s a sticky navigation bar with sections like:

- **Reality** (expectations, timelines, hours)
- **Blueprint** (multi-phase plan)
- **Openings / Attacks / Defense / Patterns / Memory / Masters**
- **Middlegame / Endgame**
- **Schedule / Calculation / Tournament / Resources**

Click any tab to switch sections.

### Collapsible panels

Most sections contain collapsible panels. Click a panel header to expand/collapse it.

### Keyboard shortcuts

- **Left Arrow / Right Arrow**: cycle through the top navigation tabs.

### Theme toggle (light/dark)

Use the theme toggle in the header to switch between dark and light mode.

- The selection is **saved in your browser** via `localStorage` under the key **`gmb-theme`**.
- If storage is blocked (strict privacy mode), the app still works; it just won’t persist the theme.

## Customizing the content

Everything is in `index.html`, so editing is straightforward:

- **Text/content**: Search for the section you want (e.g. `section-blueprint`, `section-endgame`, `section-schedule`) and edit the HTML.
- **Add a new tab/section**:
  1. Add a new button in the nav:
     - `<button class="nav-btn" data-section="yourid">…</button>`
  2. Add a matching section container:
     - `<div class="section" id="section-yourid"> … </div>`
  3. Keep the `data-section="yourid"` and `id="section-yourid"` pairing consistent (that’s how the JS finds the section).
- **Styling**: The CSS is in a `<style>` block in the `<head>`. Colors are defined as CSS variables under `:root`.

## Offline / network notes

- The UI uses Google Fonts loaded from:
  - `fonts.googleapis.com` (CSS)
  - `fonts.gstatic.com` (font files)
- If you want fully offline use, you can replace the Google Fonts `<link>` with locally hosted fonts (or remove it and rely on system fonts).

## Deploying (share as a website)

Because this is a static site, you can host it anywhere.

### GitHub Pages

1. Push this repository to GitHub.
2. In GitHub: **Settings → Pages**
3. Set:
   - **Source**: “Deploy from a branch”
   - **Branch**: `main` (or your default branch), folder `/ (root)`
4. Save, then open the published Pages URL.

### Netlify / Vercel / Static hosting

Upload the repo as a static site with:

- **Build command**: none
- **Output/public directory**: repository root (where `index.html` lives)

## Troubleshooting

- **The page looks unstyled**: Ensure you opened the correct `index.html` and your browser didn’t block local resources. Try the local server option.
- **Theme doesn’t persist**: Your browser may be blocking storage (private mode, strict tracking protection). The app still functions without persistence.
- **Fonts look different**: Your network may be blocking Google Fonts or you’re offline. This only affects typography.

## License

No license file is included by default. If you plan to share publicly or accept contributions, add a `LICENSE` (e.g., MIT) and clarify attribution/usage expectations.

