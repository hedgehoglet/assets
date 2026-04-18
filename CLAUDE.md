# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

**Forage** by Hedgehoglet. Open asset library served at `assets.hedgehoglet.dev`. No build step, no framework, pure HTML/CSS/JS. Open the HTML files directly in a browser or use any static file server (e.g. `npx serve .`) to preview locally.

## Design system

Styles follow the same design system as `https://github.com/hedgehoglet/hedgehoglet.dev` exactly:
- Dark theme via CSS custom properties defined in `assets/style.css` (`--bg`, `--surface`, `--border`, `--text`, `--muted`, `--accent`, `--accent2`)
- All icons are inline SVGs, no icon libraries
- Scroll-reveal via `.reveal` / `.reveal.visible` classes, driven by an IntersectionObserver inlined at the bottom of `index.html`
- Animations use `fadeUp` and `gradientShift` keyframes defined in `assets/style.css`

## Adding a new asset

1. Drop the file into `assets/shared/<format>/` (e.g. `assets/shared/csv/myfile.csv`)
2. Add one entry to `assets/registry.json`:

```json
{
  "file": "myfile.csv",
  "path": "assets/shared/csv/myfile.csv",
  "icon": "📊",
  "format": "csv",
  "description": "One sentence describing the asset.",
  "tags": ["tag1", "tag2"],
  "size": "12 KB",
  "added": "2025-06-01"
}
```

The site reads `assets/registry.json` at runtime. No HTML changes needed. Format filter pills, badge colours, and search all update automatically.

## File roles

| File | Purpose |
|------|---------|
| `assets/registry.json` | Single source of truth listing every available asset |
| `assets/shared/**` | The actual asset files (any format) |
| `assets/style.css` | All styles for `index.html` |
| `assets/404.css` | Styles for `404.html` |
| `assets/logo.png` | Hedgehoglet logo (mirrored from hedgehoglet.dev) |

## Badge colours

Defined in `assets/style.css`. Currently supported: `badge-json`, `badge-csv`, `badge-yaml`, `badge-xml`, `badge-txt`, `badge-other`. Add a new `.badge-<format>` rule to support a new format visually.
