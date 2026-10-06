# Vellum — Offline Illustration Studio

A self-contained vector illustration tool that runs entirely in the browser — no
build step, no server, no dependencies. One HTML file, works offline once loaded.

## Features

**Drawing**
- Pen tool — click for corner points, click-drag for bezier curve handles,
  click the green start point to close, Enter to finish an open path, Esc to cancel
- Shapes — rectangle (corner radius), ellipse, polygon (adjustable sides), star
  (adjustable points + inner radius), line, text
- Reference photo — place an image to trace over (added locked, dimmed, sent to back)

**Selection & editing**
- Select tool — move, resize (corner handles), rotate (on-canvas handle,
  shift to snap to 15°), shift-constrained proportional resize
- Direct Select tool — edit individual anchor points and bezier handles on
  any pen path: drag an anchor to move it, drag a handle to reshape a curve,
  Alt+click an anchor to strip its handles into a corner, select + Delete to
  remove a point
- Multi-select — shift-click, or drag a marquee over empty canvas
- Group / Ungroup (Ctrl+G / Ctrl+Shift+G)
- Align (6 directions) and Distribute (horizontal/vertical)
- Copy / Paste / Duplicate (Ctrl+C/V/D), arrow-key nudge (1px, 10px with Shift)
- Hand tool for panning (or hold Space with any tool), Eraser tool
- Layers panel — visibility, lock, reorder, rename, grouping shown inline

**Style**
- Solid, linear, and radial gradient fills
- Stroke color/opacity/width/cap/dash
- Effects: Drop Shadow, Gaussian Blur, Outer Glow, Inner Shadow
- Color Adjustments: hue, saturation, brightness, contrast, grayscale
- Blend modes (Multiply, Screen, Overlay, Darken, Lighten, Difference)

**File handling**
- Undo / redo, Export to SVG (vector) and PNG (2x raster)
- Save / Open a project as JSON
- Autosave — falls back from the host app's storage API to `localStorage`

## Known limitations

This is a from-scratch browser tool, not a reimplementation of Adobe
Illustrator. Notably missing, by design:
- No Pathfinder / boolean path operations (union, subtract, intersect, exclude)
- No pattern fills or gradient meshes
- No multiple artboards
- No type-on-a-path or Shape Builder tool
- Direct Select only works on pen-drawn paths, not rectangles/ellipses/polygons directly

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
| `A` | Direct Select tool |
| `P` | Pen tool |
| `R` | Rectangle |
| `O` | Ellipse |
| `G` | Polygon |
| `S` | Star |
| `L` | Line |
| `T` | Text |
| `I` | Eyedropper |
| `H` | Hand (pan) |
| `E` | Eraser |
| `Space` (hold) | Temporary pan with any tool |
| `Ctrl/Cmd + Z` | Undo |
| `Ctrl/Cmd + Y` (or Shift+Z) | Redo |
| `Ctrl/Cmd + C / V / D` | Copy / Paste / Duplicate |
| `Ctrl/Cmd + G` / `Ctrl/Cmd + Shift + G` | Group / Ungroup |
| `Delete` / `Backspace` | Delete selection (or selected anchor in Direct Select) |
| `Arrow keys` | Nudge selection (Shift = 10px) |
| `Enter` | Finish an open pen path |
| `Esc` | Cancel current pen path / exit anchor edit / deselect |
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
