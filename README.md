# Vellum — Offline Illustration Studio

A self-contained vector illustration tool that runs entirely in the browser — no
build step, no server, no dependencies. One HTML file, works offline once loaded.

## Features

- **Pen tool** — click for corner points, click-drag for bezier curve handles,
  click the start point to close a path, Enter to finish an open path, Esc to cancel
- **Shapes** — rectangle (with corner radius), ellipse, line, text
- **Select & transform** — move, resize via corner handles, rotate, numeric
  X / Y / W / H entry
- **Layers panel** — visibility toggle, lock, reorder (bring to front / send to
  back), rename
- **Style controls** — fill and stroke color with opacity, stroke width / cap /
  dash, recent-color swatches, eyedropper
- **Undo / redo**, duplicate, delete
- **Export** — SVG (real vector output) and PNG (2x raster render)
- **Save / Open** a project as JSON
- **Autosave** — falls back from the host app's storage API to `localStorage`,
  so work survives a refresh with zero setup

## Usage

Just open `index.html` in a browser. No install, no build, no internet
connection required after the page loads (Google Fonts is fetched on first
load; the app still works if that request fails).

### Run locally

```bash
git clone https://github.com/<your-username>/vellum.git
cd vellum
open index.html   # or just double-click the file
```

### Deploy to GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`,
   branch `main`, folder `/ (root)`.
4. Your app will be live at `https://<your-username>.github.io/<repo-name>/`.

A ready-made GitHub Actions workflow is also included at
`.github/workflows/deploy.yml` if you'd rather deploy via Actions — enable it
by setting **Source** to `GitHub Actions` in the Pages settings instead.

## Keyboard shortcuts

| Key | Action |
|---|---|
| `V` | Select tool |
| `P` | Pen tool |
| `R` | Rectangle |
| `O` | Ellipse |
| `L` | Line |
| `T` | Text |
| `I` | Eyedropper |
| `Ctrl/Cmd + Z` | Undo |
| `Ctrl/Cmd + Y` (or Shift+Z) | Redo |
| `Delete` / `Backspace` | Delete selected shape |
| `Enter` | Finish an open pen path |
| `Esc` | Cancel current pen path / deselect |
| `Ctrl/Cmd + scroll` | Zoom |

## Project structure

```
.
├── index.html    # the entire app — markup, styles, and logic in one file
├── README.md
└── LICENSE
```

## License

MIT — see [LICENSE](LICENSE).
